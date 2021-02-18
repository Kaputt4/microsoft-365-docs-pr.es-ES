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
description: Los administradores pueden obtener información sobre las notificaciones de correo no deseado para el usuario final para los mensajes en cuarentena en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287550"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados. Para obtener más información, vea [Mensajes en cuarentena en EOP.](quarantine-email-messages.md)

De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado. Cuando un administrador habilita las notificaciones de correo no deseado para el usuario final, los destinatarios (incluidos los [buzones](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)compartidos con la autoapping habilitada) recibirán notificaciones periódicas sobre sus mensajes que se han puesto en cuarentena como correo no deseado, correo electrónico masivo o suplantación de identidad (a partir de abril de 2020).

Para los buzones compartidos, las notificaciones de correo no deseado para el usuario final solo se admiten para los usuarios a los que se concede permiso FullAccess para el buzón compartido. Para obtener más información, [vea Usar el EAC para editar la delegación de buzones compartidos.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

La notificación de correo no deseado para el usuario final no es compatible con los grupos.

> [!NOTE]
> Los mensajes que se han puesto en cuarentena como suplantación de identidad de alta confianza, malware o por reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores. Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).

Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:

- **Remitente:** el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.

- **Asunto:** texto de la línea de asunto del mensaje en cuarentena.

- **Fecha:** fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.

- **Bloquear remitente:** haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados. Para obtener más información, vea [Bloquear un remitente de correo.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Versión:** para mensajes de correo no deseado (no de suplantación de identidad), puede liberar el mensaje aquí sin ir a Cuarentena del Centro de seguridad & cumplimiento.

- **Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages. Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en EOP.](find-and-release-quarantined-messages-as-a-user.md)

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)

> [!NOTE]
> Un remitente bloqueado aún puede enviarle correo. Los mensajes de este remitente que se envían a su buzón de correo se mueven inmediatamente a la carpeta correo no deseado. Los mensajes futuros de este remitente irán a la carpeta de correo no deseado o a la cuarentena del usuario final. Si desea eliminar estos mensajes al llegar en lugar de anularlos, [use](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) reglas de flujo de correo (también conocidas como reglas de transporte) para eliminar los mensajes al llegar.
