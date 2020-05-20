---
title: Administrar métodos de pago
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Obtenga información sobre cómo administrar los métodos de pago en el centro de administración de Microsoft 365.
ms.openlocfilehash: d31da19c10eb61719ba813d271dbdcf573a5aff3
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322164"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="3ba70-103">Administrar métodos de pago</span><span class="sxs-lookup"><span data-stu-id="3ba70-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="3ba70-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="3ba70-104">The admin center is changing.</span></span> <span data-ttu-id="3ba70-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3ba70-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="3ba70-106">Cuando compre productos o servicios empresariales de Microsoft, puede usar un método de pago existente o agregar uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="3ba70-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="3ba70-107">Puede usar una tarjeta de crédito o débito o una cuenta bancaria para pagar las cosas que compre.</span><span class="sxs-lookup"><span data-stu-id="3ba70-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="3ba70-108">Si la cuenta empresarial tiene un perfil de facturación y usted es el propietario de un perfil de facturación o un colaborador de Perfil de facturación, puede usar el perfil de facturación respaldado por un pago de tarjeta de crédito o factura para realizar compras o pagar facturas.</span><span class="sxs-lookup"><span data-stu-id="3ba70-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="3ba70-109">Si es un administrador de facturas de facturación, solo puede usar un perfil de facturación para pagar las facturas.</span><span class="sxs-lookup"><span data-stu-id="3ba70-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="3ba70-110">Para obtener más información acerca de los perfiles de facturación y los roles, consulte [Manage Billing profiles](manage-billing-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3ba70-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="3ba70-111">Si su cuenta de empresa no tiene un perfil de facturación, cualquier administrador global o de facturación puede administrar y usar cualquier cuenta bancaria que se agregue a la cuenta empresarial.</span><span class="sxs-lookup"><span data-stu-id="3ba70-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="3ba70-112">Sin embargo, solo puede administrar o usar las tarjetas de crédito que agregue.</span><span class="sxs-lookup"><span data-stu-id="3ba70-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="3ba70-113">La opción para pagar con una cuenta bancaria no está disponible en algunos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="3ba70-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="3ba70-114">Debe usar una forma de pago emitida desde el mismo país que su inquilino.</span><span class="sxs-lookup"><span data-stu-id="3ba70-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="3ba70-115">Agregar un método de pago.</span><span class="sxs-lookup"><span data-stu-id="3ba70-115">Add a payment method</span></span>

<span data-ttu-id="3ba70-116">Agregar un método de pago no asocia ninguna suscripción con él.</span><span class="sxs-lookup"><span data-stu-id="3ba70-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="3ba70-117">Para asignar una única suscripción al método de pago, vea [cambiar un método de pago para una única suscripción](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="3ba70-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="3ba70-118">Para reemplazar todas las suscripciones que usan otro método de pago con la nueva, vea [reemplazar un método de pago](#replace-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="3ba70-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="3ba70-119">En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="3ba70-120">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="3ba70-121">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="3ba70-122">Seleccione **Agregar o seleccionar un método de pago**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="3ba70-123">En la página **Métodos de pago**, seleccione un método de pago con el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ba70-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="3ba70-124">Escriba la información de la nueva tarjeta o cuenta bancaria y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="3ba70-125">Actualizar detalles del método de pago</span><span class="sxs-lookup"><span data-stu-id="3ba70-125">Update payment method details</span></span>

<span data-ttu-id="3ba70-126">Puede cambiar el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de caducidad de un método de pago existente.</span><span class="sxs-lookup"><span data-stu-id="3ba70-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="3ba70-127">Sin embargo, no puede cambiar la tarjeta o el número de cuenta.</span><span class="sxs-lookup"><span data-stu-id="3ba70-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="3ba70-128">Si el número de cuenta ha cambiado, [reemplácelo con un método de pago diferente](#replace-a-payment-method)y, a continuación, [elimine el antiguo](#delete-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="3ba70-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="3ba70-129">En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="3ba70-130">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="3ba70-131">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="3ba70-132">Seleccione la fila del método de pago que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="3ba70-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="3ba70-133">En el panel derecho, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="3ba70-134">Actualice la información del método de pago, incluido el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de expiración y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="3ba70-135">Reemplazar un método de pago</span><span class="sxs-lookup"><span data-stu-id="3ba70-135">Replace a payment method</span></span>

<span data-ttu-id="3ba70-136">Cuando se reemplaza un método de pago, se reemplaza para todas las suscripciones y perfiles de facturación que usan el mismo método de pago.</span><span class="sxs-lookup"><span data-stu-id="3ba70-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="3ba70-137">Al reemplazar un método de pago no se elimina el método de pago existente.</span><span class="sxs-lookup"><span data-stu-id="3ba70-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="3ba70-138">Sigue estando disponible para su selección y uso para otras suscripciones y perfiles de facturación.</span><span class="sxs-lookup"><span data-stu-id="3ba70-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="3ba70-139">Para cambiar el método de pago para una sola suscripción, vea [cambiar un método de pago para una sola suscripción](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="3ba70-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="3ba70-140">En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="3ba70-141">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="3ba70-142">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="3ba70-143">Seleccione la fila del método de pago que desea reemplazar.</span><span class="sxs-lookup"><span data-stu-id="3ba70-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="3ba70-144">El panel derecho muestra todos los perfiles de facturación y suscripciones individuales que usan el método de pago seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3ba70-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="3ba70-145">En el panel derecho, seleccione **reemplazar el método de pago para todos los elementos**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="3ba70-146">Para usar un método de pago existente, elija uno en la lista desplegable y, a continuación, seleccione **reemplazar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="3ba70-147">Si tiene suscripciones asociadas a un perfil de facturación, solo puede usar una tarjeta de crédito o débito para pagar por ellas.</span><span class="sxs-lookup"><span data-stu-id="3ba70-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="3ba70-148">Si tiene cuentas bancarias que aparecen en la página de **métodos de pago** , no estarán disponibles para seleccionar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ba70-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="3ba70-149">Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="3ba70-150">En el panel **Agregar un método de pago** , escriba la información de la cuenta y, después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="3ba70-151">Debe usar un método de pago del mismo país que el inquilino.</span><span class="sxs-lookup"><span data-stu-id="3ba70-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="3ba70-152">El nuevo método de pago ya está seleccionado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ba70-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="3ba70-153">Seleccione **Reemplazar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="3ba70-154">Cambio de un método de pago para una única suscripción</span><span class="sxs-lookup"><span data-stu-id="3ba70-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="3ba70-155">Puede cambiar el método de pago que se usa para pagar una sola suscripción.</span><span class="sxs-lookup"><span data-stu-id="3ba70-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="3ba70-156">En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="3ba70-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="3ba70-157">En el centro de administración, vaya a la página **Facturación** > **Sus productos**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="3ba70-158">En el centro de administración, vaya a la página **Facturación** > **Sus productos**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="3ba70-159">En la pestaña **suscripciones** , seleccione la suscripción por la que desea pagar con el método de pago alternativo.</span><span class="sxs-lookup"><span data-stu-id="3ba70-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="3ba70-160">En **facturación**, junto al método de pago, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="3ba70-161">Junto a su método de pago existente, seleccione **cambiar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="3ba70-162">En la lista desplegable, elija un método de pago alternativo o elija Agregar un método de pago.</span><span class="sxs-lookup"><span data-stu-id="3ba70-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="3ba70-163">Si agrega un método de pago, escriba los detalles de la tarjeta o la cuenta y, después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="3ba70-164">Compruebe que el método de pago seleccionado sea correcto y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="3ba70-165">Eliminar un método de pago</span><span class="sxs-lookup"><span data-stu-id="3ba70-165">Delete a payment method</span></span>

<span data-ttu-id="3ba70-166">Solo se puede eliminar un método de pago que no esté adjunto a una suscripción o a un perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="3ba70-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="3ba70-167">Esto se aplica a todas las suscripciones, independientemente de su estado.</span><span class="sxs-lookup"><span data-stu-id="3ba70-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="3ba70-168">Eliminar un método de pago sin suscripciones o perfiles de facturación adjuntos</span><span class="sxs-lookup"><span data-stu-id="3ba70-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="3ba70-169">Si un método de pago no está asociado a ninguna suscripción o Perfil de facturación, puede eliminarlo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="3ba70-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="3ba70-170">En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="3ba70-171">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="3ba70-172">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="3ba70-173">Busque el método de pago para eliminar, seleccione los tres puntos y, a continuación, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="3ba70-174">En la parte inferior del panel derecho, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="3ba70-175">Eliminar un método de pago con suscripciones o perfiles de facturación adjuntos</span><span class="sxs-lookup"><span data-stu-id="3ba70-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="3ba70-176">Si se adjunta un método de pago a cualquier suscripción o Perfil de facturación, cámbielo por un método de pago existente o agregue uno nuevo y, a continuación, elimine el método de pago antiguo.</span><span class="sxs-lookup"><span data-stu-id="3ba70-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="3ba70-177">En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="3ba70-178">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="3ba70-179">En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.</span><span class="sxs-lookup"><span data-stu-id="3ba70-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="3ba70-180">Seleccione la fila del método de pago que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="3ba70-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="3ba70-181">En el panel derecho se enumeran las suscripciones existentes que usan esa forma de pago.</span><span class="sxs-lookup"><span data-stu-id="3ba70-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="3ba70-182">En el panel derecho, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="3ba70-183">Para usar un método de pago existente, elija uno en la lista desplegable, seleccione **siguiente**y, a continuación, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="3ba70-184">Si tiene suscripciones asociadas a un perfil de facturación, solo puede usar una tarjeta de crédito para pagar por ellas.</span><span class="sxs-lookup"><span data-stu-id="3ba70-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="3ba70-185">Si tiene cuentas bancarias que aparecen en la página de **métodos de pago** , no estarán disponibles para elegir en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ba70-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="3ba70-186">Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="3ba70-187">Elija el tipo de método de pago que desea agregar, escriba la información de la cuenta y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="3ba70-188">El nuevo método de pago ya está seleccionado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ba70-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="3ba70-189">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-189">Select **Next**.</span></span>

8. <span data-ttu-id="3ba70-190">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3ba70-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="3ba70-191">Solucionar los problemas de los métodos de pago</span><span class="sxs-lookup"><span data-stu-id="3ba70-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="3ba70-192">**Problema**</span><span class="sxs-lookup"><span data-stu-id="3ba70-192">**Issue**</span></span>|<span data-ttu-id="3ba70-193">**Pasos para la solución de problemas**</span><span class="sxs-lookup"><span data-stu-id="3ba70-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="3ba70-194">**Obtengo un mensaje de error que dice que el explorador está configurado actualmente para bloquear las cookies.**</span><span class="sxs-lookup"><span data-stu-id="3ba70-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="3ba70-195">Configure el explorador para permitir cookies de terceros y vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="3ba70-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="3ba70-196">**Se ha rechazado mi tarjeta de crédito o débito.**</span><span class="sxs-lookup"><span data-stu-id="3ba70-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="3ba70-197">Si paga con tarjeta de crédito o débito y se rechaza su tarjeta, recibirá un mensaje de correo electrónico en el que se indica que Microsoft no pudo procesar el pago.</span><span class="sxs-lookup"><span data-stu-id="3ba70-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="3ba70-198">Compruebe que los detalles de la tarjeta &mdash; , la fecha de expiración, el nombre de la tarjeta y la dirección, incluidos el código postal, la ciudad, el estado y la ciudad &mdash; aparecen exactamente como en la tarjeta y en la instrucción.</span><span class="sxs-lookup"><span data-stu-id="3ba70-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="3ba70-199">Puede actualizar la información de la tarjeta y enviar el pago inmediatamente mediante el vínculo **liquidar saldo** en la sección **facturación** de la página Detalles de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3ba70-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="3ba70-200">Para obtener más información, consulte [¿Qué sucede si se ha rechazado mi tarjeta de crédito y el pago está vencido?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span><span class="sxs-lookup"><span data-stu-id="3ba70-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="3ba70-201">Si sigues viendo el mensaje "rechazado", ponte en contacto con tu banco.</span><span class="sxs-lookup"><span data-stu-id="3ba70-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="3ba70-202">Es posible que la tarjeta no esté activa.</span><span class="sxs-lookup"><span data-stu-id="3ba70-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="3ba70-203">Si ha recibido recientemente la tarjeta en el correo con una fecha de expiración actualizada, asegúrese de que esté activada.</span><span class="sxs-lookup"><span data-stu-id="3ba70-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="3ba70-204">El Banco también puede decirle si su tarjeta no está aprobada para transacciones en línea, internacionales o recurrentes.</span><span class="sxs-lookup"><span data-stu-id="3ba70-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="3ba70-205">**Quiero actualizar una tarjeta o un número de cuenta bancaria.**</span><span class="sxs-lookup"><span data-stu-id="3ba70-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="3ba70-206">No puede cambiar la tarjeta o el número de cuenta en un método de pago existente.</span><span class="sxs-lookup"><span data-stu-id="3ba70-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="3ba70-207">Si ha cambiado la tarjeta o el número de cuenta, [reemplácelo con un método de pago diferente](#replace-a-payment-method), que mueve todas las suscripciones activas del método de pago al nuevo y, a continuación, [elimine el método de pago antiguo](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span><span class="sxs-lookup"><span data-stu-id="3ba70-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="3ba70-208">**Solo tengo una tarjeta o cuenta bancaria en mi cuenta y quiero quitarla.**</span><span class="sxs-lookup"><span data-stu-id="3ba70-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="3ba70-209">Si solo tiene un método de pago, debe [reemplazarlo por un nuevo método de pago](#replace-a-payment-method) para poder eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="3ba70-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="3ba70-210">**No puedo agregar mi tarjeta o cuenta bancaria.**</span><span class="sxs-lookup"><span data-stu-id="3ba70-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="3ba70-211">Debe usar una forma de pago emitida desde el mismo país que su inquilino.</span><span class="sxs-lookup"><span data-stu-id="3ba70-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="3ba70-212">Si tiene problemas para escribir la información de la tarjeta o de la cuenta bancaria, puede [ponerse en contacto con el soporte técnico](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="3ba70-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="3ba70-213">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="3ba70-213">Related articles</span></span>

[<span data-ttu-id="3ba70-214">Pagar la suscripción de su empresa</span><span class="sxs-lookup"><span data-stu-id="3ba70-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="3ba70-215">Administrar perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="3ba70-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="3ba70-216">Cambiar la frecuencia de pago</span><span class="sxs-lookup"><span data-stu-id="3ba70-216">Change your payment frequency</span></span>](change-payment-frequency.md)