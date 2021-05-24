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
ms.openlocfilehash: df2d2660267c38dccf5ef09fa4955615d3a78141
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636271"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5da4b-104">Priorizar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5da4b-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5da4b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5da4b-105">**Applies to:**</span></span>
- <span data-ttu-id="5da4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5da4b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5da4b-107">Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente.</span><span class="sxs-lookup"><span data-stu-id="5da4b-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="5da4b-108">Microsoft 365 Defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de un extremo a otro que Microsoft 365 Defender tiene en todo el conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="5da4b-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="5da4b-109">Esta vista ofrece a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="5da4b-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="5da4b-110">La **cola Incidentes muestra** una colección de incidentes que se crearon en dispositivos, usuarios y buzones.</span><span class="sxs-lookup"><span data-stu-id="5da4b-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="5da4b-111">Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.</span><span class="sxs-lookup"><span data-stu-id="5da4b-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="5da4b-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="5da4b-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="5da4b-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5da4b-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

<span data-ttu-id="5da4b-115">La **sección Incidentes y alertas** más recientes muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="5da4b-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="5da4b-116">De forma predeterminada, la cola de incidentes del centro Microsoft 365 de seguridad muestra incidentes vistos en los últimos seis meses.</span><span class="sxs-lookup"><span data-stu-id="5da4b-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="5da4b-117">El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.</span><span class="sxs-lookup"><span data-stu-id="5da4b-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="5da4b-118">La cola de incidentes tiene columnas personalizables (seleccione **Elegir** columnas) que le dan visibilidad de distintas características del incidente o de las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="5da4b-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="5da4b-119">Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.</span><span class="sxs-lookup"><span data-stu-id="5da4b-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="5da4b-120">Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="5da4b-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="5da4b-121">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="5da4b-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="5da4b-122">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="5da4b-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="5da4b-123">Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="5da4b-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="5da4b-124">La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos.</span><span class="sxs-lookup"><span data-stu-id="5da4b-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="5da4b-125">Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="5da4b-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="5da4b-126">Filtros disponibles</span><span class="sxs-lookup"><span data-stu-id="5da4b-126">Available filters</span></span>

<span data-ttu-id="5da4b-127">En la cola de incidentes  predeterminada, puede seleccionar Filtros para ver un panel Filtros, desde el que puede ver un conjunto filtrado de incidentes.</span><span class="sxs-lookup"><span data-stu-id="5da4b-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="5da4b-128">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5da4b-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes":::

<span data-ttu-id="5da4b-130">En esta tabla se enumeran los nombres de filtro disponibles.</span><span class="sxs-lookup"><span data-stu-id="5da4b-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="5da4b-131">Nombre del filtro</span><span class="sxs-lookup"><span data-stu-id="5da4b-131">Filter name</span></span> | <span data-ttu-id="5da4b-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="5da4b-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="5da4b-133">Asignado a</span><span class="sxs-lookup"><span data-stu-id="5da4b-133">Assigned to</span></span> | <span data-ttu-id="5da4b-134">Puede elegir mostrar las alertas que se le han asignado o las que controla la automatización.</span><span class="sxs-lookup"><span data-stu-id="5da4b-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="5da4b-135">Categorías</span><span class="sxs-lookup"><span data-stu-id="5da4b-135">Categories</span></span> | <span data-ttu-id="5da4b-136">Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="5da4b-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="5da4b-137">Clasificación</span><span class="sxs-lookup"><span data-stu-id="5da4b-137">Classification</span></span> | <span data-ttu-id="5da4b-138">Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5da4b-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="5da4b-139">Los valores incluyen alertas verdaderas, alertas falsas o no establecidas.</span><span class="sxs-lookup"><span data-stu-id="5da4b-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="5da4b-140">Confidencialidad de datos</span><span class="sxs-lookup"><span data-stu-id="5da4b-140">Data sensitivity</span></span> | <span data-ttu-id="5da4b-141">Algunos ataques tienen por objetivo extraer datos confidenciales o importantes.</span><span class="sxs-lookup"><span data-stu-id="5da4b-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="5da4b-142">Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.</span><span class="sxs-lookup"><span data-stu-id="5da4b-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="5da4b-143">Solo se aplica si se ha activado Microsoft Information Protection. </span><span class="sxs-lookup"><span data-stu-id="5da4b-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="5da4b-144">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="5da4b-144">Device group</span></span> | <span data-ttu-id="5da4b-145">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="5da4b-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="5da4b-146">Estado de investigación</span><span class="sxs-lookup"><span data-stu-id="5da4b-146">Investigation state</span></span> | <span data-ttu-id="5da4b-147">Filtrar incidentes por el estado de la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="5da4b-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="5da4b-148">Varias categorías</span><span class="sxs-lookup"><span data-stu-id="5da4b-148">Multiple categories</span></span> | <span data-ttu-id="5da4b-149">Puede elegir ver solo incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daños.</span><span class="sxs-lookup"><span data-stu-id="5da4b-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="5da4b-150">Múltiples orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="5da4b-150">Multiple service sources</span></span>  | <span data-ttu-id="5da4b-151">Filtra para ver solo incidentes que contienen alertas de diferentes orígenes (Microsoft Defender para endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="5da4b-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="5da4b-152">Plataforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="5da4b-152">OS platform</span></span> | <span data-ttu-id="5da4b-153">Limitar la vista de cola de incidentes por sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5da4b-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="5da4b-154">Orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="5da4b-154">Service sources</span></span> | <span data-ttu-id="5da4b-155">Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5da4b-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="5da4b-156">Gravedad</span><span class="sxs-lookup"><span data-stu-id="5da4b-156">Severity</span></span> | <span data-ttu-id="5da4b-157">La gravedad de un incidente indica el impacto que puede tener en los activos.</span><span class="sxs-lookup"><span data-stu-id="5da4b-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="5da4b-158">Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="5da4b-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="5da4b-159">Estado</span><span class="sxs-lookup"><span data-stu-id="5da4b-159">Status</span></span> | <span data-ttu-id="5da4b-160">Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.</span><span class="sxs-lookup"><span data-stu-id="5da4b-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-steps"></a><span data-ttu-id="5da4b-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5da4b-161">Next steps</span></span>

<span data-ttu-id="5da4b-162">Después de determinar qué incidente requiere la prioridad más alta, selecciónelo y:</span><span class="sxs-lookup"><span data-stu-id="5da4b-162">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="5da4b-163">[Administrar](manage-incidents.md) las propiedades del incidente para etiquetas, asignación, resolución inmediata de incidentes falsos positivos y comentarios.</span><span class="sxs-lookup"><span data-stu-id="5da4b-163">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="5da4b-164">Comience las [investigaciones](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="5da4b-164">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5da4b-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="5da4b-165">See also</span></span>
- [<span data-ttu-id="5da4b-166">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="5da4b-166">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5da4b-167">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="5da4b-167">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="5da4b-168">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="5da4b-168">Investigate incidents</span></span>](investigate-incidents.md)
