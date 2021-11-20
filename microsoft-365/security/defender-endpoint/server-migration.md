---
title: Escenarios de migración de servidor para la nueva versión de Microsoft Defender para endpoint
description: Lea este artículo para obtener información general sobre cómo migrar los servidores de la solución anterior basada en MMA al paquete de solución unificada de Defender para endpoint actual.
keywords: migrar servidor, servidor, 2012r2, 2016, migración de servidores, administración de dispositivos, configuración de Servidores de Microsoft Defender para endpoints, incorporación de Microsoft Defender para servidores de punto de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9e4381063d872a097423fed4a3cb47b05b42bf38
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61122362"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>Escenarios de migración de servidor de la solución anterior de Microsoft Defender para endpoint basada en MMA

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- Windows Server 2012 R2
- Windows Server 2016

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> Asegúrese siempre de Antivirus de Microsoft Defender se actualice completamente en Windows Server 2016 antes de continuar con la instalación o actualización. Para recibir mejoras y correcciones periódicas del producto para el componente del sensor de EDR, asegúrese de que Windows se aplique o apruebe la actualización [KB5005292.](https://go.microsoft.com/fwlink/?linkid=2168277) Además, para mantener actualizados los componentes de protección, consulte [Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base.](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)

Estas instrucciones se aplican a la nueva solución unificada y al paquete de instalador de Microsoft Defender para endpoint para Windows Server 2012 R2 y Windows Server 2016. Este artículo contiene instrucciones de alto nivel para varios escenarios de migración posibles de la solución anterior a la actual. Estos pasos de alto nivel están pensados como directrices para ajustarse a las herramientas de implementación y configuración disponibles en el entorno.

> [!NOTE]
> No se admiten las actualizaciones del sistema operativo con Microsoft Defender para endpoint instalado. Por favor, desinstale antes de continuar con una actualización.

> [!NOTE]
> Durante la versión preliminar, Microsoft Endpoint Configuration Manager completa de automatización e integración para realizar una actualización automatizada estará disponible en la versión 2111 de MECM. Desde la versión 2107, puede usar el nodo Endpoint Protection para la configuración, así como la directiva de grupo, PowerShell, Microsoft Endpoint Manager de inquilino o la configuración local. Además, puede aprovechar la funcionalidad existente en Microsoft Endpoint Configuration Manager para automatizar los pasos de actualización manuales; métodos para los que se describen a continuación.

## <a name="installer-script"></a>Script del instalador

Para facilitar las actualizaciones cuando Microsoft Endpoint Configuration Manager o Microsoft Defender para la nube no están en uso o aún no están disponibles para realizar la actualización, puede usar este [script de actualización](https://github.com/microsoft/mdefordownlevelserver). Puede ayudar a automatizar los siguientes pasos necesarios:

1. Quite el área de trabajo oms para Microsoft Defender para endpoint (OPTIONAL).
2. Quite System Center Endpoint Protection cliente si está instalado.
3. Descargue e instale los [requisitos previos](configure-server-endpoints.md#prerequisites) (Windows Server 2012 R2) si es necesario.
4. Instalar Microsoft Defender para endpoint.
5. Aplicar el script de incorporación **para su uso con la directiva de** grupo descargada desde [Centro de seguridad de Microsoft Defender](https://securitycenter.microsoft.com).

Para usar el script, descárbalo en un directorio de instalación donde también haya colocado los paquetes de instalación e incorporación (vea [Configure server endpoints](configure-server-endpoints.md)).

EJEMPLO: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager de migración 

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-including-system-center-endpoint-protection-scep-and-are-running-the-microsoft-monitoring-agent-mma-based-sensor-you-want-to-upgrade-to-the-microsoft-defender-for-endpoint-unified-solution-preview"></a>Actualmente está usando Microsoft Endpoint Configuration Manager para administrar los servidores, incluido System Center Endpoint Protection (SCEP) y está ejecutando el sensor basado en Microsoft Monitoring Agent (MMA). Desea actualizar a la versión preliminar de la solución unificada de Microsoft Defender para endpoint **.**

>[!NOTE]
>Necesitarás una Microsoft Endpoint Configuration Manager, versión 2107.


Pasos de migración: 

1. Actualice completamente el equipo, incluido Antivirus de Microsoft Defender (Windows Server 2016).
2. Cree una nueva colección con reglas de pertenencia para incluir las máquinas que se migrarán.
3. [Cree una aplicación para](/mem/configmgr/apps/deploy-use/create-applications) realizar las siguientes tareas: 
   1. Quite la configuración del área de trabajo de MMA para Microsoft Defender para endpoint. Consulte [Remove a workspace using PowerShell](/azure/azure-monitor/agents/agent-manage). Este paso es opcional; el sensor EDR anterior dejará de ejecutarse después de que el nuevo se active (tenga en cuenta que esto puede tardar varias horas).
   2. Desinstalar SCEP.
   3. Instale los [requisitos previos](configure-server-endpoints.md#prerequisites) cuando corresponda.
   4. Instalar Microsoft Defender para endpoint (vea [Configure server endpoints](configure-server-endpoints.md)).
   5. Aplicar el script de incorporación **para su uso con la directiva de** grupo descargada desde [Centro de seguridad de Microsoft Defender](https://securitycenter.microsoft.com). 

   > [!TIP]
   > Puede usar el [script del instalador](server-migration.md#installer-script) como parte de la aplicación para automatizar los pasos anteriores.
4. Implemente la aplicación en la nueva colección.
5. Cree y/o asigne directivas de Endpoint Protection (existentes) a la colección.
6. Aplicar actualizaciones.

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-are-running-a-non-microsoft-antivirus-solution-and-the-mma-based-sensor-you-want-to-upgrade-to-the-new-microsoft-defender-for-endpoint"></a>Actualmente está usando Microsoft Endpoint Configuration Manager para administrar los servidores, está ejecutando una solución antivirus que no es microsoft y el sensor basado en MMA. Desea actualizar al nuevo Microsoft Defender para endpoint.

Pasos de migración:

1. Actualice completamente el equipo, incluido Antivirus de Microsoft Defender (Windows Server 2016).
2. Cree una nueva colección con reglas de pertenencia para incluir las máquinas que se migrarán. 
3. Asegúrese de que la administración de antivirus de terceros ya no inserta antivirus en estas máquinas.*
4. Cree sus directivas en el nodo Endpoint Protection de MECM y de destino a la colección recién creada.*
5. Cree una aplicación para realizar las siguientes tareas:
   1. Quite la configuración del área de trabajo de MMA para Microsoft Defender para endpoint. Consulte [Remove a workspace using PowerShell](/azure/azure-monitor/agents/agent-manage). Este paso es opcional; el sensor EDR anterior dejará de ejecutarse después de que el nuevo se active (tenga en cuenta que esto puede tardar varias horas).
   2. Instale los [requisitos previos](configure-server-endpoints.md#prerequisites) cuando corresponda.
   3. Instale el microsoft defender para el punto de conexión para Windows Server 2012 paquete R2 y 2016 y **habilite el modo pasivo**. Consulte [Install Antivirus de Microsoft Defender using command line](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-command-line).
   4. Aplicar el script de incorporación **para su uso con la directiva de** grupo descargada desde [Centro de seguridad de Microsoft Defender](https://securitycenter.microsoft.com).
6. Aplicar actualizaciones.
7. Quite el software antivirus que no sea de Microsoft mediante la consola antivirus que no es de Microsoft o mediante Microsoft Endpoint Configuration Manager según corresponda. Asegúrese de quitar la configuración del modo pasivo.*

> [!TIP]
> Puede usar el script [del instalador](server-migration.md#installer script) como parte de la aplicación para automatizar los pasos anteriores. Para habilitar el modo pasivo, aplique la marca -Passive. Por ejemplo, .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*Estos pasos solo se aplican si desea reemplazar la solución antivirus que no es de Microsoft. Vea [Better together: Antivirus de Microsoft Defender y Microsoft Defender para Endpoint](why-use-microsoft-defender-antivirus.md).

Para sacar una máquina del modo pasivo, establezca la siguiente clave en 0:

Ruta de acceso: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode Type: REG_DWORD Value: 0


## <a name="other-migration-scenarios"></a>Otros escenarios de migración

### <a name="you-have-a-server-that-has-been-onboarded-using-the-mma-based-microsoft-defender-for-endpoint-it-has-scep-installed-windows-server-2012-r2-or-microsoft-defender-antivirus-windows-server-2016-this-machine-is-not-managed-through-microsoft-defender-for-cloud-microsoft-endpoint-manager-or-microsoft-endpoint-configuration-manager"></a>Tiene un servidor que se ha incorporado con Microsoft Defender para endpoint basado en MMA. Tiene SCEP instalado (Windows Server 2012 R2) o Antivirus de Microsoft Defender (Windows Server 2016). Esta máquina no **se administra** a través de Microsoft Defender para la nube, Microsoft Endpoint Manager o Microsoft Endpoint Configuration Manager.

1. Actualice completamente el equipo, incluido Antivirus de Microsoft Defender (Windows Server 2016).
2. Quite la configuración del área de trabajo de MMA para Microsoft Defender para endpoint. Consulte [Remove a workspace using PowerShell](/azure/azure-monitor/agents/agent-manage).
3. Desinstalar System Center Endpoint Protection (Windows Server 2012 R2).
4. Instale los [requisitos previos](configure-server-endpoints.md#prerequisites) cuando corresponda. 
5. Instalar Microsoft Defender para endpoint (consulte [Configure server endpoints](configure-server-endpoints.md).)
6. Aplicar el script de incorporación **para su uso con la directiva de** grupo descargada desde [Centro de seguridad de Microsoft Defender](https://securitycenter.microsoft.com). 
7. Aplicar actualizaciones.
8. Cree y aplique directivas con la directiva de grupo, PowerShell o una solución de administración de terceros.

> [!TIP]
> Puede usar el script del instalador para automatizar los pasos anteriores.

### <a name="you-have-a-server-on-which-you-want-to-install-microsoft-defender-for-endpoint-it-has-a-non-microsoft-endpoint-protection-or-endpoint-detection-and-response-solution-installed-you-do-not-intend-to-use-microsoft-endpoint-configuration-manager-or-microsoft-defender-for-cloud-you-use-your-own-deployment-mechanism"></a>Tiene un servidor en el que desea instalar Microsoft Defender para endpoint. Tiene instalada una solución de protección de extremo que no sea de Microsoft detección y respuesta de puntos de conexión de conexión. No tiene la intención de usar Microsoft Endpoint Configuration Manager o Microsoft Defender para la nube. Use su propio mecanismo de implementación. 

1. Actualice completamente el equipo, incluido Antivirus de Microsoft Defender (Windows Server 2016).
2. Instale el paquete de Microsoft Defender para endpoint para Windows Server 2012 R2 & 2016 y **habilite el modo pasivo**. Consulte [Install Antivirus de Microsoft Defender using command line](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-command-line).
3. Aplique el script de incorporación, adecuado para su entorno, descargado desde [Centro de seguridad de Microsoft Defender](https://securitycenter.microsoft.com). 
4. Quite la protección de extremo que no es de Microsoft detección y respuesta de puntos de conexión solución y quite el modo pasivo.*
5. Aplicar actualizaciones.
6. Cree y aplique directivas con la directiva de grupo, PowerShell o una solución de administración de terceros.

> [!TIP]
> Puede usar el [script del instalador para](server-migration.md#installer-script) ayudar a automatizar los pasos del 1 al 4. Para habilitar el modo pasivo, aplica la marca -Passive que garantizará que Antivirus de Defender entre en modo pasivo antes de la incorporación y no interfiera con una solución antimalware que no sea de Microsoft. A continuación, para asegurarse de que Defender Antivirus permanece en modo pasivo después de la incorporación para admitir EDR funcionalidades como EDR Block, asegúrese de establecer la clave del Registro "ForceDefenderPassiveMode". EJEMPLO: `.\install.ps1 -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive`


*Este paso solo se aplica si desea reemplazar la solución antivirus que no es de Microsoft. Se recomienda usar Antivirus de Microsoft Defender, incluido en Microsoft Defender para endpoint, para proporcionar el conjunto completo de funcionalidades. Vea [Better together: Antivirus de Microsoft Defender y Microsoft Defender para Endpoint](why-use-microsoft-defender-antivirus.md).

Para sacar una máquina del modo pasivo, establezca la siguiente clave en 0:

Ruta de acceso: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode Type: REG_DWORD Value: 0


## <a name="microsoft-defender-for-cloud-scenarios"></a>Escenarios de Microsoft Defender para la nube

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Estás usando Microsoft Defender para la nube. El Microsoft Monitoring Agent (MMA) y/o Microsoft Antimalware para Azure (SCEP) están instalados y desea actualizar.
Si usa Microsoft Defender para la nube, puede aprovechar el proceso de actualización automatizada. Consulte [Protect your endpoints with Defender for Cloud's integrated EDR solution: Microsoft Defender for Endpoint](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration).

## <a name="group-policy-configuration"></a>Configuración de directiva de grupo
Para la configuración mediante la directiva de grupo, asegúrese de que está usando los archivos ADMX más recientes del almacén central para tener acceso a las opciones de directiva de Defender for Endpoint correctas. Consulta [Cómo crear y administrar la](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) Tienda central para plantillas administrativas de directiva de grupo en Windows y descarga los archivos más recientes para usarlos **con Windows 10**.
