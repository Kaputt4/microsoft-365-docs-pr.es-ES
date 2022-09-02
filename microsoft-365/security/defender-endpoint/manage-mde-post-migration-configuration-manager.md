---
title: Administrar Microsoft Defender para punto de conexión mediante Configuration Manager
description: Aprenda a administrar Microsoft Defender para punto de conexión con Configuration Manager
keywords: posterior a la migración, administración, operaciones, mantenimiento, uso, Configuration Manager, Microsoft Defender para punto de conexión, edr
ms.service: microsoft-365-security
ms.subservice: mde
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
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 07/01/2022
ms.reviewer: chventou
ms.openlocfilehash: 458686d2de45acabae118846a962f0e887887bbb
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522463"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Administración de Microsoft Defender para punto de conexión con Configuration Manager

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Se recomienda usar [Microsoft Endpoint Manager](/mem), que incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) y [Configuration Manager de punto de conexión de Microsoft](/mem/configmgr/core/understand/introduction) (Configuration Manager ) para administrar las características de protección contra amenazas de su organización para dispositivos (también conocidos como puntos de conexión).

- [Más información sobre Endpoint Manager](/mem/endpoint-manager-overview)
- [Administración conjunta de Microsoft Defender para punto de conexión en dispositivos Windows 10 y Windows 11 con Configuration Manager y Intune](manage-mde-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuración de Microsoft Defender para punto de conexión con Configuration Manager

|Tarea|Recursos para obtener más información|
|---|---|
|**Instale la consola de Configuration Manager** si aún no la tiene. <br/><br/> *Si aún no tiene la consola de Configuration Manger, use estos recursos para obtener los bits e instalarlos.*|[Obtención de los medios de instalación](/mem/configmgr/core/servers/deploy/install/get-install-media) <br/><br/> [Instalación de la consola de Configuration Manager](/mem/configmgr/core/servers/deploy/install/install-consoles)|
|**Uso de Configuration Manager para incorporar dispositivos** a Microsoft Defender para punto de conexión <br/><br/> *Si aún no tiene dispositivos (o puntos de conexión) incorporados a Microsoft Defender para punto de conexión, puede hacerlo con Configuration Manager.*|[Incorporación a Microsoft Defender para punto de conexión con Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)|
|**Administración de directivas antimalware y seguridad de Firewall de Windows** para equipos cliente (puntos de conexión) <br/><br/> *Configure las características de endpoint protection, como Microsoft Defender para punto de conexión, protección contra vulnerabilidades de seguridad, control de aplicaciones, antimalware, configuración de firewall, etc.*|[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)|
|**Elección de métodos para actualizar actualizaciones antimalware** en los dispositivos de la organización <br/><br/> *Con Endpoint Protection en Configuration Manager, puede elegir entre varios métodos para mantener actualizadas las definiciones de antimalware en los dispositivos de la organización.*|[Configurar actualizaciones de definiciones para Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/> [Uso de Configuration Manager para entregar actualizaciones de definiciones](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr)|
|**Habilitar Protección de red** para evitar que los empleados usen aplicaciones que contengan contenido malintencionado en Internet <br/><br/> *Se recomienda usar el [modo de auditoría](/microsoft-365/security/defender-endpoint/evaluate-network-protection) al principio para la protección de red en un entorno de prueba para ver qué aplicaciones se bloquearían antes de implementarse.*|[Activar la protección de red con Configuration Manager](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)|
|**Configuración del acceso controlado a carpetas** para protegerse frente a ransomware <br/><br/> *El acceso controlado a carpetas también se conoce como protección contra antiransomware.*|[Endpoint Protection: acceso controlado a carpetas](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [Habilitación del acceso controlado a carpetas en Administración de configuración de puntos de conexión de Microsoft](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Configuración del portal de Microsoft 365 Defender

Si aún no lo ha hecho, configure el portal de Microsoft 365 Defender para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de la organización. Consulte Mientras se detectó y detuvo el ataque, las alertas, como una "alerta de acceso inicial", se desencadenaron y aparecieron en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). También puede configurar si y qué características pueden ver los usuarios finales en el portal de Microsoft 365 Defender.

- [Introducción a Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [Endpoint Protection: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información general sobre la administración de vulnerabilidades de Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Visite el panel de operaciones de seguridad del portal de Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [Administración de Microsoft Defender para punto de conexión con Intune](manage-mde-post-migration-intune.md)
