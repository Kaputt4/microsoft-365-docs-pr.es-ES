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
ms.openlocfilehash: 41ba622a58b0abb5ce668e6d94d89b1694a328c9
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551480"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="cfe01-104">Cerrar, volver a abrir y eliminar un caso de exhibición de documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="cfe01-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="cfe01-105">En este artículo se describe cómo cerrar, volver a abrir y eliminar los casos de eDiscovery principales en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfe01-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="cfe01-106">Cerrar un caso</span><span class="sxs-lookup"><span data-stu-id="cfe01-106">Close a case</span></span>

<span data-ttu-id="cfe01-107">Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición de documentos electrónicos principal, puede cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="cfe01-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="cfe01-108">Esto es lo que sucede cuando se cierra un caso:</span><span class="sxs-lookup"><span data-stu-id="cfe01-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="cfe01-109">Si el caso contiene alguna ubicación de contenido en la suspensión de exhibición de documentos electrónicos, dichas suspensiones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="cfe01-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="cfe01-110">Esto puede dar lugar a que el usuario o un proceso automatizado eliminen o purguen permanentemente el contenido, como una directiva de eliminación.</span><span class="sxs-lookup"><span data-stu-id="cfe01-110">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="cfe01-111">Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="cfe01-111">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="cfe01-112">Si se colocan otras suspensiones en una ubicación de contenido (como una retención por juicio, una directiva de retención o una retención de un caso de exhibición de documentos electrónicos principal diferente), estas se conservarán.</span><span class="sxs-lookup"><span data-stu-id="cfe01-112">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="cfe01-113">El caso todavía aparece en la Página principal de eDiscovery del centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfe01-113">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="cfe01-114">Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="cfe01-114">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="cfe01-115">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="cfe01-115">You can edit a case after it's closed.</span></span> <span data-ttu-id="cfe01-116">Por ejemplo, puede Agregar o quitar miembros, crear búsquedas y exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cfe01-116">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="cfe01-117">La principal diferencia entre los casos activos y cerrados es que las suspensiones de eDiscovery se desactivan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="cfe01-117">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="cfe01-118">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="cfe01-118">To close a case:</span></span>
  
1. <span data-ttu-id="cfe01-119">En la entrada de cumplimiento de Microsoft 365, haga clic en **eDiscovery** > **Core** para mostrar la lista de casos de eDiscovery principales en su organización.</span><span class="sxs-lookup"><span data-stu-id="cfe01-119">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="cfe01-120">Haga clic en el nombre del caso que desea cerrar.</span><span class="sxs-lookup"><span data-stu-id="cfe01-120">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="cfe01-121">Se muestra la página flotante **administrar este caso** .</span><span class="sxs-lookup"><span data-stu-id="cfe01-121">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="cfe01-122">En **administrar estado de caso**, haga clic en **cerrar caso**.</span><span class="sxs-lookup"><span data-stu-id="cfe01-122">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="cfe01-123">Se muestra una advertencia que indica que las suspensiones asociadas con el caso se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="cfe01-123">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="cfe01-124">Haga clic en **sí** para cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="cfe01-124">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="cfe01-125">El estado de la página desplegable **administrar este caso** se cambia de **activo** a **cierre**.</span><span class="sxs-lookup"><span data-stu-id="cfe01-125">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="cfe01-126">Cierre la página **administrar este caso** .</span><span class="sxs-lookup"><span data-stu-id="cfe01-126">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="cfe01-127">En la página **principal de eDiscovery** , haga clic en **Actualizar** para actualizar el estado del caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="cfe01-127">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="cfe01-128">El proceso de cierre puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="cfe01-128">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="cfe01-129">Una vez finalizado el proceso, el estado del caso cambia a **cerrado** en la página **principal de eDiscovery** .</span><span class="sxs-lookup"><span data-stu-id="cfe01-129">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="cfe01-130">Vuelva a hacer clic en el nombre del caso para mostrar la página flotante **administrar este caso** , que contiene información sobre cuándo se cerró el caso y quién lo cerró.</span><span class="sxs-lookup"><span data-stu-id="cfe01-130">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="cfe01-131">Volver a abrir un caso cerrado</span><span class="sxs-lookup"><span data-stu-id="cfe01-131">Reopen a closed case</span></span>

<span data-ttu-id="cfe01-132">Cuando vuelva a abrir un caso, las suspensiones de exhibición de documentos electrónicos que estuvieran en su ubicación cuando se cerró el caso no se restituyerán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="cfe01-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="cfe01-133">Después de volver a abrir el caso, tendrá que ir a la página **suspensiones** y activar las suspensiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cfe01-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="cfe01-134">Para activar una retención, selecciónela para mostrar la página de flotante y, a continuación, establezca el **Estado** en activar como **activado**.</span><span class="sxs-lookup"><span data-stu-id="cfe01-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="cfe01-135">En la entrada de cumplimiento de Microsoft 365, haga clic en **eDiscovery** > **Core** para mostrar la lista de casos de eDiscovery principales en su organización.</span><span class="sxs-lookup"><span data-stu-id="cfe01-135">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="cfe01-136">Haga clic en el nombre del caso que desea volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="cfe01-136">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="cfe01-137">Se muestra la página flotante **administrar este caso** .</span><span class="sxs-lookup"><span data-stu-id="cfe01-137">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="cfe01-138">En **administrar estado de caso**, haga clic en **volver a abrir el caso**.</span><span class="sxs-lookup"><span data-stu-id="cfe01-138">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="cfe01-139">Se muestra una advertencia que indica que las suspensiones asociadas con el caso cuando se cerró no se activarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="cfe01-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="cfe01-140">Haga clic en **sí** para volver a abrir el caso.</span><span class="sxs-lookup"><span data-stu-id="cfe01-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="cfe01-141">El estado de la página desplegable **administrar este caso** se ha cambiado de **cerrado** a **activo**.</span><span class="sxs-lookup"><span data-stu-id="cfe01-141">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="cfe01-142">Cierre la página **administrar este caso** .</span><span class="sxs-lookup"><span data-stu-id="cfe01-142">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="cfe01-143">En la página **principal de eDiscovery** , haga clic en **Actualizar** para actualizar el estado del caso reabierto.</span><span class="sxs-lookup"><span data-stu-id="cfe01-143">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="cfe01-144">El proceso de reapertura puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="cfe01-144">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="cfe01-145">Una vez finalizado el proceso, el estado del caso cambia a **activo** en la página **principal de eDiscovery** .</span><span class="sxs-lookup"><span data-stu-id="cfe01-145">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="cfe01-146">Eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="cfe01-146">Delete a case</span></span>

<span data-ttu-id="cfe01-147">También puede eliminar casos de exhibición de documentos electrónicos principales activos y cerrados.</span><span class="sxs-lookup"><span data-stu-id="cfe01-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="cfe01-148">Al eliminar un caso, se eliminan todas las búsquedas y exportaciones en el caso y se elimina el caso de la lista de casos de la página **principal de eDiscovery** en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfe01-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="cfe01-149">No se puede volver a abrir un caso eliminado.</span><span class="sxs-lookup"><span data-stu-id="cfe01-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="cfe01-150">Antes de que pueda eliminar un caso (ya sea activo o cerrado), primero debe eliminar *todas* las suspensiones de eDiscovery asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="cfe01-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="cfe01-151">Esto incluye la eliminación de suspensiones con el estado **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="cfe01-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="cfe01-152">Para eliminar una suspensión de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="cfe01-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="cfe01-153">Vaya a la pestaña **suspensiones** en el caso de que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="cfe01-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="cfe01-154">Haga clic en la suspensión que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="cfe01-154">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="cfe01-155">En la página flotante, haga clic en **eliminar suspensión**.</span><span class="sxs-lookup"><span data-stu-id="cfe01-155">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="cfe01-156">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="cfe01-156">To delete a case:</span></span>

1. <span data-ttu-id="cfe01-157">En la entrada de cumplimiento de Microsoft 365, haga clic en **eDiscovery** > **Core** para mostrar la lista de casos de eDiscovery principales en su organización.</span><span class="sxs-lookup"><span data-stu-id="cfe01-157">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="cfe01-158">Haga clic en el nombre del caso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="cfe01-158">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="cfe01-159">En **administrar estado de caso** en la página flotante, haga clic en **eliminar caso**.</span><span class="sxs-lookup"><span data-stu-id="cfe01-159">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="cfe01-160">Si el caso que está intentando eliminar todavía contiene suspensiones de eDiscovery, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="cfe01-160">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="cfe01-161">Tendrá que eliminar todas las suspensiones asociadas con el caso y, a continuación, volver a intentar eliminar el caso.</span><span class="sxs-lookup"><span data-stu-id="cfe01-161">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
