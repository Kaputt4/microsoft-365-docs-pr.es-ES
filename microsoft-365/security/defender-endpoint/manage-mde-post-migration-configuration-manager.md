---
title: Administrar Microsoft Defender para endpoint con Configuration Manager
description: Obtenga información sobre cómo administrar Microsoft Defender para endpoint con Configuration Manager
keywords: post-migration, manage, operations, maintenance, utilization, Configuration Manager, Microsoft Defender for Endpoint, edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 11/29/2021
ms.reviewer: chventou
ms.openlocfilehash: 1da8a079016b09b9398d48be85f7815adf2998da
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221595"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Administrar Microsoft Defender para endpoint con Configuration Manager

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


Se recomienda usar [Microsoft Endpoint Manager](/mem), que incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) para administrar las características de protección contra amenazas de la organización para dispositivos ( también denominados puntos de conexión).

- [Obtenga más información sobre Endpoint Manager](/mem/endpoint-manager-overview)
- [Administrar Microsoft Defender para endpoint en Windows 10 y Windows 11 dispositivos con Configuration Manager e Intune](manage-mde-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configurar Microsoft Defender para endpoint con Configuration Manager

<br/><br/>

|Tarea|Recursos para obtener más información|
|---|---|
|**Instalar la consola de Configuration Manager** si aún no la tiene <br/><br/> *Si aún no tiene la consola de administrador de configuración, use estos recursos para obtener los bits e instalarlo.*|[Obtener los medios de instalación](/mem/configmgr/core/servers/deploy/install/get-install-media) <br/><br/> [Instalar la consola de Configuration Manager](/mem/configmgr/core/servers/deploy/install/install-consoles)|
|**Usar Configuration Manager para incorporar dispositivos** a Microsoft Defender para endpoint <br/><br/> *Si ya tienes dispositivos (o puntos de conexión) no incorporados a Microsoft Defender para Endpoint, puedes hacerlo con Configuration Manager.*|[Incorporación a Microsoft Defender para endpoint con Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)|
|**Administrar directivas de antimalware y Windows firewall para** equipos cliente (puntos de conexión) <br/><br/> *Configure características de protección de puntos de conexión, como Microsoft Defender para endpoint, protección contra vulnerabilidades, control de aplicaciones, antimalware, configuración de firewall y mucho más.*|[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)|
|**Elegir métodos para actualizar actualizaciones de antimalware** en los dispositivos de la organización <br/><br/> *Con Endpoint Protection Configuration Manager, puede elegir entre varios métodos para mantener las definiciones de antimalware actualizadas en los dispositivos de la organización.*|[Configurar actualizaciones de definiciones para Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/> [Usar Configuration Manager para entregar actualizaciones de definiciones](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr)|
|**Habilitar la protección de** red para ayudar a evitar que los empleados utilicen aplicaciones que usan contenido malintencionado en Internet <br/><br/> *Se recomienda usar [el modo de auditoría](/microsoft-365/security/defender-endpoint/evaluate-network-protection) al principio para la protección de red en un entorno de prueba para ver qué aplicaciones se bloquearían antes de implementarse.*|[Activar la protección de red con Configuration Manager](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)|
|**Configurar el acceso controlado a carpetas** para proteger contra ransomware <br/><br/> *El acceso controlado a carpetas también se conoce como protección antiransomware.*|[Protección de extremo: acceso controlado a carpetas](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [Habilitar el acceso controlado a carpetas en Administración de configuración de punto de conexión de Microsoft](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Configurar el portal Microsoft 365 Defender web

Si aún no lo ha hecho, configure el portal de Microsoft 365 Defender para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de su organización. Vea [Microsoft 365 Defender portal](microsoft-defender-security-center.md). También puede configurar si los usuarios finales pueden ver y qué características pueden ver en Microsoft 365 Defender portal.

- [Información general sobre Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [Protección de extremo: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Siguientes pasos

- [Introducción a la administración de amenazas y vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Visite el panel Microsoft 365 Defender operaciones de seguridad del portal](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [Administrar Microsoft Defender para endpoint con Intune](manage-mde-post-migration-intune.md)
