---
title: Hacer seguimiento y responder a amenazas emergentes con el análisis de amenazas
ms.reviewer: ''
description: Obtenga información sobre las amenazas emergentes y las técnicas de ataque y cómo detenerlos. Evalúe su impacto en la organización y evalúe la resistencia de la organización.
keywords: análisis de amenazas, evaluación de riesgos, Microsoft 365 Defender, M365D, estado de mitigación, configuración segura, Microsoft Defender para Office 365, Microsoft Defender para análisis de amenazas de Office 365, análisis de amenazas de MDO, datos de análisis de amenazas MDE y MDO integrados, integración de datos de análisis de amenazas, análisis de amenazas Microsoft 365 Defender integrado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c03dfef28744e2ee565c25d921902b8d11ecb7a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290248"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="b0200-105">Hacer seguimiento y responder a amenazas emergentes con el análisis de amenazas</span><span class="sxs-lookup"><span data-stu-id="b0200-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b0200-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b0200-106">**Applies to:**</span></span>
- <span data-ttu-id="b0200-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0200-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="b0200-108">¿Quiere experimentar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="b0200-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="b0200-109">Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="b0200-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="b0200-110">El análisis de amenazas es nuestra solución de inteligencia de amenazas en el producto de investigadores expertos en seguridad de Microsoft, diseñada para ayudar a los equipos de seguridad a ser lo más eficientes posibles mientras se enfrentan a amenazas emergentes, como:</span><span class="sxs-lookup"><span data-stu-id="b0200-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="b0200-111">Actores de amenazas activas y sus campañas</span><span class="sxs-lookup"><span data-stu-id="b0200-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="b0200-112">Técnicas de ataque populares y nuevas</span><span class="sxs-lookup"><span data-stu-id="b0200-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="b0200-113">Vulnerabilidades críticas</span><span class="sxs-lookup"><span data-stu-id="b0200-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="b0200-114">Superficies de ataque comunes</span><span class="sxs-lookup"><span data-stu-id="b0200-114">Common attack surfaces</span></span>
- <span data-ttu-id="b0200-115">Malware frecuentes</span><span class="sxs-lookup"><span data-stu-id="b0200-115">Prevalent malware</span></span>

<span data-ttu-id="b0200-116">Vea este breve vídeo para obtener más información sobre cómo los análisis de amenazas pueden ayudarle a realizar un seguimiento de las amenazas más recientes y detenerlos.</span><span class="sxs-lookup"><span data-stu-id="b0200-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="b0200-117">Puedes acceder al análisis de amenazas desde la parte superior izquierda de la barra de navegación del portal de seguridad de Microsoft 365 o desde una tarjeta de panel dedicada que muestra las principales amenazas de la organización. Obtener visibilidad de las campañas activas o en curso y saber qué hacer a través del análisis de amenazas puede ayudar a dotar a su equipo de operaciones de seguridad de decisiones fundamentadas.</span><span class="sxs-lookup"><span data-stu-id="b0200-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![Imagen del panel de análisis de amenazas](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="b0200-119">_Dónde acceder al análisis de amenazas_</span><span class="sxs-lookup"><span data-stu-id="b0200-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="b0200-120">Con los adversarios más sofisticados y las nuevas amenazas que surgen con frecuencia y con frecuencia, es fundamental poder hacer lo siguiente rápidamente:</span><span class="sxs-lookup"><span data-stu-id="b0200-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="b0200-121">Identificar y reaccionar ante amenazas emergentes</span><span class="sxs-lookup"><span data-stu-id="b0200-121">Identify and react to emerging threats</span></span>
- <span data-ttu-id="b0200-122">Obtenga información sobre si está actualmente bajo ataque</span><span class="sxs-lookup"><span data-stu-id="b0200-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="b0200-123">Evaluar el impacto de la amenaza en sus activos</span><span class="sxs-lookup"><span data-stu-id="b0200-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="b0200-124">Revisar la resistencia frente a las amenazas o su exposición a las amenazas.</span><span class="sxs-lookup"><span data-stu-id="b0200-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="b0200-125">Identificar las acciones de mitigación, recuperación o prevención que puede realizar para detener o contener las amenazas</span><span class="sxs-lookup"><span data-stu-id="b0200-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="b0200-126">Cada informe proporciona un análisis de una amenaza rastreada y una amplia guía sobre cómo defenderse de esa amenaza.</span><span class="sxs-lookup"><span data-stu-id="b0200-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="b0200-127">También incorpora datos de la red, que indican si la amenaza está activa y si tiene protecciones aplicables.</span><span class="sxs-lookup"><span data-stu-id="b0200-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="b0200-128">Ver el panel de análisis de amenazas</span><span class="sxs-lookup"><span data-stu-id="b0200-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="b0200-129">El panel de análisis de amenazas ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) resalta los informes que son más relevantes para su organización.</span><span class="sxs-lookup"><span data-stu-id="b0200-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="b0200-130">Resume las amenazas en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0200-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="b0200-131">**Últimas amenazas:** enumera los informes de amenazas publicados o actualizados más recientemente, junto con el número de alertas activas y resueltas.</span><span class="sxs-lookup"><span data-stu-id="b0200-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="b0200-132">**Amenazas de alto** impacto: enumera las amenazas que tienen mayor impacto en su organización.</span><span class="sxs-lookup"><span data-stu-id="b0200-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="b0200-133">En esta sección se enumeran primero las amenazas con el mayor número de alertas activas y resueltas.</span><span class="sxs-lookup"><span data-stu-id="b0200-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="b0200-134">**Resumen de amenazas:** proporciona el impacto general de todas las amenazas rastreadas mostrando el número de amenazas con alertas activas y resueltas.</span><span class="sxs-lookup"><span data-stu-id="b0200-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="b0200-135">Seleccione una amenaza en el panel para ver el informe de esa amenaza.</span><span class="sxs-lookup"><span data-stu-id="b0200-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![Captura de pantalla del panel de análisis de amenazas](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="b0200-137">_Panel de análisis de amenazas. También puedes hacer clic en el icono Buscar para claver una palabra clave relacionada con el informe de análisis de amenazas que quieras leer._</span><span class="sxs-lookup"><span data-stu-id="b0200-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="b0200-138">Ver un informe de análisis de amenazas</span><span class="sxs-lookup"><span data-stu-id="b0200-138">View a threat analytics report</span></span>

<span data-ttu-id="b0200-139">Cada informe de análisis de amenazas proporciona información en varias secciones:</span><span class="sxs-lookup"><span data-stu-id="b0200-139">Each threat analytics report provides information in several sections:</span></span>

- [<span data-ttu-id="b0200-140">**Información general**</span><span class="sxs-lookup"><span data-stu-id="b0200-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses)
- [<span data-ttu-id="b0200-141">**Informe de analistas**</span><span class="sxs-lookup"><span data-stu-id="b0200-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="b0200-142">**Incidentes relacionados**</span><span class="sxs-lookup"><span data-stu-id="b0200-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="b0200-143">**Activos afectados**</span><span class="sxs-lookup"><span data-stu-id="b0200-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="b0200-144">**Intentos de correo electrónico impedidos**</span><span class="sxs-lookup"><span data-stu-id="b0200-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="b0200-145">**Mitigaciones**</span><span class="sxs-lookup"><span data-stu-id="b0200-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="b0200-146">Información general: comprender rápidamente la amenaza, evaluar su impacto y revisar las defensas</span><span class="sxs-lookup"><span data-stu-id="b0200-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="b0200-147">La **sección** Información general proporciona una vista previa del informe detallado del analista.</span><span class="sxs-lookup"><span data-stu-id="b0200-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="b0200-148">También proporciona gráficos que resaltan el impacto de la amenaza para su organización y su exposición a través de dispositivos mal configurados y sin aparear.</span><span class="sxs-lookup"><span data-stu-id="b0200-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![Imagen de la sección de información general de un informe de análisis de amenazas](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="b0200-150">_Sección información general de un informe de análisis de amenazas_</span><span class="sxs-lookup"><span data-stu-id="b0200-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="b0200-151">Evaluar el impacto en la organización</span><span class="sxs-lookup"><span data-stu-id="b0200-151">Assess impact on your organization</span></span>

<span data-ttu-id="b0200-152">Cada informe incluye gráficos diseñados para proporcionar información sobre el impacto organizativo de una amenaza:</span><span class="sxs-lookup"><span data-stu-id="b0200-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>

- <span data-ttu-id="b0200-153">**Incidentes relacionados:** proporciona información general sobre el impacto de la amenaza rastreada en su organización con los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="b0200-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="b0200-154">Número de alertas activas y el número de incidentes activos con los que están asociados</span><span class="sxs-lookup"><span data-stu-id="b0200-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="b0200-155">Gravedad de los incidentes activos</span><span class="sxs-lookup"><span data-stu-id="b0200-155">Severity of active incidents</span></span>
- <span data-ttu-id="b0200-156">**Alertas con el tiempo:** muestra el número de alertas **activas** **y** resueltas relacionadas con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="b0200-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="b0200-157">El número de alertas resueltas indica la rapidez con la que la organización responde a las alertas asociadas con una amenaza.</span><span class="sxs-lookup"><span data-stu-id="b0200-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="b0200-158">Lo ideal es que el gráfico muestre las alertas resueltas en unos días.</span><span class="sxs-lookup"><span data-stu-id="b0200-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="b0200-159">**Activos afectados:** muestra el número de dispositivos distintos y cuentas de correo electrónico (buzones) que actualmente tienen al menos una alerta activa asociada a la amenaza rastreada.</span><span class="sxs-lookup"><span data-stu-id="b0200-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="b0200-160">Las alertas se desencadenan para los buzones que recibieron mensajes de correo electrónico de amenazas.</span><span class="sxs-lookup"><span data-stu-id="b0200-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="b0200-161">Revise las directivas de nivel de organización y de usuario para obtener invalidaciones que causen la entrega de mensajes de correo electrónico de amenazas.</span><span class="sxs-lookup"><span data-stu-id="b0200-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="b0200-162">**Intentos de correo** electrónico impedidos: muestra el número de correos electrónicos de los últimos siete días que se bloquearon antes de la entrega o se entregaron a la carpeta de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b0200-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="b0200-163">Revisar la resistencia y la postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="b0200-163">Review security resilience and posture</span></span>

<span data-ttu-id="b0200-164">Cada informe incluye gráficos que proporcionan información general sobre la resistencia de la organización frente a una amenaza determinada:</span><span class="sxs-lookup"><span data-stu-id="b0200-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>

- <span data-ttu-id="b0200-165">**Estado de configuración segura:** muestra el número de dispositivos con configuraciones de seguridad mal configuradas.</span><span class="sxs-lookup"><span data-stu-id="b0200-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="b0200-166">Aplica la configuración de seguridad recomendada para ayudar a mitigar la amenaza.</span><span class="sxs-lookup"><span data-stu-id="b0200-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="b0200-167">Los dispositivos se consideran **seguros** si han aplicado _toda_ la configuración de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0200-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="b0200-168">**Estado de revisión de vulnerabilidad:** muestra el número de dispositivos vulnerables.</span><span class="sxs-lookup"><span data-stu-id="b0200-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="b0200-169">Aplicar actualizaciones de seguridad o revisiones para solucionar las vulnerabilidades aprovechadas por la amenaza.</span><span class="sxs-lookup"><span data-stu-id="b0200-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

#### <a name="view-reports-per-threat-tags"></a><span data-ttu-id="b0200-170">Ver informes por etiquetas de amenazas</span><span class="sxs-lookup"><span data-stu-id="b0200-170">View reports per threat tags</span></span>

<span data-ttu-id="b0200-171">Puede filtrar la lista de informes de amenazas y ver los informes más relevantes según una etiqueta de amenaza (categoría) específica o un tipo de informe.</span><span class="sxs-lookup"><span data-stu-id="b0200-171">You can filter the threat report list and view the most relevant reports according to a specific threat tag (category) or a report type.</span></span>

- <span data-ttu-id="b0200-172">**Etiquetas de** amenazas: le ayudarán a ver los informes más relevantes según una categoría de amenaza específica.</span><span class="sxs-lookup"><span data-stu-id="b0200-172">**Threat tags**—assist you in viewing the most relevant reports according to a specific threat category.</span></span> <span data-ttu-id="b0200-173">Por ejemplo, todos los informes relacionados con ransomware.</span><span class="sxs-lookup"><span data-stu-id="b0200-173">For example, all reports related to ransomware.</span></span>
- <span data-ttu-id="b0200-174">**Tipos de informe:** le ayudarán a ver los informes más relevantes según un tipo de informe específico.</span><span class="sxs-lookup"><span data-stu-id="b0200-174">**Report types**—assist you in viewing the most relevant reports according to a specific report type.</span></span> <span data-ttu-id="b0200-175">Por ejemplo, todos los informes que cubren herramientas y técnicas.</span><span class="sxs-lookup"><span data-stu-id="b0200-175">For example, all reports that cover tools and techniques.</span></span> 
- <span data-ttu-id="b0200-176">**Filtros:** le ayudarán a revisar eficazmente la lista de informes de amenazas y filtrar la vista en función de un tipo de informe o etiqueta de amenaza específico.</span><span class="sxs-lookup"><span data-stu-id="b0200-176">**Filters**—assist you in efficiently reviewing the threat report list and filtering the view based on a specific threat tag or report type.</span></span> <span data-ttu-id="b0200-177">Por ejemplo, revise todos los informes de amenazas relacionados con la categoría ransomware o los informes de amenazas que cubren vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="b0200-177">For example, review all threat reports related to ransomware category, or threat reports that cover vulnerabilities.</span></span>

##### <a name="how-does-it-work"></a><span data-ttu-id="b0200-178">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="b0200-178">How does it work?</span></span>

<span data-ttu-id="b0200-179">El equipo de Inteligencia de amenazas de Microsoft ha agregado etiquetas de amenazas a cada informe de amenazas:</span><span class="sxs-lookup"><span data-stu-id="b0200-179">The Microsoft Threat Intelligence team has added threat tags to each threat report:</span></span>

- <span data-ttu-id="b0200-180">Ahora hay cuatro etiquetas de amenazas disponibles:</span><span class="sxs-lookup"><span data-stu-id="b0200-180">Four threat tags are now available:</span></span>
  - <span data-ttu-id="b0200-181">Ransomware</span><span class="sxs-lookup"><span data-stu-id="b0200-181">Ransomware</span></span>
  - <span data-ttu-id="b0200-182">Suplantación de identidad (phishing)</span><span class="sxs-lookup"><span data-stu-id="b0200-182">Phishing</span></span>
  - <span data-ttu-id="b0200-183">Vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="b0200-183">Vulnerability</span></span>
  - <span data-ttu-id="b0200-184">Grupo de actividades</span><span class="sxs-lookup"><span data-stu-id="b0200-184">Activity group</span></span>
- <span data-ttu-id="b0200-185">Las etiquetas de amenazas se presentan en la parte superior de la página análisis de amenazas, con contadores para el número de informes disponibles en cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b0200-185">Threat tags are presented at the top of the threat analytics page, with counters for the number of available reports under each tag.</span></span>

  ![etiquetas de amenazas](../../media/threat-analytics/ta-threattags-mtp.png)

- <span data-ttu-id="b0200-187">La lista también se puede ordenar por etiquetas de amenaza:</span><span class="sxs-lookup"><span data-stu-id="b0200-187">The list can also be sorted by threat tags:</span></span>

  ![lists](../../media/threat-analytics//ta-taglist-mtp.png)

- <span data-ttu-id="b0200-189">Los filtros están disponibles por etiqueta de amenaza y tipo de informe:</span><span class="sxs-lookup"><span data-stu-id="b0200-189">Filters are available per threat tag and report type:</span></span>

  ![filtros](../../media/threat-analytics/ta-threattag-filters-mtp.png)

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="b0200-191">Informe de analistas: obtener información de expertos de los investigadores de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0200-191">Analyst report: Get expert insight from Microsoft security researchers</span></span>

<span data-ttu-id="b0200-192">En la **sección Informe de** analistas, lea la escritura detallada del experto.</span><span class="sxs-lookup"><span data-stu-id="b0200-192">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="b0200-193">La mayoría de los informes proporcionan descripciones detalladas de las cadenas de ataque, incluidas las tácticas y técnicas [](advanced-hunting-overview.md) asignadas al marco de CK de MITRE ATT&, listas exhaustivas de recomendaciones y instrucciones de búsqueda de amenazas eficaces.</span><span class="sxs-lookup"><span data-stu-id="b0200-193">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="b0200-194">Más información sobre el informe de analistas</span><span class="sxs-lookup"><span data-stu-id="b0200-194">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="b0200-195">Incidentes relacionados: ver y administrar incidentes relacionados</span><span class="sxs-lookup"><span data-stu-id="b0200-195">Related incidents: View and manage related incidents</span></span>

<span data-ttu-id="b0200-196">La **pestaña Incidentes relacionados** proporciona la lista de todos los incidentes relacionados con la amenaza rastreada.</span><span class="sxs-lookup"><span data-stu-id="b0200-196">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="b0200-197">Puede asignar incidentes o administrar alertas vinculadas a cada incidente.</span><span class="sxs-lookup"><span data-stu-id="b0200-197">You can assign incidents or manage alerts linked to each incident.</span></span> 


![Imagen de la sección incidentes relacionados de un informe de análisis de amenazas](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="b0200-199">_Sección incidentes relacionados de un informe de análisis de amenazas_</span><span class="sxs-lookup"><span data-stu-id="b0200-199">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="b0200-200">Activos afectados: obtener una lista de dispositivos y buzones afectados</span><span class="sxs-lookup"><span data-stu-id="b0200-200">Impacted assets: Get list of impacted devices and mailboxes</span></span>

<span data-ttu-id="b0200-201">Un activo se considera afectado si se ve afectado por una alerta activa y sin resolver.</span><span class="sxs-lookup"><span data-stu-id="b0200-201">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="b0200-202">La **pestaña Activos afectados** enumera los siguientes tipos de activos afectados:</span><span class="sxs-lookup"><span data-stu-id="b0200-202">The **Impacted assets** tab lists the following types of impacted assets:</span></span>

- <span data-ttu-id="b0200-203">**Dispositivos afectados:** puntos de conexión que tienen alertas de Microsoft Defender para puntos de conexión sin resolver.</span><span class="sxs-lookup"><span data-stu-id="b0200-203">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="b0200-204">Estas alertas suelen dispararse en avistamientos de indicadores y actividades de amenazas conocidos.</span><span class="sxs-lookup"><span data-stu-id="b0200-204">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="b0200-205">**Buzones afectados:** buzones que han recibido mensajes de correo electrónico que han desencadenado Microsoft Defender para Office 365 alertas.</span><span class="sxs-lookup"><span data-stu-id="b0200-205">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="b0200-206">Aunque la mayoría de los mensajes que desencadenan alertas suelen estar bloqueados, las directivas de nivel de usuario o de organización pueden invalidar los filtros.</span><span class="sxs-lookup"><span data-stu-id="b0200-206">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![Imagen de la sección activos afectados de un informe de análisis de amenazas](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="b0200-208">_Sección activos afectados de un informe de análisis de amenazas_</span><span class="sxs-lookup"><span data-stu-id="b0200-208">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="b0200-209">Intentos de correo electrónico impedidos: ver mensajes de correo electrónico bloqueados o de amenazas no deseados</span><span class="sxs-lookup"><span data-stu-id="b0200-209">Prevented email attempts: View blocked or junked threat emails</span></span>

<span data-ttu-id="b0200-210">Microsoft Defender para Office 365 normalmente bloquea los correos electrónicos con indicadores de amenazas conocidos, incluidos vínculos malintencionados o datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="b0200-210">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="b0200-211">En algunos casos, los mecanismos de filtrado proactivo que comprueban el contenido sospechoso enviarán correos electrónicos de amenazas a la carpeta de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b0200-211">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="b0200-212">En cualquier caso, se reducen las posibilidades de que la amenaza inicie código de malware en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b0200-212">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="b0200-213">La **pestaña Intentos** de correo electrónico impedido enumera todos los correos electrónicos que Microsoft Defender ha bloqueado antes de la entrega o que Microsoft Defender ha enviado a la carpeta de correo no deseado Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0200-213">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![Imagen de la sección intentos de correo electrónico impedidos de un informe de análisis de amenazas](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="b0200-215">_Sección Intentos de correo electrónico impedidos de un informe de análisis de amenazas_</span><span class="sxs-lookup"><span data-stu-id="b0200-215">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="b0200-216">Mitigaciones: revisar la lista de mitigaciones y el estado de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="b0200-216">Mitigations: Review list of mitigations and the status of your devices</span></span>

<span data-ttu-id="b0200-217">En la **sección Mitigaciones,** revise la lista de recomendaciones específicas que se pueden usar y que pueden ayudarle a aumentar la resistencia de la organización frente a la amenaza.</span><span class="sxs-lookup"><span data-stu-id="b0200-217">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="b0200-218">La lista de mitigaciones rastreadas incluye:</span><span class="sxs-lookup"><span data-stu-id="b0200-218">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="b0200-219">**Actualizaciones de seguridad:** implementación de actualizaciones de seguridad de software compatibles para vulnerabilidades encontradas en dispositivos incorporados</span><span class="sxs-lookup"><span data-stu-id="b0200-219">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="b0200-220">**Configuraciones de seguridad admitidas**</span><span class="sxs-lookup"><span data-stu-id="b0200-220">**Supported security configurations**</span></span>
  - <span data-ttu-id="b0200-221">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="b0200-221">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="b0200-222">Protección de aplicaciones potencialmente no deseadas (PUA)</span><span class="sxs-lookup"><span data-stu-id="b0200-222">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="b0200-223">Protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="b0200-223">Real-time protection</span></span>

<span data-ttu-id="b0200-224">La información de mitigación de esta sección incorpora datos de [Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), que también proporciona información detallada de detalles de varios vínculos del informe.</span><span class="sxs-lookup"><span data-stu-id="b0200-224">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

![Imagen de la sección mitigaciones de un informe de análisis de amenazas que muestra detalles de configuración segura](../../media/threat-analytics/ta_mitigations_mtp.png)

![Imagen de la sección mitigaciones de un informe de análisis de amenazas que muestra detalles de vulnerabilidad](../../media/threat-analytics/ta_mitigations_mtp2.png)

<span data-ttu-id="b0200-227">_Sección Mitigaciones de un informe de análisis de amenazas_</span><span class="sxs-lookup"><span data-stu-id="b0200-227">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="b0200-228">Detalles y limitaciones adicionales del informe</span><span class="sxs-lookup"><span data-stu-id="b0200-228">Additional report details and limitations</span></span>

> [!NOTE]
> <span data-ttu-id="b0200-229">Como parte de la experiencia de seguridad unificada, el análisis de amenazas ahora está disponible no solo para Microsoft Defender para Endpoint, sino también para Microsoft Defender para los Office licencias de E5.</span><span class="sxs-lookup"><span data-stu-id="b0200-229">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
>
> <span data-ttu-id="b0200-230">Si no usa el portal de seguridad de Microsoft 365 (Microsoft 365 Defender), también puede ver los detalles del informe (sin Microsoft Defender para datos Office) en el portal de Centro de seguridad de Microsoft Defender (Microsoft Defender para endpoint).</span><span class="sxs-lookup"><span data-stu-id="b0200-230">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span>

<span data-ttu-id="b0200-231">Para obtener acceso al informe de análisis de amenazas, necesita ciertos roles y permisos.</span><span class="sxs-lookup"><span data-stu-id="b0200-231">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="b0200-232">Vea [Roles personalizados en el control de](custom-roles.md) acceso basado en roles para obtener Microsoft 365 Defender detalles.</span><span class="sxs-lookup"><span data-stu-id="b0200-232">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>

- <span data-ttu-id="b0200-233">Para ver alertas, incidentes o datos de activos afectados, debe tener permisos para Microsoft Defender para los datos de alertas de Office o Microsoft Defender para puntos de conexión, o ambos.</span><span class="sxs-lookup"><span data-stu-id="b0200-233">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
- <span data-ttu-id="b0200-234">Para ver los intentos de correo electrónico impedidos, debe tener permisos para Microsoft Defender para obtener Office de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b0200-234">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
- <span data-ttu-id="b0200-235">Para ver las mitigaciones, debe tener permisos para Administración de amenazas y vulnerabilidades datos en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="b0200-235">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="b0200-236">Al ver los datos de análisis de amenazas, recuerde los siguientes factores:</span><span class="sxs-lookup"><span data-stu-id="b0200-236">When looking at the threat analytics data, remember the following factors:</span></span>

- <span data-ttu-id="b0200-237">Los gráficos reflejan solo las mitigaciones a las que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0200-237">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="b0200-238">Compruebe en el informe información general para ver mitigaciones adicionales que no se muestran en los gráficos.</span><span class="sxs-lookup"><span data-stu-id="b0200-238">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="b0200-239">Las mitigaciones no garantizan una resistencia completa.</span><span class="sxs-lookup"><span data-stu-id="b0200-239">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="b0200-240">Las mitigaciones proporcionadas reflejan las mejores acciones posibles necesarias para mejorar la resistencia.</span><span class="sxs-lookup"><span data-stu-id="b0200-240">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="b0200-241">Los dispositivos se cuentan como "no disponibles" si no han transmitido datos al servicio.</span><span class="sxs-lookup"><span data-stu-id="b0200-241">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="b0200-242">Las estadísticas relacionadas con el antivirus se basan en Antivirus de Microsoft Defender configuración.</span><span class="sxs-lookup"><span data-stu-id="b0200-242">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="b0200-243">Los dispositivos con soluciones antivirus de terceros pueden aparecer como "expuestos".</span><span class="sxs-lookup"><span data-stu-id="b0200-243">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0200-244">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b0200-244">Related topics</span></span>

- [<span data-ttu-id="b0200-245">Búsqueda proactiva de amenazas con búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="b0200-245">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="b0200-246">Comprender la sección de informe de analistas</span><span class="sxs-lookup"><span data-stu-id="b0200-246">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="b0200-247">Evaluar y resolver debilidades y exposiciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="b0200-247">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
