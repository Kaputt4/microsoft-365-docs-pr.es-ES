---
title: Información de la red de 365 de Microsoft (versión preliminar)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Información de la red de 365 de Microsoft (versión preliminar)
ms.openlocfilehash: 682c888fefb9bec9725e470d62019c857fc2de07
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171343"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="ebf04-103">Información de la red de 365 de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ebf04-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="ebf04-104">**Network Insights** son métricas de rendimiento que recopila el inquilino de Microsoft 365 y que solo pueden ver los usuarios administrativos de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ebf04-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="ebf04-105">La información se muestra en el centro de administración de Microsoft 365 en <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="ebf04-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="ebf04-106">La información está destinada a ayudar en el diseño de perímetros de red para sus ubicaciones de oficina.</span><span class="sxs-lookup"><span data-stu-id="ebf04-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="ebf04-107">Cada conocimiento proporciona detalles sobre las características de rendimiento de un problema común específico para cada ubicación geográfica en la que los usuarios obtienen acceso a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="ebf04-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="ebf04-108">Hay seis opciones de red específicas que pueden mostrarse para cada ubicación de la oficina:</span><span class="sxs-lookup"><span data-stu-id="ebf04-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="ebf04-109">Salida de red en recorrido</span><span class="sxs-lookup"><span data-stu-id="ebf04-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="ebf04-110">Se ha detectado un mejor rendimiento para los clientes cercanos</span><span class="sxs-lookup"><span data-stu-id="ebf04-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="ebf04-111">Uso de una puerta principal no óptima del servicio de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ebf04-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="ebf04-112">Uso de puerta frontal del servicio de SharePoint Online no óptimo</span><span class="sxs-lookup"><span data-stu-id="ebf04-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="ebf04-113">Velocidad de descarga baja desde la puerta frontal de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ebf04-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="ebf04-114">Salida de red óptima de usuario de China</span><span class="sxs-lookup"><span data-stu-id="ebf04-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="ebf04-115">Hay dos información sobre la red de nivel de inquilino que puede mostrarse para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="ebf04-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="ebf04-116">También aparecen en las páginas de puntuación de producvitivy:</span><span class="sxs-lookup"><span data-stu-id="ebf04-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="ebf04-117">Conexiones de ejemplo de Exchange afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="ebf04-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="ebf04-118">Conexiones de muestreo de SharePoint afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="ebf04-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="ebf04-119">Información sobre la red, recomendaciones de rendimiento y evaluaciones en el centro de administración de Microsoft 365 se encuentra actualmente en estado de versión preliminar y solo está disponible para los inquilinos de Microsoft 365 que se han inscrito en el programa de vista previa de características.</span><span class="sxs-lookup"><span data-stu-id="ebf04-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="ebf04-120">Salida de red en recorrido</span><span class="sxs-lookup"><span data-stu-id="ebf04-120">Backhauled network egress</span></span>

<span data-ttu-id="ebf04-121">Esta información se mostrará si el servicio de Network Insights detecta que la distancia desde una ubicación de usuario determinada a la red de salida es superior a 500 millas (800 kilómetros), lo que indica que el tráfico de Microsoft 365 se está reteniendo en un dispositivo perimetral de Internet o proxy común.</span><span class="sxs-lookup"><span data-stu-id="ebf04-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="ebf04-122">Esta información se abrevia como "salida" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ebf04-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Salida de red en recorrido](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ebf04-124">Escenario</span><span class="sxs-lookup"><span data-stu-id="ebf04-124">What does this mean?</span></span>

<span data-ttu-id="ebf04-125">Esto identifica que la distancia entre la ubicación de la oficina y la red de salida es de más de 500 millas (800 kilómetros).</span><span class="sxs-lookup"><span data-stu-id="ebf04-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="ebf04-126">La ubicación de la oficina se identifica con una ubicación de equipo cliente confusa y la ubicación de salida de red se identifica con las bases de datos dirección IP inversa para la ubicación.</span><span class="sxs-lookup"><span data-stu-id="ebf04-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="ebf04-127">La ubicación de la oficina puede no ser exacta si servicios de ubicación de Windows está deshabilitado en los equipos.</span><span class="sxs-lookup"><span data-stu-id="ebf04-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="ebf04-128">La ubicación de salida de red puede ser inexacta si la información de la base de datos de direcciones IP inversas no es exacta.</span><span class="sxs-lookup"><span data-stu-id="ebf04-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="ebf04-129">Los detalles de esta visión incluyen la ubicación de la oficina, el porcentaje estimado del usuario total del inquilino en la ubicación, la ubicación de salida actual de la red, la relevancia de la ubicación de salida, la distancia entre la ubicación y el punto de salida actual, la fecha en que se detectó la condición por primera vez y la fecha en que se resolvió la condición.</span><span class="sxs-lookup"><span data-stu-id="ebf04-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ebf04-130">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ebf04-130">What should I do?</span></span>

<span data-ttu-id="ebf04-131">Para esta idea, recomendamos que se acerque la salida de red a la ubicación de la oficina para que la conectividad pueda enrutarse de forma óptima a la red global de Microsoft y a la puerta frontal del servicio Microsoft 365 más cercana.</span><span class="sxs-lookup"><span data-stu-id="ebf04-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="ebf04-132">Dejar la red cercana a los usuarios las ubicaciones de Office también permiten un mejor rendimiento en el futuro, ya que Microsoft expande tanto los puntos de presencia de red como las puertas frontales del servicio 365 de Microsoft en el futuro.</span><span class="sxs-lookup"><span data-stu-id="ebf04-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="ebf04-133">Para obtener más información acerca de cómo resolver este problema, vea [conexiones de red de salida de forma local](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) en los principios de conectividad de red de [Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="ebf04-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="ebf04-134">Se ha detectado un mejor rendimiento para los clientes cercanos</span><span class="sxs-lookup"><span data-stu-id="ebf04-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="ebf04-135">Esta información se mostrará si el servicio de Network Insights detecta que un número importante de clientes en el área metropolitana tiene mejor rendimiento que los usuarios de la organización en esta ubicación de la oficina.</span><span class="sxs-lookup"><span data-stu-id="ebf04-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="ebf04-136">Esta información se abrevia como "homólogos" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ebf04-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Rendimiento de red relativo](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ebf04-138">Escenario</span><span class="sxs-lookup"><span data-stu-id="ebf04-138">What does this mean?</span></span>

<span data-ttu-id="ebf04-139">Esta visión examina el rendimiento agregado de los clientes de Microsoft 365 en la misma ciudad que esta ubicación de la oficina.</span><span class="sxs-lookup"><span data-stu-id="ebf04-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="ebf04-140">Esta información se muestra si el promedio de latencia de los usuarios es un 10% mayor que la latencia media de los inquilinos vecinos.</span><span class="sxs-lookup"><span data-stu-id="ebf04-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ebf04-141">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ebf04-141">What should I do?</span></span>

<span data-ttu-id="ebf04-142">Puede haber muchas razones para esta condición, como la latencia en la red corporativa o los problemas de diseño de la arquitectura o del ISP, o los cuellos de botella.</span><span class="sxs-lookup"><span data-stu-id="ebf04-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="ebf04-143">Examine la latencia entre cada salto en la ruta entre la red de la oficina y la puerta de frontal de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebf04-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="ebf04-144">Para obtener más información, consulte [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="ebf04-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="ebf04-145">Uso de una puerta principal no óptima del servicio de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ebf04-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="ebf04-146">Esta información se mostrará si el servicio de Network Insights detecta que los usuarios de una ubicación específica no se conectan a una puerta de enlace de servicio de Exchange Online óptima.</span><span class="sxs-lookup"><span data-stu-id="ebf04-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="ebf04-147">Esta información se abrevia como "enrutamiento" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ebf04-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Puerta delantera no óptima EXO](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ebf04-149">Escenario</span><span class="sxs-lookup"><span data-stu-id="ebf04-149">What does this mean?</span></span>

<span data-ttu-id="ebf04-150">Enumeramos las puertas frontales del servicio de Exchange online que son adecuadas para su uso desde la ciudad de la ubicación de la oficina con buen rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ebf04-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="ebf04-151">Si la prueba actual muestra el uso de una puerta de servicio de Exchange online que no está en esta lista, se indica esta recomendación.</span><span class="sxs-lookup"><span data-stu-id="ebf04-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ebf04-152">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ebf04-152">What should I do?</span></span>

<span data-ttu-id="ebf04-153">El uso de un servicio de Exchange online no óptimo puede deberse a una backhaul? n de red antes de que la red corporativa se deshaga, en cuyo caso se recomienda la salida local y directa de la red.</span><span class="sxs-lookup"><span data-stu-id="ebf04-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="ebf04-154">También podría deberse al uso de un servidor remoto de resolución de recursiva de DNS, en cuyo caso se recomienda alinear el servidor de resolución de DNS recursivo con la salida de red.</span><span class="sxs-lookup"><span data-stu-id="ebf04-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="ebf04-155">Uso de puerta frontal del servicio de SharePoint Online no óptimo</span><span class="sxs-lookup"><span data-stu-id="ebf04-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="ebf04-156">Esta información se mostrará si el servicio de Network Insights detecta que los usuarios de una ubicación específica no se conectan a la puerta frontal del servicio de SharePoint Online más cercana.</span><span class="sxs-lookup"><span data-stu-id="ebf04-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="ebf04-157">Esta información se abrevia como "AFD" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ebf04-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Puerta frontal no óptima de SPO](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ebf04-159">Escenario</span><span class="sxs-lookup"><span data-stu-id="ebf04-159">What does this mean?</span></span>

<span data-ttu-id="ebf04-160">Identificamos la puerta frontal del servicio de SharePoint Online a la que se conecta el cliente de prueba.</span><span class="sxs-lookup"><span data-stu-id="ebf04-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="ebf04-161">A continuación, para la ciudad de la ubicación de la oficina, la encontrarás en la puerta frontal esperada del servicio de SharePoint Online para esa ciudad.</span><span class="sxs-lookup"><span data-stu-id="ebf04-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="ebf04-162">Si no coincide, realizamos esta recomendación.</span><span class="sxs-lookup"><span data-stu-id="ebf04-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ebf04-163">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ebf04-163">What should I do?</span></span>

<span data-ttu-id="ebf04-164">El uso de un servicio de SharePoint Online no óptimo puede deberse a la backhaul? n de red antes de que la red corporativa se deshaga, en cuyo caso se recomienda la salida local y directa de la red.</span><span class="sxs-lookup"><span data-stu-id="ebf04-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="ebf04-165">También podría deberse al uso de un servidor remoto de resolución de recursiva de DNS, en cuyo caso se recomienda alinear el servidor de resolución de DNS recursivo con la salida de red.</span><span class="sxs-lookup"><span data-stu-id="ebf04-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="ebf04-166">Velocidad de descarga baja desde la puerta frontal de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ebf04-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="ebf04-167">Esta información se mostrará si el servicio de Network Insights detecta que el ancho de banda entre la ubicación específica de la oficina y SharePoint Online es inferior a 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="ebf04-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="ebf04-168">Esta información se abrevia como "rendimiento" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ebf04-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ebf04-169">Escenario</span><span class="sxs-lookup"><span data-stu-id="ebf04-169">What does this mean?</span></span>

<span data-ttu-id="ebf04-170">La velocidad de descarga que un usuario puede obtener del servicio de SharePoint Online y OneDrive para la empresa las puertas del anverso se mide en megabytes por segundo (MBps).</span><span class="sxs-lookup"><span data-stu-id="ebf04-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="ebf04-171">Si este valor es inferior a 1 MBps, proporcionaremos esta visión.</span><span class="sxs-lookup"><span data-stu-id="ebf04-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ebf04-172">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ebf04-172">What should I do?</span></span>

<span data-ttu-id="ebf04-173">Para mejorar la velocidad de descarga, es posible que sea necesario aumentar el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="ebf04-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="ebf04-174">Como alternativa, puede que exista una congestión de red entre los equipos de los usuarios en la ubicación de la oficina y la puerta de servicio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ebf04-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="ebf04-175">A veces se denomina pérdida de Congestive y restringe la velocidad de descarga disponible para los usuarios, incluso si hay suficiente ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="ebf04-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="ebf04-176">Salida de red óptima de usuario de China</span><span class="sxs-lookup"><span data-stu-id="ebf04-176">China user optimal network egress</span></span>

<span data-ttu-id="ebf04-177">Esta información se mostrará si su organización tiene usuarios en China que se conectan a su inquilino de Microsoft 365 en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="ebf04-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="ebf04-178">Escenario</span><span class="sxs-lookup"><span data-stu-id="ebf04-178">What does this mean?</span></span>

<span data-ttu-id="ebf04-179">Si su organización tiene conectividad WAN privada, le recomendamos configurar un circuito de WAN de red desde sus ubicaciones de oficina en China que tenga red de salida a Internet en cualquiera de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="ebf04-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="ebf04-180">RAE de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="ebf04-180">Hong Kong</span></span>
- <span data-ttu-id="ebf04-181">Japón</span><span class="sxs-lookup"><span data-stu-id="ebf04-181">Japan</span></span>
- <span data-ttu-id="ebf04-182">Taiwán</span><span class="sxs-lookup"><span data-stu-id="ebf04-182">Taiwan</span></span>
- <span data-ttu-id="ebf04-183">Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="ebf04-183">South Korea</span></span>
- <span data-ttu-id="ebf04-184">Singapur</span><span class="sxs-lookup"><span data-stu-id="ebf04-184">Singapore</span></span>
- <span data-ttu-id="ebf04-185">Malasia</span><span class="sxs-lookup"><span data-stu-id="ebf04-185">Malaysia</span></span>

<span data-ttu-id="ebf04-186">Internet sale aún más de los usuarios que estas ubicaciones reducirán el rendimiento y los resultados en China podrían causar problemas de alta latencia y conectividad debido a congestión transfronteriza.</span><span class="sxs-lookup"><span data-stu-id="ebf04-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ebf04-187">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ebf04-187">What should I do?</span></span>

<span data-ttu-id="ebf04-188">Para obtener más información acerca de cómo mitigar problemas de rendimiento relacionados con esta visión, consulte [Office 365 global tenant performance Optimization for China users](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="ebf04-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="ebf04-189">Conexiones de ejemplo de Exchange afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="ebf04-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="ebf04-190">Esta información se mostrará cuando se vean afectados el 50% o más de las conexiones muestreadas.</span><span class="sxs-lookup"><span data-stu-id="ebf04-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="ebf04-191">El impacto se define mediante la evaluación de Exchange por debajo del 60% para cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ebf04-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ebf04-192">Escenario</span><span class="sxs-lookup"><span data-stu-id="ebf04-192">What does this mean?</span></span>

<span data-ttu-id="ebf04-193">Es una indicación de que es probable que la mayoría de los usuarios experimenten problemas de experiencia de usuario con Outlook que se conecta a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ebf04-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="ebf04-194">El porcentaje de muestras probablemente representará el porcentaje de usuarios que aparecen a menos de 60 puntos.</span><span class="sxs-lookup"><span data-stu-id="ebf04-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="ebf04-195">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ebf04-195">What should I do?</span></span>

<span data-ttu-id="ebf04-196">Habilite la visibilidad de conectividad de red de la ubicación de Office si todavía no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="ebf04-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="ebf04-197">Desea identificar las oficinas que se ven afectadas por una mala conectividad de red que está afectando a Exchange y encontrar formas de mejorar el perímetro de red en cada una de las que conecta a los usuarios a la red de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ebf04-197">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="ebf04-198">Conexiones de muestreo de SharePoint afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="ebf04-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="ebf04-199">Esta información se mostrará cuando se vean afectados el 50% o más de las conexiones muestreadas.</span><span class="sxs-lookup"><span data-stu-id="ebf04-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="ebf04-200">El impacto se define en la evaluación de SharePoint por debajo de 40% para cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ebf04-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ebf04-201">Escenario</span><span class="sxs-lookup"><span data-stu-id="ebf04-201">What does this mean?</span></span>

<span data-ttu-id="ebf04-202">Es una indicación de que es probable que la mayoría de los usuarios experimenten problemas de experiencia de usuario con SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ebf04-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="ebf04-203">El porcentaje de muestras probablemente representará el porcentaje de usuarios que aparecen a menos de 40 puntos.</span><span class="sxs-lookup"><span data-stu-id="ebf04-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="ebf04-204">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ebf04-204">What should I do?</span></span>

<span data-ttu-id="ebf04-205">Habilite la visibilidad de conectividad de red de la ubicación de Office si todavía no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="ebf04-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="ebf04-206">Desea identificar las oficinas que se ven afectadas por una mala conectividad de red que está afectando a SharePoint y encontrar formas de mejorar el perímetro de red en cada una de las que conecta a los usuarios a la red de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ebf04-206">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ebf04-207">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ebf04-207">Related topics</span></span>

[<span data-ttu-id="ebf04-208">Conectividad de red en el centro de administración de 365 de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ebf04-208">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="ebf04-209">Evaluación de red de Microsoft 365 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ebf04-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="ebf04-210">Herramienta de prueba de conectividad de red 365 de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ebf04-210">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="ebf04-211">Servicios de ubicación de conectividad de red 365 de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ebf04-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
