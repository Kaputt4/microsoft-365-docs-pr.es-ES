---
title: Establecer la configuración de buzón compartido
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
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Cree un buzón compartido y configure algunas opciones para sus usuarios, como el reenvío de correo electrónico y las respuestas automáticas.
ms.openlocfilehash: ff17c9d16f84da5ef93d777e10eaf1fcfb99c55f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68194013"
---
# <a name="configure-microsoft-365-shared-mailbox-settings"></a>Configuración del buzón compartido de Microsoft 365

Después de [crear un buzón compartido](create-a-shared-mailbox.md), querrá configurar algunas opciones para los usuarios del buzón, como el reenvío de correo electrónico y las respuestas automáticas. Más adelante, es posible que quiera cambiar otra configuración, como el nombre del buzón, los miembros o los permisos de miembro. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Cambie el nombre o el alias de correo electrónico de un buzón compartido o cambie la dirección de correo electrónico principal.

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Editar** junto a **Nombre, Email, Email alias**.

3. Escriba un nuevo nombre o agregue otro alias. Si desea cambiar la dirección de correo electrónico principal, el buzón debe tener más de un alias de correo electrónico.

4. Seleccione **Guardar**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Reenviar mensajes de correo electrónico que se envían a un buzón compartido

No es necesario asignar una licencia al buzón compartido para reenviar el correo electrónico que se le envía. Puede reenviar los mensajes a cualquier dirección de correo electrónico o lista de distribución válida.

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Email edición de** \> reenvío.
    
3. Establezca el botón de alternancia **en Activado** y escriba una dirección de correo electrónico a la que reenviar los mensajes. Puede ser cualquier dirección de correo electrónico válida. Para reenviar a varias direcciones, debe [crear un grupo de distribución](/office365/admin/setup/create-distribution-lists) para las direcciones y, a continuación, escribir el nombre del grupo en este cuadro.
    
4. Seleccione **Guardar**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Enviar respuestas automáticas desde un buzón compartido

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Edición** **automática de** \> respuestas.
    
3. Establezca el botón de alternancia en **Activado** y elija si desea enviar la respuesta a las personas de su organización o de fuera de su organización.

4. Escriba la respuesta que desee enviar a personas dentro de su organización. No puede agregar imágenes, solo texto.

5. Si *también* desea enviar una respuesta a personas ajenas a su organización, active la casilla , a quién quiere obtener la respuesta y escriba el texto. No hay forma de enviar solo a las personas de fuera de la organización pero no a las personas de dentro de la organización.

6. Seleccione **Guardar**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Permitir que cualquier usuario vea el correo enviado (las respuestas)

By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.

Si desea permitir que todos vean el correo electrónico enviado, en el centro de administración, edite la configuración del buzón compartido y seleccione **Editar elementos enviados**\>.


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Elija las aplicaciones que puede usar un buzón compartido para acceder al correo electrónico de Microsoft.

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **editar Email aplicaciones** \> **.**

3. Establezca el botón de alternancia **en Activado** para todas las aplicaciones que quiera que los miembros puedan usar para acceder al buzón compartido. Establezca el botón de alternancia en **Desactivado** para las aplicaciones que no quiera que usen. 

4. Seleccione **Guardar**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Colocación de un buzón compartido en suspensión por juicio

Para obtener más información sobre la suspensión por juicio, consulte [Creación de una suspensión por juicio](../../compliance/create-a-litigation-hold.md).

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Edición de suspensión** \> por juicio.

3. Establezca el botón de alternancia **en Activado**. 

4. Opcionalmente, escriba una duración, una nota sobre la suspensión y una dirección URL con más información.  

5. Seleccione **Guardar**.


## <a name="add-or-remove-members"></a>Agregar o quitar miembros

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Edición de miembros**\>.

3. Realiza una de las siguientes acciones:
   - Para agregar miembros, seleccione **Agregar miembros**, busque o seleccione un miembro para agregar y, a continuación, seleccione **Guardar**.
   - Para quitar miembros, use el cuadro Buscar para buscar el miembro si es necesario, seleccione la **X** junto al nombre del miembro y, a continuación, seleccione **Guardar**. 

4. Seleccione **Guardar** nuevamente.

## <a name="add-or-remove-permissions-of-members"></a>Adición o eliminación de permisos de miembros

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Miembros** \> **Personalizar permisos**.

3. Seleccione **Editar** junto al permiso que desea cambiar para un miembro. 

4. Realiza una de las siguientes acciones:
   - Para conceder ese permiso a un miembro adicional, seleccione **Agregar permisos**, busque o seleccione un miembro para agregar y, a continuación, seleccione **Guardar**.
   - Para quitar el permiso de un miembro, use el cuadro Buscar para buscar el miembro si es necesario, seleccione la **X** situada junto al nombre del miembro y, a continuación, seleccione **Guardar**. 

4. Seleccione **Guardar** nuevamente.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Mostrar u ocultar un buzón compartido en la lista global de direcciones

Si decide no mostrar el buzón compartido en la lista de direcciones global, el buzón no aparecerá en la lista de direcciones de su organización, pero seguirá recibiendo correo electrónico enviado. 

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Mostrar en la lista** \> global **de direcciones Editar**.

3. Establezca el botón de alternancia **en Activado**  o **Desactivado**. 

4. Seleccione **Guardar**.

> [!NOTE]
> Ocultar un buzón compartido de la lista de direcciones hará imposible que los nuevos miembros del buzón compartido agreguen el buzón oculto a su perfil de Outlook hasta que el buzón compartido se muestre de nuevo en la lista de direcciones. 

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)