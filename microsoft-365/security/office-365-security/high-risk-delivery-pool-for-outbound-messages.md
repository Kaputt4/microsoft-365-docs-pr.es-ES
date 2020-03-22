---
title: Grupo de entrega de alto riesgo para mensajes salientes
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo se usa el grupo de entrega de alto riesgo para proteger la reputación de los servidores de correo electrónico en los centros de información de Office 365.
ms.openlocfilehash: 5d1bd2b14eb17ed74ee1cf1e44967f660f4595b8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895364"
---
# <a name="high-risk-delivery-pool-for-outbound-messages-in-office-365"></a><span data-ttu-id="c01c6-103">Grupo de entrega de alto riesgo para mensajes salientes en Office 365</span><span class="sxs-lookup"><span data-stu-id="c01c6-103">High-risk delivery pool for outbound messages in Office 365</span></span>

<span data-ttu-id="c01c6-104">Los servidores de correo electrónico de los centros de recursos de Office 365 pueden ser temporalmente culpables de enviar correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c01c6-104">Email servers in the Office 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="c01c6-105">Por ejemplo, un ataque de malware o de correo no deseado en una organización de correo electrónico local que envía correo saliente a través de Office 365 o cuentas de Office 365 comprometidas.</span><span class="sxs-lookup"><span data-stu-id="c01c6-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Office 365, or compromised Office 365 accounts.</span></span> <span data-ttu-id="c01c6-106">Estos escenarios pueden dar como resultado la dirección IP de los servidores de Office 365 Datacenter Server afectados que aparecen en las listas de bloqueados de terceros.</span><span class="sxs-lookup"><span data-stu-id="c01c6-106">These scenarios can result in the IP address of the affected Office 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="c01c6-107">Las organizaciones de correo electrónico de destino que usen estas listas de bloqueo rechazarán el correo electrónico de esos orígenes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c01c6-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="c01c6-108">Para evitarlo, todos los mensajes salientes de los servidores de centro de [servicios](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) de Office 365 que se determine que son correo no deseado o que superen los límites de envío del servicio o [las directivas de correo no deseado salientes](configure-the-outbound-spam-policy.md) se envían a través del _grupo de entrega de alto riesgo_.</span><span class="sxs-lookup"><span data-stu-id="c01c6-108">To prevent this, all outbound messages from Office 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="c01c6-109">El grupo de entrega de alto riesgo es un grupo de direcciones IP secundarias para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y [dispersión](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="c01c6-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="c01c6-110">El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo electrónico saliente envíe correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c01c6-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="c01c6-111">El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación enviando mensajes de "alta calidad", lo que reduce la probabilidad de que esta dirección IP aparezca en las listas de direcciones IP bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="c01c6-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="c01c6-112">La posibilidad muy real de que las direcciones IP en el grupo de entrega de alto riesgo se coloquen en las listas de bloqueo de IP, pero esto es así por diseño.</span><span class="sxs-lookup"><span data-stu-id="c01c6-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="c01c6-113">La entrega a los destinatarios deseados no está garantizada porque muchas organizaciones de correo electrónico no aceptan mensajes del grupo de entrega de alto riesgo.</span><span class="sxs-lookup"><span data-stu-id="c01c6-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="c01c6-114">Para obtener más información, consulte [controlar el correo no deseado saliente en Office 365](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="c01c6-114">For more information, see [Control outbound spam in Office 365](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c01c6-115">Los mensajes en los que el dominio de correo electrónico de origen no tiene ningún registro A y no MX definido en DNS público siempre se redirigen a través del grupo de entrega de alto riesgo, independientemente de su correo no deseado o la disposición del límite de envío.</span><span class="sxs-lookup"><span data-stu-id="c01c6-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="c01c6-116">Mensajes de devolución</span><span class="sxs-lookup"><span data-stu-id="c01c6-116">Bounce messages</span></span>

<span data-ttu-id="c01c6-117">El grupo de entrega de alto riesgo saliente administra la entrega de todos los informes de no entrega (también conocidos como NDR, mensajes de devolución, notificaciones de estado de entrega o DSN).</span><span class="sxs-lookup"><span data-stu-id="c01c6-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="c01c6-118">Entre las posibles causas de un aumento de NDR se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c01c6-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="c01c6-119">Una campaña de suplantación de identidad que afecta a uno de los clientes que usan el servicio.</span><span class="sxs-lookup"><span data-stu-id="c01c6-119">A spoofing campaign that affects one of the customers using the service.</span></span>

- <span data-ttu-id="c01c6-120">Un ataque de recopilación de directorios.</span><span class="sxs-lookup"><span data-stu-id="c01c6-120">A directory harvest attack.</span></span>

- <span data-ttu-id="c01c6-121">Un ataque de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c01c6-121">A spam attack.</span></span>

- <span data-ttu-id="c01c6-122">Un servidor de correo electrónico malintencionado.</span><span class="sxs-lookup"><span data-stu-id="c01c6-122">A rogue email server.</span></span>

<span data-ttu-id="c01c6-123">Todos estos problemas pueden dar como resultado un aumento repentino del número de NDR que procesa el servicio.</span><span class="sxs-lookup"><span data-stu-id="c01c6-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="c01c6-124">Muchas veces, estos NDR parecen ser correo no deseado para otros servidores y servicios de correo electrónico (también conocido como _[redispersión](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="c01c6-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
