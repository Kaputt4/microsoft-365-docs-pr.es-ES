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
description: Obtenga información sobre qué sucede cuando se cierra o elimina una investigación o un caso legal admitido por un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: efbcbe34e6d7d8b564bcfa0cf9bbd8a1fbb59709
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194637"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="2cd08-103">Cerrar o eliminar un Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="2cd08-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="2cd08-104">Cuando se complete el caso legal o la investigación admitida por un Advanced eDiscovery caso, puede cerrar o eliminar un caso.</span><span class="sxs-lookup"><span data-stu-id="2cd08-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="2cd08-105">También puede volver a abrir un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="2cd08-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="2cd08-106">Cerrar un caso</span><span class="sxs-lookup"><span data-stu-id="2cd08-106">Close a case</span></span>

<span data-ttu-id="2cd08-107">Esto es lo que sucede al cerrar un Advanced eDiscovery caso:</span><span class="sxs-lookup"><span data-stu-id="2cd08-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="2cd08-108">Si el caso contiene ubicaciones de contenido en espera, esas retenciones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="2cd08-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="2cd08-109">Después de desactivar la retención, se aplica un período de gracia de 30 días (denominado retención de *retraso)* a las ubicaciones de contenido que estaban en espera.</span><span class="sxs-lookup"><span data-stu-id="2cd08-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="2cd08-110">Esto ayuda a evitar que el contenido se elimine inmediatamente y ofrece a los administradores la oportunidad de buscar o recuperar contenido que se eliminará permanentemente después de que expire el período de retención de retraso.</span><span class="sxs-lookup"><span data-stu-id="2cd08-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="2cd08-111">Para obtener más información, vea [Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="2cd08-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="2cd08-112">Cerrar un caso solo desactiva las retenciones que están asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="2cd08-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="2cd08-113">Si otras retenciones se encuentran en una ubicación de contenido (como una retención por juicio, una retención de exhibición de documentos electrónicos principal o una retención de un caso Advanced eDiscovery diferente) esas retenciones se mantendrán.</span><span class="sxs-lookup"><span data-stu-id="2cd08-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="2cd08-114">El caso sigue estando en la página exhibición de documentos electrónicos de la Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cd08-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2cd08-115">Se conservan los detalles, las retenciones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="2cd08-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="2cd08-116">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="2cd08-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="2cd08-117">Por ejemplo, puede agregar o quitar miembros, crear búsquedas, exportar resultados de búsqueda y preparar resultados de búsqueda para el análisis en Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2cd08-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="2cd08-118">La principal diferencia entre los casos activos y cerrados es que las retenciones se desactivarán cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="2cd08-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="2cd08-119">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="2cd08-119">To close a case:</span></span>

1. <span data-ttu-id="2cd08-120">En la página de **eDiscovery avanzado**, seleccione el caso que desea cerrar.</span><span class="sxs-lookup"><span data-stu-id="2cd08-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="2cd08-121">En la pestaña **Configuración**, en **Información del**, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="2cd08-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

   ![Obtener acceso a la página desplegable de información de caso en un Advanced eDiscovery caso](..\media\AeDSelectCaseInformation.png) 

3. <span data-ttu-id="2cd08-123">En la parte inferior de la **página desplegable Información** del caso, haga clic en Acciones y, a continuación, haga clic en Cerrar **caso**. </span><span class="sxs-lookup"><span data-stu-id="2cd08-123">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Close case**.</span></span>

   <span data-ttu-id="2cd08-124">El proceso de cierre puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="2cd08-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="2cd08-125">Volver a abrir un caso cerrado</span><span class="sxs-lookup"><span data-stu-id="2cd08-125">Reopen a closed case</span></span>

<span data-ttu-id="2cd08-126">Al volver a abrir un Advanced eDiscovery, las retenciones que estaban en su lugar cuando se cerró el caso no se restablecerán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2cd08-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="2cd08-127">Una vez que se vuelva a abrir el caso, tendrás que ir a la pestaña **Retenciones** y activar las retenciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="2cd08-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="2cd08-128">Para activar una retención, selecciónela para mostrar la página flotante y luego configure el interruptor de **Estado** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="2cd08-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="2cd08-129">Para volver a abrir un caso cerrado:</span><span class="sxs-lookup"><span data-stu-id="2cd08-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="2cd08-130">En la página de **eDiscovery avanzado**, seleccione el caso que quiere volver a abrir.</span><span class="sxs-lookup"><span data-stu-id="2cd08-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="2cd08-131">En la pestaña **Configuración**, en **Información de caso**, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="2cd08-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="2cd08-132">En la parte inferior de la **página desplegable Información** del caso, haga clic en Acciones y, a continuación, haga clic en Abrir **caso**. </span><span class="sxs-lookup"><span data-stu-id="2cd08-132">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Reopen case**.</span></span>

   <span data-ttu-id="2cd08-133">El proceso de reapertura puede tardar hasta 60 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="2cd08-133">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="2cd08-134">Eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="2cd08-134">Delete a case</span></span>

<span data-ttu-id="2cd08-135">Puede eliminar los casos activos y Advanced eDiscovery cerrados.</span><span class="sxs-lookup"><span data-stu-id="2cd08-135">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="2cd08-136">Al eliminar un caso, se eliminan todos los componentes asociados al caso, como la lista de administradores, comunicaciones, búsquedas, conjuntos de revisión y trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="2cd08-136">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="2cd08-137">El caso se quita de la lista de casos de la **página Advanced eDiscovery** de la Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cd08-137">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2cd08-138">No puede recuperar ni volver a abrir un caso eliminado.</span><span class="sxs-lookup"><span data-stu-id="2cd08-138">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="2cd08-139">En escenarios de derrame de datos, la única forma de quitar elementos de un conjunto de revisión es eliminar el Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="2cd08-139">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="2cd08-140">Otros métodos de "búsqueda y purga" no quitan elementos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2cd08-140">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="2cd08-141">Para poder eliminar un caso (ya sea activo o  cerrado), primero debe eliminar todas las retenciones asociadas con el caso.</span><span class="sxs-lookup"><span data-stu-id="2cd08-141">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="2cd08-142">Esto incluye la eliminación de retenciones con el estado **Off**.</span><span class="sxs-lookup"><span data-stu-id="2cd08-142">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="2cd08-143">Para eliminar las retenciones asociadas a un caso:</span><span class="sxs-lookup"><span data-stu-id="2cd08-143">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="2cd08-144">Vaya a **la pestaña Retenciones** en el Advanced eDiscovery caso que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="2cd08-144">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="2cd08-145">Haga clic en la retención que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="2cd08-145">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="2cd08-146">En la página desplegable, haga clic **en Eliminar retención**.</span><span class="sxs-lookup"><span data-stu-id="2cd08-146">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="2cd08-147">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="2cd08-147">To delete a case:</span></span>

1. <span data-ttu-id="2cd08-148">En la página de **eDiscovery avanzado**, seleccione el caso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="2cd08-148">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="2cd08-149">En la pestaña **Configuración**, en **Información del**, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="2cd08-149">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="2cd08-150">En la parte inferior de la **página desplegable Información** de casos, haga clic en Acciones y, a continuación, haga clic en Eliminar **caso**. </span><span class="sxs-lookup"><span data-stu-id="2cd08-150">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Delete case**.</span></span>

