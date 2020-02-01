---
title: Mensajes de reenvío masivo de correo electrónico y EOP
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
description: Los mensajes de reenvío masivo son mensajes de devolución automatizados que se envían a direcciones de correo electrónico falsificadas. La DNSBL de la indispersión identifica los servidores que envían mensajes de reenvío masivo (que pueden incluir muchos orígenes de correo electrónico legítimos). Dado que no se trata de una lista de remitentes de correo no deseado, no tratamos de eliminarlas de la DNSBL.
ms.openlocfilehash: 3dc83c303e861c8762f2276de521e1b550ae2e59
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599737"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="45139-105">Mensajes de reenvío masivo de correo electrónico y EOP</span><span class="sxs-lookup"><span data-stu-id="45139-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="45139-106">*Los mensajes* de reenvío masivo son informes de no entrega (también conocidos como NDR o mensajes de devolución) que se reciben para los mensajes que no se enviaron.</span><span class="sxs-lookup"><span data-stu-id="45139-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="45139-107">Los remitentes de correo no deseado falsifican (suplantan) la dirección de: de sus mensajes y suelen usar direcciones de correo electrónico reales para prestar credibilidad a sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="45139-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="45139-108">Por lo tanto, cuando envían mensajes inevitablemente a destinatarios no existentes (el correo no deseado es una operación de gran volumen), es posible que el servidor de correo electrónico de destino responda dutifully con un NDR, que se envía al remitente falsificado en la dirección from:.</span><span class="sxs-lookup"><span data-stu-id="45139-108">So, when they inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server might dutifully respond with an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="45139-109">Exchange Online Protection (EOP) hace todo lo posible para identificar y eliminar silenciosamente los mensajes de fuentes dudosas sin generar un NDR.</span><span class="sxs-lookup"><span data-stu-id="45139-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="45139-110">Pero, a partir de la gran cantidad de correo electrónico que fluye a través del servicio, siempre hay la posibilidad de que EOP envíe mensajes posdispersos de forma involuntaria.</span><span class="sxs-lookup"><span data-stu-id="45139-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="45139-111">Backscatterer.org mantiene una lista de bloqueados (también conocida como una lista de bloqueados de DNS o DNSBL) de los servidores de correo electrónico responsables del envío de mensajes de reenvío masivo, y es posible que aparezcan en esta lista los servidores de EOP.</span><span class="sxs-lookup"><span data-stu-id="45139-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="45139-112">Pero no estamos intentando eliminarlas de la lista de bloqueadores de Backscatterer.org porque no es una lista de remitentes de correo no deseado (por su propia admisión).</span><span class="sxs-lookup"><span data-stu-id="45139-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="45139-113">De acuerdo con el servicio de dispersión. o`http://www.backscatterer.org/?target=usage`el sitio web (), se recomienda usar el servicio para comprobar el correo electrónico entrante en modo seguro en lugar de rechazar el modo (los servicios de correo electrónico grandes casi siempre envían mensajes de reenvío masivo).</span><span class="sxs-lookup"><span data-stu-id="45139-113">According to the Backscatter.or website (`http://www.backscatterer.org/?target=usage`), they recommend using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
