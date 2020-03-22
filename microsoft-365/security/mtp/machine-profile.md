---
title: Perfil de equipo en el portal de seguridad 365 de Microsoft
description: Ver los niveles de riesgo y exposición de un dispositivo en la organización. Analice las amenazas pasadas y presentes y proteja el equipo con las actualizaciones más recientes.
keywords: seguridad, malware, Microsoft 365, M365, protección contra amenazas de Microsoft, MTP, centro de seguridad, ATP de Microsoft defender, Office 365 ATP, ATP de Azure, página de equipo, lista de equipos, perfil de máquina
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 1dfb567c8e6b8573397d503ae27c0aceb447c916
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895468"
---
# <a name="machine-profile-page"></a><span data-ttu-id="af40c-105">Página de perfil de equipo</span><span class="sxs-lookup"><span data-stu-id="af40c-105">Machine profile page</span></span>

<span data-ttu-id="af40c-106">El portal de seguridad 365 de Microsoft proporciona páginas de Perfil de equipo, para que pueda evaluar el estado y el estado de los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="af40c-106">The Microsoft 365 security portal provides you with Machine profile pages, so you can assess the health and status of devices on your network.</span></span> <span data-ttu-id="af40c-107">Cada página de Perfil de la máquina contiene una gran cantidad de información sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-107">Each Machine profile page contains a wealth of information about the device.</span></span>

<span data-ttu-id="af40c-108">Puede revisar información detallada sobre el software que se está ejecutando, las alertas y eventos de seguridad pasados y presentes, y buscar vínculos a revisiones de software relevantes.</span><span class="sxs-lookup"><span data-stu-id="af40c-108">You can review in-depth information about what software it is running, any past and present security events or alerts, and find links to relevant software patches.</span></span>

<span data-ttu-id="af40c-109">También puede usar el perfil del equipo para realizar tareas comunes relacionadas con la seguridad y revisar rápidamente los detalles básicos del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-109">You can also use the Machine profile to perform common security-related tasks, and quickly review basic details about the device.</span></span>

## <a name="navigating-the-machine-profile-page"></a><span data-ttu-id="af40c-110">Navegación por la página de Perfil de la máquina</span><span class="sxs-lookup"><span data-stu-id="af40c-110">Navigating the Machine profile page</span></span>

<span data-ttu-id="af40c-111">La página de perfil del equipo se divide en tres secciones.</span><span class="sxs-lookup"><span data-stu-id="af40c-111">The machine profile page is broken up into three sections.</span></span>

![Imagen de la página Perfil de la máquina con (1) área de la ficha (2) sidebar y (3) acciones resaltadas en rojo](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

<span data-ttu-id="af40c-113">El área de contenido principal (1) contiene siete pestañas que puede alternar para ver distintos tipos de información sobre el equipo.</span><span class="sxs-lookup"><span data-stu-id="af40c-113">The main content area (1) contains seven tabs that you can toggle through to view different kinds of information about the machine.</span></span>

<span data-ttu-id="af40c-114">La barra lateral (2) enumera los detalles básicos sobre el equipo.</span><span class="sxs-lookup"><span data-stu-id="af40c-114">The sidebar (2) lists basic details about the machine.</span></span>

<span data-ttu-id="af40c-115">También hay acciones de respuesta disponibles en un encabezado (3) antes de las secciones de barra lateral y contenido principal.</span><span class="sxs-lookup"><span data-stu-id="af40c-115">There are also response actions available in a header (3) before the sidebar and main content sections.</span></span> <span data-ttu-id="af40c-116">Puede usar las acciones de este encabezado para realizar tareas comunes relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="af40c-116">You can use the actions in this header to perform common security-related tasks.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="af40c-117">Sección Tabulaciones</span><span class="sxs-lookup"><span data-stu-id="af40c-117">Tabs section</span></span>

<span data-ttu-id="af40c-118">Las pestañas de Perfil de equipo permiten alternar información general sobre la seguridad de la máquina y tablas que contienen una lista de alertas, una escala de tiempo, una lista de recomendaciones de seguridad, un inventario de software, una lista de vulnerabilidades detectadas y que faltan. KB (actualizaciones de seguridad).</span><span class="sxs-lookup"><span data-stu-id="af40c-118">The Machine profile tabs allow you to toggle through an overview of security details about the machine, and tables containing a list of alerts, a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="af40c-119">Ficha Información general</span><span class="sxs-lookup"><span data-stu-id="af40c-119">Overview tab</span></span>

<span data-ttu-id="af40c-120">La pestaña predeterminada es **información general**.</span><span class="sxs-lookup"><span data-stu-id="af40c-120">The default tab is **Overview**.</span></span> <span data-ttu-id="af40c-121">Proporciona una visión rápida del hecho de seguridad más importante sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-121">It provides a quick look at the most important security fact about the device.</span></span>

![Imagen de la ficha Información general para el perfil del equipo](../../media/mtp-machine-profile/overview.png)

<span data-ttu-id="af40c-123">Aquí puede encontrar un gráfico del nivel de riesgo del dispositivo y las alertas activas, cualquier usuario que haya iniciado sesión, una lista breve de los usuarios más frecuentes y las evaluaciones de seguridad que detallan el nivel de exposición del dispositivo, las recomendaciones de seguridad, el software afectado y vulnerabilidades detectadas.</span><span class="sxs-lookup"><span data-stu-id="af40c-123">Here, you can find a chart of the device's risk level and active alerts, any currently logged on users, a brief list of most and least frequent users, and security assessments that detail the device's exposure level, security recommendations, affected software, and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="af40c-124">Ficha Alertas</span><span class="sxs-lookup"><span data-stu-id="af40c-124">Alerts tab</span></span>

<span data-ttu-id="af40c-125">La ficha **alertas** contiene una lista de las alertas que se han notificado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-125">The **Alerts** tab contains a list of alerts that have been reported on the device.</span></span>

![Imagen de la ficha alertas para el perfil del equipo](../../media/mtp-machine-profile/alerts.png)

<span data-ttu-id="af40c-127">Puede personalizar el número de elementos mostrados, así como qué columnas se muestran para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="af40c-127">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="af40c-128">El comportamiento predeterminado es enumerar 30 elementos por página y tener 11 columnas activadas para mostrar.</span><span class="sxs-lookup"><span data-stu-id="af40c-128">The default behavior is to list 30 items per page, and have 11 columns toggled on to display.</span></span>

<span data-ttu-id="af40c-129">Las columnas de esta pestaña incluyen información sobre la gravedad de la amenaza que desencadenó la alerta, así como el estado, el estado de investigación y quién, si se ha asignado a algún usuario la alerta.</span><span class="sxs-lookup"><span data-stu-id="af40c-129">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who if anyone the alert has been assigned to.</span></span>

<span data-ttu-id="af40c-130">La columna *entidades afectadas* se refiere a la máquina (entidad) cuyo perfil está viendo actualmente, además de otros equipos de la red que se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="af40c-130">The *impacted entities* column refers to the machine (entity) whose profile you are currently viewing, plus any other machines in your network that are affected.</span></span>

<span data-ttu-id="af40c-131">Al seleccionar un elemento de esta lista, se abrirá un vínculo a la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="af40c-131">Selecting an item from this list will open a link to the selected alert.</span></span>

<span data-ttu-id="af40c-132">Esta lista se puede filtrar por gravedad, estado o asignada.</span><span class="sxs-lookup"><span data-stu-id="af40c-132">This list can be filtered by severity, status, or assignee.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="af40c-133">Ficha escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="af40c-133">Timeline tab</span></span>

<span data-ttu-id="af40c-134">La pestaña **escala de tiempo** incluye un gráfico interactivo e cronológico de eventos provocados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-134">The **Timeline** tab includes a interactive, chronological chart of events raised on the device.</span></span> <span data-ttu-id="af40c-135">Moviendo el área resaltada del gráfico, puede ver los eventos en intervalos de tiempo diferentes.</span><span class="sxs-lookup"><span data-stu-id="af40c-135">By moving the highlighted area of the chart, you can view events over different ranges of time.</span></span> <span data-ttu-id="af40c-136">También puede escribir un intervalo de fechas personalizado.</span><span class="sxs-lookup"><span data-stu-id="af40c-136">You can also type in a custom range of dates.</span></span>

<span data-ttu-id="af40c-137">Debajo del gráfico hay una lista de eventos para el intervalo de fechas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="af40c-137">Below the chart is a list of events for the selected range of dates.</span></span>

![Imagen de la ficha escala de tiempo para el perfil del equipo](../../media/mtp-machine-profile/timeline.png)

<span data-ttu-id="af40c-139">El número de elementos mostrados y las columnas de la lista se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="af40c-139">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="af40c-140">Las columnas predeterminadas muestran el tiempo del evento, el usuario activo, el tipo de acción, las entidades (procesos) y la información adicional sobre el evento.</span><span class="sxs-lookup"><span data-stu-id="af40c-140">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="af40c-141">Al seleccionar un elemento de la lista, se abrirá un control flotante que muestra un gráfico de entidades de evento, que muestra los procesos primarios y secundarios que desencadenó el evento.</span><span class="sxs-lookup"><span data-stu-id="af40c-141">Selecting an item from the list will open a flyout displaying an Event entities graph, showing the parent and child processes that triggered the event.</span></span>

<span data-ttu-id="af40c-142">Esta lista se puede filtrar por el tipo específico de evento; por ejemplo, eventos de registro o eventos de pantalla inteligente.</span><span class="sxs-lookup"><span data-stu-id="af40c-142">This list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="af40c-143">Ficha recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="af40c-143">Security recommendations tab</span></span>

<span data-ttu-id="af40c-144">La ficha **recomendaciones de seguridad** enumera las acciones que puede realizar para proteger el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-144">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="af40c-145">Al seleccionar un elemento de esta lista, se abrirá un control flotante donde puede obtener instrucciones sobre cómo aplicar la recomendación.</span><span class="sxs-lookup"><span data-stu-id="af40c-145">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Imagen de la ficha recomendaciones de seguridad para Perfil de equipo](../../media/mtp-machine-profile/security-recs.png)

<span data-ttu-id="af40c-147">Como con las pestañas anteriores, se puede personalizar el número de elementos que se muestran por página y qué columnas son visibles.</span><span class="sxs-lookup"><span data-stu-id="af40c-147">As with the previous tabs, the number of items displayed per page and which columns are visible can be customized.</span></span>

<span data-ttu-id="af40c-148">La vista predeterminada incluye columnas que detallan las debilidades de seguridad tratadas, la amenaza asociada, el componente o software relacionado con la amenaza, entre otros.</span><span class="sxs-lookup"><span data-stu-id="af40c-148">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="af40c-149">Los elementos se pueden filtrar por el estado de la recomendación.</span><span class="sxs-lookup"><span data-stu-id="af40c-149">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="af40c-150">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="af40c-150">Software inventory</span></span>

<span data-ttu-id="af40c-151">La ficha **inventario de software** enumera el software instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-151">The **Software inventory** tab lists software installed on the device.</span></span>

![Imagen de la ficha inventario de software para Perfil de equipo](../../media/mtp-machine-profile/software-inventory.png)

<span data-ttu-id="af40c-153">La vista predeterminada muestra el proveedor de software, el número de versión instalado, el número de debilidades de software conocidos, la información sobre amenazas, el código de producto y las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="af40c-153">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="af40c-154">El número de elementos mostrados y las columnas que se muestran pueden personalizarse.</span><span class="sxs-lookup"><span data-stu-id="af40c-154">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="af40c-155">Al seleccionar un elemento de esta lista, se abre un control flotante que contiene más detalles sobre el software seleccionado, así como la ruta de acceso y la marca de tiempo de la última vez que se encontró el software.</span><span class="sxs-lookup"><span data-stu-id="af40c-155">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="af40c-156">Esta lista se puede filtrar por código de producto.</span><span class="sxs-lookup"><span data-stu-id="af40c-156">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="af40c-157">Ficha vulnerabilidades detectadas</span><span class="sxs-lookup"><span data-stu-id="af40c-157">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="af40c-158">En la ficha **vulnerabilidades detectadas** se muestran las vulnerabilidades y los puntos débiles comunes (CVE) que pueden afectar al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-158">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Imagen de la ficha vulnerabilidades detectadas para el perfil del equipo](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

<span data-ttu-id="af40c-160">La vista predeterminada muestra la gravedad de CVE, la puntuación de vulnerabilidad común (CVS), el software relacionado con el CVE, Cuándo se publicó el CVE, Cuándo se actualizó por última vez el CVE y las amenazas asociadas con el CVE.</span><span class="sxs-lookup"><span data-stu-id="af40c-160">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="af40c-161">Como en las pestañas anteriores, se puede personalizar el número de elementos que se muestran y las columnas que son visibles.</span><span class="sxs-lookup"><span data-stu-id="af40c-161">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="af40c-162">Al seleccionar un elemento de esta lista, se abrirá un control flotante que describe el CVE.</span><span class="sxs-lookup"><span data-stu-id="af40c-162">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="af40c-163">KB faltantes</span><span class="sxs-lookup"><span data-stu-id="af40c-163">Missing KBs</span></span>

<span data-ttu-id="af40c-164">La ficha **KB que falta** muestra una lista de las actualizaciones de Microsoft que aún no se han aplicado al equipo.</span><span class="sxs-lookup"><span data-stu-id="af40c-164">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the machine.</span></span> <span data-ttu-id="af40c-165">Los "KB" en cuestión son [artículos de Knowledge Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que describen estas actualizaciones; por ejemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="af40c-165">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Imagen de la ficha de KB que falta para el perfil del equipo](../../media/mtp-machine-profile/missing-kbs.PNG)

<span data-ttu-id="af40c-167">La vista predeterminada enumera el boletín que contiene las actualizaciones, la versión del sistema operativo, los productos afectados, CVE dirección, el número de KB y las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="af40c-167">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="af40c-168">Se puede personalizar el número de elementos que se muestran por página y qué columnas se muestran.</span><span class="sxs-lookup"><span data-stu-id="af40c-168">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="af40c-169">Al seleccionar un elemento, se abrirá un control flotante que se vincula a la actualización.</span><span class="sxs-lookup"><span data-stu-id="af40c-169">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="sidebar"></a><span data-ttu-id="af40c-170">-</span><span class="sxs-lookup"><span data-stu-id="af40c-170">Sidebar</span></span>

<span data-ttu-id="af40c-171">Junto al área de contenido principal de la página de perfil del equipo se encuentra la barra lateral.</span><span class="sxs-lookup"><span data-stu-id="af40c-171">Beside the main content area of the Machine profile page is the sidebar.</span></span>

![Imagen de la pestaña de la barra lateral para el perfil del equipo](../../media/mtp-machine-profile/sidebar.png)

<span data-ttu-id="af40c-173">La barra lateral proporciona información básica importante en subsecciones pequeñas que se pueden alternar abrir o cerrar:</span><span class="sxs-lookup"><span data-stu-id="af40c-173">The sidebar provides some important basic information in small subsections which can be toggled open or closed:</span></span>

* <span data-ttu-id="af40c-174">**Etiquetas** : todas las etiquetas asociadas con el dispositivo</span><span class="sxs-lookup"><span data-stu-id="af40c-174">**Tags** - Any tags associated with the device</span></span>
* <span data-ttu-id="af40c-175">**Información de seguridad** : incidentes abiertos, alertas activas, nivel de exposición y nivel de riesgo</span><span class="sxs-lookup"><span data-stu-id="af40c-175">**Security info** - Open incidents, active alerts, exposure level and risk level</span></span>
* <span data-ttu-id="af40c-176">**Detalles de dispositivo** : dominio, sistema operativo, grupo de activos, estado de mantenimiento, sensibilidad de datos y direcciones IP</span><span class="sxs-lookup"><span data-stu-id="af40c-176">**Device details** - Domain, OS, Asset group, health state, data sensitivity, and IP addresses</span></span>
* <span data-ttu-id="af40c-177">**Actividad de red** : marcas de tiempo de la primera vez y última vez que el dispositivo se ve en la red</span><span class="sxs-lookup"><span data-stu-id="af40c-177">**Network activity** - Timestamps for the first time and last time the device was seen on the network</span></span>

<span data-ttu-id="af40c-178">En esta sección también se incluye el nombre y el nivel de exposición del dispositivo, y un icono para indicar si está activo actualmente en la red.</span><span class="sxs-lookup"><span data-stu-id="af40c-178">This section also includes the name and exposure level of the device, and an icon to indicate if it is currently active on the network.</span></span>

## <a name="response-actions"></a><span data-ttu-id="af40c-179">Acciones de respuesta</span><span class="sxs-lookup"><span data-stu-id="af40c-179">Response actions</span></span>

<span data-ttu-id="af40c-180">Las acciones de respuesta ofrecen una forma rápida de defenderse y analizar las amenazas.</span><span class="sxs-lookup"><span data-stu-id="af40c-180">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Imagen de la pestaña de la barra lateral para el perfil del equipo](../../media/mtp-machine-profile/actions.PNG)

<span data-ttu-id="af40c-182">Las acciones de respuesta disponibles para usted incluyen:</span><span class="sxs-lookup"><span data-stu-id="af40c-182">The response actions available to you here include:</span></span>

* <span data-ttu-id="af40c-183">**Administrar etiquetas** : actualiza las etiquetas personalizadas que hayas aplicado a este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af40c-183">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="af40c-184">**Aislar** : aísla el equipo de la red de la organización y manteniéndolo conectado a la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="af40c-184">**Isolate machine** - Isolates the machine from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="af40c-185">Puede optar por permitir que Outlook, Microsoft Teams y Skype empresarial se ejecuten mientras el equipo está aislado, con fines de comunicación.</span><span class="sxs-lookup"><span data-stu-id="af40c-185">You can choose to allow Outlook, Teams, and Skype for Business to run while the machine is isolated, for communication purposes.</span></span>
* <span data-ttu-id="af40c-186">**Restringir la ejecución** de la aplicación: evita que se ejecuten las aplicaciones que Microsoft no ha firmado.</span><span class="sxs-lookup"><span data-stu-id="af40c-186">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running</span></span>
* <span data-ttu-id="af40c-187">**Ejecutar detección de virus** : actualiza las definiciones de antivirus de Windows Defender y ejecuta inmediatamente un examen de antivirus.</span><span class="sxs-lookup"><span data-stu-id="af40c-187">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="af40c-188">Elija entre análisis rápido o análisis completo.</span><span class="sxs-lookup"><span data-stu-id="af40c-188">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="af40c-189">**Recopilar el paquete de investigación** : recopila información sobre el equipo.</span><span class="sxs-lookup"><span data-stu-id="af40c-189">**Collect investigation package** - Gathers information about the machine.</span></span> <span data-ttu-id="af40c-190">Una vez completada la investigación, puede descargarla.</span><span class="sxs-lookup"><span data-stu-id="af40c-190">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="af40c-191">**Iniciar sesión de respuesta activa** : carga un shell remoto en el equipo para [investigaciones de seguridad en profundidad](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="af40c-191">**Initiate Live Response session** - Loads a remote shell on the machine for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="af40c-192">**Iniciar investigación automatizada** : [investiga y corrige](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)automáticamente las amenazas.</span><span class="sxs-lookup"><span data-stu-id="af40c-192">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="af40c-193">Aunque puede desencadenar de forma manual investigaciones automáticas para que se ejecuten desde esta página, [algunas directivas de alertas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) desencadenan investigaciones automáticas por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="af40c-193">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="af40c-194">**Centro de actividades** : ver el estado de las acciones enviadas.</span><span class="sxs-lookup"><span data-stu-id="af40c-194">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="af40c-195">Solo está disponible si ya se ha seleccionado otra acción.</span><span class="sxs-lookup"><span data-stu-id="af40c-195">Only available if another action has already been selected.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af40c-196">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="af40c-196">Related topics</span></span>

* [<span data-ttu-id="af40c-197">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="af40c-197">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="af40c-198">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="af40c-198">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="af40c-199">Investigar entidades en equipos que usan la respuesta activa</span><span class="sxs-lookup"><span data-stu-id="af40c-199">Investigate entities on machines using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="af40c-200">Investigación y respuesta automatizadas (AIR) en Office 365</span><span class="sxs-lookup"><span data-stu-id="af40c-200">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
