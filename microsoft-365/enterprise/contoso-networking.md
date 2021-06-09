---
title: Redes para Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la infraestructura de red de Contoso y cómo la empresa usa su tecnología SD-WAN para obtener un rendimiento de red óptimo para Microsoft 365 servicios en la nube empresariales.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754019"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="2806f-103">Redes para Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="2806f-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="2806f-104">Para adoptar una infraestructura inclusiva en la nube, Contoso ideó un cambio fundamental en la forma en que se desplaza el tráfico de red a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="2806f-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="2806f-105">En lugar de un modelo interno de concentrador y radio que centra la conectividad de red y el tráfico para el siguiente nivel de la jerarquía de oficina, asignaron ubicaciones de usuario a la salida de Internet local y conexiones locales a la ubicación de red de Microsoft 365 más cercana en Internet.</span><span class="sxs-lookup"><span data-stu-id="2806f-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="2806f-106">Infraestructura de red</span><span class="sxs-lookup"><span data-stu-id="2806f-106">Networking infrastructure</span></span>

<span data-ttu-id="2806f-107">Estos son los elementos de red que vinculan las oficinas de Contoso en todo el mundo:</span><span class="sxs-lookup"><span data-stu-id="2806f-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="2806f-108">Red WAN de conmutación de etiquetas multiprotocolo (MPLS)</span><span class="sxs-lookup"><span data-stu-id="2806f-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="2806f-109">Una red WAN de MPLS conecta la sede central de París con las oficinas regionales y las oficinas regionales a las oficinas satélite en una configuración de radio y concentrador.</span><span class="sxs-lookup"><span data-stu-id="2806f-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="2806f-110">La red permite a los usuarios tener acceso a los servidores locales que integran aplicaciones de línea de negocio en la sede central de París.</span><span class="sxs-lookup"><span data-stu-id="2806f-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="2806f-111">También enruta cualquier tráfico genérico de Internet a la oficina de París, donde los dispositivos de seguridad de red limpian las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="2806f-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="2806f-112">Dentro de cada oficina, los enrutadores entregan tráfico a hosts con cable o puntos de acceso inalámbrico en subredes, que usan el espacio de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="2806f-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="2806f-113">Acceso directo a Internet local para Microsoft 365 tráfico</span><span class="sxs-lookup"><span data-stu-id="2806f-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="2806f-114">Cada oficina tiene un dispositivo WAN (SD-WAN) definido por software que tiene uno o más circuitos de red ISP de Internet local con su propia conectividad a Internet a través de un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="2806f-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="2806f-115">Esto suele implementarse como un vínculo WAN a un ISP local que también proporciona direcciones IP públicas y un servidor DNS local.</span><span class="sxs-lookup"><span data-stu-id="2806f-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="2806f-116">Presencia en Internet</span><span class="sxs-lookup"><span data-stu-id="2806f-116">Internet presence</span></span>

  <span data-ttu-id="2806f-117">Contoso es propietario del nombre de dominio público contoso \. com.</span><span class="sxs-lookup"><span data-stu-id="2806f-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="2806f-118">El sitio web público de Contoso para ordenar productos es un conjunto de servidores en un centro de datos conectado a Internet en el campus de París.</span><span class="sxs-lookup"><span data-stu-id="2806f-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="2806f-119">Contoso usa un intervalo de direcciones IP públicas /24 en Internet.</span><span class="sxs-lookup"><span data-stu-id="2806f-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="2806f-120">En la figura 1 se muestra la infraestructura de red de Contoso y sus conexiones a Internet.</span><span class="sxs-lookup"><span data-stu-id="2806f-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![La red contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="2806f-122">**Figura 1: La red contoso**</span><span class="sxs-lookup"><span data-stu-id="2806f-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="2806f-123">Uso de SD-WAN para la conectividad de red óptima a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2806f-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="2806f-124">Contoso siguió los [principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md) para:</span><span class="sxs-lookup"><span data-stu-id="2806f-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="2806f-125">Identificar y diferenciar el tráfico de red de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2806f-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="2806f-126">Conexiones de red de salida de forma local</span><span class="sxs-lookup"><span data-stu-id="2806f-126">Egress network connections locally</span></span>
- <span data-ttu-id="2806f-127">Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="2806f-127">Avoid network hairpins</span></span>
- <span data-ttu-id="2806f-128">Omitir los dispositivos de seguridad de red duplicados</span><span class="sxs-lookup"><span data-stu-id="2806f-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="2806f-129">Hay tres categorías de tráfico de red para Microsoft 365: *Optimize*, *Allow* y *Default*.</span><span class="sxs-lookup"><span data-stu-id="2806f-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="2806f-130">Optimizar y permitir el tráfico es un tráfico de red de confianza que está cifrado y protegido en los puntos de conexión y está destinado a la Microsoft 365 red.</span><span class="sxs-lookup"><span data-stu-id="2806f-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="2806f-131">Contoso decidió:</span><span class="sxs-lookup"><span data-stu-id="2806f-131">Contoso decided to:</span></span>

- <span data-ttu-id="2806f-132">Use la salida directa de Internet para optimizar y permitir el tráfico de categorías y para reenviar todo el tráfico de categoría predeterminado a la conexión central de Internet basada en París.</span><span class="sxs-lookup"><span data-stu-id="2806f-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="2806f-133">Implemente dispositivos SD-WAN en cada oficina como una forma sencilla de seguir estos principios y lograr un rendimiento de red óptimo para Microsoft 365 servicios basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="2806f-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="2806f-134">Los dispositivos SD-WAN tienen un puerto LAN para la red de oficina local y varios puertos WAN.</span><span class="sxs-lookup"><span data-stu-id="2806f-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="2806f-135">Un puerto WAN se conecta a su red MPLS.</span><span class="sxs-lookup"><span data-stu-id="2806f-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="2806f-136">Otro se conecta a un circuito isp local.</span><span class="sxs-lookup"><span data-stu-id="2806f-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="2806f-137">El dispositivo SD-WAN enruta el tráfico de las categorías Optimizar y Permitir en el vínculo de ISP.</span><span class="sxs-lookup"><span data-stu-id="2806f-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="2806f-138">La infraestructura de aplicaciones de línea de negocio de Contoso</span><span class="sxs-lookup"><span data-stu-id="2806f-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="2806f-139">Contoso diseñó su infraestructura de intranet de servidor y aplicación de línea de negocio para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2806f-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="2806f-140">En las oficinas satélite se usan servidores de almacenamiento en caché locales para almacenar documentos y sitios web internos a los que se accede frecuentemente.</span><span class="sxs-lookup"><span data-stu-id="2806f-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="2806f-p107">En los centros regionales se usan servidores de aplicaciones regionales para las oficinas regionales y satélite. Estos servidores se sincronizan con los de la sede de París.</span><span class="sxs-lookup"><span data-stu-id="2806f-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="2806f-143">Los centros de datos del campus de París contienen servidores de aplicaciones centralizados que sirven a toda la organización.</span><span class="sxs-lookup"><span data-stu-id="2806f-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="2806f-144">La figura 2 muestra el porcentaje de capacidad de tráfico de red que se usa al obtener acceso a los servidores en toda la intranet de Contoso.</span><span class="sxs-lookup"><span data-stu-id="2806f-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![La infraestructura de Contoso para aplicaciones internas](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="2806f-146">**Figura 2: La infraestructura de Contoso para aplicaciones internas**</span><span class="sxs-lookup"><span data-stu-id="2806f-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="2806f-147">Para las oficinas centrales de satélite o regionales, el 60 % de los recursos necesarios para los empleados pueden ser atendidos por servidores de oficinas centrales regionales y satélites.</span><span class="sxs-lookup"><span data-stu-id="2806f-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="2806f-148">El 40 % adicional de solicitudes de recursos debe pasar por el vínculo WAN al campus de París.</span><span class="sxs-lookup"><span data-stu-id="2806f-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="2806f-149">Análisis de red y preparación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2806f-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="2806f-150">La adopción correcta de Microsoft 365 para los servicios empresariales por parte de los usuarios de Contoso depende de una conectividad altamente disponible y de rendimiento a Internet o directamente a los servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2806f-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="2806f-151">Contoso realizó estos pasos para planear e implementar la conectividad optimizada para Microsoft 365 para los servicios de nube empresariales:</span><span class="sxs-lookup"><span data-stu-id="2806f-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="2806f-152">Crear un diagrama de red WAN de empresa para ayudar con la planeación</span><span class="sxs-lookup"><span data-stu-id="2806f-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="2806f-153">Para iniciar su planeación de red, Contoso creó un diagrama que muestra sus ubicaciones de oficina, conectividad de red existente, dispositivos perimetrales de red existentes y clases de servicio que se administran en la red.</span><span class="sxs-lookup"><span data-stu-id="2806f-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="2806f-154">Usaron este diagrama para cada paso posterior en la planeación e implementación de la conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="2806f-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="2806f-155">Crear un plan para Microsoft 365 conectividad de red empresarial</span><span class="sxs-lookup"><span data-stu-id="2806f-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="2806f-156">Contoso usó los Microsoft 365 de conectividad de red y las [arquitecturas](microsoft-365-network-connectivity-principles.md) de red de referencia de ejemplo para identificar SD-WAN como su topología preferida para Microsoft 365 conectividad.</span><span class="sxs-lookup"><span data-stu-id="2806f-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="2806f-157">Analizar el uso de conexión a Internet y el ancho de banda MPLS-WAN en cada oficina y aumentar el ancho de banda según sea necesario</span><span class="sxs-lookup"><span data-stu-id="2806f-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="2806f-158">Se analizó el uso actual de cada oficina y se aumentaron los circuitos para que el tráfico Microsoft 365 basado en la nube funcionara con un promedio de 20 por ciento de capacidad sin usar.</span><span class="sxs-lookup"><span data-stu-id="2806f-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="2806f-159">Optimizar el rendimiento de los servicios de red de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2806f-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="2806f-160">Contoso determinó el conjunto de Office 365, Intune y puntos de conexión de Azure y firewalls configurados, dispositivos de seguridad y otros sistemas en la ruta de acceso a Internet para un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="2806f-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="2806f-161">Los puntos de conexión Office 365 optimizar y permitir tráfico de categorías se configuraron en los dispositivos SD-WAN para el enrutamiento a través del circuito ISP.</span><span class="sxs-lookup"><span data-stu-id="2806f-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="2806f-162">Configurar DNS interno</span><span class="sxs-lookup"><span data-stu-id="2806f-162">Configure internal DNS</span></span>

   <span data-ttu-id="2806f-163">DNS debe ser funcional y buscarse de forma local para el tráfico de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2806f-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="2806f-164">Validar la conectividad de puerto y punto de conexión de red</span><span class="sxs-lookup"><span data-stu-id="2806f-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="2806f-165">Contoso ejecutó las herramientas de prueba de conectividad de red de Microsoft para validar la conectividad Microsoft 365 para los servicios de nube empresariales.</span><span class="sxs-lookup"><span data-stu-id="2806f-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="2806f-166">Optimizar los equipos de empleados para la conectividad de red</span><span class="sxs-lookup"><span data-stu-id="2806f-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="2806f-167">Se comprobaron equipos individuales para asegurarse de que se instalaron las últimas actualizaciones del sistema operativo y de que la supervisión de seguridad de puntos de conexión estaba activa en todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="2806f-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="2806f-168">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2806f-168">Next step</span></span>

<span data-ttu-id="2806f-169">Obtenga información sobre cómo Contoso está aprovechando sus servicios de dominio de [Active Directory](contoso-identity.md) locales en la nube para los empleados y la autenticación federada para clientes y socios empresariales.</span><span class="sxs-lookup"><span data-stu-id="2806f-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="2806f-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2806f-170">See also</span></span>

[<span data-ttu-id="2806f-171">Guía básica de redes para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2806f-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="2806f-172">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2806f-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2806f-173">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="2806f-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
