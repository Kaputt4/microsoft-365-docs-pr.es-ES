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
description: Obtenga información sobre cómo administrar quién recibe correos electrónicos de notificación de facturación y datos adjuntos de facturación.
ms.date: 03/17/2021
ms.openlocfilehash: 75c75175930434619a01886b1096757bf04111c5
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888366"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="55e0e-103">Administrar las notificaciones de facturación y los datos adjuntos en las facturas</span><span class="sxs-lookup"><span data-stu-id="55e0e-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="55e0e-104">La **página Notificaciones de facturación** le permite administrar quién recibe correos electrónicos de notificación de facturación de su organización.</span><span class="sxs-lookup"><span data-stu-id="55e0e-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="55e0e-105">La página también proporciona la opción de recibir las facturas de su organización [como datos adjuntos de correo electrónico.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="55e0e-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="55e0e-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="55e0e-106">Before you begin</span></span>

<span data-ttu-id="55e0e-107">Debe ser un administrador global para realizar los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="55e0e-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="55e0e-108">Los administradores de facturación pueden realizar algunos de estos cambios, como se indica en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="55e0e-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="55e0e-109">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="55e0e-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="55e0e-110">Cambiar el idioma en el que recibe el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="55e0e-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="55e0e-111">Los administradores de facturación también pueden realizar los pasos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="55e0e-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="55e0e-112">Los correos electrónicos de notificación de facturación se envían en el idioma preferido de la organización.</span><span class="sxs-lookup"><span data-stu-id="55e0e-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="55e0e-113">Para cambiar el idioma preferido, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="55e0e-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="55e0e-114">En el centro Microsoft 365 administración, vaya a la página **Notificaciones**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">de facturación de</a> facturación.</span><span class="sxs-lookup"><span data-stu-id="55e0e-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="55e0e-115">En la sección **Configuración de notificación de facturación,** seleccione Editar configuración de **notificación**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="55e0e-116">En el **panel Configuración de notificación de** facturación, en **Idioma** preferido, seleccione el idioma que desea usar y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="55e0e-117">Cambiar quién recibe notificaciones de facturación</span><span class="sxs-lookup"><span data-stu-id="55e0e-117">Change who receives billing notifications</span></span>

<span data-ttu-id="55e0e-118">Las notificaciones de facturación de su organización se envían a la dirección de correo electrónico principal y alternativa de todos los administradores globales y de facturación. Para cambiar qué usuarios tienen el rol de administrador Global o Facturación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="55e0e-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="55e0e-119">Asignar roles de administrador mediante la página Notificaciones de facturación</span><span class="sxs-lookup"><span data-stu-id="55e0e-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="55e0e-120">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="55e0e-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="55e0e-121">En la **sección Administradores que reciben notificaciones de facturación,** seleccione **el** vínculo Administrador de facturación **o** Administrador global en el texto de descripción.</span><span class="sxs-lookup"><span data-stu-id="55e0e-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="55e0e-122">En el panel derecho, en la **pestaña Administradores asignados,** seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="55e0e-123">En el **panel Agregar administradores,** escriba el nombre para mostrar o el nombre de usuario del usuario y, a continuación, seleccione el usuario en la lista de sugerencias.</span><span class="sxs-lookup"><span data-stu-id="55e0e-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="55e0e-124">Agregue varios usuarios hasta que haya terminado.</span><span class="sxs-lookup"><span data-stu-id="55e0e-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="55e0e-125">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-125">Select **Save**.</span></span> <span data-ttu-id="55e0e-126">El usuario se agrega a la lista de administradores asignados.</span><span class="sxs-lookup"><span data-stu-id="55e0e-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="55e0e-127">Quitar roles de administrador mediante la página Notificaciones de facturación</span><span class="sxs-lookup"><span data-stu-id="55e0e-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="55e0e-128">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="55e0e-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="55e0e-129">En la **sección Administradores que reciben notificaciones de facturación,** seleccione **el** vínculo Administrador de facturación **o** Administrador global en el texto de descripción.</span><span class="sxs-lookup"><span data-stu-id="55e0e-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="55e0e-130">En el panel derecho, en la pestaña Administradores **asignados,** seleccione los usuarios que desea quitar del rol y, a continuación, **seleccione Quitar**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="55e0e-131">En el cuadro de confirmación, seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="55e0e-132">El usuario se quita de la lista de administradores asignados.</span><span class="sxs-lookup"><span data-stu-id="55e0e-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="55e0e-133">Cambiar las direcciones de correo electrónico de los administradores</span><span class="sxs-lookup"><span data-stu-id="55e0e-133">Change the email addresses for admins</span></span>

<span data-ttu-id="55e0e-134">Para cambiar la dirección de correo electrónico principal y alternativa de otros administradores de la organización, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="55e0e-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="55e0e-135">Los administradores de facturación pueden cambiar sus propias direcciones de correo electrónico principales y alternativas, pero no para otros administradores.</span><span class="sxs-lookup"><span data-stu-id="55e0e-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="55e0e-136">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="55e0e-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="55e0e-137">En la **sección Administradores que reciben notificaciones de facturación,** seleccione un nombre.</span><span class="sxs-lookup"><span data-stu-id="55e0e-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="55e0e-138">En el panel derecho, agregue o actualice la dirección de correo electrónico principal y alternativa según sea necesario y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="55e0e-139">Cambiar el correo electrónico de contacto de la organización</span><span class="sxs-lookup"><span data-stu-id="55e0e-139">Change your organization's contact email</span></span>

<span data-ttu-id="55e0e-140">Además de los administradores globales y de facturación, enviamos notificaciones de facturación a la dirección de correo electrónico de contacto de su organización.</span><span class="sxs-lookup"><span data-stu-id="55e0e-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="55e0e-141">Para cambiar la dirección de correo electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="55e0e-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="55e0e-142">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="55e0e-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="55e0e-143">En **Contacto de la organización que recibe notificaciones de facturación,** seleccione el contacto de la organización.</span><span class="sxs-lookup"><span data-stu-id="55e0e-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="55e0e-144">En el panel derecho, escriba la dirección de correo electrónico que desea usar y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="55e0e-145">Recibir facturas de su organización como datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="55e0e-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="55e0e-146">Los administradores de facturación también pueden realizar los pasos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="55e0e-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="55e0e-147">Puede tener adjunta una copia de la factura de su organización como un archivo PDF para facturar correos electrónicos de notificación cuando esté lista una nueva factura.</span><span class="sxs-lookup"><span data-stu-id="55e0e-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="55e0e-148">Siga estos pasos para recibir facturas como datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="55e0e-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="55e0e-149">En el Centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificaciones de facturación</a>.</span><span class="sxs-lookup"><span data-stu-id="55e0e-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="55e0e-150">En **Configuración de notificación de facturación,** seleccione Editar configuración de **notificación**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="55e0e-151">En el **panel Configuración de notificaciones de** facturación, en Adjuntar un PDF a los correos electrónicos de facturación, active la casilla y, **a** continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="55e0e-152">Para dejar de recibir los datos adjuntos de la factura en cualquier momento, siga los pasos anteriores y desactive la casilla Adjuntar **un PDF a** los correos electrónicos de la factura en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="55e0e-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="55e0e-153">¿Qué ocurre si tengo un perfil de facturación?</span><span class="sxs-lookup"><span data-stu-id="55e0e-153">What if I have a billing profile?</span></span>

<span data-ttu-id="55e0e-154">Si tienes un perfil de facturación, algunos de los pasos descritos en este artículo pueden ser ligeramente diferentes para algunas de tus suscripciones.</span><span class="sxs-lookup"><span data-stu-id="55e0e-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="55e0e-155">En esta sección se describen esas diferencias.</span><span class="sxs-lookup"><span data-stu-id="55e0e-155">This section describes those differences.</span></span> [<span data-ttu-id="55e0e-156">¿Cómo sé si tengo un perfil de facturación?</span><span class="sxs-lookup"><span data-stu-id="55e0e-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="55e0e-157">Quién Recibe notificaciones de facturación?</span><span class="sxs-lookup"><span data-stu-id="55e0e-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="55e0e-158">Los correos electrónicos de notificación de facturación se envían a las direcciones de correo electrónico principales y alternativas para los usuarios a los que se asigna uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="55e0e-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="55e0e-159">Propietario del perfil de facturación</span><span class="sxs-lookup"><span data-stu-id="55e0e-159">Billing profile owner</span></span>
- <span data-ttu-id="55e0e-160">Colaborador de perfiles de facturación</span><span class="sxs-lookup"><span data-stu-id="55e0e-160">Billing profile contributor</span></span>
- <span data-ttu-id="55e0e-161">Administrador de facturas</span><span class="sxs-lookup"><span data-stu-id="55e0e-161">Invoice manager</span></span>

<span data-ttu-id="55e0e-162">Para obtener más información sobre los roles de perfil de facturación y cómo administrarlos, vea [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span><span class="sxs-lookup"><span data-stu-id="55e0e-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="55e0e-163">Para cambiar quién recibe las notificaciones de facturación de su organización, siga estos pasos para cambiar los roles asignados a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55e0e-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="55e0e-164">En el Centro de administración, vaya a la página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturación & pagos.</a></span><span class="sxs-lookup"><span data-stu-id="55e0e-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="55e0e-165">En la **pestaña Perfil de** facturación, seleccione un perfil de facturación.</span><span class="sxs-lookup"><span data-stu-id="55e0e-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="55e0e-166">En la **sección Roles de perfil de** facturación, asigne o quite roles para **el** propietario del perfil de facturación, el colaborador del perfil **de facturación** o el **administrador de facturación.**</span><span class="sxs-lookup"><span data-stu-id="55e0e-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="55e0e-167">Recibir facturas como datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="55e0e-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="55e0e-168">Para recibir las facturas como datos adjuntos a las notificaciones de factura, siga estos pasos para activar esta configuración para un perfil de facturación específico.</span><span class="sxs-lookup"><span data-stu-id="55e0e-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="55e0e-169">En el Centro de administración, vaya a la página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturación & pagos.</a></span><span class="sxs-lookup"><span data-stu-id="55e0e-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="55e0e-170">Seleccione la **pestaña Perfiles de facturación** y, a continuación, seleccione un perfil de facturación de la lista.</span><span class="sxs-lookup"><span data-stu-id="55e0e-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="55e0e-171">En la página de detalles del perfil de facturación, en **Obtener facturas en datos adjuntos de correo electrónico,** cambie la alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="55e0e-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="55e0e-172">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="55e0e-172">Related content</span></span>

<span data-ttu-id="55e0e-173">[Vea su factura o recibo](view-your-bill-or-invoice.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="55e0e-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)\</span></span>
<span data-ttu-id="55e0e-174">[Información de facturación Microsoft 365 para empresas en México](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (artículo) </span><span class="sxs-lookup"><span data-stu-id="55e0e-174">[Billing information for Microsoft 365 for business in Mexico](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (article) </span></span>\
<span data-ttu-id="55e0e-175">[Comprender la factura o factura de Microsoft 365 para empresas](understand-your-invoice2.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="55e0e-175">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="55e0e-176">[Agregar usuarios y asignar licencias al mismo tiempo](../../admin/add-users/add-users.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="55e0e-176">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
