---
title: Administrar incidentes en Protección contra amenazas de Microsoft
description: Obtenga información acerca de cómo asignar, actualizar el estado
keywords: incidente, incidentes, alertas, alertas correlacionadas, asignar, actualizar, estado, administrar, clasificación, microsoft, 365, m365
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f711cc2ff38f15dfd22097e37a1dec42719eb5aa
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148119"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="505e4-104">Administrar incidentes en Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="505e4-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="505e4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="505e4-105">**Applies to:**</span></span>
- <span data-ttu-id="505e4-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="505e4-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="505e4-107">La administración de incidentes es esencial para lidiar con las amenazas y poder contenerlas.</span><span class="sxs-lookup"><span data-stu-id="505e4-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="505e4-108">En Protección contra amenazas de Microsoft, tiene acceso a la administración de incidentes en dispositivos, usuarios y buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="505e4-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="505e4-109">Para administrar los incidentes, seleccione un incidente en la **Cola de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="505e4-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="505e4-110">Puede editar el nombre del incidente, resolverlo, y establecer su clasificación y determinación.</span><span class="sxs-lookup"><span data-stu-id="505e4-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="505e4-111">También puede asignarse el incidente a usted mismo, y agregarle etiquetas o comentarios.</span><span class="sxs-lookup"><span data-stu-id="505e4-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="505e4-112">En los casos en los que, durante la investigación, quiera pasar las alertas de un incidente a otro, también puede hacerlo desde la pestaña Alertas. Así, puede crear un incidente mayor o menor que incluya todas las alertas relevantes.</span><span class="sxs-lookup"><span data-stu-id="505e4-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="505e4-113">Editar el nombre del incidente</span><span class="sxs-lookup"><span data-stu-id="505e4-113">Edit incident name</span></span>
<span data-ttu-id="505e4-114">De forma predeterminada, un incidente tiene asignado un número.</span><span class="sxs-lookup"><span data-stu-id="505e4-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="505e4-115">Puede modificar el nombre del incidente para adecuarlo al sistema de nomenclatura que prefiera.</span><span class="sxs-lookup"><span data-stu-id="505e4-115">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!TIP]
> <span data-ttu-id="505e4-116">Para obtener una visibilidad más rápida, los nombres automáticos de incidentes, actualmente en la versión preliminar pública, generan nombres de incidente basados en atributos de alerta como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="505e4-116">For additional visibility at-a-glance, automatic incident naming, currently in public preview, generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="505e4-117">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="505e4-117">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="505e4-118">Por ejemplo: *incidente de varias fases en varios puntos de conexión que han sido notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="505e4-118">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="505e4-119">Los incidentes que existían antes de la implementación de la asignación automática de nombres de incidentes no tendrán su nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="505e4-119">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>
>
> <span data-ttu-id="505e4-120">Obtenga más información sobre cómo [activar las características de vista previa](preview.md#turn-on-preview-features).</span><span class="sxs-lookup"><span data-stu-id="505e4-120">Learn more about [turning on preview features](preview.md#turn-on-preview-features).</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="505e4-121">Asignar incidentes</span><span class="sxs-lookup"><span data-stu-id="505e4-121">Assign incidents</span></span>
<span data-ttu-id="505e4-122">Si aún no se ha asignado un incidente, puede seleccionar **Asignarme a mí** para asignarse el incidente a usted mismo.</span><span class="sxs-lookup"><span data-stu-id="505e4-122">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="505e4-123">Esta asignación no incluye solo el incidente, sino también todas las alertas asociadas a él.</span><span class="sxs-lookup"><span data-stu-id="505e4-123">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="505e4-124">Establecer estado y clasificación</span><span class="sxs-lookup"><span data-stu-id="505e4-124">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="505e4-125">Estado del incidente</span><span class="sxs-lookup"><span data-stu-id="505e4-125">Incident status</span></span>
<span data-ttu-id="505e4-126">Puede categorizar los incidentes (por ejemplo, como **Activo** o **Resuelto**) cambiando su estado a medida que progresa la investigación.</span><span class="sxs-lookup"><span data-stu-id="505e4-126">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="505e4-127">Esto le ayuda a organizar y administrar la forma en que su equipo puede responder a incidencias.</span><span class="sxs-lookup"><span data-stu-id="505e4-127">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="505e4-128">Por ejemplo, su analista de SOC puede revisar los incidentes de urgencia clasificados como **Activo** durante el día y decidir asignárselos a sí mismo para investigarlos.</span><span class="sxs-lookup"><span data-stu-id="505e4-128">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="505e4-129">O, si el incidente se ha corregido, el analista puede establecerlo como **Resuelto**.</span><span class="sxs-lookup"><span data-stu-id="505e4-129">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="505e4-130">Al resolver un incidente, se cierran automáticamente todas las alertas relacionadas con él que permanecieran abiertas.</span><span class="sxs-lookup"><span data-stu-id="505e4-130">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="505e4-131">Clasificación y determinación</span><span class="sxs-lookup"><span data-stu-id="505e4-131">Classification and determination</span></span>
<span data-ttu-id="505e4-132">Si lo desea, puede decidir no establecer ninguna clasificación o especificar si un incidente es verdadero o falso.</span><span class="sxs-lookup"><span data-stu-id="505e4-132">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="505e4-133">Al hacerlo, su equipo podrá ver los patrones y obtener información.</span><span class="sxs-lookup"><span data-stu-id="505e4-133">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="505e4-134">Agregar comentarios</span><span class="sxs-lookup"><span data-stu-id="505e4-134">Add comments</span></span>
<span data-ttu-id="505e4-135">Puede agregar comentarios y ver eventos históricos de un incidente para comprobar los cambios ya realizados.</span><span class="sxs-lookup"><span data-stu-id="505e4-135">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="505e4-136">Siempre que se realice un cambio o comentario en una alerta, esta se registra en la sección Comentarios e historial.</span><span class="sxs-lookup"><span data-stu-id="505e4-136">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="505e4-137">Los comentarios agregados aparecen al instante en el panel.</span><span class="sxs-lookup"><span data-stu-id="505e4-137">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="505e4-138">Agregar etiquetas de incidente</span><span class="sxs-lookup"><span data-stu-id="505e4-138">Add incident tags</span></span>
<span data-ttu-id="505e4-139">Puede agregar etiquetas personalizadas a un incidente, por ejemplo, para marcar un grupo de incidencias con características comunes.</span><span class="sxs-lookup"><span data-stu-id="505e4-139">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="505e4-140">Posteriormente, puede filtrar la cola de incidentes para ver los incidentes que tengan una etiqueta específica.</span><span class="sxs-lookup"><span data-stu-id="505e4-140">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>