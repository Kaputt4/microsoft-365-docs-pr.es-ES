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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Aprenda a convertir un buzón privado en un buzón compartido al que puedan tener acceso varias personas en lugar de solo una persona. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635479"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Convertir un buzón de usuario en un buzón compartido

Al convertir el buzón de un usuario en un buzón compartido, se conserva todo el correo electrónico y el calendario existentes. Solo ahora está en un buzón compartido en el que varias personas podrán tener acceso a él en lugar de una persona. En una fecha posterior, puede volver a convertir un buzón compartido en un buzón de usuario (privado).

## <a name="before-you-begin"></a>Antes de empezar

**Estas son algunas cosas realmente importantes que necesita saber:**

- El buzón de usuario que está convirtiendo necesita una licencia asignada antes de convertirlo en un buzón compartido. De lo contrario, no verá la opción para convertir el buzón. Si ha quitado la licencia, vuelva a agregarla para poder convertir el buzón. Después de convertir el buzón en uno compartido, puede quitar la licencia de la cuenta del usuario.

- Los buzones compartidos pueden tener hasta 50 GB de datos sin una licencia asignada. Para contener más datos que eso, necesita una licencia asignada. Es posible que deba eliminar un montón de correos electrónicos grandes (por ejemplo, los que tienen datos adjuntos) del buzón compartido para reducirlo para poder quitar la licencia.

- No elimine la cuenta del usuario anterior. Eso es necesario para delimitar el buzón compartido. Si ya eliminó la cuenta de usuario, vea [Convertir el buzón de un usuario eliminado.](#convert-the-mailbox-of-a-deleted-user)

- Las reglas están intactas después de convertir el buzón en un buzón compartido.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Usar el Centro Exchange administración para convertir un buzón
 
1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

2. Seleccione **Destinatarios** \> **Buzones**.

3. Seleccione el buzón de usuario. En **Convertir a buzón compartido,** seleccione **Convertir**.

4. Si el buzón es inferior a 50 [](../manage/remove-licenses-from-users.md)GB, puede quitar la licencia del usuario y dejar de pagarla. No elimine la cuenta del usuario. El buzón compartido lo necesita allí como delimitador. Si va a convertir el buzón de un empleado que abandona la organización, debe seguir pasos adicionales para asegurarse de que ya no puedan iniciar sesión. Consulte [Quitar un antiguo empleado de Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> No es necesario restablecer la contraseña del usuario durante la conversión del buzón. Sin embargo, si la contraseña no se restablece, el nombre de usuario y la contraseña originales siguen **funcionando** una vez finalizada la conversión del buzón.

Para todo lo demás que necesita saber acerca de los buzones compartidos, vea Acerca de los buzones [compartidos](about-shared-mailboxes.md) y [Crear un buzón compartido.](create-a-shared-mailbox.md)

> [!NOTE]
> Los buzones compartidos no requieren una licencia independiente. Sin embargo, si desea habilitar In-Place Archive o poner una retención de In-Place o una retención por juicio en un buzón compartido, debe asignar una licencia del Plan 1 de Exchange Online con una licencia del Plan 2 Archivado de Exchange Online o Exchange Online al buzón.

## <a name="convert-the-mailbox-of-a-deleted-user"></a>Convertir el buzón de un usuario eliminado

Supongamos que ha eliminado una cuenta de usuario y ahora desea convertir su buzón antiguo en un buzón de recurso compartido. Esto es lo que debe hacer:

1. [Restaurar la cuenta del usuario](../add-users/restore-user.md).

2. Asegúrese de que Microsoft 365 licencia de usuario está asignada.

3. Restablezca la contraseña del usuario.
    
4. Espere entre 20 y 30 minutos para volver a crear su buzón.
    
5. Ahora siga las instrucciones de esta página para convertir su buzón en un buzón compartido.
    
6. Una vez hecho esto, puede quitar la licencia del buzón del usuario. No elimine el buzón antiguo del usuario. El buzón compartido lo necesita allí como delimitador.
    
7. Agregue miembros al buzón compartido.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Convertir un buzón compartido de nuevo en el buzón (privado) de un usuario

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.
   
2. Seleccione **Destinatarios** \> **compartidos**.

3. Seleccione el buzón compartido. En **Convertir a buzón normal,** seleccione **Convertir**.

4. Vuelva al Centro de administración. En **Usuarios,** elija la cuenta de usuario asociada al buzón compartido anterior. Asigne una licencia a la cuenta y restablezca la contraseña.

   El buzón de correo tardará unos minutos en configurarse, pero después de eso, la persona que va a usar esa cuenta está lista para usarse. Cuando inicien sesión, verán los elementos de correo electrónico y calendario que solían estar en el buzón compartido.

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