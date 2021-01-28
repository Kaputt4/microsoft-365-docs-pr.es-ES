---
title: Corrección de información de reglas de flujo de correo lento
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información sobre las reglas de flujo de correo lentas fix en el Centro de seguridad y cumplimiento de & para identificar y corregir reglas de flujo de correo ineficaces o rotas (también conocidas como reglas de transporte) en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef9f26994f563a5f9dad411f2276fd42c28496f9
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029131"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="670cd-103">Corregir información de reglas de flujo de correo lentas en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="670cd-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="670cd-104">Las reglas de flujo de correo ineficientes (también conocidas como reglas de transporte) pueden provocar retrasos en el flujo de correo para su organización.</span><span class="sxs-lookup"><span data-stu-id="670cd-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="670cd-105">Esta información informa sobre las reglas de flujo de correo que tienen un impacto en el flujo de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="670cd-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="670cd-106">Algunos ejemplos de estos tipos de reglas son:</span><span class="sxs-lookup"><span data-stu-id="670cd-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="670cd-107">Condiciones que usan **Es miembro de** para grupos grandes.</span><span class="sxs-lookup"><span data-stu-id="670cd-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="670cd-108">Condiciones que usan coincidencia de patrón de expresión regular compleja (regex).</span><span class="sxs-lookup"><span data-stu-id="670cd-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="670cd-109">Condiciones que usan la comprobación de contenido en datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="670cd-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="670cd-110">La  información corregir reglas de  flujo de correo [](mail-flow-insights-v2.md) lentas en el área Recomendado para usted del panel de flujo de correo en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuando una regla de flujo de correo tarda demasiado tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="670cd-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="670cd-111">Esta información aparece solo después de que se detecte la condición (si no tiene bucles de correo, no verá la información).</span><span class="sxs-lookup"><span data-stu-id="670cd-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="670cd-112">Puede usar esta notificación para ayudarle a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos en el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="670cd-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Corregir información de reglas de flujo de correo lentas en el área Recomendado para el panel de flujo de correo](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="670cd-114">Al hacer clic **en Ver detalles** en el widget, aparece un control flotante con más información:</span><span class="sxs-lookup"><span data-stu-id="670cd-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="670cd-115">**Regla:** puede pasar el puntero sobre el resumen para ver todas las condiciones, excepciones y acciones de la regla.</span><span class="sxs-lookup"><span data-stu-id="670cd-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="670cd-116">Puede hacer clic en el resumen para editar la regla en el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="670cd-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="670cd-117">**Número de mensajes evaluados:** puede hacer clic [](message-trace-scc.md) en Ver mensajes de ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados por la regla. </span><span class="sxs-lookup"><span data-stu-id="670cd-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="670cd-118">**Tiempo promedio empleado en cada mensaje**</span><span class="sxs-lookup"><span data-stu-id="670cd-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="670cd-119">**Mediana de tiempo invertido en un mensaje:** el valor intermedio que separa la mitad superior de los datos de la mitad inferior del tiempo.</span><span class="sxs-lookup"><span data-stu-id="670cd-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Control de detalles que aparece después de hacer clic en Ver detalles en la información de las reglas de flujo de correo de corrección lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="670cd-121">Para obtener más información acerca de las condiciones y excepciones en las reglas de flujo de correo, vea Condiciones y excepciones de reglas de flujo de correo [(predicados) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="670cd-121">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="670cd-122">Consulta también</span><span class="sxs-lookup"><span data-stu-id="670cd-122">See also</span></span>

<span data-ttu-id="670cd-123">Para obtener información sobre otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="670cd-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
