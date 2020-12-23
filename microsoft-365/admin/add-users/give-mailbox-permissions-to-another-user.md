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
ms.openlocfilehash: af12cfe3acad9e12ca3983c9fa13f52b72f0a467
ms.sourcegitcommit: 16e018f8b6eef5dad48eabf179691ead3cebe533
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2020
ms.locfileid: "49725158"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="442f4-104">Conceder permisos de buzón a otro usuario: Ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="442f4-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="442f4-105">Como administrador, puede que la empresa le requiera que permita que algunos usuarios puedan acceder al buzón de otro usuario.</span><span class="sxs-lookup"><span data-stu-id="442f4-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="442f4-106">Por ejemplo, puede que quiera habilitar que un asistente envíe o lea el correo electrónico del buzón de su jefe o bien que uno de los usuarios pueda enviar correo electrónico en nombre de otro.</span><span class="sxs-lookup"><span data-stu-id="442f4-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="442f4-107">En este tema se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="442f4-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="442f4-108">Si está buscando información sobre cómo crear y administrar buzones compartidos, consulte [Crear un buzón compartido](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="442f4-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="442f4-109">¿Desea configurar los permisos de buzón?</span><span class="sxs-lookup"><span data-stu-id="442f4-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="442f4-p103">Los permisos de buzón le permiten conceder acceso de lectura y escritura en un buzón a otro usuario. Los artículos siguientes pueden proporcionarle la ayuda que necesita para configurar y usar esta característica:</span><span class="sxs-lookup"><span data-stu-id="442f4-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="442f4-112">**Configurar los permisos:**</span><span class="sxs-lookup"><span data-stu-id="442f4-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="442f4-p104">El primer paso para configurar permisos es decidir qué acciones quiere permitir que el otro usuario realice en el buzón específico. Puede permitir que un usuario lea mensajes de correo electrónico desde el buzón, que envíe mensajes de correo electrónico en nombre de otro usuario y que envíe mensajes de correo electrónico como si se enviasen desde ese buzón. Consulte los siguientes artículos sobre cómo configurar cada tipo de permisos:</span><span class="sxs-lookup"><span data-stu-id="442f4-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="442f4-116">Leer correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="442f4-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="442f4-117">Enviar correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="442f4-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="442f4-118">Enviar correo electrónico en nombre de otro usuario</span><span class="sxs-lookup"><span data-stu-id="442f4-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="442f4-119">**Cambiar la propagación:**</span><span class="sxs-lookup"><span data-stu-id="442f4-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="442f4-120">Después de configurar los permisos, los cambios pueden tardar hasta 60 minutos en propagarse por el sistema y hacerse efectivos.</span><span class="sxs-lookup"><span data-stu-id="442f4-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="442f4-121">**Cómo usarlo una vez que los permisos están configurados:**</span><span class="sxs-lookup"><span data-stu-id="442f4-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="442f4-p105">Hay diferentes maneras de acceder a un buzón una vez que se le ha concedido acceso. Para obtener ayuda sobre esto, consulte este artículo: [Obtener acceso al buzón de otra persona](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="442f4-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="442f4-124">Los permisos se pueden configurar solo en el espacio empresarial de la organización actual.</span><span class="sxs-lookup"><span data-stu-id="442f4-124">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="442f4-125">No es posible configurar permisos de buzón con usuarios que no sean parte de la cuenta empresarial.</span><span class="sxs-lookup"><span data-stu-id="442f4-125">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="442f4-126">Enviar correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="442f4-126">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="442f4-127">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="442f4-128">Seleccione el nombre del usuario (al que piensa conceder permiso de envío) para abrir el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="442f4-128">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="442f4-129">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-129">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="442f4-130">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-130">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="442f4-131">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="442f4-131">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="442f4-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-132">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="442f4-133">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="442f4-134">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-134">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="442f4-135">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-135">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="442f4-136">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="442f4-136">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="442f4-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-137">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="442f4-138">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="442f4-139">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-139">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="442f4-140">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-140">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="442f4-141">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="442f4-141">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="442f4-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-142">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="442f4-143">Leer correo electrónico en el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="442f4-143">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="442f4-144">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="442f4-145">Seleccione el nombre del usuario (cuyo buzón quiere permitir que se lea) para abrir el panel propiedades.</span><span class="sxs-lookup"><span data-stu-id="442f4-145">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="442f4-146">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-146">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="442f4-147">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-147">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="442f4-148">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="442f4-148">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="442f4-149">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-149">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="442f4-150">Los permisos de **Lectura** y **Administración** se llaman de **Acceso completo** cuando se otorgan en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="442f4-150">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="442f4-151">El permiso de Acceso completo no concede permisos de **Enviar como** ni **Enviar en nombre de**.</span><span class="sxs-lookup"><span data-stu-id="442f4-151">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="442f4-152">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="442f4-153">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-153">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="442f4-154">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-154">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="442f4-155">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="442f4-155">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="442f4-156">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-156">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="442f4-157">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="442f4-158">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-158">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="442f4-159">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-159">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="442f4-160">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="442f4-160">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="442f4-161">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-161">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="442f4-162">Enviar correo electrónico en nombre de otro usuario</span><span class="sxs-lookup"><span data-stu-id="442f4-162">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="442f4-163">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="442f4-164">Seleccione el nombre del usuario (al que piensa conceder permiso para **Enviar en nombre de**) para abrir el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="442f4-164">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="442f4-165">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-165">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="442f4-166">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-166">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="442f4-167">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="442f4-167">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="442f4-168">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-168">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="442f4-169">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="442f4-170">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-170">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="442f4-171">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-171">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="442f4-172">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="442f4-172">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="442f4-173">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-173">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="442f4-174">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="442f4-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="442f4-175">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="442f4-175">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="442f4-176">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-176">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="442f4-177">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="442f4-177">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="442f4-178">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="442f4-178">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="442f4-179">Enviar y leer desde Outlook y Outlook en la Web empresarial</span><span class="sxs-lookup"><span data-stu-id="442f4-179">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="442f4-p108">¿Quiere aprender cómo enviar correo electrónico desde el buzón de otro usuario? Consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="442f4-p108">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="442f4-182">Administrar elementos de correo y calendario de otra persona</span><span class="sxs-lookup"><span data-stu-id="442f4-182">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="442f4-183">Enviar correo electrónico de otra persona o grupo</span><span class="sxs-lookup"><span data-stu-id="442f4-183">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
