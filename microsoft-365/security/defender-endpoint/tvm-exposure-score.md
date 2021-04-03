---
title: Puntuación de exposición en la administración de amenazas y vulnerabilidades
description: La puntuación de exposición a la administración de amenazas y vulnerabilidades refleja lo vulnerable que es su organización a las amenazas de ciberseguridad.
keywords: puntuación de exposición, puntuación de exposición mdatp, mdatp tvm exposure score, organization exposure score, tvm organization exposure score, threat and vulnerability management, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34c3122b017b14605fdbb3358f31f73e26361a4d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500126"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="e711b-104">Puntuación de exposición: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="e711b-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e711b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e711b-105">**Applies to:**</span></span>

- [<span data-ttu-id="e711b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e711b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e711b-107">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="e711b-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e711b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e711b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e711b-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e711b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e711b-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e711b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="e711b-111">La puntuación de exposición está visible en el panel [de administración](tvm-dashboard-insights.md) de amenazas y vulnerabilidades del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e711b-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="e711b-112">Refleja lo vulnerable que es su organización a las amenazas de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="e711b-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="e711b-113">Una puntuación de exposición baja significa que los dispositivos son menos vulnerables a la explotación.</span><span class="sxs-lookup"><span data-stu-id="e711b-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="e711b-114">Comprenda e identifique rápidamente los resultados de alto nivel sobre el estado de seguridad en su organización.</span><span class="sxs-lookup"><span data-stu-id="e711b-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="e711b-115">Detectar y responder a áreas que requieren investigación o acción para mejorar el estado actual.</span><span class="sxs-lookup"><span data-stu-id="e711b-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="e711b-116">Comunicarse con compañeros y administración sobre el impacto de los esfuerzos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e711b-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="e711b-117">La tarjeta te ofrece una vista de alto nivel de la tendencia de puntuación de exposición con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="e711b-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="e711b-118">Los picos del gráfico le dan una indicación visual de una alta exposición a amenazas de ciberseguridad que puede investigar más a fondo.</span><span class="sxs-lookup"><span data-stu-id="e711b-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![Tarjeta de puntuación de exposición](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="e711b-120">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="e711b-120">How it works</span></span>

<span data-ttu-id="e711b-121">La puntuación de exposición se divide en los siguientes niveles:</span><span class="sxs-lookup"><span data-stu-id="e711b-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="e711b-122">0–29: puntuación de exposición baja</span><span class="sxs-lookup"><span data-stu-id="e711b-122">0–29: low exposure score</span></span>
- <span data-ttu-id="e711b-123">30–69: puntuación de exposición media</span><span class="sxs-lookup"><span data-stu-id="e711b-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="e711b-124">70–100: puntuación de exposición alta</span><span class="sxs-lookup"><span data-stu-id="e711b-124">70–100: high exposure score</span></span>

<span data-ttu-id="e711b-125">Puede corregir los problemas en función de las recomendaciones de seguridad prioritarias [para](tvm-security-recommendation.md) reducir la puntuación de exposición.</span><span class="sxs-lookup"><span data-stu-id="e711b-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="e711b-126">Cada software tiene debilidades que se transforman en recomendaciones y se priorizan en función del riesgo para la organización.</span><span class="sxs-lookup"><span data-stu-id="e711b-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="e711b-127">Reducir la exposición a amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="e711b-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="e711b-128">Reduzca la exposición a amenazas y vulnerabilidades mediante la corrección de [recomendaciones de seguridad](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="e711b-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="e711b-129">Para obtener el mayor impacto en la puntuación de exposición, corrija las recomendaciones de seguridad más importantes, que se pueden ver en el panel de administración de amenazas y [vulnerabilidades.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="e711b-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e711b-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e711b-130">Related topics</span></span>

- [<span data-ttu-id="e711b-131">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="e711b-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e711b-132">Puntuación de seguridad de Microsoft para dispositivos</span><span class="sxs-lookup"><span data-stu-id="e711b-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="e711b-133">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="e711b-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="e711b-134">Línea de tiempo de eventos</span><span class="sxs-lookup"><span data-stu-id="e711b-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
