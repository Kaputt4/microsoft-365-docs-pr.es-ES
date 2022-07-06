---
title: Visualización y liberación de mensajes en cuarentena desde buzones compartidos
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
description: Los usuarios pueden aprender a ver y actuar en los mensajes en cuarentena que se enviaron a buzones compartidos a los que tienen permisos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a37ed03535bd3f3b48aca81c7bf7adeb3c660b46
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629021"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Visualización y liberación de mensajes en cuarentena desde buzones compartidos

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los usuarios pueden administrar mensajes en cuarentena donde son uno de los destinatarios, tal como se describe en [Buscar y liberar mensajes en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md). ¿Pero qué ocurre con **los buzones compartidos** en los que el usuario tiene permisos de acceso completo y enviar como o Enviar en nombre al buzón, como se describe en [Buzones compartidos en Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?

Anteriormente, la capacidad de los usuarios para administrar los mensajes en cuarentena enviados a un buzón compartido requería que los administradores dejaran habilitada la asignación automática para el buzón compartido (está habilitado de forma predeterminada cuando un administrador proporciona a un usuario acceso a otro buzón). Sin embargo, en función del tamaño y el número de buzones a los que el usuario tiene acceso, el rendimiento puede verse afectado a medida que Outlook intenta abrir _todos los_ buzones a los que el usuario tiene acceso. Por este motivo, muchos administradores [deciden quitar la asignación automática de buzones compartidos](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).

Ahora, la asignación automática ya no es necesaria para que los usuarios administren los mensajes en cuarentena que se enviaron a buzones compartidos. Sólo funciona. Hay dos métodos diferentes para acceder a los mensajes en cuarentena que se enviaron a un buzón compartido:

- Si el administrador ha configurado [directivas de cuarentena](quarantine-policies.md) para permitir notificaciones de cuarentena (anteriormente conocidas como notificaciones de correo no deseado del usuario final), cualquier usuario que tenga acceso a las notificaciones de cuarentena en el buzón compartido puede hacer clic en el botón **Revisar** de la notificación para ir a cuarentena en el portal de Microsoft 365 Defender. Tenga en cuenta que este método solo permite a los usuarios administrar los mensajes en cuarentena que se enviaron al buzón compartido. Los usuarios no pueden administrar sus propios mensajes de cuarentena en este contexto.
- El usuario puede [ir a cuarentena en el portal de Microsoft 365 Defender](find-and-release-quarantined-messages-as-a-user.md) y hacer clic en **Filtrar** para filtrar los resultados por **dirección de destinatario** (la dirección de correo electrónico del buzón compartido). En la página **Cuarentena** principal, puede hacer clic en la columna **Destinatario** para ordenar por mensajes que se enviaron al buzón compartido.

## <a name="things-to-keep-in-mind"></a>Aspectos importantes

- _Las directivas de cuarentena_ definen qué usuarios pueden hacer o no en los mensajes en cuarentena en función de por qué se puso en cuarentena el mensaje (para las características admitidas). Las directivas de cuarentena predeterminadas aplican las funcionalidades históricas que permiten a los destinatarios ver y actuar en los mensajes. Los administradores pueden crear y aplicar directivas de cuarentena personalizadas que definan funcionalidades menos restrictivas o más restrictivas para los usuarios. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

- El primer usuario que actúa sobre el mensaje en cuarentena decide el destino del mensaje para todos los usuarios que usan el buzón compartido. Por ejemplo, si 10 usuarios acceden a un buzón compartido y un usuario decide eliminar el mensaje de cuarentena, el mensaje se elimina para los 10 usuarios. Del mismo modo, si un usuario decide liberar el mensaje, se publica en el buzón compartido y es accesible para todos los demás usuarios del buzón compartido.

- Actualmente, el botón **Bloquear remitente** no está disponible en el control flotante **Detalles** para los mensajes en cuarentena que se enviaron al buzón compartido.

- Con respecto a las operaciones de cuarentena para buzones compartidos, si usa grupos de seguridad anidados para conceder acceso a un buzón compartido, se recomienda no más de dos niveles de grupos anidados. Por ejemplo, el grupo A es miembro del grupo B, que es miembro del grupo C. Para asignar permisos a un buzón compartido, no agregue el usuario al grupo A y, a continuación, asigne el grupo C al buzón compartido.

- A partir de julio de 2022, los usuarios con direcciones SMTP principales distintas de sus nombres principales de usuario (UPN) deben poder acceder a los mensajes en cuarentena del buzón compartido.

- Para administrar los mensajes en cuarentena para el buzón compartido en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), el usuario final deberá usar el cmdlet [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) con la dirección de correo electrónico del buzón compartido para el valor del parámetro _RecipientAddress_ para identificar los mensajes. Por ejemplo:

  ```powershell
  Get-QuarantineMessage -RecipientAddress officeparty@contoso.com
  ```

  A continuación, el usuario final puede seleccionar un mensaje en cuarentena de la lista para ver o tomar medidas.

  En este ejemplo se muestran todos los mensajes en cuarentena que se enviaron al buzón compartido y, a continuación, se libera el primer mensaje de la lista de la cuarentena (el primer mensaje de la lista es 0, el segundo es 1, etc.).

  ```powershell
  $SharedMessages = Get-QuarantineMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantineMessage -Identity $SharedMessages[0]
  ```

  Para obtener información detallada acerca de la sintaxis y los parámetros, consulte los siguientes temas:

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
