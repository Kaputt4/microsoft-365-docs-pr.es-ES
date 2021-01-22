---
title: Establecer la configuración de buzón compartido
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Después de crear un buzón compartido, es posible que desee configurar algunas opciones para sus usuarios, como el reenvío de correo electrónico y las respuestas automáticas. Más adelante, es posible que desee cambiar otras opciones de configuración, como el nombre del buzón o los miembros.
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926611"
---
# <a name="configure-shared-mailbox-settings"></a>Establecer la configuración de buzón compartido

Después de crear [un buzón](create-a-shared-mailbox.md)compartido, es posible que desee configurar algunas opciones para los usuarios del buzón, como el reenvío de correo electrónico y las respuestas automáticas. Más adelante, es posible que desee cambiar otras opciones de configuración, como el nombre del buzón, los miembros o los permisos de miembro. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Cambiar el nombre o el alias de correo electrónico de un buzón compartido o cambiar la dirección de correo electrónico principal

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

2. Seleccione el buzón compartido que desea  editar y, a continuación, seleccione Editar junto a **Nombre, Correo electrónico, Alias de correo electrónico.**

3. Escriba un nombre nuevo o agregue otro alias. Si desea cambiar la dirección de correo electrónico principal, el buzón debe tener más de un alias de correo electrónico.

4. Seleccione **Guardar**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Reenviar mensajes de correo electrónico que se envían a un buzón compartido

No es necesario asignar una licencia al buzón compartido para reenviar el correo electrónico que se le envía. Puede reenviar los mensajes a cualquier dirección de correo electrónico o lista de distribución válida.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Edición de reenvío de correo** \> **electrónico.**
    
3. Establezca el botón de **alternancia en Activar** y escriba una dirección de correo electrónico a la que reenviar los mensajes. Puede ser cualquier dirección de correo electrónico válida. Para reenviar a varias direcciones, debe crear un grupo de distribución para las direcciones y, [a](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) continuación, escribir el nombre del grupo en este cuadro.
    
4. Seleccione **Guardar**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Enviar respuestas automáticas desde un buzón compartido

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, **seleccione Respuestas automáticas** \> **Editar.**
    
3. Establezca el botón de alternancia en **Activado** y elija si desea enviar la respuesta a las personas de su organización o de fuera de su organización.

4. Escriba la respuesta que desee enviar a personas dentro de su organización. No puede agregar imágenes, solo texto.

5. Si también desea enviar *una* respuesta a personas de fuera de su organización, active la casilla, quién desea obtener la respuesta y escriba el texto. No hay forma de enviar solo a las personas de fuera de la organización pero no a las personas de dentro de la organización.

6. Seleccione **Guardar**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Permitir que cualquier usuario vea el correo enviado (las respuestas)

De forma predeterminada, los mensajes enviados al buzón compartido no se guardan en la carpeta Elementos enviados del buzón compartido. En su lugar, se guardan en la carpeta Elementos enviados de la persona que envió el mensaje.

Si desea permitir que todos los usuarios vean el correo electrónico enviado, en el centro de administración, edite la configuración del buzón compartido y seleccione Editar **elementos** \> **enviados.**


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Elegir las aplicaciones que puede usar un buzón compartido para obtener acceso al correo electrónico de Microsoft

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Editar aplicaciones de correo** \> **electrónico.**

3. Establezca el botón de **alternancia en Activar** para todas las aplicaciones que desea que los miembros puedan usar para acceder al buzón compartido. Establece el botón de **alternancia en Desactivado** para las aplicaciones que no quieras que usen. 

4. Seleccione **Guardar**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Poner un buzón compartido en retención por juicio

Para obtener más información acerca de la retención por juicio, [vea Crear una retención por juicio.](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Retención por** juicio \> **Editar.**

3. Establezca el botón de alternancia en **On**. 

4. Opcionalmente, escriba una duración, una nota sobre la retención y una dirección URL con más información.  

5. Seleccione **Guardar**.


## <a name="add-or-remove-members"></a>Agregar o quitar miembros

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Editar** \> **miembros.**

3. Realice una de las acciones siguientes:
   - Para agregar miembros, seleccione **Agregar miembros,** busque o seleccione un miembro para agregar y, a continuación, **seleccione Guardar**.
   - Para quitar miembros, use el cuadro de búsqueda para buscar el miembro si es necesario, seleccione la **X** junto al nombre del miembro y, a continuación, **seleccione Guardar**. 

4. Seleccione **Guardar de** nuevo.

## <a name="add-or-remove-permissions-of-members"></a>Agregar o quitar permisos de miembros

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Miembros** \> **personalizar permisos.**

3. Seleccione **Editar** junto al permiso que desea cambiar para un miembro. 

4. Realice una de las acciones siguientes:
   - Para conceder ese permiso a un miembro adicional, seleccione Agregar **permisos,** busque o seleccione un miembro para agregar y, a continuación, **seleccione Guardar**.
   - Para quitar el permiso de un miembro, use el cuadro de búsqueda para buscar el miembro si es necesario, seleccione la **X** junto al nombre del miembro y, a continuación, **seleccione Guardar**. 

4. Seleccione **Guardar de** nuevo.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Mostrar u ocultar un buzón compartido en la lista global de direcciones

Si decide no mostrar el buzón compartido en la lista global de direcciones, el buzón no aparecerá en la lista de direcciones de su organización, pero seguirá recibiendo correo electrónico enviado. 

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos** > **Buzones compartidos**. 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Mostrar en la lista global de direcciones Editar** \> .

3. Establezca el botón de **alternancia en Activar** o **Desactivar.** 

4. Seleccione **Guardar**.

> [!NOTE]
> Ocultar un buzón compartido de la lista de direcciones hará imposible que los nuevos miembros del buzón compartido agreguen el buzón oculto a su perfil de Outlook hasta que el buzón compartido se vuelva a mostrar en la lista de direcciones. 

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md)

[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md)
