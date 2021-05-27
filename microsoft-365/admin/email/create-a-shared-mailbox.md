---
title: Creación de un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Cree un buzón compartido para permitir que varios usuarios de su empresa puedan compartir la responsabilidad de leer y responder correo electrónico enviado a una dirección.
ms.openlocfilehash: 35f1de41094c6bf3f806b3e8e01c0a67949c491e
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683252"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="0012e-103">Creación de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="0012e-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="0012e-104">Si su organización usa un entorno híbrido de Exchange, debe usar el Centro de administración de Exchange (EAC) local para crear y administrar buzones compartidos.</span><span class="sxs-lookup"><span data-stu-id="0012e-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="0012e-105">Consulte [Crear buzones compartidos en el centro de administración de Exchange](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span><span class="sxs-lookup"><span data-stu-id="0012e-105">See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span></span><br><br>
> <span data-ttu-id="0012e-106">Si no está seguro de si debería crear un buzón compartido o un grupo de Microsoft 365 para Outlook, vea [Comparar grupos](../create-groups/compare-groups.md) para tener más clara su decisión.</span><span class="sxs-lookup"><span data-stu-id="0012e-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="0012e-107">Tenga en cuenta que no es posible migrar un buzón compartido a un grupo de Microsoft 365 en este momento.</span><span class="sxs-lookup"><span data-stu-id="0012e-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="0012e-108">Si esto le interesaría, indíquelo [votando aquí](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="0012e-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="0012e-p103">Es fácil crear buzones compartidos de Office 365 para que un grupo de personas pueda supervisar y enviar correos electrónicos desde una dirección de correo electrónico común, como, por ejemplo, info@contoso.com. Cuando un miembro del grupo responde a un mensaje enviado al buzón compartido, parece que el correo electrónico procede del buzón compartido y no de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="0012e-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="0012e-p104">Los buzones compartidos incluyen un calendario compartido. A una gran cantidad de pequeñas empresas le gusta usar el calendario compartido como un lugar en el que todos los usuarios pueden insertar sus citas. Por ejemplo, si tiene 3 personas que realizan visitas a clientes, todas ellas pueden usar el calendario compartido para insertar las citas. Esta es una forma sencilla de mantener a todos informados.</span><span class="sxs-lookup"><span data-stu-id="0012e-p104">Shared mailboxes include a shared calendar. A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="0012e-115">Antes de crear un buzón compartido, asegúrese de leer [acerca de los buzones compartidos](about-shared-mailboxes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0012e-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="0012e-116">Crear un buzón compartido y agregar miembros</span><span class="sxs-lookup"><span data-stu-id="0012e-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="0012e-117">Inicie sesión con una cuenta de administrador global o una cuenta de administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0012e-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="0012e-118">Si recibe el mensaje "**No tiene permiso para acceder a esta página o realizar esta acción**" quiere decir que no es administrador.</span><span class="sxs-lookup"><span data-stu-id="0012e-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="0012e-119">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="0012e-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="0012e-120">En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=848041), vaya a la página **Grupos** \> **Buzones compartidos**.</span><span class="sxs-lookup"><span data-stu-id="0012e-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="0012e-121">En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=850627), vaya a la página **Grupos** \> **Buzones compartidos**.</span><span class="sxs-lookup"><span data-stu-id="0012e-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="0012e-122">En la página **buzones compartidos**, seleccione **+ agregar un buzón**.</span><span class="sxs-lookup"><span data-stu-id="0012e-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="0012e-123">Escriba un nombre para el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="0012e-124">A continuación, el asistente elige una dirección de correo electrónico, pero puede editarla.</span><span class="sxs-lookup"><span data-stu-id="0012e-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Asigne un nombre a su buzón  compartido.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="0012e-126">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0012e-126">Select **Add**.</span></span> <span data-ttu-id="0012e-127">Puede tardar unos minutos antes de poder agregar miembros.</span><span class="sxs-lookup"><span data-stu-id="0012e-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="0012e-128">En **Pasos siguientes**, elija **Agregar miembros a este buzón**.</span><span class="sxs-lookup"><span data-stu-id="0012e-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="0012e-129">Los miembros son las personas que podrán ver el correo entrante para este buzón de correo compartido y las respuestas salientes.</span><span class="sxs-lookup"><span data-stu-id="0012e-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Seleccione Agregar miembros.](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="0012e-131">Elija el botón **+ Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="0012e-131">Select the **+Add members** button.</span></span> <span data-ttu-id="0012e-132">Coloque una marca de verificación junto a las personas que desea que usen este buzón de correo compartido y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0012e-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Asignar miembros al buzón compartido](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="0012e-134">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0012e-134">Select **Close**.</span></span>

<span data-ttu-id="0012e-135">Tiene un buzón compartido que incluye un calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="0012e-136">Ahora, vaya al siguiente paso: bloquear el inicio para la cuenta de buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="0012e-137">¿Qué permisos debe usar?</span><span class="sxs-lookup"><span data-stu-id="0012e-137">Which permissions should you use?</span></span>

<span data-ttu-id="0012e-138">Puede usar los siguientes permisos con un buzón compartido:</span><span class="sxs-lookup"><span data-stu-id="0012e-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="0012e-139">**Acceso completo**: el permiso Acceso completo permite al usuario iniciar sesión en el buzón compartido y actuar como el propietario de ese buzón.</span><span class="sxs-lookup"><span data-stu-id="0012e-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="0012e-140">Después de acceder al buzón compartido, un usuario puede crear elementos de calendario, leer, ver, eliminar y cambiar los mensajes de correo electrónico, y crear tareas y contactos de calendario.</span><span class="sxs-lookup"><span data-stu-id="0012e-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="0012e-141">Sin embargo, un usuario con un permiso de Acceso total no puede enviar mensajes de correo electrónico desde el buzón compartido a menos que tenga un permiso para Enviar como o En nombre de.</span><span class="sxs-lookup"><span data-stu-id="0012e-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="0012e-142">**Enviar como**: el permiso para Enviar como le permite al usuario suplantar el buzón compartido al enviar un mensaje de correo.</span><span class="sxs-lookup"><span data-stu-id="0012e-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="0012e-143">Por ejemplo, si Carlos inicia sesión en el buzón compartido del departamento de marketing y envía un correo electrónico, el remitente de dicho correo será el departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="0012e-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="0012e-144">**Enviar en nombre de**: el permiso Enviar en nombre de le permite al usuario enviar mensajes en nombre del buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="0012e-145">Por ejemplo, si Sergio inicia sesión en el buzón compartido del Edificio de recepción 32 y envía un mensaje de correo electrónico, los destinatarios verán el mensaje como enviado por “Sergio en nombre del Edificio de recepción 32”.</span><span class="sxs-lookup"><span data-stu-id="0012e-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="0012e-146">No puede usar el CEF para conceder permisos de Enviar en nombre de. En este caso, debe utilizar el cmdlet **Set-Mailbox** con el parámetro _GrantSendonBehalf_.</span><span class="sxs-lookup"><span data-stu-id="0012e-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="0012e-147">Usar el EAC para editar la delegación de buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="0012e-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="0012e-148">En el EAC, vaya a **Destinatarios** \> **Compartidos**.</span><span class="sxs-lookup"><span data-stu-id="0012e-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="0012e-149">Seleccione el buzón de correo compartido y, después, **Editar** ![Icono de edición](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="0012e-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="0012e-150">Seleccione **Delegación de buzón**.</span><span class="sxs-lookup"><span data-stu-id="0012e-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="0012e-151">Para conceder o quitar los permisos de Acceso total y Enviar como, seleccione **Agregar** ![Icono Agregar](../../media/ITPro-EAC-AddIcon.png) o **Quitar** ![Icono de Quitar](../../media/ITPro-EAC-RemoveIcon.gif) y seleccione los usuarios a los que quiera conceder los permisos.</span><span class="sxs-lookup"><span data-stu-id="0012e-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0012e-p115">El permiso de Acceso completo permite a los usuarios abrir el buzón, así como crear y modificar sus elementos. El permiso Enviar como permite a cualquiera que no sea el propietario del buzón enviar correo electrónico desde este buzón compartido. Ambos permisos son necesarios para que el buzón compartido funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="0012e-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="0012e-155">Seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="0012e-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="0012e-156">Bloquear el inicio de sesión de la cuenta de buzón compartido</span><span class="sxs-lookup"><span data-stu-id="0012e-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="0012e-157">Cada buzón compartido tiene una cuenta de usuario correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0012e-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="0012e-158">¿Ha notado que no se le pidió que proporcionase una contraseña cuando creó el buzón de correo compartido?</span><span class="sxs-lookup"><span data-stu-id="0012e-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="0012e-159">La cuenta tiene una contraseña, pero se ha generado por el sistema (desconocida).</span><span class="sxs-lookup"><span data-stu-id="0012e-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="0012e-160">No debería usar la cuenta para iniciar sesión en el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="0012e-161">Pero, ¿qué sucede si un administrador simplemente restablece la contraseña de la cuenta de usuario del buzón compartido?</span><span class="sxs-lookup"><span data-stu-id="0012e-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="0012e-162">¿O si un atacante obtiene acceso a las credenciales de cuenta de buzón compartido?</span><span class="sxs-lookup"><span data-stu-id="0012e-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="0012e-163">Esto permitiría a la cuenta de usuario iniciar sesión en el buzón compartido y enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0012e-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="0012e-164">Para evitar esto, tiene que bloquear el inicio de sesión de la cuenta que está asociada con el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0012e-165">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="0012e-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0012e-166">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="0012e-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0012e-167">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="0012e-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
::: moniker-end

1. <span data-ttu-id="0012e-168">En la lista de cuentas de usuario, busque la cuenta para el buzón de correo compartido (por ejemplo, cambie el filtro a **usuarios sin licencia**).</span><span class="sxs-lookup"><span data-stu-id="0012e-168">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

1. <span data-ttu-id="0012e-169">Seleccione el usuario para abrir su panel de propiedades y seleccione el icono **bloquear este usuario** ![captura de pantalla del icono bloquear este usuario](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="0012e-169">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="0012e-170">**Nota**: Si la cuenta ya está bloqueada, se mostrará **inicio de sesión bloqueado** en la parte superior y el icono indicará **desbloquear este usuario**.</span><span class="sxs-lookup"><span data-stu-id="0012e-170">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

1. <span data-ttu-id="0012e-171">En el panel **¿bloquear este usuario?**, seleccione **impedir que los usuarios inicien sesión** y seleccione **guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="0012e-171">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

<span data-ttu-id="0012e-172">Para obtener instrucciones sobre cómo bloquear el inicio de sesión para cuentas con el PowerShell de Azure AD (incluyendo varias cuentas al mismo tiempo), consulte [Bloquear cuentas de usuario con PowerShell de Office 365](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0012e-172">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="0012e-173">Agregar el buzón compartido en Outlook</span><span class="sxs-lookup"><span data-stu-id="0012e-173">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="0012e-174">Si la asignación automática está habilitada en su empresa, como en la mayoría de los casos, el buzón compartido aparecerá automáticamente en la aplicación de Outlook de los usuarios tras cerrar y volver a abrir la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0012e-174">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="0012e-175">La asignación automática se establece en el buzón del usuario, no en el buzón compartido.  </span><span class="sxs-lookup"><span data-stu-id="0012e-175">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="0012e-176">Significa que si intenta usar un grupo de seguridad para administrar quién tiene acceso al buzón compartido, la asignación automática no funcionará.</span><span class="sxs-lookup"><span data-stu-id="0012e-176">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="0012e-177">Por lo tanto, si desea utilizar la asignación automática, debe asignar permisos de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="0012e-177">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="0012e-178">La asignación automática está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0012e-178">Automapping is on by default.</span></span> <span data-ttu-id="0012e-179">Para obtener información sobre cómo desactivarlo, consulte [eliminar asignación automática para un buzón compartido](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="0012e-179">To learn how to turn it off, see [Remove automapping for a shared mailbox](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="0012e-180">Para obtener más información sobre los buzones compartidos en Outlook, consulte:</span><span class="sxs-lookup"><span data-stu-id="0012e-180">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="0012e-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Abrir y usar un buzón compartido en Outlook</a></span><span class="sxs-lookup"><span data-stu-id="0012e-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="0012e-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Agregar un buzón compartido a Outlook en la Web</a></span><span class="sxs-lookup"><span data-stu-id="0012e-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="0012e-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregue un buzón compartido en Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="0012e-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="0012e-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Abrir una carpeta o un buzón compartido en Outlook para Mac</a></span><span class="sxs-lookup"><span data-stu-id="0012e-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="0012e-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Agregar reglas a un buzón compartido</a></span><span class="sxs-lookup"><span data-stu-id="0012e-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="0012e-186">Usar un buzón compartido en un dispositivo móvil (teléfono o tableta)</span><span class="sxs-lookup"><span data-stu-id="0012e-186">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="0012e-187">Puede obtener acceso a un buzón compartido en un dispositivo móvil de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="0012e-187">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="0012e-188">Agregue el buzón de correo compartido en la <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">aplicación de Outlook para iOS</a> o en la <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">aplicación móvil de Outlook para Android</a>.</span><span class="sxs-lookup"><span data-stu-id="0012e-188">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="0012e-189">Para obtener instrucciones, vea <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregar un buzón compartido en Outlook para dispositivos móviles</a>.</span><span class="sxs-lookup"><span data-stu-id="0012e-189">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="0012e-190">Abra su navegador, inicie sesión y vaya a Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="0012e-190">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="0012e-191">Desde Outlook en la Web, podrá acceder al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-191">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="0012e-192">Para obtener instrucciones, vea <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Agregar un buzón compartido en Outlook en la Web</a>.</span><span class="sxs-lookup"><span data-stu-id="0012e-192">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0012e-193">El buzón compartido solo se puede agregar a la aplicación de Outlook para iOS o la aplicación móvil de Outlook para Android</span><span class="sxs-lookup"><span data-stu-id="0012e-193">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="0012e-194">Usar el calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-194">Use the shared calendar</span></span>

<span data-ttu-id="0012e-195">Cuando creó el buzón compartido, creó automáticamente un calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-195">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="0012e-196">Preferimos usar el calendario de buzón de correo compartido, en lugar de un calendario de SharePoint, para realizar el seguimiento de las citas y de la ubicación de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0012e-196">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="0012e-197">Hay un calendario compartido integrado en Outlook y es mucho más fácil de crear y usar que un calendario de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0012e-197">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="0012e-198">En la aplicación de Outlook, vaya a la vista de calendario y seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-198">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="0012e-199">Al introducir citas, todos los usuarios que son miembros del buzón de correo compartido podrán verlas.</span><span class="sxs-lookup"><span data-stu-id="0012e-199">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="0012e-200">Todos los miembros del buzón compartido pueden crear, ver y administrar citas en el calendario, igual que lo hacen con sus citas personales.</span><span class="sxs-lookup"><span data-stu-id="0012e-200">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="0012e-201">Todos los usuarios que sean miembros del buzón compartido pueden ver sus cambios en el calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="0012e-201">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-content"></a><span data-ttu-id="0012e-202">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="0012e-202">Related content</span></span>

<span data-ttu-id="0012e-203">[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0012e-203">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="0012e-204">[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0012e-204">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="0012e-205">[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0012e-205">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="0012e-206">[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0012e-206">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="0012e-207">[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0012e-207">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>