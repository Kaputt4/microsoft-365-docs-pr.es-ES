---
title: Información de estado del flujo de correo de dominio superior en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información de estado del flujo de correo de dominio superior en el panel de flujo de correo del Centro de seguridad & cumplimiento para solucionar problemas de flujo de correo relacionados con sus registros MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ecda78047384a581a1043d0049b8dd25fadbe27
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290626"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="2910d-103">Información de estado del flujo de correo de dominio superior en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2910d-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2910d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="2910d-104">**Applies to**</span></span>
- [<span data-ttu-id="2910d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2910d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2910d-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2910d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2910d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2910d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2910d-108">La información sobre el estado [](mail-flow-insights-v2.md) **del** flujo de correo de dominio superior en el panel flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) le proporciona el estado actual del flujo de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="2910d-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="2910d-109">Esta información le ayuda a identificar y solucionar problemas de dominios que están experimentando problemas ***de flujo de*** correo.</span><span class="sxs-lookup"><span data-stu-id="2910d-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="2910d-110">Por ejemplo, el dominio no puede recibir correo electrónico externo porque el dominio ha expirado o el dominio tiene un registro MX incorrecto.</span><span class="sxs-lookup"><span data-stu-id="2910d-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget Estado del flujo de dominio superior en el panel flujo de correo del Centro de & cumplimiento](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="2910d-112">Al hacer clic **en Ver**  detalles en el widget, aparece un control flotante de estado dominio que muestra más detalles para el estado de cada dominio:</span><span class="sxs-lookup"><span data-stu-id="2910d-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="2910d-113">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="2910d-113">**Domain**</span></span>
- <span data-ttu-id="2910d-114">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="2910d-114">**Previous MX record**</span></span>
- <span data-ttu-id="2910d-115">**Registro MX actual**</span><span class="sxs-lookup"><span data-stu-id="2910d-115">**Current MX record**</span></span>
- <span data-ttu-id="2910d-116">**Estado de recepción de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="2910d-116">**Email receiving status**</span></span>
- <span data-ttu-id="2910d-117">**Estado del** dominio: una marca de verificación verde indica que el registro MX actual (en el momento en que hizo clic en el widget) coincide con el valor que tenemos en el registro y que el dominio ha recibido correo electrónico durante las últimas dos horas.</span><span class="sxs-lookup"><span data-stu-id="2910d-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="2910d-118">Una X roja indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las últimas 6 horas.</span><span class="sxs-lookup"><span data-stu-id="2910d-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="2910d-119">Esto probablemente indica que el dominio ha expirado o que el registro MX se ha actualizado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="2910d-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="2910d-120">Consulte con el registrador de dominios o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="2910d-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="2910d-121">Puede hacer clic **en Ver más** para ver la misma información para más dominios.</span><span class="sxs-lookup"><span data-stu-id="2910d-121">You can click **View more** to see the same information for more domains.</span></span>

![Control de detalles en la información de estado del flujo de correo de dominio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="2910d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2910d-123">See also</span></span>

<span data-ttu-id="2910d-124">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="2910d-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
