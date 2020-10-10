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
ms.openlocfilehash: af47f45ca4f3d14e835a39a334a9400002ac8560
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418078"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="f8cdc-104">Ejecutar el proyecto piloto de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f8cdc-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8cdc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f8cdc-105">**Applies to:**</span></span>
- <span data-ttu-id="f8cdc-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8cdc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f8cdc-107">Para determinar con eficacia el beneficio y la adopción de la protección contra amenazas de Microsoft (MTP), puede ejecutar un proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="f8cdc-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="f8cdc-108">Antes de habilitar la protección contra amenazas de Microsoft en su entorno de producción y comenzar con casos de uso definidos, es mejor pasar por un proceso de planeación para determinar las tareas que deben realizarse en este proyecto piloto y los criterios de éxito.</span><span class="sxs-lookup"><span data-stu-id="f8cdc-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="f8cdc-109">Cómo usar esta guía del piloto</span><span class="sxs-lookup"><span data-stu-id="f8cdc-109">How to use this pilot playbook</span></span>

<span data-ttu-id="f8cdc-110">En esta guía se proporciona información general sobre la protección contra amenazas de Microsoft e instrucciones paso a paso sobre cómo configurar el proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="f8cdc-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

![Fases de la ejecución de un programa piloto de Microsoft Threat Protection](../../media/pilotphases.png)

<span data-ttu-id="f8cdc-112">La siguiente escala de tiempo de ejemplo varía en función de la necesidad de disponer de los recursos adecuados en el entorno.</span><span class="sxs-lookup"><span data-stu-id="f8cdc-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="f8cdc-113">Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que los otros.</span><span class="sxs-lookup"><span data-stu-id="f8cdc-113">Some detections and workflows might need more learning time than the others.</span></span>

![Línea de tiempo de ejemplo para ejecutar una prueba piloto de Microsoft Threat Protection](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="f8cdc-115">Para obtener resultados óptimos, siga las instrucciones piloto de la forma más parecida posible.</span><span class="sxs-lookup"><span data-stu-id="f8cdc-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="f8cdc-116">Fases de la guía piloto</span><span class="sxs-lookup"><span data-stu-id="f8cdc-116">Pilot playbook phases</span></span> 

<span data-ttu-id="f8cdc-117">Hay cuatro fases para ejecutar un piloto de Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="f8cdc-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="f8cdc-118">Fase</span><span class="sxs-lookup"><span data-stu-id="f8cdc-118">Phase</span></span> | <span data-ttu-id="f8cdc-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8cdc-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="f8cdc-120">![Planificación](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="f8cdc-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="f8cdc-121">Planificación</span><span class="sxs-lookup"><span data-stu-id="f8cdc-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="f8cdc-122">Obtenga información sobre lo que debe tener en cuenta antes de ejecutar el proyecto piloto de Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="f8cdc-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="f8cdc-123">-Scope</span><span class="sxs-lookup"><span data-stu-id="f8cdc-123">- Scope</span></span> <br> <span data-ttu-id="f8cdc-124">Casos de uso de</span><span class="sxs-lookup"><span data-stu-id="f8cdc-124">- Use cases</span></span> <br><span data-ttu-id="f8cdc-125">- Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8cdc-125">- Requirements</span></span> <br><span data-ttu-id="f8cdc-126">-Plan de pruebas</span><span class="sxs-lookup"><span data-stu-id="f8cdc-126">- Test plan</span></span> <br> <span data-ttu-id="f8cdc-127">-Criterios de éxito</span><span class="sxs-lookup"><span data-stu-id="f8cdc-127">- Success criteria</span></span> <br> <span data-ttu-id="f8cdc-128">-Cuadro de mandos</span><span class="sxs-lookup"><span data-stu-id="f8cdc-128">- Scorecard</span></span> 
| <span data-ttu-id="f8cdc-129">![Declaración](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="f8cdc-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="f8cdc-130">Declaración</span><span class="sxs-lookup"><span data-stu-id="f8cdc-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="f8cdc-131">Obtenga acceso al centro de seguridad de Microsoft 365 para configurar el entorno piloto de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="f8cdc-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="f8cdc-132">Se le guiará para:</span><span class="sxs-lookup"><span data-stu-id="f8cdc-132">You will be guided to:</span></span><br><br><span data-ttu-id="f8cdc-133">-Identificar las partes interesadas y buscar la firma para el proyecto piloto</span><span class="sxs-lookup"><span data-stu-id="f8cdc-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="f8cdc-134">Consideraciones del entorno</span><span class="sxs-lookup"><span data-stu-id="f8cdc-134">- Environment considerations</span></span> <br><span data-ttu-id="f8cdc-135">Acceso a</span><span class="sxs-lookup"><span data-stu-id="f8cdc-135">- Access</span></span> <br><span data-ttu-id="f8cdc-136">-Instalación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f8cdc-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="f8cdc-137">-Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="f8cdc-137">- Configuration order</span></span> <br> <span data-ttu-id="f8cdc-138">-Inscríbase en la versión de prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f8cdc-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="f8cdc-139">-Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="f8cdc-139">- Configure domain</span></span> <br><span data-ttu-id="f8cdc-140">-Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f8cdc-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="f8cdc-141">-Completar el Asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="f8cdc-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="f8cdc-142">![Simulación de ataques](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="f8cdc-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="f8cdc-143">Simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="f8cdc-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="f8cdc-144">Para simular un ataque, se le guiará a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8cdc-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="f8cdc-145">-Comprobación de los requisitos del entorno de prueba</span><span class="sxs-lookup"><span data-stu-id="f8cdc-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="f8cdc-146">-Ejecutar la simulación</span><span class="sxs-lookup"><span data-stu-id="f8cdc-146">-  Run the simulation</span></span> <br><span data-ttu-id="f8cdc-147">-Investigar un incidente</span><span class="sxs-lookup"><span data-stu-id="f8cdc-147">- Investigate an incident</span></span> <br><span data-ttu-id="f8cdc-148">-resolver el incidente</span><span class="sxs-lookup"><span data-stu-id="f8cdc-148">- resolve the incident</span></span> 
| <span data-ttu-id="f8cdc-149">![Cierre y Resumen](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="f8cdc-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="f8cdc-150">Cierre y Resumen</span><span class="sxs-lookup"><span data-stu-id="f8cdc-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="f8cdc-151">Cuando haya llegado al final del proceso, se le guiará a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8cdc-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="f8cdc-152">-Pase por el resultado final</span><span class="sxs-lookup"><span data-stu-id="f8cdc-152">- Go through your final output</span></span><br><span data-ttu-id="f8cdc-153">-Presentar la salida a las partes interesadas</span><span class="sxs-lookup"><span data-stu-id="f8cdc-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="f8cdc-154">-Proporcionar comentarios</span><span class="sxs-lookup"><span data-stu-id="f8cdc-154">- Provide feedback</span></span> <br><span data-ttu-id="f8cdc-155">-Realizar los siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="f8cdc-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="f8cdc-156">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="f8cdc-156">Next step</span></span>
|<span data-ttu-id="f8cdc-157">![Fase de planeación](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="f8cdc-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="f8cdc-158">Fase de planeación</span><span class="sxs-lookup"><span data-stu-id="f8cdc-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="f8cdc-159">Planeación de un proyecto piloto de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f8cdc-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
