---
title: Analizar incidentes en Microsoft 365 Defender
description: Analizar incidentes relacionados con dispositivos, usuarios y buzones de correo.
keywords: incidente, incidentes, análisis, respuesta, máquinas, dispositivos, usuarios, identidades, correo, correo electrónico, buzón, investigación, gráfico, evidencia
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
ms.openlocfilehash: 72e1efb8a06fb7fa64b83ab6522fe4cdcfd1a73e
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259641"
---
# <a name="analyze-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e98f1-104">Analizar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e98f1-104">Analyze incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e98f1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e98f1-105">**Applies to:**</span></span>

- <span data-ttu-id="e98f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e98f1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e98f1-107">Microsoft 365 Defender agrega todas las alertas, activos, investigaciones y pruebas relacionadas de todos los dispositivos, usuarios y buzones de correo en un incidente para darle una visión completa de toda la amplitud de un ataque.</span><span class="sxs-lookup"><span data-stu-id="e98f1-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="e98f1-108">Dentro de un incidente, se analizan las alertas que afectan a la red, se entiende lo que significan y se recopilan las pruebas para poder diseñar un plan de corrección eficaz.</span><span class="sxs-lookup"><span data-stu-id="e98f1-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-analysis"></a><span data-ttu-id="e98f1-109">Análisis inicial</span><span class="sxs-lookup"><span data-stu-id="e98f1-109">Initial analysis</span></span>

<span data-ttu-id="e98f1-110">Antes de entrar en detalles, echa un vistazo a las propiedades y el resumen del incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="e98f1-111">Para empezar, seleccione el incidente en la columna de marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="e98f1-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="e98f1-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e98f1-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Ejemplo de selección de un incidente en la columna de marca de verificación":::

<span data-ttu-id="e98f1-114">Cuando lo haga, se abrirá un panel de resumen con información clave sobre el incidente, como la gravedad, a quién está asignado, y el ATT de MITRE&categorías [de CK &trade; ](https://attack.mitre.org/) para el incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="e98f1-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e98f1-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Ejemplo del panel de resumen de un incidente":::

<span data-ttu-id="e98f1-117">Desde aquí, puede seleccionar **Abrir página de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="e98f1-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="e98f1-118">Esto abre la página principal del incidente donde encontrará más información de resumen y pestañas para alertas, dispositivos, usuarios, investigaciones y pruebas.</span><span class="sxs-lookup"><span data-stu-id="e98f1-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="e98f1-119">También puede abrir la página principal de un incidente seleccionando el nombre del incidente en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="e98f1-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="e98f1-120">Resumen</span><span class="sxs-lookup"><span data-stu-id="e98f1-120">Summary</span></span>

<span data-ttu-id="e98f1-121">La **página Resumen le** ofrece una vista instantánea de los aspectos principales que debe tener en cuenta sobre el incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el centro Microsoft 365 seguridad":::

<span data-ttu-id="e98f1-123">Las categorías de ataque te dan una vista visual y numérica de lo avanzado que ha progresado el ataque en la cadena de eliminación.</span><span class="sxs-lookup"><span data-stu-id="e98f1-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="e98f1-124">Al igual que con otros productos de seguridad de Microsoft, Microsoft 365 Defender se alinea con el marco de&[CK &trade; de MITRE ATT.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="e98f1-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="e98f1-125">La sección de ámbito ofrece una lista de los activos que se han visto afectados y que forman parte de este incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="e98f1-126">Si hay información específica sobre este activo, como el nivel de riesgo, la prioridad de investigación, así como cualquier etiqueta en los activos, esto también se mostrará en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e98f1-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="e98f1-127">La escala de tiempo de alertas proporciona un vistazo al orden cronológico en el que se produjeron las alertas, así como los motivos por los que estas alertas están vinculadas a este incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="e98f1-128">Y por último: la sección de evidencia proporciona un resumen de cuántos artefactos diferentes se incluyeron en el incidente y su estado de corrección, por lo que puede identificar inmediatamente si necesita alguna acción.</span><span class="sxs-lookup"><span data-stu-id="e98f1-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="e98f1-129">Esta introducción puede ayudar en la evaluación inicial del incidente proporcionando información sobre las características principales del incidente que debe conocer.</span><span class="sxs-lookup"><span data-stu-id="e98f1-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="e98f1-130">Alertas</span><span class="sxs-lookup"><span data-stu-id="e98f1-130">Alerts</span></span>

<span data-ttu-id="e98f1-131">En la **pestaña** Alerta, puede ver la cola de alertas de alertas relacionadas con el incidente y otra información sobre ellas, como:</span><span class="sxs-lookup"><span data-stu-id="e98f1-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="e98f1-132">Gravedad.</span><span class="sxs-lookup"><span data-stu-id="e98f1-132">Severity.</span></span>
- <span data-ttu-id="e98f1-133">Las entidades que participaron en la alerta.</span><span class="sxs-lookup"><span data-stu-id="e98f1-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="e98f1-134">El origen de las alertas (Microsoft Defender para identity, Microsoft Defender para endpoint, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="e98f1-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="e98f1-135">La razón por la que se vincularon.</span><span class="sxs-lookup"><span data-stu-id="e98f1-135">The reason they were linked together.</span></span>

<span data-ttu-id="e98f1-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e98f1-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Ejemplo de una página de alertas para un incidente":::

<span data-ttu-id="e98f1-138">De forma predeterminada, las alertas se ordenan cronológicamente para que pueda ver cómo se produjo el incidente con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="e98f1-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="e98f1-139">La selección de cada alerta te lleva a la página principal de la alerta, donde puedes realizar un análisis detallado de esa alerta.</span><span class="sxs-lookup"><span data-stu-id="e98f1-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="e98f1-140">Obtenga información sobre cómo usar la cola de alertas y las páginas de alertas en [el análisis de alertas](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e98f1-140">Learn how to use the alert queue and alert pages in [analyze alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="e98f1-141">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="e98f1-141">Devices</span></span>

<span data-ttu-id="e98f1-142">La **pestaña Dispositivos** enumera todos los dispositivos relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="e98f1-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e98f1-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Ejemplo de una página Dispositivos para un incidente":::

<span data-ttu-id="e98f1-145">Puedes seleccionar la marca de verificación de un dispositivo para ver los detalles del dispositivo, los datos de directorio, las alertas activas y los usuarios que han iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="e98f1-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="e98f1-146">Selecciona el nombre del dispositivo para ver los detalles del dispositivo en el inventario de dispositivos de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="e98f1-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Ejemplo de una página de dispositivos para Microsoft Defender para puntos de conexión":::

<span data-ttu-id="e98f1-148">Desde la página del dispositivo, puedes recopilar información adicional sobre el dispositivo, como todas sus alertas, una escala de tiempo y recomendaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e98f1-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="e98f1-149">Por ejemplo,  desde la pestaña Escala de tiempo, puede desplazarse por la escala de tiempo de la máquina y ver todos los eventos y comportamientos observados en la máquina en orden cronológico, intercalados con las alertas generadas.</span><span class="sxs-lookup"><span data-stu-id="e98f1-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="e98f1-150">Puedes realizar exámenes a petición en una página de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e98f1-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="e98f1-151">En el centro Microsoft 365 seguridad, elija **Endpoints > Device inventory**.</span><span class="sxs-lookup"><span data-stu-id="e98f1-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="e98f1-152">Selecciona un dispositivo que tenga alertas y, a continuación, ejecuta un examen antivirus.</span><span class="sxs-lookup"><span data-stu-id="e98f1-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="e98f1-153">Las acciones, como los exámenes antivirus, se realiza un seguimiento y están visibles en la **página Inventario de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e98f1-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="e98f1-154">Para obtener más información, [consulte Run Antivirus de Microsoft Defender scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="e98f1-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="e98f1-155">Usuarios</span><span class="sxs-lookup"><span data-stu-id="e98f1-155">Users</span></span>

<span data-ttu-id="e98f1-156">La **pestaña** Usuarios enumera todos los usuarios que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="e98f1-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e98f1-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página Usuarios para un incidente":::

<span data-ttu-id="e98f1-159">Puede seleccionar la marca de verificación de un usuario para ver los detalles de la amenaza, la exposición y la información de contacto de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e98f1-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="e98f1-160">Seleccione el nombre de usuario para ver los detalles adicionales de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e98f1-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="e98f1-161">Buzones</span><span class="sxs-lookup"><span data-stu-id="e98f1-161">Mailboxes</span></span>

<span data-ttu-id="e98f1-162">La **pestaña Buzones** enumera todos los buzones que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="e98f1-163">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e98f1-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Ejemplo de una página Buzones de correo para un incidente":::

<span data-ttu-id="e98f1-165">Puede seleccionar la marca de verificación de un buzón para ver una lista de alertas activas.</span><span class="sxs-lookup"><span data-stu-id="e98f1-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="e98f1-166">Seleccione el nombre del buzón para ver detalles adicionales del buzón en la página Explorador de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e98f1-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="e98f1-167">Investigaciones</span><span class="sxs-lookup"><span data-stu-id="e98f1-167">Investigations</span></span>

<span data-ttu-id="e98f1-168">La **pestaña Investigaciones** enumera todas las investigaciones automatizadas desencadenadas por alertas en este incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-168">The **Investigations** tab lists all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="e98f1-169">Las investigaciones realizarán acciones de corrección o esperarán a que los analistas aprueben las acciones, según cómo haya configurado las investigaciones automatizadas para que se ejecuten en Microsoft Defender para Endpoint y Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e98f1-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Ejemplo de una página de investigaciones para un incidente":::

<span data-ttu-id="e98f1-171">Seleccione una investigación para ir a la página de detalles de la investigación para obtener toda la información sobre la investigación y el estado de corrección.</span><span class="sxs-lookup"><span data-stu-id="e98f1-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="e98f1-172">Si hay acciones pendientes para su aprobación como parte de la investigación, aparecerán en la pestaña Acciones pendientes. Tome medidas como parte de la corrección de incidentes.</span><span class="sxs-lookup"><span data-stu-id="e98f1-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="e98f1-173">Evidencia y respuesta</span><span class="sxs-lookup"><span data-stu-id="e98f1-173">Evidence and Response</span></span>

<span data-ttu-id="e98f1-174">La **pestaña Evidencia y respuesta** muestra todos los eventos admitidos y las entidades sospechosas en las alertas del incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-174">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="e98f1-175">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e98f1-175">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Ejemplo de una página de evidencia y respuesta para un incidente":::

<span data-ttu-id="e98f1-177">Microsoft 365 Defender investiga automáticamente todos los eventos compatibles con incidentes y las entidades sospechosas de las alertas, lo que le proporciona información sobre los correos electrónicos, archivos, procesos, servicios, direcciones IP importantes y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e98f1-177">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="e98f1-178">Esto le ayuda a detectar y bloquear rápidamente posibles amenazas en el incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-178">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="e98f1-179">Cada una de las entidades analizadas se marca con un veredicto (malintencionado, sospechoso, limpio) y un estado de corrección.</span><span class="sxs-lookup"><span data-stu-id="e98f1-179">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="e98f1-180">Esto le ayuda a comprender el estado de corrección de todo el incidente y los siguientes pasos que se pueden seguir.</span><span class="sxs-lookup"><span data-stu-id="e98f1-180">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="e98f1-181">Graph (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="e98f1-181">Graph (in Preview)</span></span>

<span data-ttu-id="e98f1-182">Con la nueva **Graph** (en vista previa), puede ver:</span><span class="sxs-lookup"><span data-stu-id="e98f1-182">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="e98f1-183">La conexión de alertas a los activos afectados de la organización.</span><span class="sxs-lookup"><span data-stu-id="e98f1-183">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="e98f1-184">Qué entidades están relacionadas con qué alertas y cómo forman parte de la historia del ataque.</span><span class="sxs-lookup"><span data-stu-id="e98f1-184">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="e98f1-185">Las alertas del incidente.</span><span class="sxs-lookup"><span data-stu-id="e98f1-185">The alerts for the incident.</span></span>

<span data-ttu-id="e98f1-186">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e98f1-186">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Ejemplo de una página Graph para un incidente":::

<span data-ttu-id="e98f1-188">El gráfico de incidentes le ayuda a comprender rápidamente el ámbito completo del ataque conectando las diferentes entidades sospechosas que forman parte del ataque con sus activos relacionados, como usuarios, dispositivos y buzones.</span><span class="sxs-lookup"><span data-stu-id="e98f1-188">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="e98f1-189">Ahora puedes comprender cómo el ataque se extendió a través de la red con el tiempo, dónde se inició y hasta dónde llegó el ataque.</span><span class="sxs-lookup"><span data-stu-id="e98f1-189">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e98f1-190">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e98f1-190">Related topics</span></span>

- [<span data-ttu-id="e98f1-191">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="e98f1-191">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e98f1-192">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="e98f1-192">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e98f1-193">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="e98f1-193">Manage incidents</span></span>](manage-incidents.md)

