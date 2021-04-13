---
title: Microsoft Defender para endpoint en Linux
ms.reviewer: ''
description: Describe cómo instalar y usar ATP de Microsoft Defender para Linux.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 0fea9d4dd46be2a77ea27728787a43b5273f92f5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687762"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender para endpoint en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se describe cómo instalar, configurar, actualizar y usar Microsoft Defender para Endpoint en Linux.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Microsoft Defender para Endpoint en Linux lleve a problemas de rendimiento y efectos secundarios impredecibles. Si la protección de extremo que no es de Microsoft es un requisito absoluto en su entorno, puede aprovechar de forma segura la funcionalidad de Defender for Endpoint for Linux EDR después de configurar la funcionalidad antivirus para que se ejecute en modo [pasivo.](linux-preferences.md#enable--disable-passive-mode)

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Cómo instalar Microsoft Defender para Endpoint en Linux

### <a name="prerequisites"></a>Requisitos previos

- Acceso al portal del Centro de seguridad de Microsoft Defender
- Distribución de Linux con [el administrador del](https://systemd.io/) sistema con sistema
- Experiencia de nivel principiante en scripts de Linux y BASH
- Privilegios administrativos en el dispositivo (en caso de implementación manual)

### <a name="installation-instructions"></a>Instrucciones de instalación

Existen varios métodos y herramientas de implementación que puede usar para instalar y configurar Microsoft Defender para Endpoint en Linux.

En general, debe seguir los siguientes pasos:

- Asegúrese de que tiene una suscripción de Microsoft Defender para endpoint y de que tiene acceso al portal de [Microsoft Defender para endpoint](microsoft-defender-security-center.md).
- Implemente Microsoft Defender para Endpoint en Linux mediante uno de los siguientes métodos de implementación:
  - La herramienta de línea de comandos:
    - [Implementación manual](linux-install-manually.md)
  - Herramientas de administración de terceros:
    - [Implementar con la herramienta de administración de configuración de Puppet](linux-install-with-puppet.md)
    - [Implementar con una herramienta de administración de configuración de Ansible](linux-install-with-ansible.md)

Si experimenta algún error de instalación, consulte [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).

### <a name="system-requirements"></a>Requisitos del sistema

- Versiones y distribuciones de servidor Linux compatibles:

  - Red Hat Enterprise Linux 7.2 o posterior
  - CentOS 7.2 o superior
  - Ubuntu 16,04 LTS o superior LTS
  - Debian 9 o posterior
  - SUSE Linux Enterprise Server 12 o posterior
  - Oracle Linux 7.2 o posterior

- Versión mínima del kernel 3.10.0-327
- La `fanotify` opción kernel debe estar habilitada
  > [!CAUTION]
  > No se admite la ejecución de Defender para Endpoint para Linux en paralelo con otras soluciones de seguridad `fanotify` basadas en. Puede dar lugar a resultados impredecibles, incluida la suspensión del sistema operativo.

- Espacio en disco: 1 GB
- /opt/microsoft/mdatp/sbin/wdavdaemon requiere permiso ejecutable. Para obtener más información, vea "Ensure that the daemon has executable permission" en [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).
- Memoria: 1 GB
    > [!NOTE]
    > Asegúrese de que tiene espacio libre en disco en /var.

- Actualmente, la solución proporciona protección en tiempo real para los siguientes tipos de sistema de archivos:

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

Después de habilitar el servicio, es posible que deba configurar la red o el firewall para permitir conexiones salientes entre él y los puntos de conexión.

- El marco de auditoría ( `auditd` ) debe estar habilitado.
  > [!NOTE]
  > Los eventos del sistema capturados por las reglas agregadas se agregarán a (s) y pueden afectar a la auditoría de host y `/etc/audit/rules.d/` `audit.log` a la colección ascendente. Los eventos agregados por Microsoft Defender para Endpoint en Linux se etiquetarán con `mdatp` clave.

### <a name="network-connections"></a>Conexiones de red

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Debe asegurarse de que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL. Si lo hay, es posible que deba crear una regla *de* permitir específicamente para ellos.

|**Hoja de cálculo de la lista de dominios**|**Descripción**|
|:-----|:-----|
|![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión](images/mdatp-urls.png)<br/>  | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo. <br><br>[Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> Para obtener una lista de direcciones URL más específica, vea [Configure proxy and Internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).

Defender for Endpoint puede detectar un servidor proxy mediante los siguientes métodos de detección:
- Proxy transparente
- Configuración manual de proxy estático

Si un proxy o firewall bloquea el tráfico anónimo, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente. Para los servidores proxy transparentes, no se necesita ninguna configuración adicional para Defender for Endpoint. Para proxy estático, siga los pasos descritos en [Configuración manual de proxy estático.](linux-static-proxy-configuration.md)

> [!WARNING]
> Pac, WPAD y proxies autenticados no son compatibles. Asegúrese de que solo se usa un proxy estático o un proxy transparente.
>
> Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad. Configure una excepción para la inspección SSL y el servidor proxy para pasar directamente los datos de Defender para Endpoint en Linux a las direcciones URL relevantes sin interceptación. Agregar el certificado de interceptación al almacén global no permitirá la interceptación.

Para ver los pasos de solución de problemas, consulte [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Cómo actualizar Microsoft Defender para endpoint en Linux

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características. Para actualizar Microsoft Defender para Endpoint en Linux, consulte [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Cómo configurar Microsoft Defender para endpoint en Linux

Las instrucciones sobre cómo configurar el producto en entornos empresariales están disponibles en Establecer preferencias para [Microsoft Defender para Endpoint en Linux.](linux-preferences.md)

## <a name="resources"></a>Recursos

- Para obtener más información sobre el registro, la desinstalación u otros temas, vea [Resources](linux-resources.md).
