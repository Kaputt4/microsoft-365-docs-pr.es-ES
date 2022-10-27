---
title: Creación de un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Cree un buzón compartido para permitir que varios usuarios de su empresa puedan compartir la responsabilidad de leer y responder correo electrónico enviado a una dirección.
ms.openlocfilehash: b44c1bfdf7db3f58f41c574368b1b76318da78db
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68718862"
---
# <a name="create-a-shared-mailbox"></a>Creación de un buzón compartido 

> [!NOTE]
> If your organization uses a hybrid Exchange environment, you should use the on-premises <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a> to create and manage shared mailboxes. See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)
>
> Si no está seguro de si debería crear un buzón compartido o un grupo de Microsoft 365 para Outlook, vea [Comparar grupos](../create-groups/compare-groups.md) para tener más clara su decisión. Tenga en cuenta que no es posible migrar un buzón compartido a un grupo de Microsoft 365 en este momento. Si esto le interesaría, indíquelo [votando aquí](https://go.microsoft.com/fwlink/?linkid=871518).

It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.

Shared mailboxes include a shared calendar. A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.

Antes de crear un buzón compartido, asegúrese de leer [acerca de los buzones compartidos](about-shared-mailboxes.md) para obtener más información.

> [!TIP]
> Si necesita ayuda con los pasos descritos en este tema, considere la posibilidad de [trabajar con un especialista de Microsoft Small Business](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="create-a-shared-mailbox-and-add-members"></a>Crear un buzón compartido y agregar miembros
  
1. Sign in with a global admin account or Exchange admin account. If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin. 

::: moniker range="o365-worldwide"

2. En el Centro de administración, vaya a la página **Teams y Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

2. En el [Centro de administración](https://go.microsoft.com/fwlink/p/?linkid=850627), vaya a la página **Teams y Grupos** \> **Buzones compartidos**.

::: moniker-end
    
3. En la página **Buzones compartidos**, seleccione **+ Agregar un buzón compartido**. Escriba un nombre para el buzón compartido. Se elige una dirección de correo electrónico pero puede editarla si fuera necesario.
    
    ![Asigne un nombre a su buzón compartido.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Select **Save changes**. It may take a few minutes before you can add members.

5. Under **Next steps**, select **Add members to this mailbox**. Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.

   ![Seleccione Agregar miembros.](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Select the **+Add members** button. Put a check mark next to the people who you want to use this shared mailbox, and then select **Save**.

   ![Asignar miembros al buzón compartido.](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Seleccione **Cerrar**.

Tiene un buzón compartido que incluye un calendario compartido. Vaya al siguiente paso: [bloquear el inicio de sesión para la cuenta de buzón compartido](#block-sign-in-for-the-shared-mailbox-account).

## <a name="which-permissions-should-you-use"></a>¿Qué permisos debe usar?

Puede usar los siguientes permisos con un buzón compartido:

- **Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox. After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts. However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.

- **Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail. For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.

- **Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox. For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32". You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.

> [!NOTE]
> Los permisos **Enviar como** y **Enviar en nombre de** no funcionan en el cliente de escritorio de Outlook con el parámetro *HiddenFromAddressListsEnabled* en el buzón establecido en **True**, ya que requieren que el buzón esté visible en Outlook a través de la lista global de direcciones.

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a>Usar el EAC para editar la delegación de buzones compartidos

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>, vaya a **Destinatarios** \> **Buzones**. Seleccione el buzón de correo compartido y, después, **Editar** ![Icono de edición](../../media/ITPro-EAC-EditIcon.png).

2. En **Permisos de buzón** de correo, seleccione **Administrar delegación de buzones**.

3. To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon.](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.

   > [!NOTE]
   > The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.

4. Seleccione **Guardar** para guardar los cambios.


## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Bloquear el inicio de sesión de la cuenta de buzón compartido

Cada buzón compartido tiene una cuenta de usuario correspondiente. ¿Ha notado que no se le pidió que proporcionase una contraseña cuando creó el buzón de correo compartido? La cuenta tiene una contraseña, pero se ha generado por el sistema (desconocida). No debería usar la cuenta para iniciar sesión en el buzón compartido.

Pero, ¿qué sucede si un administrador simplemente restablece la contraseña de la cuenta de usuario del buzón compartido? ¿O si un atacante obtiene acceso a las credenciales de cuenta de buzón compartido? Esto permitiría a la cuenta de usuario iniciar sesión en el buzón compartido y enviar correo electrónico. Para evitar esto, tiene que bloquear el inicio de sesión de la cuenta que está asociada con el buzón compartido.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.
::: moniker-end

2. En la lista de cuentas de usuario, busque la cuenta para el buzón de correo compartido (por ejemplo, cambie el filtro a **usuarios sin licencia**).

3. Seleccione el usuario para abrir su panel de propiedades y seleccione el icono **bloquear este usuario** ![captura de pantalla del icono bloquear este usuario](../../media/block-user-icon.png).

   > [!NOTE]
   > Si la cuenta ya está bloqueada, aparecerá la leyenda **Inicio de sesión bloqueado** en la parte superior y el icono indicará **Desbloquear a este usuario**.

4. En el panel **¿bloquear este usuario?**, seleccione **impedir que los usuarios inicien sesión** y seleccione **guardar cambios**.

Para obtener instrucciones sobre cómo bloquear el inicio de sesión para cuentas con el PowerShell de Azure AD (incluyendo varias cuentas al mismo tiempo), consulte [Bloquear cuentas de usuario con PowerShell de Office 365](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).

## <a name="add-the-shared-mailbox-to-outlook"></a>Agregar el buzón compartido en Outlook

Si la asignación automática está habilitada en su empresa, como en la mayoría de los casos, el buzón compartido aparecerá automáticamente en la aplicación de Outlook de los usuarios tras cerrar y volver a abrir la aplicación. 

La asignación automática se establece en el buzón del usuario, no en el buzón compartido.   Significa que si intenta usar un grupo de seguridad para administrar quién tiene acceso al buzón compartido, la asignación automática no funcionará. Por lo tanto, si desea utilizar la asignación automática, debe asignar permisos de forma explícita. La asignación automática está activada de forma predeterminada. Para obtener información sobre cómo desactivarlo, consulte [eliminar asignación automática para un buzón compartido](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).

Para obtener más información sobre los buzones compartidos en Outlook, consulte:

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Abrir y usar un buzón compartido en Outlook</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Agregar un buzón compartido a Outlook en la Web</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregue un buzón compartido en Outlook Mobile</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Abrir una carpeta o un buzón compartido en Outlook para Mac</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Agregar reglas a un buzón compartido</a>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Usar un buzón compartido en un dispositivo móvil (teléfono o tableta)

Puede obtener acceso a un buzón compartido en un dispositivo móvil de dos maneras:
- Agregue el buzón de correo compartido en la <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">aplicación de Outlook para iOS</a> o en la <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">aplicación móvil de Outlook para Android</a>. 
    
    Para obtener instrucciones, vea <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregar un buzón compartido en Outlook para dispositivos móviles</a>.

- Abra su navegador, inicie sesión y vaya a Outlook en la Web. Desde Outlook en la Web, podrá acceder al buzón compartido.

    Para obtener instrucciones, vea <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Agregar un buzón compartido en Outlook en la Web</a>.
    
> [!NOTE]
> El buzón compartido solo se puede agregar a la aplicación de Outlook para iOS o la aplicación móvil de Outlook para Android

## <a name="use-the-shared-calendar"></a>Usar el calendario compartido.

When you created the shared mailbox, you automatically created a shared calendar. We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are. A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.

1. En la aplicación de Outlook, vaya a la vista de calendario y seleccione el buzón compartido.

2. Al introducir citas, todos los usuarios que son miembros del buzón de correo compartido podrán verlas.

3. Todos los miembros del buzón compartido pueden crear, ver y administrar citas en el calendario, igual que lo hacen con sus citas personales. Todos los usuarios que sean miembros del buzón compartido pueden ver sus cambios en el calendario compartido.

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)
