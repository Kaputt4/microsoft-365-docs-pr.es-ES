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
description: Encuentre respuestas a las preguntas más comunes sobre los mensajes que se han puesto en cola, diferidos o devueltos durante el proceso de filtrado de Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207479"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="a1b25-103">Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP</span><span class="sxs-lookup"><span data-stu-id="a1b25-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a1b25-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="a1b25-104">**Applies to**</span></span>
- [<span data-ttu-id="a1b25-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a1b25-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a1b25-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a1b25-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a1b25-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1b25-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a1b25-108">En este tema se proporcionan respuestas a las preguntas más frecuentes sobre los mensajes que se han puesto en cola, aplazados o devueltos durante el proceso de filtrado de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a1b25-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="a1b25-109">¿Por qué se pone el correo en cola?</span><span class="sxs-lookup"><span data-stu-id="a1b25-109">Why is mail queuing?</span></span>

<span data-ttu-id="a1b25-110">Los mensajes se ponen en cola o se aplazan si el servicio no puede establecer una conexión con el servidor del destinatario para la entrega.</span><span class="sxs-lookup"><span data-stu-id="a1b25-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="a1b25-111">Los mensajes no se aplazan si la red del destinatario devuelve un error de tipo 500.</span><span class="sxs-lookup"><span data-stu-id="a1b25-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="a1b25-112">¿Cómo se aplaza un mensaje?</span><span class="sxs-lookup"><span data-stu-id="a1b25-112">How does a message become deferred?</span></span>

<span data-ttu-id="a1b25-113">Los mensajes se retienen cuando no se puede conectar con el servidor del destinatario y este devuelve un "error temporal" como que se agotó el tiempo de espera de la conexión, se rechazó la conexión o un error de tipo 400.</span><span class="sxs-lookup"><span data-stu-id="a1b25-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="a1b25-114">Si se produce un error permanente, como un error de tipo 500, el mensaje se devuelve al remitente.</span><span class="sxs-lookup"><span data-stu-id="a1b25-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="a1b25-115">¿Cuánto tiempo permanece aplazado un mensaje y cuál es el intervalo de reintento?</span><span class="sxs-lookup"><span data-stu-id="a1b25-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="a1b25-116">Los mensajes en aplazamiento permanecerán en nuestras colas durante 1 día.</span><span class="sxs-lookup"><span data-stu-id="a1b25-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="a1b25-117">Los reintentos de envío de mensajes se basan en el error que se obtiene del sistema de correo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="a1b25-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="a1b25-118">Los primeros aplazamientos son de 15 minutos o menos, y los reintentos posteriores (durante la siguiente media docena aproximadamente) aumentan el intervalo durante varios reintentos a un máximo de 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="a1b25-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="a1b25-119">La expansión de la duración del intervalo es dinámica, teniendo en cuenta varias variables, como los tamaños de cola y la prioridad del mensaje interno.</span><span class="sxs-lookup"><span data-stu-id="a1b25-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="a1b25-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span><span class="sxs-lookup"><span data-stu-id="a1b25-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="a1b25-121">Después de que se restaura el servidor de correo electrónico, ¿cómo se distribuyen los mensajes en cola?</span><span class="sxs-lookup"><span data-stu-id="a1b25-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="a1b25-122">Después de que se restaura el servidor de correo electrónico, todos los mensajes en cola se procesan automáticamente en el orden en que se recibieron y se pusieron en cola cuando el servidor dejó de estar disponible.</span><span class="sxs-lookup"><span data-stu-id="a1b25-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
