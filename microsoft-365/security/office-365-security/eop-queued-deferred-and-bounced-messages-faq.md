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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Encuentre respuestas a las preguntas más frecuentes sobre los mensajes que se han puesto en cola, aplazados o devueltos durante el proceso de filtrado de Exchange Online Protection (EOP).
ms.openlocfilehash: 4ae38e871c0d6e4321bd7586c5cfd0bea3aeef81
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202944"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="db09a-103">Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP</span><span class="sxs-lookup"><span data-stu-id="db09a-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="db09a-104">En este tema se proporcionan respuestas a las preguntas más frecuentes acerca de los mensajes que se han puesto en cola, aplazados o devueltos durante el proceso de filtrado de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="db09a-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="db09a-105">¿Por qué se pone el correo en cola?</span><span class="sxs-lookup"><span data-stu-id="db09a-105">Why is mail queuing?</span></span>

<span data-ttu-id="db09a-106">Los mensajes se ponen en cola o se aplazan si el servicio no puede establecer una conexión con el servidor del destinatario para la entrega.</span><span class="sxs-lookup"><span data-stu-id="db09a-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="db09a-107">Los mensajes no se aplazan si la red del destinatario devuelve un error de tipo 500.</span><span class="sxs-lookup"><span data-stu-id="db09a-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="db09a-108">¿Cómo se aplaza un mensaje?</span><span class="sxs-lookup"><span data-stu-id="db09a-108">How does a message become deferred?</span></span>

<span data-ttu-id="db09a-109">Los mensajes se retienen cuando no se puede conectar con el servidor del destinatario y este devuelve un "error temporal" como que se agotó el tiempo de espera de la conexión, se rechazó la conexión o un error de tipo 400.</span><span class="sxs-lookup"><span data-stu-id="db09a-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="db09a-110">Si se produce un error permanente, como un error de tipo 500, el mensaje se devuelve al remitente.</span><span class="sxs-lookup"><span data-stu-id="db09a-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="db09a-111">¿Cuánto tiempo permanece aplazado un mensaje y cuál es el intervalo de reintento?</span><span class="sxs-lookup"><span data-stu-id="db09a-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="db09a-112">Los mensajes en aplazamientos permanecerán en nuestras colas por 1 día.</span><span class="sxs-lookup"><span data-stu-id="db09a-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="db09a-113">Los reintentos de envío de mensajes se basan en el error que se obtiene del sistema de correo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="db09a-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="db09a-114">Los primeros aplazamientos son de 15 minutos o menos, con reintentos posteriores (en las próximas mitades o más), lo que aumenta el intervalo en varios reintentos hasta un máximo de 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="db09a-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="db09a-115">La expansión de la duración del intervalo es dinámica, teniendo en cuenta varias variables como los tamaños de las colas y la prioridad de mensajes interna.</span><span class="sxs-lookup"><span data-stu-id="db09a-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="db09a-116">En Basic, tiene 15 minutos (o menos) para comenzar y, a continuación, se expande a partir de las próximas horas a 60 min máx.</span><span class="sxs-lookup"><span data-stu-id="db09a-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="db09a-117">Después de que se restaura el servidor de correo electrónico, ¿cómo se distribuyen los mensajes en cola?</span><span class="sxs-lookup"><span data-stu-id="db09a-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="db09a-118">Después de que se restaura el servidor de correo electrónico, todos los mensajes en cola se procesan automáticamente en el orden en que se recibieron y se pusieron en cola cuando el servidor dejó de estar disponible.</span><span class="sxs-lookup"><span data-stu-id="db09a-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
