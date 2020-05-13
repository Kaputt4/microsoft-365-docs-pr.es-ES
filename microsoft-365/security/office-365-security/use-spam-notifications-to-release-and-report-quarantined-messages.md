---
title: Notificaciones de correo no deseado para el usuario final en Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 7dd6b2d14bbb4a1771c59c8a1e654e36f0f83d3e
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208554"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes en cuarentena

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, la cuarentena contiene mensajes potencialmente peligrosos o no deseados. Para obtener más información, vea [mensajes en cuarentena en EOP](quarantine-email-messages.md).

De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado. Cuando un administrador [habilita las notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), los destinatarios recibirán notificaciones periódicas acerca de sus mensajes que se pusieron en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) phishing.

> [!NOTE]
> Los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza, malware o reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores. Para obtener más información, vea [Manage Quarantined messages and files as a admin in EOP](manage-quarantined-messages-and-files.md).

Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:

- **Sender**: el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.

- **Asunto**: el texto de la línea de asunto del mensaje en cuarentena.

- **Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.

- **Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados. Para obtener más información, vea [bloquear un remitente de correo en Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Liberar**: para los mensajes de correo no deseado (no phish), puede liberar el mensaje aquí sin ir a cuarentena en el centro de seguridad & cumplimiento.

- **Revisión**: haga clic en este vínculo para ir a cuarentena en el centro de seguridad & cumplimiento, donde puede liberar, eliminar o informar de los mensajes en cuarentena. Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)
