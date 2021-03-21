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
ms.openlocfilehash: 617ff9b6325ac2d5d95d8bc591b9e4ebb7f5434d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921125"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificaciones de correo no deseado de usuario para liberar e informar de mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

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

- **Bloquear remitente:** haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados. Para obtener más información, vea [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Versión:** para mensajes de correo no deseado (no suplantación de identidad), puede liberar el mensaje aquí sin ir a Poner en cuarentena el Centro de seguridad & cumplimiento.

- **Revisar:** haga clic en este vínculo para ir a Cuarentena en el Centro de seguridad y cumplimiento de &, donde puede (según por qué el mensaje se ha puesto en cuarentena) ver, liberar, eliminar o notificar los mensajes en cuarentena. Para obtener más información, vea Buscar y liberar mensajes [en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)

> [!NOTE]
> Un remitente bloqueado aún puede enviarle correo. Los mensajes de este remitente que se envían a su buzón se mueven inmediatamente a la carpeta Correo no deseado. Los mensajes futuros de este remitente irán a la carpeta correo no deseado o a la cuarentena del usuario final. Si desea eliminar estos mensajes al llegar en lugar de anularlos, use reglas de flujo de correo [(también](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) conocidas como reglas de transporte) para eliminar los mensajes al llegar.