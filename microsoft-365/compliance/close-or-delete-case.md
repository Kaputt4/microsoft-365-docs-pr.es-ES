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
description: Obtenga información sobre lo que sucede cuando se cierra o elimina una investigación o un caso legal compatible con un caso de eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419066"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="ee78c-103">Cerrar o eliminar un caso de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="ee78c-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="ee78c-104">Cuando se complete el caso legal o la investigación compatible con un caso de eDiscovery avanzado, puede cerrar o eliminar un caso.</span><span class="sxs-lookup"><span data-stu-id="ee78c-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="ee78c-105">También puede volver a abrir un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="ee78c-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="ee78c-106">Cerrar un caso</span><span class="sxs-lookup"><span data-stu-id="ee78c-106">Close a case</span></span>

<span data-ttu-id="ee78c-107">Esto es lo que sucede cuando cierra un caso de eDiscovery avanzado:</span><span class="sxs-lookup"><span data-stu-id="ee78c-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="ee78c-108">Si el caso contiene alguna ubicación de contenido en espera, dichas retenciones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="ee78c-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="ee78c-109">Después de desactivar la retención, se aplica un período de gracia de 30 días (denominado retención retrasada) a las ubicaciones de contenido que estaban en espera.</span><span class="sxs-lookup"><span data-stu-id="ee78c-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="ee78c-110">Esto ayuda a evitar que el contenido se elimine inmediatamente y ofrece a los administradores la oportunidad de buscar o recuperar contenido que se eliminará permanentemente después de que expire el período de retención de retraso.</span><span class="sxs-lookup"><span data-stu-id="ee78c-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="ee78c-111">Para obtener más información, vea [Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="ee78c-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="ee78c-112">Cerrar un caso solo desactiva las retenciones asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="ee78c-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="ee78c-113">Si otras retenciones se encuentran en una ubicación de contenido (como una retención por juicio, una suspensión de eDiscovery principal o una retención de otro caso de eDiscovery avanzado), dichas retenciones se seguirán conservando.</span><span class="sxs-lookup"><span data-stu-id="ee78c-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="ee78c-114">El caso aún aparece en la página de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee78c-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ee78c-115">Se conservan los detalles, las retenciones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="ee78c-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="ee78c-116">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="ee78c-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="ee78c-117">Por ejemplo, puede agregar o quitar miembros, crear búsquedas, exportar resultados de búsqueda y preparar los resultados de búsqueda para el análisis en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="ee78c-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="ee78c-118">La principal diferencia entre los casos activos y cerrados es que las retenciones se apagan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="ee78c-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="ee78c-119">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="ee78c-119">To close a case:</span></span>

1. <span data-ttu-id="ee78c-120">En la **página eDiscovery avanzado,** seleccione el caso que desea cerrar.</span><span class="sxs-lookup"><span data-stu-id="ee78c-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="ee78c-121">En la **pestaña Configuración,** en Información **de casos**, haga clic **en Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="ee78c-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="ee78c-122">Haga clic **en Cerrar caso.**</span><span class="sxs-lookup"><span data-stu-id="ee78c-122">Click **Close case**.</span></span>

   <span data-ttu-id="ee78c-123">El proceso de cierre puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="ee78c-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="ee78c-124">Volver a abrir un caso cerrado</span><span class="sxs-lookup"><span data-stu-id="ee78c-124">Reopen a closed case</span></span>

<span data-ttu-id="ee78c-125">Al volver a abrir un caso de eDiscovery avanzado, las retenciones que estaban en su lugar cuando se cerró el caso no se restablecerán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ee78c-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="ee78c-126">Una vez que se vuelva a abrir el caso, tendrá que ir a la pestaña **Retenciones** y activar las retenciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="ee78c-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="ee78c-127">Para activar una retención, selecciónelo para mostrar la página desplegable y, a continuación, establezca el botón de alternancia de **estado** en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="ee78c-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="ee78c-128">Para volver a abrir un caso cerrado:</span><span class="sxs-lookup"><span data-stu-id="ee78c-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="ee78c-129">En la **página eDiscovery avanzado,** seleccione el caso que desea volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="ee78c-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="ee78c-130">En la **pestaña Configuración,** en Información **de** casos , haga clic **en Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="ee78c-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="ee78c-131">Haga clic **en Volver a abrir caso.**</span><span class="sxs-lookup"><span data-stu-id="ee78c-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="ee78c-132">El proceso de reabrimiento puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="ee78c-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="ee78c-133">Eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="ee78c-133">Delete a case</span></span>

<span data-ttu-id="ee78c-134">Puede eliminar los casos activos y cerrados de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="ee78c-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="ee78c-135">Al eliminar un caso, se eliminan todos los componentes asociados con el caso, como la lista de administradores, las comunicaciones, las búsquedas, los conjuntos de revisión y el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="ee78c-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="ee78c-136">El caso se quita de la lista de casos de la página **eDiscovery** avanzado en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee78c-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ee78c-137">No puede recuperar ni volver a abrir un caso eliminado.</span><span class="sxs-lookup"><span data-stu-id="ee78c-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="ee78c-138">En escenarios de pérdida de datos, la única forma de quitar elementos de un conjunto de revisión es eliminar el caso de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="ee78c-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="ee78c-139">Otros métodos de "búsqueda y depuración" no quitan elementos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="ee78c-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="ee78c-140">Para poder eliminar un caso (ya sea activo o  cerrado), primero debe eliminar todas las retenciones asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="ee78c-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="ee78c-141">Esto incluye la eliminación de retenciones con el estado **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="ee78c-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="ee78c-142">Para eliminar retenciones asociadas a un caso:</span><span class="sxs-lookup"><span data-stu-id="ee78c-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="ee78c-143">Vaya a **la pestaña Retenciones** en el caso de eDiscovery avanzado que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ee78c-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="ee78c-144">Haga clic en la retención que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ee78c-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="ee78c-145">En la página desplegable, haga clic **en Eliminar retención.**</span><span class="sxs-lookup"><span data-stu-id="ee78c-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="ee78c-146">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="ee78c-146">To delete a case:</span></span>

1. <span data-ttu-id="ee78c-147">En la **página eDiscovery avanzado,** seleccione el caso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ee78c-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="ee78c-148">En la **pestaña Configuración,** en Información **de casos**, haga clic **en Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="ee78c-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="ee78c-149">Haga clic **en Eliminar caso.**</span><span class="sxs-lookup"><span data-stu-id="ee78c-149">Click **Delete case**.</span></span>
