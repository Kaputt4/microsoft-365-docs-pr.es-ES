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
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537336"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="d645b-103">Entender los perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-103">Understand billing profiles</span></span>

<span data-ttu-id="d645b-104">Un perfil de facturación contiene un método de pago, información de facturación y otras opciones de facturación, como el número de pedido de compra y la preferencia de factura de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d645b-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="d645b-105">Usas un perfil de facturación para pagar los productos que compras a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d645b-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="d645b-106">Un perfil de facturación se crea automáticamente cuando un usuario realiza una compra de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="d645b-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="d645b-107">Cada perfil de facturación se factura por separado.</span><span class="sxs-lookup"><span data-stu-id="d645b-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="d645b-108">Los perfiles de facturación no están disponibles para los clientes  que compren productos y servicios de Microsoft.com o en la página Servicios de compra del centro de administración Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="d645b-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="d645b-109">¿Qué son los roles de perfil de facturación?</span><span class="sxs-lookup"><span data-stu-id="d645b-109">What are billing profile roles?</span></span>

<span data-ttu-id="d645b-110">Los roles de los perfiles de facturación tienen permisos para controlar las compras y ver y administrar facturas.</span><span class="sxs-lookup"><span data-stu-id="d645b-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="d645b-111">Asigne estos roles a los usuarios que realicen un seguimiento, organicen y paguen facturas.</span><span class="sxs-lookup"><span data-stu-id="d645b-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="d645b-112">Por ejemplo, los miembros del equipo de compras de la organización.</span><span class="sxs-lookup"><span data-stu-id="d645b-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="d645b-113">Función</span><span class="sxs-lookup"><span data-stu-id="d645b-113">Role</span></span>                         | <span data-ttu-id="d645b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d645b-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="d645b-115">Propietario del perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-115">Billing profile owner</span></span>        | <span data-ttu-id="d645b-116">Administrar todo para un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="d645b-117">Colaborador de perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-117">Billing profile contributor</span></span>  | <span data-ttu-id="d645b-118">Administrar todo excepto los permisos en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="d645b-119">Lector de perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-119">Billing profile reader</span></span>       | <span data-ttu-id="d645b-120">Vista de solo lectura de todo en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="d645b-121">Administrador de facturas</span><span class="sxs-lookup"><span data-stu-id="d645b-121">Invoice manager</span></span>              | <span data-ttu-id="d645b-122">Ver y pagar facturas y tiene una vista de solo lectura de todo en un perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="d645b-123">Ver mis perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="d645b-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="d645b-124">Si sigues estos pasos y la lista de perfiles de facturación está vacía, significa que no tienes un perfil de facturación y no puedes usar esta característica.</span><span class="sxs-lookup"><span data-stu-id="d645b-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="d645b-125">En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.</span><span class="sxs-lookup"><span data-stu-id="d645b-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="d645b-126">Seleccione la **pestaña Perfil de facturación** y, a continuación, seleccione un perfil de facturación de la lista.</span><span class="sxs-lookup"><span data-stu-id="d645b-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="d645b-127">Cada perfil de facturación incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="d645b-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="d645b-128">**Nombre y estado del perfil de facturación** &ndash; Nombre único del perfil de facturación y si el perfil de facturación está activo o deshabilitado para la compra.</span><span class="sxs-lookup"><span data-stu-id="d645b-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="d645b-129">**Configuración de factura** &ndash; Moneda basada en el país de la cuenta de facturación, información sobre la frecuencia y la fecha de facturación, la opción de recibir facturas como datos adjuntos de correo electrónico y un campo de número de pedido opcional</span><span class="sxs-lookup"><span data-stu-id="d645b-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="d645b-130">**Métodos de pago** &ndash; Muestra el método de pago principal y de copia de seguridad, si lo hay, para el perfil</span><span class="sxs-lookup"><span data-stu-id="d645b-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="d645b-131">**Cuenta de facturación** &ndash; Nombre de la cuenta de facturación a la que está relacionado el perfil.</span><span class="sxs-lookup"><span data-stu-id="d645b-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="d645b-132">Para obtener más información acerca de las cuentas de facturación, vea [Comprender cuentas de facturación.](../manage-billing-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="d645b-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="d645b-133">**Información de contacto** &ndash; Dirección de facturación y nombre de contacto y dirección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="d645b-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="d645b-134">**Roles de perfil de facturación** &ndash; Una lista de personas a las que se asigna uno de los roles de perfil de facturación para hacer cosas para ese perfil.</span><span class="sxs-lookup"><span data-stu-id="d645b-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="d645b-135">Por ejemplo, pagar facturas, agregar un número de PEDIDO o reemplazar el método de pago que se usa para realizar compras.</span><span class="sxs-lookup"><span data-stu-id="d645b-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="d645b-136">Solo puede asignar roles de perfil de facturación a los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="d645b-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="d645b-137">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="d645b-137">Need help?</span></span> <span data-ttu-id="d645b-138">Ponerse en contacto con soporte técnico</span><span class="sxs-lookup"><span data-stu-id="d645b-138">Contact support</span></span>

<span data-ttu-id="d645b-139">Si tiene preguntas o necesita ayuda con los cargos de Azure, cree una solicitud de soporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">técnico con soporte técnico de Azure</a>.</span><span class="sxs-lookup"><span data-stu-id="d645b-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="d645b-140">Si tiene preguntas o necesita ayuda con su perfil de facturación en Microsoft 365 centro de administración, póngase [en contacto con el soporte técnico](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="d645b-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="d645b-141">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="d645b-141">Related content</span></span>

<span data-ttu-id="d645b-142">[Cómo pagar la suscripción con un perfil de facturación](pay-for-subscription-billing-profile.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="d645b-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="d645b-143">[Comprender cuentas de facturación](../manage-billing-accounts.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="d645b-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="d645b-144">[Administrar métodos de pago](manage-payment-methods.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="d645b-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
