---
title: Investigar incidentes en Microsoft 365 Defender
description: Investigar incidentes relacionados con dispositivos, usuarios y buzones.
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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105361"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e84f2-104">Investigar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e84f2-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e84f2-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e84f2-105">**Applies to:**</span></span>

- <span data-ttu-id="e84f2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e84f2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e84f2-107">Microsoft 365 Defender agrega todas las alertas, activos, investigaciones y pruebas relacionadas de todos los dispositivos, usuarios y buzones de correo en un incidente para darle una visión completa de toda la amplitud de un ataque.</span><span class="sxs-lookup"><span data-stu-id="e84f2-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="e84f2-108">Dentro de un incidente, se analizan las alertas que afectan a la red, se entiende lo que significan y se recopilan las pruebas para poder diseñar un plan de corrección eficaz.</span><span class="sxs-lookup"><span data-stu-id="e84f2-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="e84f2-109">Investigación inicial</span><span class="sxs-lookup"><span data-stu-id="e84f2-109">Initial investigation</span></span>

<span data-ttu-id="e84f2-110">Antes de entrar en detalles, echa un vistazo a las propiedades y el resumen del incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="e84f2-111">Para empezar, seleccione el incidente en la columna de marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="e84f2-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="e84f2-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e84f2-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Ejemplo de selección de un incidente en la columna de marca de verificación":::

<span data-ttu-id="e84f2-114">Cuando lo haga, se abrirá un panel de resumen con información clave sobre el incidente, como la gravedad, a quién está asignado, y el ATT de MITRE&categorías [de CK &trade; ](https://attack.mitre.org/) para el incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="e84f2-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e84f2-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Ejemplo del panel de resumen de un incidente":::

<span data-ttu-id="e84f2-117">Desde aquí, puede seleccionar **Abrir página de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="e84f2-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="e84f2-118">Esto abre la página principal del incidente donde encontrará más información de resumen y pestañas para alertas, dispositivos, usuarios, investigaciones y pruebas.</span><span class="sxs-lookup"><span data-stu-id="e84f2-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="e84f2-119">También puede abrir la página principal de un incidente seleccionando el nombre del incidente en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="e84f2-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="e84f2-120">Resumen</span><span class="sxs-lookup"><span data-stu-id="e84f2-120">Summary</span></span>

<span data-ttu-id="e84f2-121">La **página Resumen le** ofrece una vista instantánea de los aspectos principales que debe tener en cuenta sobre el incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el centro Microsoft 365 seguridad":::

<span data-ttu-id="e84f2-123">Las categorías de ataque te dan una vista visual y numérica de lo avanzado que ha progresado el ataque en la cadena de eliminación.</span><span class="sxs-lookup"><span data-stu-id="e84f2-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="e84f2-124">Al igual que con otros productos de seguridad de Microsoft, Microsoft 365 Defender se alinea con el marco de&[CK &trade; de MITRE ATT.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="e84f2-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="e84f2-125">La sección de ámbito ofrece una lista de los activos que se han visto afectados y que forman parte de este incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="e84f2-126">Si hay información específica sobre este activo, como el nivel de riesgo, la prioridad de investigación, así como cualquier etiqueta en los activos, esto también se mostrará en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e84f2-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="e84f2-127">La escala de tiempo de alertas proporciona un vistazo al orden cronológico en el que se produjeron las alertas, así como los motivos por los que estas alertas están vinculadas a este incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="e84f2-128">Y por último: la sección de evidencia proporciona un resumen de cuántos artefactos diferentes se incluyeron en el incidente y su estado de corrección, por lo que puede identificar inmediatamente si necesita alguna acción.</span><span class="sxs-lookup"><span data-stu-id="e84f2-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="e84f2-129">Esta introducción puede ayudar en la evaluación inicial del incidente proporcionando información sobre las características principales del incidente que debe conocer.</span><span class="sxs-lookup"><span data-stu-id="e84f2-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="e84f2-130">Alertas</span><span class="sxs-lookup"><span data-stu-id="e84f2-130">Alerts</span></span>

<span data-ttu-id="e84f2-131">En la **pestaña** Alerta, puede ver la cola de alertas de alertas relacionadas con el incidente y otra información sobre ellas, como:</span><span class="sxs-lookup"><span data-stu-id="e84f2-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="e84f2-132">Gravedad.</span><span class="sxs-lookup"><span data-stu-id="e84f2-132">Severity.</span></span>
- <span data-ttu-id="e84f2-133">Las entidades que participaron en la alerta.</span><span class="sxs-lookup"><span data-stu-id="e84f2-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="e84f2-134">El origen de las alertas (Microsoft Defender para identity, Microsoft Defender para endpoint, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="e84f2-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="e84f2-135">La razón por la que se vincularon.</span><span class="sxs-lookup"><span data-stu-id="e84f2-135">The reason they were linked together.</span></span>

<span data-ttu-id="e84f2-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e84f2-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Ejemplo de una página de alertas para un incidente":::

<span data-ttu-id="e84f2-138">De forma predeterminada, las alertas se ordenan cronológicamente para que pueda ver cómo se produjo el incidente con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="e84f2-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="e84f2-139">Al seleccionar una alerta dentro de un incidente, Microsoft 365 Defender muestra la información de alerta específica del contexto del incidente general.</span><span class="sxs-lookup"><span data-stu-id="e84f2-139">When you select an alert within an incident, Microsoft 365 Defender displays the alert information specific to the context of the overall incident.</span></span> 

<span data-ttu-id="e84f2-140">Puede ver los eventos de la alerta, qué otras alertas desencadenadas provocaron la alerta actual y todas las entidades y actividades afectadas implicadas en el ataque, incluidos los archivos, los usuarios y los buzones.</span><span class="sxs-lookup"><span data-stu-id="e84f2-140">You can see the events of the alert, which other triggered alerts caused the current alert, and all the affected entities and activities involved in the attack, including files, users, and mailboxes.</span></span>

<span data-ttu-id="e84f2-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e84f2-141">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Ejemplo de una página de detalles de alerta dentro de un incidente":::

<span data-ttu-id="e84f2-143">Esta página de alerta de incidentes se compone de estas secciones:</span><span class="sxs-lookup"><span data-stu-id="e84f2-143">This incident alert page is composed of these sections:</span></span>

- <span data-ttu-id="e84f2-144">Artículo de alerta, que incluye un resumen de lo que ocurrió</span><span class="sxs-lookup"><span data-stu-id="e84f2-144">Alert story, which includes a summary of what happened</span></span>
- <span data-ttu-id="e84f2-145">Alertas y eventos relacionados</span><span class="sxs-lookup"><span data-stu-id="e84f2-145">Related events and alerts</span></span>
- <span data-ttu-id="e84f2-146">Detalles de resumen</span><span class="sxs-lookup"><span data-stu-id="e84f2-146">Summary details</span></span>

<span data-ttu-id="e84f2-147">Obtenga información sobre cómo usar la cola de alertas y las páginas de alertas en [investigar alertas](investigate-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="e84f2-147">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="e84f2-148">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="e84f2-148">Devices</span></span>

<span data-ttu-id="e84f2-149">La **pestaña Dispositivos** enumera todos los dispositivos relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-149">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="e84f2-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e84f2-150">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Ejemplo de una página Dispositivos para un incidente":::

<span data-ttu-id="e84f2-152">Puedes seleccionar la marca de verificación de un dispositivo para ver los detalles del dispositivo, los datos de directorio, las alertas activas y los usuarios que han iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="e84f2-152">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="e84f2-153">Selecciona el nombre del dispositivo para ver los detalles del dispositivo en el inventario de dispositivos de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="e84f2-153">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Ejemplo de una página de dispositivos para Microsoft Defender para puntos de conexión":::

<span data-ttu-id="e84f2-155">Desde la página del dispositivo, puedes recopilar información adicional sobre el dispositivo, como todas sus alertas, una escala de tiempo y recomendaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e84f2-155">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="e84f2-156">Por ejemplo,  desde la pestaña Escala de tiempo, puede desplazarse por la escala de tiempo de la máquina y ver todos los eventos y comportamientos observados en la máquina en orden cronológico, intercalados con las alertas generadas.</span><span class="sxs-lookup"><span data-stu-id="e84f2-156">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="e84f2-157">Puedes realizar exámenes a petición en una página de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e84f2-157">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="e84f2-158">En el centro Microsoft 365 seguridad, elija **Endpoints > Device inventory**.</span><span class="sxs-lookup"><span data-stu-id="e84f2-158">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="e84f2-159">Selecciona un dispositivo que tenga alertas y, a continuación, ejecuta un examen antivirus.</span><span class="sxs-lookup"><span data-stu-id="e84f2-159">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="e84f2-160">Las acciones, como los exámenes antivirus, se realiza un seguimiento y están visibles en la **página Inventario de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e84f2-160">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="e84f2-161">Para obtener más información, [consulte Run Antivirus de Microsoft Defender scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="e84f2-161">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="e84f2-162">Usuarios</span><span class="sxs-lookup"><span data-stu-id="e84f2-162">Users</span></span>

<span data-ttu-id="e84f2-163">La **pestaña** Usuarios enumera todos los usuarios que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-163">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="e84f2-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e84f2-164">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página Usuarios para un incidente":::

<span data-ttu-id="e84f2-166">Puede seleccionar la marca de verificación de un usuario para ver los detalles de la amenaza, la exposición y la información de contacto de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e84f2-166">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="e84f2-167">Seleccione el nombre de usuario para ver los detalles adicionales de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e84f2-167">Select the user name to see additional user account details.</span></span>

<span data-ttu-id="e84f2-168">Obtenga información sobre cómo ver información de usuario adicional y administrar los usuarios de un incidente en [investigar usuarios](investigate-users.md).</span><span class="sxs-lookup"><span data-stu-id="e84f2-168">Learn how to view additional user information and manage the users of an incident in [investigate users](investigate-users.md).</span></span>


## <a name="mailboxes"></a><span data-ttu-id="e84f2-169">Buzones</span><span class="sxs-lookup"><span data-stu-id="e84f2-169">Mailboxes</span></span>

<span data-ttu-id="e84f2-170">La **pestaña Buzones** enumera todos los buzones que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-170">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="e84f2-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e84f2-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Ejemplo de una página Buzones de correo para un incidente":::

<span data-ttu-id="e84f2-173">Puede seleccionar la marca de verificación de un buzón para ver una lista de alertas activas.</span><span class="sxs-lookup"><span data-stu-id="e84f2-173">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="e84f2-174">Seleccione el nombre del buzón para ver detalles adicionales del buzón en la página Explorador de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e84f2-174">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="e84f2-175">Investigaciones</span><span class="sxs-lookup"><span data-stu-id="e84f2-175">Investigations</span></span>

<span data-ttu-id="e84f2-176">La **pestaña Investigaciones** enumera todas las [investigaciones automatizadas desencadenadas](m365d-autoir.md) por alertas en este incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-176">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="e84f2-177">Las investigaciones realizarán acciones de corrección o esperarán a que los analistas aprueben las acciones, según cómo haya configurado las investigaciones automatizadas para que se ejecuten en Microsoft Defender para Endpoint y Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e84f2-177">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Ejemplo de una página de investigaciones para un incidente":::

<span data-ttu-id="e84f2-179">Seleccione una investigación para navegar a su página de detalles para obtener información completa sobre el estado de investigación y corrección.</span><span class="sxs-lookup"><span data-stu-id="e84f2-179">Select an investigation to navigate to its details page for full information on the investigation and remediation status.</span></span> <span data-ttu-id="e84f2-180">Si hay acciones pendientes para su aprobación como parte de la investigación, aparecerán en la **pestaña Historial de acciones pendientes.** Tome medidas como parte de la corrección de incidentes.</span><span class="sxs-lookup"><span data-stu-id="e84f2-180">If there are any actions pending for approval as part of the investigation, they will appear in the **Pending actions history** tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="e84f2-181">También hay una pestaña **Gráfico de investigación** que muestra:</span><span class="sxs-lookup"><span data-stu-id="e84f2-181">There is also an **Investigation graph** tab that shows:</span></span>

- <span data-ttu-id="e84f2-182">La conexión de alertas a los activos afectados de la organización.</span><span class="sxs-lookup"><span data-stu-id="e84f2-182">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="e84f2-183">Qué entidades están relacionadas con qué alertas y cómo forman parte de la historia del ataque.</span><span class="sxs-lookup"><span data-stu-id="e84f2-183">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="e84f2-184">Las alertas del incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-184">The alerts for the incident.</span></span>

<span data-ttu-id="e84f2-185">El gráfico de investigación le ayuda a comprender rápidamente el ámbito completo del ataque conectando las diferentes entidades sospechosas que forman parte del ataque con sus activos relacionados, como usuarios, dispositivos y buzones.</span><span class="sxs-lookup"><span data-stu-id="e84f2-185">The investigation graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="e84f2-186">Para obtener más información, vea [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="e84f2-186">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="e84f2-187">Evidencia y respuesta</span><span class="sxs-lookup"><span data-stu-id="e84f2-187">Evidence and Response</span></span>

<span data-ttu-id="e84f2-188">La **pestaña Evidencia y respuesta** muestra todos los eventos admitidos y las entidades sospechosas en las alertas del incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-188">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="e84f2-189">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e84f2-189">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Ejemplo de una página de evidencia y respuesta para un incidente":::

<span data-ttu-id="e84f2-191">Microsoft 365 Defender investiga automáticamente todos los eventos compatibles con incidentes y las entidades sospechosas de las alertas, lo que le proporciona información sobre los correos electrónicos, archivos, procesos, servicios, direcciones IP importantes, etc.</span><span class="sxs-lookup"><span data-stu-id="e84f2-191">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="e84f2-192">Esto le ayuda a detectar y bloquear rápidamente posibles amenazas en el incidente.</span><span class="sxs-lookup"><span data-stu-id="e84f2-192">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="e84f2-193">Cada una de las entidades analizadas se marca con un veredicto (malintencionado, sospechoso, limpio) y un estado de corrección.</span><span class="sxs-lookup"><span data-stu-id="e84f2-193">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="e84f2-194">Esto le ayuda a comprender el estado de corrección de todo el incidente y los siguientes pasos que se pueden seguir.</span><span class="sxs-lookup"><span data-stu-id="e84f2-194">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e84f2-195">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e84f2-195">Next steps</span></span>

<span data-ttu-id="e84f2-196">Según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="e84f2-196">As needed:</span></span>

- [<span data-ttu-id="e84f2-197">Investigar las alertas de un incidente</span><span class="sxs-lookup"><span data-stu-id="e84f2-197">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="e84f2-198">Investigar los usuarios de un incidente</span><span class="sxs-lookup"><span data-stu-id="e84f2-198">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="e84f2-199">Ver también</span><span class="sxs-lookup"><span data-stu-id="e84f2-199">See also</span></span>

- [<span data-ttu-id="e84f2-200">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="e84f2-200">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e84f2-201">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="e84f2-201">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e84f2-202">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="e84f2-202">Manage incidents</span></span>](manage-incidents.md)

