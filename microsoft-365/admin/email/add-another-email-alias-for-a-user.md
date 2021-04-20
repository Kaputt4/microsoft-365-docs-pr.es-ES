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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Obtenga información sobre cómo puede tener más de una dirección de correo electrónico, denominada alias de correo electrónico, asociada a su cuenta de Microsoft 365 para empresas. '
ms.openlocfilehash: 4003dcfca29a722ccdf9b86cca5aa1141fbdb367
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892810"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="8d9c9-103">Agregar otro alias de correo electrónico para un usuario</span><span class="sxs-lookup"><span data-stu-id="8d9c9-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="8d9c9-104">Este artículo está para administradores de Microsoft 365 que tienen suscripciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="8d9c9-105">No está dirigido a usuarios particulares.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-105">It's not for home users.</span></span>
  
<span data-ttu-id="8d9c9-106">Una dirección de correo electrónico principal en Microsoft 365 suele ser la dirección de correo electrónico que se asignó a un usuario cuando se creó su cuenta.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="8d9c9-107">Cuando este envía un correo electrónico a un contacto, su dirección de correo electrónico principal es la que normalmente aparece en el campo  *De*  en las aplicaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="8d9c9-108">También pueden tener más de una dirección de correo electrónico asociada a su cuenta de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="8d9c9-109">Estas direcciones adicionales se denominan "alias".</span><span class="sxs-lookup"><span data-stu-id="8d9c9-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="8d9c9-110">Por ejemplo, supongamos que Jenna tiene la dirección de correo electrónico jenna@contosoco.com, pero también quiere recibir correo electrónico en jen@contosoco.com porque algunas personas hacen referencia a ella por ese nombre.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="8d9c9-111">Puede crear alias para ella para que ambas direcciones de correo electrónico vayan a la bandeja de entrada de Jenna.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="8d9c9-112">Puede crear hasta 400 alias para un usuario.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="8d9c9-113">No se necesitan licencias o cargos adicionales.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="8d9c9-114">Si desea que varias personas administren el correo electrónico enviado a una única dirección de correo electrónico como info@NodPublishers.com o sales@NodPublishers.com, cree un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="8d9c9-115">Para obtener más información, vea [Create a shared mailbox](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="8d9c9-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="8d9c9-116">Agregar alias de correo electrónico a un usuario</span><span class="sxs-lookup"><span data-stu-id="8d9c9-116">Add email aliases to a user</span></span>
<span data-ttu-id="8d9c9-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="8d9c9-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="8d9c9-118">Debe tener permisos [de administrador](../add-users/about-admin-roles.md) para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="8d9c9-119">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="8d9c9-120">En la **página Usuarios activos,** seleccione el usuario > **Administrar alias de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-120">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="8d9c9-121">No verá esta opción si la persona no tiene una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-121">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="8d9c9-122">Seleccione **+ Agregar un alias** y escriba un nuevo alias para el usuario.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-122">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="8d9c9-123">Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre del parámetro **'EmailAddresses",** significa que tarda un poco más en terminar de configurar el espacio empresarial o el dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-123">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8d9c9-124">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-124">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8d9c9-125">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-125">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8d9c9-126">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-126">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="8d9c9-127">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-127">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="8d9c9-128">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-128">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="8d9c9-129">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="8d9c9-129">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="8d9c9-130">Cuando haya terminado, elija **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-130">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="8d9c9-131">Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-131">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="8d9c9-132">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-132">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="8d9c9-133">Por ejemplo, todo el correo enviado a la dirección principal de Eliza Hoffman, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irá a la Bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-133">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="8d9c9-134">**Cuando el usuario responda, la *dirección De* dependerá de su cliente de Outlook. Outlook en la web usará el alias en el que se recibió el correo electrónico (lo llamaremos el principio ping-pong). El escritorio de Outlook usará su alias de correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="8d9c9-134">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="8d9c9-135">Por ejemplo, supongamos que un mensaje se envía a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-135">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="8d9c9-136">Cuando Eliza responde al mensaje con el escritorio de Outlook, su dirección de correo electrónico principal aparecerá como Eliza@NodPublishers.com, no Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-136">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="8d9c9-137">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="8d9c9-138">En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-138">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="8d9c9-139">Junto a **Nombre de usuario / Alias de correo** electrónico, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-139">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="8d9c9-140">Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre del parámetro **'EmailAddresses",** significa que tarda un poco más en terminar de configurar el espacio empresarial o el dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-140">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8d9c9-141">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-141">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8d9c9-142">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-142">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8d9c9-143">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-143">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="8d9c9-144">En el cuadro de texto **en Alias**, escriba la primera parte del nuevo alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-144">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="8d9c9-145">Si ha agregado su propio dominio a Microsoft 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-145">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="8d9c9-146">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-146">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8d9c9-147">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-147">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="8d9c9-148">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-148">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="8d9c9-149">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="8d9c9-149">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="8d9c9-150">Cuando haya acabado, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-150">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="8d9c9-151">Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-151">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="8d9c9-152">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-152">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="8d9c9-153">Por ejemplo, todo el correo enviado a la dirección principal de Eliza Hoffman, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irá a la Bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-153">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="8d9c9-154">**Cuando el usuario responda, la *dirección De* dependerá de su cliente de Outlook. Outlook en la web usará el alias en el que se recibió el correo electrónico (lo llamaremos el principio ping-pong). El escritorio de Outlook usará su alias de correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="8d9c9-154">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="8d9c9-155">Por ejemplo, supongamos que un mensaje se envía a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-155">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="8d9c9-156">Cuando Eliza responde al mensaje con el escritorio de Outlook, su dirección de correo electrónico principal aparecerá como Eliza@NodPublishers.com, no Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-156">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8d9c9-157">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="8d9c9-158">En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-158">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="8d9c9-159">Junto a **Nombre de usuario / Alias de correo** electrónico, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-159">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="8d9c9-160">Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre del parámetro **'EmailAddresses",** significa que tarda un poco más en terminar de configurar el espacio empresarial o el dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-160">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8d9c9-161">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-161">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8d9c9-162">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-162">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8d9c9-163">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-163">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="8d9c9-164">En el cuadro de texto **en Alias**, escriba la primera parte del nuevo alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-164">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="8d9c9-165">Si ha agregado su propio dominio a Microsoft 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-165">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="8d9c9-166">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-166">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8d9c9-167">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-167">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="8d9c9-168">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-168">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="8d9c9-169">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="8d9c9-169">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="8d9c9-170">Cuando haya acabado, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-170">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="8d9c9-171">Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-171">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="8d9c9-172">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-172">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="8d9c9-173">Por ejemplo, todo el correo enviado a la dirección principal de Eliza Hoffman, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irá a la Bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-173">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="8d9c9-174">**Cuando el usuario responda, la *dirección De* dependerá de su cliente de Outlook. Outlook en la web usará el alias en el que se recibió el correo electrónico (lo llamaremos el principio ping-pong). El escritorio de Outlook usará su alias de correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="8d9c9-174">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="8d9c9-175">Por ejemplo, supongamos que un mensaje se envía a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-175">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="8d9c9-176">Cuando Eliza responde al mensaje con el escritorio de Outlook, su dirección de correo electrónico principal aparecerá como Eliza@NodPublishers.com, no Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-176">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="8d9c9-177">¿Ha recibido "No se puede encontrar un parámetro que coincida con el nombre del parámetro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="8d9c9-177">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="8d9c9-178">Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre del parámetro **EmailAddresses**" significa que tarda un poco más en terminar de configurar el espacio empresarial o el dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-178">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="8d9c9-179">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-179">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="8d9c9-180">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-180">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="8d9c9-181">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-181">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="8d9c9-182">¿Ha adquirido la suscripción con GoDaddy u otro partner?</span><span class="sxs-lookup"><span data-stu-id="8d9c9-182">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="8d9c9-183">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-183">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="8d9c9-184">Enviar correo electrónico desde la dirección proxy fácilmente</span><span class="sxs-lookup"><span data-stu-id="8d9c9-184">Sending email from the proxy address easily</span></span>

<span data-ttu-id="8d9c9-185">En abril de 2021 se está implementando una nueva característica que permite a los usuarios enviar desde sus alias fácilmente al usar Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-185">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="8d9c9-186">Cuando la característica se lanza a un arrendamiento en el que el administrador de inquilinos usa el cmdlet, los usuarios del arrendamiento tendrán acceso a una lista de casillas donde cada entrada corresponde a un alias en su configuración de `Set-OrganizationConfig -SendFromAliasEnabled $true` Outlook.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-186">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="8d9c9-187">Si selecciona un alias, aparecerá en el desplegable De del formulario Redacción.</span><span class="sxs-lookup"><span data-stu-id="8d9c9-187">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="8d9c9-188">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="8d9c9-188">Related articles</span></span>

[<span data-ttu-id="8d9c9-189">Enviar correo electrónico desde otra dirección</span><span class="sxs-lookup"><span data-stu-id="8d9c9-189">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="8d9c9-190">Cambiar una dirección de correo electrónico y nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="8d9c9-190">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
