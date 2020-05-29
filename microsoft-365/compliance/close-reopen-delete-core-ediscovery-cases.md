---
title: Cerrar, volver a abrir y eliminar casos principales de eDiscovery
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
description: En este artículo se describe cómo administrar casos básicos de eDiscovery. Esto incluye cerrar un caso, volver a abrir un caso cerrado y eliminar un caso.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412799"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="4fae2-104">Cerrar, volver a abrir y eliminar un caso de exhibición de documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="4fae2-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="4fae2-105">En este artículo se describe cómo cerrar, volver a abrir y eliminar los casos de eDiscovery principales en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fae2-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="4fae2-106">Cerrar un caso</span><span class="sxs-lookup"><span data-stu-id="4fae2-106">Close a case</span></span>

<span data-ttu-id="4fae2-107">Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición de documentos electrónicos principal, puede cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="4fae2-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="4fae2-108">Esto es lo que sucede cuando se cierra un caso:</span><span class="sxs-lookup"><span data-stu-id="4fae2-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="4fae2-109">Si el caso contiene alguna ubicación de contenido en la suspensión de exhibición de documentos electrónicos, dichas suspensiones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="4fae2-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="4fae2-110">Una vez desactivada la retención, se aplica un período de gracia de 30 días (denominado *retención de retardo*) a las ubicaciones de contenido que se encontraban en suspensión.</span><span class="sxs-lookup"><span data-stu-id="4fae2-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="4fae2-111">Esto ayuda a evitar que el contenido se elimine inmediatamente y proporciona a los administradores la oportunidad de buscar y restaurar el contenido antes de que se elimine de forma permanente después de que expire el período de retención de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4fae2-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="4fae2-112">Para obtener más información, vea [quitar ubicaciones de contenido de una suspensión de exhibición de](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="4fae2-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="4fae2-113">Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="4fae2-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="4fae2-114">Si se colocan otras suspensiones en una ubicación de contenido (como una retención por juicio, una directiva de retención o una retención de un caso de exhibición de documentos electrónicos principal diferente), estas se conservarán.</span><span class="sxs-lookup"><span data-stu-id="4fae2-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="4fae2-115">El caso todavía aparece en la Página principal de eDiscovery del centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fae2-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4fae2-116">Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="4fae2-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="4fae2-117">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="4fae2-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="4fae2-118">Por ejemplo, puede Agregar o quitar miembros, crear búsquedas y exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4fae2-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="4fae2-119">La principal diferencia entre los casos activos y cerrados es que las suspensiones de eDiscovery se desactivan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="4fae2-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="4fae2-120">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="4fae2-120">To close a case:</span></span>
  
1. <span data-ttu-id="4fae2-121">En el centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery**  >  **Core** para mostrar la lista de casos de eDiscovery principales en su organización.</span><span class="sxs-lookup"><span data-stu-id="4fae2-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="4fae2-122">Haga clic en el nombre del caso que desea cerrar.</span><span class="sxs-lookup"><span data-stu-id="4fae2-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="4fae2-123">Se muestra la página flotante **administrar este caso** .</span><span class="sxs-lookup"><span data-stu-id="4fae2-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="4fae2-124">En **administrar estado de caso**, haga clic en **cerrar caso**.</span><span class="sxs-lookup"><span data-stu-id="4fae2-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="4fae2-125">Se muestra una advertencia que indica que las suspensiones asociadas con el caso se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="4fae2-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="4fae2-126">Haga clic en **sí** para cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="4fae2-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="4fae2-127">El estado de la página desplegable **administrar este caso** se cambia de **activo** a **cierre**.</span><span class="sxs-lookup"><span data-stu-id="4fae2-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="4fae2-128">Cierre la página **administrar este caso** .</span><span class="sxs-lookup"><span data-stu-id="4fae2-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="4fae2-129">En la página **principal de eDiscovery** , haga clic en **Actualizar** para actualizar el estado del caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="4fae2-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="4fae2-130">El proceso de cierre puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="4fae2-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="4fae2-131">Una vez finalizado el proceso, el estado del caso cambia a **cerrado** en la página **principal de eDiscovery** .</span><span class="sxs-lookup"><span data-stu-id="4fae2-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="4fae2-132">Vuelva a hacer clic en el nombre del caso para mostrar la página flotante **administrar este caso** , que contiene información sobre cuándo se cerró el caso y quién lo cerró.</span><span class="sxs-lookup"><span data-stu-id="4fae2-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="4fae2-133">Volver a abrir un caso cerrado</span><span class="sxs-lookup"><span data-stu-id="4fae2-133">Reopen a closed case</span></span>

<span data-ttu-id="4fae2-134">Cuando vuelva a abrir un caso, las suspensiones de exhibición de documentos electrónicos que estuvieran en su ubicación cuando se cerró el caso no se restituyerán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4fae2-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="4fae2-135">Después de volver a abrir el caso, tendrá que ir a la página **suspensiones** y activar las suspensiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="4fae2-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="4fae2-136">Para activar una retención, selecciónela para mostrar la página de flotante y, a continuación, establezca el **Estado** en activar como **activado**.</span><span class="sxs-lookup"><span data-stu-id="4fae2-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="4fae2-137">En el centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery**  >  **Core** para mostrar la lista de casos de eDiscovery principales en su organización.</span><span class="sxs-lookup"><span data-stu-id="4fae2-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="4fae2-138">Haga clic en el nombre del caso que desea volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="4fae2-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="4fae2-139">Se muestra la página flotante **administrar este caso** .</span><span class="sxs-lookup"><span data-stu-id="4fae2-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="4fae2-140">En **administrar estado de caso**, haga clic en **volver a abrir el caso**.</span><span class="sxs-lookup"><span data-stu-id="4fae2-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="4fae2-141">Se muestra una advertencia que indica que las suspensiones asociadas con el caso cuando se cerró no se activarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4fae2-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="4fae2-142">Haga clic en **sí** para volver a abrir el caso.</span><span class="sxs-lookup"><span data-stu-id="4fae2-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="4fae2-143">El estado de la página desplegable **administrar este caso** se ha cambiado de **cerrado** a **activo**.</span><span class="sxs-lookup"><span data-stu-id="4fae2-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="4fae2-144">Cierre la página **administrar este caso** .</span><span class="sxs-lookup"><span data-stu-id="4fae2-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="4fae2-145">En la página **principal de eDiscovery** , haga clic en **Actualizar** para actualizar el estado del caso reabierto.</span><span class="sxs-lookup"><span data-stu-id="4fae2-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="4fae2-146">El proceso de reapertura puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="4fae2-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="4fae2-147">Una vez finalizado el proceso, el estado del caso cambia a **activo** en la página **principal de eDiscovery** .</span><span class="sxs-lookup"><span data-stu-id="4fae2-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="4fae2-148">Eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="4fae2-148">Delete a case</span></span>

<span data-ttu-id="4fae2-149">También puede eliminar casos de exhibición de documentos electrónicos principales activos y cerrados.</span><span class="sxs-lookup"><span data-stu-id="4fae2-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="4fae2-150">Al eliminar un caso, se eliminan todas las búsquedas y exportaciones en el caso y se elimina el caso de la lista de casos de la página **principal de eDiscovery** en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fae2-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4fae2-151">No se puede volver a abrir un caso eliminado.</span><span class="sxs-lookup"><span data-stu-id="4fae2-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="4fae2-152">Antes de que pueda eliminar un caso (ya sea activo o cerrado), primero debe eliminar *todas* las suspensiones de eDiscovery asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="4fae2-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="4fae2-153">Esto incluye la eliminación de suspensiones con el estado **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="4fae2-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="4fae2-154">Para eliminar una suspensión de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="4fae2-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="4fae2-155">Vaya a la pestaña **suspensiones** en el caso de que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="4fae2-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="4fae2-156">Haga clic en la suspensión que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="4fae2-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="4fae2-157">En la página flotante, haga clic en **eliminar suspensión**.</span><span class="sxs-lookup"><span data-stu-id="4fae2-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="4fae2-158">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="4fae2-158">To delete a case:</span></span>

1. <span data-ttu-id="4fae2-159">En el centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery**  >  **Core** para mostrar la lista de casos de eDiscovery principales en su organización.</span><span class="sxs-lookup"><span data-stu-id="4fae2-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="4fae2-160">Haga clic en el nombre del caso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="4fae2-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="4fae2-161">En **administrar estado de caso** en la página flotante, haga clic en **eliminar caso**.</span><span class="sxs-lookup"><span data-stu-id="4fae2-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="4fae2-162">Si el caso que está intentando eliminar todavía contiene suspensiones de eDiscovery, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="4fae2-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="4fae2-163">Tendrá que eliminar todas las suspensiones asociadas con el caso y, a continuación, volver a intentar eliminar el caso.</span><span class="sxs-lookup"><span data-stu-id="4fae2-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
