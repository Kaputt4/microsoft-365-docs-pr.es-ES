---
title: Cambiar un nombre de usuario y una dirección de correo electrónico
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: 'Obtenga información acerca de cómo un administrador global puede cambiar la dirección de correo electrónico y el nombre para mostrar de un usuario. '
ms.openlocfilehash: 76a2124c7fc73e40650a18985a5aa10acf57737a
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780630"
---
# <a name="change-a-user-name-and-email-address"></a>Cambiar un nombre de usuario y una dirección de correo electrónico

Es posible que deba cambiar la dirección de correo electrónico y el nombre para mostrar de un usuario si, por ejemplo, este decide cambiarse los apellidos.

Vea un vídeo corto sobre el cambio de la dirección de correo electrónico de un usuario. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="change-a-users-email-address"></a>Cambiar la dirección de correo electrónico de un usuario

Para poder realizar estos pasos, debe ser [Administrador global](about-admin-roles.md). 

::: moniker range="o365-worldwide"
 
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
    
2. Seleccione el nombre de usuario y después, en la pestaña **Cuenta** seleccione **Administrar nombre de usuario**.
    
3. En el primer cuadro, escriba la primera parte de la nueva dirección de correo electrónico. Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable. 

4. Seleccione **Guardar cambios**.

   
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  

2. Seleccione el usuario. En el panel flotante próximo a **Nombre de usuario/Correo electrónico**, seleccione **Editar**.

3. En el primer cuadro, escriba la primera parte de la nueva dirección de correo electrónico. Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.

4. Seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. Seleccione el usuario. En el panel flotante próximo a **Nombre de usuario/Correo electrónico**, seleccione **Editar**.

3. En el primer cuadro, escriba la primera parte de la nueva dirección de correo electrónico. Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable.

4. Seleccione **Guardar**.

::: moniker-end

**IMPORTANTE**: Si recibe un mensaje de error, consulte [Resolver mensajes de error](#resolve-error-messages).

## <a name="set-the-primary-email-address"></a>Establezca la dirección de correo electrónico principal.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
    
2. Seleccione el nombre de usuario y después, en la pestaña **Cuenta**, seleccione **Administrar alias del correo electrónico**.

3. Seleccione **Establecer como principal** para la dirección de correo electrónico que desea establecer como la dirección de correo electrónico principal de esa persona. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Además, solo verá esta opción si es un administrador global. Si no ve la opción, no tiene permisos para cambiar el nombre ni la dirección de correo electrónico principal del usuario.
  
4. Verá una gran advertencia amarilla que le dice que va a cambiar la información de inicio de sesión del usuario. Seleccione **Guardar** y, a continuación, **Cerrar**.
    
5. Comunique a la persona la siguiente información:
 
  - Este cambio puede tardar en efectuarse.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Si está usando Skype Empresarial Online, indíqueles que deberán programar otra vez cualquier reunión de Skype Empresarial Online que hayan organizado y que tendrán que comunicar a sus contactos externos que actualicen la información de contacto anterior.

  - Si está usando OneDrive, dígales que la URL para esta ubicación ha cambiado. Si tienen los cuadernos de notas de OneNote en sus OneDrive, entonces puede que necesiten cerrarlos y reabrirlos en OneNote. Si tienen archivos compartidos desde sus OneDrive, entonces puede que no funcionen los vínculos a los archivos y el usuario puede volver a compartir.    
  
  - Si también se cambió su contraseña, infórmele de que se le solicitará que escriba la nueva en su dispositivo móvil o, de lo contrario, no se realizará la sincronización.
  
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  

2. Seleccione el usuario. En el panel flotante próximo a **Nombre de usuario/Correo electrónico**, seleccione **Editar**.

3. Seleccione **Establecer como principal** para la dirección de correo electrónico que desea establecer como la dirección de correo electrónico principal de esa persona. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Además, solo verá esta opción si es un administrador global. Si no ve la opción, no tiene permisos para cambiar el nombre ni la dirección de correo electrónico principal del usuario.
  
4. Verá una gran advertencia amarilla que le dice que va a cambiar la información de inicio de sesión del usuario. Seleccione **Guardar** y, a continuación, **Cerrar**.
    
5. Comunique a la persona la siguiente información:
 
  - Este cambio puede tardar en efectuarse.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Si está usando Skype Empresarial Online, indíqueles que deberán programar otra vez cualquier reunión de Skype Empresarial Online que hayan organizado y que tendrán que comunicar a sus contactos externos que actualicen la información de contacto anterior.

  - Si está usando OneDrive, dígales que la URL para esta ubicación ha cambiado. Si tienen los cuadernos de notas de OneNote en sus OneDrive, entonces puede que necesiten cerrarlos y reabrirlos en OneNote. Si tienen archivos compartidos desde sus OneDrive, entonces puede que no funcionen los vínculos a los archivos y el usuario puede volver a compartir.    
  
  - Si también se cambió su contraseña, infórmele de que se le solicitará que escriba la nueva en su dispositivo móvil o, de lo contrario, no se realizará la sincronización.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. Seleccione el usuario. En el panel flotante próximo a **Nombre de usuario/Correo electrónico**, seleccione **Editar**.

3. Seleccione **Establecer como principal** para la dirección de correo electrónico que desea establecer como la dirección de correo electrónico principal de esa persona. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Además, solo verá esta opción si es un administrador global. Si no ve la opción, no tiene permisos para cambiar el nombre ni la dirección de correo electrónico principal del usuario.
  
4. Verá una gran advertencia amarilla que le dice que va a cambiar la información de inicio de sesión del usuario. Seleccione **Guardar** y, a continuación, **Cerrar**.
    
5. Comunique a la persona la siguiente información:
 
  - Este cambio puede tardar en efectuarse.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Si está usando Skype Empresarial Online, indíqueles que deberán programar otra vez cualquier reunión de Skype Empresarial Online que hayan organizado y que tendrán que comunicar a sus contactos externos que actualicen la información de contacto anterior.

  - Si está usando OneDrive, dígales que la URL para esta ubicación ha cambiado. Si tienen los cuadernos de notas de OneNote en sus OneDrive, entonces puede que necesiten cerrarlos y reabrirlos en OneNote. Si tienen archivos compartidos desde sus OneDrive, entonces puede que no funcionen los vínculos a los archivos y el usuario puede volver a compartir.    
  
  - Si también se cambió su contraseña, infórmele de que se le solicitará que escriba la nueva en su dispositivo móvil o, de lo contrario, no se realizará la sincronización.

::: moniker-end
  
## <a name="change-a-users-display-name"></a>Cambiar el nombre para mostrar de un usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre de usuario y después, en la pestaña **Cuenta** seleccione **Administrar información de contacto**.

3. En el cuadro **Nombre para mostrar**, escriba un nombre nuevo de la persona y después, seleccione **Guardar**.

    Si recibió el mensaje de error **No se pudo modificar el usuario. Revise la información de usuario y vuelva a intentarlo**, consulte [Resolver mensajes de error](#resolve-error-messages). 

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  

2. Seleccione el usuario. En el panel flotante próximo a **Información de contacto**, seleccione **Editar**.

3. En el cuadro **Nombre para mostrar**, escriba un nombre nuevo de la persona y después, seleccione **Guardar**.

    Si recibió el mensaje de error **No se pudo modificar el usuario. Revise la información de usuario y vuelva a intentarlo**, consulte [Resolver mensajes de error](#resolve-error-messages). 

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. Seleccione el usuario. En el panel flotante próximo a **Información de contacto**, seleccione **Editar**.

3. En el cuadro **Nombre para mostrar**, escriba un nombre nuevo de la persona y después, seleccione **Guardar**.

    Si recibió el mensaje de error **No se pudo modificar el usuario. Revise la información de usuario y vuelva a intentarlo**, consulte [Resolver mensajes de error](#resolve-error-messages). 

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

## <a name="resolve-error-messages"></a>Resolver mensajes de error

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"No se encuentra ningún parámetro que coincida con el nombre de parámetro `EmailAddresses´"

If you get the error message " **A parameter cannot be found that matches parameter name 'EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call Support and they will do a full sync for you.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>"No se pudo modificar el usuario. Revise la información de usuario y vuelva a intentarlo"

Si recibió el mensaje de error "**No se pudo modificar el usuario. Revise la información de usuario y vuelva a intentarlo**". significa que no es un administrador global y no tiene permisos para cambiar el nombre del usuario. Busque el administrador global de su empresa y pídale que realice el cambio.


## <a name="what-to-do-with-old-email-addresses"></a>Qué hacer con las direcciones de correo electrónico antiguas

A person's previous primary email address is retained as an additional email address. **We strongly recommend that you don't remove the old email address.**
  
Some people will likely continue to send email to the person's old email address and deleting it may result in NDR failures. Microsoft will automatically route it to the new one. Also, do not reuse old SMTP email addresses and apply them to new accounts. This can also cause NDR failures or delivery to an unintended mailbox.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>¿Qué sucede si la libreta de direcciones sin conexión de la persona no se sincroniza con la lista global de direcciones?

If they are using Exchange Online or if their account is linked with your organization's on-premises Exchange environment, you may see this error when you try to change a username and email address: "This user is synchronized with your local Active Directory. Some details can be edited only through your local Active Directory."
  
This is due to the Microsoft Online Email Routing Address (MOERA). The MOERA is constructed from the person's  _userPrincipalName_ attribute in Active Directory and is automatically assigned to the cloud account during the initial sync and once created, it cannot be modified or removed in Office 365. You can subsequently change the username in the Active Directory, but it will not change the MOERA and you may run into issues displaying the newly changed name in the Global Address List. 
  
Para corregir este error, inicie sesión en el [Módulo Microsoft Azure Active Directory para PowerShell]( https://go.microsoft.com/fwlink/?LinkId=823193) con sus credenciales de administrador de Microsoft 365. Use la sintaxis que se muestra a continuación: 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> Esto cambia el atributo **userPrincipalName** de la persona y no influirá en su dirección de correo electrónico Microsoft Online Email Routing Address (MOERA). Sin embargo, es recomendable, que el inicio de sesión del usuario UPN coincida con su dirección SMTP principal. 
  
Para obtener información sobre cómo cambiar el nombre de usuario de una persona en Active Directory, en Windows Server 2003 y en las versiones anteriores, vea [Cambiar el nombre de una cuenta de usuario](https://go.microsoft.com/fwlink/?LinkId=809091).
  
## <a name="related-articles"></a>Artículos relacionados

[Administradores: Restablecer una contraseña de uno o más usuarios](reset-passwords.md)
  
[Agregar otra dirección de correo electrónico a un usuario](../email/add-another-email-alias-for-a-user.md)
