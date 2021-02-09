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
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel flujo de correo del Centro de & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150608"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="69317-103">Información de mensajes reenviados automáticamente en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="69317-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="69317-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="69317-104">**Applies to**</span></span>
- [<span data-ttu-id="69317-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="69317-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="69317-106">Microsoft Defender para Office 365 plan 1 y plan 2</span><span class="sxs-lookup"><span data-stu-id="69317-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="69317-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69317-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="69317-108">La **información de** mensajes reenviados automáticamente en el panel flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra información sobre los mensajes que se reenvía automáticamente de la organización a los destinatarios de dominios externos. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="69317-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget Mensajes reenviados automáticamente en el Centro de & cumplimiento](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="69317-110">Detalles de mensajes reenviados automáticamente</span><span class="sxs-lookup"><span data-stu-id="69317-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="69317-111">Al hacer clic en el número de mensajes del widget, aparece un panel flotante que muestra más información sobre los mensajes reenviados automáticamente:</span><span class="sxs-lookup"><span data-stu-id="69317-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="69317-112">**Mensajes reenviados automáticamente mediante métodos de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="69317-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="69317-113">**Por reglas de flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="69317-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="69317-114">**Por reglas de bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="69317-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="69317-115">**Mediante el reenvío SMTP:** este método indica el reenvío automático que los administradores pueden configurar en un buzón como se describe en Configurar el reenvío de correo [electrónico para un buzón.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="69317-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="69317-116">Un vínculo al informe [de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="69317-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="69317-117">**Mensajes reenviados automáticamente por dominios y usuarios:**</span><span class="sxs-lookup"><span data-stu-id="69317-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="69317-118">**Los 5 dominios principales reenviados a**</span><span class="sxs-lookup"><span data-stu-id="69317-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="69317-119">**Nuevos dominios (la semana pasada)**</span><span class="sxs-lookup"><span data-stu-id="69317-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="69317-120">**Principales 5 usuarios de reenvío**</span><span class="sxs-lookup"><span data-stu-id="69317-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="69317-121">**Nuevos usuarios (la semana pasada)**</span><span class="sxs-lookup"><span data-stu-id="69317-121">**New users (last week)**</span></span>
  - <span data-ttu-id="69317-122">Un vínculo al informe [de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="69317-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Control de detalles del informe de mensajes reenviados automáticamente en el Centro de & cumplimiento](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="69317-124">Insights</span><span class="sxs-lookup"><span data-stu-id="69317-124">Insights</span></span>

<span data-ttu-id="69317-125">Se generan dos perspectivas basadas en los datos del informe:</span><span class="sxs-lookup"><span data-stu-id="69317-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="69317-126">Nuevos usuarios reenviando correo electrónico</span><span class="sxs-lookup"><span data-stu-id="69317-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="69317-127">Nuevos dominios que se reenván de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="69317-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="69317-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="69317-128">See also</span></span>

<span data-ttu-id="69317-129">Para obtener información sobre otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="69317-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
