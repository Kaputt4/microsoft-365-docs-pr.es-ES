---
title: Investigar alertas en Microsoft 365 Defender
description: Investigar las alertas que se ven en dispositivos, usuarios y buzones.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365
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
ms.openlocfilehash: 6a34269c414f59d40c9160d5728159ed9cddf976
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651359"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="de78e-104">Investigar alertas en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de78e-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="de78e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="de78e-105">**Applies to:**</span></span>
- <span data-ttu-id="de78e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de78e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="de78e-107">Las alertas son la base de todos los incidentes e indican la aparición de eventos malintencionados o sospechosos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="de78e-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="de78e-108">Las alertas suelen formar parte de un ataque más amplio y proporcionan pistas sobre un incidente.</span><span class="sxs-lookup"><span data-stu-id="de78e-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="de78e-109">En Microsoft 365 Defender, las alertas relacionadas se agregan juntas para formar [incidentes](incidents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="de78e-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="de78e-110">Los incidentes siempre proporcionarán el contexto más amplio de un ataque, sin embargo, el análisis de alertas puede ser útil cuando se requiere un análisis más profundo.</span><span class="sxs-lookup"><span data-stu-id="de78e-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="de78e-111">La **cola De alertas** muestra el conjunto actual de alertas.</span><span class="sxs-lookup"><span data-stu-id="de78e-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="de78e-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="de78e-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Ejemplo de la cola de alertas":::

<span data-ttu-id="de78e-114">Las alertas de diferentes soluciones de seguridad de Microsoft como Microsoft Defender para endpoint, Microsoft Defender para Office 365 y Microsoft 365 Defender aparecen aquí.</span><span class="sxs-lookup"><span data-stu-id="de78e-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="de78e-115">De forma predeterminada, la cola de alertas del centro de seguridad Microsoft 365 muestra las alertas nuevas y en curso de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="de78e-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="de78e-116">La alerta más reciente está en la parte superior de la lista para que pueda verla primero.</span><span class="sxs-lookup"><span data-stu-id="de78e-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="de78e-117">En la cola de alertas predeterminada, puede seleccionar Filtros **para** ver un panel **Filtros,** desde el que puede especificar un subconjunto de las alertas.</span><span class="sxs-lookup"><span data-stu-id="de78e-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="de78e-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="de78e-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Ejemplo del panel de filtros de la cola de alertas":::

<span data-ttu-id="de78e-120">Puede filtrar alertas según estos criterios:</span><span class="sxs-lookup"><span data-stu-id="de78e-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="de78e-121">Gravedad</span><span class="sxs-lookup"><span data-stu-id="de78e-121">Severity</span></span>
- <span data-ttu-id="de78e-122">Estado</span><span class="sxs-lookup"><span data-stu-id="de78e-122">Status</span></span>
- <span data-ttu-id="de78e-123">Categoría</span><span class="sxs-lookup"><span data-stu-id="de78e-123">Category</span></span>
- <span data-ttu-id="de78e-124">Origen de detección</span><span class="sxs-lookup"><span data-stu-id="de78e-124">Detection source</span></span>
- <span data-ttu-id="de78e-125">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="de78e-125">Tags</span></span>
- <span data-ttu-id="de78e-126">Directiva</span><span class="sxs-lookup"><span data-stu-id="de78e-126">Policy</span></span>
- <span data-ttu-id="de78e-127">Activos afectados</span><span class="sxs-lookup"><span data-stu-id="de78e-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="de78e-128">Analizar una alerta</span><span class="sxs-lookup"><span data-stu-id="de78e-128">Analyze an alert</span></span>

<span data-ttu-id="de78e-129">Para ver la página de alerta principal, seleccione el nombre de la alerta.</span><span class="sxs-lookup"><span data-stu-id="de78e-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="de78e-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="de78e-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Ejemplo de la página de detalles de una alerta en el centro Microsoft 365 seguridad":::

<span data-ttu-id="de78e-132">También puede seleccionar la acción **Abrir la página de alerta** principal en el panel **Administrar** alerta.</span><span class="sxs-lookup"><span data-stu-id="de78e-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="de78e-133">Una página de alerta se compone de estas secciones:</span><span class="sxs-lookup"><span data-stu-id="de78e-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="de78e-134">Historia de alertas, que es la cadena de eventos y alertas relacionadas con esta alerta en orden cronológico</span><span class="sxs-lookup"><span data-stu-id="de78e-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="de78e-135">Detalles de resumen</span><span class="sxs-lookup"><span data-stu-id="de78e-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Ejemplo de la página de detalles de una alerta en el centro Microsoft 365 seguridad":::

<span data-ttu-id="de78e-137">A lo largo de una página de alerta, puede seleccionar los puntos suspensivos (**...**) junto a cualquier entidad para ver las acciones disponibles, como abrir la página de alerta o vincular la alerta a otro incidente.</span><span class="sxs-lookup"><span data-stu-id="de78e-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="de78e-138">Analizar activos afectados</span><span class="sxs-lookup"><span data-stu-id="de78e-138">Analyze affected assets</span></span>

<span data-ttu-id="de78e-139">La **sección Acciones realizadas** tiene una lista de activos afectados, como buzones, dispositivos y usuarios afectados por esta alerta.</span><span class="sxs-lookup"><span data-stu-id="de78e-139">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="de78e-140">También puede seleccionar Ver **en el centro** de  acciones para ver la pestaña Historial del Centro de acciones en el centro de Microsoft 365 seguridad. </span><span class="sxs-lookup"><span data-stu-id="de78e-140">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="de78e-141">Seguimiento del rol de una alerta en el artículo de alerta</span><span class="sxs-lookup"><span data-stu-id="de78e-141">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="de78e-142">El artículo de alerta muestra todos los activos o entidades relacionados con la alerta en una vista de árbol de proceso.</span><span class="sxs-lookup"><span data-stu-id="de78e-142">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="de78e-143">La alerta del título es la que está en foco cuando se aterriza por primera vez en la página de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de78e-143">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="de78e-144">Los activos del artículo de alerta se pueden expandir y hacer clic.</span><span class="sxs-lookup"><span data-stu-id="de78e-144">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="de78e-145">Proporcionan información adicional y aceleran la respuesta, ya que permiten realizar acciones directamente en el contexto de la página de alerta.</span><span class="sxs-lookup"><span data-stu-id="de78e-145">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="de78e-146">La sección de artículo de alerta puede contener más de una alerta, con alertas adicionales relacionadas con el mismo árbol de ejecución que aparecen antes o después de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de78e-146">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="de78e-147">Ver más información de alerta en la página de detalles</span><span class="sxs-lookup"><span data-stu-id="de78e-147">View more alert information on the details page</span></span>

<span data-ttu-id="de78e-148">La página de detalles muestra los detalles de la alerta seleccionada, con detalles y acciones relacionadas con ella.</span><span class="sxs-lookup"><span data-stu-id="de78e-148">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="de78e-149">Si selecciona cualquiera de los activos o entidades afectados en el artículo de alerta, la página de detalles cambia para proporcionar información contextual y acciones para el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="de78e-149">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="de78e-150">Una vez que haya seleccionado una entidad de interés, la página de detalles cambia para mostrar información sobre el tipo de entidad seleccionada, información histórica cuando está disponible y opciones para realizar acciones en esta entidad directamente desde la página de alerta.</span><span class="sxs-lookup"><span data-stu-id="de78e-150">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="de78e-151">Administrar alertas</span><span class="sxs-lookup"><span data-stu-id="de78e-151">Manage alerts</span></span>

<span data-ttu-id="de78e-152">Para administrar una alerta, seleccione la alerta en la cola de alertas de su fila para ver un **panel Administrar alertas.**</span><span class="sxs-lookup"><span data-stu-id="de78e-152">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="de78e-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="de78e-153">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Ejemplo del panel de resumen de una alerta":::

<span data-ttu-id="de78e-155">El **panel Administrar alerta** permite especificar:</span><span class="sxs-lookup"><span data-stu-id="de78e-155">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="de78e-156">Estado de alerta (Nuevo, Resuelto, En curso).</span><span class="sxs-lookup"><span data-stu-id="de78e-156">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="de78e-157">Clasificación de la alerta (No establecido, Alerta verdadera, Alerta falsa).</span><span class="sxs-lookup"><span data-stu-id="de78e-157">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="de78e-158">Para la clasificación como una alerta verdadera, el tipo de amenaza de la alerta en **el campo Determinación.**</span><span class="sxs-lookup"><span data-stu-id="de78e-158">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="de78e-159">Un comentario sobre la alerta.</span><span class="sxs-lookup"><span data-stu-id="de78e-159">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="de78e-160">Una forma de administrar alertas mediante el uso de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="de78e-160">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="de78e-161">La funcionalidad de etiquetado para Microsoft Defender para Office 365 se está ejecutando de forma incremental y actualmente está en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="de78e-161">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="de78e-162">Actualmente, los nombres de etiqueta modificados solo se aplican a las alertas *creadas después de* la actualización.</span><span class="sxs-lookup"><span data-stu-id="de78e-162">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="de78e-163">Las alertas que se generaron antes de la modificación no reflejarán el nombre de la etiqueta actualizada.</span><span class="sxs-lookup"><span data-stu-id="de78e-163">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="de78e-164">Desde este panel, también puede realizar estas acciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="de78e-164">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="de78e-165">Abrir la página de alerta principal</span><span class="sxs-lookup"><span data-stu-id="de78e-165">Open the main alert page</span></span>
- <span data-ttu-id="de78e-166">Consultar a un experto en amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="de78e-166">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="de78e-167">Ver envío</span><span class="sxs-lookup"><span data-stu-id="de78e-167">View submission</span></span>
- <span data-ttu-id="de78e-168">Vincular a otro incidente</span><span class="sxs-lookup"><span data-stu-id="de78e-168">Link to another incident</span></span>
- <span data-ttu-id="de78e-169">Ver la alerta en una escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="de78e-169">See the alert in a timeline</span></span>
- <span data-ttu-id="de78e-170">Crear una regla de supresión</span><span class="sxs-lookup"><span data-stu-id="de78e-170">Create a suppression rule</span></span>

<span data-ttu-id="de78e-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="de78e-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Ejemplo de las acciones de una alerta en el centro de Microsoft 365 seguridad":::

<span data-ttu-id="de78e-173">La lista de acciones adicionales depende del tipo de alerta.</span><span class="sxs-lookup"><span data-stu-id="de78e-173">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="de78e-174">Resolver una alerta</span><span class="sxs-lookup"><span data-stu-id="de78e-174">Resolve an alert</span></span>

<span data-ttu-id="de78e-175">Una vez que haya terminado de analizar una alerta  y se pueda resolver, vaya al  panel Administrar alerta de la alerta y marque el estado de la alerta como Resuelto y clasifique como alerta **False** o **Alerta True**.</span><span class="sxs-lookup"><span data-stu-id="de78e-175">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="de78e-176">Para las alertas true, especifique el tipo de amenaza de la alerta en el **campo Determinación.**</span><span class="sxs-lookup"><span data-stu-id="de78e-176">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="de78e-177">Clasificar alertas y especificar su determinación ayuda a ajustar Microsoft 365 Defender para proporcionar alertas más verdaderas y menos falsas.</span><span class="sxs-lookup"><span data-stu-id="de78e-177">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de78e-178">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="de78e-178">Next steps</span></span>

<span data-ttu-id="de78e-179">Según sea necesario para incidentes en el proceso, continúe con la [investigación](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="de78e-179">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="de78e-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="de78e-180">See also</span></span>

- [<span data-ttu-id="de78e-181">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="de78e-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="de78e-182">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="de78e-182">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="de78e-183">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="de78e-183">Investigate incidents</span></span>](investigate-incidents.md)
