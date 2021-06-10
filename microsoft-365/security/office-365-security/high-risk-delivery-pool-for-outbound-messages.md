---
title: Grupos de entrega de salida
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo se usan los grupos de entrega para proteger la reputación de los servidores de correo electrónico en Microsoft 365 centros de datos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599916"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="49eba-103">Grupos de entrega de salida</span><span class="sxs-lookup"><span data-stu-id="49eba-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="49eba-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="49eba-104">**Applies to**</span></span>
- [<span data-ttu-id="49eba-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="49eba-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="49eba-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="49eba-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="49eba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49eba-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="49eba-108">Los servidores de correo electrónico Microsoft 365 centros de datos podrían ser temporalmente responsables de enviar correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="49eba-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="49eba-109">Por ejemplo, un ataque de malware o correo no deseado malintencionado en una organización de correo electrónico local que envía correo saliente a través de Microsoft 365 o cuentas Microsoft 365 comprometidas.</span><span class="sxs-lookup"><span data-stu-id="49eba-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="49eba-110">Los atacantes también intentan evitar la detección retransmitiendo mensajes a través Microsoft 365 reenvío.</span><span class="sxs-lookup"><span data-stu-id="49eba-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="49eba-111">Estos escenarios pueden dar como resultado que la dirección IP de los servidores de centros de datos Microsoft 365 de datos afectados aparezcan en listas de bloqueo de terceros.</span><span class="sxs-lookup"><span data-stu-id="49eba-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="49eba-112">Las organizaciones de correo electrónico de destino que usan estas listas de bloqueo rechazarán el correo electrónico de esos orígenes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="49eba-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="49eba-113">Grupo de entrega de alto riesgo</span><span class="sxs-lookup"><span data-stu-id="49eba-113">High-risk delivery pool</span></span>
<span data-ttu-id="49eba-114">Para evitar esto, todos los mensajes salientes de servidores de centros de datos [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) de Microsoft 365 [](configure-the-outbound-spam-policy.md) que se determina que son correo no deseado o que superan los límites de envío del servicio o las directivas de correo no deseado saliente se envían a través del grupo de entrega de alto riesgo _._</span><span class="sxs-lookup"><span data-stu-id="49eba-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="49eba-115">El grupo de entrega de alto riesgo es un grupo de direcciones IP independiente para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y [backscatter](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="49eba-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="49eba-116">El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo saliente envíe correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="49eba-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="49eba-117">El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación enviando mensajes de "alta calidad", lo que reduce la probabilidad de que estas direcciones IP aparezcan en listas de direcciones IP bloqueados.</span><span class="sxs-lookup"><span data-stu-id="49eba-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="49eba-118">La posibilidad muy real de que las direcciones IP del grupo de entrega de alto riesgo se coloquen en listas de direcciones IP bloqueados permanece, pero esto es por diseño.</span><span class="sxs-lookup"><span data-stu-id="49eba-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="49eba-119">La entrega a los destinatarios previstos no está garantizada, ya que muchas organizaciones de correo electrónico no aceptarán mensajes del grupo de entrega de alto riesgo.</span><span class="sxs-lookup"><span data-stu-id="49eba-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="49eba-120">Para obtener más información, vea [Control outbound spam](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="49eba-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="49eba-121">Los mensajes en los que el dominio de correo electrónico de origen no tiene ningún registro A y ningún registro MX definido en DNS público siempre se enrutan a través del grupo de entrega de alto riesgo, independientemente de su correo no deseado o la eliminación del límite de envío.</span><span class="sxs-lookup"><span data-stu-id="49eba-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="49eba-122">Mensajes de rebote</span><span class="sxs-lookup"><span data-stu-id="49eba-122">Bounce messages</span></span>

<span data-ttu-id="49eba-123">El grupo de entrega de alto riesgo de salida administra la entrega de todos los informes de no entrega (también conocidos como NDR, mensajes de de rebote, notificaciones de estado de entrega o DSN).</span><span class="sxs-lookup"><span data-stu-id="49eba-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="49eba-124">Entre las causas posibles de un aumento de los NDR se incluyen:</span><span class="sxs-lookup"><span data-stu-id="49eba-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="49eba-125">Una campaña de suplantación de dominio que afecta a uno de los clientes que usan el servicio.</span><span class="sxs-lookup"><span data-stu-id="49eba-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="49eba-126">Un ataque de recolección de directorios.</span><span class="sxs-lookup"><span data-stu-id="49eba-126">A directory harvest attack.</span></span>
- <span data-ttu-id="49eba-127">Un ataque de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="49eba-127">A spam attack.</span></span>
- <span data-ttu-id="49eba-128">Un servidor de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="49eba-128">A rogue email server.</span></span>

<span data-ttu-id="49eba-129">Todos estos problemas pueden provocar un aumento repentino del número de NDR que procesa el servicio.</span><span class="sxs-lookup"><span data-stu-id="49eba-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="49eba-130">Muchas veces, estos NDR parecen ser correo no deseado para otros servidores de correo electrónico y servicios (también conocidos como _[backscatter](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="49eba-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
