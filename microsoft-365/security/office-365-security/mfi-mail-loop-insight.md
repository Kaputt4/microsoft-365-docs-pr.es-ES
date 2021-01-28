---
title: Corrección de posible información de bucle de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información de corregir posibles bucles de correo en el panel de flujo de correo del Centro de seguridad & y cumplimiento para identificar y corregir bucles de correo en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029899"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="70d44-103">Corregir posibles perspectivas del bucle de correo en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="70d44-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="70d44-104">Los bucles de correo son malos porque:</span><span class="sxs-lookup"><span data-stu-id="70d44-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="70d44-105">Desperdician recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="70d44-105">They waste system resources.</span></span>
- <span data-ttu-id="70d44-106">Consumen la cuota de volumen de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="70d44-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="70d44-107">Envían informes de no entrega confusos (también conocidos como NDRs o mensajes de de rebote) a los remitentes del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="70d44-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="70d44-108">La información **de** corrección  de posibles [](mail-flow-insights-v2.md) bucles de correo en el área Recomendado para usted del panel de flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuándo se detecta un bucle de correo en su organización.</span><span class="sxs-lookup"><span data-stu-id="70d44-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="70d44-109">Esta información aparece solo después de que se detecte la condición (si no tiene bucles de correo, no verá la información).</span><span class="sxs-lookup"><span data-stu-id="70d44-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Corregir información de reglas de flujo de correo lentas en el área Recomendada para el panel de flujo de correo](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="70d44-111">Al hacer clic **en Ver detalles** en el widget, aparece un control flotante con más información:</span><span class="sxs-lookup"><span data-stu-id="70d44-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="70d44-112">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="70d44-112">**Domain**</span></span>
- <span data-ttu-id="70d44-113">**Número de mensajes:**  puede hacer clic [](message-trace-scc.md) en Ver mensajes de ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes que se vieron afectados por el bucle.</span><span class="sxs-lookup"><span data-stu-id="70d44-113">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="70d44-114">**Tipo de dominio**" Por ejemplo, autoritativo o no autoritativo.</span><span class="sxs-lookup"><span data-stu-id="70d44-114">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="70d44-115">**Registro MX:** el host (**servidor de correo)** y los valores **de** prioridad del registro MX para el dominio.</span><span class="sxs-lookup"><span data-stu-id="70d44-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="70d44-116">**Motivo del** bucle **y cómo corregir:** identificaremos los escenarios de bucle de correo más comunes y proporcionaremos las acciones recomendadas para corregir el bucle.</span><span class="sxs-lookup"><span data-stu-id="70d44-116">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Control desplegable de detalles que aparece después de hacer clic en Ver detalles en la información corregir posible bucle de correo](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="70d44-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="70d44-118">See also</span></span>

<span data-ttu-id="70d44-119">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="70d44-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
