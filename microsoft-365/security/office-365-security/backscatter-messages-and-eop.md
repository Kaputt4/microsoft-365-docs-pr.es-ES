---
title: Retrodispersión y EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: La dispersión es mensajes de devolución automatizada que se envían a direcciones de correo electrónico falsificadas. La DNSBL de la indispersión identifica los servidores que envían mensajes de reenvío masivo (que pueden incluir muchos orígenes de correo electrónico legítimos). Dado que no se trata de una lista de remitentes de correo no deseado, no tratamos de eliminarlas de la DNSBL.
ms.openlocfilehash: 22eeec29722cf1742e096234aad95b9f6ee407e2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895410"
---
# <a name="backscatter-and-eop"></a><span data-ttu-id="bc061-105">Retrodispersión y EOP</span><span class="sxs-lookup"><span data-stu-id="bc061-105">Backscatter and EOP</span></span>

<span data-ttu-id="bc061-106">La *dispersión* es un informe de no entrega (también conocido como NDR o mensajes de devolución) que recibe para los mensajes que no ha enviado.</span><span class="sxs-lookup"><span data-stu-id="bc061-106">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="bc061-107">Los remitentes de correo no deseado falsifican (suplantan) la dirección de: de sus mensajes y suelen usar direcciones de correo electrónico reales para prestar credibilidad a sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="bc061-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="bc061-108">Por lo tanto, cuando los remitentes de correo no deseado envían mensajes a destinatarios inexistentes (el correo no deseado es un gran volumen de operaciones), el servidor de correo electrónico de destino se complica básicamente a devolver el mensaje que no se entrega en un NDR al remitente falsificado en la dirección from:.</span><span class="sxs-lookup"><span data-stu-id="bc061-108">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="bc061-109">Exchange Online Protection (EOP) hace todo lo posible para identificar y eliminar silenciosamente los mensajes de fuentes dudosas sin generar un NDR.</span><span class="sxs-lookup"><span data-stu-id="bc061-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="bc061-110">Pero, en función de la gran cantidad de correo electrónico que fluye a través del servicio, siempre existe la posibilidad de que EOP envíe involuntariamente el servicio de dispersión.</span><span class="sxs-lookup"><span data-stu-id="bc061-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="bc061-111">Backscatterer.org mantiene una lista de bloqueados (también conocida como una lista de bloqueados de DNS o DNSBL) de los servidores de correo electrónico que eran responsables del envío de la copia de fondo y los servidores EOP podrían aparecer en esta lista.</span><span class="sxs-lookup"><span data-stu-id="bc061-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="bc061-112">Pero no estamos intentando eliminarlas de la lista de bloqueadores de Backscatterer.org porque no es una lista de remitentes de correo no deseado (por su propia admisión).</span><span class="sxs-lookup"><span data-stu-id="bc061-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="bc061-113">El sitio web de<http://www.backscatterer.org/?target=usage>Backscatter.org () recomienda usar su servicio para comprobar el correo electrónico entrante en modo seguro en lugar de rechazar el modo (los servicios de correo electrónico de gran tamaño casi siempre envían algún indispersión).</span><span class="sxs-lookup"><span data-stu-id="bc061-113">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
