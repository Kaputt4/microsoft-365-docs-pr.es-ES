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
description: En este artículo, aprenderá sobre protección contra correo electrónico no Microsoft Exchange Online (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165960"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="83352-103">Reenvío masivo de correo electrónico en EOP</span><span class="sxs-lookup"><span data-stu-id="83352-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="83352-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="83352-104">**Applies to**</span></span>
- [<span data-ttu-id="83352-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="83352-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="83352-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="83352-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="83352-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83352-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="83352-108">*El correo electrónico no* enviado son informes de no entrega (también conocidos como NDRs o mensajes de de rebote) que recibe para los mensajes que no envió.</span><span class="sxs-lookup"><span data-stu-id="83352-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="83352-109">Los spammers falsificar (suplantar) la dirección De: de sus mensajes y, a menudo, usan direcciones de correo electrónico reales para dar crédito a sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="83352-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="83352-110">Por lo tanto, cuando los spammers inevitablemente envían mensajes a destinatarios inexistentes (el correo no deseado es una operación de gran volumen), el servidor de correo electrónico de destino es esencialmente complicado para devolver el mensaje que no se puede entregar en un NDR al remitente falsificado en la dirección De:.</span><span class="sxs-lookup"><span data-stu-id="83352-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="83352-111">En organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP hace todo lo posible por identificar y colocar mensajes de orígenes dudosos sin generar un NDR.</span><span class="sxs-lookup"><span data-stu-id="83352-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="83352-112">Pero, en función del gran volumen de correo electrónico que fluye a través del servicio, siempre existe la posibilidad de que EOP envíe de forma involuntaria el correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="83352-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="83352-113">Backscatterer.org mantiene una lista de bloqueados (también conocida como una lista de bloqueados DNS o DNSBL) de servidores de correo electrónico responsables de enviar reenvío de correo electrónico no deseado, y los servidores EOP pueden aparecer en esta lista.</span><span class="sxs-lookup"><span data-stu-id="83352-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="83352-114">Pero no intentamos quitarnos de la lista de bloqueados de Backscatterer.org porque no es una lista de spammers (por su propia admisión).</span><span class="sxs-lookup"><span data-stu-id="83352-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="83352-115">El Backscatter.org web de correo electrónico ( ) recomienda usar su servicio para comprobar el correo electrónico entrante en modo seguro en lugar del modo de rechazo (los servicios de correo electrónico grandes casi siempre envían algo de correo <http://www.backscatterer.org/?target=usage> electrónico no deseado).</span><span class="sxs-lookup"><span data-stu-id="83352-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
