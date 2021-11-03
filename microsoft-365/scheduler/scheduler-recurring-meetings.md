---
title: Programación de reuniones periódicas dinámicas
ms.author: sarichardson
author: sallyri
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.reviewer: strettin
ms.localizationpriority: medium
description: Los usuarios pueden obtener más información sobre la programación de reuniones periódicas dinámicas.
ms.openlocfilehash: d4f99b336088e7c565c741a8f631e4fefbada68f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701394"
---
# <a name="scheduling-dynamic-recurring-meetings"></a>Programación de reuniones periódicas dinámicas

Las reuniones dinámicas del programador funcionan en torno a la programación de disponibilidad del usuario. Las reuniones periódicas administradas por Scheduler se comportan de forma diferente a las reuniones periódicas tradicionales en Outlook. Para mantener el calendario futuro abierto y minimizar los conflictos con los asistentes, scheduler programará una instancia de una reunión periódica a la vez.

Por ejemplo, si se Cortana "Programar 30 minutos de hora de enfoque cada día" se creará inicialmente una cita de 30 minutos para la siguiente fecha disponible en el calendario.  Una vez que haya transcurrido la hora de la cita, scheduler procederá a reservar otra instancia en la siguiente fecha. Si la franja horaria original no está disponible actualmente, el Programador ajustará la hora en función de su disponibilidad.

Se puede aplicar la misma heurística a las reuniones con invitados. Puede incluir asistentes en su solicitud y pedir Cortana "Programar una reunión cada dos semanas". La primera y cada reunión sucesiva se programarán dinámicamente en función de la disponibilidad actual de todos los asistentes de la organización. Si usted o un asistente no está disponible o está fuera de la oficina en la próxima fecha, la hora de la reunión se ajustará automáticamente a cuando todos estén disponibles y la cadencia deseada se conserva para las instancias de reunión de seguimiento según la fecha recién programada.

## <a name="booking-with-attendees-outside-your-organization"></a>Reserva con asistentes fuera de la organización

Al programar con asistentes fuera de la organización, el asistente virtual enviará las opciones de hora de los asistentes externos para la primera reunión. Todas las reuniones futuras se programan automáticamente en función de la disponibilidad del organizador y de los asistentes internos.

El programador admite intervalos diarios, semanales y mensuales.

## <a name="examples-of-how-to-request-recurring-meetings"></a>Ejemplos de cómo solicitar reuniones periódicas

Estos son algunos ejemplos de cómo puede enviar un correo Cortana para programar reuniones periódicas:

- "Cortana, programe una reunión cada 2 semanas".
- "Reserve 30 minutos mensuales para una revisión".
- "Cortana encontrará 30 minutos para que nos reúnamos todos los martes".
- "Cortana, programe 30 minutos cada viernes a las 15:30"

## <a name="changing-recurring-frequency"></a>Cambio de frecuencia periódica

Puede cambiar la frecuencia de cualquier reunión periódica o de una reunión no periódica administrada por scheduler. Responda a Cortana desde el último correo electrónico de confirmación en el subproceso de reunión y diga Cortana:

- "Cambie esto a una vez al mes".
- "Cortana, haga esta reunión quincenalmente."

## <a name="cancelling-recurring-meetings"></a>Cancelar reuniones periódicas

Puede responder al último mensaje de confirmación Cortana y solicitar "cancelar esta reunión" para cancelar la instancia programada. Sin embargo, el Programador seguirá programando futuras reuniones con la misma frecuencia. Como alternativa, solo puede solicitar al Programador que reprograme la siguiente instancia a la fecha u hora deseadas. Si desea cancelar toda la serie periódica, responda con "cancelar esta serie" y no se programarán instancias futuras.

## <a name="recurring-meeting-limitations"></a>Limitaciones de reunión periódicas

Tenga en cuenta que hay algunas limitaciones técnicas en los tipos de periodicidad que el programador puede comprender y admitir:

- No se admiten varias repeticiones dentro del mismo intervalo (por ejemplo: "dos veces a la semana").
- No se admiten fechas de finalización para la periodicidad (por ejemplo: "todos los días hasta el 20 de diciembre"). Dado que cada reunión está programada al finalizar la reunión anterior, simplemente responda al mensaje más reciente de Cortana con "cancelar esta serie de reuniones".
- El programador actualmente no admite frecuencias de periodicidad superiores a 90 días.
