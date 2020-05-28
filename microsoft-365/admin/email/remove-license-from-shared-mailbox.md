---
title: Quitar la licencia de un buzón compartido
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
ms.openlocfilehash: 1f69cd6f0e572da18abf7253832604ad3ac0ab8f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400033"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="a7bff-103">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="a7bff-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a7bff-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="a7bff-104">The admin center is changing.</span></span> <span data-ttu-id="a7bff-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a7bff-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="a7bff-106">Los buzones compartidos no suelen requerir una licencia.</span><span class="sxs-lookup"><span data-stu-id="a7bff-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="a7bff-107">Siga estas instrucciones para quitar una licencia de un buzón de correo compartido de manera que pueda asignarla a un usuario o devolver la licencia para que no pague por una licencia que no necesite.</span><span class="sxs-lookup"><span data-stu-id="a7bff-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="a7bff-108">Se requiere una licencia en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="a7bff-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="a7bff-109">El buzón compartido tiene más de 50 GB de almacenamiento en uso.</span><span class="sxs-lookup"><span data-stu-id="a7bff-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="a7bff-110">El buzón de correo compartido usa el archivado local.</span><span class="sxs-lookup"><span data-stu-id="a7bff-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="a7bff-111">El buzón compartido se coloca en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="a7bff-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="a7bff-112">Quitar la licencia</span><span class="sxs-lookup"><span data-stu-id="a7bff-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="a7bff-113">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="a7bff-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="a7bff-114">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="a7bff-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a7bff-115">Debe quitar la licencia de la página usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="a7bff-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="a7bff-116">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="a7bff-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="a7bff-117">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="a7bff-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="a7bff-118">Una de las pestañas **licencias y aplicaciones** , expanda **licencias** y desactive la casilla de la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="a7bff-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="a7bff-119">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="a7bff-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="a7bff-120">Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.</span><span class="sxs-lookup"><span data-stu-id="a7bff-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="a7bff-121">Todavía está pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="a7bff-121">You're still paying for the license.</span></span> <span data-ttu-id="a7bff-122">Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a7bff-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="a7bff-123">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="a7bff-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a7bff-124">Debe quitar la licencia de la página usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="a7bff-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="a7bff-125">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="a7bff-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="a7bff-126">Seleccione el buzón compartido y, a continuación, seleccione **Editar** junto a **licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="a7bff-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="a7bff-127">Una página de **licencias de productos** , establezca el botón de alternancia en **desactivado** para la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="a7bff-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="a7bff-128">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a7bff-128">Select **Save**.</span></span>

5. <span data-ttu-id="a7bff-129">Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.</span><span class="sxs-lookup"><span data-stu-id="a7bff-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="a7bff-130">Todavía está pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="a7bff-130">You're still paying for the license.</span></span> <span data-ttu-id="a7bff-131">Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a7bff-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="a7bff-132">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="a7bff-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a7bff-133">Debe quitar la licencia de la página usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="a7bff-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="a7bff-134">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="a7bff-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="a7bff-135">Seleccione el buzón compartido y, a continuación, seleccione **Editar** junto a **licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="a7bff-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="a7bff-136">Una página de **licencias de productos** , establezca el botón de alternancia en **desactivado** para la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="a7bff-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="a7bff-137">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a7bff-137">Select **Save**.</span></span>

5. <span data-ttu-id="a7bff-138">Al volver a la página **usuarios activos** , el estado del buzón compartido será **sin licencia**.</span><span class="sxs-lookup"><span data-stu-id="a7bff-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="a7bff-139">Todavía está pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="a7bff-139">You're still paying for the license.</span></span> <span data-ttu-id="a7bff-140">Para dejar de pagar por ella, [Quite la licencia de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a7bff-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="a7bff-141">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="a7bff-141">Related articles</span></span>

[<span data-ttu-id="a7bff-142">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="a7bff-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="a7bff-143">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="a7bff-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="a7bff-144">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="a7bff-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="a7bff-145">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="a7bff-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="a7bff-146">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="a7bff-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
