---
title: Convertir un buzón de usuario en un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Aprenda a convertir un buzón privado en un buzón compartido al que pueden acceder varias personas en lugar de una sola persona. '
ms.openlocfilehash: 1cc60feb7729d2ad57749b58bc246b3478fcf342
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68187281"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Convertir un buzón de usuario en un buzón compartido

Al convertir el buzón de un usuario en un buzón compartido, se conserva todo el correo electrónico y el calendario existentes. Solo ahora está en un buzón compartido donde varias personas podrán acceder a él en lugar de a una persona. En una fecha posterior, puede volver a convertir un buzón compartido en un buzón de usuario (privado).

> [!TIP]
> Si necesita ayuda con los pasos que se describen en este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="before-you-begin"></a>Antes de empezar

**Estas son algunas cosas realmente importantes que necesita saber**:

- El buzón de usuario necesita una licencia asignada antes de convertirlo en un buzón compartido. De lo contrario, no verá la opción para convertir el buzón. Si ha quitado la licencia, vuelva a agregarla para que pueda convertir el buzón. Después de convertir el buzón de usuario en un buzón compartido, puede quitar la licencia de la cuenta del usuario.

- Sin una licencia, los buzones compartidos están limitados a 50 GB. Es posible que tenga que eliminar un montón de mensajes grandes (por ejemplo, mensajes con datos adjuntos) del buzón compartido para reducirlo para que pueda quitar la licencia.

  Para aumentar el límite de tamaño a 100 GB, asigne una licencia Exchange Online plan 2 al buzón compartido.

  Si asigna una licencia Exchange Online plan 1 y una licencia de complemento de Archivado de Exchange Online al buzón compartido, puede habilitar el archivado de expansión automática para una capacidad de almacenamiento de archivo adicional.

- No elimine la cuenta del usuario anterior, ya que la cuenta es necesaria para delimitar el buzón compartido. Si ya ha eliminado la cuenta de usuario, consulte [Conversión del buzón de correo de un usuario eliminado](#convert-the-mailbox-of-a-deleted-user).

- No es necesario restablecer la contraseña de la cuenta del buzón de usuario. Sin embargo, si no restablece la contraseña, **el nombre de usuario y la contraseña originales seguirán funcionando en el buzón compartido** una vez finalizada la conversión.

- Las reglas de bandeja de entrada se conservan después de que el buzón de usuario se convierta en un buzón compartido.

- Para colocar una suspensión de In-Place o una suspensión por juicio en un buzón compartido, debe asignar una licencia de Exchange Online Plan 2 *o* una licencia del plan 1 de Exchange Online y una licencia de complemento de Archivado de Exchange Online al buzón compartido.

## <a name="use-the-classic-exchange-admin-center-to-convert-a-mailbox"></a>Uso del Centro de administración de Exchange clásico para convertir un buzón

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange clásico</a>.

2. Seleccione **Buzones de destinatarios**\>.

3. Seleccione el buzón de usuario. En **Convertir en buzón compartido**, seleccione **Convertir**.

4. Si el buzón es menor que 50 GB, puede quitar la [licencia del usuario](../manage/remove-licenses-from-users.md) y dejar de pagar por ella. No elimine la cuenta del usuario. El buzón compartido lo necesita allí como delimitador. Si va a convertir el buzón de un empleado que sale de su organización, debe realizar pasos adicionales para asegurarse de que ya no puedan iniciar sesión. Para obtener más información, consulte [Eliminación de un empleado anterior de Microsoft 365](../add-users/remove-former-employee.md).

Para todo lo demás que necesita saber sobre los buzones compartidos, consulte [Acerca de los buzones compartidos](about-shared-mailboxes.md) y [Creación de un buzón compartido](create-a-shared-mailbox.md).

## <a name="use-the-new-exchange-admin-center-to-convert-a-mailbox"></a>Uso del Nuevo Centro de administración de Exchange para convertir un buzón

1. Vaya al <a href="https://admin.exchange.microsoft.com/#/homepage" target="_blank"> Centro de administración de Exchange</a>.

2. Seleccione **Buzones de destinatarios**\>.

3. Seleccione el buzón de usuario. En la pestaña **Otros** , seleccione **Convertir en buzón compartido**.

4. Si el buzón es menor que 50 GB, puede quitar la [licencia del usuario](../manage/remove-licenses-from-users.md) y dejar de pagar por ella. No elimine la cuenta del usuario. El buzón compartido lo necesita allí como delimitador. Si va a convertir el buzón de un empleado que sale de su organización, debe realizar pasos adicionales para asegurarse de que ya no pueden iniciar sesión. Consulte [Eliminación de un empleado anterior de Microsoft 365](../add-users/remove-former-employee.md).

Para todo lo demás que necesita saber sobre los buzones compartidos, consulte [Acerca de los buzones compartidos](about-shared-mailboxes.md) y [Creación de un buzón compartido](create-a-shared-mailbox.md).

## <a name="convert-the-mailbox-of-a-deleted-user"></a>Convertir el buzón de un usuario eliminado

Después de eliminar una cuenta de usuario, siga estos pasos para convertir su buzón antiguo en un buzón de correo compartido:

1. [Restaure la cuenta del usuario](../add-users/restore-user.md).

2. Asegúrese de que se le asigna una licencia de Microsoft 365.

3. Restablezca la contraseña del usuario.

4. Espere entre 20 y 30 minutos a que se vuelva a crear su buzón.

5. Una vez que se vuelva a crear el buzón de correo, quite la licencia del buzón del usuario. No elimine el buzón antiguo del usuario. El buzón compartido lo necesita allí como delimitador.

6. Agregue miembros al buzón compartido.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Volver a convertir un buzón compartido en el buzón de un usuario (privado)

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

2. Seleccione **Destinatarios compartidos**\>.

3. Seleccione el buzón compartido. En **Convertir en buzón normal**, seleccione **Convertir**.

4. Volver al centro de administración. En **Usuarios**, elija la cuenta de usuario asociada al buzón compartido antiguo. Asigne una licencia a la cuenta y restablezca la contraseña.

   El buzón tardará unos minutos en configurarse, pero después de eso, la persona que va a usar esa cuenta está lista para usarse. Cuando inicien sesión, verán los elementos de correo electrónico y calendario que solían estar en el buzón compartido.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Convertir el buzón de un usuario en un entorno híbrido

Para obtener más información sobre cómo convertir un buzón de usuario en un buzón compartido en un entorno híbrido de Exchange, consulte:

- [Cmdlets para crear o modificar un buzón compartido remoto en un entorno de Exchange local](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
- [Los buzones compartidos se convierten inesperadamente en buzones de usuario después de que se ejecute la sincronización de directorios en una implementación híbrida de Exchange](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)

> [!NOTE]
> Si es miembro del grupo de roles Administración de la organización o Administración de destinatarios, puede usar el Shell de administración de Exchange para cambiar un buzón de usuario a un buzón compartido local. Por ejemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)
