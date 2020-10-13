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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Cree un buzón compartido para permitir que varios usuarios de su empresa puedan compartir la responsabilidad de leer y responder correo electrónico enviado a una dirección.
ms.openlocfilehash: 2cef7c742407b291d392a73e72316e7feeba4197
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445644"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="bae84-103">Creación de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="bae84-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="bae84-104">Si su organización usa un entorno híbrido de Exchange, debe usar el Centro de administración de Exchange (EAC) local para crear y administrar buzones compartidos.</span><span class="sxs-lookup"><span data-stu-id="bae84-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="bae84-105">Consulte [Crear buzones compartidos en el centro de administración de Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019&preserve-view=true.)</span><span class="sxs-lookup"><span data-stu-id="bae84-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019&preserve-view=true.)</span></span><br><br>
> <span data-ttu-id="bae84-106">Si no está seguro de si debería crear un buzón compartido o un grupo de Microsoft 365 para Outlook, vea [Comparar grupos](../create-groups/compare-groups.md) para tener más clara su decisión.</span><span class="sxs-lookup"><span data-stu-id="bae84-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="bae84-107">Tenga en cuenta que no es posible migrar un buzón compartido a un grupo de Microsoft 365 en este momento.</span><span class="sxs-lookup"><span data-stu-id="bae84-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="bae84-108">Si esto le interesaría, indíquelo [votando aquí](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="bae84-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="bae84-p103">Es fácil crear buzones compartidos de Office 365 para que un grupo de personas pueda supervisar y enviar correos electrónicos desde una dirección de correo electrónico común, como, por ejemplo, info@contoso.com. Cuando un miembro del grupo responde a un mensaje enviado al buzón compartido, parece que el correo electrónico procede del buzón compartido y no de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="bae84-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="bae84-111">Los buzones compartidos incluyen un calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="bae84-112">A una gran cantidad de pequeñas empresas les gusta usar el calendario compartido como un lugar en el que todos los usuarios introduzcan sus citas.</span><span class="sxs-lookup"><span data-stu-id="bae84-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="bae84-113">Por ejemplo, si tiene 3 personas que realizan visitas de clientes, todos pueden usar el calendario compartido para introducir las citas.</span><span class="sxs-lookup"><span data-stu-id="bae84-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="bae84-114">Esta es una forma sencilla de mantener a todos informados.</span><span class="sxs-lookup"><span data-stu-id="bae84-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="bae84-115">Antes de crear un buzón compartido, asegúrese de leer [acerca de los buzones compartidos](about-shared-mailboxes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bae84-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="bae84-116">Crear un buzón compartido y agregar miembros</span><span class="sxs-lookup"><span data-stu-id="bae84-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="bae84-117">Inicie sesión con una cuenta de administrador global o una cuenta de administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="bae84-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="bae84-118">Si recibe el mensaje "**No tiene permiso para acceder a esta página o realizar esta acción**" quiere decir que no es administrador.</span><span class="sxs-lookup"><span data-stu-id="bae84-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="bae84-119">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="bae84-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="bae84-120">En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=848041), vaya a la página **Grupos** \> **Buzones compartidos**.</span><span class="sxs-lookup"><span data-stu-id="bae84-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="bae84-121">En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=850627), vaya a la página **Grupos** \> **Buzones compartidos**.</span><span class="sxs-lookup"><span data-stu-id="bae84-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="bae84-122">En la página **buzones compartidos**, seleccione **+ agregar un buzón**.</span><span class="sxs-lookup"><span data-stu-id="bae84-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="bae84-123">Escriba un nombre para el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="bae84-124">A continuación, el asistente elige una dirección de correo electrónico, pero puede editarla.</span><span class="sxs-lookup"><span data-stu-id="bae84-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Asigne un nombre a su buzón  compartido.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="bae84-126">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bae84-126">Select **Add**.</span></span> <span data-ttu-id="bae84-127">Puede tardar unos minutos antes de poder agregar miembros.</span><span class="sxs-lookup"><span data-stu-id="bae84-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="bae84-128">En **Pasos siguientes**, elija **Agregar miembros a este buzón**.</span><span class="sxs-lookup"><span data-stu-id="bae84-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="bae84-129">Los miembros son las personas que podrán ver el correo entrante para este buzón de correo compartido y las respuestas salientes.</span><span class="sxs-lookup"><span data-stu-id="bae84-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Seleccione Agregar miembros.](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="bae84-131">Elija el botón **+ Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="bae84-131">Select the **+Add members** button.</span></span> <span data-ttu-id="bae84-132">Coloque una marca de verificación junto a las personas que desea que usen este buzón de correo compartido y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bae84-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Asignar miembros al buzón compartido](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="bae84-134">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bae84-134">Select **Close**.</span></span>

<span data-ttu-id="bae84-135">Tiene un buzón compartido que incluye un calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="bae84-136">Ahora, vaya al siguiente paso: bloquear el inicio para la cuenta de buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="bae84-137">Bloquear el inicio de sesión de la cuenta de buzón compartido</span><span class="sxs-lookup"><span data-stu-id="bae84-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="bae84-138">Cada buzón compartido tiene una cuenta de usuario correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bae84-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="bae84-139">¿Ha notado que no se le pidió que proporcionase una contraseña cuando creó el buzón de correo compartido?</span><span class="sxs-lookup"><span data-stu-id="bae84-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="bae84-140">La cuenta tiene una contraseña, pero se ha generado por el sistema (desconocida).</span><span class="sxs-lookup"><span data-stu-id="bae84-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="bae84-141">No debería usar la cuenta para iniciar sesión en el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="bae84-142">Pero, ¿qué sucede si un administrador simplemente restablece la contraseña de la cuenta de usuario del buzón compartido?</span><span class="sxs-lookup"><span data-stu-id="bae84-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="bae84-143">¿O si un atacante obtiene acceso a las credenciales de cuenta de buzón compartido?</span><span class="sxs-lookup"><span data-stu-id="bae84-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="bae84-144">Esto permitiría a la cuenta de usuario iniciar sesión en el buzón compartido y enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bae84-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="bae84-145">Para evitar esto, tiene que bloquear el inicio de sesión de la cuenta que está asociada con el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bae84-146">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="bae84-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="bae84-147">En la lista de cuentas de usuario, busque la cuenta para el buzón de correo compartido (por ejemplo, cambie el filtro a **usuarios sin licencia**).</span><span class="sxs-lookup"><span data-stu-id="bae84-147">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="bae84-148">Seleccione el usuario para abrir su panel de propiedades y seleccione el icono **bloquear este usuario** ![captura de pantalla del icono bloquear este usuario](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="bae84-148">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="bae84-149">**Nota**: Si la cuenta ya está bloqueada, se mostrará **inicio de sesión bloqueado** en la parte superior y el icono indicará **desbloquear este usuario**.</span><span class="sxs-lookup"><span data-stu-id="bae84-149">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="bae84-150">En el panel **¿bloquear este usuario?**, seleccione **impedir que los usuarios inicien sesión** y seleccione **guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="bae84-150">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bae84-151">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="bae84-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="bae84-152">En la lista de cuentas de usuario, busque la cuenta para el buzón de correo compartido (por ejemplo, cambie la vista a **usuarios sin licencia**) y seleccione la cuenta.</span><span class="sxs-lookup"><span data-stu-id="bae84-152">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="bae84-153">En el control flotante de propiedades, seleccione **bloquear inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="bae84-153">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="bae84-154">**Nota:** si la cuenta ya se ha bloqueado, el botón diría **desbloquear inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="bae84-154">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="bae84-155">En el control flotante **editar el estado de inicio de sesión**, compruebe que está activada la opción Bloquear el usuario para iniciar sesión, seleccione **guardar** y, a continuación, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bae84-155">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bae84-156">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="bae84-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="bae84-157">En la lista de cuentas de usuario, busque la cuenta para el buzón de correo compartido (por ejemplo, cambie la vista a **usuarios sin licencia**) y seleccione la cuenta.</span><span class="sxs-lookup"><span data-stu-id="bae84-157">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="bae84-158">En el control flotante de propiedades, seleccione **bloquear inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="bae84-158">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="bae84-159">**Nota:** si la cuenta ya se ha bloqueado, el botón diría **desbloquear inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="bae84-159">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="bae84-160">En el control flotante **editar el estado de inicio de sesión**, compruebe que está activada la opción Bloquear el usuario para iniciar sesión, seleccione **guardar** y, a continuación, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bae84-160">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="bae84-161">Para obtener instrucciones sobre cómo bloquear el inicio de sesión para cuentas con el PowerShell de Azure AD (incluyendo varias cuentas al mismo tiempo), consulte [Bloquear cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/block-user-accounts-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="bae84-161">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/block-user-accounts-with-microsoft-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="bae84-162">Agregar el buzón compartido en Outlook</span><span class="sxs-lookup"><span data-stu-id="bae84-162">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="bae84-163">Si la asignación automática está habilitada en su empresa, como en la mayoría de los casos, el buzón compartido aparecerá automáticamente en la aplicación de Outlook de los usuarios tras cerrar y volver a abrir la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bae84-163">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="bae84-164">La asignación automática se establece en el buzón del usuario, no en el buzón compartido.  </span><span class="sxs-lookup"><span data-stu-id="bae84-164">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="bae84-165">Significa que si intenta usar un grupo de seguridad para administrar quién tiene acceso al buzón compartido, la asignación automática no funcionará.</span><span class="sxs-lookup"><span data-stu-id="bae84-165">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="bae84-166">Por lo tanto, si desea utilizar la asignación automática, debe asignar permisos de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="bae84-166">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="bae84-167">La asignación automática está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bae84-167">Automapping is on by default.</span></span> <span data-ttu-id="bae84-168">Para obtener información sobre cómo desactivarlo, consulte [eliminar asignación automática para un buzón compartido](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="bae84-168">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="bae84-169">Para obtener más información sobre los buzones compartidos en Outlook, consulte:</span><span class="sxs-lookup"><span data-stu-id="bae84-169">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="bae84-170"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Abrir y usar un buzón compartido en Outlook</a></span><span class="sxs-lookup"><span data-stu-id="bae84-170"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="bae84-171"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Agregar un buzón compartido a Outlook en la Web</a></span><span class="sxs-lookup"><span data-stu-id="bae84-171"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="bae84-172"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregue un buzón compartido en Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="bae84-172"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="bae84-173"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Abrir una carpeta o un buzón compartido en Outlook para Mac</a></span><span class="sxs-lookup"><span data-stu-id="bae84-173"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="bae84-174"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Agregar reglas a un buzón compartido</a></span><span class="sxs-lookup"><span data-stu-id="bae84-174"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="bae84-175">Usar un buzón compartido en un dispositivo móvil (teléfono o tableta)</span><span class="sxs-lookup"><span data-stu-id="bae84-175">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="bae84-176">Puede obtener acceso a un buzón compartido en un dispositivo móvil de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="bae84-176">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="bae84-177">Agregue el buzón de correo compartido en la <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">aplicación de Outlook para iOS</a> o en la <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">aplicación móvil de Outlook para Android</a>.</span><span class="sxs-lookup"><span data-stu-id="bae84-177">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="bae84-178">Para obtener instrucciones, vea <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregar un buzón compartido en Outlook para dispositivos móviles</a>.</span><span class="sxs-lookup"><span data-stu-id="bae84-178">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="bae84-179">Abra su navegador, inicie sesión y vaya a Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="bae84-179">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="bae84-180">Desde Outlook en la Web, podrá acceder al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-180">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="bae84-181">Para obtener instrucciones, vea <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Agregar un buzón compartido en Outlook en la Web</a>.</span><span class="sxs-lookup"><span data-stu-id="bae84-181">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bae84-182">El buzón compartido solo se puede agregar a la aplicación de Outlook para iOS o la aplicación móvil de Outlook para Android</span><span class="sxs-lookup"><span data-stu-id="bae84-182">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="bae84-183">Usar el calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-183">Use the shared calendar</span></span>

<span data-ttu-id="bae84-184">Cuando creó el buzón compartido, creó automáticamente un calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-184">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="bae84-185">Preferimos usar el calendario de buzón de correo compartido, en lugar de un calendario de SharePoint, para realizar el seguimiento de las citas y de la ubicación de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bae84-185">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="bae84-186">Hay un calendario compartido integrado en Outlook y es mucho más fácil de crear y usar que un calendario de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bae84-186">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="bae84-187">En la aplicación de Outlook, vaya a la vista de calendario y seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-187">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="bae84-188">Al introducir citas, todos los usuarios que son miembros del buzón de correo compartido podrán verlas.</span><span class="sxs-lookup"><span data-stu-id="bae84-188">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="bae84-189">Todos los miembros del buzón compartido pueden crear, ver y administrar citas en el calendario, igual que lo hacen con sus citas personales.</span><span class="sxs-lookup"><span data-stu-id="bae84-189">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="bae84-190">Todos los usuarios que sean miembros del buzón compartido pueden ver sus cambios en el calendario compartido.</span><span class="sxs-lookup"><span data-stu-id="bae84-190">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bae84-191">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="bae84-191">Related articles</span></span>

[<span data-ttu-id="bae84-192">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="bae84-192">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="bae84-193">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="bae84-193">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="bae84-194">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="bae84-194">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="bae84-195">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="bae84-195">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="bae84-196">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="bae84-196">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)





