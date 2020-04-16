---
title: Perfil de dispositivo en el portal de seguridad 365 de Microsoft
description: Ver los niveles de riesgo y exposición de un dispositivo en la organización. Analice las amenazas pasadas y presentes y proteja el dispositivo con las actualizaciones más recientes.
keywords: seguridad, malware, Microsoft 365, M365, protección contra amenazas de Microsoft, MTP, centro de seguridad, ATP de Microsoft defender, Office 365 ATP, ATP de Azure, página de dispositivo, perfil de dispositivo, página de equipo, perfil de máquina
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
ms.openlocfilehash: db6109fb73f0e208ab4403e2469bc955a1a01b38
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "43517073"
---
# <a name="device-profile-page"></a><span data-ttu-id="a883d-105">Página de Perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="a883d-105">Device profile page</span></span>

<span data-ttu-id="a883d-106">El portal de seguridad 365 de Microsoft proporciona páginas de Perfil de dispositivo para que pueda evaluar rápidamente el estado y el estado de los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="a883d-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a883d-107">La página de Perfil de dispositivo puede aparecer ligeramente diferente en función de si el dispositivo está inscrito en ATP de Microsoft defender, en ATP de Azure o en ambas.</span><span class="sxs-lookup"><span data-stu-id="a883d-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender ATP, Azure ATP, or both.</span></span>

<span data-ttu-id="a883d-108">Si el dispositivo está inscrito en ATP de Microsoft defender, también puede usar la página Perfil de dispositivo para realizar algunas tareas de seguridad comunes.</span><span class="sxs-lookup"><span data-stu-id="a883d-108">If the device is enrolled in Microsoft Defender ATP, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="a883d-109">Navegación por la página de Perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="a883d-109">Navigating the device profile page</span></span>

<span data-ttu-id="a883d-110">La página de perfil se divide en varias secciones generales.</span><span class="sxs-lookup"><span data-stu-id="a883d-110">The profile page is broken up into several broad sections.</span></span>

![Imagen de la página de Perfil de dispositivo con (1) área de la ficha (2) sidebar y (3) acciones resaltadas en rojo](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="a883d-112">La barra lateral (1) enumera los detalles básicos sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="a883d-113">El área de contenido principal (2) contiene pestañas que se pueden alternar para ver distintos tipos de información sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="a883d-114">Si el dispositivo está inscrito en ATP de Microsoft defender, también verá una lista de acciones de respuesta (3).</span><span class="sxs-lookup"><span data-stu-id="a883d-114">If the device is enrolled in Microsoft Defender ATP, you will also see a list of response actions (3).</span></span> <span data-ttu-id="a883d-115">Las acciones de respuesta le permiten realizar tareas comunes relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="a883d-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="a883d-116">-</span><span class="sxs-lookup"><span data-stu-id="a883d-116">Sidebar</span></span>

<span data-ttu-id="a883d-117">Junto al área de contenido principal de la página de perfil del dispositivo se encuentra la barra lateral.</span><span class="sxs-lookup"><span data-stu-id="a883d-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Imagen de la pestaña de la barra lateral para Perfil de dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="a883d-119">La barra lateral muestra el nombre completo y el nivel de exposición del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="a883d-120">También se proporciona información básica importante en subsecciones pequeñas que se pueden alternar abiertas o cerradas, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a883d-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="a883d-121">**Etiquetas** : cualquier ATP de Microsoft defender, ATP de Azure o etiquetas personalizadas asociadas con el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-121">**Tags** - Any Microsoft Defender ATP, Azure ATP, or custom tags associated with the device.</span></span> <span data-ttu-id="a883d-122">Las etiquetas de Azure ATP no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="a883d-122">Tags from Azure ATP are not editable.</span></span>
* <span data-ttu-id="a883d-123">**Información de seguridad** : incidentes abiertos y alertas activas.</span><span class="sxs-lookup"><span data-stu-id="a883d-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="a883d-124">Los dispositivos inscritos en ATP de Microsoft defender también mostrarán el nivel de exposición y el nivel de riesgo.</span><span class="sxs-lookup"><span data-stu-id="a883d-124">Devices enrolled in Microsoft Defender ATP will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="a883d-125">El nivel de exposición está relacionado con la medida en que el dispositivo cumple con las recomendaciones de seguridad, mientras que el nivel de riesgo se calcula en función de una serie de factores, incluidos los tipos y la gravedad de las alertas activas.</span><span class="sxs-lookup"><span data-stu-id="a883d-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="a883d-126">**Detalles del dispositivo** : dominio, so, marca de tiempo para cuando se ha visto el dispositivo por primera vez, direcciones IP y recursos.</span><span class="sxs-lookup"><span data-stu-id="a883d-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="a883d-127">Los dispositivos inscritos en Microsoft defender ATP también muestran el estado de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a883d-127">Devices enrolled in Microsoft Defender ATP also display health state.</span></span> <span data-ttu-id="a883d-128">Los dispositivos inscritos en ATP de Azure mostrarán el nombre SAM y una marca de hora para cuando se creó el dispositivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a883d-128">Devices enrolled in Azure ATP will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="a883d-129">**Actividad de red** : marcas de tiempo para la primera y última vez que el dispositivo se ve en la red.</span><span class="sxs-lookup"><span data-stu-id="a883d-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="a883d-130">**Datos del directorio** (*solo para dispositivos inscritos en ATP de Azure*): marcas [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) , [SPN](https://docs.microsoft.com/windows/win32/ad/service-principal-names)y pertenencias a grupos.</span><span class="sxs-lookup"><span data-stu-id="a883d-130">**Directory data** (*only for devices enrolled in Azure ATP*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="a883d-131">Acciones de respuesta</span><span class="sxs-lookup"><span data-stu-id="a883d-131">Response actions</span></span>

<span data-ttu-id="a883d-132">Las acciones de respuesta ofrecen una forma rápida de defenderse y analizar las amenazas.</span><span class="sxs-lookup"><span data-stu-id="a883d-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Imagen de la barra de acciones para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="a883d-134">[Las acciones de respuesta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) solo están disponibles si el dispositivo está inscrito en ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a883d-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender ATP.</span></span>
> * <span data-ttu-id="a883d-135">Los dispositivos inscritos en ATP de Microsoft defender pueden mostrar diferentes números de acciones de respuesta según el sistema operativo del dispositivo y el número de versión.</span><span class="sxs-lookup"><span data-stu-id="a883d-135">Devices that are enrolled in Microsoft Defender ATP may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="a883d-136">Las acciones disponibles en la página de Perfil de dispositivo incluyen:</span><span class="sxs-lookup"><span data-stu-id="a883d-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="a883d-137">**Administrar etiquetas** : actualiza las etiquetas personalizadas que hayas aplicado a este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="a883d-138">**Aislar dispositivo** : aísla el dispositivo de la red de su organización y conserva la conexión con la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a883d-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="a883d-139">Puede elegir permitir que se ejecuten Outlook, Teams y Skype empresarial mientras el dispositivo está aislado, con fines de comunicación.</span><span class="sxs-lookup"><span data-stu-id="a883d-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="a883d-140">**Centro de actividades** : ver el estado de las acciones enviadas.</span><span class="sxs-lookup"><span data-stu-id="a883d-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="a883d-141">Solo está disponible si ya se ha seleccionado otra acción.</span><span class="sxs-lookup"><span data-stu-id="a883d-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="a883d-142">**Restringir la ejecución** de la aplicación: evita que se ejecuten las aplicaciones que Microsoft no ha firmado.</span><span class="sxs-lookup"><span data-stu-id="a883d-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="a883d-143">**Ejecutar detección de virus** : actualiza las definiciones de antivirus de Windows Defender y ejecuta inmediatamente un examen de antivirus.</span><span class="sxs-lookup"><span data-stu-id="a883d-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="a883d-144">Elija entre análisis rápido o análisis completo.</span><span class="sxs-lookup"><span data-stu-id="a883d-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="a883d-145">**Recopilar el paquete de investigación** : recopila información sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="a883d-146">Una vez completada la investigación, puede descargarla.</span><span class="sxs-lookup"><span data-stu-id="a883d-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="a883d-147">**Iniciar sesión de respuesta activa** : carga un shell remoto en el dispositivo para [investigaciones de seguridad en profundidad](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="a883d-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="a883d-148">**Iniciar investigación automatizada** : [investiga y corrige](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)automáticamente las amenazas.</span><span class="sxs-lookup"><span data-stu-id="a883d-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="a883d-149">Aunque puede desencadenar de forma manual investigaciones automáticas para que se ejecuten desde esta página, [algunas directivas de alertas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) desencadenan investigaciones automáticas por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="a883d-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="a883d-150">**Centro de actividades** : muestra información sobre las acciones de respuesta que se están ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="a883d-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="a883d-151">Sección Tabulaciones</span><span class="sxs-lookup"><span data-stu-id="a883d-151">Tabs section</span></span>

<span data-ttu-id="a883d-152">Las fichas de Perfil de dispositivo permiten alternar entre una introducción a los detalles de seguridad del dispositivo y las tablas que contienen una lista de alertas.</span><span class="sxs-lookup"><span data-stu-id="a883d-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="a883d-153">Los dispositivos inscritos en ATP de Microsoft defender también mostrarán pestañas que incluyen una escala de tiempo, una lista de recomendaciones de seguridad, un inventario de software, una lista de vulnerabilidades descubiertas y los KB (actualizaciones de seguridad) que faltan.</span><span class="sxs-lookup"><span data-stu-id="a883d-153">Devices enrolled in Microsoft Defender ATP will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="a883d-154">Ficha Información general</span><span class="sxs-lookup"><span data-stu-id="a883d-154">Overview tab</span></span>

<span data-ttu-id="a883d-155">La pestaña predeterminada es **información general**.</span><span class="sxs-lookup"><span data-stu-id="a883d-155">The default tab is **Overview**.</span></span> <span data-ttu-id="a883d-156">Proporciona una visión rápida del hecho de seguridad más importante sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-156">It provides a quick look at the most important security fact about the device.</span></span>

![Imagen de la ficha Información general de Perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="a883d-158">Aquí puede ver rápidamente las alertas activas del dispositivo y cualquier usuario que haya iniciado sesión en ese momento.</span><span class="sxs-lookup"><span data-stu-id="a883d-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="a883d-159">Si el dispositivo está inscrito en ATP de Microsoft defender, también verá el nivel de riesgo del dispositivo y los datos disponibles en las evaluaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a883d-159">If the device is enrolled in Microsoft Defender ATP, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="a883d-160">Las evaluaciones de seguridad describen el nivel de exposición del dispositivo, proporcionan recomendaciones de seguridad y enumeran el software afectado y las vulnerabilidades detectadas.</span><span class="sxs-lookup"><span data-stu-id="a883d-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="a883d-161">Ficha Alertas</span><span class="sxs-lookup"><span data-stu-id="a883d-161">Alerts tab</span></span>

<span data-ttu-id="a883d-162">La pestaña **alertas** contiene una lista de las alertas que se han generado en el dispositivo, tanto de ATP de Azure como de ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a883d-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Azure ATP and Microsoft Defender ATP.</span></span>

![Imagen de la pestaña de alertas para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="a883d-164">Puede personalizar el número de elementos mostrados, así como qué columnas se muestran para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="a883d-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="a883d-165">El comportamiento predeterminado es enumerar treinta elementos por página.</span><span class="sxs-lookup"><span data-stu-id="a883d-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="a883d-166">Las columnas de esta pestaña incluyen información sobre la gravedad de la amenaza que desencadenó la alerta, así como el estado, el estado de investigación y a quién se ha asignado la alerta.</span><span class="sxs-lookup"><span data-stu-id="a883d-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="a883d-167">La columna *entidades afectadas* se refiere al dispositivo (entidad) cuyo perfil está viendo actualmente, además de otros dispositivos de la red que se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="a883d-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="a883d-168">Al seleccionar un elemento de esta lista, se abrirá un control flotante que contiene todavía más información sobre la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a883d-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="a883d-169">Esta lista se puede filtrar por gravedad, estado o a quién se ha asignado la alerta.</span><span class="sxs-lookup"><span data-stu-id="a883d-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="a883d-170">Ficha escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="a883d-170">Timeline tab</span></span>

<span data-ttu-id="a883d-171">La ficha **escala de tiempo** incluye un gráfico cronológico interactivo de todos los eventos que se producen en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="a883d-172">Moviendo el área resaltada del gráfico a la izquierda o a la derecha, puede ver los eventos durante distintos períodos de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a883d-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="a883d-173">También puede elegir un intervalo de fechas personalizado en el menú desplegable entre el gráfico interactivo y la lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="a883d-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="a883d-174">Debajo del gráfico hay una lista de eventos para el intervalo de fechas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a883d-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Imagen de la pestaña escala de tiempo para Perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="a883d-176">El número de elementos mostrados y las columnas de la lista se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="a883d-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="a883d-177">Las columnas predeterminadas muestran el tiempo del evento, el usuario activo, el tipo de acción, las entidades (procesos) y la información adicional sobre el evento.</span><span class="sxs-lookup"><span data-stu-id="a883d-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="a883d-178">Al seleccionar un elemento de esta lista, se abrirá un control flotante que muestra un gráfico de entidades de evento, donde se muestran los procesos primarios y secundarios implicados en el evento.</span><span class="sxs-lookup"><span data-stu-id="a883d-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="a883d-179">La lista se puede filtrar por el tipo específico de evento; por ejemplo, eventos de registro o eventos de pantalla inteligente.</span><span class="sxs-lookup"><span data-stu-id="a883d-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="a883d-180">La lista también se puede exportar a un archivo CSV, para su descarga.</span><span class="sxs-lookup"><span data-stu-id="a883d-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="a883d-181">Aunque el archivo no está limitado por el número de eventos, el intervalo de tiempo máximo que puede elegir para exportar es de siete días.</span><span class="sxs-lookup"><span data-stu-id="a883d-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="a883d-182">Ficha recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="a883d-182">Security recommendations tab</span></span>

<span data-ttu-id="a883d-183">La ficha **recomendaciones de seguridad** enumera las acciones que puede realizar para proteger el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="a883d-184">Al seleccionar un elemento de esta lista, se abrirá un control flotante donde puede obtener instrucciones sobre cómo aplicar la recomendación.</span><span class="sxs-lookup"><span data-stu-id="a883d-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Imagen de la ficha recomendaciones de seguridad para Perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="a883d-186">Como en las pestañas anteriores, el número de elementos que se muestran por página, así como las columnas que están visibles, se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="a883d-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="a883d-187">La vista predeterminada incluye columnas que detallan las debilidades de seguridad tratadas, la amenaza asociada, el componente o software relacionado con la amenaza, entre otros.</span><span class="sxs-lookup"><span data-stu-id="a883d-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="a883d-188">Los elementos se pueden filtrar por el estado de la recomendación.</span><span class="sxs-lookup"><span data-stu-id="a883d-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="a883d-189">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="a883d-189">Software inventory</span></span>

<span data-ttu-id="a883d-190">La ficha **inventario de software** enumera el software instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Imagen de la ficha inventario de software para Perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="a883d-192">La vista predeterminada muestra el proveedor de software, el número de versión instalado, el número de debilidades de software conocidos, la información sobre amenazas, el código de producto y las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a883d-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="a883d-193">El número de elementos mostrados y las columnas que se muestran pueden personalizarse.</span><span class="sxs-lookup"><span data-stu-id="a883d-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="a883d-194">Al seleccionar un elemento de esta lista, se abre un control flotante que contiene más detalles sobre el software seleccionado, así como la ruta de acceso y la marca de tiempo de la última vez que se encontró el software.</span><span class="sxs-lookup"><span data-stu-id="a883d-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="a883d-195">Esta lista se puede filtrar por código de producto.</span><span class="sxs-lookup"><span data-stu-id="a883d-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="a883d-196">Ficha vulnerabilidades detectadas</span><span class="sxs-lookup"><span data-stu-id="a883d-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="a883d-197">En la ficha **vulnerabilidades detectadas** se muestran las vulnerabilidades y los puntos débiles comunes (CVE) que pueden afectar al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Imagen de la pestaña vulnerabilidades detectadas para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="a883d-199">La vista predeterminada muestra la gravedad de CVE, la puntuación de vulnerabilidad común (CVS), el software relacionado con el CVE, Cuándo se publicó el CVE, Cuándo se actualizó por última vez el CVE y las amenazas asociadas con el CVE.</span><span class="sxs-lookup"><span data-stu-id="a883d-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="a883d-200">Como en las pestañas anteriores, se puede personalizar el número de elementos que se muestran y las columnas que son visibles.</span><span class="sxs-lookup"><span data-stu-id="a883d-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="a883d-201">Al seleccionar un elemento de esta lista, se abrirá un control flotante que describe el CVE.</span><span class="sxs-lookup"><span data-stu-id="a883d-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="a883d-202">KB faltantes</span><span class="sxs-lookup"><span data-stu-id="a883d-202">Missing KBs</span></span>

<span data-ttu-id="a883d-203">La ficha **KB que falta** muestra una lista de las actualizaciones de Microsoft que aún no se han aplicado al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a883d-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="a883d-204">Los "KB" en cuestión son [artículos de Knowledge Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que describen estas actualizaciones; por ejemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="a883d-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Imagen de la ficha de KB que falta para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="a883d-206">La vista predeterminada enumera el boletín que contiene las actualizaciones, la versión del sistema operativo, los productos afectados, CVE dirección, el número de KB y las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a883d-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="a883d-207">Se puede personalizar el número de elementos que se muestran por página y qué columnas se muestran.</span><span class="sxs-lookup"><span data-stu-id="a883d-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="a883d-208">Al seleccionar un elemento, se abrirá un control flotante que se vincula a la actualización.</span><span class="sxs-lookup"><span data-stu-id="a883d-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a883d-209">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a883d-209">Related topics</span></span>

* [<span data-ttu-id="a883d-210">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a883d-210">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="a883d-211">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a883d-211">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="a883d-212">Investigar entidades en dispositivos usando la respuesta activa</span><span class="sxs-lookup"><span data-stu-id="a883d-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="a883d-213">Investigación y respuesta automatizadas (AIR) en Office 365</span><span class="sxs-lookup"><span data-stu-id="a883d-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
