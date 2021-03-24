---
title: Panel de operaciones de seguridad del Centro de seguridad de Microsoft Defender
description: Use el panel para identificar dispositivos en riesgo, realizar un seguimiento del estado del servicio y ver estadísticas e información sobre dispositivos y alertas.
keywords: panel, alertas, nuevas, en curso, resuelto, riesgo, dispositivos en riesgo, infecciones, informes, estadísticas, gráficos, gráficos, estado, detecciones de malware activo, categoría de amenazas, categorías, robo de contraseñas, ransomware, exploit, amenaza, baja gravedad, malware activo
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072952"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="318c7-104">Panel de operaciones de seguridad del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="318c7-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="318c7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="318c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="318c7-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="318c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="318c7-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="318c7-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="318c7-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="318c7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="318c7-109">El **panel de operaciones de seguridad** es donde se muestra la detección de puntos de conexión y las capacidades de respuesta.</span><span class="sxs-lookup"><span data-stu-id="318c7-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="318c7-110">Proporciona una introducción de alto nivel de dónde se han visto las detecciones y resalta dónde se necesitan acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="318c7-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="318c7-111">El panel muestra una instantánea de:</span><span class="sxs-lookup"><span data-stu-id="318c7-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="318c7-112">Alertas activas</span><span class="sxs-lookup"><span data-stu-id="318c7-112">Active alerts</span></span>
- <span data-ttu-id="318c7-113">Dispositivos en riesgo</span><span class="sxs-lookup"><span data-stu-id="318c7-113">Devices at risk</span></span>
- <span data-ttu-id="318c7-114">Estado del sensor</span><span class="sxs-lookup"><span data-stu-id="318c7-114">Sensor health</span></span>
- <span data-ttu-id="318c7-115">Estado del servicio</span><span class="sxs-lookup"><span data-stu-id="318c7-115">Service health</span></span>
- <span data-ttu-id="318c7-116">Informes de dispositivos diarios</span><span class="sxs-lookup"><span data-stu-id="318c7-116">Daily devices reporting</span></span>
- <span data-ttu-id="318c7-117">Investigaciones automatizadas activas</span><span class="sxs-lookup"><span data-stu-id="318c7-117">Active automated investigations</span></span>
- <span data-ttu-id="318c7-118">Estadísticas de investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="318c7-118">Automated investigations statistics</span></span>
- <span data-ttu-id="318c7-119">Usuarios en riesgo</span><span class="sxs-lookup"><span data-stu-id="318c7-119">Users at risk</span></span>
- <span data-ttu-id="318c7-120">Actividades sospechosas</span><span class="sxs-lookup"><span data-stu-id="318c7-120">Suspicious activities</span></span>


![Imagen del panel de operaciones de seguridad](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="318c7-122">Puedes explorar e investigar alertas y dispositivos para determinar rápidamente si, dónde y cuándo se produjeron actividades sospechosas en la red para ayudarte a comprender el contexto en el que aparecieron.</span><span class="sxs-lookup"><span data-stu-id="318c7-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="318c7-123">Desde el **panel de operaciones de** seguridad verás eventos agregados para facilitar la identificación de eventos o comportamientos significativos en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="318c7-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="318c7-124">También puede profundizar en eventos granulares e indicadores de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="318c7-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="318c7-125">También tiene iconos en los que se puede hacer clic que dan indicaciones visuales sobre el estado general de mantenimiento de la organización.</span><span class="sxs-lookup"><span data-stu-id="318c7-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="318c7-126">Cada icono abre una vista detallada de la información general correspondiente.</span><span class="sxs-lookup"><span data-stu-id="318c7-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="318c7-127">Alertas activas</span><span class="sxs-lookup"><span data-stu-id="318c7-127">Active alerts</span></span>
<span data-ttu-id="318c7-128">Puede ver el número total de alertas activas de los últimos 30 días en la red desde el icono.</span><span class="sxs-lookup"><span data-stu-id="318c7-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="318c7-129">Las alertas se agrupan **en Nuevo** y **En curso.**</span><span class="sxs-lookup"><span data-stu-id="318c7-129">Alerts are grouped into **New** and **In progress**.</span></span>

![Haga clic en cada segmento o gravedad para ver una lista de alertas de los últimos 30 días](images/active-alerts-tile.png)

<span data-ttu-id="318c7-131">Cada grupo se subcategorizó aún más en sus niveles de gravedad de alerta correspondientes.</span><span class="sxs-lookup"><span data-stu-id="318c7-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="318c7-132">Haga clic en el número de alertas dentro de cada anillo de alerta para ver una vista ordenada de la cola de esa categoría (**Nuevo** **o En curso**).</span><span class="sxs-lookup"><span data-stu-id="318c7-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="318c7-133">Para obtener más información, vea [Alerts overview](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="318c7-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="318c7-134">Cada fila incluye una categoría de gravedad de alerta y una breve descripción de la alerta.</span><span class="sxs-lookup"><span data-stu-id="318c7-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="318c7-135">Puede hacer clic en una alerta para ver su vista detallada.</span><span class="sxs-lookup"><span data-stu-id="318c7-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="318c7-136">Para obtener más información, vea  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and Alerts [overview](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="318c7-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="318c7-137">Dispositivos en riesgo</span><span class="sxs-lookup"><span data-stu-id="318c7-137">Devices at risk</span></span>
<span data-ttu-id="318c7-138">Este icono muestra una lista de dispositivos con el mayor número de alertas activas.</span><span class="sxs-lookup"><span data-stu-id="318c7-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="318c7-139">El número total de alertas para cada dispositivo se muestra en un círculo junto al nombre del dispositivo y, a continuación, se clasifica por niveles de gravedad en el extremo del icono (mantenga el puntero sobre cada barra de gravedad para ver su etiqueta).</span><span class="sxs-lookup"><span data-stu-id="318c7-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![El icono Dispositivos en riesgo muestra una lista de dispositivos con el mayor número de alertas y un desglose de la gravedad de las alertas](images/devices-at-risk-tile.png)

<span data-ttu-id="318c7-141">Haz clic en el nombre del dispositivo para ver detalles sobre ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="318c7-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="318c7-142">Para obtener más información, vea [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="318c7-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="318c7-143">También puedes hacer clic en **Lista de** dispositivos en la parte superior del icono para ir directamente a la lista Dispositivos, ordenada por el número de alertas activas. </span><span class="sxs-lookup"><span data-stu-id="318c7-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="318c7-144">Para obtener más información, vea [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="318c7-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="318c7-145">Dispositivos con problemas de sensor</span><span class="sxs-lookup"><span data-stu-id="318c7-145">Devices with sensor issues</span></span>
<span data-ttu-id="318c7-146">El **icono Dispositivos con** problemas de sensor proporciona información sobre la capacidad del dispositivo individual para proporcionar datos del sensor al servicio de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="318c7-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="318c7-147">Informa de cuántos dispositivos requieren atención y le ayuda a identificar dispositivos problemáticos.</span><span class="sxs-lookup"><span data-stu-id="318c7-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![Icono dispositivos con problemas de sensor](images/atp-tile-sensor-health.png)

<span data-ttu-id="318c7-149">Hay dos indicadores de estado que proporcionan información sobre el número de dispositivos que no están informando correctamente al servicio:</span><span class="sxs-lookup"><span data-stu-id="318c7-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="318c7-150">**Mal configurados:** estos dispositivos podrían estar informando parcialmente los datos del sensor al servicio de Microsoft Defender para endpoints y podrían tener errores de configuración que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="318c7-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="318c7-151">**Inactivo:** dispositivos que han dejado de informar al servicio Microsoft Defender para endpoints durante más de siete días en el último mes.</span><span class="sxs-lookup"><span data-stu-id="318c7-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="318c7-152">Cuando hagas clic en cualquiera de los grupos, se te dirigirá a la lista de dispositivos, filtrada según tu elección.</span><span class="sxs-lookup"><span data-stu-id="318c7-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="318c7-153">Para obtener más información, vea Comprobar el [estado del sensor](check-sensor-status.md) e Investigar [dispositivos](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="318c7-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="318c7-154">Estado del servicio</span><span class="sxs-lookup"><span data-stu-id="318c7-154">Service health</span></span>
<span data-ttu-id="318c7-155">El **icono Estado** del servicio le informa si el servicio está activo o si hay problemas.</span><span class="sxs-lookup"><span data-stu-id="318c7-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![El icono Estado del servicio muestra un indicador general del servicio](images/status-tile.png)

<span data-ttu-id="318c7-157">Para obtener más información sobre el estado del servicio, vea [Check the Microsoft Defender for Endpoint service health](service-status.md).</span><span class="sxs-lookup"><span data-stu-id="318c7-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="318c7-158">Informes de dispositivos diarios</span><span class="sxs-lookup"><span data-stu-id="318c7-158">Daily devices reporting</span></span>
<span data-ttu-id="318c7-159">El **icono Informes de dispositivos** diarios muestra un gráfico de barras que representa el número de dispositivos que informan diariamente en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="318c7-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="318c7-160">Mantenga el mouse sobre barras individuales en el gráfico para ver el número exacto de dispositivos que se informan en cada día.</span><span class="sxs-lookup"><span data-stu-id="318c7-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![Imagen del icono de informes de dispositivos diarios](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="318c7-162">Investigaciones automatizadas activas</span><span class="sxs-lookup"><span data-stu-id="318c7-162">Active automated investigations</span></span>
<span data-ttu-id="318c7-163">Puede ver el número total de investigaciones automatizadas de los últimos 30 días en la red desde el icono **Investigaciones automatizadas activas.**</span><span class="sxs-lookup"><span data-stu-id="318c7-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="318c7-164">Las investigaciones se agrupan en **Pending action**, **Waiting for device** y **Running**.</span><span class="sxs-lookup"><span data-stu-id="318c7-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![Inmaage of active automated investigations](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="318c7-166">Estadísticas de investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="318c7-166">Automated investigations statistics</span></span>
<span data-ttu-id="318c7-167">Este icono muestra estadísticas relacionadas con investigaciones automatizadas en los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="318c7-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="318c7-168">Muestra el número de investigaciones completadas, el número de investigaciones correctamente subsanadas, el promedio de tiempo pendiente que tarda en iniciarse una investigación, el tiempo promedio que se tarda en corregir una alerta, el número de alertas investigadas y el número de horas de automatización guardadas de una investigación manual típica.</span><span class="sxs-lookup"><span data-stu-id="318c7-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![Imagen de las estadísticas de investigaciones automatizadas](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="318c7-170">Puede hacer clic en **Investigaciones automatizadas,** Investigaciones **subsanadas** y Alertas investigadas para navegar a la página **Investigaciones,** filtrada por la categoría correspondiente. </span><span class="sxs-lookup"><span data-stu-id="318c7-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="318c7-171">Esto le permite ver un desglose detallado de las investigaciones en contexto.</span><span class="sxs-lookup"><span data-stu-id="318c7-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="318c7-172">Usuarios en riesgo</span><span class="sxs-lookup"><span data-stu-id="318c7-172">Users at risk</span></span>
<span data-ttu-id="318c7-173">El icono muestra una lista de cuentas de usuario con las alertas más activas y el número de alertas vistas en alertas altas, medianas o bajas.</span><span class="sxs-lookup"><span data-stu-id="318c7-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![El icono Cuentas de usuario en riesgo muestra una lista de cuentas de usuario con el mayor número de alertas y un desglose de la gravedad de las alertas](images/atp-users-at-risk.png)

<span data-ttu-id="318c7-175">Haga clic en la cuenta de usuario para ver detalles sobre la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="318c7-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="318c7-176">Para obtener más información, [vea Investigar una cuenta de usuario](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="318c7-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="318c7-177">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="318c7-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="318c7-178">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="318c7-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="318c7-179">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="318c7-179">Related topics</span></span>
- [<span data-ttu-id="318c7-180">Comprender el portal de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="318c7-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="318c7-181">Introducción al portal</span><span class="sxs-lookup"><span data-stu-id="318c7-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="318c7-182">Ver el panel de administración & vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="318c7-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="318c7-183">Ver el panel análisis de amenazas y realizar acciones de mitigación recomendadas</span><span class="sxs-lookup"><span data-stu-id="318c7-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
