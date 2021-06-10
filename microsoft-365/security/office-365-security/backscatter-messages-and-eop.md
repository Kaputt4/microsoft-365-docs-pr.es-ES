---
title: Reenvío masivo de correo electrónico en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá sobre Backscatter y Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205110"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="40165-103">Reenvío masivo de correo electrónico en EOP</span><span class="sxs-lookup"><span data-stu-id="40165-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="40165-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="40165-104">**Applies to**</span></span>
- [<span data-ttu-id="40165-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="40165-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="40165-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="40165-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="40165-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40165-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="40165-108">*Backscatter* son informes de no entrega (también conocidos como NDR o mensajes de rebote) que recibe para los mensajes que no envió.</span><span class="sxs-lookup"><span data-stu-id="40165-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="40165-109">Los emisores de correo electrónico no deseado falsifican (suplantan electrónicamente) la dirección De: de sus mensajes y, a menudo, utilizan direcciones de correo electrónico reales para dar credibilidad a sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="40165-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="40165-110">Por lo tanto, cuando los spammers envían mensajes inevitablemente a destinatarios inexistentes (el correo no deseado es una operación de gran volumen), el servidor de correo electrónico de destino es esencialmente engañado para devolver el mensaje no entregado en un NDR al remitente falsificado en la dirección De: .</span><span class="sxs-lookup"><span data-stu-id="40165-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="40165-111">En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP hace todo lo posible para identificar y colocar mensajes de orígenes dudosos sin generar un NDR.</span><span class="sxs-lookup"><span data-stu-id="40165-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="40165-112">Pero, en función del gran volumen de correo electrónico que fluye a través del servicio, siempre existe la posibilidad de que EOP envíe de forma involuntaria backscatter.</span><span class="sxs-lookup"><span data-stu-id="40165-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="40165-113">Backscatterer.org mantiene una lista de bloqueo (también conocida como lista de bloques DNS o DNSBL) de servidores de correo electrónico que eran responsables de enviar backscatter, y los servidores EOP podrían aparecer en esta lista.</span><span class="sxs-lookup"><span data-stu-id="40165-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="40165-114">Pero no intentamos quitarnos de la lista de Backscatterer.org porque no es una lista de spammers (por su propia admisión).</span><span class="sxs-lookup"><span data-stu-id="40165-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="40165-115">El Backscatter.org web de Backscatter.org ( ) recomienda usar su servicio para comprobar el correo electrónico entrante en modo Caja fuerte en lugar del modo de rechazo (los servicios de correo electrónico grandes casi siempre envían algún <http://www.backscatterer.org/?target=usage> backscatter).</span><span class="sxs-lookup"><span data-stu-id="40165-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
