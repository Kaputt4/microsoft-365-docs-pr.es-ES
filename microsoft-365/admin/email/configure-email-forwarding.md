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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: El reenvío de correo electrónico le permite reenviar los mensajes de correo electrónico enviados a un buzón Microsoft 365 de usuario a otro buzón dentro o fuera de la organización.
ms.openlocfilehash: dfea738f5d786b6e476dd02dc92fd0aef452d62f
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730143"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="0059e-103">Configurar el reenvío de correo electrónico en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0059e-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="0059e-104">Como administrador de una organización, es posible que tenga requisitos de la compañía para configurar el reenvío de correo electrónico para el buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="0059e-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="0059e-105">El reenvío de correo electrónico le permite reenviar los mensajes del buzón de correo enviados al buzón de un usuario dentro o fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="0059e-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0059e-106">Puede usar las directivas del filtro de correo no deseado saliente para controlar el reenvío automático a destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="0059e-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="0059e-107">Para obtener más información, consulte [Controlar el reenvío automático de correo electrónico externo en Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="0059e-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="0059e-108">Configurar el reenvío de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0059e-108">Configure email forwarding</span></span>

<span data-ttu-id="0059e-109">Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0059e-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="0059e-110">Permitir que los mensajes reenviados automáticamente se envíen a personas en el dominio remoto.</span><span class="sxs-lookup"><span data-stu-id="0059e-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="0059e-111">Consulta [Administrar dominios remotos](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0059e-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="0059e-112">Una vez configurado el reenvío de correo electrónico, solo se reenviarán los correos electrónicos **nuevos** enviados al buzón de  correo electrónico de *origen*.</span><span class="sxs-lookup"><span data-stu-id="0059e-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="0059e-113">El reenvío de correo electrónico requiere que la cuenta de *origen*  tenga una licencia.</span><span class="sxs-lookup"><span data-stu-id="0059e-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="0059e-114">Si está configurando el reenvío de correo electrónico porque el usuario ha dejado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="0059e-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="0059e-115">De esta forma, varias personas podrán acceder a él.</span><span class="sxs-lookup"><span data-stu-id="0059e-115">This way several people can access it.</span></span> <span data-ttu-id="0059e-116">Sin embargo, un buzón compartido no puede superar los 50 GB.</span><span class="sxs-lookup"><span data-stu-id="0059e-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="0059e-117">Debe ser Administrador de Exchange o Administrador global en Microsoft 365 para poder realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0059e-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="0059e-118">Para obtener más información, consulte el tema [Acerca de los roles de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0059e-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="0059e-119">En el Centro de administración, vaya a la página **Usuarios** \> **[Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822)**.</span><span class="sxs-lookup"><span data-stu-id="0059e-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="0059e-120">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar y, a continuación, abra la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0059e-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="0059e-121">En la pestaña **Correo**, seleccione **Administrar el reenvío de correos**.</span><span class="sxs-lookup"><span data-stu-id="0059e-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="0059e-122">En la página de reenvío de correo electrónico, seleccione **Reenviar todos los mensajes enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los correos electrónicos reenviados.</span><span class="sxs-lookup"><span data-stu-id="0059e-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0059e-123">Si no ve esta opción, asegúrese de tener asignada una licencia asignada a la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="0059e-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0059e-124">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="0059e-124">Select **Save changes**.</span></span>

    <span data-ttu-id="0059e-125">**Para reenviar a varias direcciones de correo**, puede pedir al usuario que configure una regla en Outlook para que se reenvía a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="0059e-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> 
    
    1.  <span data-ttu-id="0059e-126">Abrir **reglas de**  >    >   **inicio de** outlook > Seleccionar administrar reglas & **alertas**</span><span class="sxs-lookup"><span data-stu-id="0059e-126">Open **outlook** > **Home** >  **Rules** > Select **Manage Rules & Alerts**</span></span>
    1. <span data-ttu-id="0059e-127">Seleccione **Nueva regla** Seleccione Aplicar regla en el mensaje que recibo ubicado cerca de la parte inferior de la lista y, a continuación, haga clic en  >   **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0059e-127">Select **New Rule** > **Select Apply rule on message I receive** located near bottom of list, then click **Next**.</span></span>
    1. <span data-ttu-id="0059e-128">Haga **clic en Sí** cuando se le pida Esta regla se aplicará a todos los mensajes que reciba.</span><span class="sxs-lookup"><span data-stu-id="0059e-128">Click **Yes** when asked This rule will be applied to every message you receive.</span></span> 
    1. <span data-ttu-id="0059e-129">En la lista siguiente, seleccione las acciones que **redirigen a personas** o grupos públicos y detenga el procesamiento de más **reglas**</span><span class="sxs-lookup"><span data-stu-id="0059e-129">On the next list select the actions **redirect it to people or public group** and **stop processing more rules**</span></span>
    1. <span data-ttu-id="0059e-130">Haga clic en la frase subrayada **personas o grupo público** en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="0059e-130">Click the underlined phrase **people or public group** in the bottom part of window.</span></span>
    1. <span data-ttu-id="0059e-131">Escriba la **dirección de correo electrónico a** la que se reenviará el correo en el campo Para y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0059e-131">Type the **email address** to forward mail to in the To field, then click **OK**.</span></span>
    1. <span data-ttu-id="0059e-132">Seleccionar **finalizar**</span><span class="sxs-lookup"><span data-stu-id="0059e-132">Select **Finish**</span></span>
    

     <span data-ttu-id="0059e-133">O bien, en el Centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [agregue las direcciones](add-user-or-contact-to-distribution-list.md) y luego, configure el reenvío para que apunte a la DL con las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="0059e-133">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="0059e-134">No elimine la cuenta del usuario cuyo correo electrónico está reenviando ni le quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="0059e-134">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="0059e-135">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0059e-135">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0059e-136">En el Centro de administración, vaya a la página **Usuarios** \> **[Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=847686)**.</span><span class="sxs-lookup"><span data-stu-id="0059e-136">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="0059e-137">Seleccione el nombre del usuario cuyo correo electrónico quiere reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0059e-137">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="0059e-138">Expanda **Configuración de correo** y luego, en la sección **Reenvío de correo electrónico**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0059e-138">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="0059e-139">En la página de reenvío de correo electrónico, establezca el botón de alternancia en **Activado**, escriba la dirección de reenvío y elija si quiere conservar una copia de los correos electrónicos reenviados.</span><span class="sxs-lookup"><span data-stu-id="0059e-139">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0059e-140">Si no ve esta opción, asegúrese de tener asignada una licencia asignada a la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="0059e-140">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0059e-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0059e-141">Select **Save**.</span></span>

   <span data-ttu-id="0059e-142">**Para reenviar a varias direcciones de correo**, puede pedir al usuario que configure una regla en Outlook para que se reenvía a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="0059e-142">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="0059e-143">Para obtener más información, consulte [Usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="0059e-143">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="0059e-144">O bien, en el Centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [agregue las direcciones](add-user-or-contact-to-distribution-list.md) y luego, configure el reenvío para que apunte a la DL con las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="0059e-144">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="0059e-145">No elimine la cuenta del usuario cuyo correo electrónico está reenviando ni le quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="0059e-145">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="0059e-146">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0059e-146">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0059e-147">En el Centro de administración, vaya a la página **Usuarios** \> **[Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=850628)**.</span><span class="sxs-lookup"><span data-stu-id="0059e-147">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="0059e-148">Seleccione el nombre del usuario cuyo correo electrónico quiere reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0059e-148">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="0059e-149">Expanda **Configuración de correo** y luego, en la sección **Reenvío de correo electrónico**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0059e-149">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="0059e-150">En la página de reenvío de correo electrónico, establezca el botón de alternancia en **Activado**, escriba la dirección de reenvío y elija si quiere conservar una copia de los correos electrónicos reenviados.</span><span class="sxs-lookup"><span data-stu-id="0059e-150">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0059e-151">Si no ve esta opción, asegúrese de tener asignada una licencia asignada a la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="0059e-151">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0059e-152">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0059e-152">Select **Save**.</span></span>

   <span data-ttu-id="0059e-153">**Para reenviar a varias direcciones de correo**, puede pedir al usuario que configure una regla en Outlook para que se reenvía a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="0059e-153">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="0059e-154">Para obtener más información, consulte [Usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="0059e-154">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="0059e-155">O bien, en el Centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [agregue las direcciones](add-user-or-contact-to-distribution-list.md) y luego, configure el reenvío para que apunte a la DL con las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="0059e-155">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="0059e-156">No elimine la cuenta del usuario cuyo correo electrónico está reenviando ni le quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="0059e-156">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="0059e-157">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0059e-157">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="0059e-158">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="0059e-158">Related content</span></span> 

<span data-ttu-id="0059e-159">[Crear un buzón compartido](../email/create-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0059e-159">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="0059e-160">[Enviar correo electrónico desde una dirección](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) diferente (artículo)</span><span class="sxs-lookup"><span data-stu-id="0059e-160">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="0059e-161">[Cambiar un nombre de usuario y una dirección de correo electrónico](../add-users/change-a-user-name-and-email-address.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0059e-161">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
