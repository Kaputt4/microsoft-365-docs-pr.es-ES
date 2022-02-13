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
ms.localizationpriority: high
ms.collection:
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
ms.openlocfilehash: f8a7f725e029021626bf408a3797ac6bfbb16215
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765641"
---
# <a name="create-a-shared-mailbox"></a>Creación de un buzón compartido 

> [!NOTE]
> Si su organización usa un entorno Exchange híbrido, debe usar <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">el Centro de administración de Exchange</a> local para crear y administrar buzones compartidos. Consulte [Crear buzones compartidos en el centro de administración de Exchange](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)
>
> Si no está seguro de si debería crear un buzón compartido o un grupo de Microsoft 365 para Outlook, vea [Comparar grupos](../create-groups/compare-groups.md) para tener más clara su decisión. Tenga en cuenta que no es posible migrar un buzón compartido a un grupo de Microsoft 365 en este momento. Si esto le interesaría, indíquelo [votando aquí](https://go.microsoft.com/fwlink/?linkid=871518).

Es fácil crear buzones compartidos de Office 365 para que un grupo de personas pueda supervisar y enviar correos electrónicos desde una dirección de correo electrónico común, como, por ejemplo, info@contoso.com. Cuando un miembro del grupo responde a un mensaje enviado al buzón compartido, parece que el correo electrónico procede del buzón compartido y no de un usuario individual.

Los buzones compartidos incluyen un calendario compartido. A una gran cantidad de pequeñas empresas le gusta usar el calendario compartido como un lugar en el que todos los usuarios pueden insertar sus citas. Por ejemplo, si tiene 3 personas que realizan visitas a clientes, todas ellas pueden usar el calendario compartido para insertar las citas. Esta es una forma sencilla de mantener a todos informados.

Antes de crear un buzón compartido, asegúrese de leer [acerca de los buzones compartidos](about-shared-mailboxes.md) para obtener más información.

> [!TIP]
> Si necesita ayuda con los pasos descritos en este tema, considere la posibilidad de [trabajar con un especialista de Microsoft Small Business](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="create-a-shared-mailbox-and-add-members"></a>Crear un buzón compartido y agregar miembros
  
1. Inicie sesión con una cuenta de administrador global o una cuenta de administrador de Exchange. Si recibe el mensaje "**No tiene permiso para acceder a esta página o realizar esta acción**", no es administrador. 

::: moniker range="o365-worldwide"

2. En el Centro de administración, vaya a la página **Teams y Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

2. En el [Centro de administración](https://go.microsoft.com/fwlink/p/?linkid=850627), vaya a la página **Teams y Grupos** \> **Buzones compartidos**.

::: moniker-end
    
3. En la página **Buzones compartidos**, seleccione **+ Agregar un buzón compartido**. Escriba un nombre para el buzón compartido. Se elige una dirección de correo electrónico pero puede editarla si fuera necesario.
    
    ![Asigne un nombre a su buzón compartido.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Seleccione **Guardar cambios**. Puede tardar unos minutos en agregar miembros.

5. En **Pasos siguientes**, seleccione **Agregar miembros a este buzón**. Los miembros son las personas que podrán ver el correo entrante en este buzón compartido y las respuestas salientes.

   ![Seleccione Agregar miembros.](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Seleccione el botón **+Agregar miembros**. Coloque una marca de verificación junto a las personas que desea usar este buzón compartido y, a continuación, seleccione **Guardar**.

   ![Asignar miembros al buzón compartido.](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Seleccione **Cerrar**.

Tiene un buzón compartido que incluye un calendario compartido. Vaya al siguiente paso: [bloquear el inicio de sesión para la cuenta de buzón compartido](#block-sign-in-for-the-shared-mailbox-account).

## <a name="which-permissions-should-you-use"></a>¿Qué permisos debe usar?

Puede usar los siguientes permisos con un buzón compartido:

- **Acceso completo**: el permiso de Acceso completo permite al usuario iniciar sesión en el buzón compartido y actuar como el propietario de ese buzón. Después de tener acceso al buzón compartido, el usuario puede crear elementos de calendario; leer, ver, eliminar y modificar mensajes de correo electrónico y crear tareas y contactos del calendario. Sin embargo, un usuario con un permiso de Acceso completo no puede enviar mensajes de correo electrónico desde el buzón compartido a menos que tenga un permiso para Enviar como o En nombre de.

- **Enviar como**: el permiso Enviar como permite al usuario suplantar el buzón compartido al enviar correo. Por ejemplo, si Katerina inicia sesión en el buzón compartido del departamento de marketing y envía un correo electrónico, parecerá que el departamento de marketing envió el correo electrónico.

- **Enviar en nombre de**: el permiso Enviar en nombre de le permite al usuario enviar mensajes en nombre del buzón compartido. Por ejemplo, si Sergio inicia sesión en el buzón compartido del Edificio de recepción 32 y envía un mensaje de correo electrónico, los destinatarios verán el mensaje como enviado por “Sergio en nombre del Edificio de recepción 32”. No puede usar el CEF para conceder permisos de Enviar en nombre de. En este caso, debe utilizar el cmdlet **Set-Mailbox** con el parámetro _GrantSendonBehalf_.

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a>Usar el EAC para editar la delegación de buzones compartidos

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>, vaya a **Destinatarios** \> **Compartidos**. Seleccione el buzón de correo compartido y, después, **Editar** ![Icono de edición](../../media/ITPro-EAC-EditIcon.png).

2. Seleccione **Delegación de buzón**.

3. Para conceder o quitar los permisos de Acceso total y Enviar como, seleccione **Agregar** ![Icono Agregar](../../media/ITPro-EAC-AddIcon.png) o **Quitar** ![Icono de Quitar](../../media/ITPro-EAC-RemoveIcon.gif), y luego seleccione los usuarios a los que quiera conceder los permisos.

   > [!NOTE]
   > El permiso de Acceso completo permite a los usuarios abrir el buzón, así como crear y modificar sus elementos. El permiso Enviar como permite a cualquiera que no sea el propietario del buzón enviar correo electrónico desde este buzón compartido. Ambos permisos son necesarios para que el buzón compartido funcione correctamente.

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

Cuando creó el buzón compartido, creó automáticamente un calendario compartido. Preferimos usar el calendario de buzón de correo compartido, en lugar de un calendario de SharePoint, para realizar el seguimiento de las citas y de la ubicación de los usuarios. Hay un calendario compartido integrado en Outlook y es mucho más fácil de crear y usar que un calendario de SharePoint.

1. En la aplicación de Outlook, vaya a la vista de calendario y seleccione el buzón compartido.

2. Al introducir citas, todos los usuarios que son miembros del buzón de correo compartido podrán verlas.

3. Todos los miembros del buzón compartido pueden crear, ver y administrar citas en el calendario, igual que lo hacen con sus citas personales. Todos los usuarios que sean miembros del buzón compartido pueden ver sus cambios en el calendario compartido.

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)
