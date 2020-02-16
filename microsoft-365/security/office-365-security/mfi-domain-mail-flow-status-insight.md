---
title: Información de estado de flujo de correo de dominio superior
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden obtener información sobre el conocimiento del estado del flujo de correo del dominio superior del panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 42ce0545dad2804829d15572ce6e1f5a0ca6b49f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082857"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="ab554-103">Información de estado de flujo de correo de dominio superior</span><span class="sxs-lookup"><span data-stu-id="ab554-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="ab554-104">La información del **Estado del flujo de correo de dominio superior** le ofrece el estado actual de los dominios de su organización en términos de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="ab554-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="ab554-105">Esta visión le ayudará a identificar y solucionar problemas de dominios que experimentan problemas de impacto en el ***flujo de correo*** (por ejemplo, no se puede recibir correo electrónico externo), en especial expiraciones de dominio o dominios con registros MX incorrectos.</span><span class="sxs-lookup"><span data-stu-id="ab554-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![La información más detallada sobre el estado del flujo del dominio en el panel de flujo del correo en el centro de seguridad & cumplimiento](../../media/domain-mail-flow-status-selected.png)

<span data-ttu-id="ab554-107">Al hacer clic en **Ver detalles** en la visión, aparecerá un control flotante que muestra más detalles sobre el estado de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="ab554-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="ab554-108">Una marca de verificación verde para un dominio indica que el registro MX actual (cuando se ha explorado el panel de información de flujo de correo) coincide con el valor que tenemos en el registro y que el dominio ha recibido el correo electrónico durante las dos últimas horas.</span><span class="sxs-lookup"><span data-stu-id="ab554-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="ab554-109">Una x de color rojo para un dominio indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las 6 últimas horas.</span><span class="sxs-lookup"><span data-stu-id="ab554-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="ab554-110">Esto probablemente indica que su dominio ha expirado o que el registro MX se ha actualizado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="ab554-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="ab554-111">Consulte con el registrador de dominios o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="ab554-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![El control flotante de detalles en la información del estado del flujo superior del dominio](../../media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="ab554-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab554-113">See also</span></span>

<span data-ttu-id="ab554-114">Para obtener más información acerca de otras indicaciones del flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="ab554-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
