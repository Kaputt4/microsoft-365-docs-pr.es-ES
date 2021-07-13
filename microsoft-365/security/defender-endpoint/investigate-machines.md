---
title: Investigar dispositivos en la lista Defender para dispositivos de punto de conexión
description: Investigue los dispositivos afectados revisando alertas, información de conexión de red, agregando etiquetas y grupos de dispositivos y comprobando el estado del servicio.
keywords: dispositivos, etiquetas, grupos, punto de conexión, cola de alertas, alertas, nombre de dispositivo, dominio, última vista, IP interna, alertas activas, categoría de amenazas, filtro, ordenación, revisión de alertas, red, conexión, tipo, robo de contraseñas, ransomware, vulnerabilidad, amenaza, gravedad baja, estado del servicio
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c89de5fbf5d5b4d5d5e53074109bc8884a271eea
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394898"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="5031c-104">Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5031c-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5031c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5031c-105">**Applies to:**</span></span>
- [<span data-ttu-id="5031c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5031c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5031c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5031c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5031c-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5031c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5031c-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5031c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="5031c-110">Investigue los detalles de una alerta que se genera en un dispositivo específico para identificar otros comportamientos o eventos que puedan estar relacionados con la alerta o el ámbito potencial de la infracción.</span><span class="sxs-lookup"><span data-stu-id="5031c-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="5031c-111">Como parte del proceso de investigación o respuesta, puedes recopilar un paquete de investigación desde un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="5031c-112">Este es el modo: [Recopilar paquete de investigación de dispositivos](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="5031c-112">Here's how: [Collect investigation package from devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="5031c-113">Puedes hacer clic en los dispositivos afectados siempre que los veas en el portal para abrir un informe detallado sobre ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="5031c-114">Los dispositivos afectados se identifican en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="5031c-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="5031c-115">Lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="5031c-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="5031c-116">Cola de alertas</span><span class="sxs-lookup"><span data-stu-id="5031c-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="5031c-117">Panel de operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="5031c-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="5031c-118">Cualquier alerta individual</span><span class="sxs-lookup"><span data-stu-id="5031c-118">Any individual alert</span></span>
- <span data-ttu-id="5031c-119">Cualquier vista de detalles de archivo individual</span><span class="sxs-lookup"><span data-stu-id="5031c-119">Any individual file details view</span></span>
- <span data-ttu-id="5031c-120">Cualquier dirección IP o vista de detalles de dominio</span><span class="sxs-lookup"><span data-stu-id="5031c-120">Any IP address or domain details view</span></span>

<span data-ttu-id="5031c-121">Cuando investigues un dispositivo específico, verás lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5031c-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="5031c-122">Detalles del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5031c-122">Device details</span></span>
- <span data-ttu-id="5031c-123">Acciones de respuesta</span><span class="sxs-lookup"><span data-stu-id="5031c-123">Response actions</span></span>
- <span data-ttu-id="5031c-124">Pestañas (información general, alertas, escala de tiempo, recomendaciones de seguridad, inventario de software, vulnerabilidades detectadas, KB ausentes)</span><span class="sxs-lookup"><span data-stu-id="5031c-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="5031c-125">Tarjetas (alertas activas, usuarios que han iniciado sesión, evaluación de seguridad)</span><span class="sxs-lookup"><span data-stu-id="5031c-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Imagen de la vista de dispositivo](images/specific-device.png)

> [!NOTE]
> <span data-ttu-id="5031c-127">Debido a las restricciones del producto, el perfil del dispositivo no tiene en cuenta todas las pruebas cibernéticas al determinar el período de tiempo "Last Seen" (como también se ve en la página del dispositivo).</span><span class="sxs-lookup"><span data-stu-id="5031c-127">Due to product constrains, the device profile does not consider all cyber evidence when determining the 'Last Seen' timeframe (as seen on the device page as well).</span></span>
> <span data-ttu-id="5031c-128">Por ejemplo, el valor "Última vista" en la página Dispositivo puede mostrar un período de tiempo más antiguo, aunque hay alertas o datos más recientes disponibles en la escala de tiempo del equipo.</span><span class="sxs-lookup"><span data-stu-id="5031c-128">For example, the 'Last seen' value in the Device page may show an older time frame even though more recent alerts or data is available in the machine's timeline.</span></span>

## <a name="device-details"></a><span data-ttu-id="5031c-129">Detalles del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5031c-129">Device details</span></span>

<span data-ttu-id="5031c-130">La sección detalles del dispositivo proporciona información como el dominio, el sistema operativo y el estado de mantenimiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-130">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="5031c-131">Si hay un paquete de investigación disponible en el dispositivo, verás un vínculo que te permite descargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="5031c-131">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="5031c-132">Acciones de respuesta</span><span class="sxs-lookup"><span data-stu-id="5031c-132">Response actions</span></span>

<span data-ttu-id="5031c-133">Las acciones de respuesta se ejecutan en la parte superior de una página de dispositivo específica e incluyen:</span><span class="sxs-lookup"><span data-stu-id="5031c-133">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="5031c-134">Administrar etiquetas</span><span class="sxs-lookup"><span data-stu-id="5031c-134">Manage tags</span></span>
- <span data-ttu-id="5031c-135">Aislar dispositivo</span><span class="sxs-lookup"><span data-stu-id="5031c-135">Isolate device</span></span>
- <span data-ttu-id="5031c-136">Restringir ejecución de aplicación</span><span class="sxs-lookup"><span data-stu-id="5031c-136">Restrict app execution</span></span>
- <span data-ttu-id="5031c-137">Ejecutar examen antivirus</span><span class="sxs-lookup"><span data-stu-id="5031c-137">Run antivirus scan</span></span>
- <span data-ttu-id="5031c-138">Recopilar paquete de investigación</span><span class="sxs-lookup"><span data-stu-id="5031c-138">Collect investigation package</span></span>
- <span data-ttu-id="5031c-139">Iniciar sesión de respuesta activa</span><span class="sxs-lookup"><span data-stu-id="5031c-139">Initiate Live Response Session</span></span>
- <span data-ttu-id="5031c-140">Iniciar investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="5031c-140">Initiate automated investigation</span></span>
- <span data-ttu-id="5031c-141">Consultar a un experto en amenazas</span><span class="sxs-lookup"><span data-stu-id="5031c-141">Consult a threat expert</span></span>
- <span data-ttu-id="5031c-142">Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="5031c-142">Action center</span></span>

<span data-ttu-id="5031c-143">Puedes realizar acciones de respuesta en el Centro de acciones, en una página de dispositivo específica o en una página de archivo específica.</span><span class="sxs-lookup"><span data-stu-id="5031c-143">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="5031c-144">Para obtener más información sobre cómo realizar acciones en un dispositivo, consulta [Realizar acción de respuesta en un dispositivo](respond-machine-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="5031c-144">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="5031c-145">Para obtener más información, vea [Investigar entidades de usuario](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="5031c-145">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="5031c-146">Pestañas</span><span class="sxs-lookup"><span data-stu-id="5031c-146">Tabs</span></span>

<span data-ttu-id="5031c-147">Las pestañas proporcionan información de seguridad y prevención de amenazas relevante relacionada con el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-147">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="5031c-148">En cada pestaña, puede personalizar las columnas  que se muestran seleccionando Personalizar columnas de la barra encima de los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="5031c-148">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="5031c-149">Información general</span><span class="sxs-lookup"><span data-stu-id="5031c-149">Overview</span></span>
<span data-ttu-id="5031c-150">La **pestaña Información** general muestra las [tarjetas para](#cards) las alertas activas, los usuarios que han iniciado sesión y la evaluación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5031c-150">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Imagen de la pestaña información general en la página del dispositivo](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="5031c-152">Alertas</span><span class="sxs-lookup"><span data-stu-id="5031c-152">Alerts</span></span>

<span data-ttu-id="5031c-153">La **pestaña** Alertas proporciona una lista de alertas asociadas con el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-153">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="5031c-154">Esta lista es una [](alerts-queue.md)versión filtrada de la cola de alertas y muestra una breve descripción de la alerta, gravedad (alta, media, baja, informativo), estado de la cola (nuevo, en curso, resuelto), clasificación (no establecida, alerta falsa, alerta verdadera), estado de investigación, categoría de alerta, quién está abordando la alerta y última actividad.</span><span class="sxs-lookup"><span data-stu-id="5031c-154">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="5031c-155">También puede filtrar las alertas.</span><span class="sxs-lookup"><span data-stu-id="5031c-155">You can also filter the alerts.</span></span>

![Imagen de alertas relacionadas con el dispositivo](images/alerts-device.png)

<span data-ttu-id="5031c-157">Cuando se selecciona el icono de círculo situado a la izquierda de una alerta, aparece un desplegable.</span><span class="sxs-lookup"><span data-stu-id="5031c-157">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="5031c-158">Desde este panel puede administrar la alerta y ver más detalles, como el número de incidente y los dispositivos relacionados.</span><span class="sxs-lookup"><span data-stu-id="5031c-158">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="5031c-159">Se pueden seleccionar varias alertas a la vez.</span><span class="sxs-lookup"><span data-stu-id="5031c-159">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="5031c-160">Para ver una vista de página completa de una alerta, incluido el gráfico de incidentes y el árbol de procesos, seleccione el título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="5031c-160">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="5031c-161">Escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="5031c-161">Timeline</span></span>

<span data-ttu-id="5031c-162">La **pestaña Escala** de tiempo proporciona una vista cronológica de los eventos y alertas asociadas que se han observado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-162">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="5031c-163">Esto puede ayudarte a correlacionar cualquier evento, archivo y direcciones IP en relación con el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-163">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="5031c-164">La escala de tiempo también permite profundizar selectivamente en los eventos que se produjeron en un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="5031c-164">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="5031c-165">Puedes ver la secuencia temporal de eventos que se produjeron en un dispositivo durante un período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5031c-165">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="5031c-166">Para controlar aún más la vista, puede filtrar por grupos de eventos o personalizar las columnas.</span><span class="sxs-lookup"><span data-stu-id="5031c-166">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="5031c-167">Para que se muestren eventos de firewall, deberá habilitar la directiva de auditoría, consulte [Audit Filtering Platform connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span><span class="sxs-lookup"><span data-stu-id="5031c-167">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="5031c-168">Firewall cubre los siguientes eventos</span><span class="sxs-lookup"><span data-stu-id="5031c-168">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="5031c-169">[5025:](/windows/security/threat-protection/auditing/event-5025) servicio de firewall detenido</span><span class="sxs-lookup"><span data-stu-id="5031c-169">[5025](/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="5031c-170">[5031:](/windows/security/threat-protection/auditing/event-5031) aplicación bloqueada para no aceptar conexiones entrantes en la red</span><span class="sxs-lookup"><span data-stu-id="5031c-170">[5031](/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="5031c-171">[5157:](/windows/security/threat-protection/auditing/event-5157) conexión bloqueada</span><span class="sxs-lookup"><span data-stu-id="5031c-171">[5157](/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Imagen de la escala de tiempo del dispositivo con eventos](images/timeline-device.png)

<span data-ttu-id="5031c-173">Algunas de las funciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="5031c-173">Some of the functionality includes:</span></span>

- <span data-ttu-id="5031c-174">Buscar eventos específicos</span><span class="sxs-lookup"><span data-stu-id="5031c-174">Search for specific events</span></span>
  - <span data-ttu-id="5031c-175">Use la barra de búsqueda para buscar eventos de escala de tiempo específicos.</span><span class="sxs-lookup"><span data-stu-id="5031c-175">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="5031c-176">Filtrar eventos de una fecha específica</span><span class="sxs-lookup"><span data-stu-id="5031c-176">Filter events from a specific date</span></span>
  - <span data-ttu-id="5031c-177">Seleccione el icono de calendario de la parte superior izquierda de la tabla para mostrar los eventos del último día, semana, 30 días o intervalo personalizado.</span><span class="sxs-lookup"><span data-stu-id="5031c-177">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="5031c-178">De forma predeterminada, la escala de tiempo del dispositivo está configurada para mostrar los eventos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="5031c-178">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="5031c-179">Use la escala de tiempo para saltar a un momento específico en el tiempo resaltando la sección.</span><span class="sxs-lookup"><span data-stu-id="5031c-179">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="5031c-180">Las flechas de la escala de tiempo localizan investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="5031c-180">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="5031c-181">Exportar eventos detallados de escala de tiempo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5031c-181">Export detailed device timeline events</span></span>
  - <span data-ttu-id="5031c-182">Exporte la escala de tiempo del dispositivo para la fecha actual o un intervalo de fechas especificado hasta siete días.</span><span class="sxs-lookup"><span data-stu-id="5031c-182">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="5031c-183">En la sección Información adicional se proporcionan más detalles sobre determinados **eventos.**</span><span class="sxs-lookup"><span data-stu-id="5031c-183">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="5031c-184">Estos detalles varían según el tipo de evento, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5031c-184">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="5031c-185">Contenido por Application Guard: el evento del explorador web estaba restringido por un contenedor aislado</span><span class="sxs-lookup"><span data-stu-id="5031c-185">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="5031c-186">Amenaza activa detectada: la detección de amenazas se produjo mientras se ejecutaba la amenaza</span><span class="sxs-lookup"><span data-stu-id="5031c-186">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="5031c-187">Corrección sin éxito: se invocó un intento de corregir la amenaza detectada, pero se falló</span><span class="sxs-lookup"><span data-stu-id="5031c-187">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="5031c-188">Corrección correcta: la amenaza detectada se detuvo y se limpió</span><span class="sxs-lookup"><span data-stu-id="5031c-188">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="5031c-189">Advertencia omitida por el usuario: la advertencia Windows Defender SmartScreen fue descartada e invalidada por un usuario</span><span class="sxs-lookup"><span data-stu-id="5031c-189">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="5031c-190">Script sospechoso detectado: se encontró un script potencialmente malintencionado en ejecución</span><span class="sxs-lookup"><span data-stu-id="5031c-190">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="5031c-191">La categoría de alerta: si el evento condujo a la generación de una alerta, se proporciona la categoría de alerta ("Movimiento lateral", por ejemplo)</span><span class="sxs-lookup"><span data-stu-id="5031c-191">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="5031c-192">Detalles del evento</span><span class="sxs-lookup"><span data-stu-id="5031c-192">Event details</span></span>
<span data-ttu-id="5031c-193">Seleccione un evento para ver los detalles relevantes sobre ese evento.</span><span class="sxs-lookup"><span data-stu-id="5031c-193">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="5031c-194">Se muestra un panel para mostrar información general de eventos.</span><span class="sxs-lookup"><span data-stu-id="5031c-194">A panel displays to show general event information.</span></span> <span data-ttu-id="5031c-195">Cuando se aplica y los datos están disponibles, también se muestra un gráfico que muestra las entidades relacionadas y sus relaciones.</span><span class="sxs-lookup"><span data-stu-id="5031c-195">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="5031c-196">Para inspeccionar aún más el evento y los [](advanced-hunting-overview.md) eventos relacionados, puede ejecutar rápidamente una consulta de búsqueda **avanzada seleccionando Hunt para eventos relacionados.**</span><span class="sxs-lookup"><span data-stu-id="5031c-196">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="5031c-197">La consulta devolverá el evento seleccionado y la lista de otros eventos que se produjeron aproximadamente al mismo tiempo en el mismo extremo.</span><span class="sxs-lookup"><span data-stu-id="5031c-197">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Imagen del panel de detalles del evento](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="5031c-199">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="5031c-199">Security recommendations</span></span>

<span data-ttu-id="5031c-200">**Las recomendaciones de** seguridad se generan desde Microsoft Defender para la funcionalidad de administración de [& de](tvm-dashboard-insights.md) vulnerabilidades de Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5031c-200">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="5031c-201">Si selecciona una recomendación, se mostrará un panel en el que podrá ver detalles relevantes, como la descripción de la recomendación y los posibles riesgos asociados a no aprobarla.</span><span class="sxs-lookup"><span data-stu-id="5031c-201">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="5031c-202">Consulte [Recomendación de seguridad](tvm-security-recommendation.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5031c-202">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Imagen de la pestaña recomendaciones de seguridad](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="5031c-204">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="5031c-204">Software inventory</span></span>

<span data-ttu-id="5031c-205">La **pestaña Inventario de** software te permite ver software en el dispositivo, junto con cualquier debilidad o amenaza.</span><span class="sxs-lookup"><span data-stu-id="5031c-205">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="5031c-206">Seleccionar el nombre del software le llevará a la página de detalles del software donde puede ver recomendaciones de seguridad, vulnerabilidades detectadas, dispositivos instalados y distribución de versiones.</span><span class="sxs-lookup"><span data-stu-id="5031c-206">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="5031c-207">Consulta [Inventario de software](tvm-software-inventory.md) para obtener más información</span><span class="sxs-lookup"><span data-stu-id="5031c-207">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Imagen de la pestaña inventario de software](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="5031c-209">Vulnerabilidades detectadas</span><span class="sxs-lookup"><span data-stu-id="5031c-209">Discovered vulnerabilities</span></span>

<span data-ttu-id="5031c-210">La **pestaña Vulnerabilidades detectadas** muestra el nombre, la gravedad y las perspectivas de amenazas de las vulnerabilidades detectadas en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-210">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="5031c-211">Al seleccionar vulnerabilidades específicas, se mostrará una descripción y detalles.</span><span class="sxs-lookup"><span data-stu-id="5031c-211">Selecting specific vulnerabilities will show a description and details.</span></span>

![Imagen de la pestaña vulnerabilidades detectadas](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="5031c-213">Faltan KBs</span><span class="sxs-lookup"><span data-stu-id="5031c-213">Missing KBs</span></span>
<span data-ttu-id="5031c-214">En **la pestaña KBs que** faltan se enumeran las actualizaciones de seguridad que faltan para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5031c-214">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Imagen de la pestaña kbs que falta](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="5031c-216">Tarjetas</span><span class="sxs-lookup"><span data-stu-id="5031c-216">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="5031c-217">Alertas activas</span><span class="sxs-lookup"><span data-stu-id="5031c-217">Active alerts</span></span>

<span data-ttu-id="5031c-218">La **tarjeta protección contra** amenazas avanzada de Azure mostrará una descripción general de alto nivel de las alertas relacionadas con el dispositivo y su nivel de riesgo, si ha habilitado la característica Microsoft Defender para la identidad y hay alertas activas.</span><span class="sxs-lookup"><span data-stu-id="5031c-218">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="5031c-219">Encontrará más información en el desglose de "Alertas".</span><span class="sxs-lookup"><span data-stu-id="5031c-219">More information is available in the "Alerts" drill down.</span></span>

![Imagen de la tarjeta de alertas activas](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="5031c-221">Tendrás que habilitar la integración en Microsoft Defender para Identidad y Defender para endpoint para usar esta característica.</span><span class="sxs-lookup"><span data-stu-id="5031c-221">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="5031c-222">En Defender para endpoint, puedes habilitar esta característica en características avanzadas.</span><span class="sxs-lookup"><span data-stu-id="5031c-222">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="5031c-223">Para obtener más información sobre cómo habilitar características avanzadas, vea [Activar características avanzadas.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="5031c-223">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="5031c-224">Usuarios que han iniciado sesión</span><span class="sxs-lookup"><span data-stu-id="5031c-224">Logged on users</span></span>

<span data-ttu-id="5031c-225">La **tarjeta Usuarios que han iniciado** sesión muestra cuántos usuarios han iniciado sesión en los últimos 30 días, junto con los usuarios más y menos frecuentes.</span><span class="sxs-lookup"><span data-stu-id="5031c-225">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="5031c-226">Al seleccionar el vínculo "Ver todos los usuarios", se abre el panel de detalles, que muestra información como el tipo de usuario, el tipo de inicio de sesión y el momento en que el usuario se vio por primera y última vez.</span><span class="sxs-lookup"><span data-stu-id="5031c-226">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="5031c-227">Para obtener más información, vea [Investigar entidades de usuario](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="5031c-227">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Imagen del panel de detalles del usuario](images/logged-on-users.png)
> [!NOTE]
> <span data-ttu-id="5031c-229">El valor de usuario "Más frecuente" se calcula solo en función de la evidencia de usuarios que iniciaron sesión correctamente de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="5031c-229">The 'Most frequent' user value is calculated only based on evidence of users who successfully logged on interactively.</span></span> <span data-ttu-id="5031c-230">Sin embargo, el panel lateral "Todos los usuarios" calcula todo tipo de inicios de sesión de usuario, por lo que se espera que vea usuarios más frecuentes en el panel lateral, dado que es posible que dichos usuarios no sean interactivos.</span><span class="sxs-lookup"><span data-stu-id="5031c-230">However, the "All users" side-pane calculates all sorts of user logons so it is expected to see more frequent users in the side-pane, given that those users may not be interactive.</span></span>

### <a name="security-assessments"></a><span data-ttu-id="5031c-231">Evaluaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="5031c-231">Security assessments</span></span>

<span data-ttu-id="5031c-232">La **tarjeta Evaluaciones de seguridad** muestra el nivel de exposición general, las recomendaciones de seguridad, el software instalado y las vulnerabilidades detectadas.</span><span class="sxs-lookup"><span data-stu-id="5031c-232">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="5031c-233">El nivel de exposición de un dispositivo viene determinado por el impacto acumulado de sus recomendaciones de seguridad pendientes.</span><span class="sxs-lookup"><span data-stu-id="5031c-233">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Imagen de la tarjeta de evaluaciones de seguridad](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="5031c-235">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5031c-235">Related topics</span></span>

- [<span data-ttu-id="5031c-236">Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5031c-236">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="5031c-237">Administrar alertas de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="5031c-237">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="5031c-238">Investigar alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5031c-238">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="5031c-239">Investigar un archivo asociado a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5031c-239">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="5031c-240">Investigar una dirección IP asociada a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5031c-240">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="5031c-241">Investigar un dominio asociado a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5031c-241">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="5031c-242">Investigar una cuenta de usuario en Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5031c-242">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="5031c-243">Recomendación de seguridad</span><span class="sxs-lookup"><span data-stu-id="5031c-243">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="5031c-244">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="5031c-244">Software inventory</span></span>](tvm-software-inventory.md)
