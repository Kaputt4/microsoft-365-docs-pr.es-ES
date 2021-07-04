---
title: Ejecutar el proyecto piloto Microsoft 365 Defender proyecto
description: Ejecute el proyecto piloto Microsoft 365 Defender en producción para determinar eficazmente los beneficios y la adopción de Microsoft 365 Defender.
keywords: Microsoft 365 Defender piloto, ejecute un proyecto piloto Microsoft 365 Defender, evalúe Microsoft 365 Defender en producción, un proyecto piloto Microsoft 365 Defender, seguridad cibernética, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289960"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="8dfd0-104">Ejecutar el proyecto piloto Microsoft 365 Defender proyecto</span><span class="sxs-lookup"><span data-stu-id="8dfd0-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8dfd0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8dfd0-105">**Applies to:**</span></span>
- <span data-ttu-id="8dfd0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dfd0-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="8dfd0-107">Esta guía te ayuda a ejecutar un proyecto piloto proporcionando punteros para asegurarte de que tienes un plan bien estructurado, guiándolo a través del uso de la característica de simulación de ataques y, por último, concluyendo el piloto con claves para que reflexiones y documentes los resultados.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fases en la ejecución de un Microsoft 365 Defender piloto](../../media/pilotphases.png)


<span data-ttu-id="8dfd0-109">La ejecución de un piloto le ayuda a determinar eficazmente la ventaja de adoptar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="8dfd0-110">Antes de habilitar Microsoft 365 Defender en el entorno de producción e iniciar los casos de uso, es mejor planear determinar las tareas que se deben realizar para el proyecto piloto y establecer los criterios de éxito.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="8dfd0-111">Cómo usar este libro de juegos piloto</span><span class="sxs-lookup"><span data-stu-id="8dfd0-111">How to use this pilot playbook</span></span>

<span data-ttu-id="8dfd0-112">En esta guía se proporciona información general Microsoft 365 Defender instrucciones detalladas y paso a paso sobre cómo configurar el proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="8dfd0-113">Microsoft 365 Defender es un conjunto unificado de defensa empresarial anterior y posterior a la infracción que coordina de forma nativa la protección, detección, prevención, investigación y respuesta entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="8dfd0-114">Lo hace combinando y orquestando las siguientes funcionalidades en una única solución de seguridad:</span><span class="sxs-lookup"><span data-stu-id="8dfd0-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>

- <span data-ttu-id="8dfd0-115">Microsoft Defender para el extremo (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="8dfd0-115">Microsoft Defender for Endpoint (endpoints)</span></span>
- <span data-ttu-id="8dfd0-116">Microsoft Defender para Office 365 (correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="8dfd0-116">Microsoft Defender for Office 365 (email)</span></span>
- <span data-ttu-id="8dfd0-117">Microsoft Defender para identidad (identidad)</span><span class="sxs-lookup"><span data-stu-id="8dfd0-117">Microsoft Defender for Identity (identity)</span></span>
- <span data-ttu-id="8dfd0-118">Microsoft Cloud App Security (aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="8dfd0-118">Microsoft Cloud App Security (apps)</span></span>

![Imagen of_Microsoft solución de 365 Defender para usuarios, Microsoft Defender para identidad, para puntos de conexión de Microsoft Defender para endpoint, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="8dfd0-120">Con la solución Microsoft 365 Defender integrada, los profesionales de seguridad pueden unir las señales de amenaza que Microsoft Defender para endpoint, Microsoft Defender para Office 365, Microsoft Defender para identity y Microsoft Cloud App Security reciben y determinar el alcance completo y el impacto de la amenaza, cómo entró en el entorno, qué afecta y cómo afecta actualmente a la organización.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="8dfd0-121">Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto-sanar los buzones, puntos de conexión e identidades de usuario afectados.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="8dfd0-122">Consulte el [Microsoft 365 Defender información general sobre](microsoft-365-defender.md) el producto para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>

<span data-ttu-id="8dfd0-123">La escala de tiempo de ejemplo siguiente varía en función de tener los recursos adecuados en el entorno.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="8dfd0-124">Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que los demás.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-124">Some detections and workflows might need more learning time than the others.</span></span>

![Escala de tiempo de ejemplo en la ejecución de un Microsoft 365 Defender piloto](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> <span data-ttu-id="8dfd0-126">Para obtener resultados óptimos, siga las instrucciones piloto lo más cerca posible.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>

### <a name="pilot-playbook-phases"></a><span data-ttu-id="8dfd0-127">Fases piloto del libro de juegos</span><span class="sxs-lookup"><span data-stu-id="8dfd0-127">Pilot playbook phases</span></span>

<span data-ttu-id="8dfd0-128">Hay cuatro fases en la ejecución de un Microsoft 365 Defender piloto:</span><span class="sxs-lookup"><span data-stu-id="8dfd0-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="8dfd0-129">Fase</span><span class="sxs-lookup"><span data-stu-id="8dfd0-129">Phase</span></span> | <span data-ttu-id="8dfd0-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dfd0-130">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="8dfd0-131">Planeación</span><span class="sxs-lookup"><span data-stu-id="8dfd0-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="8dfd0-132">~ 1 día</span><span class="sxs-lookup"><span data-stu-id="8dfd0-132">~ 1 day</span></span>| <span data-ttu-id="8dfd0-133">Obtenga información sobre lo que debe tener en cuenta antes de ejecutar Microsoft 365 Defender proyecto piloto:</span><span class="sxs-lookup"><span data-stu-id="8dfd0-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="8dfd0-134">- Ámbito</span><span class="sxs-lookup"><span data-stu-id="8dfd0-134">- Scope</span></span> <br> <span data-ttu-id="8dfd0-135">- Casos de uso</span><span class="sxs-lookup"><span data-stu-id="8dfd0-135">- Use cases</span></span> <br><span data-ttu-id="8dfd0-136">- Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dfd0-136">- Requirements</span></span> <br><span data-ttu-id="8dfd0-137">- Plan de prueba</span><span class="sxs-lookup"><span data-stu-id="8dfd0-137">- Test plan</span></span> <br> <span data-ttu-id="8dfd0-138">- Criterios de éxito</span><span class="sxs-lookup"><span data-stu-id="8dfd0-138">- Success criteria</span></span> <br> <span data-ttu-id="8dfd0-139">- Cuadro de mandos</span><span class="sxs-lookup"><span data-stu-id="8dfd0-139">- Scorecard</span></span> 
| [<span data-ttu-id="8dfd0-140">Preparación</span><span class="sxs-lookup"><span data-stu-id="8dfd0-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="8dfd0-141">~2 días</span><span class="sxs-lookup"><span data-stu-id="8dfd0-141">~2 days</span></span>|  <span data-ttu-id="8dfd0-142">Obtenga Microsoft 365 Security Center para configurar su Microsoft 365 Defender piloto.</span><span class="sxs-lookup"><span data-stu-id="8dfd0-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="8dfd0-143">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="8dfd0-143">You'll be guided to:</span></span><br><br><span data-ttu-id="8dfd0-144">- Identificar partes interesadas y buscar el inicio de sesión para el piloto</span><span class="sxs-lookup"><span data-stu-id="8dfd0-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="8dfd0-145">- Consideraciones sobre el entorno</span><span class="sxs-lookup"><span data-stu-id="8dfd0-145">- Environment considerations</span></span> <br><span data-ttu-id="8dfd0-146">- Access</span><span class="sxs-lookup"><span data-stu-id="8dfd0-146">- Access</span></span> <br><span data-ttu-id="8dfd0-147">- Azure Active Directory configuración</span><span class="sxs-lookup"><span data-stu-id="8dfd0-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="8dfd0-148">- Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="8dfd0-148">- Configuration order</span></span> <br> <span data-ttu-id="8dfd0-149">- Registrarse para la Microsoft 365 E5 prueba</span><span class="sxs-lookup"><span data-stu-id="8dfd0-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="8dfd0-150">- Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="8dfd0-150">- Configure domain</span></span> <br><span data-ttu-id="8dfd0-151">- Asignar Microsoft 365 E5 licencias</span><span class="sxs-lookup"><span data-stu-id="8dfd0-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="8dfd0-152">- Completar el asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="8dfd0-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="8dfd0-153">Simulación de ataque</span><span class="sxs-lookup"><span data-stu-id="8dfd0-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="8dfd0-154">~2 días</span><span class="sxs-lookup"><span data-stu-id="8dfd0-154">~2 days</span></span>| <span data-ttu-id="8dfd0-155">Para simular un ataque, se te guiará a:</span><span class="sxs-lookup"><span data-stu-id="8dfd0-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="8dfd0-156">- Comprobar los requisitos del entorno de prueba</span><span class="sxs-lookup"><span data-stu-id="8dfd0-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="8dfd0-157">- Ejecutar la simulación</span><span class="sxs-lookup"><span data-stu-id="8dfd0-157">-  Run the simulation</span></span> <br><span data-ttu-id="8dfd0-158">- Investigar un incidente</span><span class="sxs-lookup"><span data-stu-id="8dfd0-158">- Investigate an incident</span></span> <br><span data-ttu-id="8dfd0-159">- resolver el incidente</span><span class="sxs-lookup"><span data-stu-id="8dfd0-159">- resolve the incident</span></span> 
| [<span data-ttu-id="8dfd0-160">Cierre y resumen</span><span class="sxs-lookup"><span data-stu-id="8dfd0-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="8dfd0-161">~ 1 día</span><span class="sxs-lookup"><span data-stu-id="8dfd0-161">~ 1 day</span></span>| <span data-ttu-id="8dfd0-162">Cuando haya llegado al final del proceso, se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="8dfd0-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="8dfd0-163">- Ir a través de la salida final</span><span class="sxs-lookup"><span data-stu-id="8dfd0-163">- Go through your final output</span></span><br><span data-ttu-id="8dfd0-164">- Presentar los resultados a las partes interesadas</span><span class="sxs-lookup"><span data-stu-id="8dfd0-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="8dfd0-165">- Proporcionar comentarios</span><span class="sxs-lookup"><span data-stu-id="8dfd0-165">- Provide feedback</span></span> <br><span data-ttu-id="8dfd0-166">- Siga los pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8dfd0-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="8dfd0-167">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="8dfd0-167">Next step</span></span>

|[<span data-ttu-id="8dfd0-168">Fase de planeación</span><span class="sxs-lookup"><span data-stu-id="8dfd0-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="8dfd0-169">Planear el Microsoft 365 Defender piloto</span><span class="sxs-lookup"><span data-stu-id="8dfd0-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
