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
description: Los administradores pueden aprender a usar la información sobre corregir posibles bucles de correo en el panel flujo de correo del Centro de seguridad y cumplimiento de & para identificar y corregir bucles de correo en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071299"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="7026a-103">Corregir posibles perspectivas de bucle de correo en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="7026a-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7026a-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="7026a-104">**Applies to**</span></span>
- [<span data-ttu-id="7026a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7026a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7026a-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7026a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7026a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7026a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7026a-108">Los bucles de correo son malos porque:</span><span class="sxs-lookup"><span data-stu-id="7026a-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="7026a-109">Desperdician recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="7026a-109">They waste system resources.</span></span>
- <span data-ttu-id="7026a-110">Consumen la cuota de volumen de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="7026a-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="7026a-111">Envían informes confusos de no entrega (también conocidos como NDR o mensajes de rebote) a los remitentes de mensajes originales.</span><span class="sxs-lookup"><span data-stu-id="7026a-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="7026a-112">Fix **possible mail loop** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance [Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span><span class="sxs-lookup"><span data-stu-id="7026a-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="7026a-113">Esta información aparece solo después de que se detecte la condición (si no tiene bucles de correo, no verá la información).</span><span class="sxs-lookup"><span data-stu-id="7026a-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Corregir la información de reglas de flujo de correo lento en el área Recomendado para usted del panel flujo de correo](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="7026a-115">Al hacer clic **en Ver detalles** en el widget, aparece un control flotante con más información:</span><span class="sxs-lookup"><span data-stu-id="7026a-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="7026a-116">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7026a-116">**Domain**</span></span>
- <span data-ttu-id="7026a-117">**Número de mensajes:** puede hacer clic [](message-trace-scc.md) en **Ver** mensajes de ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes que se vieron afectados por el bucle.</span><span class="sxs-lookup"><span data-stu-id="7026a-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="7026a-118">**Tipo de dominio**" Por ejemplo, Autoritativo o no autoritativo.</span><span class="sxs-lookup"><span data-stu-id="7026a-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="7026a-119">**Registro MX:** el host (**servidor de correo**) y los valores **de** prioridad del registro MX para el dominio.</span><span class="sxs-lookup"><span data-stu-id="7026a-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="7026a-120">**Motivo del** bucle **y Cómo corregir:** identificaremos los escenarios de bucle de correo más comunes y proporcionaremos acciones recomendadas para corregir el bucle.</span><span class="sxs-lookup"><span data-stu-id="7026a-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Control de detalles que aparece después de hacer clic en Ver detalles en la información de corregir posibles bucles de correo](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="7026a-122">Ver también</span><span class="sxs-lookup"><span data-stu-id="7026a-122">See also</span></span>

<span data-ttu-id="7026a-123">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="7026a-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
