---
title: Ejecutar el proyecto piloto Microsoft 365 Defender
description: Ejecute el proyecto piloto Microsoft 365 Defender en producción para determinar eficazmente los beneficios y la adopción de Microsoft 365 Defender.
keywords: Microsoft 365 Piloto de Defender, ejecutar proyecto piloto de Microsoft 365 Defender, evaluar Microsoft 365 Defender en producción, proyecto piloto de Microsoft 365 Defender, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
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
ms.openlocfilehash: 3219b329c53c32e02cd29acdd41a48cd93b2e8bb
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930516"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="60a3f-104">Ejecutar el proyecto piloto Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60a3f-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="60a3f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="60a3f-105">**Applies to:**</span></span>
- <span data-ttu-id="60a3f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60a3f-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="60a3f-107">Esta guía te ayuda a ejecutar un proyecto piloto proporcionando punteros para asegurarte de que tienes un plan bien estructurado, guiándolo a través del uso de la característica de simulación de ataques y, por último, concluyendo el piloto con claves para que reflexiones y documentes los resultados.</span><span class="sxs-lookup"><span data-stu-id="60a3f-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fases en la ejecución de un piloto Microsoft 365 Defender](../../media/pilotphases.png)


<span data-ttu-id="60a3f-109">La ejecución de un piloto le ayuda a determinar eficazmente las ventajas de adoptar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="60a3f-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="60a3f-110">Antes de habilitar Microsoft 365 Defender en el entorno de producción e iniciar los casos de uso, lo mejor es planear determinar las tareas que se deben realizar para el proyecto piloto y establecer los criterios de éxito.</span><span class="sxs-lookup"><span data-stu-id="60a3f-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="60a3f-111">Cómo usar este libro de juegos piloto</span><span class="sxs-lookup"><span data-stu-id="60a3f-111">How to use this pilot playbook</span></span>

<span data-ttu-id="60a3f-112">Esta guía proporciona información general sobre Microsoft 365 Defender e instrucciones paso a paso sobre cómo configurar el proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="60a3f-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="60a3f-113">Microsoft 365 Defender es un conjunto unificado de defensa empresarial anterior y posterior a la infracción que coordina de forma nativa la protección, la detección, la prevención, la investigación y la respuesta entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="60a3f-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="60a3f-114">Lo hace combinando y orquestando las siguientes funcionalidades en una única solución de seguridad:</span><span class="sxs-lookup"><span data-stu-id="60a3f-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="60a3f-115">Microsoft Defender para el extremo (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="60a3f-115">Microsoft Defender for Endpoint (endpoints)</span></span>
  - <span data-ttu-id="60a3f-116">Microsoft Defender para Office 365 (correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="60a3f-116">Microsoft Defender for Office 365 (email)</span></span> 
  - <span data-ttu-id="60a3f-117">Microsoft Defender para identidad (identidad)</span><span class="sxs-lookup"><span data-stu-id="60a3f-117">Microsoft Defender for Identity (identity)</span></span> 
  - <span data-ttu-id="60a3f-118">Microsoft Cloud App Security (aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="60a3f-118">Microsoft Cloud App Security (apps)</span></span>

![Imagen of_Microsoft solución de 365 Defender para usuarios, Microsoft Defender para identidad, para puntos de conexión de Microsoft Defender para endpoint, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="60a3f-120">Con la solución integrada de Microsoft 365 Defender, los profesionales de seguridad pueden unir las señales de amenaza que Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Defender para Identity y Microsoft Cloud App Security reciben y determinar el alcance completo y el impacto de la amenaza, cómo entró en el entorno, qué está afectado y cómo afecta actualmente a la organización.</span><span class="sxs-lookup"><span data-stu-id="60a3f-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="60a3f-121">Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto sanar los buzones, puntos de conexión e identidades de usuario afectados.</span><span class="sxs-lookup"><span data-stu-id="60a3f-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="60a3f-122">Consulta la [información general Microsoft 365 Defender para](microsoft-365-defender.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="60a3f-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="60a3f-123">La escala de tiempo de ejemplo siguiente varía en función de tener los recursos adecuados en el entorno.</span><span class="sxs-lookup"><span data-stu-id="60a3f-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="60a3f-124">Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que los demás.</span><span class="sxs-lookup"><span data-stu-id="60a3f-124">Some detections and workflows might need more learning time than the others.</span></span>

![Escala de tiempo de ejemplo en la ejecución de un piloto Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="60a3f-126">Para obtener resultados óptimos, siga las instrucciones piloto lo más cerca posible.</span><span class="sxs-lookup"><span data-stu-id="60a3f-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="60a3f-127">Fases piloto del libro de juegos</span><span class="sxs-lookup"><span data-stu-id="60a3f-127">Pilot playbook phases</span></span> 

<span data-ttu-id="60a3f-128">Hay cuatro fases en la ejecución de un piloto de Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="60a3f-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="60a3f-129">Fase</span><span class="sxs-lookup"><span data-stu-id="60a3f-129">Phase</span></span> | <span data-ttu-id="60a3f-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="60a3f-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="60a3f-131">Planeación</span><span class="sxs-lookup"><span data-stu-id="60a3f-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="60a3f-132">~ 1 día</span><span class="sxs-lookup"><span data-stu-id="60a3f-132">~ 1 day</span></span>| <span data-ttu-id="60a3f-133">Obtenga información sobre lo que debe tener en cuenta antes de ejecutar el proyecto piloto de Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="60a3f-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="60a3f-134">- Ámbito</span><span class="sxs-lookup"><span data-stu-id="60a3f-134">- Scope</span></span> <br> <span data-ttu-id="60a3f-135">- Casos de uso</span><span class="sxs-lookup"><span data-stu-id="60a3f-135">- Use cases</span></span> <br><span data-ttu-id="60a3f-136">- Requisitos</span><span class="sxs-lookup"><span data-stu-id="60a3f-136">- Requirements</span></span> <br><span data-ttu-id="60a3f-137">- Plan de prueba</span><span class="sxs-lookup"><span data-stu-id="60a3f-137">- Test plan</span></span> <br> <span data-ttu-id="60a3f-138">- Criterios de éxito</span><span class="sxs-lookup"><span data-stu-id="60a3f-138">- Success criteria</span></span> <br> <span data-ttu-id="60a3f-139">- Cuadro de mandos</span><span class="sxs-lookup"><span data-stu-id="60a3f-139">- Scorecard</span></span> 
| [<span data-ttu-id="60a3f-140">Preparación</span><span class="sxs-lookup"><span data-stu-id="60a3f-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="60a3f-141">~2 días</span><span class="sxs-lookup"><span data-stu-id="60a3f-141">~2 days</span></span>|  <span data-ttu-id="60a3f-142">Acceda Microsoft 365 Security Center para configurar el entorno piloto de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="60a3f-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="60a3f-143">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="60a3f-143">You'll be guided to:</span></span><br><br><span data-ttu-id="60a3f-144">- Identificar partes interesadas y buscar el inicio de sesión para el piloto</span><span class="sxs-lookup"><span data-stu-id="60a3f-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="60a3f-145">- Consideraciones sobre el entorno</span><span class="sxs-lookup"><span data-stu-id="60a3f-145">- Environment considerations</span></span> <br><span data-ttu-id="60a3f-146">- Access</span><span class="sxs-lookup"><span data-stu-id="60a3f-146">- Access</span></span> <br><span data-ttu-id="60a3f-147">- Azure Active Directory configuración</span><span class="sxs-lookup"><span data-stu-id="60a3f-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="60a3f-148">- Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="60a3f-148">- Configuration order</span></span> <br> <span data-ttu-id="60a3f-149">- Registrarse para la Microsoft 365 E5 prueba</span><span class="sxs-lookup"><span data-stu-id="60a3f-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="60a3f-150">- Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="60a3f-150">- Configure domain</span></span> <br><span data-ttu-id="60a3f-151">- Asignar Microsoft 365 E5 licencias</span><span class="sxs-lookup"><span data-stu-id="60a3f-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="60a3f-152">- Completar el asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="60a3f-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="60a3f-153">Simulación de ataque</span><span class="sxs-lookup"><span data-stu-id="60a3f-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="60a3f-154">~2 días</span><span class="sxs-lookup"><span data-stu-id="60a3f-154">~2 days</span></span>| <span data-ttu-id="60a3f-155">Para simular un ataque, se te guiará a:</span><span class="sxs-lookup"><span data-stu-id="60a3f-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="60a3f-156">- Comprobar los requisitos del entorno de prueba</span><span class="sxs-lookup"><span data-stu-id="60a3f-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="60a3f-157">- Ejecutar la simulación</span><span class="sxs-lookup"><span data-stu-id="60a3f-157">-  Run the simulation</span></span> <br><span data-ttu-id="60a3f-158">- Investigar un incidente</span><span class="sxs-lookup"><span data-stu-id="60a3f-158">- Investigate an incident</span></span> <br><span data-ttu-id="60a3f-159">- resolver el incidente</span><span class="sxs-lookup"><span data-stu-id="60a3f-159">- resolve the incident</span></span> 
| [<span data-ttu-id="60a3f-160">Cierre y resumen</span><span class="sxs-lookup"><span data-stu-id="60a3f-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="60a3f-161">~ 1 día</span><span class="sxs-lookup"><span data-stu-id="60a3f-161">~ 1 day</span></span>| <span data-ttu-id="60a3f-162">Cuando haya llegado al final del proceso, se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="60a3f-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="60a3f-163">- Ir a través de la salida final</span><span class="sxs-lookup"><span data-stu-id="60a3f-163">- Go through your final output</span></span><br><span data-ttu-id="60a3f-164">- Presentar los resultados a las partes interesadas</span><span class="sxs-lookup"><span data-stu-id="60a3f-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="60a3f-165">- Proporcionar comentarios</span><span class="sxs-lookup"><span data-stu-id="60a3f-165">- Provide feedback</span></span> <br><span data-ttu-id="60a3f-166">- Siga los pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="60a3f-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="60a3f-167">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="60a3f-167">Next step</span></span>
|[<span data-ttu-id="60a3f-168">Fase de planeación</span><span class="sxs-lookup"><span data-stu-id="60a3f-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="60a3f-169">Planear el proyecto piloto Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60a3f-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
