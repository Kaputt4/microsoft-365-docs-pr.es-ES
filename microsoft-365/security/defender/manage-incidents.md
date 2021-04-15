---
title: Administrar incidentes en Microsoft 365 Defender
description: Obtenga información acerca de cómo asignar, actualizar el estado
keywords: incidente, incidentes, alertas, alertas correlacionadas, asignar, actualizar, estado, administrar, clasificación, microsoft, 365, m365
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
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760073"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="62006-104">Administrar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62006-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="62006-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="62006-105">**Applies to:**</span></span>
- <span data-ttu-id="62006-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62006-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="62006-107">La administración de incidentes es fundamental para garantizar que las amenazas se contengan y se aborde.</span><span class="sxs-lookup"><span data-stu-id="62006-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="62006-108">Puede administrar incidentes desde incidentes **& alertas > incidentes** en el inicio rápido del centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="62006-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="62006-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62006-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

<span data-ttu-id="62006-111">Estas son las formas en que puede administrar sus incidentes:</span><span class="sxs-lookup"><span data-stu-id="62006-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="62006-112">Cambiar el nombre del incidente</span><span class="sxs-lookup"><span data-stu-id="62006-112">Change the incident name</span></span>
- <span data-ttu-id="62006-113">Agregar etiquetas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="62006-113">Add incident tags.</span></span>
- <span data-ttu-id="62006-114">Asignar el incidente a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="62006-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="62006-115">Resolverlos</span><span class="sxs-lookup"><span data-stu-id="62006-115">Resolve them</span></span> 
- <span data-ttu-id="62006-116">Establecer su clasificación y determinación</span><span class="sxs-lookup"><span data-stu-id="62006-116">Set its classification and determination</span></span>
- <span data-ttu-id="62006-117">Agregar comentarios.</span><span class="sxs-lookup"><span data-stu-id="62006-117">Add comments.</span></span>

<span data-ttu-id="62006-118">Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente.</span><span class="sxs-lookup"><span data-stu-id="62006-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="62006-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62006-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Ejemplo del panel Administrar incidentes de un incidente":::

<span data-ttu-id="62006-121">Puede mostrar este panel desde el vínculo **Administrar incidentes** en:</span><span class="sxs-lookup"><span data-stu-id="62006-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="62006-122">Panel de propiedades de un incidente en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="62006-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="62006-123">**Página de** resumen de un incidente.</span><span class="sxs-lookup"><span data-stu-id="62006-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="62006-124">En los casos en los que, al investigar, quieras mover alertas de un incidente a otro, también puedes hacerlo desde la pestaña Alertas, creando así un incidente mayor o menor que incluya todas las alertas relevantes. </span><span class="sxs-lookup"><span data-stu-id="62006-124">In cases where, while investigating you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="62006-125">Editar el nombre del incidente</span><span class="sxs-lookup"><span data-stu-id="62006-125">Edit the incident name</span></span>

<span data-ttu-id="62006-126">A los incidentes se les asigna automáticamente un nombre en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="62006-126">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="62006-127">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="62006-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="62006-128">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="62006-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="62006-129">Puede editar el nombre del incidente desde el campo **Nombre del** incidente en el **panel Administrar** incidente.</span><span class="sxs-lookup"><span data-stu-id="62006-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="62006-130">Los incidentes que existían antes de la implementación de la característica de nomenclatura automática de incidentes conservarán su nombre.</span><span class="sxs-lookup"><span data-stu-id="62006-130">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="62006-131">Agregar etiquetas de incidente</span><span class="sxs-lookup"><span data-stu-id="62006-131">Add incident tags</span></span>

<span data-ttu-id="62006-132">Puede agregar etiquetas personalizadas a un incidente, por ejemplo, para marcar un grupo de incidentes con una característica común.</span><span class="sxs-lookup"><span data-stu-id="62006-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="62006-133">Más adelante, puede filtrar la cola de incidentes para todos los incidentes que contengan una etiqueta específica.</span><span class="sxs-lookup"><span data-stu-id="62006-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="62006-134">Al empezar a escribir, tiene la opción de seleccionar de una lista de etiquetas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="62006-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="62006-135">Asignar incidentes</span><span class="sxs-lookup"><span data-stu-id="62006-135">Assign incidents</span></span>

<span data-ttu-id="62006-136">Si aún no se ha asignado un incidente, puede seleccionar **Asignar a** y especificar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="62006-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="62006-137">Al hacerlo, se asigna la propiedad del incidente y todas las alertas asociadas con él.</span><span class="sxs-lookup"><span data-stu-id="62006-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="62006-138">Resolver incidente</span><span class="sxs-lookup"><span data-stu-id="62006-138">Resolve incident</span></span>

<span data-ttu-id="62006-139">Si el incidente se ha corregido, seleccione **Resolver incidente** para mover la alternancia a la derecha.</span><span class="sxs-lookup"><span data-stu-id="62006-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="62006-140">Tenga en cuenta que la resolución de un incidente también resuelve todas las alertas vinculadas y activas relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="62006-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="62006-141">Un incidente que no se resuelve se muestra como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="62006-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="62006-142">Establecer la clasificación y la determinación</span><span class="sxs-lookup"><span data-stu-id="62006-142">Set the classification and determination</span></span>

<span data-ttu-id="62006-143">La clasificación de incidentes es si se trata de una alerta verdadera o una alerta falsa, que se configura desde el **campo Clasificación.**</span><span class="sxs-lookup"><span data-stu-id="62006-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="62006-144">Si se trataba de una alerta verdadera, también debe especificar qué tipo de amenaza era con el **campo Determinación.**</span><span class="sxs-lookup"><span data-stu-id="62006-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="62006-145">Especificar el tipo de amenaza ayuda a su equipo de seguridad a ver patrones de amenazas y actuar para defender su organización de ellos.</span><span class="sxs-lookup"><span data-stu-id="62006-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="62006-146">Agregar comentarios</span><span class="sxs-lookup"><span data-stu-id="62006-146">Add comments</span></span>

<span data-ttu-id="62006-147">Puede agregar varios comentarios a un incidente con el **campo Comentario.**</span><span class="sxs-lookup"><span data-stu-id="62006-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="62006-148">Cada comentario se agrega a los eventos históricos del incidente.</span><span class="sxs-lookup"><span data-stu-id="62006-148">Each comment is added to the historical events of the incident.</span></span> <span data-ttu-id="62006-149">Puede ver los comentarios y el historial de un incidente desde el vínculo **Comentarios e** historial en la **página Resumen.**</span><span class="sxs-lookup"><span data-stu-id="62006-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>
