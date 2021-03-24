---
title: Solucionar problemas de instalación de ATP de Microsoft Defender para Linux
ms.reviewer: ''
description: Solucionar problemas de instalación de ATP de Microsoft Defender para Linux
keywords: microsoft, defender, atp, linux, instalación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a83794675a20a61f4075e0f9c729cef95400e64e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073747"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Solucionar problemas de instalación de Microsoft Defender para Endpoint para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>Comprobar si la instalación se ha instalado correctamente

Un error en la instalación puede o no provocar un mensaje de error significativo por parte del administrador de paquetes. Para comprobar si la instalación se ha hecho correctamente, obtenga y compruebe los registros de instalación mediante:

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

Un resultado del comando anterior con la fecha y hora correctas de instalación indica que se ha correcto.

Compruebe también la [configuración del cliente](linux-install-manually.md#client-configuration) para comprobar el estado del producto y detectar el archivo de texto EICAR.

## <a name="make-sure-you-have-the-correct-package"></a>Asegúrese de que tiene el paquete correcto

Tenga en cuenta que el paquete que va a instalar coincide con la distribución y la versión del host.

| paquete                       | distribución                             |
|-------------------------------|------------------------------------------|
| mdatp-rhel8. Linux.x86_64.rpm  | Oracle, RHEL y CentOS 8.x              |
| mdatp-sles12. Linux.x86_64.rpm | SuSE Linux Enterprise Server 12.x        |
| mdatp-sles15. Linux.x86_64.rpm | SuSE Linux Enterprise Server 15.x        |
| mdatp. Linux.x86_64.rpm        | Oracle, RHEL y CentOS 7.x              |
| mdatp. Linux.x86_64.deb        | Debian y Ubuntu 16.04, 18.04 y 20.04 |

Para [la implementación manual,](linux-install-manually.md)asegúrese de que se han elegido el distro y la versión correctas.

## <a name="installation-failed"></a>Error en la instalación

Compruebe si el servicio mdatp se está ejecutando:

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>Pasos para solucionar problemas si el servicio mdatp no se está ejecutando

1. Compruebe si existe el usuario "mdatp":

    ```bash
    id "mdatp"
    ```

    Si no hay salida, ejecute

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Intente habilitar y reiniciar el servicio con:

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. Si no se encuentra mdatp.service al ejecutar el comando anterior, ejecute:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    donde ```<systemd_path>``` está para las distribuciones de Ubuntu y Debian y para ```/lib/systemd/system``` ```/usr/lib/systemd/system``` Rhel, CentOS, Oracle y SLES.
   A continuación, vuelva a ejecutar el paso 2.

4. Si los pasos anteriores no funcionan, compruebe si SELinux está instalado y en modo de aplicación. Si es así, intenta establecerlo en modo permisivo (preferiblemente) o deshabilitado. Se puede hacer estableciendo el parámetro en "permisivo" o "deshabilitado" en el archivo, seguido `SELINUX` `/etc/selinux/config` del reinicio. Consulta la página man de selinux para obtener más detalles.
Ahora intente reiniciar el servicio mdatp mediante el paso 2. Revert the configuration change immediately though for security reasons after trying it and reboot.

5. Si `/opt` el directorio es un vínculo simbólico, cree un montaje de enlace para `/opt/microsoft` .

6. Asegúrese de que el demonio tiene permiso ejecutable.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Si el demonio no tiene permisos ejecutables, haga que sea ejecutable mediante:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    y vuelva a intentar ejecutar el paso 2.

7. Asegúrese de que el sistema de archivos que contiene wdavdaemon no esté montado con "noexec".

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>Si se está ejecutando el servicio mdatp, pero la detección de archivos de texto EICAR no funciona

1. Compruebe el tipo de sistema de archivos mediante:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    Los sistemas de archivos compatibles actualmente para la actividad en tiempo de acceso se enumeran [aquí.](microsoft-defender-endpoint-linux.md#system-requirements) Los archivos fuera de estos sistemas de archivos no se examinarán.

## <a name="command-line-tool-mdatp-isnt-working"></a>La herramienta de línea de comandos "mdatp" no funciona

1. Si al ejecutar la herramienta de línea de `mdatp` comandos se produce un `command not found` error, ejecute el siguiente comando:

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    e inténtelo de nuevo.

    Si ninguno de los pasos anteriores ayuda, recopile los registros de diagnóstico:

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    La ruta de acceso a un archivo zip que contiene los registros se mostrará como salida. Llegue a nuestro servicio de atención al cliente con estos registros.
