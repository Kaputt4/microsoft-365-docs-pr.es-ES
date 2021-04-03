---
title: Escala de tiempo de eventos en la administración de amenazas y vulnerabilidades
description: La escala de tiempo de eventos es una fuente de noticias de riesgo que le ayuda a interpretar cómo se introduce el riesgo en la organización y qué mitigaciones se han producido para reducirlo.
keywords: escala de tiempo de eventos, escala de tiempo de eventos mdatp, escala de tiempo de eventos mdatp tvm, administración de amenazas y vulnerabilidades, Microsoft Defender para endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 90a124f9b0bf9ef775141e359224fde566c61c8d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501207"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="6c121-104">Escala de tiempo de eventos: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6c121-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c121-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6c121-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c121-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6c121-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6c121-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c121-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6c121-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="6c121-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c121-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c121-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="6c121-110">La escala de tiempo del evento es una fuente de noticias de riesgo que le ayuda a interpretar cómo se introduce el riesgo en la organización a través de nuevas vulnerabilidades o vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="6c121-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="6c121-111">Puede ver eventos que pueden afectar al riesgo de su organización.</span><span class="sxs-lookup"><span data-stu-id="6c121-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="6c121-112">Por ejemplo, puede encontrar nuevas vulnerabilidades que se introdujeron, vulnerabilidades que se convirtieron en explotables, vulnerabilidades que se agregaron a un kit de vulnerabilidades y mucho más.</span><span class="sxs-lookup"><span data-stu-id="6c121-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="6c121-113">La escala de tiempo [](tvm-exposure-score.md) del evento también cuenta la historia de la puntuación de exposición y la puntuación segura de [Microsoft](tvm-microsoft-secure-score-devices.md) para dispositivos para que puedas determinar la causa de grandes cambios.</span><span class="sxs-lookup"><span data-stu-id="6c121-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="6c121-114">Los eventos pueden afectar a los dispositivos o a la puntuación de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6c121-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="6c121-115">Reduzca la exposición abordando lo que debe corregirse en función de las recomendaciones de [seguridad prioritarias.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="6c121-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="6c121-116">Para obtener correos electrónicos sobre nuevos eventos de vulnerabilidad, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="6c121-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="6c121-117">Vaya a la página Escala de tiempo de eventos</span><span class="sxs-lookup"><span data-stu-id="6c121-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="6c121-118">También hay tres puntos de entrada del panel de administración de amenazas [y vulnerabilidades:](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="6c121-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="6c121-119">**Tarjeta de puntuación de** exposición de la organización: mantenga el mouse sobre los puntos del evento en el gráfico "Puntuación de exposición con el tiempo" y seleccione "Ver todos los eventos de este día".</span><span class="sxs-lookup"><span data-stu-id="6c121-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="6c121-120">Los eventos representan vulnerabilidades de software.</span><span class="sxs-lookup"><span data-stu-id="6c121-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="6c121-121">**Puntuación segura de Microsoft** para dispositivos: mantenga el mouse sobre los puntos de evento en el gráfico "Su puntuación para dispositivos con el tiempo" y seleccione "Ver todos los eventos de este día".</span><span class="sxs-lookup"><span data-stu-id="6c121-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="6c121-122">Los eventos representan nuevas evaluaciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="6c121-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="6c121-123">**Tarjeta de eventos superior:** seleccione "Mostrar más" en la parte inferior de la tabla de eventos superior.</span><span class="sxs-lookup"><span data-stu-id="6c121-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="6c121-124">La tarjeta muestra los tres eventos más impactantes de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="6c121-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="6c121-125">Los eventos de impacto pueden incluir si el evento afecta a un gran número de dispositivos o si es una vulnerabilidad crítica.</span><span class="sxs-lookup"><span data-stu-id="6c121-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="6c121-126">Puntuación de exposición y puntuación segura de Microsoft para gráficos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="6c121-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="6c121-127">En el panel de administración de amenazas y vulnerabilidades, mantenga el mouse sobre el gráfico puntuación de exposición para ver los eventos de vulnerabilidad de software principales de ese día que afectaron a sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6c121-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="6c121-128">Mantenga el mouse sobre el gráfico Puntuación segura de Microsoft para dispositivos para ver las nuevas evaluaciones de configuración de seguridad que afectan a su puntuación.</span><span class="sxs-lookup"><span data-stu-id="6c121-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="6c121-129">Si no hay eventos que afecten a los dispositivos o a la puntuación de los dispositivos, no se mostrará ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c121-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="6c121-130">![Puntuación de exposición activa ](images/tvm-event-timeline-exposure-score350.png) 
 ![ el puntero puntuación segura de Microsoft para dispositivos](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="6c121-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="6c121-131">Profundizar en los eventos de ese día</span><span class="sxs-lookup"><span data-stu-id="6c121-131">Drill down to events from that day</span></span>

<span data-ttu-id="6c121-132">Si selecciona Mostrar todos los eventos de este **día,** podrá ir a la página Escala de tiempo de eventos con un intervalo de fechas personalizado para ese día.</span><span class="sxs-lookup"><span data-stu-id="6c121-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![Intervalo de fechas personalizado seleccionado de escala de tiempo de eventos](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="6c121-134">Seleccione **Intervalo personalizado** para cambiar el intervalo de fechas a otro personalizado o a un intervalo de tiempo predefinido.</span><span class="sxs-lookup"><span data-stu-id="6c121-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![Opciones del intervalo de fechas de escala de tiempo de eventos](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="6c121-136">Introducción a la escala de tiempo de eventos</span><span class="sxs-lookup"><span data-stu-id="6c121-136">Event timeline overview</span></span>

<span data-ttu-id="6c121-137">En la página Escala de tiempo del evento, puedes ver toda la información necesaria relacionada con un evento.</span><span class="sxs-lookup"><span data-stu-id="6c121-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="6c121-138">Características:</span><span class="sxs-lookup"><span data-stu-id="6c121-138">Features:</span></span>

- <span data-ttu-id="6c121-139">Personalizar columnas</span><span class="sxs-lookup"><span data-stu-id="6c121-139">Customize columns</span></span>
- <span data-ttu-id="6c121-140">Filtrar por tipo de evento o porcentaje de dispositivos afectados</span><span class="sxs-lookup"><span data-stu-id="6c121-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="6c121-141">Ver 30, 50 o 100 elementos por página</span><span class="sxs-lookup"><span data-stu-id="6c121-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="6c121-142">Los dos números grandes en la parte superior de la página muestran el número de nuevas vulnerabilidades y vulnerabilidades aprovechables, no eventos.</span><span class="sxs-lookup"><span data-stu-id="6c121-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="6c121-143">Algunos eventos pueden tener varias vulnerabilidades y algunas vulnerabilidades pueden tener varios eventos.</span><span class="sxs-lookup"><span data-stu-id="6c121-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![Página escala de tiempo de eventos](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="6c121-145">Columnas</span><span class="sxs-lookup"><span data-stu-id="6c121-145">Columns</span></span>

- <span data-ttu-id="6c121-146">**Fecha:** mes, día, año</span><span class="sxs-lookup"><span data-stu-id="6c121-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="6c121-147">**Evento:** evento de impacto, incluido el componente, el tipo y el número de dispositivos afectados</span><span class="sxs-lookup"><span data-stu-id="6c121-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="6c121-148">**Componente relacionado**: software</span><span class="sxs-lookup"><span data-stu-id="6c121-148">**Related component**: software</span></span>
- <span data-ttu-id="6c121-149">**Dispositivos afectados originalmente:** el número y el porcentaje de dispositivos afectados cuando se produjo este evento originalmente.</span><span class="sxs-lookup"><span data-stu-id="6c121-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="6c121-150">También puedes filtrar por el porcentaje de dispositivos afectados originalmente, de tu número total de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6c121-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="6c121-151">**Dispositivos afectados actualmente:** el número actual y el porcentaje de dispositivos que este evento afecta actualmente.</span><span class="sxs-lookup"><span data-stu-id="6c121-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="6c121-152">Puede encontrar este campo seleccionando **Personalizar columnas**.</span><span class="sxs-lookup"><span data-stu-id="6c121-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="6c121-153">**Tipos:** reflejan eventos con marca de tiempo que afectan a la puntuación.</span><span class="sxs-lookup"><span data-stu-id="6c121-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="6c121-154">Se pueden filtrar.</span><span class="sxs-lookup"><span data-stu-id="6c121-154">They can be filtered.</span></span>
    - <span data-ttu-id="6c121-155">Exploit agregado a un kit de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6c121-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="6c121-156">Se ha comprobado la vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="6c121-156">Exploit was verified</span></span>
    - <span data-ttu-id="6c121-157">Nueva vulnerabilidad pública</span><span class="sxs-lookup"><span data-stu-id="6c121-157">New public exploit</span></span>
    - <span data-ttu-id="6c121-158">Nueva vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="6c121-158">New vulnerability</span></span>
    - <span data-ttu-id="6c121-159">Nueva evaluación de configuración</span><span class="sxs-lookup"><span data-stu-id="6c121-159">New configuration assessment</span></span>
- <span data-ttu-id="6c121-160">**Tendencia de puntuación:** tendencia de puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="6c121-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="6c121-161">Iconos</span><span class="sxs-lookup"><span data-stu-id="6c121-161">Icons</span></span>

<span data-ttu-id="6c121-162">Los siguientes iconos se muestran junto a los eventos:</span><span class="sxs-lookup"><span data-stu-id="6c121-162">The following icons show up next to events:</span></span>

- ![icono de error](images/tvm-black-bug-icon.png) <span data-ttu-id="6c121-164">Nueva vulnerabilidad pública</span><span class="sxs-lookup"><span data-stu-id="6c121-164">New public exploit</span></span>
- ![icono de advertencia de informe](images/report-warning-icon.png) <span data-ttu-id="6c121-166">Se publicó una nueva vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="6c121-166">New vulnerability was published</span></span>
- ![exploit kit](images/bug-lightning-icon2.png) <span data-ttu-id="6c121-168">Exploit encontrado en el kit de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6c121-168">Exploit found in exploit kit</span></span>
- ![icono de error con icono de advertencia](images/bug-caution-icon2.png) <span data-ttu-id="6c121-170">Exploit verified</span><span class="sxs-lookup"><span data-stu-id="6c121-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="6c121-171">Profundizar en un evento específico</span><span class="sxs-lookup"><span data-stu-id="6c121-171">Drill down to a specific event</span></span>

<span data-ttu-id="6c121-172">Una vez que selecciones un evento, aparecerá un flyout con una lista de los detalles y las CVEs actuales que afectan a tus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6c121-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="6c121-173">Puede mostrar más CVEs o ver la recomendación relacionada.</span><span class="sxs-lookup"><span data-stu-id="6c121-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="6c121-174">La flecha debajo de "tendencia de puntuación" te ayuda a determinar si este evento potencialmente ha elevado o reducido la puntuación de exposición de la organización.</span><span class="sxs-lookup"><span data-stu-id="6c121-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="6c121-175">Una mayor puntuación de exposición significa que los dispositivos son más vulnerables a la explotación.</span><span class="sxs-lookup"><span data-stu-id="6c121-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![Control desplegable de escala de tiempo de eventos](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="6c121-177">Desde allí, seleccione **Ir a la vista de** recomendación de seguridad relacionada la recomendación que aborda la nueva vulnerabilidad de software en la página recomendaciones de [seguridad](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="6c121-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="6c121-178">Después de leer la descripción y los detalles de vulnerabilidad en la recomendación de seguridad, puede enviar una solicitud de corrección y realizar un seguimiento de la solicitud en la [página de corrección](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="6c121-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="6c121-179">Ver escalas de tiempo de eventos en páginas de software</span><span class="sxs-lookup"><span data-stu-id="6c121-179">View Event timelines in software pages</span></span>

<span data-ttu-id="6c121-180">Para abrir una página de software, seleccione un evento > el nombre de software con hipervínculo (como Visual Studio 2017) en la sección denominada "Componente relacionado" en el control desplegable.</span><span class="sxs-lookup"><span data-stu-id="6c121-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="6c121-181">Más información sobre las páginas de software</span><span class="sxs-lookup"><span data-stu-id="6c121-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="6c121-182">Aparecerá una página completa con todos los detalles de un software específico.</span><span class="sxs-lookup"><span data-stu-id="6c121-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="6c121-183">Pase el mouse sobre el gráfico para ver la escala de tiempo de los eventos de ese software específico.</span><span class="sxs-lookup"><span data-stu-id="6c121-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![Página de software con un gráfico de escala de tiempo de eventos](images/tvm-event-timeline-software2.png)

<span data-ttu-id="6c121-185">Vaya a la pestaña escala de tiempo del evento para ver todos los eventos relacionados con ese software.</span><span class="sxs-lookup"><span data-stu-id="6c121-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="6c121-186">También puede ver recomendaciones de seguridad, vulnerabilidades detectadas, dispositivos instalados y distribución de versiones.</span><span class="sxs-lookup"><span data-stu-id="6c121-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![Página de software con una pestaña Escala de tiempo de eventos](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="6c121-188">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6c121-188">Related topics</span></span>

- [<span data-ttu-id="6c121-189">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6c121-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6c121-190">Panel</span><span class="sxs-lookup"><span data-stu-id="6c121-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="6c121-191">Puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="6c121-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="6c121-192">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="6c121-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="6c121-193">Corregir puntos vulnerables</span><span class="sxs-lookup"><span data-stu-id="6c121-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="6c121-194">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="6c121-194">Software inventory</span></span>](tvm-software-inventory.md)

