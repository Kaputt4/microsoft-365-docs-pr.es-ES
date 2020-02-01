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
ms.openlocfilehash: 46904323a1ec8f969355931f8b69a3ed0ebf4519
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600217"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="fce98-104">Administrar incidentes en Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fce98-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="fce98-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="fce98-105">**Applies to:**</span></span>
- <span data-ttu-id="fce98-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fce98-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="fce98-107">La administración de incidentes es esencial para lidiar con las amenazas y poder contenerlas.</span><span class="sxs-lookup"><span data-stu-id="fce98-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="fce98-108">En Protección contra amenazas de Microsoft, tiene acceso a la administración de incidentes en dispositivos, usuarios y buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="fce98-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="fce98-109">Para administrar los incidentes, seleccione un incidente en la **Cola de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="fce98-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="fce98-110">Puede editar el nombre del incidente, resolverlo, y establecer su clasificación y determinación.</span><span class="sxs-lookup"><span data-stu-id="fce98-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="fce98-111">También puede asignarse el incidente a usted mismo, y agregarle etiquetas o comentarios.</span><span class="sxs-lookup"><span data-stu-id="fce98-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="fce98-112">En los casos en los que, durante la investigación, quiera pasar las alertas de un incidente a otro, también puede hacerlo desde la pestaña Alertas. Así, puede crear un incidente mayor o menor que incluya todas las alertas relevantes.</span><span class="sxs-lookup"><span data-stu-id="fce98-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="fce98-113">Editar el nombre del incidente</span><span class="sxs-lookup"><span data-stu-id="fce98-113">Edit incident name</span></span>
<span data-ttu-id="fce98-114">De forma predeterminada, un incidente tiene asignado un número.</span><span class="sxs-lookup"><span data-stu-id="fce98-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="fce98-115">Puede modificar el nombre del incidente para adecuarlo al sistema de nomenclatura que prefiera.</span><span class="sxs-lookup"><span data-stu-id="fce98-115">You can modify the incident name to better align with your preferred naming convention.</span></span>
 
## <a name="assign-incidents"></a><span data-ttu-id="fce98-116">Asignar incidentes</span><span class="sxs-lookup"><span data-stu-id="fce98-116">Assign incidents</span></span>
<span data-ttu-id="fce98-117">Si aún no se ha asignado un incidente, puede seleccionar **Asignarme a mí** para asignarse el incidente a usted mismo.</span><span class="sxs-lookup"><span data-stu-id="fce98-117">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="fce98-118">Esta asignación no incluye solo el incidente, sino también todas las alertas asociadas a él.</span><span class="sxs-lookup"><span data-stu-id="fce98-118">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="fce98-119">Establecer estado y clasificación</span><span class="sxs-lookup"><span data-stu-id="fce98-119">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="fce98-120">Estado del incidente</span><span class="sxs-lookup"><span data-stu-id="fce98-120">Incident status</span></span>
<span data-ttu-id="fce98-121">Puede categorizar los incidentes (por ejemplo, como **Activo** o **Resuelto**) cambiando su estado a medida que progresa la investigación.</span><span class="sxs-lookup"><span data-stu-id="fce98-121">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="fce98-122">Esto le ayuda a organizar y administrar la forma en que su equipo puede responder a incidencias.</span><span class="sxs-lookup"><span data-stu-id="fce98-122">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="fce98-123">Por ejemplo, su analista de SOC puede revisar los incidentes de urgencia clasificados como **Activo** durante el día y decidir asignárselos a sí mismo para investigarlos.</span><span class="sxs-lookup"><span data-stu-id="fce98-123">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="fce98-124">O, si el incidente se ha corregido, el analista puede establecerlo como **Resuelto**.</span><span class="sxs-lookup"><span data-stu-id="fce98-124">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="fce98-125">Al resolver un incidente, se cierran automáticamente todas las alertas relacionadas con él que permanecieran abiertas.</span><span class="sxs-lookup"><span data-stu-id="fce98-125">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="fce98-126">Clasificación y determinación</span><span class="sxs-lookup"><span data-stu-id="fce98-126">Classification and determination</span></span>
<span data-ttu-id="fce98-127">Si lo desea, puede decidir no establecer ninguna clasificación o especificar si un incidente es verdadero o falso.</span><span class="sxs-lookup"><span data-stu-id="fce98-127">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="fce98-128">Al hacerlo, su equipo podrá ver los patrones y obtener información.</span><span class="sxs-lookup"><span data-stu-id="fce98-128">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="fce98-129">Agregar comentarios</span><span class="sxs-lookup"><span data-stu-id="fce98-129">Add comments</span></span>
<span data-ttu-id="fce98-130">Puede agregar comentarios y ver eventos históricos de un incidente para comprobar los cambios ya realizados.</span><span class="sxs-lookup"><span data-stu-id="fce98-130">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="fce98-131">Siempre que se realice un cambio o comentario en una alerta, esta se registra en la sección Comentarios e historial.</span><span class="sxs-lookup"><span data-stu-id="fce98-131">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="fce98-132">Los comentarios agregados aparecen al instante en el panel.</span><span class="sxs-lookup"><span data-stu-id="fce98-132">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="fce98-133">Agregar etiquetas de incidente</span><span class="sxs-lookup"><span data-stu-id="fce98-133">Add incident tags</span></span>
<span data-ttu-id="fce98-134">Puede agregar etiquetas personalizadas a un incidente, por ejemplo, para marcar un grupo de incidencias con características comunes.</span><span class="sxs-lookup"><span data-stu-id="fce98-134">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="fce98-135">Posteriormente, puede filtrar la cola de incidentes para ver los incidentes que tengan una etiqueta específica.</span><span class="sxs-lookup"><span data-stu-id="fce98-135">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>

