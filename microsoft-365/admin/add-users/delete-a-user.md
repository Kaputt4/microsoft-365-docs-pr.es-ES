---
title: Elimine un usuario de su organización
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Obtenga información sobre cómo eliminar una cuenta de usuario Microsoft 365, qué hacer con el correo electrónico del usuario y OneDrive contenido, y si desea conservar la licencia del producto.
ms.openlocfilehash: faa971fa8419f6bcc80855fd9dcd559a542e00a8
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2022
ms.locfileid: "65436787"
---
# <a name="delete-a-user-from-your-organization"></a>Elimine un usuario de su organización
  
**¿Busca cómo eliminar su *propia* cuenta de usuario Microsoft 365 que usa en el trabajo o la escuela? Póngase en contacto con el soporte técnico de su trabajo o universidad para realizar estos pasos.**

## <a name="before-you-begin"></a>Antes de empezar

- Solo las personas que tienen [Microsoft 365 permisos de administrador global](about-admin-roles.md) o administración de usuarios para la empresa o la escuela pueden eliminar cuentas de usuario.
- Tiene 30 días para [restaurar](restore-user.md) la cuenta antes de que los datos del usuario se eliminen de forma permanente.
- Si desea conservar los datos del usuario de OneDrive, muévalos a otra ubicación. Incluso puede mover los datos hasta 30 días después de eliminar la cuenta. Vea [Acceder a los datos de usuario antiguos y realizar una copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md). No es necesario mover sus archivos de SharePoint, pues seguirá teniendo acceso a ellos.
- Si desea mantener el correo electrónico del usuario, **ANTES** de eliminar la cuenta, mueva el correo electrónico a otra ubicación. Si ya ha eliminado la cuenta: si hace menos de 30 días puede restaurarla, mover los datos del correo y eliminarla. Vea cómo [acceder a los datos de un antiguo usuario y realizar copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md).
- Si tiene una suscripción Enterprise como Office 365 Enterprise E3, puede conservar los datos de buzón de una cuenta de usuario eliminada convirtiéndolos en un *buzón inactivo*. Para obtener más información, vea [Administrar buzones inactivos en Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Administrador global: elimine un usuario, deje de pagar su licencia y elija qué hacer con su correo electrónico y OneDrive contenido

Si es un administrador global, al eliminar un usuario también puede conceder a otro usuario acceso a su correo electrónico y elegir qué hacer con su contenido OneDrive.

### <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

Antes de empezar, piense en lo que quiere hacer con el correo electrónico del usuario y OneDrive contenido, y si desea conservar la licencia o dejar de pagarla.
  
|Elemento | Descripción |
|:-----|:-----|
|Licencias de producto  <br/> |Puede quitar la licencia del usuario y quitarla de las suscripciones para dejar de pagar esa licencia. Si selecciona esta opción, la licencia se quitará automáticamente de las suscripciones.  <br/><br/> **No puede quitar la licencia si la** compró a través de un partner o licencias por volumen. Si paga por un plan anual o si está en medio de un ciclo de facturación, no podrá quitar la licencia de su suscripción hasta que se complete el compromiso.  <br/> |
|OneDrive contenido  <br/> |Si el usuario guardó sus archivos en OneDrive, puede conceder a otro usuario acceso a estos archivos.  <br/><br/> Tendrá que mover los archivos que desea conservar dentro del período de retención establecido para OneDrive archivos. **De forma predeterminada, el período de retención es de 30 días.** Si no mueve los archivos dentro del período de retención después de eliminar al usuario, el OneDrive para el usuario eliminado se mueve a la papelera de reciclaje de la colección de sitios, donde se mantiene durante 93 días. Durante este tiempo, los usuarios ya no podrán acceder a ningún contenido compartido de la OneDrive. Para restaurar el OneDrive, debe usar PowerShell. Para obtener información, consulte [Restauración de un OneDrive eliminado](/onedrive/restore-deleted-onedrive).<br/><br/> Para aumentar el número de días que conserva OneDrive archivos para las cuentas eliminadas, consulte [Establecer la retención de OneDrive para los usuarios eliminados](/onedrive/set-retention).  <br/><br/> **¡Importante!** Si el usuario eliminado usó un equipo personal para descargar archivos de SharePoint y OneDrive, no hay ninguna manera de borrar los archivos almacenados en su equipo. Seguirán teniendo acceso a los archivos que se sincronizaron desde OneDrive.           |
|Correo electrónico  <br/> | Dar a otro usuario acceso al correo electrónico del usuario eliminado convertirá el buzón del usuario eliminado en un buzón compartido. A continuación, el nuevo propietario del buzón puede acceder al buzón y supervisar el nuevo correo electrónico. También tendrá las siguientes opciones:  <br/>  <br/>Cambiar el nombre para mostrar: se recomienda cambiar el nombre para mostrar para que sea fácil identificar el buzón compartido en la lista **Usuarios activos** .  <br/>  <br/>  Activar respuestas automáticas: ya hemos escrito una respuesta automática educada para usted. Puede enviar diferentes respuestas automáticas a personas de su organización y personas de fuera de la organización. <br/> <br/> [Quite los permisos de calendario existentes](/powershell/module/exchange/remove-mailboxfolderpermission?view=exchange-ps) mediante PowerShell. <br/> <br/> Limpieza de alias: los alias son direcciones de correo electrónico adicionales para los usuarios. Algunas organizaciones no las usan, por lo que, si no tiene ninguna, no es necesario hacer nada más aquí. Si el usuario tiene alias, se recomienda quitarlos para que pueda reutilizar esas direcciones de correo electrónico. De lo contrario, no puede reutilizar esas direcciones de correo electrónico hasta que haya pasado el período de retención de los buzones eliminados. De forma predeterminada, un buzón eliminado se puede recuperar durante 30 días. Para obtener más información, vea [Eliminar o restaurar buzones de usuario en Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |Si su empresa usa **Active Directory** que está sincronizando con Azure AD, debe eliminar la cuenta de usuario de Active Directory. No podrá hacerlo a través de Office 365. Para obtener instrucciones, consulte [Eliminación de una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).  <br/> |

### <a name="get-started"></a>Comenzar

Dado que la experiencia guiada recorre los pasos para eliminar un usuario, aquí se muestra cómo empezar.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione el usuario que desea eliminar y, a continuación, seleccione **Eliminar usuario**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Administrador de administración de usuarios: elimine uno o varios usuarios de Office 365

> [!IMPORTANT]
> No elimine la cuenta de un usuario si [la ha convertido en un buzón compartido](../email/convert-user-mailbox-to-shared-mailbox.md) o si ha configurado el reenvío de correo electrónico en la cuenta. Esas funciones siguen necesitando la cuenta. Un buzón compartido no requiere una licencia. Si ha convertido la cuenta en un buzón compartido, puede [dejar de pagar por la licencia](#stop-paying-for-the-license). Si ha configurado el reenvío de correo electrónico en la cuenta, no puede quitar la licencia. Al hacerlo, se detendrá el reenvío de correo electrónico y se desactivará el buzón.
  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione los nombres de los usuarios que desea eliminar, seleccione los tres puntos (más acciones) y, a continuación, elija  **Eliminar usuario**.

   Aunque eliminó la cuenta del usuario, **sigue pagando por la licencia**. Consulte el siguiente procedimiento para dejar de pagar la licencia.  O bien, puede asignar la licencia a otro usuario. No se asignará automáticamente a alguien.

### <a name="stop-paying-for-the-license"></a>Dejar de pagar por la licencia

Reducir el número de licencias es un paso independiente que solo puede realizar el administrador global o el administrador de facturación.
  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Sus productos</a>.
::: moniker-end

2. En la pestaña **Productos** , seleccione la suscripción para la que desea quitar licencias.

3. En la página de detalles de la suscripción, seleccione **Quitar licencias**.

4. En el panel **Quitar licencias** , en **Nueva cantidad**, en el cuadro **Total de licencias** , escriba el número total de licencias que desea para esta suscripción. Por ejemplo, si tiene 100 licencias y quiere quitar cinco de ellas, escriba 95.

5. Seleccione **Guardar**.

Más adelante, cuando siga los pasos para agregar otra persona a su negocio, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.

## <a name="delete-many-users-at-the-same-time"></a>Eliminar muchos usuarios al mismo tiempo

Consulte el cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) de PowerShell.

## <a name="fix-issues-with-deleting-a-user"></a>Corregir problemas relacionados con la eliminación de un usuario

Estos son los problemas más comunes que los usuarios encuentran al eliminar un usuario:
  
- **Recibe un mensaje de error similar a "No se puede eliminar el usuario. Inténtelo de nuevo más tarde".** Compruebe si la cuenta tiene configurado el reenvío de correo electrónico o si se ha convertido en un buzón compartido. Ambas opciones causarán dicho error. No elimine la cuenta si tiene reenvío de correo electrónico o si se ha convertido en un buzón compartido.

- **No tiene los permisos adecuados para eliminar un usuario**. Solo las personas que son [Microsoft 365 administradores globales o administradores de administración de](about-admin-roles.md) usuarios pueden eliminar usuarios. Normalmente se trata del soporte técnico de su escuela o empresa.

- **Ha eliminado el usuario, pero el nombre todavía aparece en la libreta de direcciones global**. Esto ocurre cuando una empresa usa Active Directory. Debe eliminar la cuenta de usuarios de Active Directory. Para obtener instrucciones, consulte [Eliminación de una cuenta de usuario.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**¿Desea eliminar Microsoft 365 del equipo? Vaya a [Cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md).**

## <a name="related-content"></a>Contenido relacionado

[Restauración de un usuario](restore-user.md) (artículo)\
[Eliminar permanentemente un buzón](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (artículo)\
[Eliminación de un antiguo empleado de Office 365](remove-former-employee.md) (artículo)\
[Agregar un nuevo empleado a Office 365](add-new-employee.md) (artículo)\
[Eliminar una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): use estas instrucciones si su empresa usa **Active Directory** que se sincroniza con Azure AD. No podrá hacerlo a través de Office 365. (artículo)
