---
title: Corrección de posible información de bucle de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información sobre cómo solucionar posibles bucles de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento para identificar y corregir bucles de correo en su organización.
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826958"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="988c8-103">Corrección de la información posible sobre el bucle de correo en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="988c8-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="988c8-104">Un bucle de correo es incorrecto porque desperdicia recursos del sistema, consume la cuota del volumen de correo de su organización y envía informes de no entrega confusos (también conocidos como NDR o mensajes de devolución) a los remitentes originales.</span><span class="sxs-lookup"><span data-stu-id="988c8-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="988c8-105">La información de **corrección posible del bucle de correo** en el área **recomendada para** el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de seguridad & cumplimiento le avisa cuando se detecta un bucle de correo en la organización.</span><span class="sxs-lookup"><span data-stu-id="988c8-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="988c8-106">Esta información sólo aparece cuando se detecta la condición (si no tiene bucles de correo, no verá la información).</span><span class="sxs-lookup"><span data-stu-id="988c8-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Corrección de la información lenta reglas de flujo de correo en el área recomendada para el panel del flujo de correo](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="988c8-108">Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:</span><span class="sxs-lookup"><span data-stu-id="988c8-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="988c8-109">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="988c8-109">**Domain**</span></span>
- <span data-ttu-id="988c8-110">**Número de mensajes**: puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados por el bucle.</span><span class="sxs-lookup"><span data-stu-id="988c8-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="988c8-111">**Tipo de dominio**"por ejemplo, autoritario o no autoritativo.</span><span class="sxs-lookup"><span data-stu-id="988c8-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="988c8-112">**Registro MX**: host (**servidor de correo**) y valores de **prioridad** del registro MX para el dominio.</span><span class="sxs-lookup"><span data-stu-id="988c8-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="988c8-113">**Razón** **para el bucle y cómo corregir**: intentaremos identificar los escenarios de bucle de correo más comunes y proporcionar las acciones recomendadas (si están disponibles) para corregir el bucle.</span><span class="sxs-lookup"><span data-stu-id="988c8-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![Control flotante de detalles después de hacer clic en ver detalles en la información de corrección posible bucle de correo](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="988c8-115">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="988c8-115">Related topics</span></span>

<span data-ttu-id="988c8-116">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="988c8-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
