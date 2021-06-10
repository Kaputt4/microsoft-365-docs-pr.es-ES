---
title: Información sobre el flujo de correo entrante y saliente en el panel flujo de correo
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
description: Los administradores pueden obtener información sobre el flujo de correo saliente y entrante en el panel flujo de correo en el Centro de seguridad & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205299"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="51293-103">Información sobre el flujo de correo entrante y saliente en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="51293-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="51293-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="51293-104">**Applies to**</span></span>
- [<span data-ttu-id="51293-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="51293-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="51293-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="51293-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="51293-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51293-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="51293-108">La **información de flujo** de [](mail-flow-insights-v2.md) correo saliente y entrante en el panel flujo de correo del Centro de seguridad [& cumplimiento](https://protection.office.com) combina la información del informe [de Conector](view-mail-flow-reports.md#connector-report) y el informe de información general de **TLS** anterior en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="51293-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="51293-109">El widget muestra el cifrado TLS que se usa para la conexión cuando se entregan mensajes desde y hacia su organización.</span><span class="sxs-lookup"><span data-stu-id="51293-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="51293-110">Las conexiones establecidas con otros servicios de correo electrónico se cifran mediante TLS cuando TLS se ofrece por ambas partes.</span><span class="sxs-lookup"><span data-stu-id="51293-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="51293-111">El widget ofrece una instantánea de la última semana de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="51293-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget de flujo de correo entrante y saliente en el panel Flujo de correo del Centro de seguridad & cumplimiento](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="51293-113">La información del widget está relacionada con conectores y protección de mensajes TLS en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51293-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="51293-114">Para obtener más información, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="51293-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="51293-115">Configurar un flujo de correo mediante conectores</span><span class="sxs-lookup"><span data-stu-id="51293-115">Configure mail flow using connectors</span></span>](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="51293-116">Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="51293-116">How Exchange Online uses TLS to secure email connections</span></span>](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [<span data-ttu-id="51293-117">Detalles de referencia técnica sobre el cifrado en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51293-117">Technical reference details about encryption in Microsoft 365</span></span>](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="51293-118">Mensaje protegido en tránsito (por TLS)</span><span class="sxs-lookup"><span data-stu-id="51293-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="51293-119">Al hacer clic en **Ver** detalles en el widget, el control flotante Mensaje protegido en tránsito **(por TLS)** muestra la protección TLS para los mensajes que entran y salen de la organización.</span><span class="sxs-lookup"><span data-stu-id="51293-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Mensajes protegidos en tránsito (por TLS) flotante que aparecen después de hacer clic en Ver detalles en el widget de correo electrónico saliente y entrante](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="51293-121">Actualmente, TLS 1.2 es la versión más segura de TLS que ofrece Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51293-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="51293-122">A menudo, necesitará conocer el cifrado TLS que se usa para las auditorías de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="51293-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="51293-123">Probablemente no tenga una relación directa con la mayoría de los servidores de correo electrónico de origen y destino (no los posee ni Microsoft), por lo que no tiene muchas opciones para mejorar el cifrado TLS que usan esos servidores.</span><span class="sxs-lookup"><span data-stu-id="51293-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="51293-124">Sin embargo, puede usar conectores [para](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) garantizar la mejor protección TLS disponible para los mensajes que se envían entre los servidores de correo electrónico y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51293-124">But, you can use [connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="51293-125">El flujo de correo entre Microsoft 365 y sus propios servidores de correo electrónico o servidores que pertenecen a sus socios suele ser más importante y confidencial que los mensajes normales, por lo que querrá aplicar seguridad y vigilancia adicionales a esos mensajes.</span><span class="sxs-lookup"><span data-stu-id="51293-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="51293-126">Puede actualizar o corregir sus propios servidores de correo electrónico para mejorar el cifrado TLS que se está utilizando o comunicarse con sus asociados para hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="51293-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="51293-127">El **informe de conector** muestra el volumen de flujo de correo y el cifrado TLS para los mensajes que usan los conectores Microsoft 365 correo.</span><span class="sxs-lookup"><span data-stu-id="51293-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="51293-128">Puede hacer clic en el **vínculo Informe de conector** para ir al informe de [Conector.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="51293-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="51293-129">Las siguientes perspectivas podrían estar disponibles en la página de informe **de Connector** si se ha detectado la condición asociada:</span><span class="sxs-lookup"><span data-stu-id="51293-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="51293-130">**Conector de partner entrante que ve un flujo de correo TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="51293-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="51293-131">**Conector Entrante OnPremises que ve un flujo de correo TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="51293-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="51293-132">Para las conexiones TLS 1.0, realmente necesita actualizar o solucionar el servidor de correo electrónico o el servidor de su partner para evitar cualquier problema cuando la compatibilidad con TLS 1.0 esté en desuso en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51293-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="51293-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51293-133">See also</span></span>

<span data-ttu-id="51293-134">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="51293-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>