---
title: Creación de un buzón compartido
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Cree un buzón compartido para permitir que varios usuarios de su empresa puedan compartir la responsabilidad de leer y responder correo electrónico enviado a una dirección.
ms.openlocfilehash: 2ceec37928eafab0c4f02382dd24aa3fa91aa9cd
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362305"
---
# <a name="create-a-shared-mailbox"></a>Creación de un buzón compartido 

> [!NOTE]
> Si su organización usa un entorno híbrido de Exchange, debe usar el Centro de administración de Exchange (EAC) local para crear y administrar buzones compartidos. Consulte [Crear buzones compartidos en el centro de administración de Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)<br><br>
> Si no está seguro de si debería crear un buzón compartido o un grupo de Office 365 para Outlook, vea [Comparar grupos](../create-groups/compare-groups.md) para guiarse. Tenga en cuenta que, actualmente, no es posible migrar un buzón compartido a un grupo de Office 365. Si esto le interesaría, indíquelo [votando aquí](https://go.microsoft.com/fwlink/?linkid=871518).

Es fácil crear buzones compartidos de Office 365 para que un grupo de personas pueda supervisar y enviar correos electrónicos desde una dirección de correo electrónico común, como, por ejemplo, info@contoso.com. Cuando un miembro del grupo responde a un mensaje enviado al buzón compartido, parece que el correo electrónico procede del buzón compartido y no de un usuario individual.

Los buzones compartidos incluyen un calendario compartido. A una gran cantidad de pequeñas empresas les gusta usar el calendario compartido como un lugar en el que todos los usuarios introduzcan sus citas. Por ejemplo, si tiene 3 personas que realizan visitas de clientes, todos pueden usar el calendario compartido para introducir las citas. Esta es una forma sencilla de mantener a todos informados.

Antes de crear un buzón compartido, asegúrese de leer [acerca de los buzones compartidos](about-shared-mailboxes.md) para obtener más información.

## <a name="create-a-shared-mailbox-and-add-members"></a>Crear un buzón compartido y agregar miembros
  
1. Inicie sesión con una cuenta de administrador global de Office 365 o una cuenta de administrador de Exchange. Si recibe el mensaje "**No tiene permiso para acceder a esta página o realizar esta acción**" quiere decir que no es administrador. 

::: moniker range="o365-worldwide"

2. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end

::: moniker range="o365-germany"

2. En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=848041), vaya a la página **Grupos** \> **Buzones compartidos**.

::: moniker-end

::: moniker range="o365-21vianet"

2. En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=850627), vaya a la página **Grupos** \> **Buzones compartidos**.

::: moniker-end
    
3. En la página **buzones compartidos**, seleccione **+ agregar un buzón**. Escriba un nombre para el buzón compartido. A continuación, el asistente elige una dirección de correo electrónico, pero puede editarla.
    
    ![Asigne un nombre a su buzón  compartido.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Seleccione **Agregar**. Puede tardar unos minutos antes de poder agregar miembros.

5. En **Pasos siguientes**, elija **Agregar miembros a este buzón**. Los miembros son las personas que podrán ver el correo entrante para este buzón de correo compartido y las respuestas salientes.

   ![Seleccione Agregar miembros.](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Elija el botón **+ Agregar miembros**. Coloque una marca de verificación junto a las personas que desea que usen este buzón de correo compartido y seleccione **Guardar**.

   ![Asignar miembros al buzón compartido](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Seleccione **Cerrar**.

Tiene un buzón compartido que incluye un calendario compartido. Ahora, vaya al siguiente paso: bloquear el inicio para la cuenta de buzón compartido.

## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Bloquear el inicio de sesión de la cuenta de buzón compartido

Cada buzón compartido tiene una cuenta de usuario correspondiente. ¿Ha notado que no se le pidió que proporcionase una contraseña cuando creó el buzón de correo compartido? La cuenta tiene una contraseña, pero se ha generado por el sistema (desconocida). No debería usar la cuenta para iniciar sesión en el buzón compartido.

Pero, ¿qué sucede si un administrador simplemente restablece la contraseña de la cuenta de usuario del buzón compartido? ¿O si un atacante obtiene acceso a las credenciales de cuenta de buzón compartido? Esto permitiría a la cuenta de usuario iniciar sesión en el buzón compartido y enviar correo electrónico. Para evitar esto, tiene que bloquear el inicio de sesión de la cuenta que está asociada con el buzón compartido.

::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la lista de cuentas de usuario, busque la cuenta para el buzón de correo compartido (por ejemplo, cambie el filtro a **usuarios sin licencia**).

3. Seleccione el usuario para abrir su panel de propiedades y seleccione el icono **bloquear este usuario** ![captura de pantalla del icono bloquear este usuario](../../media/block-user-icon.png).

   **Nota**: Si la cuenta ya está bloqueada, se mostrará **inicio de sesión bloqueado** en la parte superior y el icono indicará **desbloquear este usuario**.

4. En el panel **¿bloquear este usuario?**, seleccione **impedir que los usuarios inicien sesión** y seleccione **guardar cambios**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. En la lista de cuentas de usuario, busque la cuenta para el buzón de correo compartido (por ejemplo, cambie la vista a **usuarios sin licencia**) y seleccione la cuenta.

3. En el control flotante de propiedades, seleccione **bloquear inicio de sesión**.

    **Nota:** si la cuenta ya se ha bloqueado, el botón diría **desbloquear inicio de sesión**.

4. En el control flotante **editar el estado de inicio de sesión**, compruebe que está activada la opción Bloquear el usuario para iniciar sesión, seleccione **guardar** y, a continuación, **cerrar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. En la lista de cuentas de usuario, busque la cuenta para el buzón de correo compartido (por ejemplo, cambie la vista a **usuarios sin licencia**) y seleccione la cuenta.

3. En el control flotante de propiedades, seleccione **bloquear inicio de sesión**.

    **Nota:** si la cuenta ya se ha bloqueado, el botón diría **desbloquear inicio de sesión**.

4. En el control flotante **editar el estado de inicio de sesión**, compruebe que está activada la opción Bloquear el usuario para iniciar sesión, seleccione **guardar** y, a continuación, **cerrar**.
::: moniker-end

Para obtener instrucciones sobre cómo bloquear el inicio de sesión para cuentas con el PowerShell de Azure AD (incluyendo varias cuentas al mismo tiempo), consulte [Bloquear cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).

## <a name="add-the-shared-mailbox-to-outlook"></a>Agregar el buzón compartido en Outlook

Si la asignación automática está habilitada en su empresa, como en la mayoría de los casos, el buzón compartido aparecerá automáticamente en la aplicación de Outlook de los usuarios tras cerrar y volver a abrir la aplicación. 

La asignación automática se establece en el buzón del usuario, no en el buzón compartido.   Significa que si intenta usar un grupo de seguridad para administrar quién tiene acceso al buzón compartido, la asignación automática no funcionará. Por lo tanto, si desea utilizar la asignación automática, debe asignar permisos de forma explícita. La asignación automática está activada de forma predeterminada. Para obtener información sobre cómo desactivarlo, consulte [eliminar asignación automática para un buzón compartido](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).

Para obtener más información sobre los buzones compartidos en Outlook, consulte:

- <a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Abrir y usar un buzón compartido en Outlook</a>

- <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Agregar un buzón compartido a Outlook en la Web</a>

- <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregue un buzón compartido en Outlook Mobile</a>

- <a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Abrir una carpeta o un buzón compartido en Outlook para Mac</a>

- <a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Agregar reglas a un buzón compartido</a>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Usar un buzón compartido en un dispositivo móvil (teléfono o tableta)

Puede obtener acceso a un buzón compartido en un dispositivo móvil de dos maneras:
- Agregue el buzón de correo compartido en la <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">aplicación de Outlook para iOS</a> o en la <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">aplicación móvil de Outlook para Android</a>. 
    
    Para obtener instrucciones, vea <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregar un buzón compartido en Outlook para dispositivos móviles</a>.

- Abra su navegador, inicie sesión en Office 365 y vaya a Outlook en la Web. Desde Outlook en la Web, podrá acceder al buzón compartido.

    Para obtener instrucciones, vea <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Agregar un buzón compartido en Outlook en la Web</a>.

## <a name="use-the-shared-calendar"></a>Usar el calendario compartido.

Cuando creó el buzón compartido, creó automáticamente un calendario compartido. Preferimos usar el calendario de buzón de correo compartido, en lugar de un calendario de SharePoint, para realizar el seguimiento de las citas y de la ubicación de los usuarios. Hay un calendario compartido integrado en Outlook y es mucho más fácil de crear y usar que un calendario de SharePoint.

1. En la aplicación de Outlook, vaya a la vista de calendario y seleccione el buzón compartido.

2. Al introducir citas, todos los usuarios que son miembros del buzón de correo compartido podrán verlas.

3. Todos los miembros del buzón compartido pueden crear, ver y administrar citas en el calendario, igual que lo hacen con sus citas personales. Todos los usuarios que sean miembros del buzón compartido pueden ver sus cambios en el calendario compartido.

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md)

[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md)





