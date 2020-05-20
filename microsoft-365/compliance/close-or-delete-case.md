---
title: Cerrar o eliminar un caso
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre qué ocurre cuando se cierra o se elimina una investigación o un caso legal admitido por un caso avanzado de eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292416"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="21afa-103">Cerrar o eliminar un caso de exhibición avanzada de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="21afa-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="21afa-104">Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición avanzada de documentos electrónicos, puede cerrar o eliminar un caso.</span><span class="sxs-lookup"><span data-stu-id="21afa-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="21afa-105">También puede volver a abrir un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="21afa-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="21afa-106">Cerrar un caso</span><span class="sxs-lookup"><span data-stu-id="21afa-106">Close a case</span></span>

<span data-ttu-id="21afa-107">Esto es lo que sucede cuando cierra un caso de exhibición avanzada de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="21afa-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="21afa-108">Si el caso contiene ubicaciones de contenido en suspensión, dichas suspensiones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="21afa-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="21afa-109">Esto puede dar lugar a que el usuario o un proceso automatizado eliminen o purguen permanentemente el contenido, como una directiva de eliminación.</span><span class="sxs-lookup"><span data-stu-id="21afa-109">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="21afa-110">Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="21afa-110">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="21afa-111">Si otras retenciones se colocan en una ubicación de contenido (como una retención por juicio, una suspensión de exhibición de documentos electrónicos principal o una retención de un caso de eDiscovery avanzado diferente), estas se conservarán.</span><span class="sxs-lookup"><span data-stu-id="21afa-111">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="21afa-112">El caso sigue apareciendo en la página de exhibición de documentos electrónicos del centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21afa-112">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="21afa-113">Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="21afa-113">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="21afa-114">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="21afa-114">You can edit a case after it's closed.</span></span> <span data-ttu-id="21afa-115">Por ejemplo, puede Agregar o quitar miembros, crear búsquedas, exportar los resultados de la búsqueda y preparar los resultados de la búsqueda para analizarlos en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="21afa-115">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="21afa-116">La principal diferencia entre los casos activos y cerrados es que las suspensiones se desactivan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="21afa-116">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="21afa-117">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="21afa-117">To close a case:</span></span>

1. <span data-ttu-id="21afa-118">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera cerrar.</span><span class="sxs-lookup"><span data-stu-id="21afa-118">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="21afa-119">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="21afa-119">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="21afa-120">Haga clic en **cerrar caso**.</span><span class="sxs-lookup"><span data-stu-id="21afa-120">Click **Close case**.</span></span>

   <span data-ttu-id="21afa-121">El proceso de cierre puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="21afa-121">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="21afa-122">Volver a abrir un caso cerrado</span><span class="sxs-lookup"><span data-stu-id="21afa-122">Reopen a closed case</span></span>

<span data-ttu-id="21afa-123">Cuando vuelve a abrir un caso de exhibición avanzada de documentos electrónicos, las suspensiones que estuvieran en su ubicación cuando se cerró el caso no se restituyerán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="21afa-123">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="21afa-124">Después de volver a abrir el caso, tendrá que ir a la pestaña **suspensiones** y activar las suspensiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="21afa-124">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="21afa-125">Para activar una retención, selecciónela para mostrar la página de flotante y, a continuación, establezca el **Estado** en activar como **activado**.</span><span class="sxs-lookup"><span data-stu-id="21afa-125">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="21afa-126">Para volver a abrir un caso cerrado:</span><span class="sxs-lookup"><span data-stu-id="21afa-126">To reopen a closed case:</span></span>

1. <span data-ttu-id="21afa-127">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="21afa-127">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="21afa-128">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="21afa-128">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="21afa-129">Haga clic en **volver a abrir el caso**.</span><span class="sxs-lookup"><span data-stu-id="21afa-129">Click **Reopen case**.</span></span>

   <span data-ttu-id="21afa-130">El proceso de reapertura puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="21afa-130">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="21afa-131">Eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="21afa-131">Delete a case</span></span>

<span data-ttu-id="21afa-132">Puede eliminar tanto los casos de eDiscovery avanzado activos como los cerrados.</span><span class="sxs-lookup"><span data-stu-id="21afa-132">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="21afa-133">Al eliminar un caso, se eliminan todos los componentes asociados con el caso, como la lista de custodios, las comunicaciones, las búsquedas, los conjuntos de revisión y el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="21afa-133">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="21afa-134">El caso se elimina de la lista de casos de la página **exhibición avanzada** de documentos electrónicos en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21afa-134">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="21afa-135">No se puede recuperar ni volver a abrir un caso eliminado.</span><span class="sxs-lookup"><span data-stu-id="21afa-135">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="21afa-136">En los escenarios de derrames de datos, la única forma de quitar elementos de un conjunto de revisiones es eliminar el caso de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="21afa-136">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="21afa-137">Otros métodos de "búsqueda y depuración" no quitan elementos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="21afa-137">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="21afa-138">Antes de que pueda eliminar un caso (ya sea activo o cerrado), primero debe eliminar *todas las* suspensiones asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="21afa-138">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="21afa-139">Esto incluye la eliminación de suspensiones con el estado **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="21afa-139">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="21afa-140">Para eliminar suspensiones asociadas a un caso:</span><span class="sxs-lookup"><span data-stu-id="21afa-140">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="21afa-141">Vaya a la pestaña **suspensiones** en el caso de eDiscovery avanzado que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="21afa-141">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="21afa-142">Haga clic en la suspensión que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="21afa-142">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="21afa-143">En la página flotante, haga clic en **eliminar suspensión**.</span><span class="sxs-lookup"><span data-stu-id="21afa-143">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="21afa-144">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="21afa-144">To delete a case:</span></span>

1. <span data-ttu-id="21afa-145">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="21afa-145">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="21afa-146">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="21afa-146">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="21afa-147">Haga clic en **eliminar caso**.</span><span class="sxs-lookup"><span data-stu-id="21afa-147">Click **Delete case**.</span></span>
