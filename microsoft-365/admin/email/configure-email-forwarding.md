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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configure el reenvío de correo electrónico a una o más cuentas de correo electrónico con Office365.
ms.openlocfilehash: 5807649fa43d094fd8f05cf63e2905d7cdb6dd7d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628920"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="7ed06-103">Configurar el reenvío de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7ed06-103">Configure email forwarding</span></span>
  
<span data-ttu-id="7ed06-104">Como administrador de una organización, es posible que los requisitos de la compañía configuren el reenvío de correo electrónico para el buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="7ed06-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="7ed06-105">El reenvío de correo electrónico le permite reenviar mensajes de correo electrónico enviados al buzón de un usuario al buzón de otro usuario dentro o fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="7ed06-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="7ed06-106">Configurar el reenvío de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7ed06-106">Configure email forwarding</span></span>

 <span data-ttu-id="7ed06-107">Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed06-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="7ed06-108">Una vez que haya configurado el reenvío de correo electrónico, solo se fowarded los correos electrónicos **nuevos** enviados al buzón *de* correo.</span><span class="sxs-lookup"><span data-stu-id="7ed06-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="7ed06-109">El reenvío de correo electrónico requiere que la cuenta *de* tiene una licencia.</span><span class="sxs-lookup"><span data-stu-id="7ed06-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="7ed06-110">Si está configurando el reenvío de correo electrónico porque el usuario ha abandonado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="7ed06-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="7ed06-111">De este modo, varias personas pueden tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="7ed06-111">This way several people can access it.</span></span> <span data-ttu-id="7ed06-112">Sin embargo, un buzón compartido no puede superar los 50 GB.</span><span class="sxs-lookup"><span data-stu-id="7ed06-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="7ed06-113">Para realizar estos pasos, debe ser administrador de Exchange o administrador global en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ed06-113">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="7ed06-114">Para obtener más información, vea el tema [sobre los roles de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7ed06-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="7ed06-115">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="7ed06-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="7ed06-116">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="7ed06-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="7ed06-117">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="7ed06-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="7ed06-118">En la pestaña **correo** , seleccione **administrar reenvío de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="7ed06-119">En la página reenvío de correo, seleccione **reenviar todos los correos electrónicos enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="7ed06-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7ed06-120">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7ed06-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7ed06-121">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="7ed06-122">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="7ed06-122">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7ed06-123">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="7ed06-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="7ed06-124">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="7ed06-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="7ed06-125">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="7ed06-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7ed06-126">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7ed06-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="7ed06-127">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="7ed06-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="7ed06-128">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="7ed06-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="7ed06-129">Expanda **configuración de correo**y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="7ed06-130">En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="7ed06-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7ed06-131">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7ed06-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7ed06-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-132">Select **Save**.</span></span>
    
    <span data-ttu-id="7ed06-133">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="7ed06-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7ed06-134">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="7ed06-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="7ed06-135">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="7ed06-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="7ed06-136">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="7ed06-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7ed06-137">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7ed06-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="7ed06-138">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="7ed06-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="7ed06-139">Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="7ed06-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="7ed06-140">Expanda **configuración de correo**y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="7ed06-141">En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados.</span><span class="sxs-lookup"><span data-stu-id="7ed06-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7ed06-142">Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7ed06-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7ed06-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-143">Select **Save**.</span></span>
    
    <span data-ttu-id="7ed06-144">**Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="7ed06-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7ed06-145">Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="7ed06-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="7ed06-146">O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="7ed06-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="7ed06-147">No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="7ed06-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7ed06-148">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7ed06-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
