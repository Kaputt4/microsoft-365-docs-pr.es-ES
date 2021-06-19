---
title: Incidentes en Microsoft 365 Defender
description: Investigar incidentes vistos en dispositivos, usuarios y buzones en el portal de Microsoft 365 Defender web.
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
ms.openlocfilehash: 3dac22afb074a58ea2afdf842a9a62c6cee77dcc
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022791"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="87421-104">Incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87421-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="87421-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="87421-105">**Applies to:**</span></span>
- <span data-ttu-id="87421-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87421-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="87421-107">¿Quiere experimentar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="87421-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="87421-108">Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="87421-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="87421-109">Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que son la historia de un ataque.</span><span class="sxs-lookup"><span data-stu-id="87421-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="87421-110">Microsoft 365 servicios y aplicaciones crean alertas cuando detectan un evento o actividad sospechosos o malintencionados.</span><span class="sxs-lookup"><span data-stu-id="87421-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="87421-111">Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso.</span><span class="sxs-lookup"><span data-stu-id="87421-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="87421-112">Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones.</span><span class="sxs-lookup"><span data-stu-id="87421-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="87421-113">El resultado son varias alertas para varias entidades del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="87421-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="87421-114">Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada a un incidente.</span><span class="sxs-lookup"><span data-stu-id="87421-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Cómo Microsoft 365 Defender los eventos de entidades en un incidente":::

<span data-ttu-id="87421-116">Vea esta breve introducción a los incidentes en Microsoft 365 Defender (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="87421-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="87421-117">La agrupación de alertas relacionadas en un incidente le ofrece una vista completa de un ataque.</span><span class="sxs-lookup"><span data-stu-id="87421-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="87421-118">Por ejemplo, puede ver:</span><span class="sxs-lookup"><span data-stu-id="87421-118">For example, you can see:</span></span>

- <span data-ttu-id="87421-119">Donde se inició el ataque.</span><span class="sxs-lookup"><span data-stu-id="87421-119">Where the attack started.</span></span>
- <span data-ttu-id="87421-120">Qué tácticas se usaron.</span><span class="sxs-lookup"><span data-stu-id="87421-120">What tactics were used.</span></span>
- <span data-ttu-id="87421-121">Cuánto ha llegado el ataque a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="87421-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="87421-122">El ámbito del ataque, como el número de dispositivos, usuarios y buzones de correo afectados.</span><span class="sxs-lookup"><span data-stu-id="87421-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="87421-123">Todos los datos asociados con el ataque.</span><span class="sxs-lookup"><span data-stu-id="87421-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="87421-124">Si [está habilitado,](m365d-enable.md)Microsoft 365 Defender investigar y resolver [alertas](m365d-autoir.md) automáticamente a través de la automatización y la inteligencia artificial.</span><span class="sxs-lookup"><span data-stu-id="87421-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="87421-125">También puedes realizar pasos de corrección adicionales para resolver el ataque.</span><span class="sxs-lookup"><span data-stu-id="87421-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="87421-126">Incidentes y alertas en el portal Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="87421-126">Incidents and alerts in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="87421-127">Puede administrar incidentes de incidentes **& alertas** > incidentes en el inicio rápido del portal de Microsoft 365 Defender ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="87421-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="87421-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="87421-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La página Incidentes del portal de Microsoft 365 Defender web":::

<span data-ttu-id="87421-130">Al seleccionar un nombre de incidente, se muestra un resumen del incidente y se proporciona acceso a las pestañas con información adicional.</span><span class="sxs-lookup"><span data-stu-id="87421-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el portal Microsoft 365 Defender web":::

<span data-ttu-id="87421-132">Las pestañas adicionales para un incidente son:</span><span class="sxs-lookup"><span data-stu-id="87421-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="87421-133">Alertas</span><span class="sxs-lookup"><span data-stu-id="87421-133">Alerts</span></span> 

  <span data-ttu-id="87421-134">Todas las alertas relacionadas con el incidente y su información.</span><span class="sxs-lookup"><span data-stu-id="87421-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="87421-135">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="87421-135">Devices</span></span>

  <span data-ttu-id="87421-136">Todos los dispositivos que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="87421-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="87421-137">Usuarios</span><span class="sxs-lookup"><span data-stu-id="87421-137">Users</span></span>

  <span data-ttu-id="87421-138">Todos los usuarios identificados para formar parte del incidente o relacionados con ellos.</span><span class="sxs-lookup"><span data-stu-id="87421-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="87421-139">Buzones</span><span class="sxs-lookup"><span data-stu-id="87421-139">Mailboxes</span></span>

  <span data-ttu-id="87421-140">Todos los buzones que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="87421-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="87421-141">Investigaciones</span><span class="sxs-lookup"><span data-stu-id="87421-141">Investigations</span></span>

  <span data-ttu-id="87421-142">Todas las [investigaciones automatizadas desencadenadas](m365d-autoir.md) por alertas en el incidente.</span><span class="sxs-lookup"><span data-stu-id="87421-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="87421-143">Evidencia y respuesta</span><span class="sxs-lookup"><span data-stu-id="87421-143">Evidence and Response</span></span>

  <span data-ttu-id="87421-144">Todos los eventos admitidos y las entidades sospechosas en las alertas del incidente.</span><span class="sxs-lookup"><span data-stu-id="87421-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="87421-145">Graph (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="87421-145">Graph (in preview)</span></span>

  <span data-ttu-id="87421-146">Una figura que muestra la conexión de alertas a los activos afectados de la organización.</span><span class="sxs-lookup"><span data-stu-id="87421-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="87421-147">Esta es la relación entre un incidente y sus datos y las pestañas de un incidente en Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="87421-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="La relación de un incidente y sus datos con las pestañas de un incidente en el portal de Microsoft 365 Defender web":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="87421-149">Flujo de trabajo de respuesta a incidentes de ejemplo para Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87421-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="87421-150">Este es un flujo de trabajo de ejemplo para responder a incidentes en Microsoft 365 con el portal Microsoft 365 Defender web.</span><span class="sxs-lookup"><span data-stu-id="87421-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Ejemplo de flujo de trabajo de respuesta a incidentes para Microsoft 365":::

<span data-ttu-id="87421-152">De forma continua, identifique los incidentes de mayor prioridad para el análisis y la resolución en la cola de incidentes y prepárese para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="87421-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="87421-153">Esta es una combinación de:</span><span class="sxs-lookup"><span data-stu-id="87421-153">This is a combination of:</span></span>

- <span data-ttu-id="87421-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span><span class="sxs-lookup"><span data-stu-id="87421-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="87421-155">[Administrar](manage-incidents.md) incidentes modificando su título, asignándolos a un analista y agregando etiquetas y comentarios.</span><span class="sxs-lookup"><span data-stu-id="87421-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="87421-156">Para cada incidente, inicie una investigación y análisis de [ataques y alertas:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="87421-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   1. <span data-ttu-id="87421-157">Vea el resumen del incidente para comprender su ámbito y gravedad y qué entidades se ven afectadas (la **pestaña Resumen).**</span><span class="sxs-lookup"><span data-stu-id="87421-157">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   1. <span data-ttu-id="87421-158">Comience a analizar las alertas para comprender su origen, ámbito y gravedad (la **pestaña** Alertas).</span><span class="sxs-lookup"><span data-stu-id="87421-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   1. <span data-ttu-id="87421-159">Según sea necesario, recopila información sobre dispositivos, usuarios y buzones afectados (las pestañas **Dispositivos,** **Usuarios** y **Buzones).**</span><span class="sxs-lookup"><span data-stu-id="87421-159">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   1. <span data-ttu-id="87421-160">Vea cómo Microsoft 365 Defender [ha resuelto automáticamente algunas alertas](m365d-autoir.md) (la **pestaña Investigaciones).**</span><span class="sxs-lookup"><span data-stu-id="87421-160">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   1. <span data-ttu-id="87421-161">Según sea necesario, use la información del conjunto de datos para el incidente para obtener más información (la **pestaña Evidencia y** respuesta).</span><span class="sxs-lookup"><span data-stu-id="87421-161">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="87421-162">Después o durante el análisis, realice la contención para reducir cualquier impacto adicional del ataque y la eliminación de la amenaza de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87421-162">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="87421-163">En la medida de lo posible, recuperándose del ataque restaurando los recursos del espacio empresarial al estado en el que se encontraban antes del incidente.</span><span class="sxs-lookup"><span data-stu-id="87421-163">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="87421-164">[Resuelva](manage-incidents.md#resolve-an-incident) el incidente y tome tiempo para aprender después del incidente a:</span><span class="sxs-lookup"><span data-stu-id="87421-164">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="87421-165">Comprender el tipo de ataque y su impacto.</span><span class="sxs-lookup"><span data-stu-id="87421-165">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="87421-166">Investigue el ataque en [Análisis de amenazas](threat-analytics.md) y la comunidad de seguridad para obtener una tendencia de ataque de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87421-166">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="87421-167">Recuerde el flujo de trabajo que usó para resolver el incidente y actualice los flujos de trabajo, procesos, directivas y libros de reproducción estándar según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="87421-167">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="87421-168">Determine si es necesario realizar cambios en la configuración de seguridad e implementarlos.</span><span class="sxs-lookup"><span data-stu-id="87421-168">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="87421-169">Si es nuevo en el [](incidents-overview.md) análisis de seguridad, vea la introducción para responder al primer incidente para obtener información adicional y para pasar por un incidente de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="87421-169">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="87421-170">Operaciones de seguridad de ejemplo para Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87421-170">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="87421-171">Este es un ejemplo de operaciones de seguridad para Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="87421-171">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Un ejemplo de operaciones de seguridad para Microsoft 365 Defender":::

<span data-ttu-id="87421-173">Las tareas diarias pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="87421-173">Daily tasks can include:</span></span>

- <span data-ttu-id="87421-174">[Administración](manage-incidents.md) de incidentes</span><span class="sxs-lookup"><span data-stu-id="87421-174">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="87421-175">Revisión [de acciones de investigación y respuesta automatizadas (AIR)](m365d-action-center.md) en el Centro de acciones</span><span class="sxs-lookup"><span data-stu-id="87421-175">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="87421-176">Revisión de los análisis [de amenazas más recientes](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="87421-176">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="87421-177">[Responder a](investigate-incidents.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="87421-177">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="87421-178">Las tareas mensuales pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="87421-178">Monthly tasks can include:</span></span>

- <span data-ttu-id="87421-179">Revisión de [la configuración de AIR](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="87421-179">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="87421-180">Revisión [de la puntuación segura](microsoft-secure-score-improvement-actions.md) y la administración & [vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="87421-180">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="87421-181">Informes en la cadena de administración de seguridad de IT</span><span class="sxs-lookup"><span data-stu-id="87421-181">Reporting to your IT security management chain</span></span>

<span data-ttu-id="87421-182">Las tareas trimestrales pueden incluir un informe y un informe de los resultados de seguridad al director de seguridad de la información (CISO).</span><span class="sxs-lookup"><span data-stu-id="87421-182">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="87421-183">Las tareas anuales pueden incluir llevar a cabo un ejercicio importante de incidentes o infracciones para probar el personal, los sistemas y los procesos.</span><span class="sxs-lookup"><span data-stu-id="87421-183">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="87421-184">Las tareas diarias, mensuales, trimestrales y anuales se pueden usar para actualizar o refinar procesos, directivas y configuraciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87421-184">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="87421-185">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="87421-185">Next steps</span></span>

<span data-ttu-id="87421-186">**Si es nuevo en el análisis** de seguridad y la respuesta a incidentes:</span><span class="sxs-lookup"><span data-stu-id="87421-186">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="87421-187">Consulte [el](first-incident-overview.md) tutorial Responder a su primer incidente para obtener una visita guiada de un proceso típico de análisis, corrección y revisión posterior al incidente en el portal de Microsoft 365 Defender con un ejemplo de un ataque.</span><span class="sxs-lookup"><span data-stu-id="87421-187">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 Defender portal with an example of an attack.</span></span>

<span data-ttu-id="87421-188">**Si tiene experiencia con el análisis** de seguridad y la respuesta a incidentes:</span><span class="sxs-lookup"><span data-stu-id="87421-188">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="87421-189">Introducción a la cola de incidentes desde **la página Incidentes** del portal Microsoft 365 Defender incidentes.</span><span class="sxs-lookup"><span data-stu-id="87421-189">Get started with the incident queue from the **Incidents** page of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="87421-190">Desde ahí, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87421-190">From here, you can:</span></span>

  - <span data-ttu-id="87421-191">Vea qué incidentes deben [priorizarse en](incident-queue.md) función de la gravedad y otros factores.</span><span class="sxs-lookup"><span data-stu-id="87421-191">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="87421-192">[Administrar incidentes, que](manage-incidents.md)incluye cambiar el nombre, la asignación, clasificar y agregar etiquetas y comentarios en función del flujo de trabajo de administración de incidentes.</span><span class="sxs-lookup"><span data-stu-id="87421-192">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="87421-193">Realizar [investigaciones](investigate-incidents.md) de incidentes.</span><span class="sxs-lookup"><span data-stu-id="87421-193">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="87421-194">Consulta estos [libros de reproducción de respuesta a](/security/compass/incident-response-playbooks) incidentes para obtener instrucciones detalladas sobre los ataques de suplantación de identidad (phishing), el uso de contraseñas y la concesión de consentimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="87421-194">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

