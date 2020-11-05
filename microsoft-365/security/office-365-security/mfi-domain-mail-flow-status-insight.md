---
title: Información sobre el estado del flujo de correo de dominio superior en el panel flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información más detallada sobre el estado del flujo de correo del dominio en el panel de flujo del correo en el centro de seguridad & cumplimiento para solucionar problemas del flujo de correo relacionados con sus registros MX.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920589"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="ecbea-103">Información más detallada sobre el estado del flujo de correo del dominio en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ecbea-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ecbea-104">La información sobre el **Estado del flujo de correo del dominio superior** del [Panel flujo](mail-flow-insights-v2.md) de correo del [centro de seguridad & cumplimiento](https://protection.office.com) le proporciona el estado actual del flujo de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="ecbea-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="ecbea-105">Esta información le ayudará a identificar y solucionar problemas de dominios que experimentan problemas de *_flujo de correo_*.</span><span class="sxs-lookup"><span data-stu-id="ecbea-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow_* _ issues.</span></span> <span data-ttu-id="ecbea-106">Por ejemplo, el dominio no puede recibir correo electrónico externo porque el dominio ha expirado o el dominio tiene un registro MX incorrecto.</span><span class="sxs-lookup"><span data-stu-id="ecbea-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget de estado de flujo superior del dominio en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="ecbea-108">Al hacer clic en _ *Ver detalles* \* en el widget, aparece un control flotante de **Estado de dominio** que muestra más detalles para el estado de cada dominio:</span><span class="sxs-lookup"><span data-stu-id="ecbea-108">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="ecbea-109">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ecbea-109">**Domain**</span></span>
- <span data-ttu-id="ecbea-110">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="ecbea-110">**Previous MX record**</span></span>
- <span data-ttu-id="ecbea-111">**Registro MX actual**</span><span class="sxs-lookup"><span data-stu-id="ecbea-111">**Current MX record**</span></span>
- <span data-ttu-id="ecbea-112">**Estado de recepción de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="ecbea-112">**Email receiving status**</span></span>
- <span data-ttu-id="ecbea-113">**Estado del dominio** : una marca de verificación verde indica que el registro MX actual (en el momento en que hizo clic en el widget) coincide con el valor que tenemos en el registro y el dominio ha recibido el correo electrónico durante las dos últimas horas.</span><span class="sxs-lookup"><span data-stu-id="ecbea-113">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="ecbea-114">Una X de color rojo indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las 6 últimas horas.</span><span class="sxs-lookup"><span data-stu-id="ecbea-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="ecbea-115">Esto probablemente indica que su dominio ha expirado o que el registro MX se ha actualizado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="ecbea-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="ecbea-116">Consulte con el registrador de dominios o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="ecbea-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="ecbea-117">Puede hacer clic en **Ver más** para ver la misma información de más dominios.</span><span class="sxs-lookup"><span data-stu-id="ecbea-117">You can click **View more** to see the same information for more domains.</span></span>

![Flotante de detalles en la información del estado del flujo de correo del dominio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="ecbea-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecbea-119">See also</span></span>

<span data-ttu-id="ecbea-120">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="ecbea-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
