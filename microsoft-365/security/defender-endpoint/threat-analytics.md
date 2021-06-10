---
title: Seguimiento y respuesta a amenazas emergentes con Microsoft Defender para análisis de amenazas de extremo
ms.reviewer: ''
description: Obtenga información sobre las amenazas emergentes y las técnicas de ataque y cómo detenerlos. Evalúe su impacto en la organización y evalúe la resistencia de la organización.
keywords: análisis de amenazas, evaluación de riesgos, mitigación del sistema operativo, mitigación de microcódigos, estado de mitigación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 61b6b0c19730045468c77e5f24bf18470aa5dbd5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688266"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="07aaa-105">Seguimiento y respuesta a amenazas emergentes con análisis de amenazas</span><span class="sxs-lookup"><span data-stu-id="07aaa-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07aaa-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="07aaa-106">**Applies to:**</span></span>
- [<span data-ttu-id="07aaa-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="07aaa-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="07aaa-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07aaa-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="07aaa-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="07aaa-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="07aaa-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="07aaa-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="07aaa-111">Con los adversarios más sofisticados y las nuevas amenazas que surgen con frecuencia y con frecuencia, es fundamental poder hacer lo siguiente rápidamente:</span><span class="sxs-lookup"><span data-stu-id="07aaa-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="07aaa-112">Evaluar el impacto de las nuevas amenazas</span><span class="sxs-lookup"><span data-stu-id="07aaa-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="07aaa-113">Revisar la resistencia frente a las amenazas o su exposición a las amenazas.</span><span class="sxs-lookup"><span data-stu-id="07aaa-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="07aaa-114">Identificar las acciones que puede realizar para detener o contener las amenazas</span><span class="sxs-lookup"><span data-stu-id="07aaa-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="07aaa-115">El análisis de amenazas es un conjunto de informes de investigadores expertos en seguridad de Microsoft que cubren las amenazas más relevantes, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="07aaa-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="07aaa-116">Actores de amenazas activas y sus campañas</span><span class="sxs-lookup"><span data-stu-id="07aaa-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="07aaa-117">Técnicas de ataque populares y nuevas</span><span class="sxs-lookup"><span data-stu-id="07aaa-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="07aaa-118">Vulnerabilidades críticas</span><span class="sxs-lookup"><span data-stu-id="07aaa-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="07aaa-119">Superficies de ataque comunes</span><span class="sxs-lookup"><span data-stu-id="07aaa-119">Common attack surfaces</span></span>
- <span data-ttu-id="07aaa-120">Malware común</span><span class="sxs-lookup"><span data-stu-id="07aaa-120">Prevalent malware</span></span>

<span data-ttu-id="07aaa-121">Cada informe proporciona un análisis detallado de una amenaza y una amplia guía sobre cómo defenderse de esa amenaza.</span><span class="sxs-lookup"><span data-stu-id="07aaa-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="07aaa-122">También incorpora datos de la red, que indican si la amenaza está activa y si tiene protecciones aplicables.</span><span class="sxs-lookup"><span data-stu-id="07aaa-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="07aaa-123">Vea este breve vídeo para obtener más información sobre cómo los análisis de amenazas pueden ayudarle a realizar un seguimiento de las amenazas más recientes y detenerlos.</span><span class="sxs-lookup"><span data-stu-id="07aaa-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="07aaa-124">Ver el panel de análisis de amenazas</span><span class="sxs-lookup"><span data-stu-id="07aaa-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="07aaa-125">El panel de análisis de amenazas es un gran punto de partida para llegar a los informes que son más relevantes para su organización.</span><span class="sxs-lookup"><span data-stu-id="07aaa-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="07aaa-126">Resume las amenazas en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="07aaa-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="07aaa-127">**Últimas amenazas:** enumera los informes de amenazas publicados más recientemente, junto con el número de dispositivos con alertas activas y resueltas.</span><span class="sxs-lookup"><span data-stu-id="07aaa-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="07aaa-128">**Amenazas de alto** impacto: enumera las amenazas que han tenido mayor impacto en la organización.</span><span class="sxs-lookup"><span data-stu-id="07aaa-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="07aaa-129">En esta sección se clasifican las amenazas por el número de dispositivos que tienen alertas activas.</span><span class="sxs-lookup"><span data-stu-id="07aaa-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="07aaa-130">**Resumen de amenazas:** muestra el impacto general de las amenazas rastreadas mostrando el número de amenazas con alertas activas y resueltas.</span><span class="sxs-lookup"><span data-stu-id="07aaa-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="07aaa-131">Seleccione una amenaza en el panel para ver el informe de esa amenaza.</span><span class="sxs-lookup"><span data-stu-id="07aaa-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![Imagen de un panel de análisis de amenazas](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="07aaa-133">Ver un informe de análisis de amenazas</span><span class="sxs-lookup"><span data-stu-id="07aaa-133">View a threat analytics report</span></span>

<span data-ttu-id="07aaa-134">Cada informe de análisis de amenazas proporciona información en tres secciones: **Overview**, **Analyst report** y **Mitigations**.</span><span class="sxs-lookup"><span data-stu-id="07aaa-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="07aaa-135">Información general: comprender rápidamente la amenaza, evaluar su impacto y revisar las defensas</span><span class="sxs-lookup"><span data-stu-id="07aaa-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="07aaa-136">La **sección** Información general proporciona una vista previa del informe detallado del analista.</span><span class="sxs-lookup"><span data-stu-id="07aaa-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="07aaa-137">También proporciona gráficos que resaltan el impacto de la amenaza para su organización y su exposición a través de dispositivos mal configurados y sin aparear.</span><span class="sxs-lookup"><span data-stu-id="07aaa-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="07aaa-138">![Imagen de la sección información general de un informe de análisis de amenazas ](images/ta-overview.png)
 _Sección información general de un informe de análisis de amenazas_</span><span class="sxs-lookup"><span data-stu-id="07aaa-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="07aaa-139">Evaluar el impacto en la organización</span><span class="sxs-lookup"><span data-stu-id="07aaa-139">Assess the impact to your organization</span></span>
<span data-ttu-id="07aaa-140">Cada informe incluye gráficos diseñados para proporcionar información sobre el impacto organizativo de una amenaza:</span><span class="sxs-lookup"><span data-stu-id="07aaa-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="07aaa-141">**Dispositivos con alertas:** muestra el número actual de dispositivos distintos que se han visto afectados por la amenaza.</span><span class="sxs-lookup"><span data-stu-id="07aaa-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="07aaa-142">Un dispositivo se clasifica como **Activo** si hay al menos una  alerta asociada a esa amenaza y **Resuelto** si se han resuelto todas las alertas asociadas con la amenaza en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07aaa-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="07aaa-143">**Dispositivos con alertas a lo** largo del tiempo: muestra el número de dispositivos distintos con **alertas activas** **y** resueltas con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="07aaa-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="07aaa-144">El número de alertas resueltas indica la rapidez con la que la organización responde a las alertas asociadas con una amenaza.</span><span class="sxs-lookup"><span data-stu-id="07aaa-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="07aaa-145">Lo ideal es que el gráfico muestre las alertas resueltas en unos días.</span><span class="sxs-lookup"><span data-stu-id="07aaa-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="07aaa-146">Revisar la resistencia y la postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="07aaa-146">Review security resilience and posture</span></span>
<span data-ttu-id="07aaa-147">Cada informe incluye gráficos que proporcionan información general sobre la resistencia de la organización frente a una amenaza determinada:</span><span class="sxs-lookup"><span data-stu-id="07aaa-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="07aaa-148">**Estado de configuración de** seguridad: muestra el número de dispositivos que han aplicado la configuración de seguridad recomendada que puede ayudar a mitigar la amenaza.</span><span class="sxs-lookup"><span data-stu-id="07aaa-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="07aaa-149">Los dispositivos se consideran **seguros** si han aplicado _toda_ la configuración de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="07aaa-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="07aaa-150">**Estado de revisión de vulnerabilidad:** muestra el número de dispositivos que han aplicado actualizaciones de seguridad o revisiones que abordan las vulnerabilidades explotadas por la amenaza.</span><span class="sxs-lookup"><span data-stu-id="07aaa-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="07aaa-151">Informe de analistas: obtener información de expertos de los investigadores de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="07aaa-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="07aaa-152">Vaya a la **sección Informe de** analistas para leer la escritura detallada del experto.</span><span class="sxs-lookup"><span data-stu-id="07aaa-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="07aaa-153">La mayoría de los informes proporcionan descripciones detalladas de las cadenas de ataque, incluidas las tácticas y técnicas [](advanced-hunting-overview.md) asignadas al marco de CK de MITRE ATT&, listas exhaustivas de recomendaciones y instrucciones de búsqueda de amenazas eficaces.</span><span class="sxs-lookup"><span data-stu-id="07aaa-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="07aaa-154">Más información sobre el informe de analistas</span><span class="sxs-lookup"><span data-stu-id="07aaa-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="07aaa-155">Mitigaciones: revisar la lista de mitigaciones y el estado de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="07aaa-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="07aaa-156">En la **sección Mitigaciones,** revise la lista de recomendaciones específicas que se pueden usar y que pueden ayudarle a aumentar la resistencia de la organización frente a la amenaza.</span><span class="sxs-lookup"><span data-stu-id="07aaa-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="07aaa-157">La lista de mitigaciones rastreadas incluye:</span><span class="sxs-lookup"><span data-stu-id="07aaa-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="07aaa-158">**Actualizaciones de seguridad:** implementación de actualizaciones de seguridad o revisiones para vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="07aaa-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="07aaa-159">**Antivirus de Microsoft Defender configuración**</span><span class="sxs-lookup"><span data-stu-id="07aaa-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="07aaa-160">Versión de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="07aaa-160">Security intelligence version</span></span>
  - <span data-ttu-id="07aaa-161">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="07aaa-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="07aaa-162">Protección de aplicaciones potencialmente no deseadas (PUA)</span><span class="sxs-lookup"><span data-stu-id="07aaa-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="07aaa-163">Protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="07aaa-163">Real-time protection</span></span>
 
<span data-ttu-id="07aaa-164">La información de mitigación de esta sección incorpora datos de [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md), que también proporciona información detallada de detalles de varios vínculos del informe.</span><span class="sxs-lookup"><span data-stu-id="07aaa-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="07aaa-165">![Imagen de la sección mitigaciones de un informe de análisis de amenazas Sección ](images/ta-mitigations.png)
 _Mitigaciones de un informe de análisis de amenazas_</span><span class="sxs-lookup"><span data-stu-id="07aaa-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="07aaa-166">Detalles y limitaciones adicionales del informe</span><span class="sxs-lookup"><span data-stu-id="07aaa-166">Additional report details and limitations</span></span>
<span data-ttu-id="07aaa-167">Al usar los informes, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07aaa-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="07aaa-168">Los datos se tienen en cuenta en el ámbito del control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="07aaa-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="07aaa-169">Verá el estado de los dispositivos en grupos a los [que puede tener acceso](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="07aaa-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="07aaa-170">Los gráficos reflejan solo las mitigaciones a las que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="07aaa-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="07aaa-171">Compruebe en el informe información general para ver mitigaciones adicionales que no se muestran en los gráficos.</span><span class="sxs-lookup"><span data-stu-id="07aaa-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="07aaa-172">Las mitigaciones no garantizan una resistencia completa.</span><span class="sxs-lookup"><span data-stu-id="07aaa-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="07aaa-173">Las mitigaciones proporcionadas reflejan las mejores acciones posibles necesarias para mejorar la resistencia.</span><span class="sxs-lookup"><span data-stu-id="07aaa-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="07aaa-174">Los dispositivos se cuentan como "no disponibles" si no han transmitido datos al servicio.</span><span class="sxs-lookup"><span data-stu-id="07aaa-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="07aaa-175">Las estadísticas relacionadas con el antivirus se basan en Antivirus de Microsoft Defender configuración.</span><span class="sxs-lookup"><span data-stu-id="07aaa-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="07aaa-176">Los dispositivos con soluciones antivirus de terceros pueden aparecer como "expuestos".</span><span class="sxs-lookup"><span data-stu-id="07aaa-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="07aaa-177">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="07aaa-177">Related topics</span></span>
- [<span data-ttu-id="07aaa-178">Búsqueda proactiva de amenazas con búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="07aaa-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="07aaa-179">Comprender la sección de informe de analistas</span><span class="sxs-lookup"><span data-stu-id="07aaa-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="07aaa-180">Evaluar y resolver debilidades y exposiciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="07aaa-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)