---
title: Ejecutar el proyecto piloto de Microsoft Threat Protection
description: Ejecute el proyecto piloto de Microsoft Threat Protection en producción para determinar de forma eficaz las ventajas y la adopción de la protección contra amenazas de Microsoft (MTP).
keywords: Microsoft Threat Protection Pilot, ejecute piloto proyecto de Microsoft Threat Protection, evaluación de la protección contra amenazas de Microsoft en producción, Microsoft Threat Protection Pilot Project, Cyber Security, prevención persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 4ec46891248c09f580b19d888573544ad2b4930f
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446872"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="4fccc-104">Ejecutar el proyecto piloto de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4fccc-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4fccc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4fccc-105">**Applies to:**</span></span>
- <span data-ttu-id="4fccc-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4fccc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4fccc-107">Para determinar con eficacia el beneficio y la adopción de la protección contra amenazas de Microsoft (MTP), puede ejecutar un proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="4fccc-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="4fccc-108">Antes de habilitar la protección contra amenazas de Microsoft en el entorno de producción e iniciar los casos de uso, es mejor planear la determinación de las tareas que se deben realizar para el proyecto piloto y establecer los criterios de éxito.</span><span class="sxs-lookup"><span data-stu-id="4fccc-108">Before enabling Microsoft Threat Protection in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="4fccc-109">Cómo usar esta guía del piloto</span><span class="sxs-lookup"><span data-stu-id="4fccc-109">How to use this pilot playbook</span></span>

<span data-ttu-id="4fccc-110">En esta guía se proporciona información general sobre la protección contra amenazas de Microsoft e instrucciones paso a paso sobre cómo configurar el proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="4fccc-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

![Fases de la ejecución de un programa piloto de Microsoft Threat Protection](../../media/pilotphases.png)

<span data-ttu-id="4fccc-112">La siguiente escala de tiempo de ejemplo varía en función de la necesidad de disponer de los recursos adecuados en el entorno.</span><span class="sxs-lookup"><span data-stu-id="4fccc-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="4fccc-113">Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que los otros.</span><span class="sxs-lookup"><span data-stu-id="4fccc-113">Some detections and workflows might need more learning time than the others.</span></span>

![Línea de tiempo de ejemplo para ejecutar una prueba piloto de Microsoft Threat Protection](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="4fccc-115">Para obtener resultados óptimos, siga las instrucciones piloto de la forma más parecida posible.</span><span class="sxs-lookup"><span data-stu-id="4fccc-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="4fccc-116">Fases de la guía piloto</span><span class="sxs-lookup"><span data-stu-id="4fccc-116">Pilot playbook phases</span></span> 

<span data-ttu-id="4fccc-117">Hay cuatro fases para ejecutar un piloto de Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="4fccc-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="4fccc-118">Fase</span><span class="sxs-lookup"><span data-stu-id="4fccc-118">Phase</span></span> | <span data-ttu-id="4fccc-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fccc-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="4fccc-120">![Planeación](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="4fccc-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="4fccc-121">Planeación</span><span class="sxs-lookup"><span data-stu-id="4fccc-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="4fccc-122">Obtenga información sobre lo que debe tener en cuenta antes de ejecutar el proyecto piloto de Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="4fccc-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="4fccc-123">-Scope</span><span class="sxs-lookup"><span data-stu-id="4fccc-123">- Scope</span></span> <br> <span data-ttu-id="4fccc-124">Casos de uso de</span><span class="sxs-lookup"><span data-stu-id="4fccc-124">- Use cases</span></span> <br><span data-ttu-id="4fccc-125">- Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fccc-125">- Requirements</span></span> <br><span data-ttu-id="4fccc-126">-Plan de pruebas</span><span class="sxs-lookup"><span data-stu-id="4fccc-126">- Test plan</span></span> <br> <span data-ttu-id="4fccc-127">-Criterios de éxito</span><span class="sxs-lookup"><span data-stu-id="4fccc-127">- Success criteria</span></span> <br> <span data-ttu-id="4fccc-128">-Cuadro de mandos</span><span class="sxs-lookup"><span data-stu-id="4fccc-128">- Scorecard</span></span> 
| <span data-ttu-id="4fccc-129">![Declaración](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="4fccc-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="4fccc-130">Declaración</span><span class="sxs-lookup"><span data-stu-id="4fccc-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="4fccc-131">Obtenga acceso al centro de seguridad de Microsoft 365 para configurar su entorno piloto de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="4fccc-131">Access Microsoft 365 Security Center to set up your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="4fccc-132">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="4fccc-132">You'll be guided to:</span></span><br><br><span data-ttu-id="4fccc-133">-Identificar las partes interesadas y buscar la firma para el proyecto piloto</span><span class="sxs-lookup"><span data-stu-id="4fccc-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="4fccc-134">Consideraciones del entorno</span><span class="sxs-lookup"><span data-stu-id="4fccc-134">- Environment considerations</span></span> <br><span data-ttu-id="4fccc-135">Acceso a</span><span class="sxs-lookup"><span data-stu-id="4fccc-135">- Access</span></span> <br><span data-ttu-id="4fccc-136">-Instalación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4fccc-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="4fccc-137">-Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="4fccc-137">- Configuration order</span></span> <br> <span data-ttu-id="4fccc-138">-Inscríbase en la versión de prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4fccc-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="4fccc-139">-Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="4fccc-139">- Configure domain</span></span> <br><span data-ttu-id="4fccc-140">-Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4fccc-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="4fccc-141">-Completar el Asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="4fccc-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="4fccc-142">![Simulación de ataques](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="4fccc-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="4fccc-143">Simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="4fccc-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="4fccc-144">Para simular un ataque, se le guiará a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4fccc-144">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="4fccc-145">-Comprobación de los requisitos del entorno de prueba</span><span class="sxs-lookup"><span data-stu-id="4fccc-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="4fccc-146">-Ejecutar la simulación</span><span class="sxs-lookup"><span data-stu-id="4fccc-146">-  Run the simulation</span></span> <br><span data-ttu-id="4fccc-147">-Investigar un incidente</span><span class="sxs-lookup"><span data-stu-id="4fccc-147">- Investigate an incident</span></span> <br><span data-ttu-id="4fccc-148">-resolver el incidente</span><span class="sxs-lookup"><span data-stu-id="4fccc-148">- resolve the incident</span></span> 
| <span data-ttu-id="4fccc-149">![Cierre y Resumen](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="4fccc-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="4fccc-150">Cierre y Resumen</span><span class="sxs-lookup"><span data-stu-id="4fccc-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="4fccc-151">Cuando haya llegado al final del proceso, se le guiará a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4fccc-151">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="4fccc-152">-Pase por el resultado final</span><span class="sxs-lookup"><span data-stu-id="4fccc-152">- Go through your final output</span></span><br><span data-ttu-id="4fccc-153">-Presentar la salida a las partes interesadas</span><span class="sxs-lookup"><span data-stu-id="4fccc-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="4fccc-154">-Proporcionar comentarios</span><span class="sxs-lookup"><span data-stu-id="4fccc-154">- Provide feedback</span></span> <br><span data-ttu-id="4fccc-155">-Realizar los siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="4fccc-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="4fccc-156">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="4fccc-156">Next step</span></span>
|<span data-ttu-id="4fccc-157">![Fase de planeación](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="4fccc-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="4fccc-158">Fase de planeación</span><span class="sxs-lookup"><span data-stu-id="4fccc-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="4fccc-159">Planeación de un proyecto piloto de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4fccc-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
