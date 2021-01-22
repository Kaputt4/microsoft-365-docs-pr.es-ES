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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Obtenga información acerca de cómo conceder a un usuario el derecho de acceso al buzón de otro usuario. Esto le dará al usuario el derecho de leer el correo electrónico y enviar correo electrónico desde el buzón del otro usuario. '
ms.openlocfilehash: e6b94d4e24b0ff1d5dc397ccbcfba98929a303f2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925547"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>Conceder permisos de buzón a otro usuario: Ayuda para administradores

Como administrador, puede que la empresa le requiera que permita que algunos usuarios puedan acceder al buzón de otro usuario. Por ejemplo, puede que quiera habilitar que un asistente envíe o lea el correo electrónico del buzón de su jefe o bien que uno de los usuarios pueda enviar correo electrónico en nombre de otro. En este tema se muestra cómo hacerlo.
  
Si está buscando información sobre cómo crear y administrar buzones compartidos, consulte [Crear un buzón compartido](../email/create-a-shared-mailbox.md).
    
## <a name="looking-to-set-up-mailbox-permissions"></a>¿Desea configurar los permisos de buzón?

Los permisos de buzón le permiten conceder acceso de lectura y escritura en un buzón a otro usuario. Los artículos siguientes pueden proporcionarle la ayuda que necesita para configurar y usar esta característica:
  
 **Configurar los permisos:**
  
El primer paso para configurar permisos es decidir qué acciones quiere permitir que el otro usuario realice en el buzón específico. Puede permitir que un usuario lea mensajes de correo electrónico desde el buzón, que envíe mensajes de correo electrónico en nombre de otro usuario y que envíe mensajes de correo electrónico como si se enviasen desde ese buzón. Consulte los siguientes artículos sobre cómo configurar cada tipo de permisos:
  
- [Leer correo electrónico desde el buzón de otro usuario](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [Enviar correo electrónico desde el buzón de otro usuario](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [Enviar correo electrónico en nombre de otro usuario](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **Cambiar la propagación:**
  
Después de configurar los permisos, los cambios pueden tardar hasta 60 minutos en propagarse por el sistema y hacerse efectivos.
  
 **Cómo usarlo una vez que los permisos están configurados:**
  
Hay diferentes maneras de acceder a un buzón una vez que se le ha concedido acceso. Para obtener ayuda sobre esto, consulte este artículo: [Obtener acceso al buzón de otra persona](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).

> [!NOTE]
> Los permisos se pueden configurar solo en el espacio empresarial de la organización actual. No es posible configurar permisos de buzón con usuarios que no sean parte de la cuenta empresarial.
  
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


> [!NOTE]
> Los permisos de **Lectura** y **Administración** se llaman de **Acceso completo** cuando se otorgan en el Centro de administración de Exchange. El permiso de Acceso completo no concede permisos de **Enviar como** ni **Enviar en nombre de**.

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


¿Quiere aprender cómo enviar correo electrónico desde el buzón de otro usuario? Consulte los temas siguientes:
  
- [Administrar elementos de correo y calendario de otra persona](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [Enviar correo electrónico de otra persona o grupo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
