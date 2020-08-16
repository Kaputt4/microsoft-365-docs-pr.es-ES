---
title: Asignar licencias a los usuarios
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Obtenga información sobre cómo asignar las licencias a los usuarios.
ms.date: 08/14/2020
ms.openlocfilehash: e1f28107f7774fa4eccbecb3882cbd002a6eea1a
ms.sourcegitcommit: 919b5d0f33b41b4beaca5fbb06e1c75d65027b7e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2020
ms.locfileid: "46757562"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="9c220-103">Asignar licencias a los usuarios</span><span class="sxs-lookup"><span data-stu-id="9c220-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9c220-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="9c220-104">The admin center is changing.</span></span> <span data-ttu-id="9c220-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9c220-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="9c220-106">Puede asignar licencias a los usuarios en la página **usuarios activos** o en la página **licencias**.</span><span class="sxs-lookup"><span data-stu-id="9c220-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="9c220-107">El método que use dependerá de si desea asignar licencias de producto a usuarios específicos o si quiere asignar licencias de usuarios a productos específicos.</span><span class="sxs-lookup"><span data-stu-id="9c220-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="9c220-108">[Obtenga información sobre cómo agregar un usuario y asignar una licencia al mismo tiempo](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="9c220-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9c220-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="9c220-109">Before you begin</span></span>

- <span data-ttu-id="9c220-110">Debe ser un administrador global, de licencia o de usuarios para asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="9c220-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="9c220-111">Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9c220-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="9c220-112">Puede [asignar licencias a cuentas de usuario con PowerShell de Office 365](https://go.microsoft.com/fwlink/p/?linkid=850410).</span><span class="sxs-lookup"><span data-stu-id="9c220-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="9c220-113">Para usar las licencias basadas en grupos, vea [Asignar licencias a usuarios por la pertenencia a grupos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="9c220-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="9c220-114">Algunos servicios, como Sway, se asignan automáticamente a los usuarios y no es necesario que los asigne individualmente.</span><span class="sxs-lookup"><span data-stu-id="9c220-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="9c220-115">Use la página de licencias para asignar licencias a los usuarios</span><span class="sxs-lookup"><span data-stu-id="9c220-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="9c220-116">Al usar la página de **licencias** de para asignar licencias, asigna licencias para un producto específico a un máximo de 20 usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="9c220-117">En la página de **licencias**, verá una lista de todos los productos para los que tiene suscripciones.</span><span class="sxs-lookup"><span data-stu-id="9c220-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="9c220-118">También verá el número total de licencias de cada producto, cuántas licencias están asignadas y cuántas están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9c220-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="9c220-119">En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="9c220-120">Seleccione un producto.</span><span class="sxs-lookup"><span data-stu-id="9c220-120">Select a product.</span></span>
3. <span data-ttu-id="9c220-121">En la página de detalles del producto, seleccione **Asignar licencias**.</span><span class="sxs-lookup"><span data-stu-id="9c220-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="9c220-122">En el panel **asignar licencias a usuarios**, empiece a escribir un nombre y elíjalo en los resultados para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="9c220-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="9c220-123">Puede agregar hasta 20 usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="9c220-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="9c220-124">Seleccione **activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="9c220-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="9c220-125">Cuando termine, seleccione **Asignar** y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="9c220-126">Si hay un conflicto, se muestra un mensaje que indica cuál es el problema y cómo corregirlo.</span><span class="sxs-lookup"><span data-stu-id="9c220-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="9c220-127">Por ejemplo, si seleccionó licencias que contienen servicios en conflicto, el mensaje de error indica que debe revisar los servicios incluidos en cada licencia y volver a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="9c220-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="9c220-128">Cambiar las aplicaciones y los servicios a los que tiene acceso un usuario</span><span class="sxs-lookup"><span data-stu-id="9c220-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="9c220-129">En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="9c220-130">En la página **Licencias**, seleccione la fila para un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="9c220-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="9c220-131">En el panel derecho, active o desactive las aplicaciones y servicios a los que quiere dar o quitar acceso.</span><span class="sxs-lookup"><span data-stu-id="9c220-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="9c220-132">Cuando haya terminado, seleccione **guardar** y haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="9c220-133">Use la página Usuarios activos para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="9c220-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="9c220-134">Cuando usa la página **Usuarios activos** para asignar licencias, asigna licencias de usuarios a los productos.</span><span class="sxs-lookup"><span data-stu-id="9c220-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="9c220-135">Asignar licencias a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="9c220-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="9c220-136">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9c220-137">Seleccione los círculos que se encuentran junto a los nombres de los usuarios a los que quiere asignarles licencias.</span><span class="sxs-lookup"><span data-stu-id="9c220-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="9c220-138">En la parte superior, seleccione **más opciones (...)** y seleccione **administrar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="9c220-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="9c220-139">En el panel **administrar licencias de producto**, seleccione **agregar a las asignaciones de licencias de producto existentes** \> **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c220-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9c220-140">En el panel **Agregar a los productos existentes**, cambie el botón a la posición de **Activado** para la licencia que quiere que tengan los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="9c220-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="9c220-141">De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="9c220-142">Puede limitar los servicios que están disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="9c220-143">Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="9c220-144">En la parte inferior del panel, seleccione **agregar** \> **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="9c220-145">Asignar licencias a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="9c220-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="9c220-146">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9c220-147">Seleccione los cuadros junto a los nombres de los usuarios a los que quiere asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="9c220-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="9c220-148">En el panel **Acciones en masa**, elija **Editar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="9c220-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="9c220-149">En el panel **Asignar productos**, seleccione **Agregar a las asignaciones de licencias de producto existentes** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c220-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9c220-150">Sitúe el botón en la posición **Activado** para las licencias que quiere que tengan los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="9c220-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="9c220-151">De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="9c220-152">Puede limitar los servicios que están disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="9c220-153">Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="9c220-154">En la parte inferior del panel **Agregar a los productos existentes**, seleccione **Agregar** \> **Cerrar** \> **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="9c220-155">Asignar licencias a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="9c220-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="9c220-156">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9c220-157">Seleccione los cuadros junto a los nombres de los usuarios a los que quiere asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="9c220-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="9c220-158">En el panel **Acciones en masa**, elija **Editar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="9c220-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="9c220-159">En el panel **Asignar productos**, seleccione **Agregar a las asignaciones de licencias de producto existentes** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c220-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9c220-160">Sitúe el botón en la posición **Activado** para las licencias que quiere que tengan los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="9c220-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="9c220-161">De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="9c220-162">Puede limitar los servicios que están disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="9c220-163">Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c220-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="9c220-164">En la parte inferior del panel **Agregar a los productos existentes**, seleccione **Agregar** \> **Cerrar** \> **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="9c220-165">Asignar licencias a un usuario</span><span class="sxs-lookup"><span data-stu-id="9c220-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="9c220-166">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9c220-167">Seleccione la fila del usuario al que quiere asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="9c220-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="9c220-168">En el panel derecho, seleccione **licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9c220-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="9c220-169">Expanda la sección **licencias**, active las casillas de las licencias que quiera asignar y seleccione **guardar los cambios**.</span><span class="sxs-lookup"><span data-stu-id="9c220-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="9c220-170">Asignar licencias a un usuario</span><span class="sxs-lookup"><span data-stu-id="9c220-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="9c220-171">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9c220-172">Seleccione el cuadro junto al nombre del usuario al que quiere asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="9c220-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="9c220-173">En el panel derecho, en la fila **licencias de producto**, seleccione **editar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="9c220-174">En el panel **Licencias de producto**, sitúe el botón en la posición **Activada** para la licencia que quiera asignar a este usuario.</span><span class="sxs-lookup"><span data-stu-id="9c220-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="9c220-175">De manera predeterminada, todos los servicios asociados a esa licencia se asignan automáticamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="9c220-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="9c220-176">Puede limitar los servicios que están disponibles para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9c220-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="9c220-177">Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tenga el usuario.</span><span class="sxs-lookup"><span data-stu-id="9c220-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="9c220-178">En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="9c220-179">Asignar licencias a un usuario</span><span class="sxs-lookup"><span data-stu-id="9c220-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="9c220-180">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9c220-181">Seleccione el cuadro junto al nombre del usuario al que quiere asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="9c220-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="9c220-182">En el panel derecho, en la fila **licencias de producto**, seleccione **editar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="9c220-183">En el panel **Licencias de producto**, sitúe el botón en la posición **Activada** para la licencia que quiera asignar a este usuario.</span><span class="sxs-lookup"><span data-stu-id="9c220-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="9c220-184">De manera predeterminada, todos los servicios asociados a esa licencia se asignan automáticamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="9c220-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="9c220-185">Puede limitar los servicios que están disponibles para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9c220-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="9c220-186">Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tenga el usuario.</span><span class="sxs-lookup"><span data-stu-id="9c220-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="9c220-187">En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="9c220-188">Asignar una licencia a un usuario invitado</span><span class="sxs-lookup"><span data-stu-id="9c220-188">Assign a license to a guest user</span></span>

<span data-ttu-id="9c220-189">Puede invitar a usuarios invitados a colaborar con su organización en el centro de administración de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9c220-189">You can invite guest users to collaborate with your organization in Azure Active directory admin center.</span></span> <span data-ttu-id="9c220-190">Para obtener más información sobre los usuarios invitados, vea [¿Qué es el acceso de usuarios invitados en Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="9c220-190">To learn about guess users, see [What is guest user access in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b)</span></span> <span data-ttu-id="9c220-191">Si no tiene usuarios invitados, vea [Inicio rápido: agregar usuarios invitados al directorio de Azure Portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="9c220-191">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c220-192">Para poder realizar estos pasos, debe ser un administrador global.</span><span class="sxs-lookup"><span data-stu-id="9c220-192">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="9c220-193">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Centro de administración de Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="9c220-193">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="9c220-194">En el panel de navegación, seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="9c220-194">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="9c220-195">En la página **Usuarios | Todos los usuarios (vista previa)**, seleccione **Agregar filtros**.</span><span class="sxs-lookup"><span data-stu-id="9c220-195">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="9c220-196">En el menú **Elegir un campo**, seleccione **Tipo de usuario** y, después, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-196">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="9c220-197">En el menú siguiente, seleccione **Invitado**.</span><span class="sxs-lookup"><span data-stu-id="9c220-197">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="9c220-198">En la lista de resultados, seleccione el usuario que necesita una licencia.</span><span class="sxs-lookup"><span data-stu-id="9c220-198">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="9c220-199">En **Administrar**, seleccione **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="9c220-199">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="9c220-200">Seleccione **Asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="9c220-200">Select **Assignments**.</span></span>
9. <span data-ttu-id="9c220-201">En la página **Actualizar asignaciones de licencia**, seleccione el producto al que quiere asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="9c220-201">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="9c220-202">En la parte derecha, desactive las casillas de los servicios a los que no quiere que el usuario invitado tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="9c220-202">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="9c220-203">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9c220-203">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9c220-204">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9c220-204">Next steps</span></span>

<span data-ttu-id="9c220-205">Si los usuarios aún no tienen aplicaciones de Office instaladas, puede compartir la [Guía de inicio rápido para empleados](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) con los usuarios para que configuren todo, como [cómo descargar e instalar Microsoft 365 u Office 2019 en un equipo Windows o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y [cómo configurar las aplicaciones de Office y el correo electrónico en un dispositivo móvil](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="9c220-205">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="9c220-206">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="9c220-206">Related content</span></span>

<span data-ttu-id="9c220-207">[Entender las suscripciones y las licencias](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9c220-207">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="9c220-208">[Cancelar asignación a licencias de usuarios](remove-licenses-from-users.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9c220-208">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="9c220-209">[Comprar o quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9c220-209">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>