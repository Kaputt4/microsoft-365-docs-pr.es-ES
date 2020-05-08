---
title: Administrar aplicaciones de software como servicio de su organización
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
search.appverid: MET150
description: Obtenga información sobre cómo activar y administrar aplicaciones de terceros en el centro de administración de Microsoft 365.
ms.openlocfilehash: eb2826a4b0c69d61eb35a9dfff37e9dc2dd6ad71
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141193"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="18306-103">Administrar suscripciones de aplicaciones de terceros para la organización</span><span class="sxs-lookup"><span data-stu-id="18306-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="18306-104">El centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="18306-104">The admin center is changing.</span></span> <span data-ttu-id="18306-105">Si su experiencia no coincide con los detalles que se presentan aquí, vea [acerca del nuevo centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="18306-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="18306-106">Puede administrar las licencias y la facturación de aplicaciones de terceros en el centro de administración de Microsoft 365 con el modo de vista previa activado.</span><span class="sxs-lookup"><span data-stu-id="18306-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="18306-107">Las características actualizadas incluyen una administración de suscripciones mejorada, un mejor acceso a la información de facturación y una mayor flexibilidad para la administración de facturas.</span><span class="sxs-lookup"><span data-stu-id="18306-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="18306-108">La administración de suscripciones se basa en la plataforma de comercio actualizada de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18306-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="18306-109">Esto se aplica a las aplicaciones de software como un servicio que los clientes compren directamente o de un proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="18306-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="18306-110">Cómo obtener aplicaciones de software como servicio</span><span class="sxs-lookup"><span data-stu-id="18306-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="18306-111">Hay varias formas de comprar aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="18306-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="18306-112">**Compra directa** : los clientes pueden comprar directamente suscripciones de [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)o [AppSource](https://www.appsource.com/).</span><span class="sxs-lookup"><span data-stu-id="18306-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="18306-113">**Compra de asociados** : trabaje con un Partner a través del centro de asociados para comprar suscripciones.</span><span class="sxs-lookup"><span data-stu-id="18306-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="18306-114">**Propuesta de Microsoft** : responda a una propuesta de ventas de Microsoft que incluya aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="18306-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="18306-115">Una vez que los clientes compren las aplicaciones y acepten el contrato de cliente de Microsoft, podrán administrarlos en el centro de administración de Microsoft 365 o en Microsoft Store for Business.</span><span class="sxs-lookup"><span data-stu-id="18306-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="18306-116">Los proveedores de aplicaciones venden sus aplicaciones a una tasa plana o mediante la compra de licencias para usuarios.</span><span class="sxs-lookup"><span data-stu-id="18306-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="18306-117">**Tasa plana** : también se denomina precio basado en el sitio, el precio de las aplicaciones es mensual o anual.</span><span class="sxs-lookup"><span data-stu-id="18306-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="18306-118">En la página de la aplicación, la cantidad de la licencia aparece como ilimitada.</span><span class="sxs-lookup"><span data-stu-id="18306-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="18306-119">**Licencias** : el precio de las aplicaciones se asigna por licencia.</span><span class="sxs-lookup"><span data-stu-id="18306-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="18306-120">Los clientes asignan licencias a todos los usuarios de la organización</span><span class="sxs-lookup"><span data-stu-id="18306-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="18306-121">Regiones admitidas</span><span class="sxs-lookup"><span data-stu-id="18306-121">Supported regions</span></span>

<span data-ttu-id="18306-122">La compatibilidad con aplicaciones de terceros está disponible en estas regiones:</span><span class="sxs-lookup"><span data-stu-id="18306-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="18306-123">Argentina</span><span class="sxs-lookup"><span data-stu-id="18306-123">Argentina</span></span>
- <span data-ttu-id="18306-124">Australia</span><span class="sxs-lookup"><span data-stu-id="18306-124">Australia</span></span>
- <span data-ttu-id="18306-125">Canadá</span><span class="sxs-lookup"><span data-stu-id="18306-125">Canada</span></span>
- <span data-ttu-id="18306-126">Chile</span><span class="sxs-lookup"><span data-stu-id="18306-126">Chile</span></span>
- <span data-ttu-id="18306-127">Francia</span><span class="sxs-lookup"><span data-stu-id="18306-127">France</span></span>
- <span data-ttu-id="18306-128">Alemania</span><span class="sxs-lookup"><span data-stu-id="18306-128">Germany</span></span>
- <span data-ttu-id="18306-129">Grecia</span><span class="sxs-lookup"><span data-stu-id="18306-129">Greece</span></span>
- <span data-ttu-id="18306-130">Puerto Rico</span><span class="sxs-lookup"><span data-stu-id="18306-130">Puerto Rico</span></span>
- <span data-ttu-id="18306-131">Sudáfrica</span><span class="sxs-lookup"><span data-stu-id="18306-131">South Africa</span></span>
- <span data-ttu-id="18306-132">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="18306-132">United Kingdom</span></span>
- <span data-ttu-id="18306-133">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="18306-133">United States</span></span>
- <span data-ttu-id="18306-134">Europa occidental</span><span class="sxs-lookup"><span data-stu-id="18306-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="18306-135">Activar aplicaciones de terceros</span><span class="sxs-lookup"><span data-stu-id="18306-135">Activate third-party apps</span></span>

<span data-ttu-id="18306-136">Los administradores deben activar aplicaciones de terceros antes de asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="18306-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="18306-137">Estas aplicaciones se activan en el portal del proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="18306-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="18306-138">En el centro de administración, vaya a la página **facturación** > **de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicaciones</a> de productos.</span><span class="sxs-lookup"><span data-stu-id="18306-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="18306-139">Busque y seleccione la aplicación que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="18306-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="18306-140">En **configuración & acciones**, seleccione **administrar en el portal de Publisher**.</span><span class="sxs-lookup"><span data-stu-id="18306-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="18306-141">Se le dirigirá al sitio del editor de la aplicación donde puede activar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18306-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="18306-142">Administrar aplicaciones de terceros</span><span class="sxs-lookup"><span data-stu-id="18306-142">Manage third-party apps</span></span>

<span data-ttu-id="18306-143">Los administradores administran aplicaciones de terceros en dos ubicaciones: el centro de administración de Microsoft 365 y el portal del proveedor de aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="18306-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="18306-144">Esto es lo que puede hacer en cada portal.</span><span class="sxs-lookup"><span data-stu-id="18306-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="18306-145">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="18306-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="18306-146">Portal del publicador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="18306-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="18306-147">Cambiar la cantidad de licencias</span><span class="sxs-lookup"><span data-stu-id="18306-147">Change license quantity</span></span> <br> <span data-ttu-id="18306-148">Administrar la forma de pago de la factura</span><span class="sxs-lookup"><span data-stu-id="18306-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="18306-149">Administrar la forma de pago de la factura</span><span class="sxs-lookup"><span data-stu-id="18306-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="18306-150">Cambiar el método de pago (tarjeta de crédito)</span><span class="sxs-lookup"><span data-stu-id="18306-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="18306-151">Ver factura</span><span class="sxs-lookup"><span data-stu-id="18306-151">View invoice</span></span> <br> <span data-ttu-id="18306-152">Cancelar la suscripción a la aplicación</span><span class="sxs-lookup"><span data-stu-id="18306-152">Cancel app subscription</span></span> | <span data-ttu-id="18306-153">Configurar la aplicación (una vez por cada aplicación)</span><span class="sxs-lookup"><span data-stu-id="18306-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="18306-154">Asignar licencias a los usuarios</span><span class="sxs-lookup"><span data-stu-id="18306-154">Assign licenses to users</span></span> <br> <span data-ttu-id="18306-155">Soporte técnico</span><span class="sxs-lookup"><span data-stu-id="18306-155">Technical support</span></span> |

<span data-ttu-id="18306-156">Una vez activada la aplicación, permanece activa a menos que se cancele, expire o si no se mantiene el pago actual.</span><span class="sxs-lookup"><span data-stu-id="18306-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="18306-157">Estos eventos cambian el estado de la aplicación a deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="18306-157">These events change the app status to disabled.</span></span> <span data-ttu-id="18306-158">Una vez que una aplicación está deshabilitada, no se puede reactivar.</span><span class="sxs-lookup"><span data-stu-id="18306-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="18306-159">Para seguir usando la aplicación, compre otra copia de la misma.</span><span class="sxs-lookup"><span data-stu-id="18306-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="18306-160">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="18306-160">Assign licenses</span></span>

<span data-ttu-id="18306-161">Los administradores deben activar aplicaciones de terceros antes de asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="18306-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="18306-162">Se activan en el portal del proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="18306-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="18306-163">En la página aplicación, en **configuración & acciones**, seleccione el vínculo para asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="18306-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="18306-164">En el centro de administración, vaya a la página **facturación** > **de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicaciones</a> de productos.</span><span class="sxs-lookup"><span data-stu-id="18306-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="18306-165">Busque y seleccione la aplicación que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="18306-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="18306-166">En **configuración & acciones**, seleccione el vínculo para **administrar en el portal de Publisher**.</span><span class="sxs-lookup"><span data-stu-id="18306-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="18306-167">Cambiar la cantidad de licencias</span><span class="sxs-lookup"><span data-stu-id="18306-167">Change license quantity</span></span>

<span data-ttu-id="18306-168">Los administradores pueden cambiar el número de licencias que pertenecen a su organización.</span><span class="sxs-lookup"><span data-stu-id="18306-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="18306-169">Esto solo se aplica a las aplicaciones adquiridas con precios basados en el asiento.</span><span class="sxs-lookup"><span data-stu-id="18306-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="18306-170">En el centro de administración, vaya a la página **facturación** > **de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicaciones</a> de productos.</span><span class="sxs-lookup"><span data-stu-id="18306-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="18306-171">Busque y seleccione la aplicación que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="18306-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="18306-172">Seleccione **cambiar cantidad de licencia**.</span><span class="sxs-lookup"><span data-stu-id="18306-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="18306-173">Administrar métodos de pago</span><span class="sxs-lookup"><span data-stu-id="18306-173">Manage payment methods</span></span>

<span data-ttu-id="18306-174">Cada aplicación de software como un servicio tiene asignado un perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="18306-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="18306-175">Los perfiles de facturación le permiten personalizar qué productos se incluyen en su factura y cómo pagar sus facturas.</span><span class="sxs-lookup"><span data-stu-id="18306-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="18306-176">Entre ellos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="18306-176">They include:</span></span>

- <span data-ttu-id="18306-177">**Métodos de pago** : tarjetas de crédito o cheque/transferencia bancaria</span><span class="sxs-lookup"><span data-stu-id="18306-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="18306-178">**Información de contacto** : dirección de facturación y nombre de contacto</span><span class="sxs-lookup"><span data-stu-id="18306-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="18306-179">**Roles** : roles que permiten cambiar el perfil de facturación, pagar facturas o usar el método de pago en el perfil de facturación para realizar la compra.</span><span class="sxs-lookup"><span data-stu-id="18306-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="18306-180">Para obtener más información acerca de los perfiles de facturación, consulte Understanding [Billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="18306-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="18306-181">Cambiar el perfil de facturación en una suscripción de aplicación de software como un servicio</span><span class="sxs-lookup"><span data-stu-id="18306-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="18306-182">En el centro de administración, vaya a la página **facturación** > **de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicaciones</a> de productos.</span><span class="sxs-lookup"><span data-stu-id="18306-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="18306-183">Busque y seleccione la aplicación que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="18306-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="18306-184">Junto a **Perfil de facturación**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="18306-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="18306-185">Para obtener más información sobre las facturas, consulte [comprender la factura](billing-and-payments/understand-your-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="18306-185">For more information on invoices, see [Understand your invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="18306-186">Cancelar una suscripción a una aplicación de software como servicio</span><span class="sxs-lookup"><span data-stu-id="18306-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="18306-187">Puede cancelar una aplicación de software como servicio desde la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18306-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="18306-188">En el centro de administración, vaya a la página **facturación** > **de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicaciones</a> de productos.</span><span class="sxs-lookup"><span data-stu-id="18306-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="18306-189">Busque y seleccione la aplicación que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="18306-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="18306-190">En **configuración & acciones**, seleccione **Cancelar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="18306-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
