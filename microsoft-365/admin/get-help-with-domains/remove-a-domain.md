---
title: Quitar un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Obtenga información sobre cómo quitar un dominio antiguo de Microsoft 365 y mover usuarios y grupos a otro dominio.
ms.openlocfilehash: c5e629f0d683c6dc3e18b1278027ac3a88cc834b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399901"
---
# <a name="remove-a-domain"></a><span data-ttu-id="efe00-103">Quitar un dominio</span><span class="sxs-lookup"><span data-stu-id="efe00-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="efe00-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="efe00-104">The admin center is changing.</span></span> <span data-ttu-id="efe00-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="efe00-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="efe00-106">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="efe00-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="efe00-107">¿Está eliminando su dominio porque quiere agregarlo a un plan de suscripción de Microsoft 365 diferente?</span><span class="sxs-lookup"><span data-stu-id="efe00-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="efe00-108">¿O solo quiere cancelar su suscripción?</span><span class="sxs-lookup"><span data-stu-id="efe00-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="efe00-109">Puede [cambiar su plan o suscripción](../../commerce/subscriptions/switch-to-a-different-plan.md), o bien [cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="efe00-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="efe00-110">Paso 1: mover usuarios a otro dominio</span><span class="sxs-lookup"><span data-stu-id="efe00-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="efe00-111">Mover usuarios</span><span class="sxs-lookup"><span data-stu-id="efe00-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="efe00-112">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="efe00-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="efe00-113">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a>.</span><span class="sxs-lookup"><span data-stu-id="efe00-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="efe00-114">Seleccione **usuarios** > **activos**.</span><span class="sxs-lookup"><span data-stu-id="efe00-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="efe00-115">Active las casillas situadas junto a los nombres de todos los usuarios que desee mover.</span><span class="sxs-lookup"><span data-stu-id="efe00-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="efe00-116">Seleccione **más opciones** (**...**), en la parte superior de la página y, a continuación, elija **cambiar dominios**.</span><span class="sxs-lookup"><span data-stu-id="efe00-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="efe00-117">En el panel **cambiar dominios** , seleccione un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="efe00-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="efe00-p103">Tendrá que realizar esta acción también para su propio usuario si se encuentra en el dominio que quiere quitar. Al editar el dominio para su cuenta, tendrá que cerrar sesión y volver a iniciarla con el dominio nuevo que eligió para continuar.</span><span class="sxs-lookup"><span data-stu-id="efe00-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="efe00-120">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>.</span><span class="sxs-lookup"><span data-stu-id="efe00-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="efe00-121">Seleccione **usuarios** > **activos**.</span><span class="sxs-lookup"><span data-stu-id="efe00-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="efe00-122">Active las casillas situadas junto a los nombres de todos los usuarios que desee mover.</span><span class="sxs-lookup"><span data-stu-id="efe00-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="efe00-123">En la parte superior de la página, elija **más** > **dominios de edición**.</span><span class="sxs-lookup"><span data-stu-id="efe00-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="efe00-124">En el panel **Editar dominios** , seleccione un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="efe00-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="efe00-p104">Tendrá que realizar esta acción también para su propio usuario si se encuentra en el dominio que quiere quitar. Al editar el dominio para su cuenta, tendrá que cerrar sesión y volver a iniciarla con el dominio nuevo que eligió para continuar.</span><span class="sxs-lookup"><span data-stu-id="efe00-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="efe00-127">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>.</span><span class="sxs-lookup"><span data-stu-id="efe00-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="efe00-128">Seleccione **usuarios** > **activos**.</span><span class="sxs-lookup"><span data-stu-id="efe00-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="efe00-129">Active las casillas situadas junto a los nombres de todos los usuarios que desee mover.</span><span class="sxs-lookup"><span data-stu-id="efe00-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="efe00-130">En la parte superior de la página, elija **más** > **dominios de edición**.</span><span class="sxs-lookup"><span data-stu-id="efe00-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="efe00-131">En el panel **Editar dominios** , seleccione un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="efe00-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="efe00-p105">Tendrá que realizar esta acción también para su propio usuario si se encuentra en el dominio que quiere quitar. Al editar el dominio para su cuenta, tendrá que cerrar sesión y volver a iniciarla con el dominio nuevo que eligió para continuar.</span><span class="sxs-lookup"><span data-stu-id="efe00-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="efe00-134">Desplazarse</span><span class="sxs-lookup"><span data-stu-id="efe00-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="efe00-135">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="efe00-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="efe00-136">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>.</span><span class="sxs-lookup"><span data-stu-id="efe00-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="efe00-137">Vaya a **usuarios** \> **activos**y seleccione su cuenta de la lista.</span><span class="sxs-lookup"><span data-stu-id="efe00-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="efe00-138">En la pestaña **cuenta** , seleccione **administrar nombre de usuario**y, a continuación, elija un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="efe00-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="efe00-139">En la parte superior, selecciona el nombre de la cuenta y, a continuación, selecciona **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="efe00-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="efe00-140">Inicie sesión con el nuevo dominio y la misma contraseña.</span><span class="sxs-lookup"><span data-stu-id="efe00-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="efe00-141">También puede usar PowerShell para mover los usuarios a otro dominio.</span><span class="sxs-lookup"><span data-stu-id="efe00-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="efe00-142">Vea [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="efe00-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="efe00-143">Para establecer el dominio predeterminado, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="efe00-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="efe00-144">Vaya a **usuarios** \> **activos**y seleccione su nombre en la lista.</span><span class="sxs-lookup"><span data-stu-id="efe00-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="efe00-145">En la sección **nombre de usuario/correo electrónico** , seleccione **Editar**y, a continuación, elija un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="efe00-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="efe00-146">Seleccione **establecer como principal** > **Guardar** > **cierre**.</span><span class="sxs-lookup"><span data-stu-id="efe00-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="efe00-147">En la parte superior, selecciona el nombre de la cuenta y, a continuación, selecciona **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="efe00-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="efe00-148">Inicie sesión con el nuevo dominio y la misma contraseña.</span><span class="sxs-lookup"><span data-stu-id="efe00-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="efe00-149">También puede usar PowerShell para mover los usuarios a otro dominio.</span><span class="sxs-lookup"><span data-stu-id="efe00-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="efe00-150">Vea [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="efe00-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="efe00-151">Para establecer el dominio predeterminado, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="efe00-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="efe00-152">Vaya a **usuarios** \> **activos**y seleccione su nombre en la lista.</span><span class="sxs-lookup"><span data-stu-id="efe00-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="efe00-153">En la sección **nombre de usuario/correo electrónico** , seleccione **Editar**y, a continuación, elija un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="efe00-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="efe00-154">Seleccione **establecer como principal** > **Guardar** > **cierre**.</span><span class="sxs-lookup"><span data-stu-id="efe00-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="efe00-155">En la parte superior, selecciona el nombre de la cuenta y, a continuación, selecciona **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="efe00-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="efe00-156">Inicie sesión con el nuevo dominio y la misma contraseña.</span><span class="sxs-lookup"><span data-stu-id="efe00-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="efe00-157">También puede usar PowerShell para mover los usuarios a otro dominio.</span><span class="sxs-lookup"><span data-stu-id="efe00-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="efe00-158">Vea [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="efe00-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="efe00-159">Para establecer el dominio predeterminado, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="efe00-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="efe00-160">Paso 2: mover grupos a otro dominio</span><span class="sxs-lookup"><span data-stu-id="efe00-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="efe00-161">En el centro de administración, vaya a **la** página grupos de grupos \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="efe00-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="efe00-162">Seleccione el nombre del grupo y, a continuación, en la pestaña **General** , en **dirección de correo electrónico,** haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="efe00-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="efe00-163">Use la lista desplegable para elegir otro dominio.</span><span class="sxs-lookup"><span data-stu-id="efe00-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="efe00-164">Seleccione **Guardar** y, a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="efe00-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="efe00-165">Repita este proceso para todas las listas de distribución o grupos que estén asociados al dominio que quiere quitar.</span><span class="sxs-lookup"><span data-stu-id="efe00-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="efe00-166">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a **la** página grupos de grupos > **Groups** .</span><span class="sxs-lookup"><span data-stu-id="efe00-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="efe00-167">Seleccione el nombre del grupo y, a continuación, seleccione **Editar** junto a **nombre**.</span><span class="sxs-lookup"><span data-stu-id="efe00-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="efe00-168">Use la lista desplegable para elegir otro dominio.</span><span class="sxs-lookup"><span data-stu-id="efe00-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="efe00-169">Seleccione **Guardar** y, a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="efe00-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="efe00-170">Repita este proceso para todas las listas de distribución o grupos que estén asociados al dominio que quiere quitar.</span><span class="sxs-lookup"><span data-stu-id="efe00-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="efe00-171">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a **la** página grupos de grupos > **Groups** .</span><span class="sxs-lookup"><span data-stu-id="efe00-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="efe00-172">Seleccione el nombre del grupo y, a continuación, seleccione **Editar** junto a **nombre**.</span><span class="sxs-lookup"><span data-stu-id="efe00-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="efe00-173">Use la lista desplegable para elegir otro dominio.</span><span class="sxs-lookup"><span data-stu-id="efe00-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="efe00-174">Seleccione **Guardar** y, a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="efe00-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="efe00-175">Repita este proceso para todas las listas de distribución o grupos que estén asociados al dominio que quiere quitar.</span><span class="sxs-lookup"><span data-stu-id="efe00-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="efe00-176">Paso 3: quitar el dominio anterior</span><span class="sxs-lookup"><span data-stu-id="efe00-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="efe00-177">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="efe00-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="efe00-178">En el centro de administración, vaya a la página de **configuración** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="efe00-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="efe00-179">En el centro de administración, vaya a la página de **configuración** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="efe00-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="efe00-180">En la página **dominios** , seleccione el dominio que quiera quitar.</span><span class="sxs-lookup"><span data-stu-id="efe00-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="efe00-181">En el panel derecho, seleccione **quitar**.</span><span class="sxs-lookup"><span data-stu-id="efe00-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="efe00-182">Siga los mensajes adicionales y, a continuación, seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="efe00-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="efe00-183">¿Cuánto tiempo tarda un dominio en quitarse?</span><span class="sxs-lookup"><span data-stu-id="efe00-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="efe00-184">Microsoft 365 puede tardar hasta 5 minutos en quitar un dominio si no se hace referencia a él en muchos lugares como, por ejemplo, grupos de seguridad, listas de distribución, usuarios y grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="efe00-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="efe00-185">Si hay muchas referencias que usan el dominio, el dominio puede tardar varias horas (o incluso un día) en quitarse.</span><span class="sxs-lookup"><span data-stu-id="efe00-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="efe00-p113">Si tiene cientos o miles de usuarios, use PowerShell para consultar todos los usuarios y moverlos a otro dominio. En caso contrario, es posible que falten usuarios en la interfaz y que, cuando vaya a quitar el dominio, no pueda y no sepa por qué. Vea [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para obtener más información. Para establecer el dominio predeterminado, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="efe00-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="efe00-190">¿Sigue necesitando ayuda?</span><span class="sxs-lookup"><span data-stu-id="efe00-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="efe00-191">No puede quitar el dominio [". onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="efe00-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="efe00-p114">¿Todavía no funciona? Puede que su dominio necesite quitarse manualmente. [Llámenos](../contact-support-for-business-products.md) y le ayudaremos.</span><span class="sxs-lookup"><span data-stu-id="efe00-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="efe00-195">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="efe00-195">Related articles</span></span>

[<span data-ttu-id="efe00-196">Preguntas más frecuentes de dominios</span><span class="sxs-lookup"><span data-stu-id="efe00-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="efe00-197">Obtener ayuda con Office 365 dominios</span><span class="sxs-lookup"><span data-stu-id="efe00-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="efe00-198">Cambiar a otro plan de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="efe00-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="efe00-199">Cancelar la suscripción</span><span class="sxs-lookup"><span data-stu-id="efe00-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
