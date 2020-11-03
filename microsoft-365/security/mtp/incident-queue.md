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
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846717"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="a5048-104">Priorizar incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="a5048-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a5048-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a5048-105">**Applies to:**</span></span>
- <span data-ttu-id="a5048-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="a5048-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="a5048-107">Microsoft 365 defender aplica análisis de correlación y agrega todas las alertas y investigaciones relacionadas de distintos productos en un incidente.</span><span class="sxs-lookup"><span data-stu-id="a5048-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="a5048-108">Microsoft 365 defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dado la visibilidad de un extremo a otro que Microsoft 365 defender tiene en toda la población y en el conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="a5048-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="a5048-109">Al hacerlo, Microsoft 365 defender narra la historia de ataque más amplio, lo que permite a un analista de operaciones de seguridad comprender y tratar amenazas complejas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="a5048-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="a5048-110">La **cola de incidentes** muestra un conjunto de incidentes que se han marcado desde diferentes dispositivos, usuarios y buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="a5048-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="a5048-111">Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.</span><span class="sxs-lookup"><span data-stu-id="a5048-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Imagen de cola de incidentes](../../media/incidents-queue.png) 

<span data-ttu-id="a5048-113">De manera predeterminada, la cola del Centro de seguridad de Microsoft 365 muestra los incidentes encontrados en los últimos 30 días, con el incidente más reciente en la parte superior de la lista, ayudándole así a ver primero los incidentes más recientes.</span><span class="sxs-lookup"><span data-stu-id="a5048-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="a5048-114">La cola de incidentes expone columnas personalizables donde podrá ver las distintas características del incidente o de las entidades que contiene, lo que le permite tomar decisiones fundamentadas sobre la priorización de incidentes que debe controlar.</span><span class="sxs-lookup"><span data-stu-id="a5048-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="a5048-115">Para obtener más visibilidad de un vistazo, la denominación automática de incidentes genera nombres de incidente en función de atributos de alerta como el número de puntos de conexión afectados, los usuarios afectados, las fuentes o categorías de detección.</span><span class="sxs-lookup"><span data-stu-id="a5048-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="a5048-116">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="a5048-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="a5048-117">Por ejemplo: *incidente de varias fases en varios puntos de conexión que han sido notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="a5048-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="a5048-118">Los incidentes que existían antes de la implementación de la asignación automática de nombres de incidentes no tendrán su nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="a5048-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="a5048-119">La cola de incidentes también muestra opciones de filtrado que, al aplicarlas, le permiten decidir si limpiar todos los incidentes existentes en su entorno o enfocarse en un escenario o amenaza específica.</span><span class="sxs-lookup"><span data-stu-id="a5048-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="a5048-120">Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="a5048-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="a5048-121">Filtros disponibles</span><span class="sxs-lookup"><span data-stu-id="a5048-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="a5048-122">Estado</span><span class="sxs-lookup"><span data-stu-id="a5048-122">Status</span></span>
<span data-ttu-id="a5048-123">Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.</span><span class="sxs-lookup"><span data-stu-id="a5048-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="a5048-124">Gravedad</span><span class="sxs-lookup"><span data-stu-id="a5048-124">Severity</span></span>
<span data-ttu-id="a5048-125">La gravedad de un incidente indica el impacto que puede tener en sus activos.</span><span class="sxs-lookup"><span data-stu-id="a5048-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="a5048-126">Cuanto mayor sea el nivel de gravedad, mayor será el impacto y, por lo general, requerirá atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="a5048-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="a5048-127">Asignado a (propietario)</span><span class="sxs-lookup"><span data-stu-id="a5048-127">Assigned to (owner)</span></span>
<span data-ttu-id="a5048-128">Puede filtrar la lista seleccionando los incidentes asignados a cualquiera o solo los asignados a su usuario.</span><span class="sxs-lookup"><span data-stu-id="a5048-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="a5048-129">Más de una alerta</span><span class="sxs-lookup"><span data-stu-id="a5048-129">Multiple alerts</span></span> 
<span data-ttu-id="a5048-130">Filtre para ver solo los incidentes que contienen más de una alerta.</span><span class="sxs-lookup"><span data-stu-id="a5048-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="a5048-131">Esto podría ser una indicación para un ataque que es más complejo o que progresa en la cadena de eliminación.</span><span class="sxs-lookup"><span data-stu-id="a5048-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="a5048-132">Múltiples orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="a5048-132">Multiple service sources</span></span> 
<span data-ttu-id="a5048-133">Filtrar solo para ver incidentes que contienen alertas de diferentes orígenes (Microsoft defender para el extremo, Microsoft Cloud App Security, Microsoft defender para identidad, Microsoft defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="a5048-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365)</span></span>
### <a name="service-sources"></a><span data-ttu-id="a5048-134">Orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="a5048-134">Service sources</span></span>
<span data-ttu-id="a5048-135">Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a5048-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="a5048-136">Varias categorías</span><span class="sxs-lookup"><span data-stu-id="a5048-136">Multiple categories</span></span> 
<span data-ttu-id="a5048-137">Puede elegir ver solo los incidentes que se han asignado a varias categorías de la cadena de eliminación y que pueden provocar más daño.</span><span class="sxs-lookup"><span data-stu-id="a5048-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="a5048-138">Categorías</span><span class="sxs-lookup"><span data-stu-id="a5048-138">Categories</span></span>
<span data-ttu-id="a5048-139">Elija categorías específicas para concentrarse en un paso específico de la cadena de eliminación</span><span class="sxs-lookup"><span data-stu-id="a5048-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="a5048-140">Confidencialidad de datos</span><span class="sxs-lookup"><span data-stu-id="a5048-140">Data sensitivity</span></span>
<span data-ttu-id="a5048-141">Algunos ataques tienen por objetivo extraer datos confidenciales o importantes.</span><span class="sxs-lookup"><span data-stu-id="a5048-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="a5048-142">Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.</span><span class="sxs-lookup"><span data-stu-id="a5048-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="a5048-143">Solo se aplica si se ha activado Microsoft Information Protection. </span><span class="sxs-lookup"><span data-stu-id="a5048-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="a5048-144">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="a5048-144">Next steps</span></span>
<span data-ttu-id="a5048-145">Una vez que haya determinado qué incidente tiene mayor prioridad, puede seguir investigando.</span><span class="sxs-lookup"><span data-stu-id="a5048-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="a5048-146">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="a5048-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="a5048-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a5048-147">Related topics</span></span>
- [<span data-ttu-id="a5048-148">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="a5048-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a5048-149">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="a5048-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a5048-150">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="a5048-150">Manage incidents</span></span>](manage-incidents.md)
