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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Obtenga información sobre cómo eliminar una cuenta de usuario y qué hacer con el correo electrónico del usuario y OneDrive contenido y si desea conservar la licencia del producto.
ms.openlocfilehash: 43a57a69ce0d810af2b029f49c15d32d75a4dc33
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683144"
---
# <a name="delete-a-user-from-your-organization"></a>Elimine un usuario de su organización
  
**¿Está buscando cómo eliminar su propia cuenta *Microsoft 365* usuario que usa en el trabajo o en la escuela? Póngase en contacto con el soporte técnico de su trabajo o universidad para realizar estos pasos por usted.**

## <a name="before-you-begin"></a>Antes de empezar

- Solo las personas que [tienen Microsoft 365 administrador global](about-admin-roles.md) o permisos de administración de usuarios para la empresa o la escuela pueden eliminar cuentas de usuario.
- Tiene 30 días para [restaurar](restore-user.md) la cuenta antes de que los datos del usuario se eliminen de forma permanente.
- Si desea conservar los datos del usuario de OneDrive, muévalos a otra ubicación. Incluso puede mover los datos hasta 30 días después de eliminar la cuenta. Vea [Acceder a los datos de usuario antiguos y realizar una copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md). No es necesario mover sus archivos de SharePoint, pues seguirá teniendo acceso a ellos.
- Si desea mantener el correo electrónico del usuario, **ANTES** de eliminar la cuenta, mueva el correo electrónico a otra ubicación. Si ya ha eliminado la cuenta: si hace menos de 30 días puede restaurarla, mover los datos del correo y eliminarla. Vea cómo [acceder a los datos de un antiguo usuario y realizar copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md).
- Si tiene una suscripción Enterprise como Office 365 Enterprise E3, puede conservar los datos del buzón de una cuenta de usuario eliminada convirtiéndolo en un buzón *inactivo.* Para obtener más información, vea [Administrar buzones inactivos en Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Administrador global: elimine un usuario, deje de pagar por su licencia y elija qué hacer con su correo electrónico y OneDrive contenido

Si es un administrador global, al eliminar un usuario también puede dar a otro usuario acceso a su correo electrónico y elegir qué hacer con su contenido OneDrive usuario.

### <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

Antes de empezar, piense en lo que desea hacer con el correo electrónico del usuario y el contenido OneDrive, y si desea mantener la licencia o dejar de pagar por ella.
  
|Elemento | Descripción |
|:-----|:-----|
|Licencias de productos  <br/> |Puede quitar la licencia del usuario y quitarla de sus suscripciones para dejar de pagar por esa licencia. Si selecciona esta opción, la licencia se quitará automáticamente de las suscripciones.  <br/><br/> **No puede quitar la licencia si** la compró a través de un partner o una licencia por volumen. Si estás pagando un plan anual o si estás en medio de un ciclo de facturación, no podrás quitar la licencia de la suscripción hasta que se complete el compromiso.  <br/> |
|OneDrive contenido  <br/> |Si el usuario guardó sus archivos en OneDrive, puede proporcionar a otro usuario acceso a estos archivos.  <br/><br/> Tendrás que mover los archivos que quieras conservar dentro del período de retención que se establece para los OneDrive archivos. **De forma predeterminada, el período de retención es de 30 días.** Si no mueve los archivos dentro del período de retención después de eliminar el usuario, el contenido OneDrive se eliminará permanentemente. Para aumentar el número de días que conserva los archivos OneDrive para cuentas eliminadas, vea [Set the OneDrive retention for deleted users](/onedrive/set-retention).  <br/><br/> **¡Importante!** Si el usuario eliminado usó un equipo personal para descargar archivos de SharePoint y OneDrive, no hay forma de borrar los archivos que almacenaban en su equipo. Seguirán teniendo acceso a los archivos que se sincronizaron desde OneDrive.           |
|Correo electrónico  <br/> | Si otro usuario tiene acceso al correo electrónico del usuario eliminado, se convertirá el buzón del usuario eliminado en un buzón compartido. A continuación, el nuevo propietario del buzón puede tener acceso al buzón y supervisar el nuevo correo electrónico. También tendrá las siguientes opciones:  <br/>  <br/>Cambiar el nombre para mostrar: se recomienda cambiar el nombre para mostrar para que sea fácil identificar el buzón compartido en la **lista Usuarios** activos.  <br/>  Activar las respuestas automáticas: ya hemos escrito una respuesta automática educada. Puede enviar diferentes respuestas automáticas a personas dentro de su organización y a personas de fuera de la organización.  <br/> <br/> Limpiar alias: los alias son direcciones de correo electrónico adicionales para los usuarios. Algunas organizaciones no las usan, por lo que si no tiene ninguna, no necesita hacer nada más aquí. Si el usuario tiene alias, se recomienda eliminarlos para que pueda reutilizar esas direcciones de correo electrónico. De lo contrario, no puede volver a usar esas direcciones de correo electrónico hasta que haya transcurrido el período de retención de los buzones eliminados. De forma predeterminada, un buzón eliminado se puede recuperar durante 30 días. Para obtener más información, vea [Eliminar o restaurar buzones](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)de usuario en Exchange Online . <br/> |
|Active Directory  <br/> |Si su empresa usa **Active Directory** que está sincronizando con Azure AD, debe eliminar la cuenta de usuario de Active Directory. No podrá hacerlo a través de Office 365. Para obtener instrucciones, [vea Eliminar una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).  <br/> |

### <a name="get-started"></a>Introducción

Dado que la experiencia guiada recorre los pasos para eliminar un usuario, aquí le explicamos cómo empezar.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione el usuario que desea eliminar y, a continuación, **seleccione Eliminar usuario**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Administrador de administración de usuarios: elimine uno o más usuarios de Office 365

> [!IMPORTANT]
> No elimine la cuenta de un usuario si la ha convertido [a](../email/convert-user-mailbox-to-shared-mailbox.md) un buzón compartido o si ha configurado el reenvío de correo electrónico en la cuenta. Esas funciones aún necesitan la cuenta. Un buzón compartido no requiere una licencia. Si ha convertido la cuenta en un buzón compartido, puede [dejar de pagar por la licencia](#stop-paying-for-the-license). Si ha configurado el reenvío de correo electrónico en la cuenta, no puede quitar la licencia. Al hacerlo, se detendrá el reenvío de correo electrónico y se desactivará el buzón.
  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione los nombres de los usuarios que desea eliminar, seleccione los tres puntos (más acciones) y, a continuación,  **elija Eliminar usuario**.

   Aunque eliminó la cuenta del usuario, **sigue pagando por la licencia**. Consulte el siguiente procedimiento para dejar de pagar la licencia.  O bien, puede asignar la licencia a otro usuario. No se asignará a alguien automáticamente.

### <a name="stop-paying-for-the-license"></a>Dejar de pagar por la licencia

Reducir el número de licencias es un paso independiente que solo puede realizar el administrador global o el administrador de facturación.
  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Sus productos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Sus productos</a>.
::: moniker-end

2. En la **pestaña Productos,** seleccione la suscripción para la que desea quitar licencias.

3. En la página de detalles de la suscripción, seleccione **Quitar licencias**.

4. En el **panel Quitar licencias,** en Nueva cantidad **,** en el cuadro **Licencias** totales, escriba el número total de licencias que desea para esta suscripción. Por ejemplo, si tiene 100 licencias y desea quitar cinco de ellas, escriba 95.

5. Seleccione **Guardar**.

Más adelante, cuando sigas los pasos para agregar otra persona a tu empresa, se te pedirá que compres una licencia al mismo tiempo, con un solo paso.

## <a name="delete-many-users-at-the-same-time"></a>Eliminar muchos usuarios al mismo tiempo

Consulte el cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell.

## <a name="fix-issues-with-deleting-a-user"></a>Corregir problemas relacionados con la eliminación de un usuario

Estos son los problemas más comunes que los usuarios encuentran al eliminar un usuario:
  
- **Recibe un mensaje de error similar a "No se puede eliminar el usuario. Inténtelo de nuevo más tarde".** Compruebe si la cuenta tiene configurada la reenviamiento de correo electrónico o si se ha convertido en un buzón compartido. Ambas opciones causarán dicho error. No elimine la cuenta si tiene reenvío de correo electrónico o si se ha convertido en un buzón compartido.

- **No tiene los permisos adecuados para eliminar un usuario**. Solo las personas que Microsoft 365 [administradores globales o](about-admin-roles.md) administradores de administración de usuarios pueden eliminar usuarios. Normalmente se trata del soporte técnico de su escuela o empresa.

- **Ha eliminado el usuario, pero el nombre todavía aparece en la libreta de direcciones global**. Esto ocurre cuando una empresa usa Active Directory. Debe eliminar la cuenta de usuarios de Active Directory. Para obtener instrucciones, consulte [Eliminar una cuenta de usuario.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**¿Desea eliminar Microsoft 365 del equipo? Vaya a [Cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md).**

## <a name="related-content"></a>Contenido relacionado

[Restaurar un usuario](restore-user.md) (artículo)\
[Eliminar permanentemente un buzón](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (artículo)\
[Quitar un antiguo empleado de Office 365](remove-former-employee.md) (artículo)\
[Agregar un nuevo empleado a Office 365](add-new-employee.md) (artículo)\
[Eliminar una cuenta de usuario:](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))use estas instrucciones si su empresa usa **Active Directory** que se sincroniza con Azure AD. No podrá hacerlo a través de Office 365. (artículo)