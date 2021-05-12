---
title: Entender los perfiles de facturación
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Obtenga información sobre cómo los perfiles de facturación admiten facturas.
ms.date: 04/02/2021
ms.openlocfilehash: 36d762e50627763b7856ed1fe6c109e8da2b4789
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332035"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="ec976-103">Entender los perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-103">Understand billing profiles</span></span>

<span data-ttu-id="ec976-104">Para los clientes comerciales que compran productos y servicios de Microsoft, los perfiles de facturación te permiten personalizar qué elementos se incluyen en la factura y cómo pagas tus facturas.</span><span class="sxs-lookup"><span data-stu-id="ec976-104">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="ec976-105">Los perfiles de facturación incluyen la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ec976-105">Billing profiles include the following information:</span></span>

- <span data-ttu-id="ec976-106">**Cuenta de facturación** &ndash; Nombre de la cuenta de facturación con la que está relacionado el perfil</span><span class="sxs-lookup"><span data-stu-id="ec976-106">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="ec976-107">**Métodos de pago** &ndash; Tarjetas de crédito o débito, cuentas bancarias, cheque o transferencia bancaria</span><span class="sxs-lookup"><span data-stu-id="ec976-107">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="ec976-108">**Información de contacto** &ndash; Dirección de facturación y un nombre de contacto</span><span class="sxs-lookup"><span data-stu-id="ec976-108">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="ec976-109">**Configuración de factura** &ndash; Moneda basada en el país de la cuenta de facturación, un número de PEDIDO opcional y la opción de recibir facturas como datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ec976-109">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="ec976-110">**Permisos** &ndash; Permisos que le permiten cambiar el perfil de facturación, pagar facturas o usar el método de pago en el perfil de facturación para realizar compras</span><span class="sxs-lookup"><span data-stu-id="ec976-110">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="ec976-111">Usa perfiles de facturación para controlar tus compras y personalizar la factura.</span><span class="sxs-lookup"><span data-stu-id="ec976-111">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="ec976-112">Se genera una factura mensual para los productos comprados con el perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="ec976-112">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="ec976-113">Puede personalizar la factura, como actualizar el número de pedido de compra y la preferencia de factura de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ec976-113">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="ec976-114">Se crea automáticamente un perfil de facturación para tu cuenta de facturación durante la primera compra.</span><span class="sxs-lookup"><span data-stu-id="ec976-114">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="ec976-115">Puede crear perfiles de facturación en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfiles de facturación</a> para configurar más facturas.</span><span class="sxs-lookup"><span data-stu-id="ec976-115">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="ec976-116">Por ejemplo, puede usar diferentes perfiles de facturación al realizar compras para cada departamento de su organización.</span><span class="sxs-lookup"><span data-stu-id="ec976-116">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="ec976-117">En la próxima fecha de facturación, recibirás una factura para cada perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="ec976-117">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="ec976-118">Roles de perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-118">Billing profile roles</span></span>

<span data-ttu-id="ec976-119">Los roles de los perfiles de facturación tienen permisos para controlar las compras y ver y administrar facturas.</span><span class="sxs-lookup"><span data-stu-id="ec976-119">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="ec976-120">Asigne estos roles a los usuarios que realicen un seguimiento, organicen y paguen facturas, como los miembros del equipo de compras de la organización.</span><span class="sxs-lookup"><span data-stu-id="ec976-120">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="ec976-121">Role</span><span class="sxs-lookup"><span data-stu-id="ec976-121">Role</span></span>                         | <span data-ttu-id="ec976-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec976-122">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="ec976-123">Propietario del perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-123">Billing profile owner</span></span>        | <span data-ttu-id="ec976-124">Administrar todo para un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-124">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="ec976-125">Colaborador de perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-125">Billing profile contributor</span></span>  | <span data-ttu-id="ec976-126">Administrar todo excepto los permisos en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-126">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="ec976-127">Lector de perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-127">Billing profile reader</span></span>       | <span data-ttu-id="ec976-128">Vista de solo lectura de todo en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-128">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="ec976-129">Administrador de facturas</span><span class="sxs-lookup"><span data-stu-id="ec976-129">Invoice manager</span></span>              | <span data-ttu-id="ec976-130">Ver y pagar facturas y tiene una vista de solo lectura de todo en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-130">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-billing-profiles"></a><span data-ttu-id="ec976-131">Ver perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="ec976-131">View billing profiles</span></span>

1. <span data-ttu-id="ec976-132">En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.</span><span class="sxs-lookup"><span data-stu-id="ec976-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="ec976-133">Elija **Perfiles de facturación** y, a continuación, elija un perfil de facturación de la lista.</span><span class="sxs-lookup"><span data-stu-id="ec976-133">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="ec976-134">En la **pestaña Información** general, puede editar los detalles del perfil de facturación y activar o desactivar el envío de una factura por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ec976-134">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>
    - <span data-ttu-id="ec976-135">En la **pestaña Permisos,** puede asignar roles a los usuarios para pagar facturas.</span><span class="sxs-lookup"><span data-stu-id="ec976-135">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>
    - <span data-ttu-id="ec976-136">En la **pestaña Saldo de crédito de Azure,** los clientes de Azure pueden ver el historial de saldos de transacciones para los créditos de Azure usados por ese perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="ec976-136">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>
    - <span data-ttu-id="ec976-137">En la **pestaña Créditos de Azure,** los clientes de Azure pueden ver una lista de créditos de Azure asociados con ese perfil de facturación y sus fechas de expiración.</span><span class="sxs-lookup"><span data-stu-id="ec976-137">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec976-138">Si no tiene créditos de Azure, no verá las pestañas Saldo de crédito de **Azure** o **Créditos de Azure.**</span><span class="sxs-lookup"><span data-stu-id="ec976-138">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="ec976-139">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="ec976-139">Need help?</span></span> <span data-ttu-id="ec976-140">Contactar soporte</span><span class="sxs-lookup"><span data-stu-id="ec976-140">Contact support</span></span>

<span data-ttu-id="ec976-141">Si tiene preguntas o necesita ayuda con los cargos de Azure, cree una solicitud de soporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">técnico con soporte técnico de Azure</a>.</span><span class="sxs-lookup"><span data-stu-id="ec976-141">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="ec976-142">Si tiene preguntas o necesita ayuda con su perfil de facturación en el Centro de administración de Microsoft 365, póngase en contacto con el soporte [técnico para productos empresariales](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="ec976-142">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](../../business-video/get-help-support.md).</span></span>
