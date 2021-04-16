---
title: Microsoft Defender para punto de conexión
description: Microsoft Defender para endpoint es una plataforma de seguridad de extremo de empresa que ayuda a defenderse de las amenazas persistentes avanzadas.
keywords: introducción a Microsoft Defender para endpoint, introducción a protección contra amenazas avanzada de Microsoft Defender, introducción a Microsoft Defender para endpoint, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, sensor de comportamiento de máquina, seguridad en la nube, análisis, inteligencia de amenazas, reducción de superficie de ataque, protección de última generación, investigación automatizada y corrección, expertos en amenazas de Microsoft, puntuación segura, búsqueda avanzada, protección contra amenazas de Microsoft, búsqueda de amenazas cibernéticas
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
ms.openlocfilehash: adc7d780c1af73d8cb4fe229720ac2ed74f90251
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861832"
---
# <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="50b8a-104">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="50b8a-104">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="50b8a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="50b8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="50b8a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="50b8a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="50b8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50b8a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="50b8a-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="50b8a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="50b8a-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="50b8a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> <span data-ttu-id="50b8a-110">Para obtener más información acerca de las características y funcionalidades de Windows 10 Enterprise Edition, consulta [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span><span class="sxs-lookup"><span data-stu-id="50b8a-110">For more info about Windows 10 Enterprise Edition features and functionality, see [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span></span>

<span data-ttu-id="50b8a-111">Microsoft Defender para endpoint es una plataforma de seguridad de extremo de empresa diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas.</span><span class="sxs-lookup"><span data-stu-id="50b8a-111">Microsoft Defender for Endpoint is an enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span>
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

<span data-ttu-id="50b8a-112">Defender for Endpoint usa la siguiente combinación de tecnología integrada en Windows 10 y el robusto servicio en la nube de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="50b8a-112">Defender for Endpoint uses the following combination of technology built into Windows 10 and Microsoft's robust cloud service:</span></span>

-   <span data-ttu-id="50b8a-113">**Sensores** de comportamiento de extremo: incrustados en Windows 10, estos sensores recopilan y procesan señales de comportamiento del sistema operativo y envían estos datos de sensor a la instancia privada, aislada y en la nube de Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="50b8a-113">**Endpoint behavioral sensors**: Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and send this sensor data to your private, isolated, cloud instance of Microsoft Defender for Endpoint.</span></span>


-   <span data-ttu-id="50b8a-114">**Análisis** de seguridad en la nube: aprovechando los datos grandes, el aprendizaje de dispositivos y la óptica única de Microsoft en todo el ecosistema de Windows, los productos en la nube empresarial (como Office 365) y los activos en línea, las señales de comportamiento se traducen en información, detecciones y respuestas recomendadas a amenazas avanzadas.</span><span class="sxs-lookup"><span data-stu-id="50b8a-114">**Cloud security analytics**: Leveraging big-data, device-learning, and unique Microsoft optics across the Windows ecosystem, enterprise cloud products (such as Office 365), and online assets, behavioral signals are translated into insights, detections, and recommended responses to advanced threats.</span></span>

-   <span data-ttu-id="50b8a-115">Inteligencia de **amenazas:** generada por cazadores de Microsoft, equipos de seguridad y aumentada por la inteligencia de amenazas proporcionada por socios, la inteligencia de amenazas permite a Defender for Endpoint identificar herramientas, técnicas y procedimientos de atacantes y generar alertas cuando se observan en datos de sensor recopilados.</span><span class="sxs-lookup"><span data-stu-id="50b8a-115">**Threat intelligence**: Generated by Microsoft hunters, security teams, and augmented by threat intelligence provided by partners, threat intelligence enables Defender for Endpoint to identify attacker tools, techniques, and procedures, and generate alerts when they are observed in collected sensor data.</span></span>

<center><h2><span data-ttu-id="50b8a-116">Microsoft Defender para endpoint</center></span><span class="sxs-lookup"><span data-stu-id="50b8a-116">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><span data-ttu-id="50b8a-117"><b>Administración & vulnerabilidades de amenazas</b></center></a></span><span class="sxs-lookup"><span data-stu-id="50b8a-117"><b>Threat & Vulnerability Management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><span data-ttu-id="50b8a-118"><b>Reducción de superficie de ataque</b></center></a></span><span class="sxs-lookup"><span data-stu-id="50b8a-118"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <span data-ttu-id="50b8a-119"><b>Protección de última generación</b></a></center></span><span class="sxs-lookup"><span data-stu-id="50b8a-119"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <span data-ttu-id="50b8a-120"><b>Detección y respuesta de puntos de conexión</b></a></center></span><span class="sxs-lookup"><span data-stu-id="50b8a-120"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <span data-ttu-id="50b8a-121"><b>Investigación y corrección automatizadas</b></a></center></span><span class="sxs-lookup"><span data-stu-id="50b8a-121"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <span data-ttu-id="50b8a-122"><b>Expertos en amenazas de Microsoft</b></a></center></span><span class="sxs-lookup"><span data-stu-id="50b8a-122"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="50b8a-123">
<a href="#apis"><center><b>Configuración y administración centralizadas, API</a></span><span class="sxs-lookup"><span data-stu-id="50b8a-123">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="50b8a-124"><a href="#mtp"><center><b>Protección contra amenazas de Microsoft</a></span><span class="sxs-lookup"><span data-stu-id="50b8a-124"><a href="#mtp"><center><b>Microsoft Threat Protection</a></span></span></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - <span data-ttu-id="50b8a-125">Obtenga información sobre las mejoras más recientes en Defender para endpoint: [Novedades de Microsoft Defender para endpoint.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="50b8a-125">Learn about the latest enhancements in Defender for Endpoint: [What's new in Microsoft Defender for Endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
> - <span data-ttu-id="50b8a-126">Microsoft Defender para endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE.</span><span class="sxs-lookup"><span data-stu-id="50b8a-126">Microsoft Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="50b8a-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="50b8a-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<a name="tvm"></a>

<span data-ttu-id="50b8a-128">**[Administración & vulnerabilidades de amenazas](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-128">**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="50b8a-129">Esta funcionalidad integrada usa un enfoque basado en riesgos que cambia el juego para la detección, priorización y corrección de vulnerabilidades y configuraciones erróneas de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="50b8a-129">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span> 

<a name="asr"></a>

<span data-ttu-id="50b8a-130">**[Reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-130">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="50b8a-131">El conjunto de capacidades de reducción de superficie de ataque proporciona la primera línea de defensa de la pila.</span><span class="sxs-lookup"><span data-stu-id="50b8a-131">The attack surface reduction set of capabilities provides the first line of defense in the stack.</span></span> <span data-ttu-id="50b8a-132">Al garantizar que las opciones de configuración se establecen correctamente y se aplican técnicas de mitigación de vulnerabilidades, las capacidades resisten los ataques y la explotación.</span><span class="sxs-lookup"><span data-stu-id="50b8a-132">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, the capabilities resist attacks and exploitation.</span></span> <span data-ttu-id="50b8a-133">Este conjunto de funcionalidades también incluye protección [de](network-protection.md) red y [protección web,](web-protection-overview.md)que regulan el acceso a direcciones IP malintencionadas, dominios y direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="50b8a-133">This set of capabilities also includes [network protection](network-protection.md) and [web protection](web-protection-overview.md), which regulate access to malicious IP addresses, domains, and URLs.</span></span> 

<a name="ngp"></a>

<span data-ttu-id="50b8a-134">**[Protección de última generación](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-134">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="50b8a-135">Para reforzar aún más el perímetro de seguridad de la red, Microsoft Defender para endpoint usa la protección de última generación diseñada para detectar todo tipo de amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="50b8a-135">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

<a name="edr"></a>

<span data-ttu-id="50b8a-136">**[EDR](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-136">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="50b8a-137">Las capacidades de detección y respuesta de extremos se ponen en marcha para detectar, investigar y responder a amenazas avanzadas que pueden haber pasado los dos primeros pilares de seguridad.</span><span class="sxs-lookup"><span data-stu-id="50b8a-137">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to advanced threats that may have made it past the first two security pillars.</span></span> <span data-ttu-id="50b8a-138">[La búsqueda avanzada](advanced-hunting-overview.md) proporciona una herramienta de búsqueda de amenazas basada en consultas que le permite encontrar de forma proactiva infracciones y crear detecciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="50b8a-138">[Advanced hunting](advanced-hunting-overview.md) provides a query-based threat-hunting tool that lets you proactively find breaches and create custom detections.</span></span>

<a name="ai"></a>

<span data-ttu-id="50b8a-139">**[Investigación y corrección automatizadas](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-139">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="50b8a-140">Junto con la capacidad de responder rápidamente a ataques avanzados, Microsoft Defender para Endpoint ofrece capacidades automáticas de investigación y corrección que ayudan a reducir el volumen de alertas en minutos a escala.</span><span class="sxs-lookup"><span data-stu-id="50b8a-140">In conjunction with being able to quickly respond to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span> 

<a name="ss"></a>

<span data-ttu-id="50b8a-141">**[Puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-141">**[Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md)**</span></span><br>

<span data-ttu-id="50b8a-142">Defender for Endpoint incluye Puntuación segura de Microsoft para dispositivos para ayudarle a evaluar dinámicamente el estado de seguridad de su red empresarial, identificar sistemas sin protección y realizar acciones recomendadas para mejorar la seguridad general de su organización.</span><span class="sxs-lookup"><span data-stu-id="50b8a-142">Defender for Endpoint includes Microsoft Secure Score for Devices to help you dynamically assess the security state of your enterprise network, identify unprotected systems, and take recommended actions to improve the overall security of your organization.</span></span>

<a name="mte"></a>

<span data-ttu-id="50b8a-143">**[Expertos en amenazas de Microsoft](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="50b8a-144">El nuevo servicio de búsqueda de amenazas administradas de Microsoft Defender para Endpoint proporciona búsqueda proactiva, priorización y contexto y conocimientos adicionales que permiten a los centros de operaciones de seguridad (SOC) identificar y responder a las amenazas de forma rápida y precisa.</span><span class="sxs-lookup"><span data-stu-id="50b8a-144">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights that further empower Security operation centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

>[!IMPORTANT]
><span data-ttu-id="50b8a-145">Los clientes de Defender for Endpoint deben solicitar el servicio de búsqueda de amenazas administradas por Expertos en amenazas de Microsoft para obtener notificaciones proactivas de ataques dirigidos y colaborar con expertos a petición.</span><span class="sxs-lookup"><span data-stu-id="50b8a-145">Defender for Endpoint customers need to apply for the Microsoft Threat Experts managed threat hunting service to get proactive Targeted Attack Notifications and to collaborate with experts on demand.</span></span> <span data-ttu-id="50b8a-146">Expertos a petición es un servicio de complemento.</span><span class="sxs-lookup"><span data-stu-id="50b8a-146">Experts on Demand is an add-on service.</span></span> <span data-ttu-id="50b8a-147">Las notificaciones de ataques dirigidos siempre se incluyen después de haber sido aceptados en el servicio de búsqueda de amenazas administrado por expertos en amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="50b8a-147">Targeted Attack Notifications are always included after you have been accepted into Microsoft Threat Experts managed threat hunting service.</span></span><p>
><p><span data-ttu-id="50b8a-148">Si aún no está inscrito y desea experimentar sus <b></b> ventajas, vaya a Configuración > <b>General</b> > <b>Advanced features</b> Microsoft Threat > <b>Experts</b> para aplicar.</span><span class="sxs-lookup"><span data-stu-id="50b8a-148">If you are not enrolled yet and would like to experience its benefits, go to <b>Settings</b> > <b>General</b> > <b>Advanced features</b> > <b>Microsoft Threat Experts</b> to apply.</span></span> <span data-ttu-id="50b8a-149">Una vez aceptado, se obtienen las ventajas de las notificaciones de ataque dirigido e inicia una prueba de 90 días de Expertos a petición.</span><span class="sxs-lookup"><span data-stu-id="50b8a-149">Once accepted, you will get the benefits of Targeted Attack Notifications, and start a  90-day trial of Experts on Demand.</span></span> <span data-ttu-id="50b8a-150">Póngase en contacto con su representante de Microsoft para obtener una suscripción completa a Expertos a petición.</span><span class="sxs-lookup"><span data-stu-id="50b8a-150">Contact your Microsoft representative to get a full Experts on Demand subscription.</span></span>

<a name="apis"></a>

<span data-ttu-id="50b8a-151">**[Configuración y administración centralizadas, API](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-151">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="50b8a-152">Integre Microsoft Defender para Endpoint en los flujos de trabajo existentes.</span><span class="sxs-lookup"><span data-stu-id="50b8a-152">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>

<a name="mtp"></a>

<span data-ttu-id="50b8a-153">**[Integración con soluciones de Microsoft](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-153">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
<span data-ttu-id="50b8a-154">Defender for Endpoint se integra directamente con varias soluciones de Microsoft, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="50b8a-154">Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="50b8a-155">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="50b8a-155">Azure Security Center</span></span>
- <span data-ttu-id="50b8a-156">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="50b8a-156">Azure Sentinel</span></span>
- <span data-ttu-id="50b8a-157">Intune</span><span class="sxs-lookup"><span data-stu-id="50b8a-157">Intune</span></span>
- <span data-ttu-id="50b8a-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="50b8a-158">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="50b8a-159">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="50b8a-159">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="50b8a-160">Microsoft Defender para Office</span><span class="sxs-lookup"><span data-stu-id="50b8a-160">Microsoft Defender for Office</span></span>
- <span data-ttu-id="50b8a-161">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="50b8a-161">Skype for Business</span></span>

<span data-ttu-id="50b8a-162">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="50b8a-162">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
<span data-ttu-id="50b8a-163">Con Microsoft 365 Defender, Defender para endpoint y varias soluciones de seguridad de Microsoft forman un conjunto de aplicaciones de defensa empresarial unificado previo y posterior a la infracción que se integra de forma nativa en los puntos de conexión, identidad, correo electrónico y aplicaciones para detectar, prevenir, investigar y responder automáticamente a ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="50b8a-163">With Microsoft 365 Defender, Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>


## <a name="related-topic"></a><span data-ttu-id="50b8a-164">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="50b8a-164">Related topic</span></span>
[<span data-ttu-id="50b8a-165">Microsoft Defender para endpoint ayuda a detectar amenazas sofisticadas</span><span class="sxs-lookup"><span data-stu-id="50b8a-165">Microsoft Defender for Endpoint helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
