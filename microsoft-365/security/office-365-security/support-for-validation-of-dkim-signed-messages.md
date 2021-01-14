---
title: Compatibilidad con la validación de mensajes firmados de claves de dominio identificadas con correo (DKIM)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Obtenga información sobre la validación de mensajes firmados por DKIM en Exchange Online Protection y Exchange Online
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845064"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="58125-103">Compatibilidad para la validación de mensajes firmados con DKIM</span><span class="sxs-lookup"><span data-stu-id="58125-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="58125-104">Exchange Online Protection (EOP) y Exchange Online admiten la validación entrante de los mensajes de correo identificado con claves de dominio[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="58125-104">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="58125-105">DKIM valida que un mensaje de correo electrónico no fue *suplantado* por otra persona y se envió desde el dominio del que *dice* que es de.</span><span class="sxs-lookup"><span data-stu-id="58125-105">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="58125-106">Vincula un mensaje de correo electrónico a la organización que lo envió.</span><span class="sxs-lookup"><span data-stu-id="58125-106">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="58125-107">La verificación DKIM se usa automáticamente para todos los mensajes enviados con IPv6.</span><span class="sxs-lookup"><span data-stu-id="58125-107">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="58125-108">Microsoft 365 también admite DKIM cuando se envía correo a través de IPv4.</span><span class="sxs-lookup"><span data-stu-id="58125-108">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="58125-109">(Para obtener más información acerca de la compatibilidad con IPv6, consulte [Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)).</span><span class="sxs-lookup"><span data-stu-id="58125-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="58125-110">DKIM valida un mensaje firmado digitalmente que aparece en el DKIM-Signature de los encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="58125-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="58125-111">Los resultados de una DKIM-Signature validación se marcan en el Authentication-Results encabezado.</span><span class="sxs-lookup"><span data-stu-id="58125-111">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="58125-112">El texto del encabezado del mensaje tiene un aspecto similar al siguiente (donde contoso.com es el remitente):</span><span class="sxs-lookup"><span data-stu-id="58125-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="58125-113">Para obtener más información acerca del encabezado Authentication-Results, vea RFC 7001 (campo de encabezado de mensaje para indicar el estado de[autenticación de mensajes).](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="58125-113">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="58125-114">La implementación dkim de Microsoft se ajusta a esta RFC.</span><span class="sxs-lookup"><span data-stu-id="58125-114">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="58125-115">Los administradores pueden crear reglas [de flujo de](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) correo de Exchange (también conocidas como reglas de transporte) en los resultados de la validación dkim.</span><span class="sxs-lookup"><span data-stu-id="58125-115">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="58125-116">Estas reglas de flujo de correo permitirán a los administradores filtrar o enrutar mensajes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="58125-116">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
