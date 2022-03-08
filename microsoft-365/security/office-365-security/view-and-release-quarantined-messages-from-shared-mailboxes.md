---
title: Ver y liberar mensajes en cuarentena de buzones compartidos
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Los usuarios pueden aprender a ver y actuar en mensajes en cuarentena que se enviaron a buzones compartidos a los que tienen permisos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d9f83f176675be26fadf3d720dcc78e5146bde3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324527"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Ver y liberar mensajes en cuarentena de buzones compartidos

Los usuarios pueden administrar mensajes en cuarentena donde son uno de los destinatarios, tal como se describe en Buscar y liberar mensajes en cuarentena como usuario [en EOP](find-and-release-quarantined-messages-as-a-user.md). Sin embargo, ¿qué sucede **con** los buzones compartidos en los que el usuario tiene permisos acceso total y enviar como o Enviar en nombre del buzón, tal como se describe en [Buzones compartidos en Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?

Anteriormente, la capacidad de los usuarios para administrar los mensajes en cuarentena enviados a un buzón compartido requería que los administradores dejara habilitado el automapping para el buzón compartido (está habilitado de forma predeterminada cuando un administrador proporciona a un usuario acceso a otro buzón). Sin embargo, según el tamaño y el número de buzones a los que tenga acceso el usuario, el rendimiento puede sufrir a medida que  Outlook intenta abrir todos los buzones a los que el usuario tiene acceso. Por este motivo, muchos administradores eligen quitar [la automapping para buzones compartidos](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).

Ahora, la automapping ya no es necesaria para que los usuarios administren los mensajes en cuarentena que se enviaron a buzones compartidos. Solo funciona. Hay dos métodos diferentes para obtener acceso a los mensajes en cuarentena que se enviaron a un buzón compartido:

- Si el administrador ha configurado [](quarantine-policies.md) directivas de cuarentena para permitir notificaciones de cuarentena (anteriormente conocidas como notificaciones de correo no deseado de usuario final), cualquier usuario que tenga acceso a las notificaciones de cuarentena en el buzón  compartido puede hacer clic en el botón Revisar de la notificación para pasar a la cuarentena en el portal de Microsoft 365 Defender. Tenga en cuenta que este método solo permite a los usuarios administrar mensajes en cuarentena que se enviaron al buzón compartido. Los usuarios no pueden administrar sus propios mensajes de cuarentena en este contexto.
- El usuario puede [ir a la cuarentena en el portal de Microsoft 365 Defender y](find-and-release-quarantined-messages-as-a-user.md) hacer clic  en Filtrar para filtrar los resultados por dirección de **destinatario (la** dirección de correo electrónico del buzón compartido). En la página **cuarentena** principal, puede hacer clic en la columna **Destinatario** para ordenar por mensajes que se enviaron al buzón compartido.

## <a name="things-to-keep-in-mind"></a>Aspectos importantes

- _Las directivas de_ cuarentena definen lo que los usuarios pueden hacer o no hacer en los mensajes en cuarentena en función del motivo por el que el mensaje se ha puesto en cuarentena (para las características admitidas). Las directivas de cuarentena predeterminadas aplican las capacidades históricas que permiten a los destinatarios ver y actuar en los mensajes. Los administradores pueden crear y aplicar directivas de cuarentena personalizadas que definen capacidades menos restrictivas o más restrictivas para los usuarios. Para más información, consulte [Políticas de cuarentena](quarantine-policies.md).

- El primer usuario que actúa en el mensaje en cuarentena decide el destino del mensaje para todos los usuarios que usan el buzón compartido. Por ejemplo, si 10 usuarios tienen acceso a un buzón compartido y un usuario decide eliminar el mensaje en cuarentena, el mensaje se elimina para los 10 usuarios. Del mismo modo, si un usuario decide liberar el mensaje, se libera en el buzón compartido y es accesible para todos los demás usuarios del buzón compartido.

- Actualmente, el **botón Bloquear remitente** no está disponible en el  control desplegable Detalles para los mensajes en cuarentena que se enviaron al buzón compartido.

- Con respecto a las operaciones de cuarentena para buzones compartidos, si usa grupos de seguridad anidados para conceder acceso a un buzón compartido, se recomienda no más de dos niveles de grupos anidados. Por ejemplo, el grupo A es un miembro del grupo B, que es un miembro del grupo C. Para asignar permisos a un buzón compartido, no agregue al usuario al grupo A y, a continuación, asigne el grupo C al buzón compartido.  

- Para administrar mensajes en cuarentena para el buzón compartido en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), el usuario final tendrá que usar el cmdlet [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) con dirección de correo electrónico de buzón compartido para el valor del parámetro _RecipientAddress_ para identificar los mensajes. Por ejemplo:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  A continuación, el usuario final puede seleccionar un mensaje en cuarentena de la lista en el que ver o realizar acciones.

  En este ejemplo se muestran todos los mensajes en cuarentena que se enviaron al buzón compartido y, a continuación, se libera el primer mensaje de la lista desde la cuarentena (el primer mensaje de la lista es 0, el segundo es 1, y así sucesivamente).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Para obtener información detallada acerca de la sintaxis y los parámetros, consulte los siguientes temas:

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
