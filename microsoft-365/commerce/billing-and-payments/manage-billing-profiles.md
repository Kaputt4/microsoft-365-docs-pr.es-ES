---
title: Entender los perfiles de facturación
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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- Commerce
search.appverid:
- MET150
description: Obtenga información sobre cómo los perfiles de facturación admiten facturas.
ms.openlocfilehash: 7f4c0aed1bccd0e5df5b09e15e6201933e937993
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576954"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="abadd-103">Entender los perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-103">Understand billing profiles</span></span>

<span data-ttu-id="abadd-104">Para los clientes comerciales que compran productos y servicios de Microsoft, los perfiles de facturación te permiten personalizar qué elementos se incluyen en la factura y cómo pagas tus facturas.</span><span class="sxs-lookup"><span data-stu-id="abadd-104">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="abadd-105">Los perfiles de facturación incluyen la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="abadd-105">Billing profiles include the following information:</span></span>

- <span data-ttu-id="abadd-106">**Cuenta de facturación** &ndash; Nombre de la cuenta de facturación con la que está relacionado el perfil</span><span class="sxs-lookup"><span data-stu-id="abadd-106">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="abadd-107">**Métodos de pago** &ndash; Tarjetas de crédito o débito, cuentas bancarias, cheque o transferencia bancaria</span><span class="sxs-lookup"><span data-stu-id="abadd-107">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="abadd-108">**Información de contacto** &ndash; Dirección de facturación y un nombre de contacto</span><span class="sxs-lookup"><span data-stu-id="abadd-108">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="abadd-109">**Configuración de factura** &ndash; Moneda basada en el país de la cuenta de facturación, un número de PEDIDO opcional y la opción de recibir facturas como datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="abadd-109">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="abadd-110">**Permisos** &ndash; Permisos que le permiten cambiar el perfil de facturación, pagar facturas o usar el método de pago en el perfil de facturación para realizar compras</span><span class="sxs-lookup"><span data-stu-id="abadd-110">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="abadd-111">Usa perfiles de facturación para controlar tus compras y personalizar la factura.</span><span class="sxs-lookup"><span data-stu-id="abadd-111">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="abadd-112">Se genera una factura mensual para los productos comprados con el perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="abadd-112">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="abadd-113">Puede personalizar la factura, como actualizar el número de pedido de compra y la preferencia de factura de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="abadd-113">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="abadd-114">Se crea automáticamente un perfil de facturación para tu cuenta de facturación durante la primera compra.</span><span class="sxs-lookup"><span data-stu-id="abadd-114">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="abadd-115">Puede crear perfiles de facturación en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfiles de facturación</a> para configurar más facturas.</span><span class="sxs-lookup"><span data-stu-id="abadd-115">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="abadd-116">Por ejemplo, puede usar diferentes perfiles de facturación al realizar compras para cada departamento de su organización.</span><span class="sxs-lookup"><span data-stu-id="abadd-116">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="abadd-117">En la próxima fecha de facturación, recibirás una factura para cada perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="abadd-117">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="abadd-118">Roles de perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-118">Billing profile roles</span></span>

<span data-ttu-id="abadd-119">Los roles de los perfiles de facturación tienen permisos para controlar las compras y ver y administrar facturas.</span><span class="sxs-lookup"><span data-stu-id="abadd-119">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="abadd-120">Asigne estos roles a los usuarios que realicen un seguimiento, organicen y paguen facturas, como los miembros del equipo de compras de la organización.</span><span class="sxs-lookup"><span data-stu-id="abadd-120">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="abadd-121">Role</span><span class="sxs-lookup"><span data-stu-id="abadd-121">Role</span></span>                          | <span data-ttu-id="abadd-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="abadd-122">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="abadd-123">Propietario del perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-123">Billing profile owner</span></span>         | <span data-ttu-id="abadd-124">Administrar todo para un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-124">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="abadd-125">Colaborador de perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-125">Billing profile contributor</span></span>   | <span data-ttu-id="abadd-126">Administrar todo excepto los permisos en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-126">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="abadd-127">Lector de perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-127">Billing profile reader</span></span>        | <span data-ttu-id="abadd-128">Vista de solo lectura de todo en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-128">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="abadd-129">Administrador de facturas</span><span class="sxs-lookup"><span data-stu-id="abadd-129">Invoice manager</span></span>               | <span data-ttu-id="abadd-130">Ver y pagar facturas y tiene una vista de solo lectura de todo en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-130">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="abadd-131">Ver perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="abadd-131">View billing profiles</span></span>

1. <span data-ttu-id="abadd-132">En el Centro de administración, vaya a la página **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.</span><span class="sxs-lookup"><span data-stu-id="abadd-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="abadd-133">Elija **Perfiles de facturación** y, a continuación, elija un perfil de facturación de la lista.</span><span class="sxs-lookup"><span data-stu-id="abadd-133">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="abadd-134">En la **pestaña Información** general, puede editar los detalles del perfil de facturación y activar o desactivar el envío de una factura por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="abadd-134">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="abadd-135">En la **pestaña Permisos,** puede asignar roles a los usuarios para pagar facturas.</span><span class="sxs-lookup"><span data-stu-id="abadd-135">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="abadd-136">En la **pestaña Saldo de crédito de Azure,** los clientes de Azure pueden ver el historial de saldos de transacciones para los créditos de Azure usados por ese perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="abadd-136">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="abadd-137">En la **pestaña Créditos de Azure,** los clientes de Azure pueden ver una lista de créditos de Azure asociados con ese perfil de facturación y sus fechas de expiración.</span><span class="sxs-lookup"><span data-stu-id="abadd-137">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abadd-138">Si no tiene créditos de Azure, no verá las pestañas Saldo de crédito de **Azure** o **Créditos de Azure.**</span><span class="sxs-lookup"><span data-stu-id="abadd-138">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="abadd-139">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="abadd-139">Need help?</span></span> <span data-ttu-id="abadd-140">Póngase en contacto con el servicio de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="abadd-140">Contact support.</span></span>

<span data-ttu-id="abadd-141">Si tiene preguntas o necesita ayuda con los cargos de Azure, cree una solicitud de soporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">técnico con soporte técnico de Azure</a>.</span><span class="sxs-lookup"><span data-stu-id="abadd-141">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="abadd-142">Si tiene preguntas o necesita ayuda con su perfil de facturación en el Centro de administración de Microsoft 365, póngase en contacto con el soporte [técnico para productos empresariales](/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="abadd-142">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](/office365/admin/contact-support-for-business-products).</span></span>