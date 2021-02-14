---
title: Cerrar, volver a abrir y eliminar casos principales de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo administrar los casos principales de eDiscovery. Esto incluye cerrar un caso, volver a abrir un caso cerrado y eliminar un caso.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412799"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="ee07b-104">Cerrar, volver a abrir y eliminar un caso de eDiscovery principal</span><span class="sxs-lookup"><span data-stu-id="ee07b-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="ee07b-105">En este artículo se describe cómo cerrar, volver a abrir y eliminar los casos principales de eDiscovery en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee07b-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="ee07b-106">Cerrar un caso</span><span class="sxs-lookup"><span data-stu-id="ee07b-106">Close a case</span></span>

<span data-ttu-id="ee07b-107">Cuando se complete el caso legal o la investigación compatible con un caso de exhibición de documentos electrónicos principal, puede cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="ee07b-108">Esto es lo que sucede al cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="ee07b-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="ee07b-109">Si el caso contiene ubicaciones de contenido en retención de exhibición de documentos electrónicos, dichas retenciones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="ee07b-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="ee07b-110">Después de desactivar la retención, se aplica un período de gracia de 30 días (denominado retención retrasada) a las ubicaciones de contenido que estaban en espera.</span><span class="sxs-lookup"><span data-stu-id="ee07b-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="ee07b-111">Esto ayuda a evitar que el contenido se elimine inmediatamente y proporciona a los administradores la oportunidad de buscar y restaurar contenido antes de que se elimine de forma permanente después de que expire el período de retención de retraso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="ee07b-112">Para obtener más información, vea [Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="ee07b-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="ee07b-113">Cerrar un caso solo desactiva las retenciones asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="ee07b-114">Si se colocan otras retenciones en una ubicación de contenido (como una retención por juicio, una directiva de retención o una suspensión de otro caso de exhibición de documentos electrónicos principal), dichas retenciones se seguirán conservando.</span><span class="sxs-lookup"><span data-stu-id="ee07b-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="ee07b-115">El caso aún aparece en la página de exhibición de documentos electrónicos principal en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee07b-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ee07b-116">Se conservan los detalles, las retenciones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="ee07b-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="ee07b-117">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="ee07b-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="ee07b-118">Por ejemplo, puede agregar o quitar miembros, crear búsquedas y exportar resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ee07b-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="ee07b-119">La principal diferencia entre los casos activos y cerrados es que las retenciones de exhibición de documentos electrónicos se apagan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="ee07b-120">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="ee07b-120">To close a case:</span></span>
  
1. <span data-ttu-id="ee07b-121">En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de  >   eDiscovery en su organización.</span><span class="sxs-lookup"><span data-stu-id="ee07b-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="ee07b-122">Haga clic en el nombre del caso que desea cerrar.</span><span class="sxs-lookup"><span data-stu-id="ee07b-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="ee07b-123">Se **muestra la página desplegable** Administrar este caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="ee07b-124">En **Administrar estado de caso,** haga clic en Cerrar **caso.**</span><span class="sxs-lookup"><span data-stu-id="ee07b-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="ee07b-125">Se muestra una advertencia que dice que se desactivarán las retenciones asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="ee07b-126">Haga **clic en Sí** para cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="ee07b-127">El estado de la **página de** control desplegable Administrar este caso cambia **de Activo** a **Cierre.**</span><span class="sxs-lookup"><span data-stu-id="ee07b-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="ee07b-128">Cierre la **página Administrar este caso.**</span><span class="sxs-lookup"><span data-stu-id="ee07b-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="ee07b-129">En la **página eDiscovery principal,** haga clic **en Actualizar** para actualizar el estado del caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="ee07b-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="ee07b-130">El proceso de cierre puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="ee07b-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="ee07b-131">Una vez completado el proceso, el estado del caso cambia a **Cerrado** en la **página de eDiscovery** principal.</span><span class="sxs-lookup"><span data-stu-id="ee07b-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="ee07b-132">Vuelva a hacer clic en  el nombre del caso para mostrar la página desplegable Administrar este caso, que contiene información sobre cuándo se cerró el caso y quién lo cerró.</span><span class="sxs-lookup"><span data-stu-id="ee07b-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="ee07b-133">Volver a abrir un caso cerrado</span><span class="sxs-lookup"><span data-stu-id="ee07b-133">Reopen a closed case</span></span>

<span data-ttu-id="ee07b-134">Al volver a abrir un caso, las retenciones de exhibición de documentos electrónicos que estaban en su lugar cuando se cerró el caso no se restablecerán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ee07b-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="ee07b-135">Una vez que se vuelva a abrir el caso, tendrá que ir a la página **Retenciones** y activar las retenciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="ee07b-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="ee07b-136">Para activar una retención, selecciónelo para mostrar la página desplegable y, a continuación, establezca el botón de **alternancia** estado en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="ee07b-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="ee07b-137">En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de  >   eDiscovery en su organización.</span><span class="sxs-lookup"><span data-stu-id="ee07b-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="ee07b-138">Haga clic en el nombre del caso que desea volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="ee07b-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="ee07b-139">Se **muestra la página desplegable** Administrar este caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="ee07b-140">En **Administrar estado de caso,** haga clic en Volver a abrir **caso.**</span><span class="sxs-lookup"><span data-stu-id="ee07b-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="ee07b-141">Se muestra una advertencia que dice que las retenciones asociadas con el caso cuando se cerró no se activarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ee07b-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="ee07b-142">Haga **clic en Sí** para volver a abrir el caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="ee07b-143">El estado de la **página de** control desplegable Administrar este caso se cambia **de Cerrado** a **Activo.**</span><span class="sxs-lookup"><span data-stu-id="ee07b-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="ee07b-144">Cierre la **página Administrar este caso.**</span><span class="sxs-lookup"><span data-stu-id="ee07b-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="ee07b-145">En la **página eDiscovery principal,** haga clic **en Actualizar** para actualizar el estado del caso reabrido.</span><span class="sxs-lookup"><span data-stu-id="ee07b-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="ee07b-146">El proceso de reabrimiento puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="ee07b-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="ee07b-147">Una vez completado el proceso, el estado del caso cambia a **Activo** en la **página de exhibición** de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="ee07b-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="ee07b-148">Eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="ee07b-148">Delete a case</span></span>

<span data-ttu-id="ee07b-149">También puede eliminar los casos de eDiscovery principales activos y cerrados.</span><span class="sxs-lookup"><span data-stu-id="ee07b-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="ee07b-150">Al eliminar un caso, se eliminan todas las búsquedas y exportaciones del caso y el caso se quita de la lista de casos en la página **eDiscovery** principal del Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee07b-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ee07b-151">No puede volver a abrir un caso eliminado.</span><span class="sxs-lookup"><span data-stu-id="ee07b-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="ee07b-152">Para poder eliminar un caso (ya sea activo o cerrado), primero debe eliminar todas las retenciones de *exhibición* de documentos electrónicos asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="ee07b-153">Esto incluye la eliminación de retenciones con el estado **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="ee07b-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="ee07b-154">Para eliminar una retención de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="ee07b-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="ee07b-155">Vaya a **la pestaña Retenciones** en caso de que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="ee07b-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="ee07b-156">Haga clic en la retención que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ee07b-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="ee07b-157">En la página desplegable, haga clic **en Eliminar retención.**</span><span class="sxs-lookup"><span data-stu-id="ee07b-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="ee07b-158">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="ee07b-158">To delete a case:</span></span>

1. <span data-ttu-id="ee07b-159">En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de  >   eDiscovery en su organización.</span><span class="sxs-lookup"><span data-stu-id="ee07b-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="ee07b-160">Haga clic en el nombre del caso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ee07b-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="ee07b-161">En **Administrar estado de caso** en la página desplegable, haga clic en Eliminar **caso.**</span><span class="sxs-lookup"><span data-stu-id="ee07b-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="ee07b-162">Si el caso que intenta eliminar aún contiene retenciones de exhibición de documentos electrónicos, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ee07b-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="ee07b-163">Tendrá que eliminar todas las retenciones asociadas al caso y, a continuación, volver a intentar eliminar el caso.</span><span class="sxs-lookup"><span data-stu-id="ee07b-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
