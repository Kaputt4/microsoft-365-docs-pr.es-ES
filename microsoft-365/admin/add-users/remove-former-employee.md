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
description: 'Siga esta lista de comprobación para quitar un empleado de Microsoft 365 y proteger los datos. '
ms.openlocfilehash: 50355a20e0d0e8ff782deebd9be65fdabf875bb2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860778"
---
# <a name="remove-or-delete-a-former-employee"></a>Quitar o eliminar un antiguo empleado

## <a name="sign-out-now"></a>Cerrar la sesión ahora

::: moniker range="o365-worldwide"

Vea un breve vídeo sobre cómo quitar a un empleado. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Si este vídeo le ha sido de ayuda, vea la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Para evitar que un empleado inicia sesión:

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el cuadro situado junto al nombre del usuario y, a continuación, seleccione **Restablecer contraseña.**
3. Escriba una nueva contraseña y, a continuación, **seleccione Restablecer**. (No se lo envíe).
4. Seleccione el nombre del usuario para ir al panel de propiedades y, en la pestaña **Cuenta,** seleccione **Iniciar la sesión.**

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el usuario y, a continuación, **seleccione Restablecer contraseña**.

3. Escriba una nueva contraseña y, a continuación, **seleccione Restablecer**. (No se lo envíe).

4. Seleccione el nombre del usuario para ir al panel de propiedades y, en la pestaña **Cuenta,** seleccione **Iniciar la sesión.**

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el usuario y, a continuación, **seleccione Restablecer contraseña**.

3. Escriba una nueva contraseña y, a continuación, **seleccione Restablecer**. (No se lo envíe).

4. Seleccione el nombre del usuario para ir al panel de propiedades y, en la pestaña **Cuenta,** seleccione **Iniciar la sesión.**

::: moniker-end

> [!NOTE]
> Debe ser un administrador global para iniciar la sesión.

Dentro de una hora , o después de salir de la página actual de Microsoft 365 en la que se encuentran, se les pedirá que inicien sesión de nuevo. Un token de acceso es bueno durante una hora, por lo que la escala de tiempo depende de cuánto tiempo queda en ese token y de si navegan fuera de su página web actual.
  
> [!IMPORTANT]
> Si el usuario está en Outlook en la web, simplemente haciendo clic en su buzón, es posible que no se eche inmediatamente. Tan pronto como seleccionan un icono diferente, como OneDrive, o actualizan su explorador, se inicia el inicio de sesión.
  
Para usar PowerShell para cerrar la sesión de un usuario inmediatamente, consulte el cmdlet [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken).
  
Para obtener más información sobre cuánto se tarda en quitar a un usuario del correo, vea [Todo lo que debe saber sobre el cierre de la sesión de un empleado](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Información general sobre todos los pasos necesarios para quitar a un empleado y proteger los datos

Una pregunta que se plantea a menudo es: "¿qué debo hacer para proteger los datos cuando un empleado abandona la organización?". En este artículo se explica cómo bloquear el acceso a Microsoft 365 y los pasos que debe seguir para proteger los datos.
  
> [!NOTE]
> Si es un administrador global, puede eliminar al empleado, reenviar su correo electrónico, elegir qué hacer con su contenido de OneDrive con la nueva experiencia guiada. Para obtener más información, [vea Global admin: Delete a user](remove-former-employee.md). Sin embargo, se recomienda completar todos los pasos adicionales enumerados aquí para garantizar que el empleado no tenga acceso a los datos de su empresa. 
  
Aquí se incluye información general rápida. Cada paso se explica en detalle en este artículo.
  
|||
|:-----|:-----|
|**Paso** <br/> |**Por qué se debe realizar este procedimiento** <br/> |
|1. [Guardar el contenido del buzón de un antiguo empleado](#save-the-contents-of-a-former-employees-mailbox) <br/> |Esto es útil para la persona que va a asumir el trabajo del empleado, o si hay litigio.  <br/> |
|2. [Reenviar el correo electrónico de un antiguo empleado a otro empleado o convertir en un buzón compartido](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |Esta opción permite mantener activa la dirección de correo electrónico de su antiguo empleado. Si tiene clientes o socios que siguen enviando correos electrónicos a la dirección del antiguo empleado, con esta opción el correo llegará a la persona que ahora se encarga del trabajo.  <br/> |
|3. [Borrar y bloquear el dispositivo móvil de un antiguo empleado](#wipe-and-block-a-former-employees-mobile-device) <br/> |Quita los datos profesionales del teléfono o de la tableta.  <br/> |
|4. Bloquear el acceso de un antiguo empleado [a datos de Microsoft 365](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Impide que la persona acceda a sus antiguos buzones y datos de Microsoft 365.  <br/><br/> **Sugerencia:** Al bloquear el acceso de un usuario, sigue pagando por su licencia. Para dejar de pagar por ella, elimine la licencia de la suscripción (paso 5).  |
|5. [Mover el contenido de OneDrive del empleado](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Si solo quita la licencia de un usuario, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después.  <br/><br/> Antes de eliminar la cuenta, es recomendable mover el contenido de su OneDrive a otra ubicación a la que pueda obtener acceso fácilmente. Después de eliminar la cuenta de un empleado, el contenido de su OneDrive se conserva durante **30** días. Durante ese período de tiempo, puede restaurar la cuenta del usuario y obtener acceso a su contenido de OneDrive. Si restablece la cuenta del usuario, podrá obtener acceso al contenido de OneDrive incluso hasta 30 días después.  <br/> |
|5a. ¿Qué sucede si la persona ha usado su equipo personal para acceder a OneDrive y SharePoint?  <br/> |Si la persona ha usado un equipo personal en lugar de uno autorizado por la empresa para descargar archivos de OneDrive y SharePoint, no podrá eliminar dichos archivos almacenados.  <br/><br/> Siguen teniendo acceso a los archivos que se sincronizaron con su equipo.  <br/> |
|6. [Quitar y eliminar la licencia de Microsoft 365 de un antiguo empleado](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |Cuando quita una licencia, puede asignarla a otra persona. O bien, puede eliminar la licencia para no pagar por ella hasta que contrate a otra persona.  <br/><br/> Al quitar o eliminar una licencia, el correo electrónico, los contactos y el calendario antiguos del usuario se conservan durante **30 días** y, después, se eliminan permanentemente. Si quita o elimina una licencia, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después.  <br/> |
|7. [Eliminar la cuenta de usuario de un antiguo empleado](#delete-a-former-employees-user-account)<br/> |Esto quita la cuenta del centro de administración. Mantiene todo organizado.  <br/> |

## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Guardar el contenido del buzón de un antiguo empleado

Puede guardar el contenido del buzón de correo del antiguo empleado de dos formas:
  
1. Agregue la dirección de correo electrónico del antiguo empleado a su versión de Outlook 2013 o 2016 y, a continuación, exporte los datos en un archivo .pst. Puede importar los datos a otra cuenta de correo electrónico si lo necesita. Para saber cómo hacerlo, consulte [Acceder y realizar una copia de seguridad de los datos de un antiguo usuario](get-access-to-and-back-up-a-former-user-s-data.md).

    O BIEN

2. Aplique una retención por juicio o una conservación local al buzón de correo antes de eliminar la cuenta del usuario. Esto es mucho más complicado que la primera opción, pero vale la pena hacerlo si su plan Enterprise incluye archivado y retención legal, si los litigios son una posibilidad o si tiene un departamento informático potente a nivel técnico.

    Después de convertir el buzón en un "buzón inactivo", los administradores, los responsables de cumplimiento o los administradores de registros pueden usar las herramientas de exhibición de documentos electrónicos de In-Place en Exchange Online para obtener acceso y buscar en el contenido.

    Los buzones inactivos no pueden recibir correo electrónico y no se muestran en la libreta de direcciones compartida de su organización ni en otras listas.

    Para obtener información sobre cómo colocar una retención en un buzón de correo, vea [Manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).

## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Reenviar el correo electrónico de un antiguo empleado a otro empleado o convertir en un buzón compartido

En este paso, asigne la dirección de correo electrónico del exempleado a otro empleado o [convierta el buzón del usuario en un buzón compartido](../email/convert-user-mailbox-to-shared-mailbox.md) que haya creado.
  
- Crear un buzón compartido es la forma más económica, ya que no conlleva el pago de una licencia **si el tamaño del buzón es menor que 50 GB**. Si el buzón supera los 50 GB, necesitará asignar una licencia.
- Si convierte el buzón en uno compartido, todos los mensajes de correo electrónico antiguos también estarán disponibles. Esto puede ocupar una gran cantidad de espacio.
- Si establece el reenvío de correo electrónico, solo los correos electrónicos  *nuevos*  que reciba el antiguo empleado se enviarán al empleado actual.

 > [!IMPORTANT]
 > Si configura el reenvío de correo electrónico o un buzón compartido, al final, no elimine la cuenta del antiguo empleado. Debe conservar la cuenta, puesto que se usa para anclar el reenvío de correo electrónico o el buzón compartido.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea bloquear y, a continuación, seleccione la **pestaña** Correo.
3. En **Reenvío de correo electrónico,** seleccione Administrar reenvío de correo **electrónico**.
4. Active **Reenviar todo el correo electrónico enviado a este buzón**. En el **cuadro Dirección de reenvío,** escriba la dirección de correo electrónico del empleado actual que va a obtener el correo electrónico.
5. Seleccione **Guardar**.
6. Recuerde no eliminar la cuenta del antiguo empleado.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desea bloquear y expanda **Configuración de correo**.

3. Junto a **Reenvío de correo electrónico,** seleccione **Editar**.

4. Active **Reenviar todo el correo electrónico enviado a este buzón**. En el cuadro **Dirección de reenvío**, escriba la dirección de correo electrónico del empleado actual (o del buzón de correo compartido) al que se enviará el correo.
  
5. Seleccione **Guardar**.

6. Recuerde no eliminar la cuenta del antiguo empleado.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desea bloquear y expanda **Configuración de correo**.

3. Junto a **Reenvío de correo electrónico,** seleccione **Editar**.

4. Active **Reenviar todo el correo electrónico enviado a este buzón**. En el cuadro **Dirección de reenvío**, escriba la dirección de correo electrónico del empleado actual (o del buzón de correo compartido) al que se enviará el correo.
  
5. Seleccione **Guardar**.

6. Recuerde no eliminar la cuenta del antiguo empleado.

::: moniker-end

## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Borrar y bloquear el dispositivo móvil de un antiguo empleado

Si el antiguo empleado tenía un teléfono de la organización, puede usar el Centro de administración de Exchange para borrar y bloquear ese dispositivo de modo que todos los datos de la organización se quiten del dispositivo y ya no se puedan conectar a Office 365.

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.
2. En el Centro de administración de Exchange, vaya a **Destinatarios** \> **Buzones**.
3. Seleccione el usuario y, en **Dispositivos móviles,** seleccione **Ver detalles**.
4. En la **página Detalles del** dispositivo móvil, en **Dispositivos** móviles , seleccione el dispositivo móvil, seleccione **Borrar** dispositivo de borrado de datos y, a ![ continuación, seleccione ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Bloquear**.
5. Seleccione **Guardar**.
   > [!TIP]
   > Asegúrese de quitar o deshabilitar el usuario de su servicio de Blackberry Enterprise local. También debe deshabilitar cualquier dispositivo BlackBerry para el usuario. Consulte la BlackBerry Business Cloud Services Administration Guide (Guía de administración de servicios de BlackBerry Business Cloud) si necesita pasos específicos sobre cómo deshabilitar al usuario.

## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Bloquear el acceso de un antiguo empleado a datos de Microsoft 365

 > [!IMPORTANT]
 > El bloqueo de una cuenta puede tardar hasta 24 horas en tener efecto. Si necesita impedir inmediatamente el acceso de inicio de [](reset-passwords.md) sesión de un usuario, debe restablecer su contraseña y, a continuación, iniciar un evento único que las cerrará de sesión de Microsoft 365 en todos los dispositivos. Consulte [Cerrar la sesión ahora](#sign-out-now)

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea bloquear y, bajo el nombre del usuario, seleccione el símbolo para **Bloquear este usuario**.
3. Seleccione **Bloquear al usuario para que no inicie sesión** y, a continuación, seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desea bloquear y, a continuación, **seleccione Bloquear inicio de sesión**.

3. Seleccione **Bloquear al usuario para que no inicie sesión** y, a continuación, seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desea bloquear y, a continuación, **seleccione Bloquear inicio de sesión**.

3. Seleccione **Bloquear al usuario para que no inicie sesión** y, a continuación, seleccione **Guardar**.

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloquear el acceso de un antiguo empleado al correo electrónico (Exchange Online)

Si tiene correo electrónico como parte de su suscripción a Microsoft 365, debe iniciar sesión en el Centro de administración de Exchange para seguir estos pasos para impedir que el antiguo empleado tenga acceso a su correo electrónico.
  
1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.
2. En el Centro de administración de Exchange, vaya a **Destinatarios** \> **Buzones**.
3. Haga doble clic en el usuario y vaya a la página **Características del buzón.** En **Dispositivos móviles,** **selecciona Deshabilitar Exchange ActiveSync** y Deshabilitar **OWA** para dispositivos y responde **Sí** a ambos cuando se le pida.
4. En **Conectividad de correo** electrónico, seleccione **Deshabilitar** y responder **Sí** cuando se le pida.

## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Quitar y eliminar la licencia de Microsoft 365 de un antiguo empleado

Por lo tanto, no siga pagando una licencia después de que alguien abandone la organización, debe quitar su licencia de Microsoft 365 y, a continuación, eliminarla de la suscripción. Si decide no eliminar la licencia de la suscripción, puede asignarla a otro usuario.
  
Al quitar la licencia, todos los datos de ese usuario se conservan durante 30 días. Puede [acceder](get-access-to-and-back-up-a-former-user-s-data.md) a los datos o [restaurar](restore-user.md) la cuenta si el usuario se vuelve a incorporar. Después de 30 días, todos los datos del usuario (excepto los documentos almacenados en SharePoint Online) se eliminan permanentemente de Microsoft 365 y no se pueden recuperar.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea bloquear y, a continuación, seleccione la pestaña **Licencias y** aplicaciones.
3. Desactive las casillas de las licencias que desea quitar y, a continuación, **seleccione Guardar cambios**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desea bloquear y, a continuación, junto **a Licencias de producto,** seleccione **Editar**.

3. En la **página Licencias de productos,** desactive las licencias que desea quitar y, a continuación, **seleccione Guardar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el empleado que desea bloquear y, a continuación, junto **a Licencias de producto,** seleccione **Editar**.

3. En la **página Licencias de productos,** desactive las licencias que desea quitar y, a continuación, **seleccione Guardar**.

::: moniker-end

**Para reducir el número de licencias que está pagando** hasta que contrate a otra persona, siga estos pasos:

::: moniker range="o365-worldwide"
1. En el Centro de  administración, vaya a la página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Facturación de sus productos</a> y seleccione la **pestaña** Productos.
2. Seleccione la suscripción de la que desea quitar licencias.
3. En la página de detalles, seleccione **Quitar licencias**.
4. En el **panel Quitar licencias,** en Nueva cantidad, en el cuadro **Total** de licencias, escriba el número total de licencias que desea para esta suscripción. Por ejemplo, si tiene 25 licencias y desea quitar una de ellas, escriba 24.
5. Seleccione **Guardar**.
::: moniker-end

::: moniker range="o365-germany"
1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Suscripciones</a>.
2. Seleccione **Agregar o quitar licencias** para eliminar la licencia para que no la pague hasta que contrate a otra persona.
::: moniker-end

::: moniker range="o365-21vianet"
1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>.
2. Seleccione **Agregar o quitar licencias** para eliminar la licencia para que no la pague hasta que contrate a otra persona.
::: moniker-end

Cuando [agregues otra persona](add-users.md) a tu empresa, se te pedirá que compres una licencia al mismo tiempo, con un solo paso.

Para obtener más información acerca de la administración de licencias de usuario para Microsoft 365 para empresas, vea Asignar licencias a usuarios de [Microsoft 365](../manage/assign-licenses-to-users.md)para empresas y [Unassign licenses from users in Microsoft 365 for business](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Cómo afectan las cuentas de empleados eliminadas a Skype Empresarial

Al quitar una licencia de usuario de Office 365, el número de RTC asociado con este se liberará. Puede asignarlo a otro usuario.
  
Si el usuario pertenece a un grupo de cola, ya no será un destino apto de los agentes de cola de llamadas. Por lo tanto, le recomendamos quitar también al usuario de los grupos asociados con la cola de llamadas.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Configurar el reenvío de llamadas a personas de la organización

Si necesita configurar el reenvío de llamadas para el número de teléfono del empleado terminado, la configuración de reenvío de llamadas en las directivas de llamadas puede configurar el reenvío donde las llamadas entrantes se pueden reenviar a otros usuarios o pueden llamar a otra persona al mismo tiempo. Para obtener más información, vea [Calling policies in Microsoft Teams](/microsoftteams/teams-calling-policy).
  
## <a name="delete-a-former-employees-user-account"></a>Eliminar la cuenta de usuario de un antiguo empleado

Después de haber guardado y accedido a todos los datos de usuario del antiguo empleado, puede suprimir su cuenta.
  
No elimine la cuenta si ha configurado el reenvío de correo electrónico o la ha convertido en un buzón compartido. En ambos casos se necesita la cuenta para anclar el reenvío de correo o el buzón compartido.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea eliminar.
3. Bajo el nombre del usuario, seleccione el símbolo para **Eliminar usuario**. Elija las opciones que desee para este usuario y, a continuación, **seleccione Eliminar usuario**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre del empleado que desea eliminar.

3. En la parte superior de la página, seleccione **Eliminar usuario**. Elija las opciones que desee para este usuario y, a continuación, **seleccione Eliminar usuario**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el nombre del empleado que desea eliminar.

3. En la parte superior de la página, seleccione **Eliminar usuario**. Elija las opciones que desee para este usuario y, a continuación, **seleccione Eliminar usuario**.

::: moniker-end

Al eliminar un usuario, la cuenta se vuelve inactiva durante aproximadamente 30 días. Tiene tiempo hasta ese momento para restaurar la cuenta antes de que se elimine de forma permanente.
  
### <a name="does-your-organization-use-active-directory"></a>¿Su organización utiliza Active Directory?

Si su organización sincroniza cuentas de usuario con Microsoft 365 desde un entorno local de Active Directory, debe eliminar y restaurar esas cuentas de usuario en el servicio de Active Directory local. No puede suprimirlas ni restaurarlas en Office 365.
  
Para obtener información sobre cómo eliminar y restaurar una cuenta de usuario en Active Directory, vea [Eliminar una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).
  
Si usa Azure Active Directory, consulte el cmdlet [Remove-MsolUser](https://docs.microsoft.com/powershell/module/msonline/remove-msoluser) PowerShell.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Todo lo que debe saber sobre el cierre de la sesión de un empleado

Aquí tiene información sobre cómo quitar a un empleado del correo electrónico (Exchange).
  
|||
|:-----|:-----|
|**Qué puede hacer** <br/> |**Cómo debe hacerlo** <br/> |
|Cerrar una sesión (de Outlook en la Web, Outlook, Exchange Active Sync, etc.) y forzar el inicio de una sesión nueva  <br/> |Restablecer la contraseña  <br/> |
|Cerrar una sesión y bloquear el acceso a sesiones futuras (para todos los protocolos)  <br/> |Deshabilite la cuenta. Por ejemplo, (en el Centro de administración de Exchange o mediante PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Cerrar la sesión de un protocolo en particular (como ActiveSync)  <br/> |Deshabilite el protocolo. Por ejemplo, (en el Centro de administración de Exchange o mediante PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

Las operaciones anteriores se pueden realizar en tres lugares:
  
|||
|:-----|:-----|
|**Si cierra la sesión aquí** <br/> |**Cuánto tiempo se tarda** <br/> |
|En el centro de administración de Exchange o usando PowerShell  <br/> |La duración estimada es de 30 minutos  <br/> |
|En el centro de administración de Azure Active Directory  <br/> |La duración estimada es de 60 minutos  <br/> |
|En un entorno local  <br/> |La duración estimada es de 3 horas o más  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>Procedimiento para obtener una respuesta más rápida para la eliminación de la cuenta

 **Más rápida**: use el Centro de administración de Exchange (use PowerShell) o el Centro de administración de Azure Active Directory. En un entorno local, el cambio mediante DirSync puede tardar varias horas en sincronizarse.
  
 **Más rápida para un usuario con presencia local y en el centro de datos de Exchange**: finalice la sesión mediante el Centro de administración de Azure Active Directory o el Centro de administración de Exchange Y efectúe también el cambio en el entorno local. En caso contrario, DirSync sobrescribirá el cambio realizado en el Centro de administración de Exchange o el Centro de administración Azure Active Directory.
  
## <a name="related-articles"></a>Artículos relacionados

[Restaurar un usuario](restore-user.md)