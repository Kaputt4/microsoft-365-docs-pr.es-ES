---
title: Priorizar incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 Defender
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes, análisis, respuesta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1240fbb8fb24b7231733db25e9a1859b2a84fd41
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022752"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="d7f14-104">Priorizar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7f14-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d7f14-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d7f14-105">**Applies to:**</span></span>
- <span data-ttu-id="d7f14-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7f14-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d7f14-107">Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente.</span><span class="sxs-lookup"><span data-stu-id="d7f14-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="d7f14-108">Microsoft 365 Defender activa alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de un extremo a otro que Microsoft 365 Defender en todo el conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="d7f14-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="d7f14-109">Esta vista ofrece a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="d7f14-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="d7f14-110">La **cola Incidentes muestra** una colección de incidentes que se crearon en dispositivos, usuarios y buzones.</span><span class="sxs-lookup"><span data-stu-id="d7f14-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="d7f14-111">Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.</span><span class="sxs-lookup"><span data-stu-id="d7f14-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="d7f14-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="d7f14-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="d7f14-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7f14-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

<span data-ttu-id="d7f14-115">La **sección Incidentes y alertas** más recientes muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="d7f14-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="d7f14-116">De forma predeterminada, la cola de incidentes del portal de Microsoft 365 Defender muestra los incidentes vistos en los últimos seis meses.</span><span class="sxs-lookup"><span data-stu-id="d7f14-116">By default, the incident queue in the Microsoft 365 Defender portal displays incidents seen in the last six months.</span></span> <span data-ttu-id="d7f14-117">El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.</span><span class="sxs-lookup"><span data-stu-id="d7f14-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="d7f14-118">La cola de incidentes tiene columnas personalizables (seleccione **Elegir** columnas) que le dan visibilidad de distintas características del incidente o de las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="d7f14-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="d7f14-119">Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.</span><span class="sxs-lookup"><span data-stu-id="d7f14-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="d7f14-120">Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="d7f14-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="d7f14-121">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="d7f14-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="d7f14-122">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="d7f14-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="d7f14-123">Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="d7f14-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="d7f14-124">La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos.</span><span class="sxs-lookup"><span data-stu-id="d7f14-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="d7f14-125">Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="d7f14-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="d7f14-126">Filtros disponibles</span><span class="sxs-lookup"><span data-stu-id="d7f14-126">Available filters</span></span>

<span data-ttu-id="d7f14-127">En la cola de incidentes  predeterminada, puede seleccionar Filtros para ver un panel Filtros, desde el que puede ver un conjunto filtrado de incidentes.</span><span class="sxs-lookup"><span data-stu-id="d7f14-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="d7f14-128">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d7f14-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes":::

<span data-ttu-id="d7f14-130">En esta tabla se enumeran los nombres de filtro disponibles.</span><span class="sxs-lookup"><span data-stu-id="d7f14-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="d7f14-131">Nombre del filtro</span><span class="sxs-lookup"><span data-stu-id="d7f14-131">Filter name</span></span> | <span data-ttu-id="d7f14-132">Description</span><span class="sxs-lookup"><span data-stu-id="d7f14-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="d7f14-133">Asignado a</span><span class="sxs-lookup"><span data-stu-id="d7f14-133">Assigned to</span></span> | <span data-ttu-id="d7f14-134">Puede elegir mostrar las alertas que se le han asignado o las que controla la automatización.</span><span class="sxs-lookup"><span data-stu-id="d7f14-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="d7f14-135">Categorías</span><span class="sxs-lookup"><span data-stu-id="d7f14-135">Categories</span></span> | <span data-ttu-id="d7f14-136">Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="d7f14-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="d7f14-137">Clasificación</span><span class="sxs-lookup"><span data-stu-id="d7f14-137">Classification</span></span> | <span data-ttu-id="d7f14-138">Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d7f14-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="d7f14-139">Los valores incluyen alertas verdaderas, alertas falsas o no establecidas.</span><span class="sxs-lookup"><span data-stu-id="d7f14-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="d7f14-140">Confidencialidad de datos</span><span class="sxs-lookup"><span data-stu-id="d7f14-140">Data sensitivity</span></span> | <span data-ttu-id="d7f14-141">Algunos ataques tienen por objetivo extraer datos confidenciales o importantes.</span><span class="sxs-lookup"><span data-stu-id="d7f14-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="d7f14-142">Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.</span><span class="sxs-lookup"><span data-stu-id="d7f14-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="d7f14-143">Solo se aplica si se ha activado Microsoft Information Protection. </span><span class="sxs-lookup"><span data-stu-id="d7f14-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="d7f14-144">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d7f14-144">Device group</span></span> | <span data-ttu-id="d7f14-145">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="d7f14-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="d7f14-146">Estado de investigación</span><span class="sxs-lookup"><span data-stu-id="d7f14-146">Investigation state</span></span> | <span data-ttu-id="d7f14-147">Filtrar incidentes por el estado de la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="d7f14-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="d7f14-148">Varias categorías</span><span class="sxs-lookup"><span data-stu-id="d7f14-148">Multiple categories</span></span> | <span data-ttu-id="d7f14-149">Puede elegir ver solo incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daños.</span><span class="sxs-lookup"><span data-stu-id="d7f14-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="d7f14-150">Múltiples orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="d7f14-150">Multiple service sources</span></span>  | <span data-ttu-id="d7f14-151">Filtra para ver solo incidentes que contienen alertas de diferentes orígenes (Microsoft Defender para endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="d7f14-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="d7f14-152">Plataforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d7f14-152">OS platform</span></span> | <span data-ttu-id="d7f14-153">Limitar la vista de cola de incidentes por sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d7f14-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="d7f14-154">Orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="d7f14-154">Service sources</span></span> | <span data-ttu-id="d7f14-155">Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d7f14-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="d7f14-156">Gravedad</span><span class="sxs-lookup"><span data-stu-id="d7f14-156">Severity</span></span> | <span data-ttu-id="d7f14-157">La gravedad de un incidente indica el impacto que puede tener en los activos.</span><span class="sxs-lookup"><span data-stu-id="d7f14-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="d7f14-158">Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="d7f14-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="d7f14-159">Estado</span><span class="sxs-lookup"><span data-stu-id="d7f14-159">Status</span></span> | <span data-ttu-id="d7f14-160">Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.</span><span class="sxs-lookup"><span data-stu-id="d7f14-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="save-defined-filters-as-urls"></a><span data-ttu-id="d7f14-161">Guardar filtros definidos como direcciones URL</span><span class="sxs-lookup"><span data-stu-id="d7f14-161">Save defined filters as URLs</span></span>

<span data-ttu-id="d7f14-162">Una vez que haya configurado un filtro útil en la cola de incidentes, puede marcar la dirección URL de la pestaña del explorador o guardarla como un vínculo en una página web, un documento de Word o un lugar de su elección.</span><span class="sxs-lookup"><span data-stu-id="d7f14-162">Once you have configured a useful filter in the incidents queue, you can bookmark the URL of the browser tab or otherwise save it as a link on a Web page, a Word document, or a place of your choice.</span></span> <span data-ttu-id="d7f14-163">Esto le dará acceso con un solo clic a las vistas clave de la cola de incidentes, como:</span><span class="sxs-lookup"><span data-stu-id="d7f14-163">This will give you single-click access to key views of the incident queue, such as:</span></span>

- <span data-ttu-id="d7f14-164">Nuevos incidentes</span><span class="sxs-lookup"><span data-stu-id="d7f14-164">New incidents</span></span>
- <span data-ttu-id="d7f14-165">Incidentes de alta gravedad</span><span class="sxs-lookup"><span data-stu-id="d7f14-165">High-severity incidents</span></span>
- <span data-ttu-id="d7f14-166">Incidentes sin firma</span><span class="sxs-lookup"><span data-stu-id="d7f14-166">Unassigned incidents</span></span>
- <span data-ttu-id="d7f14-167">Incidentes de gravedad alta y sin firma</span><span class="sxs-lookup"><span data-stu-id="d7f14-167">High-severity, unassigned incidents</span></span>
- <span data-ttu-id="d7f14-168">Incidentes asignados a mí</span><span class="sxs-lookup"><span data-stu-id="d7f14-168">Incidents assigned to me</span></span>
- <span data-ttu-id="d7f14-169">Incidentes asignados a mí y a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="d7f14-169">Incidents assigned to me and for Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="d7f14-170">Incidentes con una etiqueta o etiquetas específicas</span><span class="sxs-lookup"><span data-stu-id="d7f14-170">Incidents with a specific tag or tags</span></span>
- <span data-ttu-id="d7f14-171">Incidentes con una categoría de amenaza específica</span><span class="sxs-lookup"><span data-stu-id="d7f14-171">Incidents with a specific threat category</span></span>
- <span data-ttu-id="d7f14-172">Incidentes con una amenaza asociada específica</span><span class="sxs-lookup"><span data-stu-id="d7f14-172">Incidents with a specific associated threat</span></span>
- <span data-ttu-id="d7f14-173">Incidentes con un actor específico</span><span class="sxs-lookup"><span data-stu-id="d7f14-173">Incidents with a specific actor</span></span>

<span data-ttu-id="d7f14-174">Una vez que haya compilado y almacenado la lista de vistas de filtro útiles como direcciones [](manage-incidents.md) URL, puede usarla rápidamente para procesar y priorizar los incidentes de la cola y administrarlos para su análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="d7f14-174">Once you have compiled and stored your list of useful filter views as URLs, you can use it quickly process and prioritize the incidents in your queue and [manage](manage-incidents.md) them for subsequent analysis.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7f14-175">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d7f14-175">Next steps</span></span>

<span data-ttu-id="d7f14-176">Después de determinar qué incidente requiere la prioridad más alta, selecciónelo y:</span><span class="sxs-lookup"><span data-stu-id="d7f14-176">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="d7f14-177">[Administrar](manage-incidents.md) las propiedades del incidente para etiquetas, asignación, resolución inmediata de incidentes falsos positivos y comentarios.</span><span class="sxs-lookup"><span data-stu-id="d7f14-177">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="d7f14-178">Comience las [investigaciones](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="d7f14-178">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7f14-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7f14-179">See also</span></span>
- [<span data-ttu-id="d7f14-180">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="d7f14-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d7f14-181">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="d7f14-181">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="d7f14-182">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="d7f14-182">Investigate incidents</span></span>](investigate-incidents.md)
