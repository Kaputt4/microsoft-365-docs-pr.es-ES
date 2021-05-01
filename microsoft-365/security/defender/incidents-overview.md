---
title: Incidentes en Microsoft 365 Defender
description: Investigar incidentes vistos en dispositivos, usuarios y buzones en el Microsoft 365 de seguridad.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e2e29015d4cb5e04510577118eb847b9b596a6c5
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114287"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="29302-104">Incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29302-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="29302-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="29302-105">**Applies to:**</span></span>
- <span data-ttu-id="29302-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29302-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="29302-107">¿Quiere experimentar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="29302-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="29302-108">Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="29302-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="29302-109">Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que son la historia de un ataque.</span><span class="sxs-lookup"><span data-stu-id="29302-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="29302-110">Microsoft 365 servicios y aplicaciones crean alertas cuando detectan un evento o actividad sospechosos o malintencionados.</span><span class="sxs-lookup"><span data-stu-id="29302-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="29302-111">Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso.</span><span class="sxs-lookup"><span data-stu-id="29302-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="29302-112">Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones.</span><span class="sxs-lookup"><span data-stu-id="29302-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="29302-113">El resultado son varias alertas para varias entidades del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="29302-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="29302-114">Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada a un incidente.</span><span class="sxs-lookup"><span data-stu-id="29302-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Cómo Microsoft 365 Defender correlaciona eventos de entidades en un incidente":::

<span data-ttu-id="29302-116">Vea esta breve introducción a los incidentes en Microsoft 365 Defender (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="29302-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="29302-117">La agrupación de alertas relacionadas en un incidente le ofrece una vista completa de un ataque.</span><span class="sxs-lookup"><span data-stu-id="29302-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="29302-118">Por ejemplo, puede ver:</span><span class="sxs-lookup"><span data-stu-id="29302-118">For example, you can see:</span></span>

- <span data-ttu-id="29302-119">Donde se inició el ataque.</span><span class="sxs-lookup"><span data-stu-id="29302-119">Where the attack started.</span></span>
- <span data-ttu-id="29302-120">Qué tácticas se usaron.</span><span class="sxs-lookup"><span data-stu-id="29302-120">What tactics were used.</span></span>
- <span data-ttu-id="29302-121">Cuánto ha llegado el ataque a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="29302-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="29302-122">El ámbito del ataque, como el número de dispositivos, usuarios y buzones de correo afectados.</span><span class="sxs-lookup"><span data-stu-id="29302-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="29302-123">Todos los datos asociados con el ataque.</span><span class="sxs-lookup"><span data-stu-id="29302-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="29302-124">Si [está habilitado,](m365d-enable.md)Microsoft 365 Defender puede investigar y resolver alertas automáticamente a través de la automatización y la inteligencia artificial.</span><span class="sxs-lookup"><span data-stu-id="29302-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="29302-125">También puedes realizar pasos de corrección adicionales para resolver el ataque.</span><span class="sxs-lookup"><span data-stu-id="29302-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="29302-126">Incidentes y alertas en el centro Microsoft 365 seguridad</span><span class="sxs-lookup"><span data-stu-id="29302-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="29302-127">Puede administrar incidentes de **incidentes & alertas > incidentes en** el inicio rápido del centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="29302-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="29302-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29302-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La página Incidentes en el centro de Microsoft 365 seguridad":::

<span data-ttu-id="29302-130">Al seleccionar un nombre de incidente, se muestra un resumen del incidente y se proporciona acceso a las pestañas con información adicional.</span><span class="sxs-lookup"><span data-stu-id="29302-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el centro Microsoft 365 seguridad":::

<span data-ttu-id="29302-132">Las pestañas adicionales para un incidente son:</span><span class="sxs-lookup"><span data-stu-id="29302-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="29302-133">Alertas</span><span class="sxs-lookup"><span data-stu-id="29302-133">Alerts</span></span> 

  <span data-ttu-id="29302-134">Todas las alertas relacionadas con el incidente y su información.</span><span class="sxs-lookup"><span data-stu-id="29302-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="29302-135">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="29302-135">Devices</span></span>

  <span data-ttu-id="29302-136">Todos los dispositivos que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="29302-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="29302-137">Users</span><span class="sxs-lookup"><span data-stu-id="29302-137">Users</span></span>

  <span data-ttu-id="29302-138">Todos los usuarios identificados para formar parte del incidente o relacionados con ellos.</span><span class="sxs-lookup"><span data-stu-id="29302-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="29302-139">Buzones</span><span class="sxs-lookup"><span data-stu-id="29302-139">Mailboxes</span></span>

  <span data-ttu-id="29302-140">Todos los buzones que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="29302-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="29302-141">Investigaciones</span><span class="sxs-lookup"><span data-stu-id="29302-141">Investigations</span></span>

  <span data-ttu-id="29302-142">Todas las investigaciones automatizadas desencadenadas por alertas en el incidente.</span><span class="sxs-lookup"><span data-stu-id="29302-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="29302-143">Evidencia y respuesta</span><span class="sxs-lookup"><span data-stu-id="29302-143">Evidence and Response</span></span>

  <span data-ttu-id="29302-144">Todos los eventos admitidos y las entidades sospechosas en las alertas del incidente.</span><span class="sxs-lookup"><span data-stu-id="29302-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="29302-145">Esta es la relación entre un incidente y sus datos y las pestañas de un incidente en el centro Microsoft 365 seguridad.</span><span class="sxs-lookup"><span data-stu-id="29302-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="La relación de un incidente y sus datos con las pestañas de un incidente en el centro Microsoft 365 seguridad":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="29302-147">Flujo de trabajo de respuesta a incidentes de ejemplo para Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29302-147">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="29302-148">Este es un flujo de trabajo de ejemplo para responder a incidentes en Microsoft 365 con el centro Microsoft 365 seguridad.</span><span class="sxs-lookup"><span data-stu-id="29302-148">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Ejemplo de flujo de trabajo de respuesta a incidentes para Microsoft 365":::

<span data-ttu-id="29302-150">De forma continua, identifique los incidentes de mayor prioridad para el análisis y la resolución en la cola de incidentes y prepárese para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="29302-150">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="29302-151">Esta es una combinación de:</span><span class="sxs-lookup"><span data-stu-id="29302-151">This is a combination of:</span></span>

- <span data-ttu-id="29302-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span><span class="sxs-lookup"><span data-stu-id="29302-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="29302-153">[Administrar](manage-incidents.md) incidentes modificando su título, asignándolos a un analista y agregando etiquetas y comentarios.</span><span class="sxs-lookup"><span data-stu-id="29302-153">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="29302-154">Para cada incidente, comience un [análisis de ataques y alertas:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="29302-154">For each incident, begin an [attack and alert analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="29302-155">a.</span><span class="sxs-lookup"><span data-stu-id="29302-155">a.</span></span> <span data-ttu-id="29302-156">Vea el resumen del incidente para comprender su ámbito y gravedad y qué entidades se ven afectadas (la **pestaña Resumen).**</span><span class="sxs-lookup"><span data-stu-id="29302-156">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="29302-157">b.</span><span class="sxs-lookup"><span data-stu-id="29302-157">b.</span></span> <span data-ttu-id="29302-158">Comience a analizar las alertas para comprender su origen, ámbito y gravedad (la **pestaña** Alertas).</span><span class="sxs-lookup"><span data-stu-id="29302-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="29302-159">c.</span><span class="sxs-lookup"><span data-stu-id="29302-159">c.</span></span> <span data-ttu-id="29302-160">Según sea necesario, recopila información sobre dispositivos, usuarios y buzones afectados (las pestañas **Dispositivos,** **Usuarios** y **Buzones).**</span><span class="sxs-lookup"><span data-stu-id="29302-160">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="29302-161">d.</span><span class="sxs-lookup"><span data-stu-id="29302-161">d.</span></span> <span data-ttu-id="29302-162">Vea cómo Microsoft 365 Defender ha resuelto automáticamente algunas **alertas** (la pestaña Investigaciones).</span><span class="sxs-lookup"><span data-stu-id="29302-162">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="29302-163">e.</span><span class="sxs-lookup"><span data-stu-id="29302-163">e.</span></span> <span data-ttu-id="29302-164">Según sea necesario, use la información del conjunto de datos para el incidente para obtener más información (la **pestaña Evidencia y** respuesta).</span><span class="sxs-lookup"><span data-stu-id="29302-164">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="29302-165">Después o durante el análisis, realice la contención para reducir cualquier impacto adicional del ataque y la eliminación de la amenaza de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29302-165">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="29302-166">En la medida de lo posible, recuperándose del ataque restaurando los recursos del espacio empresarial al estado en el que se encontraban antes del incidente.</span><span class="sxs-lookup"><span data-stu-id="29302-166">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="29302-167">[Resuelva](manage-incidents.md#resolve-incident) el incidente y tome tiempo para aprender después del incidente a:</span><span class="sxs-lookup"><span data-stu-id="29302-167">[Resolve](manage-incidents.md#resolve-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="29302-168">Comprender el tipo de ataque y su impacto.</span><span class="sxs-lookup"><span data-stu-id="29302-168">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="29302-169">Investigue el ataque en [Análisis de amenazas](threat-analytics.md) y la comunidad de seguridad para obtener una tendencia de ataque de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29302-169">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="29302-170">Recuerde el flujo de trabajo que usó para resolver el incidente y actualice los flujos de trabajo, procesos, directivas y libros de reproducción estándar según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="29302-170">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="29302-171">Determine si es necesario realizar cambios en la configuración de seguridad e implementarlos.</span><span class="sxs-lookup"><span data-stu-id="29302-171">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="29302-172">Si es nuevo en el [](incidents-overview.md) análisis de seguridad, vea la introducción para responder al primer incidente para obtener información adicional y para pasar por un incidente de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="29302-172">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="29302-173">Operaciones de seguridad de ejemplo para Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29302-173">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="29302-174">Este es un ejemplo de operaciones de seguridad para Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="29302-174">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Un ejemplo de operaciones de seguridad para Micosoft 365 Defender":::

<span data-ttu-id="29302-176">Las tareas diarias pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="29302-176">Daily tasks can include:</span></span>

- <span data-ttu-id="29302-177">[Administración](manage-incidents.md) de incidentes</span><span class="sxs-lookup"><span data-stu-id="29302-177">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="29302-178">Revisión de [acciones de investigación y respuesta automatizadas (AIR)](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="29302-178">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions</span></span>
- <span data-ttu-id="29302-179">Revisión de los análisis [de amenazas más recientes](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="29302-179">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="29302-180">[Responder a](investigate-incidents.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="29302-180">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="29302-181">Las tareas mensuales pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="29302-181">Monthly tasks can include:</span></span>

- <span data-ttu-id="29302-182">Revisión de [la configuración de AIR](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="29302-182">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="29302-183">Revisión [de la puntuación segura](microsoft-secure-score-improvement-actions.md) y la administración & [vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="29302-183">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="29302-184">Informes en la cadena de administración de seguridad de IT</span><span class="sxs-lookup"><span data-stu-id="29302-184">Reporting to your IT security management chain</span></span>

<span data-ttu-id="29302-185">Las tareas trimestrales pueden incluir un informe y un informe de los resultados de seguridad al director de seguridad de la información (CISO).</span><span class="sxs-lookup"><span data-stu-id="29302-185">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="29302-186">Las tareas anuales pueden incluir llevar a cabo un ejercicio importante de incidentes o infracciones para probar el personal, los sistemas y los procesos.</span><span class="sxs-lookup"><span data-stu-id="29302-186">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="29302-187">Las tareas diarias, mensuales, trimestrales y anuales se pueden usar para actualizar o refinar procesos, directivas y configuraciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29302-187">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="29302-188">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="29302-188">Next steps</span></span>

<span data-ttu-id="29302-189">La cola de incidentes de **la página Incidentes** enumera los incidentes más recientes.</span><span class="sxs-lookup"><span data-stu-id="29302-189">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="29302-190">Desde aquí, puede:</span><span class="sxs-lookup"><span data-stu-id="29302-190">From here, you can:</span></span>

- <span data-ttu-id="29302-191">Vea qué incidentes deben [priorizarse en](incident-queue.md) función de la gravedad y otros factores.</span><span class="sxs-lookup"><span data-stu-id="29302-191">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="29302-192">[Administrar incidentes, que](manage-incidents.md)incluye cambiar el nombre, la asignación, clasificar y agregar etiquetas y comentarios para el flujo de trabajo de administración de incidentes.</span><span class="sxs-lookup"><span data-stu-id="29302-192">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments for your incident management workflow.</span></span>
- <span data-ttu-id="29302-193">Realice un [análisis](investigate-incidents.md) de un incidente.</span><span class="sxs-lookup"><span data-stu-id="29302-193">Perform an [analysis](investigate-incidents.md) of an incident.</span></span>
