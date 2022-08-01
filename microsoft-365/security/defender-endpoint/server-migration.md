---
title: Escenarios de migración del servidor para la nueva versión de Microsoft Defender para punto de conexión
description: Lea este artículo para obtener información general sobre cómo migrar los servidores de la solución anterior basada en MMA al paquete de soluciones unificadas de Defender para punto de conexión actual.
keywords: migrate server, server, 2012r2, 2016, server migration, device management, configure Microsoft Defender para punto de conexión servers, onboard Microsoft Defender para punto de conexión servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3fc36623e6de005ba1d9f348d6a70d839acef637
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106917"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>Escenarios de migración de servidores de la solución de Microsoft Defender para punto de conexión anterior basada en MMA

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> Asegúrese siempre de que el sistema operativo y el Antivirus de Microsoft Defender en Windows Server 2016 estén completamente actualizados antes de continuar con la instalación o actualización. Para recibir mejoras y correcciones periódicas del producto para el componente sensor EDR, asegúrese de que Windows Update [KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277) se aplique o apruebe después de la instalación. Además, para mantener actualizados los componentes de protección, consulte [Administrar actualizaciones del Antivirus de Microsoft Defender y aplicar líneas base](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions).

Estas instrucciones se aplican al nuevo paquete de solución e instalador unificado (MSI) de Microsoft Defender para punto de conexión para Windows Server 2012 R2 y Windows Server 2016. Este artículo contiene instrucciones de alto nivel para varios escenarios de migración posibles del anterior a la solución actual. Estos pasos de alto nivel están diseñados como directrices para ajustarse a las herramientas de implementación y configuración disponibles en su entorno. 

**Si usa Microsoft Defender for Cloud para realizar la implementación, puede automatizar la instalación y la actualización. Consulte [El plan 2 de Defender para servidores ahora se integra con la solución unificada MDE](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/defender-for-servers-plan-2-now-integrates-with-mde-unified/ba-p/3527534).**

> [!NOTE]
> No se admiten las actualizaciones del sistema operativo con Microsoft Defender para punto de conexión instalados. A continuación, desinstale antes de continuar con una actualización.

> [!NOTE]
> La automatización y la integración completa del punto de conexión de Microsoft Configuration Manager para realizar una actualización automatizada estarán disponibles en una versión posterior de MECM. Desde la versión 2107 con el paquete acumulativo de revisiones más reciente, puede usar el nodo Endpoint Protection para la configuración, así como directiva de grupo, PowerShell, Microsoft Endpoint Manager asociación de inquilinos o configuración local. Además, puede aprovechar la funcionalidad existente en Microsoft Endpoint Configuration Manager para automatizar los pasos de actualización manual; métodos para los que se describen a continuación.

## <a name="installer-script"></a>Script del instalador

>[!NOTE]
>Asegúrese de que las máquinas en las que ejecuta el script no bloquean la ejecución del script. La configuración de directiva de ejecución recomendada para PowerShell es Allsigned. Esto requiere la importación del certificado de firma del script en el almacén publicadores de confianza del equipo local si el script se ejecuta como SYSTEM en el punto de conexión.

Para facilitar las actualizaciones cuando el Configuration Manager de punto de conexión de Microsoft aún no está disponible o actualizado para realizar la actualización automatizada, puede usar este [script de actualización](https://github.com/microsoft/mdefordownlevelserver). Descárguelo seleccionando el botón "Código" y descargando el archivo .zip y extrayéndolo install.ps1. Puede ayudar a automatizar los siguientes pasos necesarios:

1. Quite el área de trabajo de OMS para Microsoft Defender para punto de conexión (OPCIONAL).
2. Quite System Center Endpoint Protection cliente (SCEP) si está instalado.
3. Descargue e instale (Windows Server 2012 R2) [los requisitos previos](configure-server-endpoints.md#prerequisites) si es necesario.
4. Instale Microsoft Defender para punto de conexión.
5. Aplique el script de incorporación **para su uso con directiva de grupo** descargados de [Microsoft 365 Defender](https://security.microsoft.com).

Para usar el script, descárguelo en un directorio de instalación donde también haya colocado los paquetes de instalación e incorporación (consulte [Configuración de puntos de conexión de servidor](configure-server-endpoints.md).

EJEMPLO: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Escenarios de migración Configuration Manager punto de conexión de Microsoft 

>[!NOTE]
>Necesitará la Configuration Manager de punto de conexión de Microsoft, versión 2107 o posterior, para la configuración de directivas de Endpoint Protection de perfom.

Para obtener instrucciones sobre cómo migrar con Microsoft Endpoint Configuration Manager anterior a la versión 2207, consulte [Migración de servidores de Microsoft Monitoring Agent a la solución unificada.](/microsoft-365/security/defender-endpoint/application-deployment-via-mecm)

## <a name="if-you-are-running-a-non-microsoft-antivirus-solution"></a>Si está ejecutando una solución antivirus que no es de Microsoft

1. Actualice completamente la máquina, incluido el Antivirus de Microsoft Defender (Windows Server 2016), lo que garantiza que se cumplen [los requisitos previos](configure-server-endpoints.md#prerequisites).
2. Asegúrese de que la administración de antivirus de terceros ya no inserta agentes antivirus en estas máquinas.*
3. Cree las directivas para las capacidades de protección de Microsoft Defender para punto de conexión y apunte a ellas a la máquina de la herramienta que prefiera.*
4. Instale el Microsoft Defender para punto de conexión para Windows Server 2012 paquete R2 y 2016 y **habilite el modo pasivo**. Consulte [Instalación del Antivirus de Microsoft Defender mediante la línea de comandos](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line).
   a. Aplique el script de incorporación **para su uso con directiva de grupo** descargados de [Microsoft 365 Defender](https://security.microsoft.com).
5. Aplicar actualizaciones.
6. Quite el software antivirus que no sea de Microsoft mediante la consola antivirus que no sea de Microsoft o mediante microsoft endpoint Configuration Manager según corresponda. Asegúrese de quitar la configuración del modo pasivo.*

> [!TIP]
> Puede usar el [instalador-script](server-migration.md#installer script) como parte de la aplicación para automatizar los pasos anteriores. Para habilitar el modo pasivo, aplique la marca -Passive. Por ejemplo, .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*Estos pasos solo se aplican si piensa reemplazar la solución antivirus que no es de Microsoft. Consulte [Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md).

Para sacar una máquina del modo pasivo, establezca la clave siguiente en 0:

Ruta de acceso: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode Type: REG_DWORD Value: 0

## <a name="if-you-are-running-system-center-endpoint-protection-but-are-not-managing-the-machine-using-microsoft-endpoint-configuration-manager-mecmconfigmgr"></a>Si está ejecutando System Center Endpoint Protection pero no está administrando la máquina mediante microsoft endpoint Configuration Manager (MECM/ConfigMgr)

1. Actualice completamente la máquina, incluido el Antivirus de Microsoft Defender (Windows Server 2016), lo que garantiza que se cumplen [los requisitos previos](configure-server-endpoints.md#prerequisites).
2. Cree y aplique directivas mediante directiva de grupo, PowerShell o una solución de administración de terceros.
3. Desinstale System Center Endpoint Protection (Windows Server 2012 R2).
5. Instalar Microsoft Defender para punto de conexión (consulte [Configuración de puntos de conexión de servidor](configure-server-endpoints.md)).
6. Aplique el script de incorporación **para su uso con directiva de grupo** descargados de [Microsoft 365 Defender](https://security.microsoft.com). 
7. Aplicar actualizaciones.

> [!TIP]
> Puede usar el script del instalador para automatizar los pasos anteriores.

## <a name="microsoft-defender-for-cloud-scenarios"></a>Escenarios de Microsoft Defender for Cloud

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Usa Microsoft Defender for Cloud. Microsoft Monitoring Agent (MMA) o Microsoft Antimalware para Azure (SCEP) están instalados y desea actualizar.
Si usa Microsoft Defender for Cloud, puede aprovechar el proceso de actualización automatizado. Consulte [Protección de los puntos de conexión con la solución EDR integrada de Defender for Cloud: Microsoft Defender para punto de conexión](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration).

## <a name="group-policy-configuration"></a>configuración de directiva de grupo
Para la configuración mediante directiva de grupo, asegúrese de que usa los archivos ADMX más recientes en el almacén central para acceder a las opciones correctas de directiva de Defender para punto de conexión. Consulta [Cómo crear y administrar la Tienda Central para plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) y descarga los archivos más recientes **para usarlos con Windows 10**.
