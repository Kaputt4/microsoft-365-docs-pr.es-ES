---
title: Microsoft Defender para punto de conexión
description: Microsoft Defender para punto de conexión es una plataforma de seguridad de punto de conexión empresarial que ayuda a defenderse contra amenazas persistentes avanzadas.
keywords: introducción a Microsoft Defender para punto de conexión, introducción a Microsoft Defender para punto de conexión, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, sensor de comportamiento automático, seguridad en la nube, análisis, inteligencia sobre amenazas, reducción de la superficie expuesta a ataques, protección de nueva generación, investigación y corrección automatizadas, expertos en amenazas de Microsoft, puntuación de seguridad, búsqueda avanzada, Microsoft 365 Defender, búsqueda de amenazas cibernéticas
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: high
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.custom: intro-overview
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 40450ed20daaa4c3520386aad7d6a416b8b84889
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68234044"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender para punto de conexión es una plataforma empresarial para la seguridad de puntos de conexión concebida para ayudar a impedir, detectar e investigar las amenazas avanzadas, y responder a ellas.

> [!TIP]
> Microsoft Defender para punto de conexión está disponible en dos planes: Defender para punto de conexión Plan 1 y Plan 2. Ahora hay un complemento nuevo de Administración de vulnerabilidades de Microsoft Defender disponible para el Plan 2.
>
> Para obtener más información sobre las características y funcionalidades que se incluyen en cada plan, incluido el nuevo complemento de administración de vulnerabilidades de Defender, consulte [Comparación de planes de Microsoft Defender para punto de conexión](defender-endpoint-plan-1-2.md).

<p><p>

Vea el siguiente vídeo para obtener más información sobre Defender para punto de conexión:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Microsoft Defender para punto de conexión usa la siguiente combinación de tecnologías integrada en Windows 10 y el robusto servicio en la nube de Microsoft:

- **Sensores de comportamiento del punto de conexión**. Integrados en Windows 10, estos sensores recopilan y procesan señales de comportamiento desde el sistema operativo. Los sensores envían estos datos a la instancia de nube privada aislada de Microsoft Defender para punto de conexión.

- **Análisis de seguridad en la nube**: al aprovechar los macrodatos, el aprendizaje de dispositivos y la óptica exclusiva de Microsoft en todo el ecosistema de Windows, los productos empresariales en la nube (como Office 365) y los activos en línea, las señales de comportamiento se traducen en información, detecciones y respuestas recomendadas a amenazas avanzadas.

- **Inteligencia sobre amenazas**. Generada por cazadores de Microsoft, equipos de seguridad y aumentada por la inteligencia de amenazas proporcionada por los socios, la inteligencia de amenazas permite a Microsoft Defender para punto de conexión identificar herramientas, técnicas y procedimientos de atacantes, y generar alertas cuando se observan en los datos de sensores recopilados.

<center><h2>Microsoft Defender para punto de conexión</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/logo-mdvm.png" alt="Vulnerability Management"> <br><b> Administración de vulnerabilidades de Defender</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Reducción de la superficie expuesta a ataques</b></center></a></td>
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

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0]

> [!TIP]
> - Obtenga información sobre las mejoras más recientes de Defender para punto de conexión: [novedades de Microsoft Defender para punto de conexión](whats-new-in-microsoft-defender-endpoint.md).
> - Microsoft Defender para punto de conexión mostró funcionalidades de detección y óptica líderes del sector en la reciente evaluación de MITRE. Lectura: [Insights de la evaluación basada en MITRE ATT&CK](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).


> [!IMPORTANT]
> Las funcionalidades de las plataformas que no son de Windows pueden ser diferentes de las de Windows. Para obtener más información sobre qué funcionalidades están disponibles para plataformas que no son de Windows, consulte [Microsoft Defender para punto de conexión para plataformas que no son de Windows](/microsoft-365/security/defender-endpoint/non-windows).

<a name="tvm"></a>

**[Administración de vulnerabilidades de Defender](../defender-vulnerability-management/defender-vulnerability-management.md)**

Las funcionalidades de administración de vulnerabilidades básicas integradas usan un enfoque moderno basado en riesgos para detectar, evaluar, priorizar y corregir vulnerabilidades de puntos de conexión y configuraciones incorrectas. Para mejorar aún más la capacidad de evaluar el nivel de seguridad y de reducir el riesgo, está disponible un complemento nuevo de administración de vulnerabilidades de Defender para el Plan 2.

Para obtener más información sobre las distintas funcionalidades de administración de vulnerabilidades disponibles, consulte [Comparación de ofertas de Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md).

<a name="asr"></a>

**[Reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)**

El conjunto de capacidades de reducción de la superficie expuesta a ataques proporciona la primera línea de defensa de la pila. Al garantizar que las opciones de configuración se establecen correctamente y se aplican técnicas de mitigación de vulnerabilidades, las capacidades se resisten a los ataques y la explotación. Este conjunto de funcionalidades también incluye [protección de red](network-protection.md) y [protección web](web-protection-overview.md), que regulan el acceso a direcciones IP, dominios y direcciones URL malintencionados.

<a name="ngp"></a>

**[Protección de última generación](next-generation-protection.md)**

Para reforzar aún más el perímetro de seguridad de la red, Microsoft Defender para punto de conexión usa la protección de próxima generación diseñada para detectar todos los tipos de amenazas emergentes.

<a name="edr"></a>

**[Detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md)**

Las funcionalidades de detección y respuesta de puntos de conexión se implementan para detectar, investigar y responder a amenazas avanzadas que pueden haber superado los dos primeros pilares de seguridad. [La búsqueda avanzada](advanced-hunting-overview.md) proporciona una herramienta de búsqueda de amenazas basada en consultas que le permite buscar infracciones de forma proactiva y crear detecciones personalizadas.

<a name="ai"></a>

**[Investigación y corrección automatizadas](automated-investigations.md)**

Junto con la capacidad de responder rápidamente a ataques avanzados, Microsoft Defender para punto de conexión ofrece capacidades de investigación y corrección automáticas que ayudan a reducir el volumen de alertas en minutos a escala.

<a name="ss"></a>

**[Puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)**

Defender para punto de conexión incluye Puntuación de seguridad de Microsoft para dispositivos para ayudarlo a evaluar dinámicamente el estado de seguridad de su red empresarial, identificar sistemas desprotegidos y tomar las acciones recomendadas para mejorar la seguridad general de su organización.

<a name="mte"></a>

**[Expertos en amenazas de Microsoft](microsoft-threat-experts.md)**

El nuevo servicio administrado de búsqueda de amenazas de Microsoft Defender para punto de conexión proporciona búsqueda proactiva, priorización y contexto e información adicional que empoderan aún más a los centros de operaciones de seguridad (SOC) para identificar y responder a las amenazas de manera rápida y precisa.

> [!IMPORTANT]
> Los clientes de Defender para punto de conexión deben solicitar el servicio de Búsqueda de amenazas administrado por Expertos en amenazas de Microsoft para obtener notificaciones proactivas de ataques dirigidos y colaborar con expertos a petición. Expertos a petición es un servicio de complemento. Las notificaciones de ataques dirigidos siempre se incluyen después de que se le haya aceptado en el servicio de búsqueda de amenazas administrado por Expertos en amenazas de Microsoft.
>
> Si aún no está inscrito y desea disfrutar de sus ventajas, vaya a **Configuración** \> **Características generales** \> **Características avanzadas** \> **Expertos en amenazas de Microsoft** para solicitar el servicio. Una vez aceptado, obtendrá las ventajas de las notificaciones de ataques dirigidos e iniciará una prueba de 90 días de Expertos a petición. Póngase en contacto con su representante de Microsoft para obtener una suscripción completa a Expertos a petición.

<a name="apis"></a>

**[Configuración y administración centralizadas, API](management-apis.md)**

Integre Microsoft Defender para punto de conexión en los flujos de trabajo existentes.

<a name="mtp"></a>

**[Integración con las soluciones de Microsoft](threat-protection-integration.md)**

Defender para punto de conexión se integra directamente con varias soluciones de Microsoft, entre las que se incluyen:

- Microsoft Defender for Cloud
- Microsoft Sentinel
- Intune
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity
- Microsoft Defender para Office
- Skype Empresarial

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)**

Con Microsoft 365 Defender, Defender para punto de conexión y varias soluciones de seguridad de Microsoft forman un conjunto unificado de defensa empresarial previa y posterior a la infracción que se integra de forma nativa en los puntos de conexión, la identidad, el correo electrónico y las aplicaciones para detectar, evitar, investigar y responder automáticamente a ataques sofisticados.


## <a name="training-for-security-analysts"></a>Aprendizaje para analistas de seguridad

Con esta ruta de aprendizaje de Microsoft Learn, podrá comprender Defender para punto de conexión y cómo puede ayudarle a evitar, detectar, investigar y responder a amenazas en los puntos de conexión de su organización: sus dispositivos y sistemas.

|Aprendizaje:|Detectar y responder a ataques cibernéticos con Microsoft 365 Defender|
|---|---|
|![Icono de aprendizaje de Microsoft 365 Defender.](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft Defender para punto de conexión es una solución de seguridad de puntos de conexión que ofrece administración de amenazas y vulnerabilidades, protección de puntos de conexión, detección y respuesta de puntos de conexión, defensa contra amenazas móviles y servicios administrados en una única plataforma unificada.<p> 2 h 25 min - Ruta de aprendizaje - 9 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/training/paths/defender-endpoint-fundamentals/)
