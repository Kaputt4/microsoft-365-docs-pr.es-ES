---
title: Información de mensajes reenviados automáticamente
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel flujo de correo del Centro de seguridad & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207326"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="33302-103">Información de mensajes reenviados automáticamente en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="33302-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33302-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="33302-104">**Applies to**</span></span>
- [<span data-ttu-id="33302-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="33302-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="33302-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="33302-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="33302-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33302-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="33302-108">La **información de mensajes** reenviados automáticamente en el panel flujo de correo del Centro de seguridad & cumplimiento muestra información sobre los mensajes que se reenvía automáticamente desde su organización [a](https://protection.office.com) los destinatarios de dominios externos. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="33302-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget de mensajes reenviados automáticamente en el Centro de seguridad & cumplimiento](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="33302-110">Detalles de mensajes reenviados automáticamente</span><span class="sxs-lookup"><span data-stu-id="33302-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="33302-111">Al hacer clic en el número de mensajes del widget, aparece un panel flotante que muestra más información sobre los mensajes reenviados automáticamente:</span><span class="sxs-lookup"><span data-stu-id="33302-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="33302-112">**Mensajes reenviados automáticamente mediante métodos de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="33302-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="33302-113">**Por reglas de flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="33302-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="33302-114">**Por reglas de la Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="33302-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="33302-115">**Mediante reenvío SMTP:** este método indica el reenvío automático que los administradores pueden configurar en un buzón, tal como se describe en [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="33302-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="33302-116">Un vínculo al informe [de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33302-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="33302-117">**Mensajes reenviados automáticamente por dominios y usuarios:**</span><span class="sxs-lookup"><span data-stu-id="33302-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="33302-118">**Principales 5 dominios reenviados a**</span><span class="sxs-lookup"><span data-stu-id="33302-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="33302-119">**Nuevos dominios (la semana pasada)**</span><span class="sxs-lookup"><span data-stu-id="33302-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="33302-120">**Principales 5 usuarios de reenvío**</span><span class="sxs-lookup"><span data-stu-id="33302-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="33302-121">**Nuevos usuarios (la semana pasada)**</span><span class="sxs-lookup"><span data-stu-id="33302-121">**New users (last week)**</span></span>
  - <span data-ttu-id="33302-122">Un vínculo al informe [de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33302-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Control de detalles del informe de mensajes reenviados automáticamente en el Centro de seguridad y & cumplimiento](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="33302-124">Enfoques</span><span class="sxs-lookup"><span data-stu-id="33302-124">Insights</span></span>

<span data-ttu-id="33302-125">Se generan dos perspectivas en función de los datos del informe:</span><span class="sxs-lookup"><span data-stu-id="33302-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="33302-126">Nuevos usuarios reenviar correo electrónico</span><span class="sxs-lookup"><span data-stu-id="33302-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="33302-127">Nuevos dominios que se reenvía correo electrónico</span><span class="sxs-lookup"><span data-stu-id="33302-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="33302-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="33302-128">See also</span></span>

<span data-ttu-id="33302-129">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="33302-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>