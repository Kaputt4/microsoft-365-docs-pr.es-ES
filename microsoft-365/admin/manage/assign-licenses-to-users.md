---
title: Asignar licencias a los usuarios
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: Asigne licencias dependiendo de si quiere asignar licencias de producto a usuarios específicos o asignar licencias de usuarios a un producto específico.
ms.date: 04/26/2021
ms.openlocfilehash: 987572ae15ffdf6d2042c6e54eba586cd39ebcb9
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393720"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="90714-103">Asignar licencias a los usuarios</span><span class="sxs-lookup"><span data-stu-id="90714-103">Assign licenses to users</span></span>

<span data-ttu-id="90714-104">Puede asignar licencias a los usuarios en la página **usuarios activos** o en la página **licencias**.</span><span class="sxs-lookup"><span data-stu-id="90714-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="90714-105">El método que use dependerá de si desea asignar licencias de producto a usuarios específicos o si quiere asignar licencias de usuarios a productos específicos.</span><span class="sxs-lookup"><span data-stu-id="90714-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="90714-106">Como administrador, no puede asignar o cancelar la asignación de licencias para una suscripción de compra de autoservicio adquirida por un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="90714-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="90714-107">Puede [apoderarse de una suscripción de compra de autoservicio](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) y, a continuación, asignar o cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="90714-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="90714-108">[Obtenga información sobre cómo agregar un usuario y asignar una licencia al mismo tiempo](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="90714-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="90714-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="90714-109">Before you begin</span></span>

- <span data-ttu-id="90714-110">Debe ser un administrador global, de licencia o de usuarios para asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="90714-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="90714-111">Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="90714-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="90714-112">Puede [asignar licencias de Microsoft 365 a cuentas de usuario con PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="90714-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="90714-113">Para usar las licencias basadas en grupos, vea [Asignar licencias a usuarios por la pertenencia a grupos en Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="90714-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="90714-114">Algunos servicios, como Sway, se asignan automáticamente a los usuarios y no es necesario que los asigne individualmente.</span><span class="sxs-lookup"><span data-stu-id="90714-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="90714-115">Use la página de licencias para asignar licencias a los usuarios</span><span class="sxs-lookup"><span data-stu-id="90714-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="90714-116">Al usar la página de **licencias** de para asignar licencias, asigna licencias para un producto específico a un máximo de 20 usuarios.</span><span class="sxs-lookup"><span data-stu-id="90714-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="90714-117">En la página de **licencias**, verá una lista de todos los productos para los que tiene suscripciones.</span><span class="sxs-lookup"><span data-stu-id="90714-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="90714-118">También verá el número total de licencias de cada producto, cuántas licencias están asignadas y cuántas están disponibles.</span><span class="sxs-lookup"><span data-stu-id="90714-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="90714-119">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="90714-120">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="90714-121">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="90714-122">Seleccione un producto.</span><span class="sxs-lookup"><span data-stu-id="90714-122">Select a product.</span></span>
3. <span data-ttu-id="90714-123">En la página de detalles del producto, seleccione **Asignar licencias**.</span><span class="sxs-lookup"><span data-stu-id="90714-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="90714-124">En el panel **asignar licencias a usuarios**, empiece a escribir un nombre y elíjalo en los resultados para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="90714-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="90714-125">Puede agregar hasta 20 usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="90714-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="90714-126">Seleccione **activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="90714-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="90714-127">Cuando termine, seleccione **Asignar** y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="90714-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="90714-128">Si hay un conflicto, se muestra un mensaje que indica cuál es el problema y cómo corregirlo.</span><span class="sxs-lookup"><span data-stu-id="90714-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="90714-129">Por ejemplo, si seleccionó licencias que contienen servicios en conflicto, el mensaje de error indica que debe revisar los servicios incluidos en cada licencia y volver a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="90714-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="90714-130">Cambiar las aplicaciones y los servicios a los que tiene acceso un usuario</span><span class="sxs-lookup"><span data-stu-id="90714-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="90714-131">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="90714-132">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="90714-133">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="90714-134">En la página **Licencias**, seleccione la fila para un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="90714-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="90714-135">En el panel derecho, active o desactive las aplicaciones y servicios a los que quiere dar o quitar acceso.</span><span class="sxs-lookup"><span data-stu-id="90714-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="90714-136">Cuando haya terminado, seleccione **guardar** y haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="90714-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="90714-137">Use la página Usuarios activos para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="90714-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="90714-138">Cuando usa la página **Usuarios activos** para asignar licencias, asigna licencias de usuarios a los productos.</span><span class="sxs-lookup"><span data-stu-id="90714-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="90714-139">Asignar licencias a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="90714-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="90714-140">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="90714-141">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="90714-142">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="90714-143">Seleccione los círculos que se encuentran junto a los nombres de los usuarios a los que quiere asignarles licencias.</span><span class="sxs-lookup"><span data-stu-id="90714-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="90714-144">En la parte superior, seleccione **Administrar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="90714-144">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="90714-145">En el panel **Administrar licencias de producto**, seleccione **Asignar más: mantener las licencias existentes y asignar más** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="90714-145">In the **Manage product licenses** pane, select **Assign more: Keep the existing licenses and assign more** \> **Next**.</span></span>
5. <span data-ttu-id="90714-146">En **Licencias**, seleccione la casilla de las licencias que desea que tengan los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="90714-146">Under **Licenses**, select the box for the license(s) that you want the selected users to have.</span></span>\
    <span data-ttu-id="90714-p107">De manera predeterminada, todos los servicios asociados a esas licencias se asignan automáticamente al usuario. Puede limitar los servicios disponibles para el usuario. Quite la selección de las casillas de los servicios que no quiere que tenga el usuario.</span><span class="sxs-lookup"><span data-stu-id="90714-p107">By default, all services associated with those licenses are automatically assigned to the users. You can limit which services are available to the users. Deselect the boxes for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="90714-150">En la parte inferior del panel, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="90714-150">At the bottom of the pane, select **Save changes**.</span></span>  
    <span data-ttu-id="90714-151">Es posible que tenga que comprar otras licencias si no tiene suficientes licencias para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="90714-151">You might have to buy additional licneses if you don't have enough licenses for everyone.</span></span>


> [!NOTE]
> <span data-ttu-id="90714-152">Si quiere asignar licencias para un gran número de usuarios, use la opción [Asignar licencias a usuarios por pertenencia a grupos en Azure Active Directory.](/azure/active-directory/enterprise-users/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="90714-152">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="90714-153">Asignar licencias a un usuario</span><span class="sxs-lookup"><span data-stu-id="90714-153">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="90714-154">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="90714-155">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="90714-156">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="90714-157">Seleccione la fila del usuario al que quiere asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="90714-157">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="90714-158">En el panel derecho, seleccione **licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="90714-158">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="90714-159">Expanda la sección **licencias**, active las casillas de las licencias que quiera asignar y seleccione **guardar los cambios**.</span><span class="sxs-lookup"><span data-stu-id="90714-159">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="90714-160">Asignar una licencia a un usuario invitado</span><span class="sxs-lookup"><span data-stu-id="90714-160">Assign a license to a guest user</span></span>

<span data-ttu-id="90714-161">Puede invitar a usuarios para colaborar con su organización en el centro de administración de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="90714-161">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="90714-162">Para obtener más información sobre los usuarios invitados, vea [¿Qué es el acceso de usuarios invitados en Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="90714-162">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="90714-163">Si no tiene usuarios invitados, vea [Inicio rápido: agregar usuarios invitados al directorio de Azure Portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="90714-163">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90714-164">Para poder realizar estos pasos, debe ser un administrador global.</span><span class="sxs-lookup"><span data-stu-id="90714-164">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="90714-165">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Centro de administración de Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="90714-165">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="90714-166">En el panel de navegación, seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="90714-166">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="90714-167">En la página **Usuarios | Todos los usuarios (vista previa)**, seleccione **Agregar filtros**.</span><span class="sxs-lookup"><span data-stu-id="90714-167">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="90714-168">En el menú **Elegir un campo**, seleccione **Tipo de usuario** y, después, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="90714-168">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="90714-169">En el menú siguiente, seleccione **Invitado**.</span><span class="sxs-lookup"><span data-stu-id="90714-169">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="90714-170">En la lista de resultados, seleccione el usuario que necesita una licencia.</span><span class="sxs-lookup"><span data-stu-id="90714-170">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="90714-171">En **Administrar**, seleccione **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="90714-171">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="90714-172">Seleccione **Asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="90714-172">Select **Assignments**.</span></span>
9. <span data-ttu-id="90714-173">En la página **Actualizar asignaciones de licencia**, seleccione el producto al que quiere asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="90714-173">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="90714-174">En la parte derecha, desactive las casillas de los servicios a los que no quiere que el usuario invitado tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="90714-174">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="90714-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="90714-175">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="90714-176">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="90714-176">Next steps</span></span>

<span data-ttu-id="90714-177">Si los usuarios aún no tienen aplicaciones de Office instaladas, puede compartir la [Guía de inicio rápido para empleados](../../business-video/employee-quick-setup.md) con los usuarios para que configuren todo, como [cómo descargar e instalar Microsoft 365 u Office 2019 en un equipo Windows o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y [cómo configurar las aplicaciones de Office y el correo electrónico en un dispositivo móvil](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="90714-177">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="90714-178">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="90714-178">Related content</span></span>

<span data-ttu-id="90714-179">[Entender las suscripciones y las licencias](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="90714-179">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="90714-180">[Cancelar asignación a licencias de usuarios](remove-licenses-from-users.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="90714-180">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="90714-181">[Comprar o quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="90714-181">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
