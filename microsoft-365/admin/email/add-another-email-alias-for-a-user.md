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
ms.openlocfilehash: 590782f7b22b1d26abef83f884d45da567f0425c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915955"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="fdd70-103">Agregar otro alias de correo electrónico para un usuario</span><span class="sxs-lookup"><span data-stu-id="fdd70-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fdd70-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="fdd70-104">The admin center is changing.</span></span> <span data-ttu-id="fdd70-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="fdd70-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="fdd70-106">Este artículo está para administradores de Microsoft 365 que tienen suscripciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="fdd70-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="fdd70-107">No está dirigido a usuarios particulares.</span><span class="sxs-lookup"><span data-stu-id="fdd70-107">It's not for home users.</span></span>
  
<span data-ttu-id="fdd70-108">Una dirección de correo electrónico principal en Microsoft 365 suele ser la dirección de correo electrónico que se asignó a un usuario cuando se creó su cuenta.</span><span class="sxs-lookup"><span data-stu-id="fdd70-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="fdd70-109">Cuando este envía un correo electrónico a un contacto, su dirección de correo electrónico principal es la que normalmente aparece en el campo  *De*  en las aplicaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="fdd70-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="fdd70-110">También pueden tener más de una dirección de correo electrónico asociada a su cuenta de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="fdd70-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="fdd70-111">Estas direcciones adicionales se denominan "alias".</span><span class="sxs-lookup"><span data-stu-id="fdd70-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="fdd70-112">Por ejemplo, supongamos que Jenna tiene la dirección de correo electrónico jenna@contosoco.com, pero también quiere recibir correo electrónico en jen@contosoco.com porque algunas personas hacen referencia a ella por ese nombre.</span><span class="sxs-lookup"><span data-stu-id="fdd70-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="fdd70-113">Puede crear alias para ella para que ambas direcciones de correo electrónico vayan a la bandeja de entrada de Jenna.</span><span class="sxs-lookup"><span data-stu-id="fdd70-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="fdd70-114">Puede crear hasta 400 alias para un usuario.</span><span class="sxs-lookup"><span data-stu-id="fdd70-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="fdd70-115">No se necesitan licencias o cargos adicionales.</span><span class="sxs-lookup"><span data-stu-id="fdd70-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="fdd70-116">Si desea que varias personas administren el correo electrónico enviado a una única dirección de correo electrónico como info@NodPublishers.com o sales@NodPublishers.com, cree un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="fdd70-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="fdd70-117">Para obtener más información, vea [Create a shared mailbox](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="fdd70-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="fdd70-118">Agregar alias de correo electrónico a un usuario</span><span class="sxs-lookup"><span data-stu-id="fdd70-118">Add email aliases to a user</span></span>
<span data-ttu-id="fdd70-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="fdd70-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="fdd70-120">Debe tener permisos [de administrador](../add-users/about-admin-roles.md) para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="fdd70-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="fdd70-121">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="fdd70-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="fdd70-122">En la **página Usuarios activos,** seleccione el usuario > **Administrar alias de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="fdd70-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="fdd70-123">No verá esta opción si la persona no tiene una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="fdd70-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="fdd70-124">Seleccione **+ Agregar un alias** y escriba un nuevo alias para el usuario.</span><span class="sxs-lookup"><span data-stu-id="fdd70-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="fdd70-125">Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre del parámetro **'EmailAddresses",** significa que tarda un poco más en terminar de configurar el espacio empresarial o el dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="fdd70-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="fdd70-126">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="fdd70-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="fdd70-127">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fdd70-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="fdd70-128">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="fdd70-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="fdd70-129">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="fdd70-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="fdd70-130">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdd70-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="fdd70-131">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="fdd70-131">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="fdd70-132">Cuando haya terminado, elija **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="fdd70-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="fdd70-133">Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdd70-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="fdd70-134">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="fdd70-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="fdd70-135">Por ejemplo, todo el correo enviado a la dirección principal de Eliza Hoffman, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irá a la Bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="fdd70-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="fdd70-136">**Cuando el usuario responda, la dirección *De*  será su alias de correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="fdd70-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="fdd70-137">Por ejemplo, supongamos que un mensaje se envía a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="fdd70-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="fdd70-138">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="fdd70-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="fdd70-139">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="fdd70-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="fdd70-140">En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.</span><span class="sxs-lookup"><span data-stu-id="fdd70-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="fdd70-141">Junto a **Nombre de usuario / Alias de correo** electrónico, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fdd70-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="fdd70-142">Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre del parámetro **'EmailAddresses",** significa que tarda un poco más en terminar de configurar el espacio empresarial o el dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="fdd70-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="fdd70-143">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="fdd70-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="fdd70-144">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fdd70-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="fdd70-145">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="fdd70-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="fdd70-146">En el cuadro de texto **en Alias**, escriba la primera parte del nuevo alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="fdd70-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="fdd70-147">Si ha agregado su propio dominio a Microsoft 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdd70-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="fdd70-148">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fdd70-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fdd70-149">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="fdd70-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="fdd70-150">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdd70-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="fdd70-151">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="fdd70-151">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="fdd70-152">Cuando haya acabado, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fdd70-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="fdd70-153">Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdd70-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="fdd70-154">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="fdd70-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="fdd70-155">Por ejemplo, todo el correo enviado a la dirección principal de Eliza Hoffman, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irá a la Bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="fdd70-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="fdd70-156">**Cuando el usuario responda, la dirección *De*  será su alias de correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="fdd70-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="fdd70-157">Por ejemplo, supongamos que un mensaje se envía a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="fdd70-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="fdd70-158">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="fdd70-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fdd70-159">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="fdd70-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="fdd70-160">En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.</span><span class="sxs-lookup"><span data-stu-id="fdd70-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="fdd70-161">Junto a **Nombre de usuario / Alias de correo** electrónico, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fdd70-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="fdd70-162">Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre del parámetro **'EmailAddresses",** significa que tarda un poco más en terminar de configurar el espacio empresarial o el dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="fdd70-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="fdd70-163">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="fdd70-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="fdd70-164">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fdd70-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="fdd70-165">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="fdd70-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="fdd70-166">En el cuadro de texto **en Alias**, escriba la primera parte del nuevo alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="fdd70-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="fdd70-167">Si ha agregado su propio dominio a Microsoft 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdd70-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="fdd70-168">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fdd70-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fdd70-169">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="fdd70-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="fdd70-170">El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdd70-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="fdd70-171">Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="fdd70-171">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="fdd70-172">Cuando haya acabado, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fdd70-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="fdd70-173">Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdd70-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="fdd70-174">El usuario ahora tendrá una dirección principal y un alias.</span><span class="sxs-lookup"><span data-stu-id="fdd70-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="fdd70-175">Por ejemplo, todo el correo enviado a la dirección principal de Eliza Hoffman, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irá a la Bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="fdd70-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="fdd70-176">**Cuando el usuario responda, la dirección *De*  será su alias de correo electrónico principal.**</span><span class="sxs-lookup"><span data-stu-id="fdd70-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="fdd70-177">Por ejemplo, supongamos que un mensaje se envía a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="fdd70-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="fdd70-178">Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="fdd70-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="fdd70-179">¿Ha recibido "No se puede encontrar un parámetro que coincida con el nombre del parámetro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="fdd70-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="fdd70-180">Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre del parámetro **EmailAddresses**" significa que tarda un poco más en terminar de configurar el espacio empresarial o el dominio personalizado si agregó uno recientemente.</span><span class="sxs-lookup"><span data-stu-id="fdd70-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="fdd70-181">El proceso de configuración puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="fdd70-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="fdd70-182">Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fdd70-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="fdd70-183">Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.</span><span class="sxs-lookup"><span data-stu-id="fdd70-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="fdd70-184">¿Ha adquirido la suscripción con GoDaddy u otro partner?</span><span class="sxs-lookup"><span data-stu-id="fdd70-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="fdd70-185">Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.</span><span class="sxs-lookup"><span data-stu-id="fdd70-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="fdd70-186">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="fdd70-186">Related articles</span></span>

[<span data-ttu-id="fdd70-187">Enviar correo electrónico desde otra dirección</span><span class="sxs-lookup"><span data-stu-id="fdd70-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="fdd70-188">Cambiar una dirección de correo electrónico y nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="fdd70-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
