---
title: Compatibilidad con la validación de mensajes firmados de claves de dominio (DKIM)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Obtenga información sobre la validación de mensajes firmados dkim en Exchange Online Protection y Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207347"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="2dff6-103">Compatibilidad para la validación de mensajes firmados con DKIM</span><span class="sxs-lookup"><span data-stu-id="2dff6-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2dff6-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="2dff6-104">**Applies to**</span></span>
- [<span data-ttu-id="2dff6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2dff6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2dff6-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2dff6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2dff6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2dff6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2dff6-108">Exchange Online Protection (EOP) y Exchange Online admiten la validación entrante de los mensajes de correo identificado de claves de dominio[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="2dff6-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="2dff6-109">DKIM valida que un mensaje de correo electrónico no fue *suplantado* por otra persona y se envió desde el dominio del que *dice* que provenía.</span><span class="sxs-lookup"><span data-stu-id="2dff6-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="2dff6-110">Vincula un mensaje de correo electrónico a la organización que lo envió.</span><span class="sxs-lookup"><span data-stu-id="2dff6-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="2dff6-111">La verificación DKIM se usa automáticamente para todos los mensajes enviados con IPv6.</span><span class="sxs-lookup"><span data-stu-id="2dff6-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="2dff6-112">Microsoft 365 también admite DKIM cuando se envía correo a través de IPv4.</span><span class="sxs-lookup"><span data-stu-id="2dff6-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="2dff6-113">(Para obtener más información acerca de la compatibilidad con IPv6, consulte [Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)).</span><span class="sxs-lookup"><span data-stu-id="2dff6-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="2dff6-114">DKIM valida un mensaje firmado digitalmente que aparece en el DKIM-Signature encabezado de los encabezados de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2dff6-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="2dff6-115">Los resultados de una DKIM-Signature validación se marcan en el Authentication-Results encabezado.</span><span class="sxs-lookup"><span data-stu-id="2dff6-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="2dff6-116">El texto del encabezado del mensaje tiene un aspecto similar al siguiente (donde contoso.com es el remitente):</span><span class="sxs-lookup"><span data-stu-id="2dff6-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="2dff6-117">Para obtener más información acerca del Authentication-Results, vea RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span><span class="sxs-lookup"><span data-stu-id="2dff6-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="2dff6-118">La implementación dkim de Microsoft se ajusta a esta RFC.</span><span class="sxs-lookup"><span data-stu-id="2dff6-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="2dff6-119">Los administradores pueden crear Exchange [de flujo](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) de correo (también conocidas como reglas de transporte) en los resultados de la validación DKIM.</span><span class="sxs-lookup"><span data-stu-id="2dff6-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="2dff6-120">Estas reglas de flujo de correo permitirán a los administradores filtrar o enrutar mensajes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2dff6-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>