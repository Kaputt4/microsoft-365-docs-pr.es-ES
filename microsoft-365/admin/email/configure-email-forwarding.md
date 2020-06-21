---
title: Configurar el reenvío de correo electrónico
f1.keywords:
- NOCSH
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configure el reenvío de correo electrónico a una o más cuentas de correo electrónico con Office365.
ms.openlocfilehash: f6c177ba37cf2b8ce3966732adbe8428d9b6179e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780258"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="00ca4-103">Configurar el reenvío de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="00ca4-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="00ca4-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="00ca4-104">The admin center is changing.</span></span> <span data-ttu-id="00ca4-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="00ca4-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="00ca4-106">Como administrador de una organización, es posible que los requisitos de la compañía configuren el reenvío de correo electrónico para el buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="00ca4-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="00ca4-107">El reenvío de correo electrónico le permite reenviar mensajes de correo electrónico enviados al buzón de un usuario al buzón de otro usuario dentro o fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="00ca4-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="00ca4-108">Configurar el reenvío de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="00ca4-108">Configure email forwarding</span></span>

 <span data-ttu-id="00ca4-109">Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="00ca4-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="00ca4-110">Una vez que haya configurado el reenvío de correo electrónico, solo se fowarded los correos electrónicos **nuevos** enviados al buzón *de* correo.</span><span class="sxs-lookup"><span data-stu-id="00ca4-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="00ca4-111">El reenvío de correo electrónico requiere que la cuenta *de* tiene una licencia.</span><span class="sxs-lookup"><span data-stu-id="00ca4-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="00ca4-112">Si está configurando el reenvío de correo electrónico porque el usuario ha abandonado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="00ca4-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="00ca4-113">De este modo, varias personas pueden tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="00ca4-113">This way several people can access it.</span></span> <span data-ttu-id="00ca4-114">Sin embargo, un buzón compartido no puede superar los 50 GB.</span><span class="sxs-lookup"><span data-stu-id="00ca4-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="00ca4-115">Para realizar estos pasos, debe ser administrador de Exchange o administrador global en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00ca4-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="00ca4-116">Para obtener más información, vea el tema [sobre los roles de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="00ca4-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="00ca4-117">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="00ca4-117">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="00ca4-118">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="00ca4-118">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="00ca4-119">En la pestaña **correo** , seleccione **administrar reenvío de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="00ca4-119">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="00ca4-120">En la página reenvío de correo, seleccione **reenviar todos los correos electrónicos enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="00ca4-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="00ca4-121">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="00ca4-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="00ca4-122">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="00ca4-122">Select **Save changes**.</span></span>
    
    <span data-ttu-id="00ca4-123">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="00ca4-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="00ca4-124">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="00ca4-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="00ca4-125">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="00ca4-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="00ca4-126">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="00ca4-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="00ca4-127">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="00ca4-127">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="00ca4-128">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="00ca4-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="00ca4-129">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="00ca4-129">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="00ca4-130">Expanda **configuración de correo**y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="00ca4-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="00ca4-131">En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="00ca4-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="00ca4-132">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="00ca4-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="00ca4-133">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="00ca4-133">Select **Save**.</span></span>
    
    <span data-ttu-id="00ca4-134">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="00ca4-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="00ca4-135">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="00ca4-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="00ca4-136">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="00ca4-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="00ca4-137">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="00ca4-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="00ca4-138">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="00ca4-138">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="00ca4-139">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="00ca4-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="00ca4-140">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="00ca4-140">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="00ca4-141">Expanda **configuración de correo**y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="00ca4-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="00ca4-142">En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="00ca4-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="00ca4-143">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="00ca4-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="00ca4-144">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="00ca4-144">Select **Save**.</span></span>
    
    <span data-ttu-id="00ca4-145">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="00ca4-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="00ca4-146">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="00ca4-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="00ca4-147">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="00ca4-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="00ca4-148">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="00ca4-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="00ca4-149">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="00ca4-149">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
