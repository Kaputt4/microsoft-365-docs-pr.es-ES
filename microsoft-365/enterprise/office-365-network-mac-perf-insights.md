---
title: Microsoft 365 Network Insights (versión preliminar)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (versión preliminar)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055478"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="ab71a-103">Microsoft 365 Network Insights (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ab71a-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="ab71a-104">**Las perspectivas de** red son métricas de rendimiento recopiladas de su inquilino de Microsoft 365 y disponibles para que las puedan ver solo los usuarios administrativos de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ab71a-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="ab71a-105">Las conclusiones se muestran en el Centro de administración de Microsoft 365 en <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="ab71a-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="ab71a-106">Insights está pensado para ayudar a diseñar perímetros de red para las ubicaciones de las oficinas.</span><span class="sxs-lookup"><span data-stu-id="ab71a-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="ab71a-107">Cada información proporciona detalles en directo sobre las características de rendimiento de un problema común específico para cada ubicación geográfica en la que los usuarios acceden a su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ab71a-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="ab71a-108">Hay seis perspectivas de red específicas que se pueden mostrar para cada ubicación de la oficina:</span><span class="sxs-lookup"><span data-stu-id="ab71a-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="ab71a-109">Salida de red contralada</span><span class="sxs-lookup"><span data-stu-id="ab71a-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="ab71a-110">Dispositivo intermediario de red</span><span class="sxs-lookup"><span data-stu-id="ab71a-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="ab71a-111">Mejor rendimiento detectado para clientes cercanos</span><span class="sxs-lookup"><span data-stu-id="ab71a-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="ab71a-112">Uso de una puerta de servicio de Exchange Online no óptima</span><span class="sxs-lookup"><span data-stu-id="ab71a-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="ab71a-113">Uso de una puerta de servicio de SharePoint Online no óptima</span><span class="sxs-lookup"><span data-stu-id="ab71a-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="ab71a-114">Baja velocidad de descarga desde la puerta principal de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ab71a-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="ab71a-115">Salida de red óptima para usuarios de China</span><span class="sxs-lookup"><span data-stu-id="ab71a-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="ab71a-116">Hay dos perspectivas de red de nivel de inquilino que se pueden mostrar para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="ab71a-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="ab71a-117">También aparecen en las páginas de puntuación de producción:</span><span class="sxs-lookup"><span data-stu-id="ab71a-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="ab71a-118">Conexiones de ejemplo de Exchange afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="ab71a-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="ab71a-119">Conexiones de ejemplo de SharePoint afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="ab71a-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="ab71a-120">Información de red, recomendaciones de rendimiento y evaluaciones en el Centro de administración de Microsoft 365 se encuentra actualmente en estado de vista previa y solo está disponible para los inquilinos de Microsoft 365 que se han inscrito en el programa de vista previa de características.</span><span class="sxs-lookup"><span data-stu-id="ab71a-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="ab71a-121">Salida de red contralada</span><span class="sxs-lookup"><span data-stu-id="ab71a-121">Backhauled network egress</span></span>

<span data-ttu-id="ab71a-122">Esta información se mostrará si el servicio de información de red detecta que la distancia desde una ubicación de usuario determinada a la salida de red es superior a 500 millas (800 kilómetros), lo que indica que el tráfico de Microsoft 365 se está reenlazando a un proxy o dispositivo perimetral de Internet común.</span><span class="sxs-lookup"><span data-stu-id="ab71a-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="ab71a-123">Esta información se abrevia como "Salida" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ab71a-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Salida de red contralada](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-125">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-125">What does this mean?</span></span>

<span data-ttu-id="ab71a-126">Esto identifica que la distancia entre la ubicación de la oficina y la salida de red es de más de 500 millas (800 kilómetros).</span><span class="sxs-lookup"><span data-stu-id="ab71a-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="ab71a-127">La ubicación de la oficina se identifica mediante una ubicación de máquina cliente oculta y la ubicación de salida de red se identifica mediante la dirección IP inversa a las bases de datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="ab71a-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="ab71a-128">La ubicación de la oficina puede ser inexacta si los Servicios de ubicación de Windows están deshabilitados en las máquinas.</span><span class="sxs-lookup"><span data-stu-id="ab71a-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="ab71a-129">La ubicación de salida de red puede ser inexacta si la información de la base de datos de direcciones IP inversas es inexacta.</span><span class="sxs-lookup"><span data-stu-id="ab71a-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="ab71a-130">Los detalles de esta información incluyen la ubicación de la oficina, el porcentaje estimado del usuario del espacio empresarial total en la ubicación, la ubicación de salida de red actual, la relevancia de la ubicación de salida, la distancia entre la ubicación y el punto de salida actual, la fecha en que se detectó por primera vez la condición y la fecha en que se resolvió la condición.</span><span class="sxs-lookup"><span data-stu-id="ab71a-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-131">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-131">What should I do?</span></span>

<span data-ttu-id="ab71a-132">Para esta información, recomendamos la salida de red más cerca de la ubicación de la oficina para que la conectividad pueda enrutar de forma óptima a la red global de Microsoft y a la puerta principal del servicio de Microsoft 365 más cercana.</span><span class="sxs-lookup"><span data-stu-id="ab71a-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="ab71a-133">Cerrar la salida de red a las ubicaciones de oficina de los usuarios también permite mejorar el rendimiento en el futuro, ya que Microsoft expande los puntos de presencia de red y las puertas frontales del servicio de Microsoft 365 en el futuro.</span><span class="sxs-lookup"><span data-stu-id="ab71a-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="ab71a-134">Para obtener más información acerca de cómo resolver este problema, consulte [Conexiones](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) de red de salida localmente en principios de conectividad de red de [Office 365.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="ab71a-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="ab71a-135">Dispositivo intermediario de red</span><span class="sxs-lookup"><span data-stu-id="ab71a-135">Network intermediary device</span></span>

<span data-ttu-id="ab71a-136">Esta información se mostrará si detectamos dispositivos entre los usuarios y la red de Microsoft, lo que puede afectar a la experiencia del usuario de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab71a-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="ab71a-137">Se recomienda que se omitan para el tráfico de red específico de Microsoft 365 destinado a centros de datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab71a-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="ab71a-138">Esta recomendación se describe además en los Principios de conectividad de [red de Microsoft 365](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="ab71a-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-139">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-139">What does this mean?</span></span>

<span data-ttu-id="ab71a-140">Los dispositivos intermediarios de red como servidores proxy, VPN y dispositivos de prevención de pérdida de datos pueden afectar al rendimiento y la estabilidad de los clientes de Microsoft 365 en los que el tráfico está intermedio.</span><span class="sxs-lookup"><span data-stu-id="ab71a-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-141">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-141">What should I do?</span></span>

<span data-ttu-id="ab71a-142">Configurar el dispositivo intermediario de red que se detectó para omitir el procesamiento del tráfico de red de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab71a-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="ab71a-143">Mejor rendimiento detectado para clientes cercanos</span><span class="sxs-lookup"><span data-stu-id="ab71a-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="ab71a-144">Esta información se mostrará si el servicio de información de red detecta que un número significativo de clientes de su área de metro tienen un mejor rendimiento que los usuarios de su organización en esta ubicación de la oficina.</span><span class="sxs-lookup"><span data-stu-id="ab71a-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="ab71a-145">Esta información se abrevia como "Pares" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ab71a-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Rendimiento de red relativo](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-147">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-147">What does this mean?</span></span>

<span data-ttu-id="ab71a-148">Esta información examina el rendimiento agregado de los clientes de Microsoft 365 en la misma ciudad que esta ubicación de la oficina.</span><span class="sxs-lookup"><span data-stu-id="ab71a-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="ab71a-149">Esta información se muestra si la latencia media de los usuarios es un 10 % mayor que la latencia media de los inquilinos vecinos.</span><span class="sxs-lookup"><span data-stu-id="ab71a-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-150">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-150">What should I do?</span></span>

<span data-ttu-id="ab71a-151">Puede haber muchas razones para esta condición, incluida la latencia en la red corporativa o isp, cuellos de botella o problemas de diseño de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="ab71a-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="ab71a-152">Examine la latencia entre cada salto de la ruta entre la red de la oficina y la puerta principal actual de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab71a-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="ab71a-153">Para obtener más información, consulte Principios de conectividad de red [de Microsoft 365.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="ab71a-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="ab71a-154">Uso de una puerta de servicio de Exchange Online no óptima</span><span class="sxs-lookup"><span data-stu-id="ab71a-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="ab71a-155">Esta información se mostrará si el servicio de información de red detecta que los usuarios de una ubicación específica no se conectan a una puerta de servicio de Exchange Online óptima.</span><span class="sxs-lookup"><span data-stu-id="ab71a-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="ab71a-156">Esta información se abrevia como "Enrutamiento" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ab71a-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Puerta frontal EXO no óptima](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-158">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-158">What does this mean?</span></span>

<span data-ttu-id="ab71a-159">Enumeramos las puertas frontales del servicio de Exchange Online que son adecuadas para su uso desde la ciudad de la ubicación de la oficina con un buen rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ab71a-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="ab71a-160">Si la prueba actual muestra el uso de una puerta de servicio de Exchange Online que no está en esta lista, llamamos a esta recomendación.</span><span class="sxs-lookup"><span data-stu-id="ab71a-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-161">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-161">What should I do?</span></span>

<span data-ttu-id="ab71a-162">El uso de una puerta frontal de servicio de Exchange Online no óptima podría deberse a la reenlace de la red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa.</span><span class="sxs-lookup"><span data-stu-id="ab71a-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="ab71a-163">También podría deberse al uso de un servidor de resolución recursiva DNS remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva dns con la salida de red.</span><span class="sxs-lookup"><span data-stu-id="ab71a-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="ab71a-164">Uso de una puerta de servicio de SharePoint Online no óptima</span><span class="sxs-lookup"><span data-stu-id="ab71a-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="ab71a-165">Esta información se mostrará si el servicio de información de red detecta que los usuarios de una ubicación específica no se conectan a la puerta principal del servicio de SharePoint Online más cercano.</span><span class="sxs-lookup"><span data-stu-id="ab71a-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="ab71a-166">Esta información se abrevia como "Afd" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ab71a-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Puerta frontal de SPO no óptima](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-168">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-168">What does this mean?</span></span>

<span data-ttu-id="ab71a-169">Identificamos la puerta principal del servicio de SharePoint Online con la que se conecta el cliente de prueba.</span><span class="sxs-lookup"><span data-stu-id="ab71a-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="ab71a-170">A continuación, para la ciudad de la ubicación de la oficina, lo comparamos con la puerta de entrada del servicio de SharePoint Online prevista para esa ciudad.</span><span class="sxs-lookup"><span data-stu-id="ab71a-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="ab71a-171">Si no coincide, le recomendamos que lo haga.</span><span class="sxs-lookup"><span data-stu-id="ab71a-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-172">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-172">What should I do?</span></span>

<span data-ttu-id="ab71a-173">El uso de una puerta frontal de servicio de SharePoint Online no óptima podría deberse a la reenlace de la red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa.</span><span class="sxs-lookup"><span data-stu-id="ab71a-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="ab71a-174">También podría deberse al uso de un servidor de resolución recursiva DNS remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva dns con la salida de red.</span><span class="sxs-lookup"><span data-stu-id="ab71a-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="ab71a-175">Baja velocidad de descarga desde la puerta principal de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ab71a-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="ab71a-176">Esta información se mostrará si el servicio de información de red detecta que el ancho de banda entre la ubicación de la oficina específica y SharePoint Online es inferior a 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="ab71a-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="ab71a-177">Esta información se abrevia como "Rendimiento" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="ab71a-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-178">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-178">What does this mean?</span></span>

<span data-ttu-id="ab71a-179">La velocidad de descarga que un usuario puede obtener de las puertas frontales del servicio de OneDrive para la Empresa y SharePoint Online se mide en megabytes por segundo (MBps).</span><span class="sxs-lookup"><span data-stu-id="ab71a-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="ab71a-180">Si este valor es menor que 1 MBps, proporcionamos esta información.</span><span class="sxs-lookup"><span data-stu-id="ab71a-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-181">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-181">What should I do?</span></span>

<span data-ttu-id="ab71a-182">Para mejorar las velocidades de descarga, es posible que sea necesario aumentar el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="ab71a-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="ab71a-183">Como alternativa, puede haber congestión de la red entre las máquinas de usuario en la ubicación de la oficina y la puerta principal del servicio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ab71a-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="ab71a-184">Esto a veces se denomina pérdida congestiva y restringe la velocidad de descarga disponible para los usuarios incluso si hay suficiente ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="ab71a-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="ab71a-185">Salida de red óptima para usuarios de China</span><span class="sxs-lookup"><span data-stu-id="ab71a-185">China user optimal network egress</span></span>

<span data-ttu-id="ab71a-186">Esta información se mostrará si su organización tiene usuarios en China que se conectan a su espacio empresarial de Microsoft 365 en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="ab71a-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-187">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-187">What does this mean?</span></span>

<span data-ttu-id="ab71a-188">Si su organización tiene conectividad WAN privada, le recomendamos que configure un circuito WAN de red desde sus ubicaciones de oficina en China que tenga salida de red a Internet en cualquiera de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="ab71a-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="ab71a-189">Hong Kong</span><span class="sxs-lookup"><span data-stu-id="ab71a-189">Hong Kong</span></span>
- <span data-ttu-id="ab71a-190">Japón</span><span class="sxs-lookup"><span data-stu-id="ab71a-190">Japan</span></span>
- <span data-ttu-id="ab71a-191">Taiwán</span><span class="sxs-lookup"><span data-stu-id="ab71a-191">Taiwan</span></span>
- <span data-ttu-id="ab71a-192">Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="ab71a-192">South Korea</span></span>
- <span data-ttu-id="ab71a-193">Singapur</span><span class="sxs-lookup"><span data-stu-id="ab71a-193">Singapore</span></span>
- <span data-ttu-id="ab71a-194">Malasia</span><span class="sxs-lookup"><span data-stu-id="ab71a-194">Malaysia</span></span>

<span data-ttu-id="ab71a-195">La salida de Internet más alejada de los usuarios que estas ubicaciones reducirá el rendimiento, y la salida en China puede causar problemas de conectividad y latencia alta debido a la congestión entre fronteras.</span><span class="sxs-lookup"><span data-stu-id="ab71a-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-196">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-196">What should I do?</span></span>

<span data-ttu-id="ab71a-197">Para obtener más información acerca de cómo mitigar los problemas de rendimiento relacionados con esta información, vea Optimización del rendimiento global de los inquilinos de [Microsoft 365 para los usuarios de China.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="ab71a-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="ab71a-198">Conexiones de ejemplo de Exchange afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="ab71a-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="ab71a-199">Esta información mostrará cuándo se verán afectadas el 50 % o más de las conexiones muestreadas.</span><span class="sxs-lookup"><span data-stu-id="ab71a-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="ab71a-200">El impacto lo define la evaluación de Exchange por debajo del 60 % para cada muestra.</span><span class="sxs-lookup"><span data-stu-id="ab71a-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-201">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-201">What does this mean?</span></span>

<span data-ttu-id="ab71a-202">Es una indicación de que es probable que la mayoría de los usuarios experimente problemas de experiencia de usuario con Outlook conectándose a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ab71a-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="ab71a-203">Es probable que el porcentaje de muestras represente el porcentaje de usuarios que se muestran por debajo de 60 puntos.</span><span class="sxs-lookup"><span data-stu-id="ab71a-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-204">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-204">What should I do?</span></span>

<span data-ttu-id="ab71a-205">Habilite la visibilidad de la conectividad de red de la ubicación de la oficina si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="ab71a-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="ab71a-206">Desea identificar qué oficinas se verán afectadas por una conectividad de red deficiente que está afectando a Exchange y buscar formas de mejorar el perímetro de red en cada una de las oficinas que conecta a los usuarios con la red de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab71a-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="ab71a-207">Conexiones de ejemplo de SharePoint afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="ab71a-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="ab71a-208">Esta información mostrará cuándo se verán afectadas el 50 % o más de las conexiones muestreadas.</span><span class="sxs-lookup"><span data-stu-id="ab71a-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="ab71a-209">El impacto lo define la evaluación de SharePoint por debajo del 40 % para cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ab71a-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ab71a-210">Escenario</span><span class="sxs-lookup"><span data-stu-id="ab71a-210">What does this mean?</span></span>

<span data-ttu-id="ab71a-211">Es una indicación de que es probable que la mayoría de los usuarios experimente problemas de experiencia del usuario con SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ab71a-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="ab71a-212">Es probable que el porcentaje de muestras represente el porcentaje de usuarios que se muestran por debajo de 40 puntos.</span><span class="sxs-lookup"><span data-stu-id="ab71a-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="ab71a-213">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="ab71a-213">What should I do?</span></span>

<span data-ttu-id="ab71a-214">Habilite la visibilidad de la conectividad de red de la ubicación de la oficina si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="ab71a-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="ab71a-215">Desea identificar qué oficinas se verán afectadas por una conectividad de red deficiente que esté afectando a SharePoint y buscar formas de mejorar el perímetro de red en cada una de las oficinas que conecta a los usuarios con la red de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab71a-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab71a-216">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ab71a-216">Related topics</span></span>

[<span data-ttu-id="ab71a-217">Conectividad de red en el Centro de administración de Microsoft 365 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ab71a-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="ab71a-218">Evaluación de red de Microsoft 365 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ab71a-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="ab71a-219">Herramienta de prueba de conectividad de red de Microsoft 365 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ab71a-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="ab71a-220">Servicios de ubicación de conectividad de red de Microsoft 365 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ab71a-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
