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
ms.openlocfilehash: dca4745b5058ed7b98bf0821e2b715393f7bf77f
ms.sourcegitcommit: 2aa5c026cc06ed39a9c1c2bcabd1f563bf5a1859
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695974"
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

Para facilitar las actualizaciones cuando el Configuration Manager de punto de conexión de Microsoft aún no está disponible o actualizado para realizar la actualización automatizada, puede usar este [script de actualización](https://github.com/microsoft/mdefordownlevelserver). Puede ayudar a automatizar los siguientes pasos necesarios:

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

Pasos de migración: 

1. Actualice completamente la máquina, incluido el Antivirus de Microsoft Defender (Windows Server 2016).
2. Cree una nueva colección con reglas de pertenencia para incluir las máquinas que se van a migrar.
3. [Cree una aplicación](/mem/configmgr/apps/deploy-use/create-applications) para realizar las siguientes tareas: 
   1. Desinstale SCEP.
   2. Instale los [requisitos previos](configure-server-endpoints.md#prerequisites) cuando corresponda.
   3. Instalar Microsoft Defender para punto de conexión (consulte [Configuración de puntos de conexión de servidor](configure-server-endpoints.md).
   4. Aplique el script de incorporación **para su uso con directiva de grupo** descargados de [Microsoft 365 Defender](https://security.microsoft.com). 
   > [!TIP]
   > Puede usar el [script del instalador](server-migration.md#installer-script) como parte de la aplicación para automatizar los pasos anteriores.
4. Implemente la aplicación en la nueva colección.
5. Cree o asigne directivas de Endpoint Protection (existentes) a la colección.
6. Aplicar actualizaciones.

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-are-running-a-non-microsoft-antivirus-solution-and-the-mma-based-sensor-you-want-to-upgrade-to-the-new-microsoft-defender-for-endpoint"></a>Actualmente usa el punto de conexión de Microsoft Configuration Manager para administrar los servidores, está ejecutando una solución antivirus que no es de Microsoft y el sensor basado en MMA. Quiere actualizar a la nueva Microsoft Defender para punto de conexión.

Pasos de migración:

1. Actualice completamente la máquina, incluido el Antivirus de Microsoft Defender (Windows Server 2016).
2. Cree una nueva colección con reglas de pertenencia para incluir las máquinas que se van a migrar. 
3. Asegúrese de que la administración de antivirus de terceros ya no inserta antivirus en estas máquinas.*
4. Cree las directivas en el nodo Endpoint Protection de MECM y apunte a la colección recién creada.*
5. Cree una aplicación para realizar las siguientes tareas:
   1. Quite la configuración del área de trabajo de MMA para Microsoft Defender para punto de conexión. Consulte [Eliminación de un área de trabajo mediante PowerShell](/azure/azure-monitor/agents/agent-manage). Este paso es opcional; El sensor EDR anterior dejará de ejecutarse después de que el más reciente se active.
   2. Instale los [requisitos previos](configure-server-endpoints.md#prerequisites) cuando corresponda.
   3. Instale el Microsoft Defender para punto de conexión para Windows Server 2012 paquete R2 y 2016 y **habilite el modo pasivo**. Consulte [Instalación del Antivirus de Microsoft Defender mediante la línea de comandos](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line).
   4. Aplique el script de incorporación **para su uso con directiva de grupo** descargados de [Microsoft 365 Defender](https://security.microsoft.com).
6. Aplicar actualizaciones.
7. Quite el software antivirus que no sea de Microsoft mediante la consola antivirus que no sea de Microsoft o mediante microsoft endpoint Configuration Manager según corresponda. Asegúrese de quitar la configuración del modo pasivo.*

> [!TIP]
> Puede usar el [instalador-script](server-migration.md#installer script) como parte de la aplicación para automatizar los pasos anteriores. Para habilitar el modo pasivo, aplique la marca -Passive. Por ejemplo, .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*Estos pasos solo se aplican si piensa reemplazar la solución antivirus que no es de Microsoft. Consulte [Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md).

Para sacar una máquina del modo pasivo, establezca la clave siguiente en 0:

Ruta de acceso: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode Type: REG_DWORD Value: 0

Para obtener más información sobre cómo migrar servidores de MMA a una solución unificada, consulte [Migración de servidores de Microsoft Monitoring Agent a la solución unificada](application-deployment-via-mecm.md).

## <a name="other-migration-scenarios"></a>Otros escenarios de migración

### <a name="you-have-a-server-that-has-been-onboarded-using-the-mma-based-microsoft-defender-for-endpoint-it-has-scep-installed-windows-server-2012-r2-or-microsoft-defender-antivirus-windows-server-2016-this-machine-is-not-managed-through-microsoft-defender-for-cloud-microsoft-endpoint-manager-or-microsoft-endpoint-configuration-manager"></a>Tiene un servidor que se ha incorporado mediante la Microsoft Defender para punto de conexión basada en MMA. Tiene instalado SCEP (Windows Server 2012 R2) o Antivirus de Microsoft Defender (Windows Server 2016). Esta máquina **no** se administra a través de Microsoft Defender for Cloud, Microsoft Endpoint Manager o Microsoft Endpoint Configuration Manager.

1. Actualice completamente la máquina, incluido el Antivirus de Microsoft Defender (Windows Server 2016).
2. Quite la configuración del área de trabajo de MMA para Microsoft Defender para punto de conexión. Consulte [Eliminación de un área de trabajo mediante PowerShell](/azure/azure-monitor/agents/agent-manage).
3. Desinstale System Center Endpoint Protection (Windows Server 2012 R2).
4. Instale los [requisitos previos](configure-server-endpoints.md#prerequisites) cuando corresponda. 
5. Instalar Microsoft Defender para punto de conexión (consulte [Configuración de puntos de conexión de servidor](configure-server-endpoints.md)).
6. Aplique el script de incorporación **para su uso con directiva de grupo** descargados de [Microsoft 365 Defender](https://security.microsoft.com). 
7. Aplicar actualizaciones.
8. Cree y aplique directivas mediante directiva de grupo, PowerShell o una solución de administración de terceros.

> [!TIP]
> Puede usar el script del instalador para automatizar los pasos anteriores.

### <a name="you-have-a-server-on-which-you-want-to-install-microsoft-defender-for-endpoint-it-has-a-non-microsoft-endpoint-protection-or-endpoint-detection-and-response-solution-installed-you-do-not-intend-to-use-microsoft-endpoint-configuration-manager-or-microsoft-defender-for-cloud-you-use-your-own-deployment-mechanism"></a>Tiene un servidor en el que desea instalar Microsoft Defender para punto de conexión. Tiene instalada una solución de detección y respuesta de puntos de conexión o detección de puntos de conexión que no sean de Microsoft. No tiene previsto usar Microsoft Endpoint Configuration Manager ni Microsoft Defender for Cloud. Use su propio mecanismo de implementación. 

1. Actualice completamente la máquina, incluido el Antivirus de Microsoft Defender (Windows Server 2016).
2. Instale el Microsoft Defender para punto de conexión para Windows Server 2012 paquete R2 & 2016 y **habilite el modo pasivo**. Consulte [Instalación del Antivirus de Microsoft Defender mediante la línea de comandos](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line).
3. Aplique el script de incorporación, adecuado para su entorno, descargado de [Microsoft 365 Defender](https://security.microsoft.com). 
4. Quite la solución de respuesta y detección de puntos de conexión o de protección de puntos de conexión que no sean de Microsoft y quite el modo pasivo.*
5. Aplicar actualizaciones.
6. Cree y aplique directivas mediante directiva de grupo, PowerShell o una solución de administración de terceros.

> [!TIP]
> Puede usar el [script del instalador](server-migration.md#installer-script) para ayudar a automatizar los pasos del 1 al 4. Para habilitar el modo pasivo, aplique la marca -Passive que garantizará que Antivirus de Defender entra en modo pasivo antes de la incorporación y no interfiere con una solución antimalware que no sea de Microsoft. A continuación, para asegurarse de que Antivirus de Defender permanece en modo pasivo después de la incorporación para admitir funcionalidades de EDR como EDR Block, asegúrese de establecer la clave del Registro "ForceDefenderPassiveMode". EJEMPLO: `.\install.ps1 -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive`


*Este paso solo se aplica si tiene previsto reemplazar la solución antivirus que no es de Microsoft. Se recomienda usar el Antivirus de Microsoft Defender, incluido en Microsoft Defender para punto de conexión, para proporcionar el conjunto completo de funcionalidades. Consulte [Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md).

Para sacar una máquina del modo pasivo, establezca la clave siguiente en 0:

Ruta de acceso: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode Type: REG_DWORD Value: 0


## <a name="microsoft-defender-for-cloud-scenarios"></a>Escenarios de Microsoft Defender for Cloud

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Usa Microsoft Defender for Cloud. Microsoft Monitoring Agent (MMA) o Microsoft Antimalware para Azure (SCEP) están instalados y desea actualizar.
Si usa Microsoft Defender for Cloud, puede aprovechar el proceso de actualización automatizado. Consulte [Protección de los puntos de conexión con la solución EDR integrada de Defender for Cloud: Microsoft Defender para punto de conexión](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration).

## <a name="group-policy-configuration"></a>configuración de directiva de grupo
Para la configuración mediante directiva de grupo, asegúrese de que usa los archivos ADMX más recientes en el almacén central para acceder a las opciones correctas de directiva de Defender para punto de conexión. Consulta [Cómo crear y administrar la Tienda Central para plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) y descarga los archivos más recientes **para usarlos con Windows 10**.
