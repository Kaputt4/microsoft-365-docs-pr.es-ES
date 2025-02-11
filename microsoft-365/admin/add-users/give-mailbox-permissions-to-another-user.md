---
title: 'Conceder permisos de buzón a otro usuario: Ayuda para administradores'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: Dé a un usuario de Microsoft 365 el derecho de acceder al buzón de otro, lo que le permite leer y enviar correos electrónicos desde el buzón del otro usuario.
ms.openlocfilehash: ceb11ab89c18602704f911ffa7bd4e391c2c050a
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722008"
---
# <a name="give-mailbox-permissions-to-another-microsoft-365-user---admin-help"></a>Conceder permisos de buzón a otro usuario de Microsoft 365: Ayuda para administradores

As the admin, you may have company requirements to allow some users access to another user's mailbox. For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user. This topic shows you how to accomplish this.
  
Si está buscando información sobre cómo crear y administrar buzones compartidos, consulte [Crear un buzón compartido](../email/create-a-shared-mailbox.md).

> [!TIP]
> Si necesita ayuda con los pasos descritos en este tema, considere la posibilidad de [trabajar con un especialista de Microsoft Small Business](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.
    
## <a name="looking-to-set-up-mailbox-permissions"></a>¿Desea configurar los permisos de buzón?

Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:
  
 **Configurar los permisos:**
  
The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:
  
- [Leer correo electrónico desde el buzón de otro usuario](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [Enviar correo electrónico desde el buzón de otro usuario](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [Enviar correo electrónico en nombre de otro usuario](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **Cambiar la propagación:**
  
Después de configurar los permisos, los cambios pueden tardar hasta 60 minutos en propagarse por el sistema y hacerse efectivos.
  
 **Cómo usarlo una vez que los permisos están configurados:**
  
There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).

> [!NOTE]
> Los permisos se pueden configurar solo en el espacio empresarial de la organización actual. No es posible configurar permisos de buzón con usuarios que no sean parte de la cuenta empresarial.
  
## <a name="send-email-from-another-users-mailbox"></a>Enviar correo electrónico desde el buzón de otro usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  
    
2. Seleccione el nombre del usuario (al que piensa conceder permiso de envío) para abrir el panel de propiedades.
    
3. En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.

4. Junto a **Enviar como**, seleccione **Editar**. 

5. Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes. 
    
6. Seleccione **Agregar**.
 
::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.

3. Junto a **Enviar como**, seleccione **Editar**. 

4. Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes. 
    
5. Seleccione **Agregar**.

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>Leer correo electrónico en el buzón de otro usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  
    
2. Seleccione el nombre del usuario (cuyo buzón quiere permitir que se lea) para abrir el panel propiedades.
    
3. En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.
    
4. Junto a **Leer y administrar**, seleccione **Editar**. 
    
5. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.

6. Seleccione **Agregar**.


> [!NOTE]
> Los permisos de **Lectura** y **Administración** se llaman **Acceso completo** cuando se otorgan en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>. Este permiso permite al buzón del usuario asignado leer y administrar correos electrónicos en el buzón del usuario al que se asigna el permiso. El permiso de acceso total no concede los permisos de **Enviar como** o **Enviar en nombre de**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 
  
2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.
    
3. Junto a **Leer y administrar**, seleccione **Editar**. 
    
4. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.

5. Seleccione **Agregar**.

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>Enviar correo electrónico en nombre de otro usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  

2. Seleccione el nombre del usuario (al que piensa conceder permiso para **Enviar en nombre de**) para abrir el panel de propiedades.
    
3. En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.
    
4. Junto a **Enviar en nombre de**, seleccione **Editar**.

5. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.

6. Seleccione **Agregar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.

3. Junto a **Enviar en nombre de**, seleccione **Editar**.
    
4. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.

5. Seleccione **Agregar**.

::: moniker-end

> [!NOTE]
> Los permisos **Enviar como** y **Enviar en nombre de** no funcionan en el cliente de escritorio de Outlook con el parámetro *HiddenFromAddressListsEnabled* en el buzón establecido en **True**, ya que requieren que el buzón esté visible en Outlook a través de la lista global de direcciones.

## <a name="related-content"></a>Contenido relacionado
  
[Administrar elementos de correo y calendario de otra persona](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (artículo)\   
[Enviar correo electrónico de otra persona o grupo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (artículo)\
[Cambiar un nombre de usuario y una dirección de correo electrónico](../add-users/change-a-user-name-and-email-address.md) (vídeo)

