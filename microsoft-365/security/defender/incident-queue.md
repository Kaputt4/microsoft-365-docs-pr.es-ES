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
ms.openlocfilehash: c3efff1e7ebb3a5e868ede018512d12cf38e38fc
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939711"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="30706-104">Priorizar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30706-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="30706-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="30706-105">**Applies to:**</span></span>
- <span data-ttu-id="30706-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30706-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="30706-107">Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente.</span><span class="sxs-lookup"><span data-stu-id="30706-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="30706-108">Microsoft 365 Defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de extremo a extremo que Microsoft 365 Defender tiene en todo el conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="30706-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="30706-109">Esta vista ofrece a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="30706-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="30706-110">La **cola Incidentes muestra** una colección de incidentes que se crearon en dispositivos, usuarios y buzones.</span><span class="sxs-lookup"><span data-stu-id="30706-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="30706-111">Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.</span><span class="sxs-lookup"><span data-stu-id="30706-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="30706-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="30706-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

<span data-ttu-id="30706-114">De forma predeterminada, la cola de incidentes en el centro de seguridad de Microsoft 365 muestra incidentes vistos en los últimos seis meses.</span><span class="sxs-lookup"><span data-stu-id="30706-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="30706-115">El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.</span><span class="sxs-lookup"><span data-stu-id="30706-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="30706-116">La cola de incidentes tiene columnas personalizables (seleccione **Elegir** columnas) que le dan visibilidad de distintas características del incidente o de las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="30706-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="30706-117">Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.</span><span class="sxs-lookup"><span data-stu-id="30706-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="30706-118">Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="30706-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="30706-119">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="30706-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="30706-120">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="30706-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="30706-121">Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="30706-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="30706-122">La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos.</span><span class="sxs-lookup"><span data-stu-id="30706-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="30706-123">Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="30706-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="30706-124">Filtros disponibles</span><span class="sxs-lookup"><span data-stu-id="30706-124">Available filters</span></span>

<span data-ttu-id="30706-125">En la cola de incidentes  predeterminada, puede seleccionar Filtros para ver un panel Filtros, desde el que puede ver un conjunto filtrado de incidentes.</span><span class="sxs-lookup"><span data-stu-id="30706-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="30706-126">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="30706-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes":::

<span data-ttu-id="30706-128">En esta tabla se enumeran los nombres de filtro disponibles.</span><span class="sxs-lookup"><span data-stu-id="30706-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="30706-129">Nombre del filtro</span><span class="sxs-lookup"><span data-stu-id="30706-129">Filter name</span></span> | <span data-ttu-id="30706-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="30706-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="30706-131">Asignado a</span><span class="sxs-lookup"><span data-stu-id="30706-131">Assigned to</span></span> | <span data-ttu-id="30706-132">Puede elegir mostrar las alertas que se le han asignado o las que controla la automatización.</span><span class="sxs-lookup"><span data-stu-id="30706-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="30706-133">Categorías</span><span class="sxs-lookup"><span data-stu-id="30706-133">Categories</span></span> | <span data-ttu-id="30706-134">Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="30706-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="30706-135">Clasificación</span><span class="sxs-lookup"><span data-stu-id="30706-135">Classification</span></span> | <span data-ttu-id="30706-136">Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="30706-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="30706-137">Los valores incluyen alertas verdaderas, alertas falsas o no establecidas.</span><span class="sxs-lookup"><span data-stu-id="30706-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="30706-138">Confidencialidad de datos</span><span class="sxs-lookup"><span data-stu-id="30706-138">Data sensitivity</span></span> | <span data-ttu-id="30706-139">Algunos ataques tienen por objetivo extraer datos confidenciales o importantes.</span><span class="sxs-lookup"><span data-stu-id="30706-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="30706-140">Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.</span><span class="sxs-lookup"><span data-stu-id="30706-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="30706-141">Solo se aplica si se ha activado Microsoft Information Protection. </span><span class="sxs-lookup"><span data-stu-id="30706-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="30706-142">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="30706-142">Device group</span></span> | <span data-ttu-id="30706-143">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="30706-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="30706-144">Estado de investigación</span><span class="sxs-lookup"><span data-stu-id="30706-144">Investigation state</span></span> | <span data-ttu-id="30706-145">Filtrar incidentes por el estado de la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="30706-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="30706-146">Varias categorías</span><span class="sxs-lookup"><span data-stu-id="30706-146">Multiple categories</span></span> | <span data-ttu-id="30706-147">Puede elegir ver solo incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daños.</span><span class="sxs-lookup"><span data-stu-id="30706-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="30706-148">Múltiples orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="30706-148">Multiple service sources</span></span>  | <span data-ttu-id="30706-149">Filtra para ver solo incidentes que contienen alertas de diferentes orígenes (Microsoft Defender para Endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="30706-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="30706-150">Plataforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="30706-150">OS platform</span></span> | <span data-ttu-id="30706-151">Limitar la vista de cola de incidentes por sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="30706-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="30706-152">Orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="30706-152">Service sources</span></span> | <span data-ttu-id="30706-153">Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado.</span><span class="sxs-lookup"><span data-stu-id="30706-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="30706-154">Severity</span><span class="sxs-lookup"><span data-stu-id="30706-154">Severity</span></span> | <span data-ttu-id="30706-155">La gravedad de un incidente indica el impacto que puede tener en los activos.</span><span class="sxs-lookup"><span data-stu-id="30706-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="30706-156">Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="30706-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="30706-157">Estado</span><span class="sxs-lookup"><span data-stu-id="30706-157">Status</span></span> | <span data-ttu-id="30706-158">Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.</span><span class="sxs-lookup"><span data-stu-id="30706-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="30706-159">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="30706-159">Next step</span></span>

<span data-ttu-id="30706-160">Después de determinar qué incidente requiere la prioridad más alta, selecciónelo e inicie el [análisis](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="30706-160">After you've determined which incident requires the highest priority, select it and begin your [analysis](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="30706-161">Ver también</span><span class="sxs-lookup"><span data-stu-id="30706-161">See also</span></span>
- [<span data-ttu-id="30706-162">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="30706-162">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="30706-163">Analizar incidentes</span><span class="sxs-lookup"><span data-stu-id="30706-163">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="30706-164">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="30706-164">Manage incidents</span></span>](manage-incidents.md)
