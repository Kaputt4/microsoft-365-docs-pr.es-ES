---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
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
description: Si el administrador habilita las notificaciones para los usuarios, recibirá un mensaje de notificación que enumera los mensajes enviados a su buzón que se identificaron como correo no deseado, en masa o de suplantación de identidad. Puede liberar o informar de los mensajes después de recibir la notificación.
ms.openlocfilehash: 4cf592f0aec948c3c8f6383cf288fb32ac644cd6
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971368"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365

Si su administrador habilita las notificaciones de correo no deseado para los usuarios, recibirá un mensaje de notificación que enumera los mensajes dirigidos a su buzón que se identificaron como correo no deseado y que se ponen en cuarentena en su lugar.

> [!TIP]
> Si es administrador y desea habilitar esta característica, puede elegir la opción cuando [modifique una directiva contra correo no deseado predeterminada](configure-your-spam-filter-policies.md).

El mensaje que recibe incluye el número de mensajes de correo no deseado en cuarentena que tiene, y la fecha y la hora (en UTC universal coordinada o UTC) del último mensaje de la lista. En la lista se incluyen los siguientes elementos para cada mensaje:

- **Remitente** El nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.

- **Asunto** El texto de la línea de asunto del mensaje en cuarentena.

- **Fecha** La fecha y hora (en UTC) en que el mensaje fue colocado en cuarentena.

Estas son las acciones que puede llevar a cabo con un mensaje en cuarentena:

- **Bloquear remitente** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.

- **Revise** para navegar al portal de cuarentena en el centro de seguridad y cumplimiento si desea realizar otras acciones, como la versión preliminar o la versión.

Tenga en cuenta lo siguiente:

- Los mensajes que se ponen en cuarentena debido a que coinciden con una regla de flujo de correo no se incluyen en los mensajes de usuario en cuarentena. Solo se enumeran los mensajes en cuarentena de correo no deseado.

- Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.
