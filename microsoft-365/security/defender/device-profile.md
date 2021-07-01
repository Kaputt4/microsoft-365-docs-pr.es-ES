---
title: Perfil de dispositivo en Microsoft 365 de seguridad
description: Ver los niveles de riesgo y exposición de un dispositivo de la organización. Analiza las amenazas pasadas y actuales y protege el dispositivo con las actualizaciones más recientes.
keywords: seguridad, malware, Microsoft 365, M365, Microsoft 365 Defender, centro de seguridad, Microsoft Defender para endpoint, Microsoft Defender para Office 365, Microsoft Defender para la identidad, página del dispositivo, perfil de dispositivo, página de máquina, perfil de máquina
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 47b25ba541264d79216748753e9f41fb7435fc10
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229484"
---
# <a name="device-profile-page"></a><span data-ttu-id="98de1-105">Página de perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="98de1-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="98de1-106">El Microsoft 365 de seguridad le proporciona páginas de perfil de dispositivo para que pueda evaluar rápidamente el estado y el estado de los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="98de1-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98de1-107">La página de perfil de dispositivo puede parecer ligeramente diferente, en función de si el dispositivo está inscrito en Microsoft Defender para Endpoint, Microsoft Defender para Identity o en ambos.</span><span class="sxs-lookup"><span data-stu-id="98de1-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="98de1-108">Si el dispositivo está inscrito en Microsoft Defender para Endpoint, también puedes usar la página de perfil de dispositivo para realizar algunas tareas de seguridad comunes.</span><span class="sxs-lookup"><span data-stu-id="98de1-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="98de1-109">Navegar por la página de perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="98de1-109">Navigating the device profile page</span></span>

<span data-ttu-id="98de1-110">La página de perfil se divide en varias secciones generales.</span><span class="sxs-lookup"><span data-stu-id="98de1-110">The profile page is broken up into several broad sections.</span></span>

![Imagen de la página de perfil de dispositivo con (1) área de pestaña (2) Barra lateral y (3) Acciones resaltadas en rojo](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="98de1-112">En la barra lateral (1) se enumeran los detalles básicos sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="98de1-113">El área de contenido principal (2) contiene pestañas que puedes alternar para ver diferentes tipos de información sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="98de1-114">Si el dispositivo está inscrito en Microsoft Defender para Endpoint, también verás una lista de acciones de respuesta (3).</span><span class="sxs-lookup"><span data-stu-id="98de1-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="98de1-115">Las acciones de respuesta permiten realizar tareas comunes relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="98de1-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="98de1-116">Barra lateral</span><span class="sxs-lookup"><span data-stu-id="98de1-116">Sidebar</span></span>

<span data-ttu-id="98de1-117">Junto al área de contenido principal de la página de perfil de dispositivo se encuentra la barra lateral.</span><span class="sxs-lookup"><span data-stu-id="98de1-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Imagen de la pestaña de la barra lateral para el perfil del dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="98de1-119">En la barra lateral se muestra el nombre completo y el nivel de exposición del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="98de1-120">También proporciona información básica importante en subsecciones pequeñas que se pueden alternar abiertas o cerradas, como:</span><span class="sxs-lookup"><span data-stu-id="98de1-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="98de1-121">**Etiquetas:** cualquier Microsoft Defender para endpoint, Microsoft Defender para Identity o etiquetas personalizadas asociadas con el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="98de1-122">Las etiquetas de Microsoft Defender para Identity no son editables.</span><span class="sxs-lookup"><span data-stu-id="98de1-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="98de1-123">**Información de seguridad:** abre incidentes y alertas activas.</span><span class="sxs-lookup"><span data-stu-id="98de1-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="98de1-124">Los dispositivos inscritos en Microsoft Defender para Endpoint también mostrarán el nivel de exposición y el nivel de riesgo.</span><span class="sxs-lookup"><span data-stu-id="98de1-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="98de1-125">El nivel de exposición se refiere a cuánto cumple el dispositivo con las recomendaciones de seguridad, mientras que el nivel de riesgo se calcula en función de una serie de factores, incluidos los tipos y la gravedad de las alertas activas.</span><span class="sxs-lookup"><span data-stu-id="98de1-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="98de1-126">**Detalles del dispositivo:** dominio, sistema operativo, marca de tiempo para cuando se vio por primera vez el dispositivo, direcciones IP, recursos.</span><span class="sxs-lookup"><span data-stu-id="98de1-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="98de1-127">Los dispositivos inscritos en Microsoft Defender para endpoint también muestran el estado de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="98de1-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="98de1-128">Los dispositivos inscritos en Microsoft Defender para Identity mostrarán el nombre SAM y una marca de tiempo para cuando se creó el dispositivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="98de1-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="98de1-129">**Actividad de red:** marcas de tiempo por primera vez y por última vez que se vio el dispositivo en la red.</span><span class="sxs-lookup"><span data-stu-id="98de1-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="98de1-130">**Datos de directorio** (*solo para dispositivos* inscritos en Microsoft Defender para identidad ) : marcas [UAC,](/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN y](/windows/win32/ad/service-principal-names)pertenencias a grupos.</span><span class="sxs-lookup"><span data-stu-id="98de1-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="98de1-131">Acciones de respuesta</span><span class="sxs-lookup"><span data-stu-id="98de1-131">Response actions</span></span>

<span data-ttu-id="98de1-132">Las acciones de respuesta ofrecen una forma rápida de defenderse y analizar las amenazas.</span><span class="sxs-lookup"><span data-stu-id="98de1-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Imagen de la barra de acciones para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="98de1-134">[Las acciones de](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) respuesta solo están disponibles si el dispositivo está inscrito en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="98de1-134">[Response actions](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="98de1-135">Los dispositivos inscritos en Microsoft Defender para Endpoint pueden mostrar diferentes números de acciones de respuesta, según el sistema operativo y el número de versión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="98de1-136">Las acciones disponibles en la página de perfil de dispositivo incluyen:</span><span class="sxs-lookup"><span data-stu-id="98de1-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="98de1-137">**Administrar etiquetas:** actualiza las etiquetas personalizadas que has aplicado a este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="98de1-138">**Aislar dispositivo:** aísla el dispositivo de la red de su organización mientras lo mantiene conectado a Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="98de1-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="98de1-139">Puedes elegir permitir que Outlook, Teams y Skype Empresarial se ejecuten mientras el dispositivo está aislado, con fines de comunicación.</span><span class="sxs-lookup"><span data-stu-id="98de1-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="98de1-140">**Centro de acciones:** ver el estado de las acciones enviadas.</span><span class="sxs-lookup"><span data-stu-id="98de1-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="98de1-141">Solo está disponible si ya se ha seleccionado otra acción.</span><span class="sxs-lookup"><span data-stu-id="98de1-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="98de1-142">**Restringir la ejecución de** aplicaciones: impide que se ejecuten aplicaciones que no están firmadas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98de1-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="98de1-143">**Ejecutar examen antivirus:** actualiza Antivirus de Windows Defender definiciones e inmediatamente ejecuta un examen antivirus.</span><span class="sxs-lookup"><span data-stu-id="98de1-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="98de1-144">Elija entre Examen rápido o Examen completo.</span><span class="sxs-lookup"><span data-stu-id="98de1-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="98de1-145">**Recopilar paquete de investigación:** recopila información sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="98de1-146">Cuando se complete la investigación, puede descargarla.</span><span class="sxs-lookup"><span data-stu-id="98de1-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="98de1-147">**Iniciar sesión de respuesta en directo:** carga un shell remoto en el dispositivo para investigaciones [de seguridad en profundidad.](/microsoft-365/security/defender-endpoint/live-response)</span><span class="sxs-lookup"><span data-stu-id="98de1-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](/microsoft-365/security/defender-endpoint/live-response).</span></span>
* <span data-ttu-id="98de1-148">**Iniciar investigación automatizada:** investiga y corrige automáticamente [las amenazas.](../office-365-security/office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="98de1-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](../office-365-security/office-365-air.md).</span></span> <span data-ttu-id="98de1-149">Aunque puede activar manualmente las investigaciones automatizadas para que se ejecuten desde esta [página,](../../compliance/alert-policies.md#default-alert-policies) determinadas directivas de alerta desencadenan investigaciones automáticas por sí solas.</span><span class="sxs-lookup"><span data-stu-id="98de1-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](../../compliance/alert-policies.md#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="98de1-150">**Centro de acciones:** muestra información sobre las acciones de respuesta que se están ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="98de1-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="98de1-151">Sección Tabulaciones</span><span class="sxs-lookup"><span data-stu-id="98de1-151">Tabs section</span></span>

<span data-ttu-id="98de1-152">Las pestañas de perfil de dispositivo te permiten alternar entre una introducción a los detalles de seguridad sobre el dispositivo y tablas que contienen una lista de alertas.</span><span class="sxs-lookup"><span data-stu-id="98de1-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="98de1-153">Los dispositivos inscritos en Microsoft Defender para endpoint también mostrarán pestañas que incluyen una escala de tiempo, una lista de recomendaciones de seguridad, un inventario de software, una lista de vulnerabilidades detectadas y KBs ausentes (actualizaciones de seguridad).</span><span class="sxs-lookup"><span data-stu-id="98de1-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="98de1-154">Ficha Información general</span><span class="sxs-lookup"><span data-stu-id="98de1-154">Overview tab</span></span>

<span data-ttu-id="98de1-155">La pestaña predeterminada es **Overview**.</span><span class="sxs-lookup"><span data-stu-id="98de1-155">The default tab is **Overview**.</span></span> <span data-ttu-id="98de1-156">Proporciona un vistazo rápido al hecho de seguridad más importante sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-156">It provides a quick look at the most important security fact about the device.</span></span>

![Imagen de la pestaña información general del perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="98de1-158">Aquí puedes ver rápidamente las alertas activas del dispositivo y los usuarios que han iniciado sesión actualmente.</span><span class="sxs-lookup"><span data-stu-id="98de1-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="98de1-159">Si el dispositivo está inscrito en Microsoft Defender para Endpoint, también verás el nivel de riesgo del dispositivo y los datos disponibles en las evaluaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="98de1-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="98de1-160">Las evaluaciones de seguridad describen el nivel de exposición del dispositivo, proporcionan recomendaciones de seguridad y enumeran el software afectado y las vulnerabilidades detectadas.</span><span class="sxs-lookup"><span data-stu-id="98de1-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="98de1-161">Ficha Alertas</span><span class="sxs-lookup"><span data-stu-id="98de1-161">Alerts tab</span></span>

<span data-ttu-id="98de1-162">La **pestaña** Alertas contiene una lista de alertas que se han elevado en el dispositivo, tanto de Microsoft Defender para Identity como de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="98de1-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Imagen de la pestaña alertas para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="98de1-164">Puede personalizar el número de elementos que se muestran, así como las columnas que se muestran para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="98de1-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="98de1-165">El comportamiento predeterminado es enumerar treinta elementos por página.</span><span class="sxs-lookup"><span data-stu-id="98de1-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="98de1-166">Las columnas de esta pestaña incluyen información sobre la gravedad de la amenaza que desencadenó la alerta, así como el estado, el estado de investigación y a quién se asignó la alerta.</span><span class="sxs-lookup"><span data-stu-id="98de1-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="98de1-167">La *columna entidades afectadas* hace referencia al dispositivo (entidad) cuyo perfil está viendo actualmente, además de cualquier otro dispositivo de la red que se vea afectado.</span><span class="sxs-lookup"><span data-stu-id="98de1-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="98de1-168">Si selecciona un elemento de esta lista, se abrirá un menú desplegable que contiene aún más información sobre la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98de1-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="98de1-169">Esta lista se puede filtrar por gravedad, estado o a quién se ha asignado la alerta.</span><span class="sxs-lookup"><span data-stu-id="98de1-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="98de1-170">Pestaña Escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="98de1-170">Timeline tab</span></span>

<span data-ttu-id="98de1-171">La **pestaña Escala** de tiempo incluye un gráfico cronológico interactivo de todos los eventos que se han producido en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="98de1-172">Al mover el área resaltada del gráfico a la izquierda o a la derecha, puede ver eventos durante diferentes períodos de tiempo.</span><span class="sxs-lookup"><span data-stu-id="98de1-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="98de1-173">También puede elegir un intervalo personalizado de fechas en el menú desplegable entre el gráfico interactivo y la lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="98de1-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="98de1-174">Debajo del gráfico hay una lista de eventos para el intervalo de fechas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="98de1-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Imagen de la pestaña escala de tiempo para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="98de1-176">El número de elementos que se muestran y las columnas de la lista se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="98de1-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="98de1-177">Las columnas predeterminadas muestran la hora del evento, el usuario activo, el tipo de acción, las entidades (procesos) y la información adicional sobre el evento.</span><span class="sxs-lookup"><span data-stu-id="98de1-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="98de1-178">Al seleccionar un elemento de esta lista, se abrirá un control desplegable que muestra un gráfico de entidades de evento, que muestra los procesos primarios y secundarios implicados en el evento.</span><span class="sxs-lookup"><span data-stu-id="98de1-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="98de1-179">La lista se puede filtrar por el tipo específico de evento; por ejemplo, eventos del Registro o Eventos de pantalla inteligente.</span><span class="sxs-lookup"><span data-stu-id="98de1-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="98de1-180">La lista también se puede exportar a un archivo CSV, para su descarga.</span><span class="sxs-lookup"><span data-stu-id="98de1-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="98de1-181">Aunque el archivo no está limitado por el número de eventos, el intervalo de tiempo máximo que puede elegir exportar es de siete días.</span><span class="sxs-lookup"><span data-stu-id="98de1-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="98de1-182">Pestaña Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="98de1-182">Security recommendations tab</span></span>

<span data-ttu-id="98de1-183">En **la pestaña Recomendaciones de** seguridad se enumeran las acciones que puedes realizar para proteger el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="98de1-184">Si selecciona un elemento en esta lista, se abrirá un menú desplegable donde podrá obtener instrucciones sobre cómo aplicar la recomendación.</span><span class="sxs-lookup"><span data-stu-id="98de1-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Imagen de la pestaña recomendaciones de seguridad para el perfil del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="98de1-186">Al igual que con las pestañas anteriores, se puede personalizar el número de elementos que se muestran por página, así como las columnas visibles.</span><span class="sxs-lookup"><span data-stu-id="98de1-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="98de1-187">La vista predeterminada incluye columnas que detallan las debilidades de seguridad abordadas, la amenaza asociada, el componente relacionado o el software afectado por la amenaza, y mucho más.</span><span class="sxs-lookup"><span data-stu-id="98de1-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="98de1-188">Los elementos se pueden filtrar por el estado de la recomendación.</span><span class="sxs-lookup"><span data-stu-id="98de1-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="98de1-189">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="98de1-189">Software inventory</span></span>

<span data-ttu-id="98de1-190">La **pestaña Inventario de** software muestra el software instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Imagen de la pestaña de inventario de software para el perfil del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="98de1-192">La vista predeterminada muestra el proveedor de software, el número de versión instalada, el número de debilidades de software conocidas, las perspectivas de amenazas, el código del producto y las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="98de1-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="98de1-193">El número de elementos que se muestran y las columnas que se muestran se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="98de1-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="98de1-194">Al seleccionar un elemento de esta lista, se abre un desplegable que contiene más detalles sobre el software seleccionado, así como la ruta de acceso y la marca de tiempo de la última vez que se encontró el software.</span><span class="sxs-lookup"><span data-stu-id="98de1-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="98de1-195">Esta lista se puede filtrar por código de producto.</span><span class="sxs-lookup"><span data-stu-id="98de1-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="98de1-196">Pestaña Vulnerabilidades detectadas</span><span class="sxs-lookup"><span data-stu-id="98de1-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="98de1-197">En **la pestaña Vulnerabilidades detectadas** se enumeran las vulnerabilidades y vulnerabilidades comunes (CVEs) que pueden afectar al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Imagen de la pestaña vulnerabilidades detectadas para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="98de1-199">La vista predeterminada enumera la gravedad de CVE, la puntuación de vulnerabilidad común (CVS), el software relacionado con CVE, cuando se publicó la CVE, cuando se actualizó por última vez la CVE y las amenazas asociadas con la CVE.</span><span class="sxs-lookup"><span data-stu-id="98de1-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="98de1-200">Al igual que con las pestañas anteriores, se puede personalizar el número de elementos mostrados y las columnas visibles.</span><span class="sxs-lookup"><span data-stu-id="98de1-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="98de1-201">Si selecciona un elemento de esta lista, se abrirá un desplegable que describe la CVE.</span><span class="sxs-lookup"><span data-stu-id="98de1-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="98de1-202">Faltan KBs</span><span class="sxs-lookup"><span data-stu-id="98de1-202">Missing KBs</span></span>

<span data-ttu-id="98de1-203">En **la pestaña KBs que** faltan se enumeran las actualizaciones de Microsoft que aún no se han aplicado al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98de1-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="98de1-204">Los "KBs" en cuestión son [artículos de Knowledge Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que describen estas actualizaciones; por ejemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="98de1-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Imagen de la pestaña kbs que falta para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="98de1-206">La vista predeterminada enumera el boletín que contiene las actualizaciones, la versión del sistema operativo, los productos afectados, las CVE dirigidas, el número KB y las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="98de1-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="98de1-207">El número de elementos que se muestran por página y las columnas que se muestran se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="98de1-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="98de1-208">Al seleccionar un elemento, se abrirá un desplegable que vincula a la actualización.</span><span class="sxs-lookup"><span data-stu-id="98de1-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="98de1-209">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="98de1-209">Related topics</span></span>

* [<span data-ttu-id="98de1-210">Microsoft 365 Defender introducción</span><span class="sxs-lookup"><span data-stu-id="98de1-210">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
* [<span data-ttu-id="98de1-211">Activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98de1-211">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
* [<span data-ttu-id="98de1-212">Investigar entidades en dispositivos con respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="98de1-212">Investigate entities on devices, using live response</span></span>](../defender-endpoint/live-response.md)
* [<span data-ttu-id="98de1-213">Investigación y respuesta automatizadas (AIR) en Office 365</span><span class="sxs-lookup"><span data-stu-id="98de1-213">Automated investigation and response (AIR) in Office 365</span></span>](../office-365-security/office-365-air.md)
