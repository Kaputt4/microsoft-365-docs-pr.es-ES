---
title: Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para Endpoint en Linux.
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
ms.prod: m365-security
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: eea9aca5e1c6ac791581e6fab93c768a06b0dc98
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156525"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se describe cómo instalar, configurar, actualizar y usar Microsoft Defender para Endpoint en Linux.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Microsoft Defender para Endpoint en Linux lleve a problemas de rendimiento y efectos secundarios impredecibles. Si la protección de extremo que no es de Microsoft es un requisito absoluto en su entorno, puede aprovechar de forma segura la funcionalidad de Defender para endpoint en Linux EDR después de configurar la funcionalidad antivirus para que se ejecute en modo [pasivo](linux-preferences.md#enable--disable-passive-mode).

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Cómo instalar Microsoft Defender para Endpoint en Linux

### <a name="prerequisites"></a>Requisitos previos

- Acceso al portal de Microsoft 365 Defender web
- Distribución de Linux con [el administrador del](https://systemd.io/) sistema con sistema
- Experiencia de nivel principiante en scripts de Linux y BASH
- Privilegios administrativos en el dispositivo (en caso de implementación manual)

> [!NOTE]
> El agente de Microsoft Defender para Endpoint en Linux es independiente [del agente OMS](/azure/azure-monitor/agents/agents-overview#log-analytics-agent). Microsoft Defender para endpoint se basa en su propia canalización de telemetría independiente.


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
    - [Implementar con la herramienta de administración de configuración de Chef](linux-deploy-defender-for-endpoint-with-chef.md)

Si experimenta algún error de instalación, consulte [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).

> [!NOTE]
> No se admite la instalación de Microsoft Defender para Endpoint en otra ubicación que no sea la ruta de instalación predeterminada. 

### <a name="system-requirements"></a>Requisitos del sistema

- Distribuciones de servidor Linux compatibles y versiones x64 (AMD64/EM64T):

  - Red Hat Enterprise Linux 6.7 o posterior
  - Red Hat Enterprise Linux 7.2 o posterior
  - Red Hat Enterprise Linux 8.x
  - CentOS 6,7 o superior 
  - CentOS 7.2 o superior
  - Ubuntu 16,04 LTS o superior LTS
  - Debian 9 o posterior
  - SUSE Linux Enterprise Server 12 o posterior
  - Oracle Linux 7.2 o posterior
  - Amazon Linux 2
  - Fedora 33 o posterior

    > [!NOTE]
    > Las distribuciones y las versiones que no se enumeran explícitamente no son compatibles (incluso si se derivan de las distribuciones admitidas oficialmente).


    Para Red Hat Enterprise Linux 6 y CentOS 6, la lista de versiones de kernel compatibles son:
       - Para 6.7: 2.6.32-573.* 
       - Para 6.8: 2.6.32-642.* 
       - Para 6.9: 2.6.32-696.* 
       - Para la 6.10: 2.6.32.754.2.1.el6.x86_64 a 2.6.32-754.41.2:

 > [!NOTE]
 > Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico. Las versiones anteriores a las que se enumeran en esta sección solo se proporcionan para soporte técnico de actualización.

    Lista de versiones:

    - 2.6.32-754.2.1.el6.x86_64 
    - 2.6.32-754.17.1.el6.x86_64
    - 2.6.32-754.29.1.el6.x86_64
    - 2.6.32-754.3.5.el6.x86_64 
    - 2.6.32-754.18.2.el6.x86_64
    - 2.6.32-754.29.2.el6.x86_64
    - 2.6.32-754.6.3.el6.x86_64 
    - 2.6.32-754.22.1.el6.x86_64
    - 2.6.32-754.30.2.el6.x86_64
    - 2.6.32-754.9.1.el6.x86_64 
    - 2.6.32-754.23.1.el6.x86_64
    - 2.6.32-754.33.1.el6.x86_64
    - 2.6.32-754.10.1.el6.x86_64
    - 2.6.32-754.24.2.el6.x86_64
    - 2.6.32-754.35.1.el6.x86_64
    - 2.6.32-754.11.1.el6.x86_64
    - 2.6.32-754.24.3.el6.x86_64
    - 2.6.32-754.39.1.el6.x86_64
    - 2.6.32-754.12.1.el6.x86_64
    - 2.6.32-754.25.1.el6.x86_64
    - 2.6.32-754.41.2.el6.x86_64
    - 2.6.32-754.14.2.el6.x86_64
    - 2.6.32-754.27.1.el6.x86_64
    - 2.6.32-754.15.3.el6.x86_64
    - 2.6.32-754.28.1.el6.x86_64       


- Versión mínima del kernel 3.10.0-327

- La `fanotify` opción kernel debe estar habilitada

  > [!CAUTION]
  > No se admite la ejecución de Defender para Endpoint en Linux en paralelo con otras soluciones de seguridad `fanotify` basadas en. Puede dar lugar a resultados impredecibles, incluida la suspensión del sistema operativo.

- Espacio en disco: 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon requiere permiso ejecutable. Para obtener más información, vea "Asegúrese de que el demonio tiene permiso ejecutable" en Solucionar problemas de instalación de [Microsoft Defender para Endpoint en Linux](/microsoft-365/security/defender-endpoint/linux-support-install).

- Núcleos: 2 mínimos, 4 preferidos

- Memoria: 1 GB como mínimo, 4 preferidos

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

### <a name="configuring-exclusions"></a>Configuración de exclusiones

Al agregar exclusiones a Antivirus de Microsoft Defender, debe tener en cuenta los errores de [exclusión comunes para Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)

### <a name="network-connections"></a>Conexiones de red

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Debe asegurarse de que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL. Si lo hay, es posible que deba crear una regla *de* permitir específicamente para ellos.

<br>

****

|Hoja de cálculo de la lista de dominios|Descripción|
|---|---|
|![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión.](images/mdatp-urls.png)|Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo. <p> Descargue la hoja de [cálculo aquí](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).|
|||

> [!NOTE]
> Para obtener una lista de direcciones URL más específica, vea [Configure proxy and Internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).

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

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Cómo configurar Microsoft Defender para punto de conexión en Linux

Las instrucciones sobre cómo configurar el producto en entornos empresariales están disponibles en Establecer preferencias para [Microsoft Defender para Endpoint en Linux.](linux-preferences.md)

## <a name="common-applications-to-microsoft-defender-for-endpoint-can-impact"></a>Las aplicaciones comunes para Microsoft Defender para endpoint pueden afectar

Las cargas de trabajo de E/S elevadas de determinadas aplicaciones pueden experimentar problemas de rendimiento cuando se instala Microsoft Defender para endpoint. Estas incluyen aplicaciones para escenarios para desarrolladores como Jenkins y Jira, y cargas de trabajo de base de datos como OracleDB y Postgres. Si experimenta una degradación del rendimiento, considere la posibilidad de establecer exclusiones para aplicaciones de confianza, teniendo en [cuenta](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus) los errores de exclusión Antivirus de Microsoft Defender comunes. Para obtener instrucciones adicionales, considere la posibilidad de consultar documentación sobre las exclusiones antivirus de aplicaciones de terceros.

## <a name="resources"></a>Recursos

- Para obtener más información sobre el registro, la desinstalación u otros temas, vea [Resources](linux-resources.md).
