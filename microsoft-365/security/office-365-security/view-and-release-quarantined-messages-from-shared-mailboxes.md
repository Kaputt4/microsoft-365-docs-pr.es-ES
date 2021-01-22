---
title: Ver y liberar mensajes en cuarentena de buzones compartidos
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Los usuarios pueden aprender a ver y actuar en mensajes en cuarentena que se enviaron a buzones compartidos para los que tienen permisos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3efccca375745b0850c91039165b72a7d6f0bcb3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931451"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Ver y liberar mensajes en cuarentena de buzones compartidos

> [!NOTE]
> Las características que se describen en este artículo están actualmente en versión preliminar, no están disponibles para todos los usuarios y están sujetas a cambios.

Los usuarios pueden administrar mensajes en cuarentena donde son uno de los destinatarios, tal como se describe en Buscar y liberar mensajes en cuarentena como un usuario [en EOP.](find-and-release-quarantined-messages-as-a-user.md) Pero, ¿qué sucede con los buzones compartidos en los que el usuario tiene permisos acceso total y Enviar como o Enviar en nombre del buzón, tal como se describe en Buzones compartidos [en Exchange Online?](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)

Anteriormente, la capacidad de los usuarios para administrar los mensajes en cuarentena enviados a un buzón compartido requería que los administradores dejara habilitada la automapping para el buzón compartido (está habilitada de forma predeterminada cuando un administrador proporciona a un usuario acceso a otro buzón). Sin embargo, según el tamaño y el número de buzones a los que  tenga acceso el usuario, el rendimiento puede sufrir cuando Outlook intenta abrir todos los buzones a los que el usuario tiene acceso. Por este motivo, muchos administradores eligen [quitar la autoapping para buzones compartidos.](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

Ahora, ya no es necesaria la autoapping para que los usuarios administren los mensajes en cuarentena que se enviaron a buzones compartidos. Simplemente funciona. Existen dos métodos diferentes para obtener acceso a los mensajes en cuarentena que se enviaron a un buzón compartido:

- Si el [](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) administrador ha habilitado notificaciones de correo no deseado para el usuario final en directivas contra correo no  deseado, cualquier usuario que tenga acceso a las notificaciones de correo no deseado del usuario final en el buzón compartido puede hacer clic en el botón Revisar de la notificación para pasar a cuarentena en el Centro de seguridad & Cumplimiento. Tenga en cuenta que este método solo permite a los usuarios administrar los mensajes en cuarentena que se enviaron al buzón compartido. Los usuarios no pueden administrar sus propios mensajes de cuarentena en este contexto.

- El usuario puede ir a la cuarentena en el Centro de [& cumplimiento.](find-and-release-quarantined-messages-as-a-user.md) De forma predeterminada, solo se muestran los mensajes que se enviaron al usuario. Sin embargo, el usuario puede  cambiar los resultados de la ordenación **(el** botón Id.  de mensaje de forma predeterminada) a la dirección de correo electrónico del **destinatario,** escribir la dirección de correo electrónico del buzón compartido y, a continuación, hacer clic en Actualizar para ver los mensajes en cuarentena que se enviaron al buzón compartido.

  ![Ordenar los mensajes en cuarentena por dirección de correo electrónico del destinatario.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Independientemente del método, los usuarios pueden evitar confusiones si incluyen la **columna Recipient** para los mensajes en cuarentena. El número máximo de columnas para mostrar es 7, por lo que el usuario tendrá que hacer clic  en Modificar **columnas,** quitar una columna existente (por **ejemplo,** Tipo de directiva), seleccionar Destinatario y, a continuación, hacer clic en Guardar o Guardar como **predeterminado.**

  ![Quite la columna Tipo de directiva y agregue la columna Destinatario a la cuarentena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Aspectos importantes

- El primer usuario que actúa en el mensaje en cuarentena decide el destino del mensaje para todos los usuarios que usan el buzón compartido. Por ejemplo, si 10 usuarios acceden a un buzón compartido y un usuario decide eliminar el mensaje en cuarentena, el mensaje se elimina para los 10 usuarios. Del mismo modo, si un usuario decide liberar el mensaje, se libera en el buzón compartido y es accesible para todos los demás usuarios del buzón compartido.

- Actualmente, el **botón Bloquear remitente** no está disponible en el control desplegable Detalles para los mensajes en cuarentena que se enviaron al buzón compartido. 

- Para administrar los mensajes en cuarentena para el buzón compartido en [Exchange Online PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)el usuario final tendrá que usar el cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) con la dirección de correo electrónico del buzón compartido para el valor del parámetro _RecipientAddress_ para identificar los mensajes. Por ejemplo:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  A continuación, el usuario final puede seleccionar un mensaje en cuarentena de la lista para ver o tomar medidas.

  En este ejemplo se muestran todos los mensajes en cuarentena que se enviaron al buzón compartido y, a continuación, se libera el primer mensaje de la lista de cuarentena (el primer mensaje de la lista es 0, el segundo es 1, y así sucesivamente).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Para obtener información detallada acerca de la sintaxis y los parámetros, consulte los siguientes temas:

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
