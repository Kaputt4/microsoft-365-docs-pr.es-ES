---
title: Configurar un buzón compartido
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Una vez que haya creado un buzón compartido, querrá configurar algunas opciones para sus usuarios, como reenvío de correo electrónico y respuestas automáticas. Más adelante, es posible que desee cambiar otras opciones, como el nombre o los miembros del buzón.
ms.openlocfilehash: edea829a8578387459afe3ce4889dfa620f95956
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255304"
---
# <a name="configure-a-shared-mailbox"></a>Configurar un buzón compartido

Una vez que haya [creado un buzón compartido](create-a-shared-mailbox.md), querrá configurar algunas opciones para los usuarios de buzones de correo, como reenvío de correo electrónico y respuestas automáticas. Más adelante, es posible que desee cambiar otras opciones, como el nombre del buzón, los miembros o los permisos de los miembros. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Cambiar el nombre o el alias de correo electrónico de un buzón compartido o cambiar la dirección de correo electrónico principal

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">buzones compartidos</a> de **grupos** \> .

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Editar** junto a **nombre, correo electrónico, alias de correo electrónico**.

3. Escriba un nuevo nombre o agregue otro alias. Si desea cambiar la dirección de correo electrónico principal, el buzón debe tener más de un alias de correo electrónico.

4. Seleccione **Guardar**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Reenviar mensajes de correo electrónico que se envían a un buzón compartido

No es necesario asignar una licencia al buzón compartido para reenviar el correo electrónico que se le envía. Puede reenviar los mensajes a cualquier dirección de correo electrónico o lista de distribución válida.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">buzones compartidos</a> de **grupos** \> .

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione \> **edición**de **reenvío de correo electrónico** .
    
3. Establezca el botón de alternancia en **activado**y escriba una dirección de correo electrónico a la que reenviar los mensajes. Puede ser cualquier dirección de correo electrónico válida. Para reenviar a varias direcciones, debe [crear un grupo de distribución](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) para las direcciones y, a continuación, escribir el nombre del grupo en este cuadro.
    
4. Seleccione **Guardar**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Enviar respuestas automáticas desde un buzón compartido

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">buzones compartidos</a> de **grupos** \> .

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione la \> **edición**de **respuestas automáticas** .
    
3. Establezca el botón de alternancia en **Activado** y elija si desea enviar la respuesta a las personas de su organización o de fuera de su organización.

4. Escriba la respuesta que desee enviar a personas dentro de su organización. No puede agregar imágenes, solo texto.

5. Si *también* quiere enviar una respuesta a personas de fuera de su organización, active la casilla de verificación, a la que desea obtener la respuesta y escriba el texto. No hay forma de enviar solo a las personas de fuera de la organización pero no a las personas de dentro de la organización.

6. Seleccione **Guardar**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Permitir que cualquier usuario vea el correo enviado (las respuestas)

De forma predeterminada, los mensajes enviados al buzón compartido no se guardan en la carpeta Elementos enviados del buzón compartido. En su lugar, se guardan en la carpeta Elementos enviados de la persona que envió el mensaje.

Si desea permitir que todos vean el correo electrónico enviado, en el centro de administración, modifique la configuración del buzón compartido y seleccione \> **Editar** **elementos enviados** .


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-office-365-email"></a>Elegir las aplicaciones que un buzón compartido puede usar para obtener acceso al correo electrónico de Office 365

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">buzones compartidos</a> de **grupos** \> .

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione \> **Editar** **aplicaciones de correo electrónico** .

3. Establezca el botón de alternancia en **activado** para todas las aplicaciones que desea que los miembros puedan usar para acceder al buzón compartido. Establezca el botón de alternancia en **desactivado** para todas las aplicaciones que no quiera que usen. 

4. Seleccione **Guardar**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Poner un buzón compartido en retención por juicio

Para obtener más información sobre la retención por juicio, consulte [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">buzones compartidos</a> de **grupos** \> .

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **edición**de **retención** \> por juicio.

3. Establezca el botón de alternancia en **activado**. 

4. De manera opcional, escriba una duración, una nota de s sobre la suspensión y una dirección URL con más información.  

5. Seleccione **Guardar**.


## <a name="add-or-remove-members"></a>Agregar o quitar miembros

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">buzones compartidos</a> de **grupos** \> .

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Editar** **miembros** \> .

3. Realice una de las acciones siguientes:
   - Para agregar miembros, seleccione **Agregar miembros**, busque o seleccione un miembro para agregarlo y, a continuación, seleccione **Guardar**.
   - Para quitar miembros, use el cuadro de búsqueda para buscar el miembro si es necesario, seleccione la **X** junto al nombre del miembro y, a continuación, seleccione **Guardar**. 

4. Vuelva a seleccionar **Guardar** .

## <a name="add-or-remove-permissions-of-members"></a>Agregar o quitar permisos de miembros

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">buzones compartidos</a> de **grupos** \> .

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione **miembros** \> **personalizar permisos**.

3. Seleccione **Editar** junto al permiso que desea cambiar para un miembro. 

4. Realice una de las acciones siguientes:
   - Para conceder ese permiso a un miembro adicional, seleccione **Agregar permisos**, busque o seleccione un miembro para agregarlo y, después, seleccione **Guardar**.
   - Para quitar el permiso de un miembro, use el cuadro de búsqueda para buscar el miembro si es necesario, seleccione la **X** junto al nombre del miembro y, a continuación, seleccione **Guardar**. 

4. Vuelva a seleccionar **Guardar** .

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Mostrar u ocultar un buzón compartido en la lista global de direcciones

Si elige no mostrar el buzón compartido en la lista global de direcciones, el buzón no aparecerá en la lista de direcciones de la organización, pero seguirá recibiendo correo electrónico que se le envíe. 

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">buzones compartidos</a> de **grupos** \> .

::: moniker-end 

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **buzones compartidos** de **grupos** > . 

::: moniker-end

2. Seleccione el buzón compartido que desea editar y, a continuación, seleccione Mostrar en la \> **edición** **de la lista global de direcciones** .

3. Establezca el botón de alternancia en **activado** o **desactivado**. 

4. Seleccione **Guardar**.

> [!NOTE]
> Si se oculta un buzón compartido de la lista de direcciones, es imposible que los nuevos miembros del buzón compartido agreguen el buzón oculto a su perfil de Outlook hasta que se vuelva a mostrar el buzón compartido en la lista de direcciones. 

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Quitar una licencia de un buzón compartido](remove-license-from-shared-mailbox.md)

[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md)
