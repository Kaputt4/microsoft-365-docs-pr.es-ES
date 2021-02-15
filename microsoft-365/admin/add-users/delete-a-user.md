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
description: Obtenga información sobre cómo eliminar una cuenta de usuario. Decida qué hacer con el correo electrónico del usuario y el contenido de OneDrive. Y decide si quieres mantener la licencia del producto o dejar de pagar por ella.
ms.openlocfilehash: 45cf8b9173a3a4260fe664b809f47ab14b57d9fe
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551381"
---
# <a name="delete-a-user-from-your-organization"></a>Elimine un usuario de su organización
  
**¿Está buscando cómo eliminar su *propia cuenta* de usuario de Microsoft 365 que usa en el trabajo o en la escuela? Póngase en contacto con el soporte técnico de su trabajo o universidad para realizar estos pasos por usted.**

## <a name="what-you-need-to-know-about-deleting-users"></a>Información importante acerca de cómo eliminar usuarios

- Solo las personas que tengan permisos de administrador global o de administración de usuarios de [Microsoft 365](about-admin-roles.md) para la empresa o escuela pueden eliminar cuentas de usuario.
- Tiene 30 días para [restaurar](restore-user.md) la cuenta antes de que los datos del usuario se eliminen de forma permanente.
- Si desea conservar los datos del usuario de OneDrive, muévalos a otra ubicación. Incluso puede mover los datos hasta 30 días después de eliminar la cuenta. Vea [Acceder a los datos de usuario antiguos y realizar una copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md). No es necesario mover sus archivos de SharePoint, pues seguirá teniendo acceso a ellos.
- Si desea mantener el correo electrónico del usuario, **ANTES** de eliminar la cuenta, mueva el correo electrónico a otra ubicación. Si ya ha eliminado la cuenta: si hace menos de 30 días puede restaurarla, mover los datos del correo y eliminarla. Vea cómo [acceder a los datos de un antiguo usuario y realizar copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md).
- Si tiene una suscripción Enterprise como Office 365 Enterprise E3, puede conservar los datos del buzón de una cuenta de usuario eliminada convirtiéndola en un *buzón inactivo.* Para obtener más información, vea [Administrar buzones inactivos en Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Administrador global: eliminar un usuario, dejar de pagar por su licencia y elegir qué hacer con el correo electrónico y el contenido de OneDrive

Si es un administrador global, al eliminar un usuario también puede dar a otro usuario acceso a su correo electrónico y elegir qué hacer con su contenido de OneDrive.

### <a name="things-to-consider"></a>Aspectos que se deben tener en cuenta...

Antes de empezar, piense en lo que quiere hacer con el correo electrónico del usuario y el contenido de OneDrive, y si desea mantener la licencia o dejar de pagar por ella.
  
|Elemento | Description |
|:-----|:-----|
|Licencias de productos  <br/> |Puedes quitar la licencia del usuario y quitarla de tus suscripciones para dejar de pagar por esa licencia. Si seleccionas esta opción, la licencia se quitará automáticamente de las suscripciones.  <br/><br/> **No puedes quitar la licencia si** la compraste a través de un partner o una licencia por volumen. Si paga un plan anual o si está en medio de un ciclo de facturación, no podrá quitar la licencia de su suscripción hasta que se complete su compromiso.  <br/> |
|Contenido de OneDrive  <br/> |Si el usuario guardó sus archivos en OneDrive, puede dar a otro usuario acceso a estos archivos.  <br/><br/> Deberá mover los archivos que desea conservar dentro del período de retención establecido para los archivos de OneDrive. **De forma predeterminada, el período de retención es de 30 días.** Si no mueve los archivos dentro del período de retención después de eliminar el usuario, el contenido de OneDrive se eliminará permanentemente. Para aumentar el número de días que conserva los archivos de OneDrive para las cuentas eliminadas, vea Establecer la retención de [OneDrive para los usuarios eliminados.](https://docs.microsoft.com/onedrive/set-retention)  <br/><br/> **¡Importante!** Si el usuario eliminado usó un equipo personal para descargar archivos de SharePoint y OneDrive, no hay forma de borrar los archivos almacenados en su equipo. Seguirán teniendo acceso a los archivos sincronizados desde OneDrive.           |
|Correo electrónico  <br/> | Si se da acceso a otro usuario al correo electrónico del usuario eliminado, el buzón del usuario eliminado se convertirá en un buzón compartido. A continuación, el nuevo propietario del buzón puede acceder al buzón y supervisar el correo electrónico nuevo. También tendrá las siguientes opciones:  <br/>  <br/>Cambiar el nombre para mostrar: se recomienda cambiar el nombre para mostrar para que sea fácil identificar el buzón compartido en la **lista de usuarios activos.**  <br/>  Activar las respuestas automáticas: ya hemos escrito una respuesta automática educada. Puede enviar diferentes respuestas automáticas a personas dentro de su organización y a personas de fuera de la organización.  <br/> <br/> Limpiar alias: los alias son direcciones de correo electrónico adicionales para los usuarios. Algunas organizaciones no las usan, por lo que si no tiene ninguna, no necesita hacer nada más aquí. Si el usuario tiene alias, se recomienda quitarlos para que pueda reutilizar esas direcciones de correo electrónico. De lo contrario, no podrá volver a usar esas direcciones de correo electrónico hasta que haya transcurrido el período de retención de los buzones eliminados. De forma predeterminada, un buzón eliminado se puede recuperar durante 30 días. Para obtener más información, vea [Eliminar o restaurar buzones de usuario en Exchange Online.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) <br/> |
|Active Directory  <br/> |Si su empresa usa **Active Directory** que está sincronizando con Azure AD, debe eliminar la cuenta de usuario de Active Directory. No podrá hacerlo a través de Office 365. Para obtener instrucciones, [vea Eliminar una cuenta de usuario.](https://go.microsoft.com/fwlink/p/?linkid=841808)  <br/> |

### <a name="get-started"></a>Introducción

Dado que la experiencia guiada le guiará por los pasos para eliminar un usuario, aquí se muestra cómo empezar.

::: moniker range="o365-worldwide"
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
::: moniker-end

::: moniker range="o365-germany"
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.
::: moniker-end

::: moniker range="o365-21vianet"
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.
::: moniker-end

2. Seleccione el usuario que desea eliminar y, a continuación, **seleccione Eliminar usuario.**

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Administrador de administración de usuarios: eliminar uno o más usuarios de Office 365

> [!IMPORTANT]
> No elimine la cuenta de un usuario si la ha convertido [en](../email/convert-user-mailbox-to-shared-mailbox.md) un buzón compartido o si ha configurado el reenvío de correo electrónico en la cuenta. Esas funciones aún necesitan la cuenta. Un buzón compartido no requiere una licencia. Si ha convertido la cuenta en un buzón compartido, puede [dejar de pagar por la licencia.](#stop-paying-for-the-license) Si ha configurado el reenvío de correo electrónico en la cuenta, no puede quitar la licencia. Si lo hace, se detendrá el reenvío de correo electrónico y se desactivará el buzón.
  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  

2. Seleccione los nombres de los usuarios que desea eliminar, seleccione **Más opciones** (**...**) y, a continuación, elija  **Eliminar usuario**.

   Aunque eliminó la cuenta del usuario, sigue pagando **por la licencia.** Vea el siguiente procedimiento para dejar de pagar por la licencia.  O bien, puede asignar la licencia a otro usuario. No se asignará a nadie automáticamente.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione los nombres de los usuarios que desea  eliminar y, en el panel acciones masivas, elija **Eliminar usuarios.**

   Aunque eliminó la cuenta del usuario, sigue pagando **por la licencia.** Vea el siguiente procedimiento para dejar de pagar por la licencia.  O bien, puede asignar la licencia a otro usuario. No se asignará a nadie automáticamente.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione los nombres de los usuarios que desea  eliminar y, en el panel acciones masivas, elija **Eliminar usuarios.**

   Aunque eliminó la cuenta del usuario, sigue pagando **por la licencia.** Vea el siguiente procedimiento para dejar de pagar por la licencia.  O bien, puede asignar la licencia a otro usuario. No se asignará a nadie automáticamente.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Dejar de pagar por la licencia

Reducir el número de licencias es un paso independiente que solo puede realizar el administrador global o el administrador de facturación.
  
::: moniker range="o365-worldwide"

1. En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>. Si no ve esta opción, no es administrador global ni administrador de facturación y no puede realizar este paso.

2. En la **pestaña** Productos, seleccione la suscripción para la que desea quitar licencias.

3. En la página de detalles de la suscripción, **seleccione Quitar licencias.**

4. En el **panel Quitar licencias,** en Nueva  **cantidad,** en el cuadro Total de licencias, escriba el número total de licencias que desea para esta suscripción. Por ejemplo, si tiene 100 licencias y desea quitar cinco de ellas, escriba 95.

5. Seleccione **Guardar**.

Más adelante, cuando sigas los pasos para agregar otra persona a tu empresa, se te pedirá que compres una licencia al mismo tiempo, con solo un paso.

::: moniker-end

::: moniker range="o365-germany"

1. En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Suscripciones</a>. Si no ve esta opción, no es administrador global ni administrador de facturación y no puede realizar este paso.

2. Seleccione la suscripción (si tiene más de  una) y, a continuación, seleccione Agregar o quitar licencias para eliminar la licencia para que no la pague hasta que contrate a otra persona.  

   Más adelante, cuando sigas los pasos para agregar otra persona a tu empresa, se te pedirá que compres una licencia al mismo tiempo, con solo un paso.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>. Si no ve esta opción, no es administrador global ni administrador de facturación y no puede realizar este paso.

2. Seleccione la suscripción (si tiene más de  una) y, a continuación, seleccione Agregar o quitar licencias para eliminar la licencia para que no la pague hasta que contrate a otra persona.  

   Más adelante, cuando sigas los pasos para agregar otra persona a tu empresa, se te pedirá que compres una licencia al mismo tiempo, con solo un paso.

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a>Eliminar muchos usuarios al mismo tiempo

Consulte el cmdlet [remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) de PowerShell.

## <a name="fix-issues-with-deleting-a-user"></a>Corregir problemas relacionados con la eliminación de un usuario

Estos son los problemas más comunes que los usuarios encuentran al eliminar un usuario:
  
- **Recibe un mensaje de error similar a "No se puede eliminar el usuario. Inténtelo de nuevo más tarde".** Compruebe de nuevo si la cuenta tiene configurado el reenvío de correo electrónico o si se ha convertido en un buzón compartido. Ambas opciones causarán dicho error. No elimine la cuenta si tiene reenvío de correo electrónico o si se ha convertido en un buzón compartido.

- **No tiene los permisos adecuados para eliminar un usuario**. Solo las personas que son administradores [globales de Microsoft 365 o](about-admin-roles.md) administradores de administración de usuarios pueden eliminar usuarios. Normalmente se trata del soporte técnico de su escuela o empresa.

- **Ha eliminado el usuario, pero el nombre todavía aparece en la libreta de direcciones global**. Esto ocurre cuando una empresa usa Active Directory. Debe eliminar la cuenta de usuario de Active Directory. Para obtener instrucciones, consulte [Eliminar una cuenta de usuario.](https://go.microsoft.com/fwlink/p/?linkid=841808)

**¿Desea eliminar Microsoft 365 de su equipo? Vaya a [Cancelar la suscripción.](../../commerce/subscriptions/cancel-your-subscription.md)**

## <a name="related-articles"></a>Artículos relacionados

[Restaurar un usuario](restore-user.md)
  
[Eliminar un buzón de forma permanente](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Quitar un antiguo empleado de Office 365](remove-former-employee.md)

[Agregar un nuevo empleado a Office 365](add-new-employee.md)

[Eliminar una cuenta de usuario:](https://go.microsoft.com/fwlink/p/?linkid=841808)siga estas instrucciones si su empresa usa **Active Directory** que se sincroniza con Azure AD. No podrá hacerlo a través de Office 365.