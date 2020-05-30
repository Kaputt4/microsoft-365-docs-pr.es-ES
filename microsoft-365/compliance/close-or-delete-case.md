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
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419066"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="5fc4d-103">Cerrar o eliminar un caso de exhibición avanzada de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="5fc4d-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="5fc4d-104">Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición avanzada de documentos electrónicos, puede cerrar o eliminar un caso.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="5fc4d-105">También puede volver a abrir un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="5fc4d-106">Cerrar un caso</span><span class="sxs-lookup"><span data-stu-id="5fc4d-106">Close a case</span></span>

<span data-ttu-id="5fc4d-107">Esto es lo que sucede cuando cierra un caso de exhibición avanzada de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="5fc4d-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="5fc4d-108">Si el caso contiene ubicaciones de contenido en suspensión, dichas suspensiones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="5fc4d-109">Una vez desactivada la retención, se aplica un período de gracia de 30 días (denominado *retención de retardo*) a las ubicaciones de contenido que se encontraban en suspensión.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="5fc4d-110">Esto ayuda a evitar que el contenido se elimine inmediatamente y le da a los administradores la oportunidad de buscar o recuperar contenido que se eliminará permanentemente después de que expire el período de retención de tiempo.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="5fc4d-111">Para obtener más información, vea [quitar ubicaciones de contenido de una suspensión de exhibición de](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="5fc4d-112">Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="5fc4d-113">Si otras retenciones se colocan en una ubicación de contenido (como una retención por juicio, una suspensión de exhibición de documentos electrónicos principal o una retención de un caso de eDiscovery avanzado diferente), estas se conservarán.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="5fc4d-114">El caso sigue apareciendo en la página de exhibición de documentos electrónicos del centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5fc4d-115">Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="5fc4d-116">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="5fc4d-117">Por ejemplo, puede Agregar o quitar miembros, crear búsquedas, exportar los resultados de la búsqueda y preparar los resultados de la búsqueda para analizarlos en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="5fc4d-118">La principal diferencia entre los casos activos y cerrados es que las suspensiones se desactivan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="5fc4d-119">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="5fc4d-119">To close a case:</span></span>

1. <span data-ttu-id="5fc4d-120">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera cerrar.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="5fc4d-121">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="5fc4d-122">Haga clic en **cerrar caso**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-122">Click **Close case**.</span></span>

   <span data-ttu-id="5fc4d-123">El proceso de cierre puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="5fc4d-124">Volver a abrir un caso cerrado</span><span class="sxs-lookup"><span data-stu-id="5fc4d-124">Reopen a closed case</span></span>

<span data-ttu-id="5fc4d-125">Cuando vuelve a abrir un caso de exhibición avanzada de documentos electrónicos, las suspensiones que estuvieran en su ubicación cuando se cerró el caso no se restituyerán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="5fc4d-126">Después de volver a abrir el caso, tendrá que ir a la pestaña **suspensiones** y activar las suspensiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="5fc4d-127">Para activar una retención, selecciónela para mostrar la página de flotante y, a continuación, establezca el **Estado** en activar como **activado**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="5fc4d-128">Para volver a abrir un caso cerrado:</span><span class="sxs-lookup"><span data-stu-id="5fc4d-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="5fc4d-129">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="5fc4d-130">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="5fc4d-131">Haga clic en **volver a abrir el caso**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="5fc4d-132">El proceso de reapertura puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="5fc4d-133">Eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="5fc4d-133">Delete a case</span></span>

<span data-ttu-id="5fc4d-134">Puede eliminar tanto los casos de eDiscovery avanzado activos como los cerrados.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="5fc4d-135">Al eliminar un caso, se eliminan todos los componentes asociados con el caso, como la lista de custodios, las comunicaciones, las búsquedas, los conjuntos de revisión y el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="5fc4d-136">El caso se elimina de la lista de casos de la página **exhibición avanzada** de documentos electrónicos en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5fc4d-137">No se puede recuperar ni volver a abrir un caso eliminado.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="5fc4d-138">En los escenarios de derrames de datos, la única forma de quitar elementos de un conjunto de revisiones es eliminar el caso de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="5fc4d-139">Otros métodos de "búsqueda y depuración" no quitan elementos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="5fc4d-140">Antes de que pueda eliminar un caso (ya sea activo o cerrado), primero debe eliminar *todas las* suspensiones asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="5fc4d-141">Esto incluye la eliminación de suspensiones con el estado **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="5fc4d-142">Para eliminar suspensiones asociadas a un caso:</span><span class="sxs-lookup"><span data-stu-id="5fc4d-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="5fc4d-143">Vaya a la pestaña **suspensiones** en el caso de eDiscovery avanzado que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="5fc4d-144">Haga clic en la suspensión que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="5fc4d-145">En la página flotante, haga clic en **eliminar suspensión**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="5fc4d-146">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="5fc4d-146">To delete a case:</span></span>

1. <span data-ttu-id="5fc4d-147">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="5fc4d-148">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="5fc4d-149">Haga clic en **eliminar caso**.</span><span class="sxs-lookup"><span data-stu-id="5fc4d-149">Click **Delete case**.</span></span>
