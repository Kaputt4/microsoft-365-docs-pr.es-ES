---
title: Corrección de información de reglas de flujo de correo lento
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre cómo usar la solución Fix Slow mail Flow rules Insight en el centro de seguridad & cumplimiento para identificar y corregir reglas de flujo de correo ineficientes o ineficientes (también conocidas como reglas de transporte) en su organización.
ms.openlocfilehash: 6a2a3c42eadf3c621b34d2a21344eafd2618e669
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877542"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="77c61-103">Corrección de las reglas de flujo de correo lenta información del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="77c61-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="77c61-104">Las reglas de flujo de correo ineficiente (también conocidas como reglas de transporte) pueden llevar a retrasos en el flujo de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="77c61-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="77c61-105">Esta visión informa de las reglas de flujo de correo que afectan al flujo de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="77c61-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="77c61-106">Algunos ejemplos de estos tipos de reglas son:</span><span class="sxs-lookup"><span data-stu-id="77c61-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="77c61-107">Condiciones que usan **son miembros de** grupos grandes.</span><span class="sxs-lookup"><span data-stu-id="77c61-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="77c61-108">Condiciones que usan la coincidencia de patrón de expresiones regulares complejas (regex).</span><span class="sxs-lookup"><span data-stu-id="77c61-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="77c61-109">Condiciones que usan la comprobación de contenido en datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="77c61-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="77c61-110">La opción para **corregir reglas de flujo de correo con lentitud** en el área **recomendada para** el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de [seguridad & cumplimiento](https://protection.office.com) le avisa cuando una regla de flujo de correo tarda mucho tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="77c61-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="77c61-111">Esta información sólo aparece cuando se detecta la condición (si no tiene bucles de correo, no verá la información).</span><span class="sxs-lookup"><span data-stu-id="77c61-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="77c61-112">Puede usar esta notificación para ayudarle a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos del flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="77c61-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Corrección de la información lenta reglas de flujo de correo en el área recomendada para el panel del flujo de correo](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="77c61-114">Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:</span><span class="sxs-lookup"><span data-stu-id="77c61-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="77c61-115">**Regla** : puede desplazar el mouse sobre el resumen para ver todas las condiciones, excepciones y acciones de la regla.</span><span class="sxs-lookup"><span data-stu-id="77c61-115">**Rule** : You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="77c61-116">Puede hacer clic en el resumen para editar la regla en el centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="77c61-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="77c61-117">**Número de mensajes evaluados** : puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados por la regla.</span><span class="sxs-lookup"><span data-stu-id="77c61-117">**Number of messages evaluated** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="77c61-118">**Tiempo promedio invertido en cada mensaje**</span><span class="sxs-lookup"><span data-stu-id="77c61-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="77c61-119">**Tiempo medio invertido en un mensaje** : el valor medio que separa la mitad superior de la mitad inferior de los datos de tiempo.</span><span class="sxs-lookup"><span data-stu-id="77c61-119">**Median time spent on a message** : The middle value that separates the upper half from the lower half of time data.</span></span>

![Control flotante de detalles que aparece después de hacer clic en ver detalles en la solución solucionar reglas de flujo de correo lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="77c61-121">Para obtener más información acerca de las condiciones y excepciones de las reglas de flujo de correo en Exchange Online, consulte [mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="77c61-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="77c61-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="77c61-122">Related topics</span></span>

<span data-ttu-id="77c61-123">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="77c61-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
