---
title: Ejecutar el proyecto piloto de Microsoft 365 Defender
description: Ejecute el proyecto piloto de Microsoft 365 Defender en producción para determinar eficazmente los beneficios y la adopción de Microsoft 365 Defender.
keywords: Piloto de Protección contra amenazas de Microsoft, ejecutar proyecto piloto de Protección contra amenazas de Microsoft, evaluar la Protección contra amenazas de Microsoft en producción, proyecto piloto de Protección contra amenazas de Microsoft, seguridad cibernética, amenaza persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizada, búsqueda avanzada
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933035"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="bc791-104">Ejecutar el proyecto piloto de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc791-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bc791-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bc791-105">**Applies to:**</span></span>
- <span data-ttu-id="bc791-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc791-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="bc791-107">Esta guía le ayuda a ejecutar un proyecto piloto proporcionando punteros para asegurarse de que tiene un plan bien estructurado, guiándolo a través del uso de la característica de simulación de ataques y, por último, concluyendo el piloto con puntos clave para que se reflejen y documenten los resultados.</span><span class="sxs-lookup"><span data-stu-id="bc791-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fases en la ejecución de un piloto de Microsoft 365 Defender](../../media/pilotphases.png)


<span data-ttu-id="bc791-109">La ejecución de un piloto le ayuda a determinar eficazmente las ventajas de adoptar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bc791-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="bc791-110">Antes de habilitar Microsoft 365 Defender en su entorno de producción e iniciar los casos de uso, es mejor planear determinar las tareas que se deben realizar para el proyecto piloto y establecer los criterios de éxito.</span><span class="sxs-lookup"><span data-stu-id="bc791-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="bc791-111">Cómo usar este libro de juegos piloto</span><span class="sxs-lookup"><span data-stu-id="bc791-111">How to use this pilot playbook</span></span>

<span data-ttu-id="bc791-112">En esta guía se proporciona información general sobre Microsoft 365 Defender e instrucciones paso a paso sobre cómo configurar el proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="bc791-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="bc791-113">Microsoft 365 Defender es un conjunto unificado de defensa empresarial anterior y posterior a la infracción que coordina de forma nativa la protección, la detección, la prevención, la investigación y la respuesta entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="bc791-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="bc791-114">Para ello, combina y orquesta las siguientes funcionalidades en una única solución de seguridad:</span><span class="sxs-lookup"><span data-stu-id="bc791-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="bc791-115">Microsoft Defender para Endpoint, el nuevo nombre de Protección contra amenazas avanzada de Microsoft Defender (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="bc791-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="bc791-116">Microsoft Defender para Office 365, el nuevo nombre de ATP de Office 365 (correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="bc791-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="bc791-117">Microsoft Defender for Identity, el nuevo nombre de Azure ATP (identidad)</span><span class="sxs-lookup"><span data-stu-id="bc791-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="bc791-118">Microsoft Cloud App Security (aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="bc791-118">Microsoft Cloud App Security (apps)</span></span>

![Imagen of_Microsoft solución de Defender 365 para usuarios, Microsoft Defender para Identidad, para puntos de conexión de Microsoft Defender para puntos de conexión, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="bc791-120">Con la solución integrada de Microsoft 365 Defender, los profesionales de seguridad pueden unir las señales de amenaza que Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Defender para Identity y Microsoft Cloud App Security reciben, así como determinar el alcance completo y el impacto de la amenaza, cómo se introdujo en el entorno, qué se ve afectado y cómo afecta actualmente a la organización.</span><span class="sxs-lookup"><span data-stu-id="bc791-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="bc791-121">Microsoft 365 Defender toma medidas automáticas para evitar o detener el ataque y sanar automáticamente los buzones de correo, los puntos de conexión y las identidades de usuario afectados.</span><span class="sxs-lookup"><span data-stu-id="bc791-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="bc791-122">Consulte la introducción [a Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bc791-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="bc791-123">La siguiente escala de tiempo de ejemplo varía en función de tener los recursos adecuados en su entorno.</span><span class="sxs-lookup"><span data-stu-id="bc791-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="bc791-124">Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que las otras.</span><span class="sxs-lookup"><span data-stu-id="bc791-124">Some detections and workflows might need more learning time than the others.</span></span>

![Escala de tiempo de ejemplo en la ejecución de un piloto de Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="bc791-126">Para obtener resultados óptimos, siga las instrucciones piloto lo más cerca posible.</span><span class="sxs-lookup"><span data-stu-id="bc791-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="bc791-127">Fases del libro de juegos piloto</span><span class="sxs-lookup"><span data-stu-id="bc791-127">Pilot playbook phases</span></span> 

<span data-ttu-id="bc791-128">Hay cuatro fases para ejecutar una prueba piloto de Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="bc791-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="bc791-129">Fase</span><span class="sxs-lookup"><span data-stu-id="bc791-129">Phase</span></span> | <span data-ttu-id="bc791-130">Description</span><span class="sxs-lookup"><span data-stu-id="bc791-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="bc791-131">Planeación</span><span class="sxs-lookup"><span data-stu-id="bc791-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="bc791-132">~ 1 día</span><span class="sxs-lookup"><span data-stu-id="bc791-132">~ 1 day</span></span>| <span data-ttu-id="bc791-133">Obtenga información sobre lo que debe tener en cuenta antes de ejecutar el proyecto piloto de Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="bc791-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="bc791-134">- Ámbito</span><span class="sxs-lookup"><span data-stu-id="bc791-134">- Scope</span></span> <br> <span data-ttu-id="bc791-135">- Casos de uso</span><span class="sxs-lookup"><span data-stu-id="bc791-135">- Use cases</span></span> <br><span data-ttu-id="bc791-136">- Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc791-136">- Requirements</span></span> <br><span data-ttu-id="bc791-137">- Plan de prueba</span><span class="sxs-lookup"><span data-stu-id="bc791-137">- Test plan</span></span> <br> <span data-ttu-id="bc791-138">- Criterios de éxito</span><span class="sxs-lookup"><span data-stu-id="bc791-138">- Success criteria</span></span> <br> <span data-ttu-id="bc791-139">- Cuadro de mandos</span><span class="sxs-lookup"><span data-stu-id="bc791-139">- Scorecard</span></span> 
| [<span data-ttu-id="bc791-140">Preparación</span><span class="sxs-lookup"><span data-stu-id="bc791-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="bc791-141">~2 días</span><span class="sxs-lookup"><span data-stu-id="bc791-141">~2 days</span></span>|  <span data-ttu-id="bc791-142">Acceda al Centro de seguridad de Microsoft 365 para configurar su entorno piloto de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bc791-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="bc791-143">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="bc791-143">You'll be guided to:</span></span><br><br><span data-ttu-id="bc791-144">- Identificar a las partes interesadas y buscar el inicio de sesión para el piloto</span><span class="sxs-lookup"><span data-stu-id="bc791-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="bc791-145">- Consideraciones de entorno</span><span class="sxs-lookup"><span data-stu-id="bc791-145">- Environment considerations</span></span> <br><span data-ttu-id="bc791-146">- Acceso</span><span class="sxs-lookup"><span data-stu-id="bc791-146">- Access</span></span> <br><span data-ttu-id="bc791-147">- Configuración de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bc791-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="bc791-148">- Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="bc791-148">- Configuration order</span></span> <br> <span data-ttu-id="bc791-149">- Registrarse para la prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bc791-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="bc791-150">- Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="bc791-150">- Configure domain</span></span> <br><span data-ttu-id="bc791-151">- Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bc791-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="bc791-152">- Completar el asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="bc791-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="bc791-153">Simulación de ataque</span><span class="sxs-lookup"><span data-stu-id="bc791-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="bc791-154">~2 días</span><span class="sxs-lookup"><span data-stu-id="bc791-154">~2 days</span></span>| <span data-ttu-id="bc791-155">Para simular un ataque, se te guiará a:</span><span class="sxs-lookup"><span data-stu-id="bc791-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="bc791-156">- Comprobar los requisitos del entorno de prueba</span><span class="sxs-lookup"><span data-stu-id="bc791-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="bc791-157">- Ejecutar la simulación</span><span class="sxs-lookup"><span data-stu-id="bc791-157">-  Run the simulation</span></span> <br><span data-ttu-id="bc791-158">- Investigar un incidente</span><span class="sxs-lookup"><span data-stu-id="bc791-158">- Investigate an incident</span></span> <br><span data-ttu-id="bc791-159">- resolver el incidente</span><span class="sxs-lookup"><span data-stu-id="bc791-159">- resolve the incident</span></span> 
| [<span data-ttu-id="bc791-160">Cierre y resumen</span><span class="sxs-lookup"><span data-stu-id="bc791-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="bc791-161">~ 1 día</span><span class="sxs-lookup"><span data-stu-id="bc791-161">~ 1 day</span></span>| <span data-ttu-id="bc791-162">Cuando haya llegado al final del proceso, se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="bc791-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="bc791-163">- Ir a través de la salida final</span><span class="sxs-lookup"><span data-stu-id="bc791-163">- Go through your final output</span></span><br><span data-ttu-id="bc791-164">- Presentar los resultados a las partes interesadas</span><span class="sxs-lookup"><span data-stu-id="bc791-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="bc791-165">- Proporcionar comentarios</span><span class="sxs-lookup"><span data-stu-id="bc791-165">- Provide feedback</span></span> <br><span data-ttu-id="bc791-166">- Siga los pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bc791-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="bc791-167">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="bc791-167">Next step</span></span>
|[<span data-ttu-id="bc791-168">Fase de planeación</span><span class="sxs-lookup"><span data-stu-id="bc791-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="bc791-169">Planear el proyecto piloto de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc791-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
