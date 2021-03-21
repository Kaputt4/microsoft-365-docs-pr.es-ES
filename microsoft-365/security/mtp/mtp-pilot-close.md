---
title: Resumen de los resultados del proyecto piloto de Microsoft 365 Defender
description: Para finalizar el proyecto piloto de Microsoft 365 Defender, complete el cuadro de mandos, analice los resultados del informe y decida cómo avanzar.
keywords: Piloto de Protección contra amenazas de Microsoft, decida qué hacer después del proyecto piloto de Protección contra amenazas de Microsoft, qué hacer después de evaluar Protección contra amenazas de Microsoft en producción, transición del piloto de Protección contra amenazas de Microsoft a la implementación, seguridad cibernética, amenaza persistente avanzada, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f646fe7061fb0793fd9922068c9037be21a236cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920401"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="df704-104">Cerrar y resumir el piloto de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df704-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="df704-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="df704-105">**Applies to:**</span></span>
- <span data-ttu-id="df704-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df704-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="df704-107">[![Planificación](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="df704-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="df704-108">Planeación</span><span class="sxs-lookup"><span data-stu-id="df704-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="df704-109">[![Preparación](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="df704-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="df704-110">Preparación</span><span class="sxs-lookup"><span data-stu-id="df704-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="df704-111">[![Simular ataque](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="df704-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="df704-112">Simular ataque</span><span class="sxs-lookup"><span data-stu-id="df704-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Cerrar y resumir](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="df704-114">Cerrar y resumir</span><span class="sxs-lookup"><span data-stu-id="df704-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="df704-115">*¡Estás aquí!*</span><span class="sxs-lookup"><span data-stu-id="df704-115">*You are here!*</span></span>|


<span data-ttu-id="df704-116">Actualmente está en la fase de cierre y resumen.</span><span class="sxs-lookup"><span data-stu-id="df704-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="df704-117">Acaba de ejecutar una simulación avanzada de ataques de solo memoria que ejecutó código de forma remota en un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="df704-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="df704-118">Has visto cómo Microsoft Defender para Endpoint y Microsoft Defender para Identity detectan y crean alertas sobre actividades malintencionadas furtivos.</span><span class="sxs-lookup"><span data-stu-id="df704-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="df704-119">También ha visto cómo las alertas de diferentes orígenes se entregan junto con otra información contextual en un solo incidente en el portal del Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df704-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="df704-120">La experiencia de esta integración permite a los analistas de SOC investigar y tomar las medidas necesarias.</span><span class="sxs-lookup"><span data-stu-id="df704-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="df704-121">También ha creado una consulta de búsqueda avanzada que identificará los correos electrónicos entrantes en los que el usuario abrió o guardó los datos adjuntos y creó la detección en función de esa consulta.</span><span class="sxs-lookup"><span data-stu-id="df704-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="df704-122">Ha llegado al final del proceso después de que todas las pruebas han finalizado.</span><span class="sxs-lookup"><span data-stu-id="df704-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="df704-123">El resultado final debe ser:</span><span class="sxs-lookup"><span data-stu-id="df704-123">The final output should be:</span></span>

- <span data-ttu-id="df704-124">Cuadro de mandos completado</span><span class="sxs-lookup"><span data-stu-id="df704-124">A completed scorecard</span></span>
- <span data-ttu-id="df704-125">Un informe detallado de los resultados del piloto</span><span class="sxs-lookup"><span data-stu-id="df704-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="df704-126">Una decisión sobre cómo avanzar</span><span class="sxs-lookup"><span data-stu-id="df704-126">A decision on how to move forward</span></span>

<span data-ttu-id="df704-127">Presente los informes del resultado final a las partes interesadas internas (que ha identificado durante la fase de [preparación)](./prepare-mtpeval.md) y a los contactos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df704-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-mtpeval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="df704-128">Este esfuerzo garantiza que los comentarios se puedan usar para mejorar los productos y la documentación.</span><span class="sxs-lookup"><span data-stu-id="df704-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="df704-129">Esperamos que haya disfrutado de esta simulación.</span><span class="sxs-lookup"><span data-stu-id="df704-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="df704-130">Comience a implementar lo aprendido a mayor escala en su organización para sacar el máximo partido a la solución de seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="df704-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="df704-131">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="df704-131">Next step</span></span>
<span data-ttu-id="df704-132">Obtenga más información sobre los pilares de Microsoft 365 Defender a través de las siguientes guías interactivas:</span><span class="sxs-lookup"><span data-stu-id="df704-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="df704-133">Proteger su organización con Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="df704-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="df704-134">Detectar actividades y posibles ataques con Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="df704-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="df704-135">Detectar amenazas y administrar alertas con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="df704-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="df704-136">Investigar y corregir amenazas con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="df704-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)