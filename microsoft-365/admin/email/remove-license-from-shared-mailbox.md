---
title: Quitar la licencia de un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Quitar la licencia de un buzón compartido para asignarlo a otro usuario. '
ms.openlocfilehash: 43d32744afe42a8f244160ace20c1d989f501b28
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445500"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="f4f98-103">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="f4f98-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f4f98-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="f4f98-104">The admin center is changing.</span></span> <span data-ttu-id="f4f98-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f4f98-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="f4f98-106">Los buzones compartidos no suelen requerir una licencia.</span><span class="sxs-lookup"><span data-stu-id="f4f98-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="f4f98-107">Siga estas instrucciones para quitar una licencia de un buzón de correo compartido de manera que pueda asignarla a un usuario o devolver la licencia para que no pague por una licencia que no necesite.</span><span class="sxs-lookup"><span data-stu-id="f4f98-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="f4f98-108">Se requiere una licencia en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="f4f98-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="f4f98-109">El buzón compartido tiene más de 50 GB de almacenamiento en uso.</span><span class="sxs-lookup"><span data-stu-id="f4f98-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="f4f98-110">El buzón de correo compartido usa el archivado local.</span><span class="sxs-lookup"><span data-stu-id="f4f98-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="f4f98-111">El buzón compartido se coloca en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="f4f98-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="f4f98-112">Quitar la licencia</span><span class="sxs-lookup"><span data-stu-id="f4f98-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f4f98-113">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="f4f98-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f4f98-114">Debe quitar la licencia de la página usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="f4f98-114">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f4f98-115">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="f4f98-115">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="f4f98-116">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="f4f98-116">Select the shared mailbox.</span></span>

3. <span data-ttu-id="f4f98-117">Una de las pestañas **licencias y aplicaciones** , expanda **licencias** y desactive la casilla de la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="f4f98-117">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="f4f98-118">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="f4f98-118">Select **Save changes**.</span></span>

5. <span data-ttu-id="f4f98-119">Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.</span><span class="sxs-lookup"><span data-stu-id="f4f98-119">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f4f98-120">Todavía está pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="f4f98-120">You're still paying for the license.</span></span> <span data-ttu-id="f4f98-121">Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="f4f98-121">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="f4f98-122">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="f4f98-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4f98-123">Debe quitar la licencia de la página usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="f4f98-123">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f4f98-124">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="f4f98-124">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f4f98-125">Seleccione el buzón compartido y, a continuación, seleccione **Editar** junto a **licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="f4f98-125">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f4f98-126">Una página de **licencias de productos** , establezca el botón de alternancia en **desactivado** para la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="f4f98-126">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f4f98-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f4f98-127">Select **Save**.</span></span>

5. <span data-ttu-id="f4f98-128">Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.</span><span class="sxs-lookup"><span data-stu-id="f4f98-128">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f4f98-129">Todavía está pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="f4f98-129">You're still paying for the license.</span></span> <span data-ttu-id="f4f98-130">Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="f4f98-130">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="f4f98-131">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="f4f98-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4f98-132">Debe quitar la licencia de la página usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="f4f98-132">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f4f98-133">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="f4f98-133">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f4f98-134">Seleccione el buzón compartido y, a continuación, seleccione **Editar** junto a **licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="f4f98-134">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f4f98-135">Una página de **licencias de productos** , establezca el botón de alternancia en **desactivado** para la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="f4f98-135">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f4f98-136">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f4f98-136">Select **Save**.</span></span>

5. <span data-ttu-id="f4f98-137">Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.</span><span class="sxs-lookup"><span data-stu-id="f4f98-137">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f4f98-138">Todavía está pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="f4f98-138">You're still paying for the license.</span></span> <span data-ttu-id="f4f98-139">Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="f4f98-139">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="f4f98-140">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="f4f98-140">Related articles</span></span>

[<span data-ttu-id="f4f98-141">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="f4f98-141">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f4f98-142">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="f4f98-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f4f98-143">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="f4f98-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f4f98-144">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="f4f98-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="f4f98-145">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="f4f98-145">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
