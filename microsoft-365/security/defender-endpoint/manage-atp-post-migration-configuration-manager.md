---
title: Administrar Microsoft Defender para endpoint con Configuration Manager
description: Obtenga información sobre cómo administrar Microsoft Defender para endpoint con Configuration Manager
keywords: post-migration, manage, operations, maintenance, utilization, Configuration Manager, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 71ad8f52fd9347abdf0146969bb84a19d8883262
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843071"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Administrar Microsoft Defender para endpoint con Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Se recomienda usar [Microsoft Endpoint Manager](/mem), que incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) para administrar las características de protección contra amenazas de la organización para dispositivos (también denominados puntos de conexión). 
- [Obtenga más información sobre Endpoint Manager](/mem/endpoint-manager-overview)
- [Co-administrar Microsoft Defender para endpoint en Windows 10 dispositivos con Configuration Manager e Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configurar Microsoft Defender para endpoint con Configuration Manager

|Tarea  |Recursos para obtener más información  |
|---------|---------|
|**Instalar la consola de Configuration Manager** si aún no la tiene<br/><br/>*Si aún no tiene la consola de administrador de configuración, use estos recursos para obtener los bits e instalarlo.* |[Obtener los medios de instalación](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Instalar la consola de Configuration Manager](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Usar Configuration Manager para incorporar dispositivos** a Microsoft Defender para endpoint <br/><br/> *Si ya tienes dispositivos (o puntos de conexión) no incorporados a Microsoft Defender para Endpoint, puedes hacerlo con Configuration Manager.*   |[Incorporación a Microsoft Defender para endpoint con Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Administrar directivas de antimalware y Windows firewall para** equipos cliente (puntos de conexión)<br/><br/>*Configure características de protección de puntos de conexión, como Microsoft Defender para endpoint, protección contra vulnerabilidades, control de aplicaciones, antimalware, configuración de firewall y mucho más.*  |[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Elegir métodos para actualizar actualizaciones de antimalware** en los dispositivos de la organización <br/><br/>*Con Endpoint Protection Configuration Manager, puede elegir entre varios métodos para mantener las definiciones de antimalware actualizadas en los dispositivos de la organización.* |[Configurar actualizaciones de definiciones para Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Usar Configuration Manager para entregar actualizaciones de definiciones](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Habilitar la protección de** red para ayudar a evitar que los empleados utilicen aplicaciones que usan contenido malintencionado en Internet <br/><br/>*Se recomienda usar [el modo de auditoría](/microsoft-365/security/defender-endpoint/evaluate-network-protection) al principio para la protección de red en un entorno de prueba para ver qué aplicaciones se bloquearían antes de implementarse.* |[Activar la protección de red con Configuration Manager](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Configurar el acceso controlado a carpetas** para proteger contra ransomware <br/><br/>*El acceso controlado a carpetas también se conoce como protección antiransomware.*   |[Protección de extremo: acceso controlado a carpetas](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Habilitar el acceso controlado a carpetas en Administración de configuración de punto de conexión de Microsoft](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurar el Centro de seguridad de Microsoft Defender

Si aún no lo ha hecho, configure su **Centro de seguridad de Microsoft Defender** ( ) para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de su [https://securitycenter.windows.com](https://securitycenter.windows.com) organización. 

También puede configurar si los usuarios finales pueden ver y qué características pueden ver en el Centro de seguridad de Microsoft Defender.

- [Información general sobre el Centro de seguridad de Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Protección de extremo: Centro de seguridad de Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información general sobre Administración de amenazas y vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite el panel Centro de seguridad de Microsoft Defender operaciones de seguridad](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Administrar Microsoft Defender para endpoint con Intune](manage-atp-post-migration-intune.md)
