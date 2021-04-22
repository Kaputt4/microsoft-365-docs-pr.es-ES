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
ms.openlocfilehash: 0cd52388feb987b4231d911cd3c3fd10babba017
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933210"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Administrar Microsoft Defender para endpoint con Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Se recomienda usar [Microsoft Endpoint Manager](https://docs.microsoft.com/mem), que incluye [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) (Intune) y Microsoft Endpoint Configuration Manager (Configuration [Manager)](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) para administrar las características de protección contra amenazas de la organización para dispositivos (también denominados puntos de conexión). 
- [Obtenga más información sobre Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [Administrar Microsoft Defender para endpoint en dispositivos Windows 10 con Configuration Manager e Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configurar Microsoft Defender para endpoint con Configuration Manager

|Tarea  |Recursos para obtener más información  |
|---------|---------|
|**Instalar la consola de Configuration Manager** si aún no la tiene<br/><br/>*Si aún no tiene la consola de administrador de configuración, use estos recursos para obtener los bits e instalarlo.* |[Obtener los medios de instalación](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Instalar la consola de Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Usar Configuration Manager para incorporar dispositivos** a Microsoft Defender para endpoint <br/><br/> *Si ya tienes dispositivos (o puntos de conexión) no incorporados a Microsoft Defender para Endpoint, puedes hacerlo con Configuration Manager.*   |[Incorporación a Microsoft Defender para endpoint con Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Administrar directivas de antimalware y seguridad de Firewall de Windows** para equipos cliente (puntos de conexión)<br/><br/>*Configure características de protección de puntos de conexión, como Microsoft Defender para endpoint, protección contra vulnerabilidades, control de aplicaciones, antimalware, configuración de firewall y mucho más.*  |[Configuration Manager: Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Elegir métodos para actualizar actualizaciones de antimalware** en los dispositivos de la organización <br/><br/>*Con Endpoint Protection en Configuration Manager, puede elegir entre varios métodos para mantener las definiciones de antimalware actualizadas en los dispositivos de la organización.* |[Configurar actualizaciones de definición para Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Usar Configuration Manager para entregar actualizaciones de definiciones](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Habilitar la protección de** red para ayudar a evitar que los empleados utilicen aplicaciones que usan contenido malintencionado en Internet <br/><br/>*Se recomienda usar [el modo de auditoría](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) al principio para la protección de red en un entorno de prueba para ver qué aplicaciones se bloquearían antes de implementarse.* |[Activar la protección de red con Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Configurar el acceso controlado a carpetas** para proteger contra ransomware <br/><br/>*El acceso controlado a carpetas también se conoce como protección antiransomware.*   |[Protección de extremo: acceso controlado a carpetas](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Habilitar el acceso controlado a carpetas en Administración de configuración de punto de conexión de Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurar el Centro de seguridad de Microsoft Defender

Si aún no lo ha hecho, configure el Centro de seguridad de **Microsoft Defender** ( ) para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de su [https://securitycenter.windows.com](https://securitycenter.windows.com) organización. 

También puede configurar si los usuarios finales pueden ver y qué características pueden ver en el Centro de seguridad de Microsoft Defender.

- [Información general del Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Protección de puntos de conexión: Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Siguientes pasos

- [Obtener información general sobre la administración de amenazas y vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite el panel de operaciones de seguridad del Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Administrar Microsoft Defender para endpoint con Intune](manage-atp-post-migration-intune.md)
