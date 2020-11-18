---
title: Resumen de los resultados del proyecto piloto de Microsoft 365 defender
description: Celebre el proyecto piloto de Microsoft 365 defender llevando a cabo el cuadro de mandos, analizando las conclusiones del informe y decidiendo cómo avanzar.
keywords: Microsoft Threat Protection Pilot, decida qué hacer después de probar la protección contra amenazas de Microsoft piloto, qué hacer después de evaluar la protección contra amenazas de Microsoft en producción, transición de Microsoft Threat Protection Pilot a implementación, seguridad del ciberespacio, amenaza persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130948"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="69656-104">Cerrar y resumir el piloto de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="69656-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69656-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="69656-105">**Applies to:**</span></span>
- <span data-ttu-id="69656-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69656-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="69656-107">[![Planificación](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="69656-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="69656-108">Planeación</span><span class="sxs-lookup"><span data-stu-id="69656-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="69656-109">[![Preparación](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="69656-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="69656-110">Declaración</span><span class="sxs-lookup"><span data-stu-id="69656-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="69656-111">[![Simular ataque](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="69656-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="69656-112">Simular ataque</span><span class="sxs-lookup"><span data-stu-id="69656-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Cerrar y resumir](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="69656-114">Cerrar y resumir</span><span class="sxs-lookup"><span data-stu-id="69656-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="69656-115">*Ya está aquí.*</span><span class="sxs-lookup"><span data-stu-id="69656-115">*You are here!*</span></span>|


<span data-ttu-id="69656-116">Actualmente está en la fase de cierre y Resumen.</span><span class="sxs-lookup"><span data-stu-id="69656-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="69656-117">Acaba de ejecutar una simulación de ataque avanzado de solo memoria que ejecutó código de forma remota en un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="69656-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="69656-118">Ha visto cómo Microsoft defender para Endpoint y Microsoft defender para la identidad detectan y crean alertas sobre actividades malintencionadas ocultas.</span><span class="sxs-lookup"><span data-stu-id="69656-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="69656-119">También ha visto cómo se entregan alertas de diferentes orígenes junto con otra información contextual en un solo incidente en el portal del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69656-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="69656-120">Esta integración permite a los analistas de SOC investigar y tomar las medidas necesarias.</span><span class="sxs-lookup"><span data-stu-id="69656-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="69656-121">También ha creado una consulta de búsqueda avanzada que identificará los correos electrónicos entrantes en los que el usuario abrió o guardó los datos adjuntos y crea una detección basada en esa consulta.</span><span class="sxs-lookup"><span data-stu-id="69656-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="69656-122">Ha alcanzado el final del proceso una vez finalizadas todas las pruebas.</span><span class="sxs-lookup"><span data-stu-id="69656-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="69656-123">El resultado final debe ser:</span><span class="sxs-lookup"><span data-stu-id="69656-123">The final output should be:</span></span>

- <span data-ttu-id="69656-124">Un cuadro de mandos completado</span><span class="sxs-lookup"><span data-stu-id="69656-124">A completed scorecard</span></span>
- <span data-ttu-id="69656-125">Un informe detallado de los resultados de la prueba piloto</span><span class="sxs-lookup"><span data-stu-id="69656-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="69656-126">Una decisión sobre cómo avanzar</span><span class="sxs-lookup"><span data-stu-id="69656-126">A decision on how to move forward</span></span>

<span data-ttu-id="69656-127">Presente los informes del resultado final a los participantes internos (que ha identificado durante la fase de [preparación](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) ) y a los contactos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="69656-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="69656-128">Un esfuerzo de este tipo garantiza que se puedan usar comentarios para mejorar los productos y la documentación.</span><span class="sxs-lookup"><span data-stu-id="69656-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="69656-129">Esperamos que haya disfrutado de esta simulación.</span><span class="sxs-lookup"><span data-stu-id="69656-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="69656-130">Empiece a implementar lo que ha aprendido en una escala de mayor tamaño en su organización para sacar el máximo partido de la solución de seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="69656-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="69656-131">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="69656-131">Next step</span></span>
<span data-ttu-id="69656-132">Obtenga más información sobre el pilares de Microsoft 365 defender mediante las siguientes guías interactivas:</span><span class="sxs-lookup"><span data-stu-id="69656-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="69656-133">Proteja su organización con Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="69656-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="69656-134">Detectar actividades y posibles ataques con Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="69656-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="69656-135">Detectar amenazas y administrar alertas con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="69656-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="69656-136">Investigar y solucionar amenazas con Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="69656-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
