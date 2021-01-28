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
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029947"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="14156-103">Información sobre mensajes reenviados automáticamente en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="14156-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="14156-104">La **información de** mensajes reenviados automáticamente en el panel flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra información sobre los mensajes que se reenvía automáticamente de la organización a los destinatarios de dominios externos. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="14156-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget Mensajes reenviados automáticamente en el Centro de & cumplimiento](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="14156-106">Detalles de mensajes reenviados automáticamente</span><span class="sxs-lookup"><span data-stu-id="14156-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="14156-107">Al hacer clic en el número de mensajes del widget, aparece un panel flotante que muestra más información sobre los mensajes reenviados automáticamente:</span><span class="sxs-lookup"><span data-stu-id="14156-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="14156-108">**Mensajes reenviados automáticamente mediante métodos de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="14156-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="14156-109">**Por reglas de flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="14156-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="14156-110">**Por reglas de bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="14156-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="14156-111">**Mediante el reenvío SMTP:** este método indica el reenvío automático que los administradores pueden configurar en un buzón como se describe en Configurar el reenvío de correo [electrónico para un buzón.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="14156-111">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="14156-112">Un vínculo al informe [de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="14156-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="14156-113">**Mensajes reenviados automáticamente por dominios y usuarios:**</span><span class="sxs-lookup"><span data-stu-id="14156-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="14156-114">**Los 5 dominios principales reenviados a**</span><span class="sxs-lookup"><span data-stu-id="14156-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="14156-115">**Nuevos dominios (la semana pasada)**</span><span class="sxs-lookup"><span data-stu-id="14156-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="14156-116">**Principales 5 usuarios de reenvío**</span><span class="sxs-lookup"><span data-stu-id="14156-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="14156-117">**Nuevos usuarios (la semana pasada)**</span><span class="sxs-lookup"><span data-stu-id="14156-117">**New users (last week)**</span></span>
  - <span data-ttu-id="14156-118">Un vínculo al informe [de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="14156-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Control de detalles del informe de mensajes reenviados automáticamente en el Centro de & cumplimiento](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="14156-120">Insights</span><span class="sxs-lookup"><span data-stu-id="14156-120">Insights</span></span>

<span data-ttu-id="14156-121">Se generan dos perspectivas en función de los datos del informe:</span><span class="sxs-lookup"><span data-stu-id="14156-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="14156-122">Nuevos usuarios reenviando correo electrónico</span><span class="sxs-lookup"><span data-stu-id="14156-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="14156-123">Nuevos dominios que se reenván de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="14156-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="14156-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="14156-124">See also</span></span>

<span data-ttu-id="14156-125">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="14156-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
