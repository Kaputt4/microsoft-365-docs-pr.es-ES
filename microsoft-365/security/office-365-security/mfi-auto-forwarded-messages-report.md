---
title: Información de mensajes reenviados automáticamente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 8d1a3ffe5ffc16a7793826b98b130121b8e68599
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827032"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="3bd44-103">Mensajes reenviados automáticamente información sobre el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3bd44-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="3bd44-104">La introducción a los **mensajes reenviados automáticamente** del [Panel flujo de correo](mail-flow-insights-v2.md) del centro de seguridad & cumplimiento muestra información acerca de los mensajes que se reenvían automáticamente desde la organización a los destinatarios de dominios externos.</span><span class="sxs-lookup"><span data-stu-id="3bd44-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget de mensajes reenviados automáticamente en el centro de seguridad & cumplimiento](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="3bd44-106">Detalles de los mensajes reenviados automáticamente</span><span class="sxs-lookup"><span data-stu-id="3bd44-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="3bd44-107">Al hacer clic en el número de mensajes del widget, aparece un panel de control flotante que muestra más información sobre los mensajes reenviados automáticamente:</span><span class="sxs-lookup"><span data-stu-id="3bd44-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="3bd44-108">Mensajes reenviados **automáticamente mediante métodos de reenvío**:</span><span class="sxs-lookup"><span data-stu-id="3bd44-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="3bd44-109">**Por reglas de flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="3bd44-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="3bd44-110">**Por reglas de la bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="3bd44-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="3bd44-111">**Por el reenvío SMTP**</span><span class="sxs-lookup"><span data-stu-id="3bd44-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="3bd44-112">Un vínculo al [Informe de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3bd44-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="3bd44-113">**Mensajes reenviados automáticamente por dominios y usuarios**:</span><span class="sxs-lookup"><span data-stu-id="3bd44-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="3bd44-114">**Los 5 primeros dominios se reenvían a**</span><span class="sxs-lookup"><span data-stu-id="3bd44-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="3bd44-115">**Nuevos dominios (última semana)**</span><span class="sxs-lookup"><span data-stu-id="3bd44-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="3bd44-116">**5 principales usuarios de reenvío**</span><span class="sxs-lookup"><span data-stu-id="3bd44-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="3bd44-117">**Nuevos usuarios (última semana)**</span><span class="sxs-lookup"><span data-stu-id="3bd44-117">**New users (last week)**</span></span>
  - <span data-ttu-id="3bd44-118">Un vínculo al [Informe de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3bd44-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Control flotante de detalles del informe de mensajes reenviados automáticamente en el centro de seguridad & cumplimiento](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="3bd44-120">Información</span><span class="sxs-lookup"><span data-stu-id="3bd44-120">Insights</span></span>

<span data-ttu-id="3bd44-121">Se generan dos perspectivas en función de los datos del informe:</span><span class="sxs-lookup"><span data-stu-id="3bd44-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="3bd44-122">Reenviar correo electrónico a los nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="3bd44-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="3bd44-123">Nuevos dominios que se reenvían correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3bd44-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="3bd44-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bd44-124">See also</span></span>

<span data-ttu-id="3bd44-125">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="3bd44-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
