---
title: Configurar el reenvío de correo electrónico
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configure el reenvío de correo electrónico a una o más cuentas de correo electrónico con Office365.
ms.openlocfilehash: 5bbb7d4fa122051725418153e43f40aec370de61
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580620"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="e9cc0-103">Configurar el reenvío de correo electrónico en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9cc0-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e9cc0-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-104">The admin center is changing.</span></span> <span data-ttu-id="e9cc0-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="e9cc0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="e9cc0-106">Como administrador de una organización, es posible que los requisitos de la compañía configuren el reenvío de correo electrónico para el buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="e9cc0-107">El reenvío de correo electrónico le permite reenviar mensajes de correo electrónico enviados al buzón de un usuario al buzón de otro usuario dentro o fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9cc0-108">Puede usar las directivas de filtro de correo no deseado saliente para controlar el reenvío automático a los destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="e9cc0-109">Para obtener más información, consulte [controlar el reenvío de correo externo automático en Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="e9cc0-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="e9cc0-110">Configurar el reenvío de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e9cc0-110">Configure email forwarding</span></span>

<span data-ttu-id="e9cc0-111">Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9cc0-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="e9cc0-112">Una vez que haya configurado el reenvío de correo electrónico, solo se reenviarán los correos electrónicos **nuevos** que se envíen al buzón  *de*  .</span><span class="sxs-lookup"><span data-stu-id="e9cc0-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="e9cc0-113">El reenvío de correo electrónico requiere que la cuenta  *de*  tiene una licencia.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="e9cc0-114">Si está configurando el reenvío de correo electrónico porque el usuario ha abandonado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="e9cc0-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="e9cc0-115">De este modo, varias personas pueden tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-115">This way several people can access it.</span></span> <span data-ttu-id="e9cc0-116">Sin embargo, un buzón compartido no puede superar los 50 GB.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="e9cc0-117">Para realizar estos pasos, debe ser administrador de Exchange o administrador global en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="e9cc0-118">Para obtener más información, vea el tema [sobre los roles de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e9cc0-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e9cc0-119">En el centro de administración, vaya a **la página usuarios** \> **[activos](https://go.microsoft.com/fwlink/p/?linkid=834822)** .</span><span class="sxs-lookup"><span data-stu-id="e9cc0-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="e9cc0-120">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="e9cc0-121">En la pestaña **correo** , seleccione **administrar reenvío de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="e9cc0-122">En la página reenvío de correo, seleccione **reenviar todos los correos electrónicos enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e9cc0-123">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e9cc0-124">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-124">Select **Save changes**.</span></span>

    <span data-ttu-id="e9cc0-125">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e9cc0-126">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e9cc0-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="e9cc0-127">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="e9cc0-128">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e9cc0-129">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e9cc0-130">En el centro de administración, vaya a **la página usuarios** \> **[activos](https://go.microsoft.com/fwlink/p/?linkid=847686)** .</span><span class="sxs-lookup"><span data-stu-id="e9cc0-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="e9cc0-131">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="e9cc0-132">Expanda **configuración de correo** y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="e9cc0-133">En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e9cc0-134">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e9cc0-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-135">Select **Save**.</span></span>

   <span data-ttu-id="e9cc0-136">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e9cc0-137">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e9cc0-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="e9cc0-138">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="e9cc0-139">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e9cc0-140">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e9cc0-141">En el centro de administración, vaya a **la página usuarios** \> **[activos](https://go.microsoft.com/fwlink/p/?linkid=850628)** .</span><span class="sxs-lookup"><span data-stu-id="e9cc0-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="e9cc0-142">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="e9cc0-143">Expanda **configuración de correo** y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="e9cc0-144">En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e9cc0-145">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e9cc0-146">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-146">Select **Save**.</span></span>

   <span data-ttu-id="e9cc0-147">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e9cc0-148">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e9cc0-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="e9cc0-149">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="e9cc0-150">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e9cc0-151">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e9cc0-151">If you do, email forwarding will stop.</span></span>

::: moniker-end
