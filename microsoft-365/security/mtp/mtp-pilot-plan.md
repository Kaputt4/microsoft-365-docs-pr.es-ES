---
title: Planeación de un proyecto piloto de Microsoft 365 defender
description: Planifique el proyecto piloto de Microsoft 365 defender con las partes interesadas para administrar las expectativas y garantizar un resultado correcto.
keywords: Microsoft Threat Protection Pilot, plan Pilot proyecto de protección contra amenazas de Microsoft, evaluación de la protección contra amenazas de Microsoft en producción, Microsoft Threat Protection Pilot Project, Cyber Security, prevención persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
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
ms.openlocfilehash: ec2bfe52308231577e4f2749e1f4cdf24a36f604
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846025"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="d5e8b-104">Planeación de un proyecto piloto de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d5e8b-104">Planning your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d5e8b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d5e8b-105">**Applies to:**</span></span>
- <span data-ttu-id="d5e8b-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d5e8b-106">Microsoft 365 Defender</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft 365 Defender project" title="Planeación de un proyecto piloto de Microsoft 365 defender" />
      <br/><span data-ttu-id="d5e8b-108">Pensado</a></span><span class="sxs-lookup"><span data-stu-id="d5e8b-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 defender" />
      <br/><span data-ttu-id="d5e8b-110">Preparación</a></span><span class="sxs-lookup"><span data-stu-id="d5e8b-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft 365 Defender attack simulations" title="Ejecutar las simulaciones de ataque de Microsoft 365 defender" />
     <br/><span data-ttu-id="d5e8b-112">Simular ataque</a></span><span class="sxs-lookup"><span data-stu-id="d5e8b-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft 365 Defender pilot" title="Cierre y resuma el piloto de Microsoft 365 defender" />
     <br/><span data-ttu-id="d5e8b-114">Cerrar y resumir</a></span><span class="sxs-lookup"><span data-stu-id="d5e8b-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="d5e8b-115">Actualmente está en la fase de planeación.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="d5e8b-116">Para asegurarse de que el proyecto piloto es un éxito, es esencial que se planee minuciosamente y obtenga aprobaciones de las partes interesadas desde el principio.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="d5e8b-117">Los elementos de planeación incluyen el ámbito de identificación, los casos de uso, los requisitos y los criterios de éxito.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="d5e8b-118">En esta guía se explica cómo planear el proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="d5e8b-119">Para obtener resultados óptimos, siga las instrucciones piloto de la forma más parecida posible.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="d5e8b-120">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d5e8b-120">Scope</span></span>

<span data-ttu-id="d5e8b-121">El ámbito del proyecto piloto determinará la amplitud de la prueba, en función de su entorno y de métodos de prueba aceptables.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="d5e8b-122">Estos son algunos de los ámbitos de ejemplo que se deben tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="d5e8b-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="d5e8b-123">Entorno de desarrollo o prueba que incluye extremos, servidores y controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="d5e8b-124">Entorno de producción con Microsoft 365, Azure, servicios de Active Directory, extremos y servidores</span><span class="sxs-lookup"><span data-stu-id="d5e8b-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="d5e8b-125">Si aún no dispone de licencias completas, puede obtener licencias de prueba para [evaluar Microsoft 365 defender](https://aka.ms/mtp-trial-lab) : planear, preparar, configurar, configurar y ejecutar el proyecto piloto.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="d5e8b-126">Las partes interesadas desempeñarán un papel importante en ayudar a facilitar el proceso desde el principio hasta el final.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="d5e8b-127">Los tipos de sistemas operativos que se van a evaluar también deben definirse en función de la estructura organizativa.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="d5e8b-128">Esto puede incluir lo siguiente: [extremos Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [servidores Linux](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [puntos de conexión windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span><span class="sxs-lookup"><span data-stu-id="d5e8b-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="d5e8b-129">Casos de uso</span><span class="sxs-lookup"><span data-stu-id="d5e8b-129">Use cases</span></span>

<span data-ttu-id="d5e8b-130">Los casos de uso representan instrucciones sobre cómo la herramienta que se está probando va a ser consumida por los usuarios previstos.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="d5e8b-131">Se pueden formular como casos de usuario desde el punto de vista de un rol en particular, como un analista de SOC.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="d5e8b-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5e8b-132">For example:</span></span>
- <span data-ttu-id="d5e8b-133">Como Analista de SOC, necesito ver, correlacionar, evaluar y administrar alertas y eventos a través de dispositivos, usuarios y buzones de correo en mi red.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="d5e8b-134">[Administración de incidentes]</span><span class="sxs-lookup"><span data-stu-id="d5e8b-134">[Incident management]</span></span>
- <span data-ttu-id="d5e8b-135">Como Analista de SOC, debo tener la herramienta y el proceso para investigar y responder automáticamente a eventos malintencionados en mi red.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="d5e8b-136">[Auto IR]</span><span class="sxs-lookup"><span data-stu-id="d5e8b-136">[Auto IR]</span></span>
- <span data-ttu-id="d5e8b-137">Como Analista de SOC, debo buscar datos de mi entorno para encontrar amenazas conocidas y potenciales, así como actividades sospechosas.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="d5e8b-138">[Caza avanzado]</span><span class="sxs-lookup"><span data-stu-id="d5e8b-138">[Advanced Hunting]</span></span>

<span data-ttu-id="d5e8b-139">Tenga en cuenta que estos casos de uso deben crearse dentro de los parámetros del ámbito definido.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="d5e8b-140">Si, por ejemplo, el ámbito de las pruebas no incluye una evaluación de herramientas como Microsoft Cloud App Security, use casos que dependan de esto como no se debe crear un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="d5e8b-141">Requirements</span><span class="sxs-lookup"><span data-stu-id="d5e8b-141">Requirements</span></span>

<span data-ttu-id="d5e8b-142">En la lista de casos de uso, puede empezar a crear requisitos.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="d5e8b-143">Los requisitos incluyen características que una herramienta debe tener para satisfacer los casos de uso.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="d5e8b-144">Estos requisitos pueden dividirse en categorías como la configuración y el mantenimiento, la compatibilidad con las integraciones y los requisitos específicos de características, como la capacidad de búsqueda y la capacidad de crear alertas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="d5e8b-145">Plan de pruebas</span><span class="sxs-lookup"><span data-stu-id="d5e8b-145">Test plan</span></span>

<span data-ttu-id="d5e8b-146">Según los requisitos, los distintos métodos de prueba pueden ser apropiados.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="d5e8b-147">Por ejemplo, si el requisito es evaluar la eficacia de la corrección automatizada, el plan de pruebas debe incluir pasos para generar los comportamientos que desencadenarían una acción de corrección automatizada en Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft 365 Defender.</span></span> <span data-ttu-id="d5e8b-148">Si el requisito es detectar un comportamiento o ataque en particular, la prueba puede implicar más pasos.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="d5e8b-149">El punto es disponer de un plan para realizar pruebas con precisión de los requisitos.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="d5e8b-150">Criterios de éxito</span><span class="sxs-lookup"><span data-stu-id="d5e8b-150">Success criteria</span></span>

<span data-ttu-id="d5e8b-151">Los criterios de éxito son en última instancia la barra que se debe medir con respecto a lo que se está probando.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="d5e8b-152">Ya sea para probar Microsoft 365 defender (o cualquier otra tecnología) con otras herramientas o por sí misma, debe haber algunos criterios cuantificables para determinar el valor que proporciona la herramienta.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-152">Whether you are testing Microsoft 365 Defender (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="d5e8b-153">Según el ámbito, los requisitos y el plan de pruebas, los criterios de éxito determinarán cómo puntuar la prueba.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="d5e8b-154">Debe ser inferior a pass o Fail y más de una puntuación ponderada según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="d5e8b-155">Por ejemplo, para que funcione correctamente, es posible que una herramienta necesite puntuar por encima del 80% en determinadas áreas críticas que identifique.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="d5e8b-156">Puntua</span><span class="sxs-lookup"><span data-stu-id="d5e8b-156">Scorecard</span></span>

<span data-ttu-id="d5e8b-157">Una forma de llevar a cabo juntos todos los elementos del plan puede ser crear un cuadro de mandos.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="d5e8b-158">Vea un cuadro de mandos de muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="d5e8b-158">See a sample scorecard below:</span></span>

| <span data-ttu-id="d5e8b-159">Caso de uso</span><span class="sxs-lookup"><span data-stu-id="d5e8b-159">Use case</span></span> | <span data-ttu-id="d5e8b-160">Requirements</span><span class="sxs-lookup"><span data-stu-id="d5e8b-160">Requirements</span></span> | <span data-ttu-id="d5e8b-161">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="d5e8b-161">Configuration requirements</span></span> | <span data-ttu-id="d5e8b-162">Plan de pruebas</span><span class="sxs-lookup"><span data-stu-id="d5e8b-162">Test plan</span></span> | <span data-ttu-id="d5e8b-163">Resultado previsto</span><span class="sxs-lookup"><span data-stu-id="d5e8b-163">Expected outcome</span></span> | <span data-ttu-id="d5e8b-164">Estado de la prueba</span><span class="sxs-lookup"><span data-stu-id="d5e8b-164">Test status</span></span> | <span data-ttu-id="d5e8b-165">Puntuación</span><span class="sxs-lookup"><span data-stu-id="d5e8b-165">Score</span></span> | <span data-ttu-id="d5e8b-166">Notas</span><span class="sxs-lookup"><span data-stu-id="d5e8b-166">Notes</span></span> |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="d5e8b-167">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="d5e8b-167">Incident management</span></span>|<span data-ttu-id="d5e8b-168">-Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d5e8b-168">-  Microsoft 365 Defender</span></span>  </br></br><span data-ttu-id="d5e8b-169">-Microsoft defender para identidad</span><span class="sxs-lookup"><span data-stu-id="d5e8b-169">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="d5e8b-170">-Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d5e8b-170">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="d5e8b-171">-Microsoft Cloud App Security (opcional)</span><span class="sxs-lookup"><span data-stu-id="d5e8b-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="d5e8b-172">Vea los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, configuración y configuración para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="d5e8b-173">Simular ataque</span><span class="sxs-lookup"><span data-stu-id="d5e8b-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="d5e8b-174">Investigar el incidente</span><span class="sxs-lookup"><span data-stu-id="d5e8b-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="d5e8b-175">Los investigadores pueden comprender el alcance y el impacto del incidente y administrar el incidente.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="d5e8b-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="d5e8b-176">AutoIR</span></span>|<span data-ttu-id="d5e8b-177">-Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d5e8b-177">-   Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="d5e8b-178">-Microsoft defender para identidad</span><span class="sxs-lookup"><span data-stu-id="d5e8b-178">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="d5e8b-179">-Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d5e8b-179">- Microsoft Defender for Endpoint</span></span> |<span data-ttu-id="d5e8b-180">Vea los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, configuración y configuración para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="d5e8b-181">Habilitar AutoIR</span><span class="sxs-lookup"><span data-stu-id="d5e8b-181">Enable AutoIR</span></span>  |[<span data-ttu-id="d5e8b-182">Simular ataque</span><span class="sxs-lookup"><span data-stu-id="d5e8b-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="d5e8b-183">Investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="d5e8b-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="d5e8b-184">Las alertas y los incidentes son corregidos automáticamente por Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d5e8b-184">Alerts and incidents are automatically remediated by Microsoft 365 Defender</span></span>||||
|<span data-ttu-id="d5e8b-185">Búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="d5e8b-185">Advanced hunting</span></span>|<span data-ttu-id="d5e8b-186">-Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d5e8b-186">- Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="d5e8b-187">-Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d5e8b-187">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="d5e8b-188">-Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d5e8b-188">-Microsoft Defender for Office 365</span></span> |<span data-ttu-id="d5e8b-189">Vea los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, configuración y configuración para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="d5e8b-190">Escenario de caza avanzado</span><span class="sxs-lookup"><span data-stu-id="d5e8b-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="d5e8b-191">Los investigadores pueden encontrar datos a través de la búsqueda avanzada, dinamizar las entidades afectadas y crear detecciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d5e8b-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="d5e8b-192">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d5e8b-192">Next step</span></span>
|<span data-ttu-id="d5e8b-193">![Fase de preparación](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="d5e8b-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="d5e8b-194">Fase de preparación</span><span class="sxs-lookup"><span data-stu-id="d5e8b-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="d5e8b-195">Preparar el entorno piloto de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d5e8b-195">Prepare your Microsoft 365 Defender pilot environment</span></span>
|:-------|:-----|
