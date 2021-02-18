---
title: Información sobre el flujo de correo entrante y saliente en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Los administradores pueden obtener información sobre el flujo de correo entrante y saliente en el panel flujo de correo en el Centro de & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87c5bd9ab0d550f50feabbb96176debbe04863e5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289454"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="27ef8-103">Información sobre el flujo de correo entrante y saliente en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="27ef8-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="27ef8-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="27ef8-104">**Applies to**</span></span>
- [<span data-ttu-id="27ef8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="27ef8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="27ef8-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="27ef8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="27ef8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27ef8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="27ef8-108">La **información sobre** el flujo [](mail-flow-insights-v2.md) de correo entrante y saliente en el panel de [](view-mail-flow-reports.md#connector-report) flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) combina la información del informe del conector y el anterior informe de información general de **TLS** en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="27ef8-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="27ef8-109">El widget muestra el cifrado TLS que se usa para la conexión cuando los mensajes se entregan a y desde su organización.</span><span class="sxs-lookup"><span data-stu-id="27ef8-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="27ef8-110">Las conexiones establecidas con otros servicios de correo electrónico se cifran mediante TLS cuando ambos lados ofrecen TLS.</span><span class="sxs-lookup"><span data-stu-id="27ef8-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="27ef8-111">El widget ofrece una instantánea de la última semana de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="27ef8-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget Flujo de correo entrante y saliente en el panel flujo de correo en el Centro de & cumplimiento](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="27ef8-113">La información del widget está relacionada con los conectores y la protección de mensajes TLS en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ef8-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="27ef8-114">Para obtener más información, consulte estos temas:</span><span class="sxs-lookup"><span data-stu-id="27ef8-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="27ef8-115">Configurar el flujo de correo mediante conectores</span><span class="sxs-lookup"><span data-stu-id="27ef8-115">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="27ef8-116">Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="27ef8-116">How Exchange Online uses TLS to secure email connections</span></span>](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [<span data-ttu-id="27ef8-117">Detalles de referencia técnica sobre el cifrado en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27ef8-117">Technical reference details about encryption in Microsoft 365</span></span>](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="27ef8-118">Mensaje protegido en tránsito (por TLS)</span><span class="sxs-lookup"><span data-stu-id="27ef8-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="27ef8-119">Al hacer clic **en** Ver detalles en el widget, el control flotante Mensaje protegido en tránsito **(por TLS)** muestra la protección TLS para los mensajes que entran y salen de la organización.</span><span class="sxs-lookup"><span data-stu-id="27ef8-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Mensajes protegidos en tránsito (por TLS) que aparecen después de hacer clic en Ver detalles en el widget Correo electrónico saliente y entrante](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="27ef8-121">Actualmente, TLS 1.2 es la versión más segura de TLS que ofrece Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ef8-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="27ef8-122">A menudo, debe conocer el cifrado TLS que se usa para las auditorías de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="27ef8-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="27ef8-123">Es probable que no tenga una relación directa con la mayoría de los servidores de correo electrónico de origen y de destino (no es el propietario y tampoco Microsoft), por lo que no tiene muchas opciones para mejorar el cifrado TLS que usan esos servidores.</span><span class="sxs-lookup"><span data-stu-id="27ef8-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="27ef8-124">Pero puede usar conectores [para](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) garantizar la mejor protección TLS disponible para los mensajes que se envían entre los servidores de correo electrónico y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ef8-124">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="27ef8-125">El flujo de correo entre Microsoft 365 y sus propios servidores de correo electrónico o servidores que pertenecen a sus asociados suele ser más importante y confidencial que los mensajes normales, por lo que le será más fácil aplicar seguridad y atención adicionales a esos mensajes.</span><span class="sxs-lookup"><span data-stu-id="27ef8-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="27ef8-126">Puede actualizar o corregir sus propios servidores de correo electrónico para mejorar el cifrado TLS que se está utilizando, o comunicarse con sus asociados para hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="27ef8-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="27ef8-127">El **informe de conectores** muestra el volumen de flujo de correo y el cifrado TLS para los mensajes que usan los conectores de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ef8-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="27ef8-128">Puede hacer clic en el **vínculo informe del** conector para ir al informe del [conector.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="27ef8-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="27ef8-129">Las siguientes conclusiones pueden estar disponibles en la página **del informe** del conector si se ha detectado la condición asociada:</span><span class="sxs-lookup"><span data-stu-id="27ef8-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="27ef8-130">**Conector de asociado de entrada que ve un flujo de correo TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="27ef8-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="27ef8-131">**Conector OnPremises entrante que ve un flujo de correo TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="27ef8-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="27ef8-132">Para las conexiones TLS 1.0, realmente necesita actualizar o solucionar el servidor de correo electrónico o el servidor de su socio para evitar problemas cuando el soporte técnico de TLS 1.0 finalmente está en desuso en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ef8-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="27ef8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="27ef8-133">See also</span></span>

<span data-ttu-id="27ef8-134">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="27ef8-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
