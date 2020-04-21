---
title: Elimine un usuario de su organización
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Obtenga información sobre cómo eliminar una cuenta de usuario. Decida qué hacer con el correo electrónico del usuario, el contenido de OneDrive y si quiere mantener la licencia del producto o dejar de pagar por él.
ms.openlocfilehash: 1d529627841c648684c8a9fe217a761b29749150
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617253"
---
# <a name="delete-a-user-from-your-organization"></a>Elimine un usuario de su organización
  
||
|:-----|
|**¿Busca cómo eliminar su *propia* cuenta de usuario de Microsoft 365 que usa en el trabajo o en la escuela? Póngase en contacto con el soporte técnico en su trabajo o Universidad para realizar estos pasos.**|
   
## <a name="what-you-need-to-know-about-deleting-users"></a>Información importante acerca de cómo eliminar usuarios

- Solo las personas que tienen permisos de [administrador global de Microsoft 365](about-admin-roles.md) o de administración de usuarios para la empresa o el centro educativo pueden eliminar cuentas de usuario. 
    
- Tiene 30 días para [restaurar](restore-user.md) la cuenta antes de que los datos del usuario se eliminen de forma permanente. 
    
- Si desea conservar los datos del usuario de OneDrive, muévalos a otra ubicación. Incluso puede hacerlo hasta 30 días después de eliminar la cuenta. Vea [Acceder a los datos de usuario antiguos y realizar una copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md). No es necesario mover sus archivos de SharePoint, pues seguirá teniendo acceso a ellos.
    
- Si desea mantener el correo electrónico del usuario, **ANTES** de eliminar la cuenta, mueva el correo electrónico a otra ubicación. Si ya ha eliminado la cuenta: si hace menos de 30 días puede restaurarla, mover los datos del correo y eliminarla. Vea cómo [acceder a los datos de un antiguo usuario y realizar copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md).
    
- Si tiene una suscripción de Enterprise como Office 365 Enterprise E3, puede conservar los datos de buzón de una cuenta de usuario eliminada convirtiéndola en un *buzón inactivo*. Para obtener más información, vea [Administrar buzones inactivos en Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Administrador global: eliminar un usuario, dejar de pagar por su licencia y elegir qué hacer con el correo electrónico y el contenido de OneDrive

Si es un administrador global, al eliminar un usuario, también puede conceder a otro usuario acceso a su correo electrónico y elegir qué hacer con su contenido de OneDrive. 

  
### <a name="things-to-consider"></a>Aspectos que se deben tener en cuenta...

Antes de empezar, piense en lo que desea hacer con el correo electrónico del usuario y en el contenido de OneDrive, y si desea mantener la licencia o dejar de pagar por ella.
  
|||
|:-----|:-----|
|Licencias de producto  <br/> |Puede quitar la licencia del usuario y quitarla de sus suscripciones para dejar de pagar por esa licencia. Si selecciona esta opción, la licencia se quitará automáticamente de sus suscripciones.  <br/><br/> **No puede quitar la licencia si la** compró a través de un partner o un licencia por volumen. Si va a pagar por un plan anual o si se encuentra en medio de un ciclo de facturación, no podrá quitar la licencia de la suscripción hasta que se complete el compromiso.  <br/> |
|Contenido de OneDrive  <br/> |Si el usuario guardó sus archivos en OneDrive, puede conceder a otro usuario acceso a estos archivos.  <br/><br/> Deberá mover los archivos que quiera conservar dentro del período de retención establecido para los archivos de OneDrive. **De forma predeterminada, el período de retención es de 30 días.** Si no mueve los archivos dentro del período de retención después de eliminar el usuario, el contenido de OneDrive se eliminará permanentemente. Para aumentar el número de días que se conservan los archivos de OneDrive para las cuentas eliminadas, consulte [Set the onedrive Retention for Deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).  <br/><br/> **¡Importante!** Si el usuario eliminado usó un equipo personal para descargar archivos de SharePoint y OneDrive, no hay forma de borrar los archivos almacenados en el equipo. Seguirán teniendo acceso a todos los archivos que se hayan sincronizado desde OneDrive.           |
|Correo electrónico  <br/> | Al conceder a otro usuario acceso al correo electrónico del usuario eliminado, se convertirá el buzón del usuario eliminado en un buzón compartido. El nuevo propietario del buzón puede tener acceso al buzón y supervisar el correo electrónico nuevo. También tendrá las siguientes opciones:  <br/>  <br/>Cambiar el nombre para mostrar: se recomienda cambiar el nombre para mostrar para que sea fácil identificar el buzón compartido en la lista de usuarios activos.  <br/>  Activar respuestas automáticas: ya hemos escrito una respuesta automática de un educado por usted. Puede enviar respuestas automáticas diferentes a personas de su organización y personas que no pertenezcan a su organización.  <br/> <br/> Limpiar alias: los alias son direcciones de correo electrónico adicionales para los usuarios. Algunas organizaciones no las usan, por lo que, si no tiene ninguno, no es necesario que realice ninguna otra acción. Si el usuario tiene alias, le recomendamos que los quite para que pueda volver a usar esas direcciones de correo electrónico. De lo contrario, no podrá volver a usar esas direcciones de correo electrónico hasta que transcurra el período de retención para los buzones eliminados. De forma predeterminada, un buzón eliminado es recuperable durante 30 días. Para obtener más información, vea [eliminar o restaurar buzones de usuario en Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |Si su empresa usa **Active Directory** que está sincronizando con Azure AD, debe eliminar la cuenta de usuario de Active Directory. No podrá hacerlo a través de Office 365. Para obtener instrucciones, consulte [eliminar una cuenta de usuario](https://go.microsoft.com/fwlink/p/?linkid=841808).  <br/> |
   
### <a name="get-started"></a>Introducción

::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

::: moniker-end

Dado que la experiencia guiada recorre los pasos para eliminar un usuario, esta es la manera de empezar.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione el usuario que desea eliminar y, a continuación, seleccione **eliminar usuario**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Administrador de administración de usuarios: eliminar uno o más usuarios de Office 365


> [!IMPORTANT]
> No elimine una cuenta de usuario si la ha [convertido en un buzón compartido](../email/convert-user-mailbox-to-shared-mailbox.md) o si ha configurado el reenvío de correo electrónico en la cuenta. Estas funciones todavía necesitan la cuenta. Un buzón compartido no requiere una licencia. Si ha convertido la cuenta en un buzón compartido, puede [dejar de pagar por la licencia](#stop-paying-for-the-license). Si ha configurado el reenvío de correo electrónico en la cuenta, no podrá quitar la licencia. Al hacerlo, se detendrá el reenvío de correo y se desactivará el buzón.
  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  

2. Seleccione los nombres de los usuarios que desea eliminar, seleccione **más opciones** (**...**) y, a continuación, elija **eliminar usuario**.

   Aunque eliminó la cuenta del usuario, **aún está pagando por la licencia**. Consulte el siguiente procedimiento para dejar de pagar por la licencia.  O bien, puede asignar la licencia a otro usuario. No se asignará a nadie automáticamente.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione los nombres de los usuarios que desea eliminar y, en el panel **acciones en masa** , elija **eliminar usuarios**.

   Aunque eliminó la cuenta del usuario, **aún está pagando por la licencia**. Consulte el siguiente procedimiento para dejar de pagar por la licencia.  O bien, puede asignar la licencia a otro usuario. No se asignará a nadie automáticamente.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione los nombres de los usuarios que desea eliminar y, en el panel **acciones en masa** , elija **eliminar usuarios**.

   Aunque eliminó la cuenta del usuario, **aún está pagando por la licencia**. Consulte el siguiente procedimiento para dejar de pagar por la licencia.  O bien, puede asignar la licencia a otro usuario. No se asignará a nadie automáticamente.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Dejar de pagar por la licencia

La reducción del número de licencias es un paso independiente que solo puede realizar el administrador global o el administrador de facturación. 
  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Productos y servicios</a>. Si no ve esta opción, no es un administrador global o administrador de facturación y no puede realizar este paso.

2. Seleccione la suscripción (si tiene más de una) y, a continuación, seleccione **Agregar o quitar licencias** para eliminar la licencia y no pagar por ella hasta que contrate a otra persona.  

   Más adelante, cuando siga los pasos para agregar a otra persona a su empresa, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Suscripciones</a>. Si no ve esta opción, no es un administrador global o administrador de facturación y no puede realizar este paso.

2. Seleccione la suscripción (si tiene más de una) y, a continuación, seleccione **Agregar o quitar licencias** para eliminar la licencia y no pagar por ella hasta que contrate a otra persona.  

   Más adelante, cuando siga los pasos para agregar a otra persona a su empresa, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>. Si no ve esta opción, no es un administrador global o administrador de facturación y no puede realizar este paso.

2. Seleccione la suscripción (si tiene más de una) y, a continuación, seleccione **Agregar o quitar licencias** para eliminar la licencia y no pagar por ella hasta que contrate a otra persona.  

   Más adelante, cuando siga los pasos para agregar a otra persona a su empresa, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a>Eliminar varios usuarios al mismo tiempo

Consulte el cmdlet [de PowerShell Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) .

## <a name="fix-issues-with-deleting-a-user"></a>Corregir problemas relacionados con la eliminación de un usuario

Estos son los problemas más comunes que se encuentran los usuarios al eliminar un usuario:
  
- **Recibe un mensaje de error similar a "No se puede eliminar el usuario. Inténtelo de nuevo más tarde".** Compruebe de nuevo si se ha establecido una regla de reenvío de correo en la cuenta o si esta se convertido en un buzón compartido. Ambas opciones causarán dicho error. No elimine la cuenta si tiene un reenvío de correo electrónico o se ha convertido en un buzón compartido.

- **No tiene los permisos adecuados para eliminar un usuario**. Solo los usuarios que son [administradores globales de Microsoft 365 o administradores de administración de usuarios](about-admin-roles.md) pueden eliminar usuarios. Normalmente se trata del soporte técnico de su escuela o empresa.

- **Ha eliminado el usuario, pero el nombre todavía aparece en la libreta de direcciones global**. Esto ocurre cuando una empresa usa Active Directory. Debe eliminar la cuenta del usuario de Active Directory. Para obtener instrucciones, consulte este artículo de TechNet: [Eliminar una cuenta de usuario.](https://go.microsoft.com/fwlink/p/?linkid=841808)

||
|:-----|
|**¿Desea eliminar Microsoft 365 del equipo? Vaya a [cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md).**|
   
## <a name="related-articles"></a>Artículos relacionados

[Restaurar un usuario](restore-user.md)
  
[Eliminar un buzón de forma permanente](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Quitar un antiguo empleado de Office 365](remove-former-employee.md)

[Agregar un nuevo empleado a Office 365](add-new-employee.md)

[Eliminar una cuenta de usuario](https://go.microsoft.com/fwlink/p/?linkid=841808): siga estas instrucciones si su empresa usa **Active** Directory que se está sincronizando con Azure ad. No podrá hacerlo a través de Office 365.