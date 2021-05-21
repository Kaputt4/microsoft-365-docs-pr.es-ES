---
title: Administrar incidentes en Microsoft 365 Defender
description: Obtenga información acerca de cómo asignar, actualizar el estado
keywords: incidente, incidentes, análisis, respuesta, alertas, alertas correlacionadas, asignar, actualizar, estado, administrar, clasificación, microsoft, 365, m365
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
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594160"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="9cb70-104">Administrar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb70-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9cb70-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9cb70-105">**Applies to:**</span></span>
- <span data-ttu-id="9cb70-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb70-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9cb70-107">La administración de incidentes es fundamental para garantizar que las amenazas se contengan y se aborde.</span><span class="sxs-lookup"><span data-stu-id="9cb70-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="9cb70-108">Puede administrar incidentes de **incidentes & alertas > incidentes en** el inicio rápido del centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="9cb70-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="9cb70-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9cb70-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

<span data-ttu-id="9cb70-111">Estas son las formas en que puede administrar sus incidentes:</span><span class="sxs-lookup"><span data-stu-id="9cb70-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="9cb70-112">Editar el nombre del incidente</span><span class="sxs-lookup"><span data-stu-id="9cb70-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="9cb70-113">Agregar etiquetas de incidente</span><span class="sxs-lookup"><span data-stu-id="9cb70-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="9cb70-114">Asignar el incidente a usted mismo</span><span class="sxs-lookup"><span data-stu-id="9cb70-114">Assign the incident to yourself</span></span>](#assign-incidents)
- [<span data-ttu-id="9cb70-115">Resolverlos</span><span class="sxs-lookup"><span data-stu-id="9cb70-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="9cb70-116">Establecer su clasificación y determinación</span><span class="sxs-lookup"><span data-stu-id="9cb70-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="9cb70-117">Agregar comentarios</span><span class="sxs-lookup"><span data-stu-id="9cb70-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="9cb70-118">Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente.</span><span class="sxs-lookup"><span data-stu-id="9cb70-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="9cb70-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9cb70-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Ejemplo del panel Administrar incidentes de un incidente":::

<span data-ttu-id="9cb70-121">Puede mostrar este panel desde el vínculo **Administrar incidentes** en:</span><span class="sxs-lookup"><span data-stu-id="9cb70-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="9cb70-122">Panel de propiedades de un incidente en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="9cb70-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="9cb70-123">**Página de** resumen de un incidente.</span><span class="sxs-lookup"><span data-stu-id="9cb70-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="9cb70-124">En los casos en los que quiera mover alertas de  un incidente a otro, también puede hacerlo desde la pestaña Alertas, creando así un incidente más grande o más pequeño que incluya todas las alertas relevantes.</span><span class="sxs-lookup"><span data-stu-id="9cb70-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="9cb70-125">Editar el nombre del incidente</span><span class="sxs-lookup"><span data-stu-id="9cb70-125">Edit the incident name</span></span>

<span data-ttu-id="9cb70-126">Microsoft 365 Defender asigna automáticamente un nombre en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="9cb70-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="9cb70-127">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="9cb70-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="9cb70-128">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="9cb70-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="9cb70-129">Puede editar el nombre del incidente desde el campo **Nombre del** incidente en el **panel Administrar** incidente.</span><span class="sxs-lookup"><span data-stu-id="9cb70-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb70-130">Los incidentes que existían antes de la implementación de la característica de nomenclatura automática de incidentes conservarán su nombre.</span><span class="sxs-lookup"><span data-stu-id="9cb70-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="9cb70-131">Agregar etiquetas de incidente</span><span class="sxs-lookup"><span data-stu-id="9cb70-131">Add incident tags</span></span>

<span data-ttu-id="9cb70-132">Puede agregar etiquetas personalizadas a un incidente, por ejemplo, para marcar un grupo de incidentes con una característica común.</span><span class="sxs-lookup"><span data-stu-id="9cb70-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="9cb70-133">Más adelante, puede filtrar la cola de incidentes para todos los incidentes que contengan una etiqueta específica.</span><span class="sxs-lookup"><span data-stu-id="9cb70-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="9cb70-134">Al empezar a escribir, tiene la opción de seleccionar de una lista de etiquetas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9cb70-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="9cb70-135">Asignar incidentes</span><span class="sxs-lookup"><span data-stu-id="9cb70-135">Assign incidents</span></span>

<span data-ttu-id="9cb70-136">Para asignar un incidente, seleccione **Asignarme**.</span><span class="sxs-lookup"><span data-stu-id="9cb70-136">To assign an incident, select **Assign to me**.</span></span> <span data-ttu-id="9cb70-137">Al hacerlo, se asigna la propiedad del incidente y todas las alertas asociadas a ella a su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="9cb70-137">Doing so assigns ownership of the incident and all the alerts associated with it to your user account.</span></span>

<span data-ttu-id="9cb70-138">Puede obtener una lista de incidentes asignados filtrando la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="9cb70-138">You can get a list of incidents assigned to you by filtering the incident queue.</span></span> 

1. <span data-ttu-id="9cb70-139">En la cola de incidentes, seleccione **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="9cb70-139">From the incident queue, select **Filters**.</span></span>
2. <span data-ttu-id="9cb70-140">en la **sección Asignación de** incidentes, desactive **Seleccionar todo** y seleccione Asignado **a mí**.</span><span class="sxs-lookup"><span data-stu-id="9cb70-140">in the **Incident assignment** section, clear **Select all** and select **Assigned to me**.</span></span>
3. <span data-ttu-id="9cb70-141">Seleccione **Aplicar** y, a continuación, cierre el **panel** Filtros.</span><span class="sxs-lookup"><span data-stu-id="9cb70-141">Select **Apply**, and then close the **Filters** pane.</span></span>

<span data-ttu-id="9cb70-142">A continuación, puede guardar la dirección URL resultante en el explorador como marcador para ver rápidamente la lista de incidentes asignados.</span><span class="sxs-lookup"><span data-stu-id="9cb70-142">You can then save the resulting URL in your browser as a bookmark to quickly see the list of incidents assigned to you.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="9cb70-143">Resolver un incidente</span><span class="sxs-lookup"><span data-stu-id="9cb70-143">Resolve an incident</span></span>

<span data-ttu-id="9cb70-144">Si el incidente se ha corregido, seleccione **Resolver incidente** para mover la alternancia a la derecha.</span><span class="sxs-lookup"><span data-stu-id="9cb70-144">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="9cb70-145">Tenga en cuenta que la resolución de un incidente también resuelve todas las alertas vinculadas y activas relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="9cb70-145">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="9cb70-146">Un incidente que no se resuelve se muestra como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="9cb70-146">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="9cb70-147">Establecer la clasificación y la determinación</span><span class="sxs-lookup"><span data-stu-id="9cb70-147">Set the classification and determination</span></span>

<span data-ttu-id="9cb70-148">La clasificación de incidentes es si se trata de una alerta verdadera o una alerta falsa, que se configura desde el **campo Clasificación.**</span><span class="sxs-lookup"><span data-stu-id="9cb70-148">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="9cb70-149">Si se trataba de una alerta verdadera, también debe especificar qué tipo de amenaza era con el **campo Determinación.**</span><span class="sxs-lookup"><span data-stu-id="9cb70-149">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="9cb70-150">Especificar el tipo de amenaza ayuda a su equipo de seguridad a ver patrones de amenazas y actuar para defender su organización de ellos.</span><span class="sxs-lookup"><span data-stu-id="9cb70-150">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="9cb70-151">Agregar comentarios</span><span class="sxs-lookup"><span data-stu-id="9cb70-151">Add comments</span></span>

<span data-ttu-id="9cb70-152">Puede agregar varios comentarios a un incidente con el **campo Comentario.**</span><span class="sxs-lookup"><span data-stu-id="9cb70-152">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="9cb70-153">Cada comentario se agrega a los eventos históricos del incidente.</span><span class="sxs-lookup"><span data-stu-id="9cb70-153">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="9cb70-154">Puede ver los comentarios y el historial de un incidente desde el vínculo **Comentarios e** historial en la **página Resumen.**</span><span class="sxs-lookup"><span data-stu-id="9cb70-154">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9cb70-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9cb70-155">Next steps</span></span>

<span data-ttu-id="9cb70-156">Para nuevos incidentes, inicie la [investigación](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="9cb70-156">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="9cb70-157">Para incidentes en el proceso, continúe con la [investigación](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="9cb70-157">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="9cb70-158">Para los incidentes resueltos, realice una [revisión posterior al incidente](first-incident-post.md).</span><span class="sxs-lookup"><span data-stu-id="9cb70-158">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9cb70-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cb70-159">See also</span></span>

- [<span data-ttu-id="9cb70-160">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="9cb70-160">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="9cb70-161">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="9cb70-161">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="9cb70-162">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="9cb70-162">Investigate incidents</span></span>](investigate-incidents.md)
