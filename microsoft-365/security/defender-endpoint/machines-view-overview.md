---
title: Ver y organizar la lista de dispositivos de Microsoft Defender para endpoints
description: Obtenga información sobre las características disponibles que puede usar en la lista dispositivos, como ordenar, filtrar y exportar la lista para mejorar las investigaciones.
keywords: sort, filter, export, csv, device name, domain, last seen, internal IP, health state, active alerts, active malware detections, threat category, review alerts, network, connection, malware, type, password stealer, ransomware, exploit, threat, general malware, unwanted software
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a031a35929f319e87a9ad1a9ca48d6bf95a3ef72
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861580"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="7cc83-104">Ver y organizar la lista de Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7cc83-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7cc83-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7cc83-105">**Applies to:**</span></span>
- [<span data-ttu-id="7cc83-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7cc83-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7cc83-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7cc83-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7cc83-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7cc83-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7cc83-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7cc83-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="7cc83-110">La **lista Dispositivos** muestra una lista de los dispositivos de la red donde se generaron alertas.</span><span class="sxs-lookup"><span data-stu-id="7cc83-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="7cc83-111">De forma predeterminada, la cola muestra los dispositivos vistos en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="7cc83-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="7cc83-112">De un vistazo verá información como dominio, nivel de riesgo, plataforma del sistema operativo y otros detalles para facilitar la identificación de los dispositivos más en riesgo.</span><span class="sxs-lookup"><span data-stu-id="7cc83-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="7cc83-113">Hay varias opciones entre las que puedes elegir para personalizar la vista de lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7cc83-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="7cc83-114">En la navegación superior puede:</span><span class="sxs-lookup"><span data-stu-id="7cc83-114">On the top navigation you can:</span></span>

- <span data-ttu-id="7cc83-115">Agregar o quitar columnas</span><span class="sxs-lookup"><span data-stu-id="7cc83-115">Add or remove columns</span></span>
- <span data-ttu-id="7cc83-116">Exportar toda la lista en formato CSV</span><span class="sxs-lookup"><span data-stu-id="7cc83-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="7cc83-117">Seleccionar el número de elementos que se mostrarán por página</span><span class="sxs-lookup"><span data-stu-id="7cc83-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="7cc83-118">Aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="7cc83-118">Apply filters</span></span>

<span data-ttu-id="7cc83-119">Durante el proceso de incorporación, la lista **de** dispositivos se rellena gradualmente con dispositivos a medida que comienzan a informar de los datos del sensor.</span><span class="sxs-lookup"><span data-stu-id="7cc83-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="7cc83-120">Use esta vista para realizar un seguimiento de los puntos de conexión incorporados a medida que se en línea o descargue la lista completa de puntos de conexión como un archivo CSV para el análisis sin conexión.</span><span class="sxs-lookup"><span data-stu-id="7cc83-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="7cc83-121">Si exportas la lista de dispositivos, contendrá todos los dispositivos de tu organización.</span><span class="sxs-lookup"><span data-stu-id="7cc83-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="7cc83-122">Puede tardar mucho tiempo en descargarse, según el tamaño de la organización.</span><span class="sxs-lookup"><span data-stu-id="7cc83-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="7cc83-123">Al exportar la lista en formato CSV, se muestran los datos sin filtrar.</span><span class="sxs-lookup"><span data-stu-id="7cc83-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="7cc83-124">El archivo CSV incluirá todos los dispositivos de la organización, independientemente de cualquier filtrado aplicado en la vista en sí.</span><span class="sxs-lookup"><span data-stu-id="7cc83-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![Imagen de la lista de dispositivos con lista de dispositivos](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="7cc83-126">Ordenar y filtrar la lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="7cc83-126">Sort and filter the device list</span></span>

<span data-ttu-id="7cc83-127">Puede aplicar los siguientes filtros para limitar la lista de alertas y obtener una vista más centrada.</span><span class="sxs-lookup"><span data-stu-id="7cc83-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="7cc83-128">Nivel de riesgo</span><span class="sxs-lookup"><span data-stu-id="7cc83-128">Risk level</span></span>

<span data-ttu-id="7cc83-129">El nivel de riesgo refleja la evaluación general del riesgo del dispositivo en función de una combinación de factores, incluidos los tipos y la gravedad de las alertas activas en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7cc83-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="7cc83-130">Resolver alertas activas, aprobar actividades de corrección y suprimir alertas posteriores puede reducir el nivel de riesgo.</span><span class="sxs-lookup"><span data-stu-id="7cc83-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="7cc83-131">Nivel de exposición</span><span class="sxs-lookup"><span data-stu-id="7cc83-131">Exposure level</span></span>

<span data-ttu-id="7cc83-132">El nivel de exposición refleja la exposición actual del dispositivo en función del impacto acumulado de sus recomendaciones de seguridad pendientes.</span><span class="sxs-lookup"><span data-stu-id="7cc83-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="7cc83-133">Los niveles posibles son bajos, medianos y altos.</span><span class="sxs-lookup"><span data-stu-id="7cc83-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="7cc83-134">Una exposición baja significa que los dispositivos son menos vulnerables a la explotación.</span><span class="sxs-lookup"><span data-stu-id="7cc83-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="7cc83-135">Si el nivel de exposición indica "No hay datos disponibles", hay algunas razones por las que esto puede ser así:</span><span class="sxs-lookup"><span data-stu-id="7cc83-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="7cc83-136">El dispositivo dejó de informar durante más de 30 días; en ese caso, se considera inactivo y no se calcula la exposición</span><span class="sxs-lookup"><span data-stu-id="7cc83-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="7cc83-137">Sistema operativo de dispositivo no compatible: consulta [requisitos mínimos para Microsoft Defender para endpoint](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="7cc83-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="7cc83-138">Dispositivo con agente obsoleto (muy poco probable)</span><span class="sxs-lookup"><span data-stu-id="7cc83-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="7cc83-139">Plataforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7cc83-139">OS Platform</span></span>

<span data-ttu-id="7cc83-140">Seleccione solo las plataformas del sistema operativo que le interesa investigar.</span><span class="sxs-lookup"><span data-stu-id="7cc83-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="7cc83-141">Estado</span><span class="sxs-lookup"><span data-stu-id="7cc83-141">Health state</span></span>

<span data-ttu-id="7cc83-142">Filtre por los siguientes estados de estado del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7cc83-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="7cc83-143">**Activo:** dispositivos que informan activamente de los datos del sensor al servicio.</span><span class="sxs-lookup"><span data-stu-id="7cc83-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="7cc83-144">**Inactivo:** dispositivos que han dejado de enviar señales por completo durante más de 7 días.</span><span class="sxs-lookup"><span data-stu-id="7cc83-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="7cc83-145">**Configuración errónea: dispositivos** que tienen comunicaciones deficientes con el servicio o que no pueden enviar datos del sensor.</span><span class="sxs-lookup"><span data-stu-id="7cc83-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="7cc83-146">Los dispositivos mal configurados se pueden clasificar en:</span><span class="sxs-lookup"><span data-stu-id="7cc83-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="7cc83-147">Sin datos del sensor</span><span class="sxs-lookup"><span data-stu-id="7cc83-147">No sensor data</span></span>
  - <span data-ttu-id="7cc83-148">Comunicaciones deficientes</span><span class="sxs-lookup"><span data-stu-id="7cc83-148">Impaired communications</span></span>

  <span data-ttu-id="7cc83-149">Para obtener más información sobre cómo solucionar problemas en dispositivos mal configurados, consulte [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span><span class="sxs-lookup"><span data-stu-id="7cc83-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="7cc83-150">Estado del antivirus</span><span class="sxs-lookup"><span data-stu-id="7cc83-150">Antivirus status</span></span>

<span data-ttu-id="7cc83-151">Filtrar dispositivos por estado antivirus.</span><span class="sxs-lookup"><span data-stu-id="7cc83-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="7cc83-152">Solo se aplica a dispositivos Windows 10 activos.</span><span class="sxs-lookup"><span data-stu-id="7cc83-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="7cc83-153">**Deshabilitado:** la protección contra & virus está desactivada.</span><span class="sxs-lookup"><span data-stu-id="7cc83-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="7cc83-154">**Not reporting:** la protección contra & amenazas de virus no está informando.</span><span class="sxs-lookup"><span data-stu-id="7cc83-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="7cc83-155">**No actualizado:** la protección contra & virus no está actualizada.</span><span class="sxs-lookup"><span data-stu-id="7cc83-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="7cc83-156">Para obtener más información, [vea View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span><span class="sxs-lookup"><span data-stu-id="7cc83-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="7cc83-157">Estado de mitigación de amenazas</span><span class="sxs-lookup"><span data-stu-id="7cc83-157">Threat mitigation status</span></span>

<span data-ttu-id="7cc83-158">Para ver los dispositivos que pueden verse afectados por una amenaza determinada, selecciona la amenaza en el menú desplegable y, a continuación, selecciona qué aspecto de vulnerabilidad debe mitigarse.</span><span class="sxs-lookup"><span data-stu-id="7cc83-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="7cc83-159">Para obtener más información sobre determinadas amenazas, consulte [Análisis de amenazas.](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="7cc83-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="7cc83-160">Para obtener información sobre mitigación, [vea Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="7cc83-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="7cc83-161">Versión de Windows 10</span><span class="sxs-lookup"><span data-stu-id="7cc83-161">Windows 10 version</span></span>

<span data-ttu-id="7cc83-162">Selecciona solo las versiones de Windows 10 que te interesan investigar.</span><span class="sxs-lookup"><span data-stu-id="7cc83-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="7cc83-163">Etiquetas & grupos</span><span class="sxs-lookup"><span data-stu-id="7cc83-163">Tags & Groups</span></span>

<span data-ttu-id="7cc83-164">Filtre la lista en función de la agrupación y el etiquetado que haya agregado a dispositivos individuales.</span><span class="sxs-lookup"><span data-stu-id="7cc83-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="7cc83-165">Consulta [Crear y administrar etiquetas de dispositivo](machine-tags.md) y Crear y administrar grupos de [dispositivos.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="7cc83-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7cc83-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7cc83-166">Related topics</span></span>

- [<span data-ttu-id="7cc83-167">Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7cc83-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
