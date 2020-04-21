---
title: Agregar otro alias de correo electrónico para un usuario
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Obtenga más información acerca de cómo puede tener más de una dirección de correo electrónico, denominada alias de correo electrónico, asociada a su cuenta de Microsoft 365 para empresas. '
ms.openlocfilehash: 66ff2441c95ed28b2072792fd0a63b16eea85c04
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629088"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="e35a2-103">Agregar otro alias de correo electrónico para un usuario</span><span class="sxs-lookup"><span data-stu-id="e35a2-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="e35a2-104">Este artículo está destinado a los administradores de Microsoft 365 que tienen suscripciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="e35a2-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="e35a2-105">No está dirigido a usuarios particulares.</span><span class="sxs-lookup"><span data-stu-id="e35a2-105">It's not for home users.</span></span>
  
<span data-ttu-id="e35a2-106">Una dirección de correo electrónico principal en Microsoft 365 suele ser la dirección de correo electrónico que se asignó al usuario cuando se creó su cuenta.</span><span class="sxs-lookup"><span data-stu-id="e35a2-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="e35a2-107">Cuando este envía un correo electrónico a un contacto, su dirección de correo electrónico principal es la que normalmente aparece en el campo  *De*  en las aplicaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e35a2-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="e35a2-108">También pueden tener más de una dirección de correo electrónico asociada a su cuenta de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="e35a2-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="e35a2-109">Estas direcciones adicionales se denominan "alias".</span><span class="sxs-lookup"><span data-stu-id="e35a2-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="e35a2-110">Por ejemplo, supongamos que Jenna tiene la dirección de correo electrónico jenna@contosoco.com, pero también quiere recibir correo electrónico en jen@contosoco.com porque algunos usuarios hacen referencia a ella con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="e35a2-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="e35a2-111">Puede crear alias para que ambas direcciones de correo electrónico vayan a la bandeja de entrada de Jenna.</span><span class="sxs-lookup"><span data-stu-id="e35a2-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="e35a2-112">Puede crear hasta 400 alias para un usuario.</span><span class="sxs-lookup"><span data-stu-id="e35a2-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="e35a2-113">No se necesitan licencias o cargos adicionales.</span><span class="sxs-lookup"><span data-stu-id="e35a2-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="e35a2-114">Si desea que varias personas administren el correo electrónico enviado a una sola dirección de correo electrónico como info@NodPublishers.com o sales@NodPublishers.com, cree un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="e35a2-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="e35a2-115">Para obtener más información, consulte [crear un buzón compartido](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="e35a2-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="e35a2-116">Agregar alias de correo electrónico a un usuario</span><span class="sxs-lookup"><span data-stu-id="e35a2-116">Add email aliases to a user</span></span>
<span data-ttu-id="e35a2-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="e35a2-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="e35a2-118">Debe tener [permisos de administrador](../add-users/about-admin-roles.md) para hacer esto.</span><span class="sxs-lookup"><span data-stu-id="e35a2-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e35a2-119">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="e35a2-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e35a2-120">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="e35a2-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e35a2-121">En la página **usuarios activos** , seleccione el usuario > **administrar alias de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="e35a2-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="e35a2-122">No verá esta opción si la persona no tiene una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="e35a2-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="e35a2-123">Seleccione **+ Agregar un alias** y escriba un nuevo alias para el usuario.</span><span class="sxs-lookup"><span data-stu-id="e35a2-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="e35a2-124">Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="e35a2-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="e35a2-125">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="e35a2-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="e35a2-126">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e35a2-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="e35a2-127">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="e35a2-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="e35a2-128">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="e35a2-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="e35a2-129">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e35a2-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="e35a2-130">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="e35a2-130">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 
  
     
5. <span data-ttu-id="e35a2-131">Cuando haya terminado, elija **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e35a2-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="e35a2-132">Espere 24 horas hasta que los alias nuevos se propaguen por Office 365.</span><span class="sxs-lookup"><span data-stu-id="e35a2-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="e35a2-133">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="e35a2-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="e35a2-134">Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="e35a2-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="e35a2-135">**Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="e35a2-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="e35a2-136">Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="e35a2-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="e35a2-137">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="e35a2-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="e35a2-138">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="e35a2-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="e35a2-139">En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.</span><span class="sxs-lookup"><span data-stu-id="e35a2-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="e35a2-140">Junto a **alias de nombre de usuario/correo electrónico**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e35a2-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="e35a2-141">Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="e35a2-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="e35a2-142">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="e35a2-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="e35a2-143">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e35a2-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="e35a2-144">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="e35a2-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="e35a2-145">En el cuadro de texto situado debajo de **alias**, escriba la primera parte del nuevo alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e35a2-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="e35a2-146">Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e35a2-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="e35a2-147">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e35a2-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e35a2-148">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="e35a2-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="e35a2-149">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e35a2-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="e35a2-150">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="e35a2-150">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="e35a2-151">Cuando haya terminado, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e35a2-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="e35a2-152">Espere 24 horas hasta que los alias nuevos se propaguen por Office 365.</span><span class="sxs-lookup"><span data-stu-id="e35a2-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="e35a2-153">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="e35a2-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="e35a2-154">Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="e35a2-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="e35a2-155">**Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="e35a2-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="e35a2-156">Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="e35a2-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="e35a2-157">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="e35a2-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e35a2-158">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="e35a2-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="e35a2-159">En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.</span><span class="sxs-lookup"><span data-stu-id="e35a2-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="e35a2-160">Junto a **alias de nombre de usuario/correo electrónico**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e35a2-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="e35a2-161">Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="e35a2-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="e35a2-162">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="e35a2-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="e35a2-163">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e35a2-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="e35a2-164">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="e35a2-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="e35a2-165">En el cuadro de texto situado debajo de **alias**, escriba la primera parte del nuevo alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e35a2-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="e35a2-166">Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e35a2-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="e35a2-167">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e35a2-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e35a2-168">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="e35a2-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="e35a2-169">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e35a2-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="e35a2-170">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="e35a2-170">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="e35a2-171">Cuando haya terminado, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e35a2-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="e35a2-172">Espere 24 horas hasta que los alias nuevos se propaguen por Office 365.</span><span class="sxs-lookup"><span data-stu-id="e35a2-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="e35a2-173">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="e35a2-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="e35a2-174">Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="e35a2-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="e35a2-175">**Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="e35a2-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="e35a2-176">Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="e35a2-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="e35a2-177">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="e35a2-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="e35a2-178">¿Ha recibido "no se encuentra un parámetro que coincida con el nombre de parámetro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="e35a2-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="e35a2-179">Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro EmailAddresses**" significa que está tardando un poco más en finalizar la configuración de su espacio empresarial, o su dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="e35a2-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="e35a2-180">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="e35a2-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="e35a2-181">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e35a2-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="e35a2-182">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="e35a2-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="e35a2-183">¿Ha adquirido la suscripción con GoDaddy u otro partner?</span><span class="sxs-lookup"><span data-stu-id="e35a2-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="e35a2-184">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="e35a2-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e35a2-185">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="e35a2-185">Related articles</span></span>

[<span data-ttu-id="e35a2-186">Enviar correo electrónico desde otra dirección</span><span class="sxs-lookup"><span data-stu-id="e35a2-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="e35a2-187">Cambiar una dirección de correo electrónico y nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="e35a2-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

