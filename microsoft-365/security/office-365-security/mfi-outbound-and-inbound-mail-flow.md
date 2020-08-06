---
title: Información de flujo de correo entrante y saliente en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Los administradores pueden obtener información sobre el conocimiento del flujo de correo entrante y saliente en el panel del flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 347e53c51c347f12795008d39458773a94ff433f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577395"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="b3ede-103">Visión del flujo de correo entrante y saliente en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b3ede-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="b3ede-104">La introducción al **flujo de correo entrante y** saliente del [Panel de flujo de correo](mail-flow-insights-v2.md) del centro de seguridad & cumplimiento combina la información del [Informe de conector](view-mail-flow-reports.md#connector-report) y del antiguo Informe de **información general de TLS** en un único punto.</span><span class="sxs-lookup"><span data-stu-id="b3ede-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="b3ede-105">El widget muestra el cifrado TLS que se usa para la conexión cuando los mensajes se entregan a la organización y desde ella.</span><span class="sxs-lookup"><span data-stu-id="b3ede-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="b3ede-106">Las conexiones que se establecen con otros servicios de correo electrónico se cifran mediante TLS cuando se ofrece TLS por ambas partes.</span><span class="sxs-lookup"><span data-stu-id="b3ede-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="b3ede-107">El widget ofrece una instantánea de la última semana del flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="b3ede-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget de flujo de correo entrante y saliente en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="b3ede-109">La información del widget está relacionada con los conectores y la protección de mensajes TLS en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3ede-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="b3ede-110">Para obtener más información, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="b3ede-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="b3ede-111">Configurar el flujo de correo mediante conectores</span><span class="sxs-lookup"><span data-stu-id="b3ede-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="b3ede-112">Uso de TLS por Exchange Online para proteger las conexiones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b3ede-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="b3ede-113">Detalles de referencia técnica sobre el cifrado en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3ede-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="b3ede-114">Mensaje protegido en tránsito (por TLS)</span><span class="sxs-lookup"><span data-stu-id="b3ede-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="b3ede-115">Al hacer clic en **Ver detalles** en el widget, el control flotante de **mensaje protegido en tránsito (por TLS)** muestra la protección de TLS para los mensajes que entran y salen de la organización.</span><span class="sxs-lookup"><span data-stu-id="b3ede-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Control flotante de mensajes protegidos en tránsito (mediante TLS) que aparece después de hacer clic en ver detalles en el widget de correo electrónico entrante y saliente](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="b3ede-117">Actualmente, TLS 1,2 es la versión más segura de TLS que ofrece Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3ede-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="b3ede-118">A menudo, necesitará conocer el cifrado de TLS que se usa para las auditorías de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b3ede-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="b3ede-119">Probablemente no tiene una relación directa con la mayoría de los servidores de correo electrónico de origen y de destino (no es propietario de ellos, ni tampoco Microsoft), por lo que no tiene muchas opciones para mejorar el cifrado de TLS que usan dichos servidores.</span><span class="sxs-lookup"><span data-stu-id="b3ede-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="b3ede-120">Sin embargo, puede usar [conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para garantizar la mejor protección de TLS disponible para los mensajes que se envían entre los servidores de correo electrónico y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3ede-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="b3ede-121">El flujo de correo entre Microsoft 365 y sus propios servidores de correo electrónico o servidores que pertenecen a sus socios suele ser más importante y sensible que los mensajes normales, por lo que querrá aplicar seguridad y vigilancia adicionales a dichos mensajes.</span><span class="sxs-lookup"><span data-stu-id="b3ede-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="b3ede-122">Puede actualizar o arreglar sus propios servidores de correo electrónico para mejorar el cifrado TLS que se está usando o llegar a sus asociados para hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="b3ede-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="b3ede-123">El **Informe de conectores** muestra el volumen del flujo de correo y el cifrado TLS para los mensajes que usan los conectores 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b3ede-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="b3ede-124">Puede hacer clic en el vínculo de **Informe de conector** para ir al [Informe de conector](view-mail-flow-reports.md#connector-report).</span><span class="sxs-lookup"><span data-stu-id="b3ede-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="b3ede-125">La siguiente información puede estar disponible en la página de **Informe de conector** si se ha detectado la condición asociada:</span><span class="sxs-lookup"><span data-stu-id="b3ede-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="b3ede-126">**Conector del asociado de entrada que ve un flujo de correo de TLS 1.0 importante**</span><span class="sxs-lookup"><span data-stu-id="b3ede-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="b3ede-127">**Conector local de entrada que ve un flujo de correo de TLS 1.0 importante**</span><span class="sxs-lookup"><span data-stu-id="b3ede-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="b3ede-128">Para las conexiones TLS 1,0, es necesario que el servidor de correo electrónico o el servidor de su compañero se actualice o se corrija para evitar problemas cuando la compatibilidad con TLS 1,0 está en desuso en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3ede-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3ede-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3ede-129">See also</span></span>

<span data-ttu-id="b3ede-130">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="b3ede-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
