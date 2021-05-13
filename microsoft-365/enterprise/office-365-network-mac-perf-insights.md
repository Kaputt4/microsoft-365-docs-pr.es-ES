---
title: Microsoft 365 Network Insights
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
description: Microsoft 365 Network Insights
ms.openlocfilehash: 10b1c66a8f9aae555c2841b2b290f341bec3c7ec
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470573"
---
# <a name="microsoft-365-network-insights"></a><span data-ttu-id="35ed0-103">Microsoft 365 Network Insights</span><span class="sxs-lookup"><span data-stu-id="35ed0-103">Microsoft 365 Network Insights</span></span>

<span data-ttu-id="35ed0-104">**Los conocimientos de** red son métricas de rendimiento recopiladas Microsoft 365 inquilino y disponibles para que solo las puedan ver los usuarios administrativos de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="35ed0-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="35ed0-105">Las perspectivas se muestran en el Centro Microsoft 365 administración en <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="35ed0-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="35ed0-106">Las perspectivas están diseñadas para ayudar a diseñar perímetros de red para las ubicaciones de la oficina.</span><span class="sxs-lookup"><span data-stu-id="35ed0-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="35ed0-107">Cada información proporciona detalles en directo sobre las características de rendimiento de un problema común específico para cada ubicación geográfica en la que los usuarios tienen acceso a su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="35ed0-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="35ed0-108">Hay seis perspectivas de red específicas que se pueden mostrar para cada ubicación de la oficina:</span><span class="sxs-lookup"><span data-stu-id="35ed0-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="35ed0-109">Salida de red backhauled</span><span class="sxs-lookup"><span data-stu-id="35ed0-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="35ed0-110">Dispositivo intermediario de red</span><span class="sxs-lookup"><span data-stu-id="35ed0-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="35ed0-111">Mejor rendimiento detectado para clientes cercanos</span><span class="sxs-lookup"><span data-stu-id="35ed0-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="35ed0-112">Uso de una puerta principal Exchange Online servicio no óptimo</span><span class="sxs-lookup"><span data-stu-id="35ed0-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="35ed0-113">Uso de una puerta principal de servicio SharePoint en línea no óptima</span><span class="sxs-lookup"><span data-stu-id="35ed0-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="35ed0-114">Baja velocidad de descarga desde SharePoint puerta principal</span><span class="sxs-lookup"><span data-stu-id="35ed0-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="35ed0-115">Salida óptima de red del usuario de China</span><span class="sxs-lookup"><span data-stu-id="35ed0-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="35ed0-116">Hay dos perspectivas de red de nivel de inquilino que se pueden mostrar para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="35ed0-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="35ed0-117">También aparecen en las páginas de puntuación de productividad:</span><span class="sxs-lookup"><span data-stu-id="35ed0-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="35ed0-118">Exchange conexiones muestreadas afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="35ed0-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="35ed0-119">SharePoint conexiones muestreadas afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="35ed0-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="35ed0-120">Los conocimientos de red, las recomendaciones de rendimiento y las evaluaciones del Centro de administración de Microsoft 365 se encuentran actualmente en estado de vista previa y solo están disponibles para los inquilinos Microsoft 365 que se han inscrito en el programa de vista previa de características.</span><span class="sxs-lookup"><span data-stu-id="35ed0-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="35ed0-121">Salida de red backhauled</span><span class="sxs-lookup"><span data-stu-id="35ed0-121">Backhauled network egress</span></span>

<span data-ttu-id="35ed0-122">Esta información se mostrará si el servicio de información de red detecta que la distancia desde una ubicación de usuario determinada a la salida de red es mayor que 500 millas (800 kilómetros), lo que indica que el tráfico de Microsoft 365 se está backhauled a un proxy o dispositivo perimetral de Internet común.</span><span class="sxs-lookup"><span data-stu-id="35ed0-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="35ed0-123">Esta información se abrevia como "Egress" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="35ed0-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="35ed0-124">![Salida de red backhauled](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="35ed0-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-125">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-125">What does this mean?</span></span>

<span data-ttu-id="35ed0-126">Esto identifica que la distancia entre la ubicación de la oficina y la salida de red es de más de 500 millas (800 kilómetros).</span><span class="sxs-lookup"><span data-stu-id="35ed0-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="35ed0-127">La ubicación de la oficina se identifica mediante una ubicación del equipo cliente ofuscado y la ubicación de salida de red se identifica mediante la dirección IP inversa a las bases de datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="35ed0-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="35ed0-128">La ubicación de la oficina puede ser inexacta si Windows location services está deshabilitada en las máquinas.</span><span class="sxs-lookup"><span data-stu-id="35ed0-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="35ed0-129">La ubicación de salida de red puede ser inexacta si la información de la base de datos de direcciones IP inversa es inexacta.</span><span class="sxs-lookup"><span data-stu-id="35ed0-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="35ed0-130">Los detalles de esta información incluyen la ubicación de la oficina, el porcentaje estimado del total de inquilinos en la ubicación, la ubicación de salida de red actual, la relevancia de la ubicación de salida, la distancia entre la ubicación y el punto de salida actual, la fecha en que se detectó la condición por primera vez y la fecha en que se resolvió la condición.</span><span class="sxs-lookup"><span data-stu-id="35ed0-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-131">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-131">What should I do?</span></span>

<span data-ttu-id="35ed0-132">Para esta información, recomendamos la salida de red más cerca de la ubicación de la oficina para que la conectividad pueda enrutar de forma óptima a la red global de Microsoft y a la puerta principal del servicio de Microsoft 365 más cercana.</span><span class="sxs-lookup"><span data-stu-id="35ed0-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="35ed0-133">Tener una salida de red cercana a las ubicaciones de oficina de los usuarios también permite mejorar el rendimiento en el futuro, ya que Microsoft expande tanto los puntos de presencia de red como Microsoft 365 puertas frontales del servicio en el futuro.</span><span class="sxs-lookup"><span data-stu-id="35ed0-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="35ed0-134">Para obtener más información acerca de cómo resolver este problema, vea [Egress conexiones](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) de red localmente en [Office 365 principios](microsoft-365-network-connectivity-principles.md)de conectividad de red .</span><span class="sxs-lookup"><span data-stu-id="35ed0-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="35ed0-135">Dispositivo intermediario de red</span><span class="sxs-lookup"><span data-stu-id="35ed0-135">Network intermediary device</span></span>

<span data-ttu-id="35ed0-136">Esta información se mostrará si detectamos dispositivos entre los usuarios y la red de Microsoft que pueden afectar a la Office 365 usuario.</span><span class="sxs-lookup"><span data-stu-id="35ed0-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="35ed0-137">Se recomienda omitir estos datos para el tráfico de red Microsoft 365 específico destinado a centros de datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35ed0-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="35ed0-138">Esta recomendación se describe además en [Microsoft 365 principios de conectividad de red](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="35ed0-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="35ed0-139">Una información intermediaria de red que mostramos es la interrupción e inspección de SSL cuando los puntos de conexión de red críticos de Office 365 para Exchange, SharePoint y Teams son interceptados y descifrados por dispositivos intermediarios de red.</span><span class="sxs-lookup"><span data-stu-id="35ed0-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-140">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-140">What does this mean?</span></span>

<span data-ttu-id="35ed0-141">Los dispositivos intermediarios de red como servidores proxy, VPN y dispositivos de prevención de pérdida de datos pueden afectar al rendimiento y la estabilidad de Microsoft 365 clientes en los que el tráfico está intermedio.</span><span class="sxs-lookup"><span data-stu-id="35ed0-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-142">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-142">What should I do?</span></span>

<span data-ttu-id="35ed0-143">Configure el dispositivo intermediario de red que se detectó para omitir el procesamiento Microsoft 365 tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="35ed0-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="35ed0-144">Mejor rendimiento detectado para clientes cercanos</span><span class="sxs-lookup"><span data-stu-id="35ed0-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="35ed0-145">Esta información se mostrará si el servicio de información de red detecta que un número significativo de clientes de su área metropolitana tienen un mejor rendimiento que los usuarios de su organización en esta ubicación de oficina.</span><span class="sxs-lookup"><span data-stu-id="35ed0-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="35ed0-146">Esta información se abrevia como "Peers" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="35ed0-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="35ed0-147">![Rendimiento relativo de la red](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="35ed0-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-148">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-148">What does this mean?</span></span>

<span data-ttu-id="35ed0-149">Esta información examina el rendimiento agregado de Microsoft 365 clientes en la misma ciudad que esta ubicación de oficina.</span><span class="sxs-lookup"><span data-stu-id="35ed0-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="35ed0-150">Esta información se muestra si la latencia media de los usuarios es un 10 % mayor que la latencia media de los inquilinos vecinos.</span><span class="sxs-lookup"><span data-stu-id="35ed0-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-151">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-151">What should I do?</span></span>

<span data-ttu-id="35ed0-152">Puede haber muchas razones para esta condición, como la latencia en su red corporativa o ISP, cuellos de botella o problemas de diseño de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="35ed0-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="35ed0-153">Examine la latencia entre cada salto de la ruta entre la red de oficina y la puerta Microsoft 365 puerta principal.</span><span class="sxs-lookup"><span data-stu-id="35ed0-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="35ed0-154">Para obtener más información, [vea Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="35ed0-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="35ed0-155">Uso de una puerta principal Exchange Online servicio no óptimo</span><span class="sxs-lookup"><span data-stu-id="35ed0-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="35ed0-156">Esta información se mostrará si el servicio de información de red detecta que los usuarios de una ubicación específica no se conectan a una puerta Exchange Online servicio óptimo.</span><span class="sxs-lookup"><span data-stu-id="35ed0-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="35ed0-157">Esta información se abrevia como "Enrutamiento" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="35ed0-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="35ed0-158">![Puerta frontal exo no óptima](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="35ed0-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-159">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-159">What does this mean?</span></span>

<span data-ttu-id="35ed0-160">Enumeramos Exchange Online puertas frontales de servicio adecuados para su uso desde la ciudad de la ubicación de la oficina con un buen rendimiento.</span><span class="sxs-lookup"><span data-stu-id="35ed0-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="35ed0-161">Si la prueba actual muestra el uso de una puerta Exchange Online de servicio no en esta lista, llamamos a esta recomendación.</span><span class="sxs-lookup"><span data-stu-id="35ed0-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-162">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-162">What should I do?</span></span>

<span data-ttu-id="35ed0-163">El uso de una puerta principal de servicio de Exchange Online no óptima podría deberse al backhaul de red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa.</span><span class="sxs-lookup"><span data-stu-id="35ed0-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="35ed0-164">También podría deberse al uso de un servidor de resolución recursiva dns remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva DNS con la salida de red.</span><span class="sxs-lookup"><span data-stu-id="35ed0-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="35ed0-165">Uso de una puerta principal de servicio SharePoint en línea no óptima</span><span class="sxs-lookup"><span data-stu-id="35ed0-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="35ed0-166">Esta información se mostrará si el servicio de información de red detecta que los usuarios de una ubicación específica no se conectan a la puerta principal del servicio en línea SharePoint más cercana.</span><span class="sxs-lookup"><span data-stu-id="35ed0-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="35ed0-167">Esta información se abrevia como "Afd" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="35ed0-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="35ed0-168">![Puerta principal de SPO no óptima](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="35ed0-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-169">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-169">What does this mean?</span></span>

<span data-ttu-id="35ed0-170">Identificamos la puerta SharePoint servicio en línea a la que se conecta el cliente de prueba.</span><span class="sxs-lookup"><span data-stu-id="35ed0-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="35ed0-171">A continuación, para la ciudad de ubicación de la oficina, lo comparamos con la puerta SharePoint de servicio en línea esperada para esa ciudad.</span><span class="sxs-lookup"><span data-stu-id="35ed0-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="35ed0-172">Si no coincide, hacemos esta recomendación.</span><span class="sxs-lookup"><span data-stu-id="35ed0-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-173">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-173">What should I do?</span></span>

<span data-ttu-id="35ed0-174">El uso de una puerta principal del servicio SharePoint Online no óptimo podría deberse a la retrohaulción de la red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa.</span><span class="sxs-lookup"><span data-stu-id="35ed0-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="35ed0-175">También podría deberse al uso de un servidor de resolución recursiva dns remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva DNS con la salida de red.</span><span class="sxs-lookup"><span data-stu-id="35ed0-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="35ed0-176">Baja velocidad de descarga desde SharePoint puerta principal</span><span class="sxs-lookup"><span data-stu-id="35ed0-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="35ed0-177">Esta información se mostrará si el servicio de información de red detecta que el ancho de banda entre la ubicación específica de la oficina y SharePoint Online es inferior a 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="35ed0-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="35ed0-178">Esta información se abrevia como "Rendimiento" en algunas vistas de resumen.</span><span class="sxs-lookup"><span data-stu-id="35ed0-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-179">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-179">What does this mean?</span></span>

<span data-ttu-id="35ed0-180">La velocidad de descarga que un usuario puede obtener de SharePoint Online y OneDrive para la Empresa las puertas frontales del servicio se mide en megabytes por segundo (MBps).</span><span class="sxs-lookup"><span data-stu-id="35ed0-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="35ed0-181">Si este valor es menor que 1 MBps, proporcionamos esta información.</span><span class="sxs-lookup"><span data-stu-id="35ed0-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-182">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-182">What should I do?</span></span>

<span data-ttu-id="35ed0-183">Para mejorar las velocidades de descarga, es posible que sea necesario aumentar el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="35ed0-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="35ed0-184">Como alternativa, puede haber congestión de red entre las máquinas de usuario en la ubicación de la oficina y la puerta principal SharePoint servicio en línea.</span><span class="sxs-lookup"><span data-stu-id="35ed0-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="35ed0-185">Esto a veces se denomina pérdida congestiva y restringe la velocidad de descarga disponible para los usuarios incluso si hay suficiente ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="35ed0-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="35ed0-186">Salida óptima de red del usuario de China</span><span class="sxs-lookup"><span data-stu-id="35ed0-186">China user optimal network egress</span></span>

<span data-ttu-id="35ed0-187">Esta información se mostrará si su organización tiene usuarios en China que se conectan a su Microsoft 365 en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="35ed0-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-188">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-188">What does this mean?</span></span>

<span data-ttu-id="35ed0-189">Si su organización tiene conectividad WAN privada, se recomienda configurar un circuito WAN de red desde sus ubicaciones de oficina en China que tenga salida de red a Internet en cualquiera de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="35ed0-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="35ed0-190">Hong Kong</span><span class="sxs-lookup"><span data-stu-id="35ed0-190">Hong Kong</span></span>
- <span data-ttu-id="35ed0-191">Japón</span><span class="sxs-lookup"><span data-stu-id="35ed0-191">Japan</span></span>
- <span data-ttu-id="35ed0-192">Taiwán</span><span class="sxs-lookup"><span data-stu-id="35ed0-192">Taiwan</span></span>
- <span data-ttu-id="35ed0-193">Corea del Sur</span><span class="sxs-lookup"><span data-stu-id="35ed0-193">South Korea</span></span>
- <span data-ttu-id="35ed0-194">Singapur</span><span class="sxs-lookup"><span data-stu-id="35ed0-194">Singapore</span></span>
- <span data-ttu-id="35ed0-195">Malasia</span><span class="sxs-lookup"><span data-stu-id="35ed0-195">Malaysia</span></span>

<span data-ttu-id="35ed0-196">La salida de Internet más lejos de los usuarios que estas ubicaciones reducirá el rendimiento y la salida en China puede provocar problemas de latencia y conectividad elevados debido a la congestión transfronteriza.</span><span class="sxs-lookup"><span data-stu-id="35ed0-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-197">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-197">What should I do?</span></span>

<span data-ttu-id="35ed0-198">Para obtener más información acerca de cómo mitigar los problemas de rendimiento relacionados con esta información, vea Microsoft 365 [global tenant performance optimization for China users](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="35ed0-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="35ed0-199">Exchange conexiones muestreadas afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="35ed0-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="35ed0-200">Esta información mostrará cuándo se afecta al 50 % o más de las conexiones muestreadas.</span><span class="sxs-lookup"><span data-stu-id="35ed0-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="35ed0-201">El impacto se define mediante la evaluación Exchange inferior al 60 % para cada muestra.</span><span class="sxs-lookup"><span data-stu-id="35ed0-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-202">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-202">What does this mean?</span></span>

<span data-ttu-id="35ed0-203">Es una indicación de que es probable que la mayoría de los usuarios experimente problemas de experiencia de usuario con Outlook conectarse a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="35ed0-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="35ed0-204">El porcentaje de muestras probablemente representa el porcentaje de usuarios que muestran menos de 60 puntos.</span><span class="sxs-lookup"><span data-stu-id="35ed0-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-205">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-205">What should I do?</span></span>

<span data-ttu-id="35ed0-206">Habilite la visibilidad de la conectividad de red de ubicación de oficina si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="35ed0-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="35ed0-207">Desea identificar qué oficinas se verán afectadas por la mala conectividad de red que está afectando a Exchange y buscar formas de mejorar el perímetro de red en cada una de las que conecte a los usuarios a la red de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35ed0-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="35ed0-208">SharePoint conexiones muestreadas afectadas por problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="35ed0-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="35ed0-209">Esta información mostrará cuándo se afecta al 50 % o más de las conexiones muestreadas.</span><span class="sxs-lookup"><span data-stu-id="35ed0-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="35ed0-210">El impacto se define mediante la evaluación SharePoint por debajo del 40 % para cada muestra.</span><span class="sxs-lookup"><span data-stu-id="35ed0-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="35ed0-211">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="35ed0-211">What does this mean?</span></span>

<span data-ttu-id="35ed0-212">Es una indicación de que es probable que la mayoría de los usuarios experimente problemas de experiencia de usuario con SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="35ed0-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="35ed0-213">El porcentaje de muestras probablemente representa el porcentaje de usuarios que muestran menos de 40 puntos.</span><span class="sxs-lookup"><span data-stu-id="35ed0-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="35ed0-214">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="35ed0-214">What should I do?</span></span>

<span data-ttu-id="35ed0-215">Habilite la visibilidad de la conectividad de red de ubicación de oficina si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="35ed0-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="35ed0-216">Desea identificar qué oficinas se verán afectadas por la mala conectividad de red que está afectando a SharePoint y buscar formas de mejorar el perímetro de red en cada una de las que conecte a los usuarios a la red de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35ed0-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="35ed0-217">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="35ed0-217">Related topics</span></span>

[<span data-ttu-id="35ed0-218">Conectividad de red en el Centro Microsoft 365 administración (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="35ed0-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="35ed0-219">Microsoft 365 de red (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="35ed0-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="35ed0-220">Microsoft 365 de prueba de conectividad de red (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="35ed0-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="35ed0-221">Microsoft 365 Servicios de ubicación de conectividad de red (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="35ed0-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
