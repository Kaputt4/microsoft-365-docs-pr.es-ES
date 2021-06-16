---
title: Notificaciones de correo no deseado del usuario final en Microsoft 365
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
description: Los administradores pueden obtener información sobre las notificaciones de correo no deseado del usuario final para mensajes en cuarentena en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71f2a33ad83f94895c396f92c18753bfca7f2905
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933172"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificaciones de correo no deseado de usuario para liberar e informar de mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados. Para obtener más información, vea [Mensajes en cuarentena en EOP](quarantine-email-messages.md).

De forma predeterminada, las notificaciones de correo no deseado del usuario final están deshabilitadas en las directivas contra correo no deseado. Cuando un administrador habilita las notificaciones de [correo](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)no deseado del usuario final, los destinatarios (incluidos los buzones compartidos con automapping habilitado) recibirán notificaciones periódicas sobre sus mensajes que se han puesto en cuarentena como correo no deseado, correo electrónico masivo o suplantación de identidad (a partir de abril de 2020).

En el caso de los buzones compartidos, las notificaciones de correo no deseado del usuario final solo se admiten para los usuarios a los que se les concede permiso FullAccess para el buzón compartido. Para obtener más información, [vea Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

La notificación de correo no deseado del usuario final no es compatible con los grupos.

> [!NOTE]
> Los mensajes que se han puesto en cuarentena como phishing de elevada confianza, malware o por reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores. Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).

Una notificación de correo no deseado del usuario final contiene la siguiente información para cada mensaje en cuarentena:

- **Remitente:** el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.
- **Asunto:** el texto de la línea de asunto del mensaje en cuarentena.
- **Fecha:** la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.
- **Bloquear remitente:** haga clic en este vínculo para agregar el remitente a la lista Remitentes bloqueados del buzón. Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).
- **Versión:** para mensajes de correo no deseado (no suplantación de identidad), puede liberar el mensaje aquí sin ir a **Poner** en cuarentena el portal de Microsoft 365 Defender.
- **Review**: Click this link to go to **Quarantine** in the Microsoft 365 Defender portal, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages. Para obtener más información, vea Buscar y liberar mensajes [en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)

> [!NOTE]
> Un remitente bloqueado aún puede enviarle correo. Los mensajes de este remitente que se envían a su buzón se mueven inmediatamente a la carpeta Correo no deseado. Los mensajes futuros de este remitente irán a la carpeta correo no deseado o a la cuarentena del usuario final. Si desea eliminar estos mensajes al llegar en lugar de anularlos, use reglas de flujo de correo [(también](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) conocidas como reglas de transporte) para eliminar los mensajes al llegar.
