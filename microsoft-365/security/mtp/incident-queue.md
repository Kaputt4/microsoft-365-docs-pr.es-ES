---
title: Priorizar incidentes en Microsoft 365 defender
description: Obtenga información sobre cómo priorizar incidentes de la cola de incidentes en Microsoft 365 defender
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4369d51ed740af652be632ba0b8752c708d6c719
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877224"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="2571f-104">Priorizar incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="2571f-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2571f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2571f-105">**Applies to:**</span></span>
- <span data-ttu-id="2571f-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="2571f-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="2571f-107">Microsoft 365 defender aplica análisis de correlación y agrega todas las alertas y investigaciones relacionadas de distintos productos en un incidente.</span><span class="sxs-lookup"><span data-stu-id="2571f-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="2571f-108">Microsoft 365 defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dado la visibilidad de un extremo a otro que Microsoft 365 defender tiene en toda la población y en el conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="2571f-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="2571f-109">Al hacerlo, Microsoft 365 defender narra la historia de ataque más amplio, lo que permite a un analista de operaciones de seguridad comprender y tratar amenazas complejas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="2571f-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="2571f-110">La **cola de incidentes** muestra un conjunto de incidentes que se han marcado desde diferentes dispositivos, usuarios y buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="2571f-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="2571f-111">Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.</span><span class="sxs-lookup"><span data-stu-id="2571f-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Imagen de cola de incidentes](../../media/incidents-queue.png) 

<span data-ttu-id="2571f-113">De forma predeterminada, la cola del centro de seguridad 365 de Microsoft muestra los incidentes que se han visto en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="2571f-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="2571f-114">El incidente más reciente se encuentra en la parte superior de la lista, por lo que puede verlo primero.</span><span class="sxs-lookup"><span data-stu-id="2571f-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="2571f-115">La cola de incidentes expone columnas personalizables que le proporcionan visibilidad en diferentes características del incidente o las entidades que contiene.</span><span class="sxs-lookup"><span data-stu-id="2571f-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="2571f-116">Esto le ayudará a tomar una decisión informada sobre la priorización de incidentes para controlar.</span><span class="sxs-lookup"><span data-stu-id="2571f-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="2571f-117">Para obtener más visibilidad de un vistazo, la denominación automática de incidentes genera nombres de incidente en función de atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="2571f-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="2571f-118">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="2571f-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="2571f-119">Por ejemplo: *incidente de varias fases en varios puntos de conexión que han sido notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="2571f-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="2571f-120">Los incidentes que existían antes de la implementación de la asignación automática de nombres de incidentes no tendrán su nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="2571f-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="2571f-121">La cola de incidentes también expone varias opciones de filtrado, que cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos.</span><span class="sxs-lookup"><span data-stu-id="2571f-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="2571f-122">Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="2571f-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="2571f-123">Filtros disponibles</span><span class="sxs-lookup"><span data-stu-id="2571f-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="2571f-124">Asignado a</span><span class="sxs-lookup"><span data-stu-id="2571f-124">Assigned to</span></span>
<span data-ttu-id="2571f-125">Puede elegir mostrar las alertas que están asignadas a usted o a las administradas por automatización.</span><span class="sxs-lookup"><span data-stu-id="2571f-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="2571f-126">Categorías</span><span class="sxs-lookup"><span data-stu-id="2571f-126">Categories</span></span>
<span data-ttu-id="2571f-127">Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos que se ven.</span><span class="sxs-lookup"><span data-stu-id="2571f-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="2571f-128">Clasificación</span><span class="sxs-lookup"><span data-stu-id="2571f-128">Classification</span></span>
<span data-ttu-id="2571f-129">Filtre las incidencias según las clasificaciones establecidas de las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2571f-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="2571f-130">Los valores incluyen alertas verdaderas, falsas alertas o no establecidas.</span><span class="sxs-lookup"><span data-stu-id="2571f-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="2571f-131">Confidencialidad de datos</span><span class="sxs-lookup"><span data-stu-id="2571f-131">Data sensitivity</span></span>
<span data-ttu-id="2571f-132">Algunos ataques tienen por objetivo extraer datos confidenciales o importantes.</span><span class="sxs-lookup"><span data-stu-id="2571f-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="2571f-133">Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.</span><span class="sxs-lookup"><span data-stu-id="2571f-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="2571f-134">Solo se aplica si se ha activado Microsoft Information Protection. </span><span class="sxs-lookup"><span data-stu-id="2571f-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="2571f-135">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2571f-135">Device group</span></span>
<span data-ttu-id="2571f-136">Filtra por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="2571f-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="2571f-137">Estado de investigación</span><span class="sxs-lookup"><span data-stu-id="2571f-137">Investigation state</span></span>
<span data-ttu-id="2571f-138">Filtrar incidentes por el estado de la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="2571f-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="2571f-139">Varias categorías</span><span class="sxs-lookup"><span data-stu-id="2571f-139">Multiple categories</span></span> 
<span data-ttu-id="2571f-140">Puede elegir ver solo los incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daño.</span><span class="sxs-lookup"><span data-stu-id="2571f-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="2571f-141">Múltiples orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="2571f-141">Multiple service sources</span></span> 
<span data-ttu-id="2571f-142">Filtrar solo para ver incidentes que contengan alertas de diferentes orígenes (Microsoft defender para extremo, Microsoft Cloud App Security, Microsoft defender para identidad, Microsoft defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="2571f-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="2571f-143">Plataforma de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="2571f-143">OS platform</span></span>
<span data-ttu-id="2571f-144">Limitar la vista de cola de incidentes por sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2571f-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="2571f-145">Orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="2571f-145">Service sources</span></span>
<span data-ttu-id="2571f-146">Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2571f-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="2571f-147">Severity</span><span class="sxs-lookup"><span data-stu-id="2571f-147">Severity</span></span>
<span data-ttu-id="2571f-148">La gravedad de un incidente indica el impacto que puede tener en los activos.</span><span class="sxs-lookup"><span data-stu-id="2571f-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="2571f-149">Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requerirá la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="2571f-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="2571f-150">Estado</span><span class="sxs-lookup"><span data-stu-id="2571f-150">Status</span></span>
<span data-ttu-id="2571f-151">Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.</span><span class="sxs-lookup"><span data-stu-id="2571f-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2571f-152">Los filtros de clasificación, grupo de dispositivos, estado de investigación y plataforma de SO solo están disponibles actualmente en la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="2571f-152">The Classification, Device group, Investigation state, and OS platform filters are currently only available in public preview.</span></span>


## <a name="next-steps"></a><span data-ttu-id="2571f-153">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="2571f-153">Next steps</span></span>
<span data-ttu-id="2571f-154">Una vez que haya determinado qué incidente tiene mayor prioridad, puede seguir investigando.</span><span class="sxs-lookup"><span data-stu-id="2571f-154">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="2571f-155">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="2571f-155">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="2571f-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2571f-156">See also</span></span>
- [<span data-ttu-id="2571f-157">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="2571f-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2571f-158">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="2571f-158">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="2571f-159">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="2571f-159">Manage incidents</span></span>](manage-incidents.md)
