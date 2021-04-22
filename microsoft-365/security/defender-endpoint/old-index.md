---
title: Protección contra amenazas (Windows 10)
description: Microsoft Defender para punto de conexión es una plataforma unificada para la protección preventiva, la detección posterior a la vulneración y la respuesta e investigación automatizadas.
keywords: protección contra amenazas, Microsoft Defender para endpoint, reducción de superficie de ataque, protección de última generación, detección y respuesta de puntos de conexión, investigación y respuesta automatizadas, expertos en amenazas de Microsoft, Puntuación segura de Microsoft para dispositivos, búsqueda avanzada, búsqueda de amenazas cibernéticas, protección contra amenazas web
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 3098c2786874650ad14d226beacd5ec760decef0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934938"
---
# <a name="threat-protection"></a>Protección contra amenazas
[Microsoft Defender para punto de conexión](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) es una plataforma unificada para la protección preventiva, la detección posterior a la vulneración y la respuesta e investigación automatizadas. Defender for Endpoint protege los puntos de conexión frente a amenazas cibernéticas, detecta ataques avanzados e infracciones de datos, automatiza los incidentes de seguridad y mejora la posición de seguridad.

> [!TIP]
> Permitir que los usuarios accedan a los servicios en la nube y a las aplicaciones locales con facilidad y habiliten las capacidades de administración modernas para todos los dispositivos. Para obtener más información, vea [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/). 

<center><h2>Microsoft Defender para endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>Administración & vulnerabilidades de amenazas</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>Reducción de superficie de ataque</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>Protección de última generación</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>Detección y respuesta de puntos de conexión</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>Investigación y corrección automatizadas</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Expertos en amenazas de Microsoft</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Configuración y administración centralizadas, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[Administración de vulnerabilidades y amenazas](next-gen-threat-and-vuln-mgt.md)**<br>
Esta funcionalidad integrada usa un enfoque basado en riesgos que cambia el juego para la detección, priorización y corrección de vulnerabilidades y configuraciones erróneas de puntos de conexión.

- [Introducción & administración de vulnerabilidades de amenazas](next-gen-threat-and-vuln-mgt.md)
- [Introducción](tvm-prerequisites.md)
- [Acceder a su posición de seguridad](tvm-dashboard-insights.md)
- [Mejorar la posición de seguridad y reducir el riesgo](tvm-security-recommendation.md)
- [Comprender las vulnerabilidades de los dispositivos](tvm-software-inventory.md)

<a name="asr"></a>

**[Reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)**<br>
El conjunto de capacidades de reducción de superficie de ataque proporcionan la primera línea de defensa de la pila. Al garantizar que las opciones de configuración se establecen correctamente y se aplican técnicas de mitigación de vulnerabilidades, este conjunto de capacidades resiste los ataques y la explotación.

- [Aislamiento basado en hardware](overview-hardware-based-isolation.md)
- [Control de la aplicación](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Control de dispositivos](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Protección contra vulnerabilidades de seguridad](exploit-protection.md)
- [Protección de red,](network-protection.md) [protección web](web-protection-overview.md)
- [Acceso controlado a carpetas](controlled-folders.md)
- [Firewall de red](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Reglas de la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)

<a name="ngp"></a>

**[Protección de última generación](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Para reforzar aún más el perímetro de seguridad de la red, Microsoft Defender para endpoint usa la protección de última generación diseñada para detectar todo tipo de amenazas emergentes.

- [Supervisión del comportamiento](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [Protección basada en la nube](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [Aprendizaje automático](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [Protección de direcciones URL](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [Servicio de espacio aislado automatizado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[EDR](overview-endpoint-detection-response.md)**<br>
Las capacidades de detección y respuesta de puntos de conexión se ponen en marcha para detectar, investigar y responder a intentos de intrusión e infracciones activas. Con la búsqueda avanzada, tienes una herramienta de búsqueda de amenazas basada en consultas que permite a los usuarios encontrar de forma proactiva infracciones y crear detecciones personalizadas.

- [Alertas](alerts-queue.md)
- [Datos de punto de conexión históricos](investigate-machines.md#timeline)
- [Orquestación de respuesta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Colección forense](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [Inteligencia de amenazas](threat-indicator-concepts.md)
- [Servicio avanzado de detonación y análisis](respond-file-alerts.md#deep-analysis)
- [Búsqueda avanzada de amenazas](advanced-hunting-overview.md)
    - [Detecciones personalizadas](overview-custom-detections.md)

<a name="ai"></a>

**[Investigación y corrección automatizadas](automated-investigations.md)**<br>
Además de responder rápidamente a ataques avanzados, Microsoft Defender para Endpoint ofrece capacidades automáticas de investigación y corrección que ayudan a reducir el volumen de alertas en minutos a escala.

- [Investigación y corrección automatizadas](automated-investigations.md)
- [Ver detalles y resultados de las investigaciones automatizadas](auto-investigation-action-center.md)
- [Ver y aprobar acciones de corrección](manage-auto-investigation.md)

<a name="mte"></a>

**[Expertos en amenazas de Microsoft](microsoft-threat-experts.md)**<br>
El nuevo servicio de búsqueda de amenazas administradas de Microsoft Defender para endpoint proporciona búsqueda proactiva, priorización y contexto e información adicionales. Los expertos en amenazas de Microsoft habilitan aún más a los Centros de operaciones de seguridad (SOC) para identificar y responder a las amenazas de forma rápida y precisa.

- [Notificación de ataque dirigido](microsoft-threat-experts.md)
- [Expertos a petición](microsoft-threat-experts.md)
- [Configurar el servicio de búsqueda administrada de Microsoft 365 Defender](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[Configuración y administración centralizadas, API](management-apis.md)**<br>
Integre Microsoft Defender para Endpoint en los flujos de trabajo existentes.
- [Incorporación](onboard-configure.md)
- [Integración de API e SIEM](configure-siem.md)
- [API expuestas](apis-intro.md)
- [Control de acceso basado en roles (RBAC)](rbac.md)
- [Informes y tendencias](threat-protection-reports.md)

<a name="integration"></a>
**[Integración con soluciones de Microsoft](threat-protection-integration.md)** <br>
 Microsoft Defender para endpoint se integra directamente con varias soluciones de Microsoft, entre las que se incluyen:
- Intune
- Microsoft Defender para Office 365
- Microsoft Defender for Identity
- Azure Defender
- Skype Empresarial
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Con Microsoft 365 Defender, Microsoft Defender para endpoint y varias soluciones de seguridad de Microsoft forman un conjunto de aplicaciones de defensa empresarial unificado previo y posterior a la infracción que se integra de forma nativa en los puntos de conexión, identidad, correo electrónico y aplicaciones para detectar, prevenir, investigar y responder automáticamente a ataques sofisticados.
