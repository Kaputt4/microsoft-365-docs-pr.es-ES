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
description: Comprenda la infraestructura de red de Contoso y cómo usa su tecnología SD-WAN el rendimiento óptimo de la red para los servicios de nube de Microsoft 365 para empresas.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754019"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="e6941-103">Redes para Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="e6941-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="e6941-p101">Para adoptar una infraestructura de nube inclusiva, contoso diseñó un cambio fundamental en cómo viaja el tráfico de red hacia los servicios en la nube. En lugar de un modelo de concentrador y radio interno que enfoca la conectividad y el tráfico de la red para el siguiente nivel de la jerarquía de Office, asignaban ubicaciones de usuario a la salida de Internet local y conexiones locales a la ubicación de red de Microsoft 365 más cercana en Internet.</span><span class="sxs-lookup"><span data-stu-id="e6941-p101">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels. Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="e6941-106">Infraestructura de red</span><span class="sxs-lookup"><span data-stu-id="e6941-106">Networking infrastructure</span></span>

<span data-ttu-id="e6941-107">Estos son los elementos de red que vinculan las oficinas de Contoso en todo el mundo:</span><span class="sxs-lookup"><span data-stu-id="e6941-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="e6941-108">Red WAN de conmutación de etiquetas multiprotocolo (MPLS)</span><span class="sxs-lookup"><span data-stu-id="e6941-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="e6941-p102">Una red WAN MPLS conecta la sede central de París con las oficinas regionales y las oficinas regionales a las oficinas satélite en una configuración de radios y concentradores. La red permite a los usuarios tener acceso a los servidores locales que forman las aplicaciones de línea de negocio en la sede central de París. También enruta todo el tráfico de Internet genérico a la oficina de París, donde los dispositivos de seguridad de red limpian las solicitudes. Dentro de cada oficina, los enrutadores entregan tráfico a los hosts con cable o a puntos de acceso inalámbrico en las subredes, que usan el espacio de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="e6941-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration. The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters. It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="e6941-113">Acceso directo a Internet local para el tráfico de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6941-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="e6941-p103">Cada oficina tiene un dispositivo WAN definido por software (SD-WAN) que tiene uno o varios circuitos de red ISP de Internet locales con su propia conectividad a Internet a través de un servidor proxy. Suele implementarse como un vínculo WAN a un ISP local que también proporciona direcciones IP públicas y un servidor DNS local.</span><span class="sxs-lookup"><span data-stu-id="e6941-p103">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="e6941-116">Presencia en Internet</span><span class="sxs-lookup"><span data-stu-id="e6941-116">Internet presence</span></span>

  <span data-ttu-id="e6941-p104">Contoso posee el \. nombre de dominio público com de contoso. El sitio web público de Contoso para pedir productos es un conjunto de servidores en un centro de información conectado a Internet en el campus de París. Contoso usa un intervalo de direcciones IP públicas a/24 en Internet.</span><span class="sxs-lookup"><span data-stu-id="e6941-p104">Contoso owns the contoso\.com public domain name. The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="e6941-120">La figura 1 muestra la infraestructura de red de Contoso y sus conexiones a Internet.</span><span class="sxs-lookup"><span data-stu-id="e6941-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![La red de Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="e6941-122">**Figura 1: la red de Contoso**</span><span class="sxs-lookup"><span data-stu-id="e6941-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="e6941-123">Uso de SD-WAN para la conectividad de red óptima a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6941-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="e6941-124">Contoso siguió los [principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md) para:</span><span class="sxs-lookup"><span data-stu-id="e6941-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="e6941-125">Identificar y diferenciar el tráfico de red de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6941-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="e6941-126">Conexiones de red de salida de forma local</span><span class="sxs-lookup"><span data-stu-id="e6941-126">Egress network connections locally</span></span>
- <span data-ttu-id="e6941-127">Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="e6941-127">Avoid network hairpins</span></span>
- <span data-ttu-id="e6941-128">Omitir los dispositivos de seguridad de red duplicados</span><span class="sxs-lookup"><span data-stu-id="e6941-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="e6941-129">Hay tres categorías de tráfico de red para Microsoft 365: *optimizar*, *permitir*y *predeterminado*.</span><span class="sxs-lookup"><span data-stu-id="e6941-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="e6941-130">Optimizar y permitir el tráfico es el tráfico de red de confianza que se cifra y protege en los puntos de conexión y que se destina a la red de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6941-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="e6941-131">Contoso decidió:</span><span class="sxs-lookup"><span data-stu-id="e6941-131">Contoso decided to:</span></span>

- <span data-ttu-id="e6941-132">Use la salida directa de Internet para optimizar y permitir el tráfico de categoría y reenviar todo el tráfico de categoría predeterminado a la conexión central a Internet basada en París.</span><span class="sxs-lookup"><span data-stu-id="e6941-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="e6941-133">Implemente dispositivos SD-WAN en cada oficina como una forma sencilla de seguir estos principios y obtener un rendimiento de red óptimo para los servicios basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6941-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="e6941-134">Los dispositivos SD-WAN tienen un puerto LAN para la red de oficina local y varios puertos WAN.</span><span class="sxs-lookup"><span data-stu-id="e6941-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="e6941-135">Un puerto WAN se conecta a su red MPLS.</span><span class="sxs-lookup"><span data-stu-id="e6941-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="e6941-136">Otro se conecta a un circuito de ISP local.</span><span class="sxs-lookup"><span data-stu-id="e6941-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="e6941-137">El dispositivo SD-WAN enruta el tráfico de las categorías Optimizar y Permitir en el vínculo de ISP.</span><span class="sxs-lookup"><span data-stu-id="e6941-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="e6941-138">La infraestructura de la aplicación de línea de negocio de Contoso</span><span class="sxs-lookup"><span data-stu-id="e6941-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="e6941-139">Contoso diseñó su infraestructura de aplicaciones de línea de negocio y de intranet de servidor para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6941-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="e6941-140">En las oficinas satélite se usan servidores de almacenamiento en caché locales para almacenar documentos y sitios web internos a los que se accede frecuentemente.</span><span class="sxs-lookup"><span data-stu-id="e6941-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="e6941-p107">En los centros regionales se usan servidores de aplicaciones regionales para las oficinas regionales y satélite. Estos servidores se sincronizan con los de la sede de París.</span><span class="sxs-lookup"><span data-stu-id="e6941-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="e6941-143">Los centros de recursos de la sede de París contienen servidores de aplicaciones centralizados que sirven a toda la organización.</span><span class="sxs-lookup"><span data-stu-id="e6941-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="e6941-144">En la figura 2 se muestra el porcentaje de capacidad de tráfico de red que se usa para obtener acceso a los servidores de la intranet de contoso.</span><span class="sxs-lookup"><span data-stu-id="e6941-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![Infraestructura de Contoso para aplicaciones internas](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="e6941-146">**Figura 2: infraestructura de Contoso para aplicaciones internas**</span><span class="sxs-lookup"><span data-stu-id="e6941-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="e6941-147">Para las oficinas satélite o regionales, el 60 por ciento de los recursos que necesitan los empleados pueden ser atendidos por servidores de oficinas centrales y de concentradores.</span><span class="sxs-lookup"><span data-stu-id="e6941-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="e6941-148">El 40 por ciento adicional de solicitudes de recursos debe pasar por el vínculo WAN a la sede de París.</span><span class="sxs-lookup"><span data-stu-id="e6941-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="e6941-149">Análisis y preparación de la red para Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e6941-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="e6941-150">La adopción satisfactoria de Microsoft 365 para los servicios empresariales por parte de los usuarios de Contoso depende de la conectividad de alta disponibilidad y de la performidad a Internet o directamente a los servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6941-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="e6941-151">Contoso llevó a cabo estos pasos para planear e implementar la conectividad optimizada a Microsoft 365 para Enterprise Cloud Services:</span><span class="sxs-lookup"><span data-stu-id="e6941-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="e6941-152">Crear un diagrama de red WAN de una compañía para ayudar con la planeación</span><span class="sxs-lookup"><span data-stu-id="e6941-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="e6941-153">Para empezar la planeación de la red, contoso creó un diagrama que muestra sus ubicaciones de oficina, la conectividad de red existente, los dispositivos perimetrales de red existentes y las clases de servicio que se administran en la red.</span><span class="sxs-lookup"><span data-stu-id="e6941-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="e6941-154">Usaron este diagrama para cada paso posterior de la planeación e implementación de la conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="e6941-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="e6941-155">Crear un plan para Microsoft 365 para conectividad de red empresarial</span><span class="sxs-lookup"><span data-stu-id="e6941-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="e6941-156">Contoso usó los [principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md) y las arquitecturas de red de referencia de ejemplo para identificar SD-WAN como su topología preferida para la conectividad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6941-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="e6941-157">Analizar el uso de conexión a Internet y el ancho de banda de MPLS-WAN en cada oficina y aumentar el ancho de banda según sea necesario</span><span class="sxs-lookup"><span data-stu-id="e6941-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="e6941-158">Se analizó el uso actual de cada oficina y se aumentaron los circuitos, de modo que el tráfico basado en la nube de Microsoft 365 previsto se operara con un promedio del 20% de capacidad sin usar.</span><span class="sxs-lookup"><span data-stu-id="e6941-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="e6941-159">Optimizar el rendimiento de los servicios de red de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6941-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="e6941-160">Contoso determinó el conjunto de extremos de Office 365, Intune y Azure, y firewalls configurados, dispositivos de seguridad y otros sistemas en la ruta de acceso a Internet para obtener un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="e6941-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="e6941-161">Los puntos de conexión de Office 365 optimizar y permitir el tráfico de categoría se configuraron en los dispositivos SD-WAN para enrutar a través del circuito del ISP.</span><span class="sxs-lookup"><span data-stu-id="e6941-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="e6941-162">Configuración de DNS interno</span><span class="sxs-lookup"><span data-stu-id="e6941-162">Configure internal DNS</span></span>

   <span data-ttu-id="e6941-163">DNS debe ser funcional y buscarse de forma local para el tráfico de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6941-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="e6941-164">Validar el punto de conexión de red y la conectividad de Puerto</span><span class="sxs-lookup"><span data-stu-id="e6941-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="e6941-165">Contoso ejecutó las herramientas de prueba de conectividad de red de Microsoft para validar la conectividad para los servicios de nube de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="e6941-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="e6941-166">Optimizar los equipos de los empleados para la conectividad de red</span><span class="sxs-lookup"><span data-stu-id="e6941-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="e6941-167">Se comprobaron los equipos individuales para asegurarse de que se instalaron las últimas actualizaciones del sistema operativo y que la supervisión de seguridad de extremos estaba activa en todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="e6941-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="e6941-168">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e6941-168">Next step</span></span>

<span data-ttu-id="e6941-169">Obtenga información sobre cómo Contoso está [aprovechando sus servicios de dominio de Active Directory local en la nube](contoso-identity.md) para los empleados y la autenticación de Federación para clientes y socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="e6941-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6941-170">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e6941-170">See also</span></span>

[<span data-ttu-id="e6941-171">Guía de redes para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6941-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="e6941-172">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e6941-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e6941-173">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="e6941-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
