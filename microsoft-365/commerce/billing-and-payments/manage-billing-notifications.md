---
title: Administrar las notificaciones de facturación y los datos adjuntos en las facturas
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid:
- MET150
description: Obtenga información sobre cómo administrar quién recibe mensajes de correo electrónico de notificación de facturación y datos adjuntos de factura.
ms.date: 03/17/2021
ms.openlocfilehash: f41d93835fed1715803052f1cf79b46f43a1d200
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054579"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="f6f86-103">Administrar las notificaciones de facturación y los datos adjuntos en las facturas</span><span class="sxs-lookup"><span data-stu-id="f6f86-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="f6f86-104">Las **notificaciones de facturación** le permiten administrar quién recibe correos electrónicos de notificación de facturación para su organización.</span><span class="sxs-lookup"><span data-stu-id="f6f86-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="f6f86-105">La página también proporciona la opción de [recibir facturas de su organización como datos adjuntos de correo](#receive-your-organizations-invoices-as-email-attachments).</span><span class="sxs-lookup"><span data-stu-id="f6f86-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f6f86-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="f6f86-106">Before you begin</span></span>

<span data-ttu-id="f6f86-107">Debe ser un administrador global para realizar los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="f6f86-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="f6f86-108">Los administradores de facturación pueden realizar algunos de estos cambios, como se indica en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f6f86-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="f6f86-109">Para más información, consulte [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f6f86-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="f6f86-110">Cambiar el idioma en el que recibe el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f6f86-110">Change the language you receive email in</span></span>

<span data-ttu-id="f6f86-111">Los correos electrónicos de notificación de facturación se envían en el idioma preferido de su organización.</span><span class="sxs-lookup"><span data-stu-id="f6f86-111">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="f6f86-112">Para cambiar el idioma preferido, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f6f86-112">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="f6f86-113">En el Centro de administración de Microsoft 365, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="f6f86-113">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="f6f86-114">En la sección **Configuración de notificaciones de facturación**, seleccione **Editar la configuración de notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-114">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="f6f86-115">En el panel **Configuración de notificaciones de facturación**, en **Idioma preferido** seleccione el idioma que desea usar y, luego, **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-115">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="f6f86-116">Cambiar quién recibe notificaciones de facturación</span><span class="sxs-lookup"><span data-stu-id="f6f86-116">Change who receives billing notifications</span></span>

<span data-ttu-id="f6f86-117">Las notificaciones de facturación de la organización se envían a la dirección de correo electrónico principal y alternativa de todos los administradores globales y de facturación. Para cambiar los usuarios que tienen el rol de administrador global o de facturación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f6f86-117">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="f6f86-118">Asignar roles de administrador mediante la página Notificaciones de facturación</span><span class="sxs-lookup"><span data-stu-id="f6f86-118">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="f6f86-119">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="f6f86-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="f6f86-120">En la sección **Administradores que reciben notificaciones de facturación**, seleccione el vínculo **Administrador de facturación** o **Administrador global** en el texto de descripción.</span><span class="sxs-lookup"><span data-stu-id="f6f86-120">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="f6f86-121">En el panel derecho, en la pestaña **Administradores asignados**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-121">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="f6f86-122">En el panel **Agregar administradores**, escriba el nombre del usuario o su nombre para mostrar y, a continuación, seleccione el usuario de la lista de sugerencias.</span><span class="sxs-lookup"><span data-stu-id="f6f86-122">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="f6f86-123">Agregue varios usuarios hasta que haya terminado.</span><span class="sxs-lookup"><span data-stu-id="f6f86-123">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="f6f86-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-124">Select **Save**.</span></span> <span data-ttu-id="f6f86-125">El usuario se agregará a la lista de administradores asignados.</span><span class="sxs-lookup"><span data-stu-id="f6f86-125">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="f6f86-126">Quitar roles de administrador mediante la página Notificaciones de facturación</span><span class="sxs-lookup"><span data-stu-id="f6f86-126">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="f6f86-127">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="f6f86-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="f6f86-128">En la sección **Administradores que reciben notificaciones de facturación**, seleccione el vínculo **Administrador de facturación** o **Administrador global** en el texto de descripción.</span><span class="sxs-lookup"><span data-stu-id="f6f86-128">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="f6f86-129">En el panel derecho, en la pestaña **Administradores asignados**, seleccione los usuarios que desea quitar del rol y, después, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-129">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="f6f86-130">En el cuadro de confirmación, seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-130">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="f6f86-131">El usuario se eliminará de la lista de administradores asignados.</span><span class="sxs-lookup"><span data-stu-id="f6f86-131">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="f6f86-132">Cambiar las direcciones de correo electrónico para administradores</span><span class="sxs-lookup"><span data-stu-id="f6f86-132">Change the email addresses for admins</span></span>

<span data-ttu-id="f6f86-133">Para cambiar las direcciones de correo electrónico principal y alternativa de otros administradores de la organización, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f6f86-133">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="f6f86-134">Los administradores de facturación pueden cambiar sus propias direcciones de correo electrónico principales y alternativas, pero no las de otros administradores.</span><span class="sxs-lookup"><span data-stu-id="f6f86-134">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="f6f86-135">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="f6f86-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="f6f86-136">En la sección **Administradores que reciben notificaciones de facturación**, seleccione un nombre.</span><span class="sxs-lookup"><span data-stu-id="f6f86-136">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="f6f86-137">En el panel derecho, agregue o actualice la dirección de correo electrónico principal y alternativa según sea necesario y, después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-137">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="f6f86-138">Cambiar el correo electrónico de contacto de su organización</span><span class="sxs-lookup"><span data-stu-id="f6f86-138">Change your organization's contact email</span></span>

<span data-ttu-id="f6f86-139">Además de los administradores globales y de facturación, enviamos notificaciones de facturación a la dirección de correo electrónico de contacto de su organización.</span><span class="sxs-lookup"><span data-stu-id="f6f86-139">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="f6f86-140">Para cambiar la dirección de correo electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f6f86-140">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="f6f86-141">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="f6f86-141">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="f6f86-142">En **Contacto de la organización que recibe notificaciones de facturación**, seleccione el contacto de la organización.</span><span class="sxs-lookup"><span data-stu-id="f6f86-142">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="f6f86-143">En el panel derecho, escriba la dirección de correo electrónico que quiere usar y, después, **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-143">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="f6f86-144">Recibir facturas de su organización como datos adjuntos de correo</span><span class="sxs-lookup"><span data-stu-id="f6f86-144">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="f6f86-145">Los administradores de facturación también pueden seguir los pasos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="f6f86-145">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="f6f86-146">Puede tener una copia de la factura de la organización adjuntada como archivo PDF para enviar correos electrónicos de notificación mediante factura cuando esté lista una nueva factura.</span><span class="sxs-lookup"><span data-stu-id="f6f86-146">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="f6f86-147">Siga estos pasos para recibir las facturas como datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="f6f86-147">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="f6f86-148">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="f6f86-148">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="f6f86-149">En **Configuración de notificaciones de facturación**, seleccione **Editar la configuración de notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-149">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="f6f86-150">En el panel **Configuración de notificaciones de facturación**, en **Adjuntar un PDF a los correos electrónicos de factura**, active la casilla y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-150">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="f6f86-151">Para dejar de recibir los datos adjuntos de factura en cualquier momento, siga los pasos anteriores y desactive la casilla **Adjuntar un PDF a los correos electrónicos de la factura** del paso 3.</span><span class="sxs-lookup"><span data-stu-id="f6f86-151">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="f6f86-152">¿Qué ocurre si tengo un perfil de facturación?</span><span class="sxs-lookup"><span data-stu-id="f6f86-152">What if I have a billing profile?</span></span>

<span data-ttu-id="f6f86-153">Si tiene un perfil de facturación, algunos de los pasos descritos en este artículo pueden ser ligeramente diferentes para algunas de sus suscripciones.</span><span class="sxs-lookup"><span data-stu-id="f6f86-153">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="f6f86-154">En esta sección se describen esas diferencias.</span><span class="sxs-lookup"><span data-stu-id="f6f86-154">This section describes those differences.</span></span> [<span data-ttu-id="f6f86-155">¿Cómo sé si tengo un perfil de facturación?</span><span class="sxs-lookup"><span data-stu-id="f6f86-155">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="f6f86-156">¿Quién recibe notificaciones de facturación?</span><span class="sxs-lookup"><span data-stu-id="f6f86-156">Who receives Billing notifications?</span></span>

<span data-ttu-id="f6f86-157">Los correos electrónicos de notificación de facturación se envían a las direcciones de correo electrónico principal y alternativa de los usuarios a los que se les asigne uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6f86-157">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="f6f86-158">Propietario del perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="f6f86-158">Billing profile owner</span></span>
- <span data-ttu-id="f6f86-159">Colaborador del perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="f6f86-159">Billing profile contributor</span></span>
- <span data-ttu-id="f6f86-160">Administrador de facturas</span><span class="sxs-lookup"><span data-stu-id="f6f86-160">Invoice manager</span></span>

<span data-ttu-id="f6f86-161">Para obtener más información sobre los roles de perfil de facturación y cómo administrarlos, consulte [Comprender los roles administrativos del Contrato de cliente de Microsoft en Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span><span class="sxs-lookup"><span data-stu-id="f6f86-161">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="f6f86-162">Para cambiar quién recibe las notificaciones de facturación de su organización, cambie los roles asignados a los usuarios con los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f6f86-162">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="f6f86-163">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.</span><span class="sxs-lookup"><span data-stu-id="f6f86-163">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="f6f86-164">En la pestaña **Perfil de facturación**, seleccione un perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="f6f86-164">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="f6f86-165">En la sección **Roles de perfil de facturación**, asigne o quite roles para **Propietario del perfil de facturación**, **Colaborador de perfil de facturación** o **Administrador de facturas**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-165">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="f6f86-166">Recibir facturas como datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f6f86-166">Receive invoices as email attachments</span></span>

<span data-ttu-id="f6f86-167">Para recibir sus facturas como datos adjuntos de en las notificaciones de factura, habilite esta opción para un perfil de facturación específico con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f6f86-167">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="f6f86-168">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturas y pagos</a>.</span><span class="sxs-lookup"><span data-stu-id="f6f86-168">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="f6f86-169">Seleccione la pestaña **Perfiles** y, a continuación, escoja un perfil de facturación de la lista.</span><span class="sxs-lookup"><span data-stu-id="f6f86-169">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="f6f86-170">En la página de detalles del perfil de facturación, en **Obtener facturas en datos adjuntos de correo**, cambie el botón de alternancia a **Activado**.</span><span class="sxs-lookup"><span data-stu-id="f6f86-170">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="f6f86-171">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f6f86-171">Related content</span></span>

<span data-ttu-id="f6f86-172">[Vea su factura o recibo](view-your-bill-or-invoice.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f6f86-172">[View your bill or invoice](view-your-bill-or-invoice.md) (article)\</span></span>
<span data-ttu-id="f6f86-173">[Información de facturación de Microsoft 365 para empresas en México](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f6f86-173">[Billing information for Microsoft 365 for business in Mexico](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (article) </span></span>\
<span data-ttu-id="f6f86-174">[Conozca su factura o recibo por la compra de Microsoft 365 para Empresas](understand-your-invoice2.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f6f86-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="f6f86-175">[Agregar usuarios y asignar licencias al mismo tiempo](../../admin/add-users/add-users.md) (artículo)\</span><span class="sxs-lookup"><span data-stu-id="f6f86-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
