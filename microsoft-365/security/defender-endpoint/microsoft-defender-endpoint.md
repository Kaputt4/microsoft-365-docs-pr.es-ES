---
title: Microsoft Defender para punto de conexión
description: Microsoft Defender para endpoint es una plataforma de seguridad de extremo de empresa que ayuda a defenderse de las amenazas persistentes avanzadas.
keywords: introducción a Microsoft Defender para endpoint, introducción a Microsoft Defender para endpoint, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, sensor de comportamiento de máquina, seguridad en la nube, análisis, inteligencia de amenazas, reducción de superficie de ataque, protección de última generación, investigación automatizada y corrección, expertos en amenazas de Microsoft, puntuación segura, búsqueda avanzada, Microsoft 365 Defender, búsqueda de amenazas cibernéticas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 57d4506e32db5defe29f2d0e59f72bd4c1998310
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935934"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Para obtener más información acerca de las características y funcionalidades de Windows 10 Enterprise Edition, consulta [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).

Microsoft Defender para endpoint es una plataforma de seguridad de extremo de empresa diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint usa la siguiente combinación de tecnología integrada en Windows 10 y el robusto servicio en la nube de Microsoft:

-   **Sensores** de comportamiento de extremo: incrustados en Windows 10, estos sensores recopilan y procesan señales de comportamiento del sistema operativo y envían estos datos de sensor a la instancia privada, aislada y en la nube de Microsoft Defender para Endpoint.


-   **Análisis** de seguridad en la nube: aprovechando los datos grandes, el aprendizaje de dispositivos y la óptica única de Microsoft en todo el ecosistema de Windows, los productos en la nube empresarial (como Office 365) y los activos en línea, las señales de comportamiento se traducen en información, detecciones y respuestas recomendadas a amenazas avanzadas.

-   Inteligencia de **amenazas:** generada por cazadores de Microsoft, equipos de seguridad y aumentada por la inteligencia de amenazas proporcionada por socios, la inteligencia de amenazas permite a Defender for Endpoint identificar herramientas, técnicas y procedimientos de atacantes y generar alertas cuando se observan en datos de sensor recopilados.

<center><h2>Microsoft Defender para endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Administración & vulnerabilidades de amenazas</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Reducción de superficie de ataque</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Protección de última generación</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Detección y respuesta de puntos de conexión</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Investigación y corrección automatizadas</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Expertos en amenazas de Microsoft</b></a></center></td>
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

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Obtenga información sobre las mejoras más recientes en Defender para endpoint: [Novedades de Microsoft Defender para endpoint.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)
> - Microsoft Defender para endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

<a name="tvm"></a>

**[Administración & vulnerabilidades de amenazas](next-gen-threat-and-vuln-mgt.md)**<br>
Esta funcionalidad integrada usa un enfoque basado en riesgos que cambia el juego para la detección, priorización y corrección de vulnerabilidades y configuraciones erróneas de puntos de conexión. 

<a name="asr"></a>

**[Reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)**<br>
El conjunto de capacidades de reducción de superficie de ataque proporciona la primera línea de defensa de la pila. Al garantizar que las opciones de configuración se establecen correctamente y se aplican técnicas de mitigación de vulnerabilidades, las capacidades resisten los ataques y la explotación. Este conjunto de funcionalidades también incluye protección [de](network-protection.md) red y [protección web,](web-protection-overview.md)que regulan el acceso a direcciones IP malintencionadas, dominios y direcciones URL. 

<a name="ngp"></a>

**[Protección de última generación](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Para reforzar aún más el perímetro de seguridad de la red, Microsoft Defender para endpoint usa la protección de última generación diseñada para detectar todo tipo de amenazas emergentes.

<a name="edr"></a>

**[EDR](overview-endpoint-detection-response.md)**<br>
Las capacidades de detección y respuesta de extremos se ponen en marcha para detectar, investigar y responder a amenazas avanzadas que pueden haber pasado los dos primeros pilares de seguridad. [La búsqueda avanzada](advanced-hunting-overview.md) proporciona una herramienta de búsqueda de amenazas basada en consultas que le permite encontrar de forma proactiva infracciones y crear detecciones personalizadas.

<a name="ai"></a>

**[Investigación y corrección automatizadas](automated-investigations.md)**<br>
Junto con la capacidad de responder rápidamente a ataques avanzados, Microsoft Defender para Endpoint ofrece capacidades automáticas de investigación y corrección que ayudan a reducir el volumen de alertas en minutos a escala. 

<a name="ss"></a>

**[Puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)**<br>

Defender for Endpoint incluye Puntuación segura de Microsoft para dispositivos para ayudarle a evaluar dinámicamente el estado de seguridad de su red empresarial, identificar sistemas sin protección y realizar acciones recomendadas para mejorar la seguridad general de su organización.

<a name="mte"></a>

**[Expertos en amenazas de Microsoft](microsoft-threat-experts.md)**<br>
El nuevo servicio de búsqueda de amenazas administradas de Microsoft Defender para Endpoint proporciona búsqueda proactiva, priorización y contexto y conocimientos adicionales que permiten a los centros de operaciones de seguridad (SOC) identificar y responder a las amenazas de forma rápida y precisa.

>[!IMPORTANT]
>Los clientes de Defender for Endpoint deben solicitar el servicio de búsqueda de amenazas administradas por Expertos en amenazas de Microsoft para obtener notificaciones proactivas de ataques dirigidos y colaborar con expertos a petición. Expertos a petición es un servicio de complemento. Las notificaciones de ataques dirigidos siempre se incluyen después de haber sido aceptados en el servicio de búsqueda de amenazas administrado por expertos en amenazas de Microsoft.<p>
><p>Si aún no está inscrito y desea experimentar sus <b></b> ventajas, vaya a Configuración > <b>General</b> > <b>Advanced features</b> Microsoft Threat > <b>Experts</b> para aplicar. Una vez aceptado, se obtienen las ventajas de las notificaciones de ataque dirigido e inicia una prueba de 90 días de Expertos a petición. Póngase en contacto con su representante de Microsoft para obtener una suscripción completa a Expertos a petición.

<a name="apis"></a>

**[Configuración y administración centralizadas, API](management-apis.md)**<br>
Integre Microsoft Defender para Endpoint en los flujos de trabajo existentes.

<a name="mtp"></a>

**[Integración con soluciones de Microsoft](threat-protection-integration.md)** <br>
Defender for Endpoint se integra directamente con varias soluciones de Microsoft, entre las que se incluyen:
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender for Identity
- Microsoft Defender para Office
- Skype Empresarial

**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Con Microsoft 365 Defender, Defender para endpoint y varias soluciones de seguridad de Microsoft forman un conjunto de aplicaciones de defensa empresarial unificado previo y posterior a la infracción que se integra de forma nativa en los puntos de conexión, identidad, correo electrónico y aplicaciones para detectar, prevenir, investigar y responder automáticamente a ataques sofisticados.


## <a name="related-topic"></a>Tema relacionado
[Microsoft Defender para endpoint ayuda a detectar amenazas sofisticadas](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
