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
description: 'Quite la licencia de un buzón compartido para asignarla a otro usuario. '
ms.openlocfilehash: 1acd549936212db7f722355ed1f2518ff6bbac18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915691"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="69c2e-103">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="69c2e-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="69c2e-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="69c2e-104">The admin center is changing.</span></span> <span data-ttu-id="69c2e-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="69c2e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="69c2e-106">Los buzones compartidos normalmente no requieren una licencia.</span><span class="sxs-lookup"><span data-stu-id="69c2e-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="69c2e-107">Siga estas instrucciones para quitar una licencia de un buzón compartido para que pueda asignarla a un usuario o devolver la licencia para que no pague una licencia que no necesite.</span><span class="sxs-lookup"><span data-stu-id="69c2e-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="69c2e-108">Se requiere una licencia en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="69c2e-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="69c2e-109">El buzón compartido tiene más de 50 GB de almacenamiento en uso.</span><span class="sxs-lookup"><span data-stu-id="69c2e-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="69c2e-110">El buzón compartido usa archivado local.</span><span class="sxs-lookup"><span data-stu-id="69c2e-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="69c2e-111">El buzón compartido se coloca en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="69c2e-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="69c2e-112">El buzón compartido tiene asignada una licencia de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="69c2e-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="69c2e-113">Quitar la licencia</span><span class="sxs-lookup"><span data-stu-id="69c2e-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="69c2e-114">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="69c2e-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="69c2e-115">Debe quitar la licencia de la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="69c2e-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="69c2e-116">No puede quitar la licencia de la página Buzón compartido porque las licencias son configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="69c2e-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="69c2e-117">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="69c2e-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="69c2e-118">Una de **las pestañas Licencias y Aplicaciones,** expanda **Licencias** y desactive la casilla de la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="69c2e-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="69c2e-119">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="69c2e-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="69c2e-120">Cuando vuelva a la **página Usuarios activos,** el estado del buzón compartido será **Sin licencia.**</span><span class="sxs-lookup"><span data-stu-id="69c2e-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="69c2e-121">Sigue pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="69c2e-121">You're still paying for the license.</span></span> <span data-ttu-id="69c2e-122">Para dejar de pagar por ella, [quite la licencia de la suscripción](../../commerce/licenses/buy-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="69c2e-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="69c2e-123">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="69c2e-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69c2e-124">Debe quitar la licencia de la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="69c2e-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="69c2e-125">No puede quitar la licencia de la página Buzón compartido porque las licencias son configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="69c2e-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="69c2e-126">Seleccione el buzón compartido y, a continuación, **seleccione Editar** junto a Licencias **de producto.**</span><span class="sxs-lookup"><span data-stu-id="69c2e-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="69c2e-127">Una de **la página Licencias del producto,** establece la alternancia en **Desactivado** para la licencia que quieres quitar.</span><span class="sxs-lookup"><span data-stu-id="69c2e-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="69c2e-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="69c2e-128">Select **Save**.</span></span>

5. <span data-ttu-id="69c2e-129">Cuando vuelva a la **página Usuarios activos,** el estado del buzón compartido será **Sin licencia.**</span><span class="sxs-lookup"><span data-stu-id="69c2e-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="69c2e-130">Sigue pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="69c2e-130">You're still paying for the license.</span></span> <span data-ttu-id="69c2e-131">Para dejar de pagar por ella, [quite la licencia de la suscripción](../../commerce/licenses/buy-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="69c2e-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="69c2e-132">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="69c2e-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69c2e-133">Debe quitar la licencia de la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="69c2e-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="69c2e-134">No puede quitar la licencia de la página Buzón compartido porque las licencias son configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="69c2e-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="69c2e-135">Seleccione el buzón compartido y, a continuación, **seleccione Editar** junto a Licencias **de producto.**</span><span class="sxs-lookup"><span data-stu-id="69c2e-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="69c2e-136">Una de **la página Licencias del producto,** establece la alternancia en **Desactivado** para la licencia que quieres quitar.</span><span class="sxs-lookup"><span data-stu-id="69c2e-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="69c2e-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="69c2e-137">Select **Save**.</span></span>

5. <span data-ttu-id="69c2e-138">Cuando vuelva a la **página Usuarios activos,** el estado del buzón compartido será **Sin licencia.**</span><span class="sxs-lookup"><span data-stu-id="69c2e-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="69c2e-139">Sigue pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="69c2e-139">You're still paying for the license.</span></span> <span data-ttu-id="69c2e-140">Para dejar de pagar por ella, [quite la licencia de la suscripción](../../commerce/licenses/buy-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="69c2e-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="69c2e-141">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="69c2e-141">Related articles</span></span>

[<span data-ttu-id="69c2e-142">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="69c2e-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="69c2e-143">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="69c2e-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="69c2e-144">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="69c2e-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="69c2e-145">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="69c2e-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="69c2e-146">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="69c2e-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)