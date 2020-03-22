---
title: Notificaciones de correo no deseado para el usuario final en Office 36
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
description: Cuando un administrador habilita las notificaciones de correo no deseado para el usuario final en las directivas contra correo no deseado, los destinatarios del mensaje recibirán notificaciones periódicas sobre los mensajes en cuarentena.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895064"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Notificaciones de correo no deseado para el usuario final en Office 365

La cuarentena retiene los mensajes que pueden ser peligrosos o no deseados en las organizaciones de Office 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online. Para obtener más información, consulte [Cuarentena en Office 365](quarantine-email-messages.md).

De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado. Cuando un administrador [habilita las notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md), los destinatarios del mensaje recibirán notificaciones periódicas sobre sus mensajes que se pusieron en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) phishing.

> [!NOTE]
> En octubre de 2019, eliminamos la capacidad de liberar los mensajes en cuarentena directamente de las notificaciones de correo no deseado para el usuario final. En su lugar, ahora los usuarios pueden ir al centro de cumplimiento de & de seguridad de Office 365 para liberar sus mensajes en cuarentena (ya sea directamente o haciendo clic en **revisar** en la notificación). Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en Office 365](find-and-release-quarantined-messages-as-a-user.md). <br/><br/> Los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza, malware o reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores. Para obtener más información, consulte [Manage Quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).

Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:

- **Sender**: el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.

- **Asunto**: el texto de la línea de asunto del mensaje en cuarentena.

- **Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.

- **Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados.

- **Revisión**: haga clic en este vínculo para ir a la cuarentena en el centro de seguridad & cumplimiento, donde puede liberar, eliminar o informar de los mensajes en cuarentena.

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)
