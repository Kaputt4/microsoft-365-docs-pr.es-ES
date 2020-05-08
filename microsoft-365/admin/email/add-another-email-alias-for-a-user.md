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
ms.openlocfilehash: 603b2f42d603ae5172c66b6f78bc55f8d44c81f5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140517"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="8959f-103">Agregar otro alias de correo electrónico para un usuario</span><span class="sxs-lookup"><span data-stu-id="8959f-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8959f-104">El centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="8959f-104">The admin center is changing.</span></span> <span data-ttu-id="8959f-105">Si su experiencia no coincide con los detalles que se presentan aquí, vea [acerca del nuevo centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8959f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="8959f-106">Este artículo está destinado a los administradores de Microsoft 365 que tienen suscripciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="8959f-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="8959f-107">No está dirigido a usuarios particulares.</span><span class="sxs-lookup"><span data-stu-id="8959f-107">It's not for home users.</span></span>
  
<span data-ttu-id="8959f-108">Una dirección de correo electrónico principal en Microsoft 365 suele ser la dirección de correo electrónico que se asignó al usuario cuando se creó su cuenta.</span><span class="sxs-lookup"><span data-stu-id="8959f-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="8959f-109">Cuando este envía un correo electrónico a un contacto, su dirección de correo electrónico principal es la que normalmente aparece en el campo  *De*  en las aplicaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8959f-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="8959f-110">También pueden tener más de una dirección de correo electrónico asociada a su cuenta de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="8959f-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="8959f-111">Estas direcciones adicionales se denominan "alias".</span><span class="sxs-lookup"><span data-stu-id="8959f-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="8959f-112">Por ejemplo, supongamos que Jenna tiene la dirección de correo electrónico jenna@contosoco.com, pero también quiere recibir correo electrónico en jen@contosoco.com porque algunos usuarios hacen referencia a ella con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="8959f-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="8959f-113">Puede crear alias para que ambas direcciones de correo electrónico vayan a la bandeja de entrada de Jenna.</span><span class="sxs-lookup"><span data-stu-id="8959f-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="8959f-114">Puede crear hasta 400 alias para un usuario.</span><span class="sxs-lookup"><span data-stu-id="8959f-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="8959f-115">No se necesitan licencias o cargos adicionales.</span><span class="sxs-lookup"><span data-stu-id="8959f-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="8959f-116">Si desea que varias personas administren el correo electrónico enviado a una sola dirección de correo electrónico como info@NodPublishers.com o sales@NodPublishers.com, cree un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="8959f-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="8959f-117">Para obtener más información, consulte [crear un buzón compartido](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="8959f-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="8959f-118">Agregar alias de correo electrónico a un usuario</span><span class="sxs-lookup"><span data-stu-id="8959f-118">Add email aliases to a user</span></span>
<span data-ttu-id="8959f-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="8959f-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="8959f-120">Debe tener [permisos de administrador](../add-users/about-admin-roles.md) para hacer esto.</span><span class="sxs-lookup"><span data-stu-id="8959f-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="8959f-121">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="8959f-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="8959f-122">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8959f-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="8959f-123">En la página **usuarios activos** , seleccione el usuario > **administrar alias de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="8959f-123">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="8959f-124">No verá esta opción si la persona no tiene una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="8959f-124">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="8959f-125">Seleccione **+ Agregar un alias** y escriba un nuevo alias para el usuario.</span><span class="sxs-lookup"><span data-stu-id="8959f-125">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="8959f-126">Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="8959f-126">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8959f-127">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="8959f-127">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8959f-128">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8959f-128">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8959f-129">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="8959f-129">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="8959f-130">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="8959f-130">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="8959f-131">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8959f-131">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="8959f-132">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="8959f-132">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="8959f-133">Cuando haya terminado, elija **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8959f-133">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="8959f-134">Espere 24 horas hasta que los alias nuevos se propaguen por Office 365.</span><span class="sxs-lookup"><span data-stu-id="8959f-134">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="8959f-135">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="8959f-135">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="8959f-136">Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="8959f-136">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="8959f-137">**Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="8959f-137">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="8959f-138">Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="8959f-138">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="8959f-139">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="8959f-139">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="8959f-140">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8959f-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="8959f-141">En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.</span><span class="sxs-lookup"><span data-stu-id="8959f-141">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="8959f-142">Junto a **alias de nombre de usuario/correo electrónico**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8959f-142">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="8959f-143">Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="8959f-143">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8959f-144">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="8959f-144">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8959f-145">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8959f-145">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8959f-146">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="8959f-146">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="8959f-147">En el cuadro de texto situado debajo de **alias**, escriba la primera parte del nuevo alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8959f-147">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="8959f-148">Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8959f-148">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="8959f-149">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8959f-149">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8959f-150">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="8959f-150">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="8959f-151">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8959f-151">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="8959f-152">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="8959f-152">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="8959f-153">Cuando haya terminado, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8959f-153">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="8959f-154">Espere 24 horas hasta que los alias nuevos se propaguen por Office 365.</span><span class="sxs-lookup"><span data-stu-id="8959f-154">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="8959f-155">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="8959f-155">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="8959f-156">Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="8959f-156">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="8959f-157">**Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="8959f-157">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="8959f-158">Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="8959f-158">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="8959f-159">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="8959f-159">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8959f-160">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8959f-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="8959f-161">En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.</span><span class="sxs-lookup"><span data-stu-id="8959f-161">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="8959f-162">Junto a **alias de nombre de usuario/correo electrónico**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8959f-162">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="8959f-163">Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="8959f-163">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8959f-164">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="8959f-164">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8959f-165">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8959f-165">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8959f-166">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="8959f-166">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="8959f-167">En el cuadro de texto situado debajo de **alias**, escriba la primera parte del nuevo alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8959f-167">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="8959f-168">Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8959f-168">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="8959f-169">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8959f-169">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8959f-170">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="8959f-170">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="8959f-171">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8959f-171">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="8959f-172">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="8959f-172">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="8959f-173">Cuando haya terminado, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8959f-173">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="8959f-174">Espere 24 horas hasta que los alias nuevos se propaguen por Office 365.</span><span class="sxs-lookup"><span data-stu-id="8959f-174">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="8959f-175">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="8959f-175">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="8959f-176">Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="8959f-176">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="8959f-177">**Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="8959f-177">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="8959f-178">Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara.</span><span class="sxs-lookup"><span data-stu-id="8959f-178">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="8959f-179">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="8959f-179">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="8959f-180">¿Ha recibido "no se encuentra un parámetro que coincida con el nombre de parámetro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="8959f-180">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="8959f-181">Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro EmailAddresses**" significa que está tardando un poco más en finalizar la configuración de su espacio empresarial, o su dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="8959f-181">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8959f-182">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="8959f-182">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8959f-183">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8959f-183">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8959f-184">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="8959f-184">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="8959f-185">¿Ha adquirido la suscripción con GoDaddy u otro partner?</span><span class="sxs-lookup"><span data-stu-id="8959f-185">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="8959f-186">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="8959f-186">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="8959f-187">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="8959f-187">Related articles</span></span>

[<span data-ttu-id="8959f-188">Enviar correo electrónico desde otra dirección</span><span class="sxs-lookup"><span data-stu-id="8959f-188">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="8959f-189">Cambiar una dirección de correo electrónico y nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="8959f-189">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

