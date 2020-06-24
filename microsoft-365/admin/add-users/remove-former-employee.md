---
title: Quitar un antiguo empleado
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Siga esta lista de comprobación para quitar a un empleado de Microsoft 365 y proteger los datos. '
ms.openlocfilehash: 51fd26835cd74fa8403437397d37395fcf1c7301
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844863"
---
# <a name="remove-a-former-employee"></a>Quitar un antiguo empleado

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
## <a name="sign-out-now"></a>Cerrar la sesión ahora

::: moniker range="o365-worldwide"

Vea un breve vídeo sobre cómo quitar a un empleado. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Para evitar que un empleado inicie sesión:

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione el cuadro situado junto al nombre del usuario y, a continuación, seleccione **Restablecer contraseña**.

3. Escriba una contraseña nueva y, a continuación, seleccione **restablecer**. (No lo envíe a ellos).
    
4. Seleccione el nombre del usuario para ir a su panel de propiedades y, en la pestaña **OneDrive** , seleccione **iniciar cierre de sesión**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el usuario y, a continuación, seleccione **Restablecer contraseña**.

3. Escriba una contraseña nueva y, a continuación, seleccione **restablecer**. (No lo envíe a ellos).

4. Vuelva a seleccionar el usuario, expanda **configuración de OneDrive**y, a continuación, seleccione **iniciar** junto a **Cerrar sesión**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el usuario y, a continuación, seleccione **Restablecer contraseña**.

3. Escriba una contraseña nueva y, a continuación, seleccione **restablecer**. (No lo envíe a ellos).

4. Vuelva a seleccionar el usuario, expanda **configuración de OneDrive**y, a continuación, seleccione **iniciar** junto a **Cerrar sesión**.

::: moniker-end

    
En una hora, o después de dejar la página actual de Microsoft 365 en la que se encuentra, se le pedirá que vuelva a iniciar sesión. (Un token de acceso es válido durante una hora, por lo que la escala de tiempo depende de la cantidad de tiempo que quede en ese token y de si se desplaza desde su página web actual).
  
 **ADVERTENCIA**: Si el usuario se encuentra en Outlook en la Web, navegando por su buzón de correo, es posible que no sea expulsado inmediatamente. En cuanto Seleccione un icono diferente, como OneDrive, o actualice el explorador, se iniciará el cierre de sesión. 
  
Para usar PowerShell para cerrar la sesión de un usuario inmediatamente, consulte el cmdlet [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345). 
  
Para obtener más información sobre cuánto se tarda en quitar a un usuario del correo, vea [Todo lo que debe saber sobre el cierre de la sesión de un empleado](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Información general sobre todos los pasos necesarios para quitar a un empleado y proteger los datos
<a name="bkmk_now"> </a>

Una pregunta que se plantea a menudo es: "¿qué debo hacer para proteger los datos cuando un empleado abandona la organización?". En este artículo se explica cómo bloquear el acceso a Microsoft 365 y los pasos que debe seguir para proteger los datos.
  
> [!NOTE]
> Si es administrador global, puede eliminar el empleado, reenviar su correo electrónico, elegir qué hacer con su contenido de OneDrive con la nueva experiencia guiada. Para obtener más información, consulte [administrador global: eliminar un usuario](remove-former-employee.md). Sin embargo, se recomienda completar todos los pasos adicionales enumerados aquí para asegurarse de que el empleado no tiene acceso a los datos de la compañía. 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**Paso** <br/> |**Por qué se debe realizar este procedimiento** <br/> |
|1. [Guardar el contenido del buzón de un antiguo empleado](#save-the-contents-of-a-former-employees-mailbox) <br/> |Esta opción es útil para la persona que se va a ocupar del trabajo del empleado o bien en caso de litigio.  <br/> |
|2. [Reenviar el correo electrónico de un antiguo empleado a otro empleado o convertir en un buzón compartido](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [Borrar y bloquear el dispositivo móvil de un antiguo empleado](#wipe-and-block-a-former-employees-mobile-device) <br/> |Quita los datos profesionales del teléfono o de la tableta.  <br/> |
|4. [bloquear el acceso de un antiguo empleado a los datos de Microsoft 365](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Impide que la persona tenga acceso a sus buzones y datos antiguos de Microsoft 365.  <br/><br/> **Sugerencia**: cuando se bloquea el acceso de un usuario, aún se está pagando por su licencia. Tiene que quitar la licencia de la suscripción para dejar de pagar por ella (paso 5).           |
|5. [Mover el contenido de OneDrive del empleado](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Si solo quita la licencia de un usuario, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |Si la persona ha usado un equipo personal en lugar de uno autorizado por la empresa para descargar archivos de OneDrive y SharePoint, no podrá eliminar dichos archivos almacenados.  <br/><br/> Seguirán teniendo acceso a los archivos que se han sincronizado en su equipo.  <br/> |
|6. [quitar y eliminar la licencia de Microsoft 365 de un antiguo empleado](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [Eliminar la cuenta de usuario de un antiguo empleado](#delete-a-former-employees-user-account)<br/> |Esto quita la cuenta del centro de administración. Mantiene todo organizado.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Guardar el contenido del buzón de un antiguo empleado
<a name="bkmk_preserve"> </a>

Puede guardar el contenido del buzón de correo del antiguo empleado de dos formas:
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    O BIEN
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    Después de convertir el buzón en un "buzón inactivo", los administradores, los responsables de cumplimiento normativo o los administradores de registros pueden utilizar las herramientas de eDiscovery local en Exchange Online para acceder al contenido y realizar búsquedas.
    
    Los buzones inactivos no pueden recibir correo electrónico y no se muestran en la libreta de direcciones compartida de su organización ni en otras listas.
    
    Para obtener información sobre cómo poner una retención en un buzón de correo, vea [administrar buzones inactivos en Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Reenviar el correo electrónico de un antiguo empleado a otro empleado o convertir en un buzón compartido
<a name="bkmk_forward"> </a>

En este paso, asigne la dirección de correo electrónico del exempleado a otro empleado o [convierta el buzón del usuario en un buzón compartido](../email/convert-user-mailbox-to-shared-mailbox.md) que haya creado. 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- Si establece el reenvío de correo electrónico, solo los correos electrónicos  *nuevos*  que reciba el antiguo empleado se enviarán al empleado actual. 
    
- El reenvío de correo electrónico requiere que la cuenta del antiguo empleado tenga una licencia.
    
 > [!IMPORTANT] 
 > Si está configurando el reenvío de correo electrónico o un buzón compartido, al final, no elimine la cuenta del antiguo empleado. Debe conservar la cuenta, puesto que se usa para anclar el reenvío de correo electrónico o el buzón compartido. 

::: moniker range="o365-worldwide"  

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre del empleado que desea bloquear y, a continuación, seleccione la pestaña **correo** .

3. En **reenvío de correo electrónico**, seleccione **administrar reenvío de correo electrónico**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Seleccione **Guardar**. 
    
6. Recuerde no eliminar la cuenta del antiguo empleado.
 
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desee bloquear y expanda **configuración de correo**.

3. Junto a **reenvío de correo electrónico**, seleccione **Editar**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Seleccione **Guardar**. 
    
6. Recuerde no eliminar la cuenta del antiguo empleado.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desee bloquear y expanda **configuración de correo**.

3. Junto a **reenvío de correo electrónico**, seleccione **Editar**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Seleccione **Guardar**. 
    
6. Recuerde no eliminar la cuenta del antiguo empleado.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Borrar y bloquear el dispositivo móvil de un antiguo empleado
<a name="bkmk_mobile"> </a>

Si su antiguo empleado tenía un teléfono de la organización, puede utilizar el Centro de administración de Exchange para borrar y bloquear ese dispositivo de tal modo que se quiten todos los datos de la organización del dispositivo y ya no pueda conectarse a Office 365.
  

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

3. En el Centro de administración de Exchange, vaya a **Destinatarios** \> **Buzones**. 
    
4. Seleccione el usuario y, en **dispositivos móviles**, seleccione **Ver detalles**. 
    
5. En la página **detalles del dispositivo móvil** , en **dispositivos móviles**, seleccione el dispositivo móvil, seleccione barrido de borrado de **datos** ![ y, ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) a continuación, seleccione **bloquear**. 
    
6. Seleccione **Guardar**. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Impedir el acceso de un antiguo empleado a los datos de Microsoft 365
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > El bloqueo de una cuenta puede tardar hasta 24 horas en surtir efecto. Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, debe [restablecer su contraseña](reset-passwords.md) y, a continuación, iniciar un evento único que las cerrará de las sesiones de Microsoft 365 en todos los dispositivos. Consulte [Cerrar la sesión ahora](#sign-out-now)
 

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre del empleado que desea bloquear y, en el nombre del usuario, seleccione el símbolo de **bloquear este usuario**.

3. Seleccione **bloquear al usuario para que no inicie sesión**y, a continuación, seleccione **Guardar**. 

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desee bloquear y, a continuación, seleccione **bloquear el inicio de sesión**.

3. Seleccione **bloquear al usuario para que no inicie sesión**y, a continuación, seleccione **Guardar**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desee bloquear y, a continuación, seleccione **bloquear el inicio de sesión**.

3. Seleccione **bloquear al usuario para que no inicie sesión**y, a continuación, seleccione **Guardar**. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloquear el acceso de un antiguo empleado al correo electrónico (Exchange Online)
<a name="bkmk_block_email"> </a>

Si tiene correo electrónico como parte de su suscripción a Microsoft 365, debe iniciar sesión en el centro de administración de Exchange para seguir estos pasos para impedir que el antiguo empleado tenga acceso a su correo electrónico.
  

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.
     
2. En el Centro de administración de Exchange, vaya a **Destinatarios** \> **Buzones**. 
    
3. Haga doble clic en el usuario y vaya a la página **características de buzón** . En **dispositivos móviles**, seleccione **deshabilitar Exchange ActiveSync** y **deshabilitar OWA para dispositivos** y responda **sí** a ambos cuando se le solicite. 
    
4. En **conectividad de correo**, seleccione **deshabilitar** y responda **sí** cuando se le pida. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Quitar y eliminar la licencia de Microsoft 365 de un antiguo empleado
<a name="bkmk_remove"> </a>

Por lo tanto, no sigue pagando una licencia después de que alguien abandone la organización, debe quitar su licencia de 365 de Microsoft y, a continuación, eliminarla de la suscripción. Si decide no eliminar la licencia de la suscripción, puede asignarla a otro usuario.
  
Al quitar la licencia, todos los datos de ese usuario se conservan durante 30 días. Puede [acceder](get-access-to-and-back-up-a-former-user-s-data.md) a los datos o [restaurar](restore-user.md) la cuenta si el usuario se vuelve a incorporar. Transcurridos los 30 días, todos los datos del usuario (excepto los documentos almacenados en SharePoint Online) se eliminan de forma permanente de Microsoft 365 y no se pueden recuperar. 

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre del empleado que desea bloquear y, a continuación, seleccione la pestaña **licencias y aplicaciones** .

4. Desactive las casillas de las licencias que desee quitar y, a continuación, seleccione **Guardar cambios**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desee bloquear y, a continuación, junto a **licencias de producto**, seleccione **Editar**.

3. En la página **licencias de productos** , desactive la licencia o licencias que desea quitar y, a continuación, seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desee bloquear y, a continuación, junto a **licencias de producto**, seleccione **Editar**.

3. En la página **licencias de productos** , desactive la licencia o licencias que desea quitar y, a continuación, seleccione **Guardar**.

::: moniker-end


**Para reducir el número de licencias por las que paga** hasta que contrate a otra persona, haga lo siguiente: 

::: moniker range="o365-worldwide"



1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.


::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Suscripciones</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>.

::: moniker-end
    
2. Seleccione **Agregar o quitar licencias** para eliminar la licencia para no pagar por ella hasta que contrate a otra persona.

Al [Agregar](add-users.md) a otra persona a su empresa, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.
    
Para obtener más información acerca de la administración de licencias de usuario para Microsoft 365 para empresas, consulte [asignar licencias a usuarios en microsoft 365 para](../manage/assign-licenses-to-users.md)empresas y [quitar licencias de usuarios en Microsoft 365 para empresas](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Cómo afectan las cuentas de empleados eliminadas a Skype Empresarial
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>Eliminar la cuenta de usuario de un antiguo empleado
<a name="bkmk_delete"> </a>

Después de haber guardado y accedido a todos los datos de usuario del antiguo empleado, puede suprimir su cuenta.
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre del empleado que desea eliminar.

3. En el nombre del usuario, seleccione el símbolo **eliminar usuario**. Elija las opciones que desee para este usuario y, a continuación, seleccione **eliminar usuario**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre del empleado que desea eliminar.

3. En la parte superior de la página, seleccione **eliminar usuario**. Elija las opciones que desee para este usuario y, a continuación, seleccione **eliminar usuario**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre del empleado que desea eliminar.

3. En la parte superior de la página, seleccione **eliminar usuario**. Elija las opciones que desee para este usuario y, a continuación, seleccione **eliminar usuario**.

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>¿Su organización utiliza Active Directory?

Si su organización sincroniza las cuentas de usuario con Microsoft 365 desde un entorno local de Active Directory, debe eliminar y restaurar esas cuentas de usuario en el servicio local de Active Directory. No puede suprimirlas ni restaurarlas en Office 365.
  
Para obtener instrucciones, consulte este artículo: [eliminar una cuenta de usuario](https://go.microsoft.com/fwlink/?linkid=841808).
  
Si usa Azure Active Directory, consulte el cmdlet de PowerShell [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230). 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Todo lo que debe saber sobre el cierre de la sesión de un empleado
<a name="bkmk_session"> </a>

Aquí tiene información sobre cómo quitar a un empleado del correo electrónico (Exchange).
  
|||
|:-----|:-----|
|**Qué puede hacer** <br/> |**Cómo debe hacerlo** <br/> |
|Cerrar una sesión (de Outlook en la Web, Outlook, Exchange Active Sync, etc.) y forzar el inicio de una sesión nueva  <br/> |Restablecer la contraseña  <br/> |
|Cerrar una sesión y bloquear el acceso a sesiones futuras (para todos los protocolos)  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Cerrar la sesión de un protocolo en particular (como ActiveSync)  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
Las operaciones anteriores pueden realizarse en 3 lugares:
  
|||
|:-----|:-----|
|**Si cierra la sesión aquí** <br/> |**Cuánto tiempo se tarda** <br/> |
|En el centro de administración de Exchange o usando PowerShell  <br/> |La duración estimada es de 30 minutos  <br/> |
|En el centro de administración de Azure Active Directory  <br/> |La duración estimada es de 60 minutos  <br/> |
|En un entorno local  <br/> |La duración estimada es de 3 horas o más  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>Procedimiento para obtener una respuesta más rápida para la eliminación de la cuenta

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>Artículos relacionados

[Restaurar un usuario](restore-user.md)
  
