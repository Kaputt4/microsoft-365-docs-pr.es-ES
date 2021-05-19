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
description: En este artículo se describe cómo administrar los casos principales de exhibición de documentos electrónicos. Esto incluye cerrar un caso, volver a abrir un caso cerrado y eliminar un caso.
ms.openlocfilehash: 8a54d5c8f93d36351538bc235a6dbeaaa602c3e9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532451"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="247a0-104">Cerrar, volver a abrir y eliminar un caso de exhibición de documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="247a0-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="247a0-105">En este artículo se describe cómo cerrar, volver a abrir y eliminar los casos principales de exhibición de documentos electrónicos en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="247a0-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="247a0-106">Cerrar un caso</span><span class="sxs-lookup"><span data-stu-id="247a0-106">Close a case</span></span>

<span data-ttu-id="247a0-107">Cuando se complete el caso legal o la investigación admitida por un caso de exhibición de documentos electrónicos principales, puede cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="247a0-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="247a0-108">Esto es lo que sucede al cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="247a0-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="247a0-109">Si el caso contiene alguna retención de exhibición de documentos electrónicos, se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="247a0-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="247a0-110">Después de desactivar la retención, se aplica un período de gracia de 30 días (denominado retención de *retraso)* a las ubicaciones de contenido que estaban en espera.</span><span class="sxs-lookup"><span data-stu-id="247a0-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="247a0-111">Esto ayuda a evitar que el contenido se elimine inmediatamente y proporciona a los administradores la oportunidad de buscar y restaurar contenido antes de que pueda eliminarse permanentemente después de que expire el período de retención de retraso.</span><span class="sxs-lookup"><span data-stu-id="247a0-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="247a0-112">Para obtener más información, vea [Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="247a0-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="247a0-113">Cerrar un caso solo desactiva las retenciones que están asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="247a0-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="247a0-114">Si otras retenciones se colocan en una ubicación de contenido (como una retención por juicio, una directiva de retención o una retención de un caso de exhibición de documentos electrónicos principal diferente) esas retenciones se mantendrán.</span><span class="sxs-lookup"><span data-stu-id="247a0-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="247a0-115">El caso sigue en la lista en la página eDiscovery principal del centro de Microsoft 365 cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="247a0-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="247a0-116">Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="247a0-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="247a0-117">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="247a0-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="247a0-118">Por ejemplo, puede agregar o quitar miembros, crear búsquedas y exportar resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="247a0-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="247a0-119">La diferencia principal entre los casos activos y cerrados es que las retenciones de exhibición de documentos electrónicos se apagan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="247a0-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="247a0-120">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="247a0-120">To close a case:</span></span>
  
1. <span data-ttu-id="247a0-121">En el centro Microsoft 365 cumplimiento, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de exhibición de documentos electrónicos  >   en su organización.</span><span class="sxs-lookup"><span data-stu-id="247a0-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="247a0-122">Haga clic en el nombre del caso que desea cerrar.</span><span class="sxs-lookup"><span data-stu-id="247a0-122">Click the name of the case that you want to close.</span></span>

   ![Cerrar caso en la página principal del caso](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="247a0-124">En la página principal, en **Estado**, haga clic **en Cerrar caso**.</span><span class="sxs-lookup"><span data-stu-id="247a0-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="247a0-125">Se muestra una advertencia que dice que las retenciones asociadas con el caso se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="247a0-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="247a0-126">Haga **clic en Sí** para cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="247a0-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="247a0-127">El estado de la página principal del caso cambia **de Activo** a **Cierre**.</span><span class="sxs-lookup"><span data-stu-id="247a0-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="247a0-128">En la **página Exhibición de documentos electrónicos principal,** haga clic **en Actualizar** para actualizar el estado del caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="247a0-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="247a0-129">El proceso de cierre puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="247a0-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="247a0-130">Una vez completado el proceso, el estado del caso cambia a **Cerrado** en la **página eDiscovery** principal.</span><span class="sxs-lookup"><span data-stu-id="247a0-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="247a0-131">Volver a abrir un caso cerrado</span><span class="sxs-lookup"><span data-stu-id="247a0-131">Reopen a closed case</span></span>

<span data-ttu-id="247a0-132">Al volver a abrir un caso, las retenciones de exhibición de documentos electrónicos que estaban en su lugar cuando se cerró el caso no se restablecerán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="247a0-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="247a0-133">Una vez que se vuelva a abrir el caso, tendrás que ir a la página **Retenciones** y activar las retenciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="247a0-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="247a0-134">Para activar una retención, selecciónela para mostrar la página flotante y luego configure el interruptor de **Estado** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="247a0-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="247a0-135">En el centro Microsoft 365 cumplimiento, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de exhibición de documentos electrónicos  >   en su organización.</span><span class="sxs-lookup"><span data-stu-id="247a0-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="247a0-136">Haga clic en el nombre del caso que desea volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="247a0-136">Click the name of the case that you want to reopen.</span></span>

   ![Volver a abrir un caso cerrado](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="247a0-138">En la página principal, en **Estado,** haga clic **en Abrir caso**.</span><span class="sxs-lookup"><span data-stu-id="247a0-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="247a0-139">Se muestra una advertencia que dice que las retenciones asociadas con el caso cuando se cerró no se activarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="247a0-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="247a0-140">Haga **clic en Sí** para volver a abrir el caso.</span><span class="sxs-lookup"><span data-stu-id="247a0-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="247a0-141">El estado de la página principal del caso se cambia de **Cerrado** a **Activo.**</span><span class="sxs-lookup"><span data-stu-id="247a0-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="247a0-142">En la **página Exhibición de documentos electrónicos principal,** haga clic **en Actualizar** para actualizar el estado del caso reabrido.</span><span class="sxs-lookup"><span data-stu-id="247a0-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="247a0-143">El proceso de reapertura puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="247a0-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="247a0-144">Una vez completado el proceso, el estado del caso cambia a **Activo** en la **página eDiscovery** principal.</span><span class="sxs-lookup"><span data-stu-id="247a0-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="247a0-145">(Opcional) Para activar las retenciones asociadas con  el caso reabierto, vaya a la  pestaña Retenciones, seleccione una retención y, a continuación, active la casilla en Estado en la página de control desplegable de retención.</span><span class="sxs-lookup"><span data-stu-id="247a0-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="247a0-146">Eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="247a0-146">Delete a case</span></span>

<span data-ttu-id="247a0-147">También puede eliminar los casos de exhibición de documentos electrónicos principales activos y cerrados.</span><span class="sxs-lookup"><span data-stu-id="247a0-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="247a0-148">Al eliminar un caso, se eliminan todas las búsquedas y exportaciones del caso  y el caso se quita de la lista de casos de la página Exhibición de documentos electrónicos principal del centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="247a0-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="247a0-149">No puede volver a abrir un caso eliminado.</span><span class="sxs-lookup"><span data-stu-id="247a0-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="247a0-150">Para poder eliminar un caso (ya sea activo o cerrado), primero debe eliminar todas las retenciones de *exhibición* de documentos electrónicos asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="247a0-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="247a0-151">Esto incluye la eliminación de retenciones con el estado **Off**.</span><span class="sxs-lookup"><span data-stu-id="247a0-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="247a0-152">Para eliminar una retención de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="247a0-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="247a0-153">Vaya a **la pestaña Retenciones** en caso de que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="247a0-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="247a0-154">Seleccione la retención que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="247a0-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="247a0-155">En la página desplegable, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="247a0-155">On the flyout page, click **Delete**.</span></span>

      ![Eliminar una retención de exhibición de documentos electrónicos](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="247a0-157">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="247a0-157">To delete a case:</span></span>

1. <span data-ttu-id="247a0-158">En el centro Microsoft 365 cumplimiento, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de exhibición de documentos electrónicos  >   en su organización.</span><span class="sxs-lookup"><span data-stu-id="247a0-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="247a0-159">Haga clic en el nombre del caso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="247a0-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="247a0-160">En la página principal del caso, en **Estado**, haga clic **en Eliminar caso**.</span><span class="sxs-lookup"><span data-stu-id="247a0-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![Eliminar un caso](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="247a0-162">Si el caso que intenta eliminar aún contiene retenciones de exhibición de documentos electrónicos, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="247a0-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="247a0-163">Tendrás que eliminar todas las retenciones asociadas con el caso e intentar de nuevo eliminar el caso.</span><span class="sxs-lookup"><span data-stu-id="247a0-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
