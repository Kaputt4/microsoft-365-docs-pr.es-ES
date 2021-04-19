---
title: Priorizar incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 Defender
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes
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
ms.openlocfilehash: 3b381749108d4a75024d9a546c0d3f1631c948ed
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887262"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="0a629-104">Priorizar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a629-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0a629-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0a629-105">**Applies to:**</span></span>
- <span data-ttu-id="0a629-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a629-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0a629-107">Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente.</span><span class="sxs-lookup"><span data-stu-id="0a629-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="0a629-108">Microsoft 365 Defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de extremo a extremo que Microsoft 365 Defender tiene en todo el conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="0a629-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="0a629-109">Esta vista ofrece a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="0a629-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="0a629-110">La **cola Incidentes muestra** una colección de incidentes que se crearon en dispositivos, usuarios y buzones.</span><span class="sxs-lookup"><span data-stu-id="0a629-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="0a629-111">Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.</span><span class="sxs-lookup"><span data-stu-id="0a629-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="0a629-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="0a629-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

<span data-ttu-id="0a629-114">De forma predeterminada, la cola de incidentes en el centro de seguridad de Microsoft 365 muestra incidentes vistos en los últimos seis meses.</span><span class="sxs-lookup"><span data-stu-id="0a629-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="0a629-115">El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.</span><span class="sxs-lookup"><span data-stu-id="0a629-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="0a629-116">La cola de incidentes tiene columnas personalizables (seleccione **Elegir** columnas) que le dan visibilidad de distintas características del incidente o de las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="0a629-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="0a629-117">Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.</span><span class="sxs-lookup"><span data-stu-id="0a629-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="0a629-118">Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="0a629-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="0a629-119">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="0a629-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="0a629-120">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="0a629-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="0a629-121">Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="0a629-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="0a629-122">La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos.</span><span class="sxs-lookup"><span data-stu-id="0a629-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="0a629-123">Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="0a629-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="0a629-124">Filtros disponibles</span><span class="sxs-lookup"><span data-stu-id="0a629-124">Available filters</span></span>

<span data-ttu-id="0a629-125">En la cola de incidentes  predeterminada, puede seleccionar Filtros para ver un panel Filtros, desde el que puede ver un conjunto filtrado de incidentes.</span><span class="sxs-lookup"><span data-stu-id="0a629-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="0a629-126">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0a629-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes":::

<span data-ttu-id="0a629-128">En esta tabla se enumeran los nombres de filtro disponibles.</span><span class="sxs-lookup"><span data-stu-id="0a629-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="0a629-129">Nombre del filtro</span><span class="sxs-lookup"><span data-stu-id="0a629-129">Filter name</span></span> | <span data-ttu-id="0a629-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="0a629-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="0a629-131">Asignado a</span><span class="sxs-lookup"><span data-stu-id="0a629-131">Assigned to</span></span> | <span data-ttu-id="0a629-132">Puede elegir mostrar las alertas que se le han asignado o las que controla la automatización.</span><span class="sxs-lookup"><span data-stu-id="0a629-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="0a629-133">Categorías</span><span class="sxs-lookup"><span data-stu-id="0a629-133">Categories</span></span> | <span data-ttu-id="0a629-134">Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="0a629-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="0a629-135">Clasificación</span><span class="sxs-lookup"><span data-stu-id="0a629-135">Classification</span></span> | <span data-ttu-id="0a629-136">Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0a629-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="0a629-137">Los valores incluyen alertas verdaderas, alertas falsas o no establecidas.</span><span class="sxs-lookup"><span data-stu-id="0a629-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="0a629-138">Confidencialidad de datos</span><span class="sxs-lookup"><span data-stu-id="0a629-138">Data sensitivity</span></span> | <span data-ttu-id="0a629-139">Algunos ataques tienen por objetivo extraer datos confidenciales o importantes.</span><span class="sxs-lookup"><span data-stu-id="0a629-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="0a629-140">Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.</span><span class="sxs-lookup"><span data-stu-id="0a629-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="0a629-141">Solo se aplica si se ha activado Microsoft Information Protection. </span><span class="sxs-lookup"><span data-stu-id="0a629-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="0a629-142">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0a629-142">Device group</span></span> | <span data-ttu-id="0a629-143">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="0a629-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="0a629-144">Estado de investigación</span><span class="sxs-lookup"><span data-stu-id="0a629-144">Investigation state</span></span> | <span data-ttu-id="0a629-145">Filtrar incidentes por el estado de la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="0a629-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="0a629-146">Varias categorías</span><span class="sxs-lookup"><span data-stu-id="0a629-146">Multiple categories</span></span> | <span data-ttu-id="0a629-147">Puede elegir ver solo incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daños.</span><span class="sxs-lookup"><span data-stu-id="0a629-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="0a629-148">Múltiples orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="0a629-148">Multiple service sources</span></span>  | <span data-ttu-id="0a629-149">Filtra para ver solo incidentes que contienen alertas de diferentes orígenes (Microsoft Defender para Endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="0a629-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="0a629-150">Plataforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="0a629-150">OS platform</span></span> | <span data-ttu-id="0a629-151">Limitar la vista de cola de incidentes por sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0a629-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="0a629-152">Orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="0a629-152">Service sources</span></span> | <span data-ttu-id="0a629-153">Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0a629-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="0a629-154">Severity</span><span class="sxs-lookup"><span data-stu-id="0a629-154">Severity</span></span> | <span data-ttu-id="0a629-155">La gravedad de un incidente indica el impacto que puede tener en los activos.</span><span class="sxs-lookup"><span data-stu-id="0a629-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="0a629-156">Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="0a629-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="0a629-157">Estado</span><span class="sxs-lookup"><span data-stu-id="0a629-157">Status</span></span> | <span data-ttu-id="0a629-158">Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.</span><span class="sxs-lookup"><span data-stu-id="0a629-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="0a629-159">Flujo de trabajo de respuesta a incidentes</span><span class="sxs-lookup"><span data-stu-id="0a629-159">Incident response workflow</span></span>

<span data-ttu-id="0a629-160">Este es el flujo de trabajo típico para responder a incidentes:</span><span class="sxs-lookup"><span data-stu-id="0a629-160">Here's the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="0a629-161">Identifique y triage los incidentes de mayor prioridad para investigación y resolución.</span><span class="sxs-lookup"><span data-stu-id="0a629-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="0a629-162">Para cada incidente de prioridad alta, inicie una [investigación:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="0a629-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="0a629-163">a.</span><span class="sxs-lookup"><span data-stu-id="0a629-163">a.</span></span> <span data-ttu-id="0a629-164">Vea el resumen del incidente para comprender su ámbito y gravedad y qué entidades se ven afectadas (la **pestaña Resumen).**</span><span class="sxs-lookup"><span data-stu-id="0a629-164">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="0a629-165">b.</span><span class="sxs-lookup"><span data-stu-id="0a629-165">b.</span></span> <span data-ttu-id="0a629-166">Comience a ver las alertas para comprender su origen, ámbito y gravedad (la **pestaña** Alertas).</span><span class="sxs-lookup"><span data-stu-id="0a629-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="0a629-167">c.</span><span class="sxs-lookup"><span data-stu-id="0a629-167">c.</span></span> <span data-ttu-id="0a629-168">Según sea necesario, recopila información sobre dispositivos, usuarios y buzones afectados (las pestañas **Dispositivos,** **Usuarios** y **Buzones).**</span><span class="sxs-lookup"><span data-stu-id="0a629-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="0a629-169">d.</span><span class="sxs-lookup"><span data-stu-id="0a629-169">d.</span></span> <span data-ttu-id="0a629-170">Vea cómo Microsoft 365 Defender ha resuelto automáticamente algunas **alertas** (la pestaña Investigaciones).</span><span class="sxs-lookup"><span data-stu-id="0a629-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="0a629-171">e.</span><span class="sxs-lookup"><span data-stu-id="0a629-171">e.</span></span> <span data-ttu-id="0a629-172">Según sea necesario, use la información del conjunto de datos para el incidente para obtener más información (la **pestaña Evidencia y** respuesta).</span><span class="sxs-lookup"><span data-stu-id="0a629-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

   <span data-ttu-id="0a629-173">A medida que investigue, debe preocuparse de:</span><span class="sxs-lookup"><span data-stu-id="0a629-173">As you investigate, you should be concerned with:</span></span>

   - <span data-ttu-id="0a629-174">Contención: reducir cualquier impacto adicional en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="0a629-174">Containment: Reducing any additional impact on your tenant.</span></span>
   - <span data-ttu-id="0a629-175">Eliminación de la amenaza de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0a629-175">Eradication: Removing the security threat.</span></span>
   - <span data-ttu-id="0a629-176">Recuperación: restaurar los recursos del espacio empresarial en el estado en que se encontraban antes del incidente.</span><span class="sxs-lookup"><span data-stu-id="0a629-176">Recovery: Restoring your tenant resources to the state they were in before the incident.</span></span>

3. <span data-ttu-id="0a629-177">Después de resolver el incidente, tómese el tiempo para:</span><span class="sxs-lookup"><span data-stu-id="0a629-177">After you resolve the incident, take the time to:</span></span>

   - <span data-ttu-id="0a629-178">Comprender el tipo de ataque y su impacto.</span><span class="sxs-lookup"><span data-stu-id="0a629-178">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="0a629-179">Investigue el ataque en la comunidad de seguridad para obtener una tendencia de ataque de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0a629-179">Research the attack in the security community for a security attack trend.</span></span>
   - <span data-ttu-id="0a629-180">Recuerde el flujo de trabajo que usó para resolver el incidente y actualice los flujos de trabajo estándar y los libros de reproducción según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0a629-180">Recall the workflow you used to resolve the incident and update your standard workflows and playbooks as needed.</span></span>
   - <span data-ttu-id="0a629-181">Determine si es necesario realizar cambios en la posición de seguridad y siga los pasos necesarios para implementarlos.</span><span class="sxs-lookup"><span data-stu-id="0a629-181">Determine whether changes in your security posture are needed and take the steps to implement them.</span></span>

<span data-ttu-id="0a629-182">Este es un resumen del proceso básico.</span><span class="sxs-lookup"><span data-stu-id="0a629-182">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Proceso básico para investigar incidentes":::

## <a name="next-step"></a><span data-ttu-id="0a629-184">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="0a629-184">Next step</span></span>

<span data-ttu-id="0a629-185">Después de determinar qué incidente requiere la prioridad más alta, selecciónelo e inicie la [investigación](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="0a629-185">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0a629-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a629-186">See also</span></span>
- [<span data-ttu-id="0a629-187">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="0a629-187">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0a629-188">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="0a629-188">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="0a629-189">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="0a629-189">Manage incidents</span></span>](manage-incidents.md)
