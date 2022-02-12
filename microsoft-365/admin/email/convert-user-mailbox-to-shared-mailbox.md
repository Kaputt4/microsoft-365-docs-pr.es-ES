---
title: Convertir un buzón de usuario en un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
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
description: 'Aprenda a convertir un buzón privado en un buzón compartido al que puedan tener acceso varias personas en lugar de solo una persona. '
ms.openlocfilehash: a1b82d744cc43f8119e9819537467133f2bae17c
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766613"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Convertir un buzón de usuario en un buzón compartido

Al convertir el buzón de un usuario en un buzón compartido, se conserva todo el correo electrónico y el calendario existentes. Solo ahora está en un buzón compartido en el que varias personas podrán tener acceso a él en lugar de una persona. En una fecha posterior, puede volver a convertir un buzón compartido en un buzón de usuario (privado).

> [!TIP]
> Si necesita ayuda con los pasos de este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso diario a los especialistas de pequeñas empresas a medida que crece su negocio, desde la incorporación hasta el uso diario.

## <a name="before-you-begin"></a>Antes de empezar

**Estas son algunas cosas realmente importantes que necesita saber:**

- El buzón de usuario que está convirtiendo necesita una licencia asignada antes de convertirlo en un buzón compartido. De lo contrario, no verá la opción para convertir el buzón. Si ha quitado la licencia, vuelva a agregarla para poder convertir el buzón. Después de convertir el buzón en uno compartido, puede quitar la licencia de la cuenta del usuario.

- Los buzones compartidos pueden tener hasta 50 GB de datos sin una licencia asignada. Para contener más datos que eso, necesita una licencia asignada. Es posible que deba eliminar un montón de correos electrónicos grandes (por ejemplo, los que tienen datos adjuntos) del buzón compartido para reducirlo para poder quitar la licencia.

- No elimine la cuenta del usuario anterior. Eso es necesario para delimitar el buzón compartido. Si ya eliminó la cuenta de usuario, vea [Convertir el buzón de un usuario eliminado](#convert-the-mailbox-of-a-deleted-user).

- Las reglas están intactas después de convertir el buzón en un buzón compartido.

## <a name="use-the-classic-exchange-admin-center-to-convert-a-mailbox"></a>Usar el Centro Exchange administración para convertir un buzón
 
1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración Exchange clásico</a>.

2. Seleccione **Destinatarios Buzones** \> **de correo**.

3. Seleccione el buzón de usuario. En **Convertir a buzón compartido**, **seleccione Convertir**.

4. Si el buzón es inferior a 50 GB, puede quitar la licencia del [](../manage/remove-licenses-from-users.md)usuario y dejar de pagarla. No elimine la cuenta del usuario. El buzón compartido lo necesita allí como delimitador. Si va a convertir el buzón de un empleado que sale de la organización, debe seguir pasos adicionales para asegurarse de que ya no puedan iniciar sesión. Para obtener más información, vea [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> No es necesario restablecer la contraseña del usuario durante la conversión del buzón. Sin embargo, si la contraseña no se restablece, el nombre de usuario y la contraseña **originales siguen funcionando** una vez finalizada la conversión del buzón.

Para todo lo demás que necesita saber acerca de los buzones compartidos, vea [Acerca de](about-shared-mailboxes.md) los buzones compartidos y [Crear un buzón compartido](create-a-shared-mailbox.md).

> [!NOTE]
> Los buzones compartidos no requieren una licencia independiente. Sin embargo, si desea habilitar In-Place Archive o poner una retención de In-Place o una retención por juicio en un buzón compartido, debe asignar una licencia del Plan 1 de Exchange Online con una licencia del Plan 2 Archivado de Exchange Online o Exchange Online al buzón.

## <a name="use-the-new-exchange-admin-center-to-convert-a-mailbox"></a>Usar el Centro de administración Exchange para convertir un buzón

1. Vaya al Centro <a href="https://admin.exchange.microsoft.com/#/homepage" target="_blank"> Exchange administración</a>.

2. Seleccione **Destinatarios Buzones** \> **de correo**.

3. Seleccione el buzón de usuario. En la **pestaña Buzón** de correo, en **Más acciones**, **seleccione Convertir en buzón compartido**.

4. Si el buzón es inferior a 50 GB, puede quitar la licencia del [](../manage/remove-licenses-from-users.md)usuario y dejar de pagarla. No elimine la cuenta del usuario. El buzón compartido lo necesita allí como delimitador. Si va a convertir el buzón de un empleado que abandona la organización, debe seguir pasos adicionales para asegurarse de que ya no puedan iniciar sesión. Consulte [Quitar un antiguo empleado de Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> No es necesario restablecer la contraseña del usuario durante la conversión del buzón. Sin embargo, si la contraseña no se restablece, el nombre de usuario y la contraseña **originales siguen funcionando** una vez finalizada la conversión del buzón.

Para todo lo demás que necesita saber acerca de los buzones compartidos, vea [Acerca de](about-shared-mailboxes.md) los buzones compartidos y [Crear un buzón compartido](create-a-shared-mailbox.md).

> [!NOTE]
> Los buzones compartidos no requieren una licencia independiente. Sin embargo, si desea habilitar In-Place Archive o poner una retención de In-Place o una retención por juicio en un buzón compartido, debe asignar una licencia del Plan 1 de Exchange Online con una licencia del Plan 2 Archivado de Exchange Online o Exchange Online al buzón.

## <a name="convert-the-mailbox-of-a-deleted-user"></a>Convertir el buzón de un usuario eliminado

Después de eliminar una cuenta de usuario, siga estos pasos para convertir su buzón antiguo en un buzón de recurso compartido:

1. [Restaure la cuenta del usuario](../add-users/restore-user.md).

2. Asegúrese de que Microsoft 365 licencia de usuario está asignada.

3. Restablezca la contraseña del usuario.
    
4. Espere entre 20 y 30 minutos para que se vuelva a crear su buzón.
      
6. Una vez que se vuelva a crear el buzón, quite la licencia del buzón del usuario. No elimine el buzón antiguo del usuario. El buzón compartido lo necesita allí como delimitador.
    
7. Agregue miembros al buzón compartido.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Convertir un buzón compartido de nuevo en el buzón (privado) de un usuario

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.
   
2. Seleccione **Destinatarios compartidos**\>.

3. Seleccione el buzón compartido. En **Convertir a buzón normal**, seleccione **Convertir**.

4. Vuelva al Centro de administración. En **Usuarios**, elija la cuenta de usuario asociada al buzón compartido anterior. Asigne una licencia a la cuenta y, a continuación, restablezca la contraseña.

   El buzón de correo tardará unos minutos en configurarse, pero después de eso, la persona que va a usar esa cuenta está lista para usar. Cuando inicien sesión, verán los elementos de correo electrónico y calendario que solían estar en el buzón compartido.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Convertir el buzón de un usuario en un entorno híbrido

Para obtener más información sobre cómo convertir un buzón de usuario en un buzón compartido en un Exchange híbrido, vea:

 - [Cmdlets para crear o modificar un buzón compartido remoto en un entorno Exchange local](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [Los buzones compartidos se convierten inesperadamente en buzones de usuario después de que se ejecute la sincronización de directorios Exchange implementación híbrida](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Si es miembro del grupo de roles Administración de la organización o Administración de destinatarios, puede usar el Shell de administración de Exchange para cambiar un buzón de usuario a un buzón compartido local. Por ejemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)
