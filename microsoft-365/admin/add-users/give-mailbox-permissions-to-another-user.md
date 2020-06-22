---
title: 'Conceder permisos de buzón a otro usuario: Ayuda para administradores'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Obtenga información acerca de cómo conceder a un usuario el derecho de acceso al buzón de otro usuario. Esto le dará al usuario el derecho de leer el correo electrónico y enviar correo electrónico desde el buzón del otro usuario. '
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780606"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>Conceder permisos de buzón a otro usuario: Ayuda para administradores

Como administrador, puede que la empresa le requiera que permita que algunos usuarios puedan acceder al buzón de otro usuario. Por ejemplo, puede que quiera habilitar que un asistente envíe o lea el correo electrónico del buzón de su jefe o bien que uno de los usuarios pueda enviar correo electrónico en nombre de otro. En este tema se muestra cómo hacerlo.
  
Si está buscando información sobre cómo crear y administrar buzones compartidos, consulte [Crear un buzón compartido](../email/create-a-shared-mailbox.md).
    
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
  
There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)
  
## <a name="send-email-from-another-users-mailbox"></a>Enviar correo electrónico desde el buzón de otro usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  
    
2. Seleccione el nombre del usuario (al que piensa conceder permiso de envío) para abrir el panel de propiedades.
    
3. En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.

4. Junto a **Enviar como**, seleccione **Editar**. 

5. Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes. 
    
6. Seleccione **Guardar**.
 
::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  

2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.

3. Junto a **Enviar como**, seleccione **Editar**. 

4. Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes. 
    
5. Seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.

3. Junto a **Enviar como**, seleccione **Editar**. 

4. Seleccione **Agregar permisos** y elija el nombre de la persona en cuyo nombre desea que este usuario pueda enviar mensajes. 
    
5. Seleccione **Guardar**.

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>Leer correo electrónico en el buzón de otro usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  
    
2. Seleccione el nombre del usuario (cuyo buzón quiere permitir que se lea) para abrir el panel propiedades.
    
3. En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.
    
4. Junto a **Leer y administrar**, seleccione **Editar**. 
    
5. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.

6. Seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  
  
2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.
    
3. Junto a **Leer y administrar**, seleccione **Editar**. 
    
4. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.

5. Seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 
  
2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.
    
3. Junto a **Leer y administrar**, seleccione **Editar**. 
    
4. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir leer el correo electrónico de este buzón.

5. Seleccione **Guardar**.

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>Enviar correo electrónico en nombre de otro usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.  

2. Seleccione el nombre del usuario (al que piensa conceder permiso para **Enviar en nombre de**) para abrir el panel de propiedades.
    
3. En la pestaña **Correo**, seleccione **Administrar permisos de buzón**.
    
4. Junto a **Enviar en nombre de**, seleccione **Editar**.

5. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.

6. Seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.  

2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.

3. Junto a **Enviar en nombre de**, seleccione **Editar**.
    
4. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.

5. Seleccione **Guardar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

2. Seleccione el usuario que desee, expanda **Configuración de correo** y seleccione **Editar** junto a **Permisos del buzón**.

3. Junto a **Enviar en nombre de**, seleccione **Editar**.
    
4. Seleccione **Agregar permisos** y elija el nombre del usuario o los usuarios a los que quiere permitir enviar el correo electrónico en nombre de este buzón.

5. Seleccione **Guardar**.

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a>Enviar y leer desde Outlook y Outlook en la Web empresarial


Want to know how to send email from another user's mailbox? Check out the following topics:
  
- [Administrar elementos de correo y calendario de otra persona](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [Enviar correo electrónico de otra persona o grupo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
