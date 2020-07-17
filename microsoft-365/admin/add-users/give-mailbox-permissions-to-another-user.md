---
title: 'Conceder permisos de buzón a otro usuario: Ayuda para administradores'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Obtenga información acerca de cómo conceder a un usuario el derecho de acceso al buzón de otro usuario. Esto le dará al usuario el derecho de leer el correo electrónico y enviar correo electrónico desde el buzón del otro usuario. '
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780606"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="d20f1-104">Conceder permisos de buzón a otro usuario: Ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="d20f1-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="d20f1-105">Como administrador, puede que la empresa le requiera que permita que algunos usuarios puedan acceder al buzón de otro usuario.</span><span class="sxs-lookup"><span data-stu-id="d20f1-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="d20f1-106">Por ejemplo, puede que quiera habilitar que un asistente envíe o lea el correo electrónico del buzón de su jefe o bien que uno de los usuarios pueda enviar correo electrónico en nombre de otro.</span><span class="sxs-lookup"><span data-stu-id="d20f1-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="d20f1-107">En este tema se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d20f1-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="d20f1-108">Si está buscando información sobre cómo crear y administrar buzones compartidos, consulte [Crear un buzón compartido](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="d20f1-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="d20f1-109">¿Desea configurar los permisos de buzón?</span><span class="sxs-lookup"><span data-stu-id="d20f1-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="d20f1-p103">Los permisos de buzón le permiten conceder acceso de lectura y escritura en un buzón a otro usuario. Los artículos siguientes pueden proporcionarle la ayuda que necesita para configurar y usar esta característica:</span><span class="sxs-lookup"><span data-stu-id="d20f1-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="d20f1-112">**Configurar los permisos:**</span><span class="sxs-lookup"><span data-stu-id="d20f1-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="d20f1-p104">El primer paso para configurar permisos es decidir qué acciones quiere permitir que el otro usuario realice en el buzón específico. Puede permitir que un usuario lea mensajes de correo electrónico desde el buzón, que envíe mensajes de correo electrónico en nombre de otro usuario y que envíe mensajes de correo electrónico como si se enviasen desde ese buzón. Consulte los siguientes artículos sobre cómo configurar cada tipo de permisos:</span><span class="sxs-lookup"><span data-stu-id="d20f1-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="d20f1-116">Leer correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="d20f1-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="d20f1-117">Enviar correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="d20f1-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="d20f1-118">Enviar correo electrónico en nombre de otro usuario</span><span class="sxs-lookup"><span data-stu-id="d20f1-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="d20f1-119">**Cambiar la propagación:**</span><span class="sxs-lookup"><span data-stu-id="d20f1-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="d20f1-120">Después de configurar los permisos, los cambios pueden tardar hasta 60 minutos en propagarse por el sistema y hacerse efectivos.</span><span class="sxs-lookup"><span data-stu-id="d20f1-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="d20f1-121">**Cómo usarlo una vez que los permisos están configurados:**</span><span class="sxs-lookup"><span data-stu-id="d20f1-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="d20f1-p105">Hay diferentes maneras de acceder a un buzón una vez que se le ha concedido acceso. Para obtener ayuda sobre esta cuestión, consulte este artículo: [Obtener acceso al buzón de otra persona](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span><span class="sxs-lookup"><span data-stu-id="d20f1-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="d20f1-124">Enviar correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="d20f1-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d20f1-125">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="d20f1-126">Seleccione el nombre del usuario (al que piensa conceder permiso de envío) para abrir el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d20f1-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="d20f1-127">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="d20f1-128">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="d20f1-129">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="d20f1-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="d20f1-130">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d20f1-131">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="d20f1-132">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="d20f1-133">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="d20f1-134">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="d20f1-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="d20f1-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d20f1-136">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="d20f1-137">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="d20f1-138">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="d20f1-139">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="d20f1-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="d20f1-140">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="d20f1-141">Leer correo electrónico en el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="d20f1-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d20f1-142">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="d20f1-143">Seleccione el nombre del usuario (cuyo buzón quiere permitir que se lea) para abrir el panel propiedades.</span><span class="sxs-lookup"><span data-stu-id="d20f1-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="d20f1-144">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="d20f1-145">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="d20f1-146">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="d20f1-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="d20f1-147">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d20f1-148">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="d20f1-149">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="d20f1-150">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="d20f1-151">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="d20f1-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="d20f1-152">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d20f1-153">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="d20f1-154">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="d20f1-155">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="d20f1-156">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="d20f1-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="d20f1-157">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="d20f1-158">Enviar correo electrónico en nombre de otro usuario</span><span class="sxs-lookup"><span data-stu-id="d20f1-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d20f1-159">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="d20f1-160">Seleccione el nombre del usuario (al que piensa conceder permiso para **Enviar en nombre de**) para abrir el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d20f1-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="d20f1-161">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="d20f1-162">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="d20f1-163">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="d20f1-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="d20f1-164">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d20f1-165">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="d20f1-166">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="d20f1-167">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="d20f1-168">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="d20f1-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="d20f1-169">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d20f1-170">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="d20f1-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="d20f1-171">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="d20f1-172">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="d20f1-173">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="d20f1-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="d20f1-174">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d20f1-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="d20f1-175">Enviar y leer desde Outlook y Outlook en la Web empresarial</span><span class="sxs-lookup"><span data-stu-id="d20f1-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="d20f1-p106">¿Quiere aprender cómo enviar correo electrónico desde el buzón de otro usuario? Consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d20f1-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="d20f1-178">Administrar elementos de correo y calendario de otra persona</span><span class="sxs-lookup"><span data-stu-id="d20f1-178">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="d20f1-179">Enviar correo electrónico de otra persona o grupo</span><span class="sxs-lookup"><span data-stu-id="d20f1-179">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
