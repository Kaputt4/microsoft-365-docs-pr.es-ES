---
title: Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para punto de conexión en Linux.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 166750a65ac8a7c15a58f1cbd0270ea6bd511546
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734459"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se describe cómo instalar, configurar, actualizar y usar Microsoft Defender para punto de conexión en Linux.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Microsoft Defender para punto de conexión en Linux genere problemas de rendimiento y efectos secundarios impredecibles. Si la protección de puntos de conexión que no son de Microsoft es un requisito absoluto en su entorno, puede aprovechar con seguridad la funcionalidad EDR de Defender para punto de conexión en Linux después de configurar la funcionalidad antivirus para que se ejecute en [modo pasivo](linux-preferences.md#enforcement-level-for-antivirus-engine).

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Instalación de Microsoft Defender para punto de conexión en Linux

Microsoft Defender para punto de conexión para Linux incluye funcionalidades de detección y respuesta de puntos de conexión y antimalware (EDR). 


### <a name="prerequisites"></a>Requisitos previos

- Acceso al portal de Microsoft 365 Defender
- Distribución de Linux mediante el administrador del sistema [systemd](https://systemd.io/)

  >[!NOTE]
  >La distribución de Linux mediante el administrador del sistema, excepto para RHEL/CentOS 6.x, admite SystemV y Upstart.

- Experiencia de nivel principiante en scripting de Linux y BASH
- Privilegios administrativos en el dispositivo (en caso de implementación manual)

> [!NOTE]
> Microsoft Defender para punto de conexión en el agente de Linux es independiente del [agente de OMS](/azure/azure-monitor/agents/agents-overview#log-analytics-agent). Microsoft Defender para punto de conexión se basa en su propia canalización de telemetría independiente.


### <a name="installation-instructions"></a>Instrucciones de instalación

Hay varios métodos y herramientas de implementación que puede usar para instalar y configurar Microsoft Defender para punto de conexión en Linux.

En general, debe realizar los pasos siguientes:

- Asegúrese de que tiene una suscripción Microsoft Defender para punto de conexión.
- Implemente Microsoft Defender para punto de conexión en Linux mediante uno de los métodos de implementación siguientes:
  - La herramienta de línea de comandos:
    - [Implementación manual](linux-install-manually.md)
  - Herramientas de administración de terceros:
    - [Implementación mediante la herramienta de administración de configuración de Puppet](linux-install-with-puppet.md)
    - [Implementación mediante la herramienta de administración de configuración de Ansible](linux-install-with-ansible.md)
    - [Implementación mediante la herramienta de administración de configuración de Chef](linux-deploy-defender-for-endpoint-with-chef.md)

Si experimenta algún error de instalación, consulte [Solución de problemas de errores de instalación en Microsoft Defender para punto de conexión en Linux](linux-support-install.md).

> [!NOTE]
> No se admite la instalación de Microsoft Defender para punto de conexión en ninguna otra ubicación que no sea la ruta de instalación predeterminada. 

> [!NOTE]
> Microsoft Defender para punto de conexión en Linux crea un usuario "mdatp" con UID y GID aleatorios. Si desea controlar el UID y el GID, cree un usuario "mdatp" antes de la instalación mediante la opción de shell "/usr/sbin/nologin".
> Por ejemplo: `mdatp:x:UID:GID::/home/mdatp:/usr/sbin/nologin`.

### <a name="system-requirements"></a>Requisitos del sistema

> [!NOTE]
> La compatibilidad con Red Hat Enterprise Linux y CentOS 6.7+ a 6.10+ está en versión preliminar.

- Distribuciones de servidores Linux compatibles y versiones x64 (AMD64/EM64T) y x86_64:

  - Red Hat Enterprise Linux 6.7 o superior (versión preliminar)
  - Red Hat Enterprise Linux 7.2 o superior
  - Red Hat Enterprise Linux 8.x
  - Red Hat Enterprise Linux 9.x
  - CentOS 6.7 o superior (versión preliminar)
  - CentOS 7.2 o superior
  - Ubuntu 16.04 LTS o posterior LTS
  - Debian 9 o superior
  - SUSE Linux Enterprise Server 12 o superior
  - Oracle Linux 7.2 o superior
  - Oracle Linux 8.x
  - Amazon Linux 2
  - Fedora 33 o superior

    > [!NOTE]
    > Las distribuciones y versiones que no se enumeran explícitamente no son compatibles (incluso si se derivan de las distribuciones admitidas oficialmente).




- Lista de versiones de kernel admitidas
  > [!NOTE]
  > Microsoft Defender para punto de conexión en Red Hat Enterprise Linux y CentOS : 6.7 a 6.10 es una solución basada en kernel. Debe comprobar que se admite la versión del kernel antes de actualizar a una versión más reciente del kernel. Consulte la lista siguiente para obtener la lista de kernels admitidos.
  > Microsoft Defender para punto de conexión para todas las demás distribuciones y versiones admitidas es independiente de la versión del kernel. Con un requisito mínimo para que la versión del kernel sea igual o superior a 3.10.0-327.

  - La `fanotify` opción kernel debe estar habilitada
  - Red Hat Enterprise Linux 6 y CentOS 6:
    - Para la versión 6.7: 2.6.32-573.*
    - Para la versión 6.8: 2.6.32-642.*
    - Para 6.9: 2.6.32-696.* (excepto 2.6.32-696.el6.x86_64)
    - Para la versión 6.10: 2.6.32.754.2.1.el6.x86_64 a 2.6.32-754.48.1:
    
       - 2.6.32-754.10.1.el6.x86_64
       - 2.6.32-754.11.1.el6.x86_64
       - 2.6.32-754.12.1.el6.x86_64
       - 2.6.32-754.14.2.el6.x86_64
       - 2.6.32-754.15.3.el6.x86_64
       - 2.6.32-754.17.1.el6.x86_64
       - 2.6.32-754.18.2.el6.x86_64
       - 2.6.32-754.2.1.el6.x86_64
       - 2.6.32-754.22.1.el6.x86_64
       - 2.6.32-754.23.1.el6.x86_64
       - 2.6.32-754.24.2.el6.x86_64
       - 2.6.32-754.24.3.el6.x86_64
       - 2.6.32-754.25.1.el6.x86_64
       - 2.6.32-754.27.1.el6.x86_64
       - 2.6.32-754.28.1.el6.x86_64
       - 2.6.32-754.29.1.el6.x86_64
       - 2.6.32-754.29.2.el6.x86_64
       - 2.6.32-754.3.5.el6.x86_64
       - 2.6.32-754.30.2.el6.x86_64
       - 2.6.32-754.33.1.el6.x86_64
       - 2.6.32-754.35.1.el6.x86_64
       - 2.6.32-754.39.1.el6.x86_64
       - 2.6.32-754.41.2.el6.x86_64
       - 2.6.32-754.43.1.el6.x86_64
       - 2.6.32-754.47.1.el6.x86_64
       - 2.6.32-754.48.1.el6.x86_64
       - 2.6.32-754.6.3.el6.x86_64
       - 2.6.32-754.9.1.el6.x86_64

 > [!NOTE]
 > Una vez publicada la nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce solo al soporte técnico. Las versiones anteriores a las que se enumeran en esta sección se proporcionan solo para soporte técnico de actualización.


  > [!CAUTION]
  > No se admite la ejecución de Defender para punto de conexión en Linux en paralelo con otras `fanotify`soluciones de seguridad basadas en . Puede dar lugar a resultados imprevisibles, incluida la suspensión del sistema operativo.

- Espacio en disco: 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon requiere permiso ejecutable. Para obtener más información, consulte "Asegúrese de que el demonio tiene permiso ejecutable" en [Solución de problemas de instalación de Microsoft Defender para punto de conexión en Linux](/microsoft-365/security/defender-endpoint/linux-support-install).

- Núcleos: 2 como mínimo, 4 preferidos

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

Después de habilitar el servicio, es posible que tenga que configurar la red o el firewall para permitir las conexiones salientes entre él y los puntos de conexión.

- El marco de auditoría (`auditd`) debe estar habilitado.

  > [!NOTE]
  > Los eventos del sistema capturados por reglas agregadas a `/etc/audit/rules.d/` se agregarán a `audit.log`(s) y podrían afectar a la auditoría del host y a la recopilación ascendente. Los eventos agregados por Microsoft Defender para punto de conexión en Linux se etiquetarán con `mdatp` clave.

### <a name="configuring-exclusions"></a>Configuración de exclusiones

Al agregar exclusiones a Microsoft Defender Antivirus, debe tener en cuenta [los errores comunes de exclusión de Microsoft Defender Antivirus](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus).

### <a name="network-connections"></a>Conexiones de red

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Debe asegurarse de que no haya reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL. Si lo hay, es posible que tenga que crear una regla *de permiso* específicamente para ellos.

<br>

****

|Hoja de cálculo de la lista de dominios| Descripción|
|---|---|
|Microsoft Defender para punto de conexión lista de direcciones URL para clientes comerciales| Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes comerciales. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender para punto de conexión lista de direcciones URL de Gov/GCC/DoD | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes de Gov/GCC/DoD. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

> [!NOTE]
> Para obtener una lista de direcciones URL más específicas, consulte [Configuración de opciones de conectividad a Internet y proxy](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).

Defender for Endpoint puede detectar un servidor proxy mediante los siguientes métodos de detección:

- Proxy transparente
- Configuración de proxy estático manual

Si un proxy o firewall bloquea el tráfico anónimo, asegúrese de que se permite el tráfico anónimo en las direcciones URL enumeradas anteriormente. En el caso de los servidores proxy transparentes, no se necesita ninguna configuración adicional para Defender para punto de conexión. Para el proxy estático, siga los pasos descritos en [Configuración manual de proxy estático](linux-static-proxy-configuration.md).

> [!WARNING]
> No se admiten los servidores proxy PAC, WPAD y autenticados. Asegúrese de que solo se usa un proxy estático o un proxy transparente.
>
> Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad. Configure una excepción para la inspección ssl y el servidor proxy para pasar directamente los datos de Defender para punto de conexión en Linux a las direcciones URL pertinentes sin interceptación. Agregar el certificado de interceptación al almacén global no permitirá la interceptación.

Para ver los pasos de solución de problemas, consulte [Solución de problemas de conectividad en la nube para Microsoft Defender para punto de conexión en Linux](linux-support-connectivity.md).

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Actualización de Microsoft Defender para punto de conexión en Linux

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características. Para actualizar Microsoft Defender para punto de conexión en Linux, consulte [Implementación de actualizaciones para Microsoft Defender para punto de conexión en Linux](linux-updates.md).

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Cómo configurar Microsoft Defender para punto de conexión en Linux

Las instrucciones para configurar el producto en entornos empresariales están disponibles en [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md).

## <a name="common-applications-to-microsoft-defender-for-endpoint-can-impact"></a>Las aplicaciones comunes que se Microsoft Defender para punto de conexión pueden afectar

Las cargas de trabajo de E/S elevadas de determinadas aplicaciones pueden experimentar problemas de rendimiento cuando se instala Microsoft Defender para punto de conexión. Estas incluyen aplicaciones para escenarios de desarrollador como Jenkins y Jira, y cargas de trabajo de base de datos como OracleDB y Postgres. Si experimenta una degradación del rendimiento, considere la posibilidad de establecer exclusiones para aplicaciones de confianza, teniendo en cuenta [los errores comunes de exclusión de Microsoft Defender Antivirus](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus). Para obtener instrucciones adicionales, considere la posibilidad de consultar documentación sobre exclusiones de antivirus de aplicaciones de terceros.

## <a name="resources"></a>Recursos

- Para obtener más información sobre el registro, la desinstalación u otros temas, consulte [Recursos](linux-resources.md).
  
## <a name="related-articles"></a>Artículos relacionados
  
- [Protección de los puntos de conexión con la solución EDR integrada de Defender for Cloud: Microsoft Defender para punto de conexión](/azure/defender-for-cloud/integration-defender-for-endpoint)
- [Conexión de las máquinas que no son de Azure a Microsoft Defender for Cloud](/azure/defender-for-cloud/quickstart-onboard-machines)
- [Activar la protección de red para Linux](network-protection-linux.md)
