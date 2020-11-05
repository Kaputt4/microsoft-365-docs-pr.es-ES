---
title: Corrección de posible información de bucle de correo
f1.keywords:
- NOCSH
ms.author: siosulli
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
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920575"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="eb47c-103">Corrección de la información posible sobre el bucle de correo en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="eb47c-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="eb47c-104">Los bucles de correo son incorrectos porque:</span><span class="sxs-lookup"><span data-stu-id="eb47c-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="eb47c-105">Desperdician recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="eb47c-105">They waste system resources.</span></span>
- <span data-ttu-id="eb47c-106">Consumen la cuota del volumen de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="eb47c-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="eb47c-107">Envían informes de no entrega confusos (también conocidos como NDR o mensajes de devolución) a los remitentes de mensajes originales.</span><span class="sxs-lookup"><span data-stu-id="eb47c-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="eb47c-108">La información de **corrección posible del bucle de correo** en el área **recomendada para** el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de [seguridad & cumplimiento](https://protection.office.com) le avisa cuando se detecta un bucle de correo en la organización.</span><span class="sxs-lookup"><span data-stu-id="eb47c-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="eb47c-109">Esta información sólo aparece cuando se detecta la condición (si no tiene bucles de correo, no verá la información).</span><span class="sxs-lookup"><span data-stu-id="eb47c-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Corrección de la información lenta reglas de flujo de correo en el área recomendada para el panel del flujo de correo](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="eb47c-111">Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:</span><span class="sxs-lookup"><span data-stu-id="eb47c-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="eb47c-112">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="eb47c-112">**Domain**</span></span>
- <span data-ttu-id="eb47c-113">**Número de mensajes** : puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados por el bucle.</span><span class="sxs-lookup"><span data-stu-id="eb47c-113">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="eb47c-114">**Tipo de dominio** "por ejemplo, autoritario o no autoritativo.</span><span class="sxs-lookup"><span data-stu-id="eb47c-114">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="eb47c-115">**Registro MX** : host ( **servidor de correo** ) y valores de **prioridad** del registro MX para el dominio.</span><span class="sxs-lookup"><span data-stu-id="eb47c-115">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="eb47c-116">**Razón** **para el bucle y cómo corregir** : identificaremos los escenarios de bucle de correo más comunes y proporcionaremos las acciones recomendadas para corregir el bucle.</span><span class="sxs-lookup"><span data-stu-id="eb47c-116">**Loop reason** and **How to fix** : We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Control flotante de detalles después de hacer clic en ver detalles en la información de corrección posible bucle de correo](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="eb47c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb47c-118">See also</span></span>

<span data-ttu-id="eb47c-119">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="eb47c-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
