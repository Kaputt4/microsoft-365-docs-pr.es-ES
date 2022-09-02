---
title: Solución de problemas de instalación de Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Solución de problemas de instalación de Microsoft Defender para punto de conexión en Linux
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, instalación
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 761cc1ea72bfccba98145daa2e8649f33268997e
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521727"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solución de problemas de instalación de Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-that-the-installation-succeeded"></a>Comprobación de que la instalación se realizó correctamente

Un error en la instalación puede dar lugar o no a un mensaje de error significativo por parte del administrador de paquetes. Para comprobar si la instalación se realizó correctamente, obtenga y compruebe los registros de instalación mediante:

```bash
 sudo journalctl --no-pager|grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

Una salida del comando anterior con la fecha y hora correctas de instalación indica que se ha realizado correctamente.

Compruebe también la [configuración del cliente](linux-install-manually.md#client-configuration) para comprobar el estado del producto y detectar el archivo de texto EICAR.

## <a name="make-sure-you-have-the-correct-package"></a>Asegúrese de que tiene el paquete correcto.

Compruebe que el paquete que está instalando coincide con la distribución y la versión del host.

<br>

****

|paquete|Distribución|
|---|---|
|mdatp-rhel8. Linux.x86_64.rpm|Oracle, RHEL y CentOS 8.x|
|mdatp-sles12. Linux.x86_64.rpm|SUSE Linux Enterprise Server 12.x|
|mdatp-sles15. Linux.x86_64.rpm|SUSE Linux Enterprise Server 15.x|
|mdatp. Linux.x86_64.rpm|Oracle, RHEL y CentOS 7.x|
|mdatp. Linux.x86_64.deb|Debian y Ubuntu 16.04, 18.04 y 20.04|
|

Para la [implementación manual](linux-install-manually.md), asegúrese de que se ha elegido la distribución y la versión correctas.

## <a name="installation-failed"></a>Error de instalación

Compruebe si el servicio Defender para punto de conexión se está ejecutando:

```bash
service mdatp status
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

## <a name="steps-to-troubleshoot-if-the-mdatp-service-isnt-running"></a>Pasos para solucionar problemas si el servicio mdatp no se está ejecutando

1. Compruebe si existe el usuario "mdatp":

    ```bash
    id "mdatp"
    ```

    Si no hay ninguna salida, ejecute

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Intente habilitar y reiniciar el servicio mediante:

    ```bash
    sudo service mdatp start
    ```

    ```bash
    sudo service mdatp restart
    ```

3. Si no se encuentra mdatp.service al ejecutar el comando anterior, ejecute:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path> 
    ```

    donde `<systemd_path>` es `/lib/systemd/system` para distribuciones de Ubuntu y Debian y /usr/lib/systemd/system' para Rhel, CentOS, Oracle y SLES. A continuación, vuelva a ejecutar el paso 2.

4. Si los pasos anteriores no funcionan, compruebe si SELinux está instalado y en modo de aplicación. Si es así, intente establecerlo en modo permisivo (preferiblemente) o deshabilitado. Se puede hacer estableciendo el parámetro `SELINUX` en "permisivo" o "deshabilitado" en el `/etc/selinux/config` archivo, seguido del reinicio. Consulte la página man-page de selinux para obtener más detalles.
Ahora intente reiniciar el servicio mdatp mediante el paso 2. Revierta el cambio de configuración inmediatamente por motivos de seguridad después de probarlo y reiniciar.

5. Si `/opt` el directorio es un vínculo simbólico, cree un montaje de enlace para `/opt/microsoft`.

6. Asegúrese de que el demonio tiene permiso ejecutable.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Si el demonio no tiene permisos ejecutables, consiéndolo ejecutable mediante:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    y vuelva a intentar ejecutar el paso 2.

7. Asegúrese de que el sistema de archivos que contiene wdavdaemon no esté montado con "noexec".

## <a name="if-the-defender-for-endpoint-service-is-running-but-the-eicar-text-file-detection-doesnt-work"></a>Si el servicio Defender para punto de conexión se está ejecutando, pero la detección de archivos de texto EICAR no funciona

1. Compruebe el tipo de sistema de archivos mediante:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    Los sistemas de archivos admitidos actualmente para la actividad de acceso se enumeran [aquí](microsoft-defender-endpoint-linux.md#system-requirements). No se examinarán los archivos que estén fuera de estos sistemas de archivos.

## <a name="command-line-tool-mdatp-isnt-working"></a>La herramienta de línea de comandos "mdatp" no funciona

1. Si al ejecutar la herramienta `mdatp` de línea de comandos se produce un error `command not found`, ejecute el siguiente comando:

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

    La ruta de acceso a un archivo ZIP que contiene los registros se mostrará como una salida. Póngase en contacto con nuestro servicio de atención al cliente con estos registros.
