---
title: Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Encuentre respuestas a las preguntas más comunes sobre los mensajes que se han puesto en cola, aplazado o devuelto durante el proceso de filtrado de Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e54a260a70a9c68a94412243308bffe60d989e99
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289704"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En este tema se proporcionan respuestas a las preguntas más frecuentes sobre los mensajes que se han puesto en cola, aplazado o devuelto durante el proceso de filtrado de Exchange Online Protection (EOP).

## <a name="why-is-mail-queuing"></a>¿Por qué se pone el correo en cola?

Los mensajes se ponen en cola o se aplazan si el servicio no puede establecer una conexión con el servidor del destinatario para la entrega. Los mensajes no se aplazan si la red del destinatario devuelve un error de tipo 500.

## <a name="how-does-a-message-become-deferred"></a>¿Cómo se aplaza un mensaje?

Los mensajes se retienen cuando no se puede conectar con el servidor del destinatario y este devuelve un "error temporal" como que se agotó el tiempo de espera de la conexión, se rechazó la conexión o un error de tipo 400. Si se produce un error permanente, como un error de tipo 500, el mensaje se devuelve al remitente.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>¿Cuánto tiempo permanece aplazado un mensaje y cuál es el intervalo de reintento?

Los mensajes aplazados permanecerán en las colas durante 1 día. Los reintentos de envío de mensajes se basan en el error que se obtiene del sistema de correo del destinatario. Los primeros aplazamientos son de 15 minutos o menos, con reintentos posteriores (durante la siguiente media docenas o más) aumentando el intervalo durante varios reintentos a un máximo de 60 minutos. La expansión de la duración del intervalo es dinámica, teniendo en cuenta varias variables, como los tamaños de cola y la prioridad de los mensajes internos. En básico, el inicio es de 15 minutos (o menos) y, a continuación, se expande desde allí en las próximas horas a 60 minutos como máximo.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Después de que se restaura el servidor de correo electrónico, ¿cómo se distribuyen los mensajes en cola?

Después de que se restaura el servidor de correo electrónico, todos los mensajes en cola se procesan automáticamente en el orden en que se recibieron y se pusieron en cola cuando el servidor dejó de estar disponible.
