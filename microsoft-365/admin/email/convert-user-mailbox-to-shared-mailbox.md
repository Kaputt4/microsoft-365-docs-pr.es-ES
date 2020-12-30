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
description: 'Aprenda a convertir un buzón privado en un buzón compartido al que puedan tener acceso varios usuarios. '
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737970"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Convertir un buzón de usuario en un buzón compartido

Cuando se convierte el buzón de un usuario en un buzón compartido, se conservan todos los correos electrónicos y calendarios existentes. Solo ahora está en un buzón compartido donde varias personas podrán tener acceso a él en lugar de una persona. En una fecha posterior, puede volver a convertir un buzón de correo compartido en un buzón de usuario (privado).

**A continuación, se indican algunas cosas muy importantes que necesita saber:**

- El buzón de usuario que está convirtiendo necesita una licencia asignada antes de convertirla en un buzón compartido. De lo contrario, no verá la opción para convertir el buzón. Si ha quitado la licencia, agréguela de nuevo para que pueda convertir el buzón. Después de convertir el buzón en uno compartido, puede quitar la licencia de la cuenta del usuario.

- Los buzones compartidos pueden tener hasta 50 GB de datos sin una licencia asignada a ellos. Para contener más datos de los que necesita, necesita una licencia asignada. Es posible que deba eliminar un grupo de correos electrónicos grandes (por ejemplo, con datos adjuntos) del buzón compartido para reducirlo para que pueda quitar la licencia.

- No elimine la cuenta de usuario antigua. Esto es necesario para anclar el buzón compartido. Si ya ha eliminado la cuenta de usuario, vea [convertir el buzón de un usuario eliminado](#convert-the-mailbox-of-a-deleted-user).

- Las reglas permanecen intactas después de que el buzón se convierte en un buzón compartido.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Usar el centro de administración de Exchange para convertir un buzón
 
1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

2. Seleccione  \> **buzones** de destinatarios.

3. Seleccione el buzón de usuario. En **convertir a buzón compartido**, seleccione **convertir**.

4. Si el buzón es inferior a 50 GB, puede quitar la [licencia del usuario](../manage/remove-licenses-from-users.md)y dejar de pagar por ella. No elimine la cuenta de usuario. El buzón compartido lo necesita como un delimitador. Si va a convertir el buzón de un empleado que abandona su organización, debe realizar pasos adicionales para asegurarse de que ya no pueden iniciar sesión. Consulte [quitar un antiguo empleado de Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> No es necesario restablecer la contraseña del usuario durante la conversión de buzones de correo. Sin embargo, si no se restablece la contraseña, **el nombre de usuario y la contraseña originales seguirán funcionando** una vez finalizada la conversión del buzón.

Para todos los demás que necesite saber sobre los buzones compartidos, vea [About Shared mailboxes](about-shared-mailboxes.md) y [Create a Shared Mailbox](create-a-shared-mailbox.md).

> [!NOTE]
> Los buzones compartidos no requieren una licencia independiente. Sin embargo, si desea habilitar In-Place archivo o poner una retención de In-Place o una retención por juicio en un buzón compartido, debe asignar una licencia de Exchange Online plan 1 con archivado de Exchange online o Exchange Online plan 2 al buzón.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Convertir el buzón de un usuario eliminado

Supongamos que ha eliminado una cuenta de usuario y ahora desea convertir su buzón antiguo en un buzón de correo compartido. Esto es lo que necesita hacer:

1. [Restaurar la cuenta del usuario](../add-users/restore-user.md).

2. Asegúrese de que se le ha asignado una licencia de Microsoft 365.

3. Restablecer la contraseña del usuario.
    
4. Espere 20-30 minutos para que se vuelva a crear el buzón de correo.
    
5. Ahora siga las instrucciones que se indican en esta página para convertir su buzón de correo en un buzón compartido.
    
6. Una vez hecho, puede quitar la licencia del buzón de correo del usuario. No elimine el buzón de correo antiguo del usuario. El buzón compartido lo necesita como un delimitador.
    
7. Agregar miembros al buzón compartido.


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Volver a convertir un buzón de correo compartido en un buzón de correo (privado) de un usuario

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.
   
2. Seleccione **destinatarios** \> **compartidos**.

3. Seleccione el buzón compartido. En **convertir a buzón normal**, seleccione **convertir**.

4. Vuelva al centro de administración. En **usuarios**, seleccione la cuenta de usuario asociada con el buzón compartido antiguo. Asigne una licencia a la cuenta y restablezca la contraseña.

   El buzón tardará unos minutos en configurarse, pero, después de eso, la persona que va a usar esa cuenta está lista. Cuando inicien sesión, verán los elementos de calendario y correo electrónico que solían estar en el buzón compartido.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Convertir el buzón de un usuario en un entorno híbrido

Para obtener más información sobre cómo convertir un buzón de usuario en un buzón compartido en un entorno híbrido de Exchange, consulte:

 - [Cmdlets para crear o modificar un buzón de correo compartido remoto en un entorno de Exchange local](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [Los buzones compartidos se convierten inesperadamente en buzones de usuario después de ejecutar la sincronización de directorios en una implementación híbrida de Exchange](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Si es miembro del grupo de funciones administración de la organización o administración de destinatarios, puede usar el shell de administración de Exchange para cambiar el buzón de un usuario a un buzón compartido local. Por ejemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md)

[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md)
