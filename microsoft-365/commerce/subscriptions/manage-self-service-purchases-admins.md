---
title: Administrar compras de autoservicio (administradores)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce_ssp
search.appverid:
- MET150
description: Los administradores pueden aprender a administrar las compras de autoservicio realizadas por los usuarios de su organización.
ms.date: 03/26/2021
ms.openlocfilehash: af1786b7e3d1b3e4a03202d605d734271acb1da5
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333343"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="ca6a6-103">Administrar compras de autoservicio (administrador)</span><span class="sxs-lookup"><span data-stu-id="ca6a6-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="ca6a6-104">Como administrador, puede ver las compras de autoservicio realizadas por personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="ca6a6-105">Verá el nombre del producto, el nombre del comprador, las suscripciones compradas, la fecha de expiración, el precio de compra y los usuarios asignados para cada compra de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="ca6a6-106">Si la organización lo requiere, puede desactivar las compras de autoservicio por producto a través de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="ca6a6-107">Tiene las mismas directivas de administración de datos y acceso a los productos comprados a través de la compra de autoservicio o de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="ca6a6-108">También puede controlar si los usuarios de su organización pueden realizar compras de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="ca6a6-109">Para obtener más información, [vea Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ca6a6-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="ca6a6-110">Ver suscripciones de autoservicio</span><span class="sxs-lookup"><span data-stu-id="ca6a6-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca6a6-111">En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ca6a6-112">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-112">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ca6a6-113">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="ca6a6-114">En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Autoservicio.**</span><span class="sxs-lookup"><span data-stu-id="ca6a6-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="ca6a6-115">Para ver más detalles sobre una suscripción, elija una de la lista.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="ca6a6-116">Ver quién tiene licencias para una suscripción de compra de autoservicio</span><span class="sxs-lookup"><span data-stu-id="ca6a6-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="ca6a6-117">Como administrador, no puede asignar o cancelar la asignación de licencias para una suscripción de compra de autoservicio adquirida por un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="ca6a6-118">Puede [apoderarse de una suscripción de compra de autoservicio](#take-over-a-self-service-purchase-subscription) y, a continuación, asignar o cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca6a6-119">En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="ca6a6-120">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="ca6a6-121">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="ca6a6-122">Seleccione el icono de filtro y, a continuación, **elija Autoservicio.**</span><span class="sxs-lookup"><span data-stu-id="ca6a6-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="ca6a6-123">Seleccione un producto para ver las licencias asignadas a personas.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="ca6a6-124">Si hay varias compras para un producto, ese producto  solo aparece una vez y la columna Cantidad disponible muestra el total de todas las suscripciones compradas para ese producto.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="ca6a6-125">La **lista** de usuarios se agrupa por los nombres de las personas que realizaron compras de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="ca6a6-126">Para exportar una lista de usuarios con licencias para estas suscripciones, elija las suscripciones que desea exportar y, a continuación, **elija Exportar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="ca6a6-127">Deshabilitar o habilitar compras de autoservicio</span><span class="sxs-lookup"><span data-stu-id="ca6a6-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="ca6a6-128">Puede deshabilitar o habilitar compras de autoservicio para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="ca6a6-129">El módulo de PowerShell de **MSCommerce** incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras de autoservicio y para qué productos.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="ca6a6-130">Puede usar el módulo **MSCommerce** PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="ca6a6-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="ca6a6-131">Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase,** ya sea que esté habilitado o deshabilitado por el producto</span><span class="sxs-lookup"><span data-stu-id="ca6a6-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="ca6a6-132">Ver una lista de productos aplicables y si la compra de autoservicio está habilitada o deshabilitada</span><span class="sxs-lookup"><span data-stu-id="ca6a6-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="ca6a6-133">Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo</span><span class="sxs-lookup"><span data-stu-id="ca6a6-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="ca6a6-134">Para obtener más información, [vea Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ca6a6-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="ca6a6-135">Centralizar licencias en una sola suscripción</span><span class="sxs-lookup"><span data-stu-id="ca6a6-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="ca6a6-136">Puede asignar licencias existentes o comprar suscripciones adicionales a través de acuerdos existentes para usuarios asignados a compras de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="ca6a6-137">Después de asignar estas licencias compradas de forma centralizada, puede solicitar que los compradores cancelen sus suscripciones existentes.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca6a6-138">En el Centro de administración, vaya a la página **Servicios de compra** de > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">facturación.</a></span><span class="sxs-lookup"><span data-stu-id="ca6a6-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ca6a6-139">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la página **Servicios de compra** de > **facturación.**</span><span class="sxs-lookup"><span data-stu-id="ca6a6-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ca6a6-140">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la página **Servicios de compra** de > **facturación.**</span><span class="sxs-lookup"><span data-stu-id="ca6a6-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="ca6a6-141">Busque y elija el producto que desea comprar y, a continuación, elija **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="ca6a6-142">Complete los pasos restantes para completar la compra.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="ca6a6-143">Siga los pasos de [Ver](#view-who-has-licenses-for-a-self-service-purchase-subscription) quién tiene licencias para una suscripción comprada por autoservicio para exportar una lista de usuarios a los que hacer referencia en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="ca6a6-144">Asignar licencias a todos los usuarios que tienen una licencia en la otra suscripción.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="ca6a6-145">Para ver los pasos [completos, vea Asignar licencias a los usuarios.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="ca6a6-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="ca6a6-146">Póngase en contacto con la persona que compró la suscripción de compra de autoservicio y pídale que [la cancele.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="ca6a6-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="ca6a6-147">Asumir una suscripción de compra de autoservicio</span><span class="sxs-lookup"><span data-stu-id="ca6a6-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="ca6a6-148">Puede hacerse cargo de una suscripción de compra de autoservicio realizada por un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="ca6a6-149">Al asumir una suscripción de compra de autoservicio, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="ca6a6-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="ca6a6-150">Mueva los usuarios a una suscripción diferente y cancele la suscripción original.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="ca6a6-151">Cancele la suscripción de compra de autoservicio y quite las licencias de los usuarios asignados.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="ca6a6-152">Mover usuarios a una suscripción diferente</span><span class="sxs-lookup"><span data-stu-id="ca6a6-152">Move users to a different subscription</span></span>

<span data-ttu-id="ca6a6-153">Al mover usuarios a una suscripción diferente, la suscripción antigua se cancela automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="ca6a6-154">El usuario que compró originalmente la suscripción de compra de autoservicio recibe un correo electrónico que indica que se canceló la suscripción.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="ca6a6-155">Debe tener una licencia disponible para cada usuario al que se está moviendo en la suscripción a la que va a mover usuarios.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca6a6-156">En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ca6a6-157">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la página  > **Facturación de sus** productos.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ca6a6-158">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la página  > **Facturación de sus** productos.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="ca6a6-159">En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Autoservicio.**</span><span class="sxs-lookup"><span data-stu-id="ca6a6-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="ca6a6-160">Selecciona la suscripción que quieras asumir.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="ca6a6-161">En la página detalles de la suscripción, en la sección **Suscripciones y** configuración, seleccione Tomar el control de **esta suscripción.**</span><span class="sxs-lookup"><span data-stu-id="ca6a6-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="ca6a6-162">En el panel derecho, seleccione **Mover usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="ca6a6-163">Seleccione el producto al que desea mover los usuarios y, a continuación, **seleccione Mover usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="ca6a6-164">En el **cuadro Mover usuarios a,** seleccione **Mover usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="ca6a6-165">El proceso de movimiento puede tardar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-165">The move process might take several minutes.</span></span> <span data-ttu-id="ca6a6-166">No cierre el explorador mientras se ejecuta el proceso.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="ca6a6-167">Cuando finalice el proceso de movimiento, cierre el **panel Mover completado**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="ca6a6-168">En la página de detalles de la suscripción, el estado **de** suscripción de la suscripción comprada por autoservicio se muestra como **Eliminado**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="ca6a6-169">Cancelar una suscripción de compra de autoservicio</span><span class="sxs-lookup"><span data-stu-id="ca6a6-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="ca6a6-170">Cuando decide cancelar una suscripción de compra de autoservicio, los usuarios con licencias pierden el acceso al producto.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="ca6a6-171">El usuario que compró originalmente la suscripción de compra de autoservicio recibe un correo electrónico que indica que se canceló la suscripción.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca6a6-172">En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ca6a6-173">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la página  > **Facturación de sus** productos.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ca6a6-174">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la página  > **Facturación de sus** productos.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="ca6a6-175">En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Autoservicio.**</span><span class="sxs-lookup"><span data-stu-id="ca6a6-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="ca6a6-176">Seleccione la suscripción que quiere cancelar.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="ca6a6-177">En la página detalles de la suscripción, en la sección **Suscripciones y** configuración, seleccione Tomar el control de **esta suscripción.**</span><span class="sxs-lookup"><span data-stu-id="ca6a6-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="ca6a6-178">En el panel derecho, seleccione **Cancelar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="ca6a6-179">Seleccione un motivo para la cancelación en la lista desplegable y, a continuación, **seleccione Cancelar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="ca6a6-180">En el **cuadro ¿Está seguro de que desea cancelar?** seleccione **Cancelar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="ca6a6-181">Cierre el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-181">Close the right pane.</span></span>
9. <span data-ttu-id="ca6a6-182">En la página de detalles de la suscripción, el **estado de suscripción** se muestra como **Eliminado**.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="ca6a6-183">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="ca6a6-183">Need help?</span></span> <span data-ttu-id="ca6a6-184">Póngase en contacto con nosotros.</span><span class="sxs-lookup"><span data-stu-id="ca6a6-184">Contact us.</span></span>

<span data-ttu-id="ca6a6-185">Para obtener preguntas comunes acerca de las compras de autoservicio, consulta Preguntas más frecuentes sobre compras [de autoservicio.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="ca6a6-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="ca6a6-186">Si tiene preguntas o necesita ayuda con las compras de autoservicio, póngase [en contacto con el soporte técnico](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="ca6a6-186">If you have questions or need help with self-service purchases, [contact support](../../business-video/get-help-support.md).</span></span>
