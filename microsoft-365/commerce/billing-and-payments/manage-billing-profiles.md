---
title: Administrar perfiles de facturación
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Obtenga información sobre cómo los perfiles de facturación admiten facturas.
keywords: Perfil de facturación, facturas, cargos, cargos administrados
ms.openlocfilehash: de6d6cd65d9e83e7211bcdc33f1774aaec3d1729
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638452"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="03876-104">Administrar perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="03876-105">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="03876-105">The admin center is changing.</span></span> <span data-ttu-id="03876-106">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="03876-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="03876-107">Para los clientes comerciales que compran productos y servicios de Microsoft, los perfiles de facturación le permiten personalizar los elementos que se incluyen en la factura y cómo pagar sus facturas.</span><span class="sxs-lookup"><span data-stu-id="03876-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="03876-108">Los perfiles de facturación incluyen la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="03876-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="03876-109">**Cuenta** &ndash; de facturación Nombre de la cuenta de facturación con la que está relacionado el perfil</span><span class="sxs-lookup"><span data-stu-id="03876-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="03876-110">**Métodos** &ndash; de pago Tarjetas de crédito o débito, cuentas bancarias, cheque o transferencia bancaria</span><span class="sxs-lookup"><span data-stu-id="03876-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="03876-111">**Información** &ndash; de contacto Dirección de facturación y nombre de contacto</span><span class="sxs-lookup"><span data-stu-id="03876-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="03876-112">Configuración de la **factura** &ndash; Divisa basada en el país de la cuenta de facturación, un número de pedido de compra opcional y la opción de recibir facturas como datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="03876-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="03876-113">**Permisos** &ndash; Permisos que permiten cambiar el perfil de facturación, pagar facturas o usar el método de pago en el perfil de facturación para realizar compras</span><span class="sxs-lookup"><span data-stu-id="03876-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="03876-114">Use perfiles de facturación para controlar las compras y personalizar la factura.</span><span class="sxs-lookup"><span data-stu-id="03876-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="03876-115">Se genera una factura mensual para los productos comprados con el perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="03876-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="03876-116">Puede personalizar la factura como actualizar el número de pedido de compra y la preferencia de factura de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="03876-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="03876-117">Durante la primera compra, se creará automáticamente un perfil de facturación para la cuenta de facturación.</span><span class="sxs-lookup"><span data-stu-id="03876-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="03876-118">Puede crear perfiles de facturación en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfiles de facturación</a> para configurar más facturas.</span><span class="sxs-lookup"><span data-stu-id="03876-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="03876-119">Por ejemplo, puede usar diferentes perfiles de facturación al realizar compras para cada departamento de su organización.</span><span class="sxs-lookup"><span data-stu-id="03876-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="03876-120">En la próxima fecha de facturación, recibirá una factura para cada perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="03876-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="03876-121">Roles de Perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-121">Billing profile roles</span></span>

<span data-ttu-id="03876-122">Los roles en perfiles de facturación tienen permisos para controlar las compras y ver y administrar las facturas.</span><span class="sxs-lookup"><span data-stu-id="03876-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="03876-123">Asigne estos roles a los usuarios que realizan un seguimiento, organizan y pagan facturas, como los miembros del equipo de compras de su organización.</span><span class="sxs-lookup"><span data-stu-id="03876-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="03876-124">Role</span><span class="sxs-lookup"><span data-stu-id="03876-124">Role</span></span>                          | <span data-ttu-id="03876-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="03876-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="03876-126">Propietario del perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-126">Billing profile owner</span></span>         | <span data-ttu-id="03876-127">Administrar todo para un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="03876-128">Colaborador de Perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-128">Billing profile contributor</span></span>   | <span data-ttu-id="03876-129">Administrar todo excepto permisos en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="03876-130">Lector de perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-130">Billing profile reader</span></span>        | <span data-ttu-id="03876-131">Vista de solo lectura de todo en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="03876-132">Administrador de facturas</span><span class="sxs-lookup"><span data-stu-id="03876-132">Invoice manager</span></span>               | <span data-ttu-id="03876-133">Ver y pagar facturas y tiene una vista de solo lectura de todo en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="03876-134">Ver perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="03876-134">View billing profiles</span></span>

1. <span data-ttu-id="03876-135">En el Centro de administración, vaya a la página **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.</span><span class="sxs-lookup"><span data-stu-id="03876-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="03876-136">Elija **perfiles de facturación**y, después, elija un perfil de facturación de la lista.</span><span class="sxs-lookup"><span data-stu-id="03876-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="03876-137">En la ficha **información general** , puede editar los detalles del perfil de facturación y activar o desactivar el envío de facturas por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="03876-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="03876-138">En la pestaña **permisos** , puede asignar roles a los usuarios para pagar facturas.</span><span class="sxs-lookup"><span data-stu-id="03876-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="03876-139">En la pestaña **saldo de crédito de Azure** , los clientes de Azure pueden ver el historial de saldo de transacciones para los créditos de Azure usados por ese perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="03876-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="03876-140">En la pestaña **Azure créditos** , los clientes de Azure pueden ver una lista de créditos de Azure asociados con ese perfil de facturación y sus fechas de expiración.</span><span class="sxs-lookup"><span data-stu-id="03876-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03876-141">Si no tiene ningún crédito de Azure, no podrá ver las pestañas de **saldo haber** de Azure o **créditos de Azure** .</span><span class="sxs-lookup"><span data-stu-id="03876-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="03876-142">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="03876-142">Need help?</span></span> <span data-ttu-id="03876-143">Póngase en contacto con el servicio de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="03876-143">Contact support.</span></span>

<span data-ttu-id="03876-144">Si tiene preguntas o necesita ayuda con los cargos de Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">cree una solicitud de soporte técnico con el soporte de Azure</a>.</span><span class="sxs-lookup"><span data-stu-id="03876-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="03876-145">Si tiene alguna pregunta o necesita ayuda con su perfil de facturación en el centro de administración de Microsoft 365, [póngase en contacto con soporte técnico para productos empresariales](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="03876-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
