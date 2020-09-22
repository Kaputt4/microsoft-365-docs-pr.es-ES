---
title: Información sobre el estado del flujo de correo de dominio superior en el panel flujo de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información más detallada sobre el estado del flujo de correo del dominio en el panel de flujo del correo en el centro de seguridad & cumplimiento para solucionar problemas del flujo de correo relacionados con los registros MX en sus dominios de correo electrónico.
ms.openlocfilehash: 24922d6ae7d2ec50e3d9383631991cf46a818c05
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197530"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="4d354-103">Información más detallada sobre el estado del flujo de correo del dominio en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4d354-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4d354-104">La información más detallada sobre el **Estado del flujo de correo del dominio** en el panel del flujo de [correo](mail-flow-insights-v2.md) en el [centro de seguridad & cumplimiento](https://protection.office.com) le ofrece el estado actual de los dominios de su organización en términos de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="4d354-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="4d354-105">Esta visión le ayudará a identificar y solucionar problemas de dominios que experimentan problemas de impacto en el ***flujo de correo*** (por ejemplo, no se puede recibir correo electrónico externo), en especial expiraciones de dominio o dominios con registros MX incorrectos.</span><span class="sxs-lookup"><span data-stu-id="4d354-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Widget de estado de flujo superior del dominio en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="4d354-107">Al hacer clic en **Ver detalles** en el widget, aparece un control flotante de **Estado de dominio** que muestra más detalles para el estado de cada dominio:</span><span class="sxs-lookup"><span data-stu-id="4d354-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="4d354-108">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="4d354-108">**Domain**</span></span>
- <span data-ttu-id="4d354-109">**Registro MX anterior**</span><span class="sxs-lookup"><span data-stu-id="4d354-109">**Previous MX record**</span></span>
- <span data-ttu-id="4d354-110">**Registro MX actual**</span><span class="sxs-lookup"><span data-stu-id="4d354-110">**Current MX record**</span></span>
- <span data-ttu-id="4d354-111">**Estado de recepción de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="4d354-111">**Email receiving status**</span></span>
- <span data-ttu-id="4d354-112">**Estado del dominio**: una marca de verificación verde indica que el registro MX actual (en el momento en que hizo clic en el widget) coincide con el valor que tenemos en el registro y que el dominio ha recibido el correo electrónico durante las dos últimas horas.</span><span class="sxs-lookup"><span data-stu-id="4d354-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="4d354-113">Una X roja indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las 6 últimas horas.</span><span class="sxs-lookup"><span data-stu-id="4d354-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="4d354-114">Esto probablemente indica que su dominio ha expirado o que el registro MX se ha actualizado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="4d354-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="4d354-115">Consulte con el registrador de dominios o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="4d354-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="4d354-116">Puede hacer clic en **Ver más** para ver la misma información de más dominios.</span><span class="sxs-lookup"><span data-stu-id="4d354-116">You can click **View more** to see the same information for more domains.</span></span>

![Flotante de detalles en la información del estado del flujo de correo del dominio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="4d354-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4d354-118">Related topics</span></span>

<span data-ttu-id="4d354-119">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="4d354-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
