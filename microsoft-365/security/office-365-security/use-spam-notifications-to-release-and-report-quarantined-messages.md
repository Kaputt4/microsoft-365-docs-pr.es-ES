---
title: Notificaciones de correo no deseado para el usuario final en Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las notificaciones de correo no deseado para el usuario final sobre los mensajes en cuarentena de Exchange Online Protection (EOP).
ms.openlocfilehash: 0440056e8e31d24e659f9d0ff6662f86f31a6189
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600302"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados. Para obtener más información, vea [mensajes en cuarentena en EOP](quarantine-email-messages.md).

De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado. Cuando un administrador [habilita las notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), los destinatarios (incluidos los buzones compartidos con asignación automática habilitada) recibirán notificaciones periódicas sobre sus mensajes que se pusieron en cuarentena como correo no deseado, correo electrónico masivo o (a partir de la suplantación de identidad de abril de 2020).

Para los buzones compartidos, las notificaciones de correo no deseado para el usuario final solo se admiten para los usuarios que tienen el permiso FullAccess en el buzón compartido. Para obtener más información, vea [usar el EAC para editar la delegación de buzones compartidos](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

La notificación de correo no deseado para el usuario final no es compatible con grupos.

> [!NOTE]
> Los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza, malware o reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores. Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).

Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:

- **Sender**: el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.

- **Asunto**: el texto de la línea de asunto del mensaje en cuarentena.

- **Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.

- **Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados. Para obtener más información, vea [bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Versión**: para los mensajes de correo no deseado (no "phishing"), puede liberar el mensaje aquí sin ir a cuarentena en el centro de seguridad & cumplimiento.

- **Revisión**: haga clic en este vínculo para ir a cuarentena en el centro de seguridad & cumplimiento, donde puede (en función de por qué se puso en cuarentena el mensaje) ver, liberar, eliminar o informar de los mensajes en cuarentena. Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)

> [!NOTE]
> Un remitente bloqueado todavía puede enviarle correo. Los mensajes de este remitente que lo hagan a su buzón se moverán inmediatamente a la carpeta de correo electrónico no deseado. Los mensajes futuros de este remitente Irán a la carpeta de correo electrónico no deseado o a la cuarentena de usuario final. Si desea eliminar estos mensajes al recibirlos en lugar de ponerlos en cuarentena, use [las reglas de flujo de correo](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (también conocidas como reglas de transporte) para eliminar los mensajes al recibirlas.
