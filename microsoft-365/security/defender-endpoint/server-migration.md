---
title: Escenarios de migración del servidor para la nueva versión de Microsoft Defender para punto de conexión
description: Lea este artículo para obtener información general sobre cómo migrar los servidores de la solución anterior basada en MMA al paquete de soluciones unificadas de Defender para punto de conexión actual.
keywords: migrate server, server, 2012r2, 2016, server migration, device management, configure Microsoft Defender para punto de conexión servers, onboard Microsoft Defender para punto de conexión servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
ms.date: 09/19/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 0720eb69c37b9767d96819cdea431422bed145a1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68625971"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>Escenarios de migración de servidores de la solución de Microsoft Defender para punto de conexión anterior basada en MMA

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> [!NOTE]
> Asegúrese siempre de que el sistema operativo y Microsoft Defender Antivirus en Windows Server 2016 estén totalmente actualizados antes de continuar con la instalación o actualización. Para recibir mejoras y correcciones periódicas del producto para el componente sensor EDR, asegúrese de que Windows Update [KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277) se aplique o apruebe después de la instalación. Además, para mantener actualizados los componentes de protección, consulte [Administrar actualizaciones Microsoft Defender Antivirus y aplicar líneas base](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions).

Estas instrucciones se aplican al nuevo paquete de solución e instalador unificado (MSI) de Microsoft Defender para punto de conexión para Windows Server 2012 R2 y Windows Server 2016. Este artículo contiene instrucciones de alto nivel para varios escenarios de migración posibles del anterior a la solución actual. Estos pasos de alto nivel están diseñados como directrices para ajustarse a las herramientas de implementación y configuración disponibles en su entorno. 

**Si usa Microsoft Defender para que Cloud realice la implementación, puede automatizar la instalación y la actualización. Consulte [El plan 2 de Defender para servidores ahora se integra con la solución unificada MDE](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/defender-for-servers-plan-2-now-integrates-with-mde-unified/ba-p/3527534).**

> [!NOTE]
> No se admiten las actualizaciones del sistema operativo con Microsoft Defender para punto de conexión instalados. Quite el panel y desinstale, actualice el sistema operativo y, a continuación, continúe con la instalación.

> [!NOTE]
> La integración y automatización completa de Microsoft Endpoint Configuration Manager para realizar una actualización automatizada estará disponible en una versión posterior de MECM. Desde la versión 2107 con el paquete acumulativo de revisiones más reciente, puede usar el nodo Endpoint Protection para la configuración, así como समूह नीति, PowerShell, Microsoft Endpoint Manager asociación de inquilinos o configuración local. Además, puede aprovechar la funcionalidad existente en Microsoft Endpoint Configuration Manager para automatizar los pasos de actualización manual; métodos para los que se describen a continuación.

## <a name="installer-script"></a>Script del instalador

>[!NOTE]
>Asegúrese de que las máquinas en las que ejecuta el script no bloquean la ejecución del script. La configuración de directiva de ejecución recomendada para PowerShell es Allsigned. Esto requiere la importación del certificado de firma del script en el almacén publicadores de confianza del equipo local si el script se ejecuta como SYSTEM en el punto de conexión.

Para facilitar las actualizaciones cuando Microsoft Endpoint Configuration Manager aún no está disponible o actualizado para realizar la actualización automatizada, puede usar este [script de actualización](https://github.com/microsoft/mdefordownlevelserver/archive/refs/heads/main.zip). Descárguelo seleccionando el botón "Código" y descargando el archivo .zip y extrayéndolo install.ps1. Puede ayudar a automatizar los siguientes pasos necesarios:

1. Quite el área de trabajo de OMS para Microsoft Defender para punto de conexión (OPCIONAL).
2. Quite System Center Endpoint Protection cliente (SCEP) si está instalado.
3. Descargue e instale (Windows Server 2012 R2) [los requisitos previos](configure-server-endpoints.md#prerequisites) si es necesario.
4. Instale Microsoft Defender para punto de conexión.
5. Aplique el script de incorporación **para su uso con समूह नीति** descargados de [Microsoft 365 Defender](https://security.microsoft.com).

Para usar el script, descárguelo en un directorio de instalación donde también haya colocado los paquetes de instalación e incorporación (consulte [Configuración de puntos de conexión de servidor](configure-server-endpoints.md)).

EJEMPLO: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

Para obtener más información sobre cómo usar el script, use el comando de PowerShell "get-help .\install.ps1".

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Escenarios de migración de Microsoft Endpoint Configuration Manager 

>[!NOTE]
>Necesitará Microsoft Endpoint Configuration Manager, versión 2107 o posterior, para la configuración de directivas de Endpoint Protection de perfom.

Para obtener instrucciones sobre cómo migrar con Microsoft Endpoint Configuration Manager anterior a la versión 2207, consulte [Migración de servidores de Microsoft Monitoring Agent a la solución unificada.](/microsoft-365/security/defender-endpoint/application-deployment-via-mecm)

## <a name="if-you-are-running-a-non-microsoft-antivirus-solution"></a>Si está ejecutando una solución antivirus que no es de Microsoft

1. Actualice completamente la máquina, incluido Microsoft Defender Antivirus (Windows Server 2016), lo que garantiza que se cumplen [los requisitos previos](configure-server-endpoints.md#prerequisites). Para obtener más información sobre los requisitos previos que deben cumplirse, consulte [Requisitos previos para Windows Server 2016](configure-server-endpoints.md#prerequisites-for-windows-server-2016).
2. Asegúrese de que la administración de antivirus de terceros ya no inserta agentes antivirus en estas máquinas.*
3. Cree las directivas para las capacidades de protección de Microsoft Defender para punto de conexión y apunte a ellas a la máquina de la herramienta que prefiera.*
4. Instale el Microsoft Defender para punto de conexión para Windows Server 2012 paquete R2 y 2016 y **habilite el modo pasivo**. Consulte [Instalación de Microsoft Defender Antivirus mediante la línea de comandos](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line).
   a. Aplique el script de incorporación **para su uso con समूह नीति** descargados de [Microsoft 365 Defender](https://security.microsoft.com).
5. Aplicar actualizaciones.
6. Quite el software antivirus que no es de Microsoft mediante la consola antivirus que no es de Microsoft o mediante Microsoft Endpoint Configuration Manager según corresponda. Asegúrese de quitar la configuración del modo pasivo.*

> [!TIP]
> Puede usar el [instalador-script](server-migration.md#installer script) como parte de la aplicación para automatizar los pasos anteriores. Para habilitar el modo pasivo, aplique la marca -Passive. Por ejemplo, .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*Estos pasos solo se aplican si piensa reemplazar la solución antivirus que no es de Microsoft. Consulte [Mejor juntos: Microsoft Defender Antivirus y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md).

Para sacar una máquina del modo pasivo, establezca la clave siguiente en 0:

Ruta de acceso: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode Type: REG_DWORD Value: 0

## <a name="if-you-are-running-system-center-endpoint-protection-but-are-not-managing-the-machine-using-microsoft-endpoint-configuration-manager-mecmconfigmgr"></a>Si está ejecutando System Center Endpoint Protection pero no está administrando la máquina mediante Microsoft Endpoint Configuration Manager (MECM/ConfigMgr)

1. Actualice completamente la máquina, incluido Microsoft Defender Antivirus (Windows Server 2016), lo que garantiza que se cumplen [los requisitos previos](configure-server-endpoints.md#prerequisites).
2. Cree y aplique directivas mediante समूह नीति, PowerShell o una solución de administración de terceros.
3. Desinstale System Center Endpoint Protection (Windows Server 2012 R2).
5. Instalar Microsoft Defender para punto de conexión (consulte [Configuración de puntos de conexión de servidor](configure-server-endpoints.md)).
6. Aplique el script de incorporación **para su uso con समूह नीति** descargados de [Microsoft 365 Defender](https://security.microsoft.com). 
7. Aplicar actualizaciones.

> [!TIP]
> Puede usar el script del instalador para automatizar los pasos anteriores.

## <a name="microsoft-defender-for-cloud-scenarios"></a>escenarios de Microsoft Defender para la nube

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Usa Microsoft Defender para la nube. Microsoft Monitoring Agent (MMA) o Microsoft Antimalware para Azure (SCEP) están instalados y desea actualizar.
Si usa Microsoft Defender for Cloud, puede aprovechar el proceso de actualización automatizado. Consulte [Protección de los puntos de conexión con la solución EDR integrada de Defender for Cloud: Microsoft Defender para punto de conexión](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration).

## <a name="group-policy-configuration"></a>configuración de समूह नीति
Para la configuración mediante समूह नीति, asegúrese de usar los archivos ADMX más recientes en el almacén central para acceder a las opciones correctas de directiva de Defender para punto de conexión. Consulta [Cómo crear y administrar la Tienda central para समूह नीति plantillas administrativas en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) y descarga los archivos más recientes **para usarlos con Windows 10**.
