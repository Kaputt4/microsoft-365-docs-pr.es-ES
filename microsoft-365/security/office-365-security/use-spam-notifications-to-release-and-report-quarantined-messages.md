---
title: Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes en cuarentena
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
ms.openlocfilehash: 641efc024a2842f30f7754c52f624a9f668851de
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636421"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes en cuarentena

Quarantine contiene mensajes potencialmente peligrosos o no deseados en Microsoft 365 organizaciones con buzones en Exchange online o organizaciones independientes de Exchange Online (EOP) sin buzones de Exchange Online. Para obtener más información, consulte [Cuarentena en Office 365](quarantine-email-messages.md).

De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado. Cuando un administrador [habilita las notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), los destinatarios recibirán notificaciones periódicas sobre sus mensajes que se pusieron en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) suplantación de identidad.

> [!NOTE]
> Los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza, malware o reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores. Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en Office 365](manage-quarantined-messages-and-files.md).

Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:

- **Sender**: el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.

- **Asunto**: el texto de la línea de asunto del mensaje en cuarentena.

- **Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.

- **Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados. Para obtener más información, vea [bloquear un remitente de correo en Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Liberar**: para los mensajes de correo no deseado (no phish), puede liberar el mensaje aquí sin ir a cuarentena en el centro de seguridad & cumplimiento.

- **Revisión**: haga clic en este vínculo para ir a cuarentena en el centro de seguridad & cumplimiento, donde puede liberar, eliminar o informar de los mensajes en cuarentena. Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en Office 365](find-and-release-quarantined-messages-as-a-user.md).

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)
