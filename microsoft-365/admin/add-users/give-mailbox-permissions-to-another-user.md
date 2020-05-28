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
ms.openlocfilehash: 51de5f4e2b134a503ec935b1f1d0ec6519d2c229
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387182"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="89d2d-104">Conceder permisos de buzón a otro usuario: Ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="89d2d-104">Give mailbox permissions to another user - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="89d2d-105">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="89d2d-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="89d2d-106">Como administrador, puede que la empresa le requiera que permita que algunos usuarios puedan acceder al buzón de otro usuario.</span><span class="sxs-lookup"><span data-stu-id="89d2d-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="89d2d-107">Por ejemplo, puede que quiera habilitar que un asistente envíe o lea el correo electrónico del buzón de su jefe o bien que uno de los usuarios pueda enviar correo electrónico en nombre de otro.</span><span class="sxs-lookup"><span data-stu-id="89d2d-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="89d2d-108">En este tema se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="89d2d-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="89d2d-109">Si está buscando información sobre cómo crear y administrar buzones compartidos, consulte [Crear un buzón compartido](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="89d2d-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="89d2d-110">¿Desea configurar los permisos de buzón?</span><span class="sxs-lookup"><span data-stu-id="89d2d-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="89d2d-p103">Los permisos de buzón le permiten conceder acceso de lectura y escritura en un buzón a otro usuario. Los artículos siguientes pueden proporcionarle la ayuda que necesita para configurar y usar esta característica:</span><span class="sxs-lookup"><span data-stu-id="89d2d-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="89d2d-113">**Configurar los permisos:**</span><span class="sxs-lookup"><span data-stu-id="89d2d-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="89d2d-p104">El primer paso para configurar permisos es decidir qué acciones quiere permitir que el otro usuario realice en el buzón específico. Puede permitir que un usuario lea mensajes de correo electrónico desde el buzón, que envíe mensajes de correo electrónico en nombre de otro usuario y que envíe mensajes de correo electrónico como si se enviasen desde ese buzón. Consulte los siguientes artículos sobre cómo configurar cada tipo de permisos:</span><span class="sxs-lookup"><span data-stu-id="89d2d-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="89d2d-117">Leer correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="89d2d-117">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="89d2d-118">Enviar correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="89d2d-118">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="89d2d-119">Enviar correo electrónico en nombre de otro usuario</span><span class="sxs-lookup"><span data-stu-id="89d2d-119">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="89d2d-120">**Cambiar la propagación:**</span><span class="sxs-lookup"><span data-stu-id="89d2d-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="89d2d-121">Después de configurar los permisos, los cambios pueden tardar hasta 60 minutos en propagarse por el sistema y hacerse efectivos.</span><span class="sxs-lookup"><span data-stu-id="89d2d-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="89d2d-122">**Cómo usarlo una vez que los permisos están configurados:**</span><span class="sxs-lookup"><span data-stu-id="89d2d-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="89d2d-p105">Hay diferentes maneras de acceder a un buzón una vez que se le ha concedido acceso. Para obtener ayuda sobre esta cuestión, consulte este artículo: [Obtener acceso al buzón de otra persona](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="89d2d-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="89d2d-125">Enviar correo electrónico desde el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="89d2d-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="89d2d-126">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="89d2d-127">Seleccione el nombre del usuario (al que piensa conceder permiso de envío) para abrir el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="89d2d-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="89d2d-128">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="89d2d-129">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="89d2d-130">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="89d2d-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="89d2d-131">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="89d2d-132">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="89d2d-133">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="89d2d-134">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="89d2d-135">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="89d2d-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="89d2d-136">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="89d2d-137">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="89d2d-138">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="89d2d-139">Junto a **Enviar como**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="89d2d-140">Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="89d2d-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="89d2d-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="89d2d-142">Leer correo electrónico en el buzón de otro usuario</span><span class="sxs-lookup"><span data-stu-id="89d2d-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="89d2d-143">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="89d2d-144">Seleccione el nombre del usuario (cuyo buzón quiere permitir que se lea) para abrir el panel propiedades.</span><span class="sxs-lookup"><span data-stu-id="89d2d-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="89d2d-145">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="89d2d-146">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="89d2d-147">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="89d2d-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="89d2d-148">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="89d2d-149">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="89d2d-150">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="89d2d-151">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="89d2d-152">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="89d2d-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="89d2d-153">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="89d2d-154">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="89d2d-155">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="89d2d-156">Junto a **Leer y administrar**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="89d2d-157">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.</span><span class="sxs-lookup"><span data-stu-id="89d2d-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="89d2d-158">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="89d2d-159">Enviar correo electrónico en nombre de otro usuario</span><span class="sxs-lookup"><span data-stu-id="89d2d-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="89d2d-160">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="89d2d-161">Seleccione el nombre del usuario (al que piensa conceder permiso para **Enviar en nombre de**) para abrir el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="89d2d-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="89d2d-162">En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="89d2d-163">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="89d2d-164">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="89d2d-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="89d2d-165">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="89d2d-166">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="89d2d-167">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="89d2d-168">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="89d2d-169">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="89d2d-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="89d2d-170">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="89d2d-171">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="89d2d-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="89d2d-172">Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="89d2d-173">Junto a **Enviar en nombre de**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="89d2d-174">Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.</span><span class="sxs-lookup"><span data-stu-id="89d2d-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="89d2d-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="89d2d-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="89d2d-176">Enviar y leer desde Outlook y Outlook en la Web empresarial</span><span class="sxs-lookup"><span data-stu-id="89d2d-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="89d2d-p106">¿Quiere aprender cómo enviar correo electrónico desde el buzón de otro usuario? Consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="89d2d-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="89d2d-179">Administrar elementos de correo y calendario de otra persona</span><span class="sxs-lookup"><span data-stu-id="89d2d-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="89d2d-180">Enviar correo electrónico de otra persona o grupo</span><span class="sxs-lookup"><span data-stu-id="89d2d-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
