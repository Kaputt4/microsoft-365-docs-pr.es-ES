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
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698308"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="8d575-103">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="8d575-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8d575-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="8d575-104">The admin center is changing.</span></span> <span data-ttu-id="8d575-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="8d575-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="8d575-106">Los buzones compartidos normalmente no requieren una licencia.</span><span class="sxs-lookup"><span data-stu-id="8d575-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="8d575-107">Siga estas instrucciones para quitar una licencia de un buzón compartido de modo que pueda asignarla a un usuario o devolver la licencia para que no tenga que pagar por una licencia que no necesite.</span><span class="sxs-lookup"><span data-stu-id="8d575-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="8d575-108">Se requiere una licencia en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="8d575-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="8d575-109">El buzón compartido tiene más de 50 GB de almacenamiento en uso.</span><span class="sxs-lookup"><span data-stu-id="8d575-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="8d575-110">El buzón compartido usa el archivado local.</span><span class="sxs-lookup"><span data-stu-id="8d575-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="8d575-111">El buzón compartido se coloca en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="8d575-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="8d575-112">El buzón compartido tiene asignada una licencia de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="8d575-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="8d575-113">Quitar la licencia</span><span class="sxs-lookup"><span data-stu-id="8d575-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8d575-114">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8d575-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8d575-115">Debe quitar la licencia de la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="8d575-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="8d575-116">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="8d575-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="8d575-117">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="8d575-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="8d575-118">Una en **la pestaña Licencias y aplicaciones,** expanda **Licencias** y desactive la casilla de la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="8d575-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="8d575-119">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8d575-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="8d575-120">Cuando vuelva a la página **Usuarios activos,** el estado del buzón compartido será **Sin licencia.**</span><span class="sxs-lookup"><span data-stu-id="8d575-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="8d575-121">Sigues pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="8d575-121">You're still paying for the license.</span></span> <span data-ttu-id="8d575-122">Para dejar de pagar por ella, [quite la licencia de su suscripción.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="8d575-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="8d575-123">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8d575-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d575-124">Debe quitar la licencia de la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="8d575-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="8d575-125">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="8d575-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="8d575-126">Seleccione el buzón compartido y, a continuación, **seleccione Editar** junto a Licencias **de producto.**</span><span class="sxs-lookup"><span data-stu-id="8d575-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="8d575-127">Una de **las páginas Licencias de producto,** establece el botón de **alternancia** en Desactivado para la licencia que quieras quitar.</span><span class="sxs-lookup"><span data-stu-id="8d575-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="8d575-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8d575-128">Select **Save**.</span></span>

5. <span data-ttu-id="8d575-129">Cuando vuelva a la página **Usuarios activos,** el estado del buzón compartido será **Sin licencia.**</span><span class="sxs-lookup"><span data-stu-id="8d575-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="8d575-130">Sigues pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="8d575-130">You're still paying for the license.</span></span> <span data-ttu-id="8d575-131">Para dejar de pagar por ella, [quite la licencia de su suscripción.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="8d575-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="8d575-132">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8d575-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d575-133">Debe quitar la licencia de la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="8d575-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="8d575-134">No puede quitar la licencia de la página buzón compartido porque las licencias son configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="8d575-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="8d575-135">Seleccione el buzón compartido y, a continuación, **seleccione Editar** junto a Licencias **de producto.**</span><span class="sxs-lookup"><span data-stu-id="8d575-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="8d575-136">Una de **las páginas Licencias de producto,** establece el botón de **alternancia** en Desactivado para la licencia que quieras quitar.</span><span class="sxs-lookup"><span data-stu-id="8d575-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="8d575-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8d575-137">Select **Save**.</span></span>

5. <span data-ttu-id="8d575-138">Cuando vuelva a la página **Usuarios activos,** el estado del buzón compartido será **Sin licencia.**</span><span class="sxs-lookup"><span data-stu-id="8d575-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="8d575-139">Sigues pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="8d575-139">You're still paying for the license.</span></span> <span data-ttu-id="8d575-140">Para dejar de pagar por ella, [quite la licencia de su suscripción.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="8d575-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="8d575-141">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="8d575-141">Related articles</span></span>

[<span data-ttu-id="8d575-142">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="8d575-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="8d575-143">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="8d575-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="8d575-144">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="8d575-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="8d575-145">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="8d575-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="8d575-146">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="8d575-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
