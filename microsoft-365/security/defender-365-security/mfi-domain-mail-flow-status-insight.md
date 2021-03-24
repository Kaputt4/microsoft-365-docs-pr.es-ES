---
title: Información de estado del flujo de correo de dominio superior en el panel Flujo de correo
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
description: Los administradores pueden aprender a usar la información sobre el estado del flujo de correo de dominio superior en el panel flujo de correo del Centro de seguridad & cumplimiento para solucionar problemas de flujo de correo relacionados con sus registros MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071312"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="ba0d9-103">Información de estado del flujo de correo de dominio superior en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ba0d9-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ba0d9-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="ba0d9-104">**Applies to**</span></span>
- [<span data-ttu-id="ba0d9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ba0d9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ba0d9-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ba0d9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ba0d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba0d9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ba0d9-108">La **información sobre el** estado [](mail-flow-insights-v2.md) del flujo de correo de dominio superior en el panel Flujo de correo del Centro de seguridad [& cumplimiento](https://protection.office.com) le proporciona el estado del flujo de correo actual de su organización.</span><span class="sxs-lookup"><span data-stu-id="ba0d9-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="ba0d9-109">Esta información le ayuda a identificar y solucionar problemas de dominios que están experimentando problemas ***de flujo de*** correo.</span><span class="sxs-lookup"><span data-stu-id="ba0d9-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="ba0d9-110">Por ejemplo, el dominio no puede recibir correo electrónico externo porque el dominio ha expirado o el dominio tiene un registro MX incorrecto.</span><span class="sxs-lookup"><span data-stu-id="ba0d9-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget de estado de flujo de dominio superior en el panel Flujo de correo del Centro de seguridad & cumplimiento](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="ba0d9-112">Al hacer clic **en Ver detalles** en el widget, aparece un control flotante Estado del dominio que muestra más detalles sobre el estado de cada dominio: </span><span class="sxs-lookup"><span data-stu-id="ba0d9-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="ba0d9-113">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ba0d9-113">**Domain**</span></span>
- <span data-ttu-id="ba0d9-114">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="ba0d9-114">**Previous MX record**</span></span>
- <span data-ttu-id="ba0d9-115">**Registro MX actual**</span><span class="sxs-lookup"><span data-stu-id="ba0d9-115">**Current MX record**</span></span>
- <span data-ttu-id="ba0d9-116">**Estado de recepción de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="ba0d9-116">**Email receiving status**</span></span>
- <span data-ttu-id="ba0d9-117">**Estado del** dominio: una marca de verificación verde indica que el registro MX actual (en el momento en que hizo clic en el widget) coincide con el valor que tenemos en el registro y el dominio ha recibido correo electrónico durante las últimas dos horas.</span><span class="sxs-lookup"><span data-stu-id="ba0d9-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="ba0d9-118">Una X roja indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las últimas 6 horas.</span><span class="sxs-lookup"><span data-stu-id="ba0d9-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="ba0d9-119">Esto probablemente indica que el dominio ha expirado o que el registro MX se ha actualizado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="ba0d9-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="ba0d9-120">Compruebe con el registrador de dominio o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="ba0d9-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="ba0d9-121">Puede hacer clic **en Ver más** para ver la misma información para más dominios.</span><span class="sxs-lookup"><span data-stu-id="ba0d9-121">You can click **View more** to see the same information for more domains.</span></span>

![Control remoto de detalles en la información de estado del flujo de correo de dominio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="ba0d9-123">Ver también</span><span class="sxs-lookup"><span data-stu-id="ba0d9-123">See also</span></span>

<span data-ttu-id="ba0d9-124">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="ba0d9-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
