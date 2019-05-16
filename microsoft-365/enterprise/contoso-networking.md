---
title: Redes para Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/18/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la infraestructura de red de Contoso y cómo usa su tecnología SD-WAN para obtener conectividad de red de rendimiento óptimo a los servicios basados en la nube de Microsoft 365 Enterprise.
ms.openlocfilehash: 4a2b9f2172def2c62821536e456b2194795158c4
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072560"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="e47b2-103">Redes para Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="e47b2-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="e47b2-104">**Resumen:** comprenda la infraestructura de red de Contoso y cómo usa su tecnología SD-WAN para obtener conectividad de red de rendimiento óptimo a los servicios basados en la nube de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e47b2-104">**Summary:** Understand the Contoso networking infrastructure and how it uses its SD-WAN technology for optimal performance network connectivity to Microsoft 365 Enterprise cloud based services.</span></span>

<span data-ttu-id="e47b2-p101">Para adoptar una infraestructura de nube inclusiva, los ingenieros de redes de Contoso materializaron el cambio fundamental en el modo en que el tráfico de red viaja a los servicios basados en la nube. En lugar de un modelo de concentrador y radio que centrara la conectividad de red en la sede central, trabajaron para asignar las ubicaciones de usuario a la salida de Internet local y las conexiones locales a ubicaciones de red de Microsoft en Internet.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud-based services travels. Instead of a hub and spoke model that focusses network connectivity on the head office, they worked to map user locations to local Internet egress and local connections to Microsoft network locations on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="e47b2-107">Infraestructura de red de Contoso</span><span class="sxs-lookup"><span data-stu-id="e47b2-107">Contoso's networking infrastructure</span></span>

<span data-ttu-id="e47b2-108">Los elementos de la red de Contoso que vincula sus oficinas en todo el mundo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e47b2-108">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="e47b2-109">Red WAN MPLS</span><span class="sxs-lookup"><span data-stu-id="e47b2-109">MPLS WAN network</span></span>

  <span data-ttu-id="e47b2-p102">Una red WAN MPLS conecta la sede central de París a las oficinas regionales y las oficinas regionales a las oficinas satélite en una configuración de concentrador y radio. Esto permite a los usuarios acceder a los servidores locales que conforman las aplicaciones de línea de negocio en la oficina de París. También enruta el tráfico de Internet genérico a la oficina de París, donde los dispositivos de seguridad de red limpian las solicitudes. En cada oficina, los enrutadores entregan el tráfico a hosts o puntos de acceso inalámbricos en subredes, en las que se usa el espacio de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="e47b2-114">Acceso a Internet directo local para el tráfico de Office 365</span><span class="sxs-lookup"><span data-stu-id="e47b2-114">Local direct Internet access for Office 365 traffic</span></span>

  <span data-ttu-id="e47b2-p103">Cada oficina tiene un dispositivo SD-WAN con uno o varios circuitos de red de ISP de Internet local con su propia conectividad a Internet a través de un servidor proxy. Esto suele implementarse como un vínculo WAN a un ISP local que también proporciona direcciones IP públicas y direcciones IP del servidor DNS locales para el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p103">Each office has an SD-WAN device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and local DNS server IP addresses for the proxy server.</span></span>

- <span data-ttu-id="e47b2-117">Presencia en Internet</span><span class="sxs-lookup"><span data-stu-id="e47b2-117">Internet presence</span></span>

  <span data-ttu-id="e47b2-p104">Contoso posee el nombre de dominio público contoso.com. El sitio web público de Contoso para pedir productos es un conjunto de servidores en un centro de datos conectado a Internet en las instalaciones de París. Contoso usa un intervalo de direcciones IP públicas /24 en Internet.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="e47b2-121">En la ilustración 1, se muestra la infraestructura de red de Contoso y sus conexiones a Internet.</span><span class="sxs-lookup"><span data-stu-id="e47b2-121">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![](./media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="e47b2-122">**Ilustración 1: Red de Contoso**</span><span class="sxs-lookup"><span data-stu-id="e47b2-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="e47b2-123">Uso de SD-WAN para la conectividad de red óptima a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e47b2-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="e47b2-124">Contoso siguió los [principios de conectividad de red de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span><span class="sxs-lookup"><span data-stu-id="e47b2-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span></span>

1. <span data-ttu-id="e47b2-125">Identificar y diferenciar el tráfico de red de Office 365</span><span class="sxs-lookup"><span data-stu-id="e47b2-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="e47b2-126">Conexiones de red de salida de forma local</span><span class="sxs-lookup"><span data-stu-id="e47b2-126">Egress network connections locally</span></span>
3. <span data-ttu-id="e47b2-127">Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="e47b2-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="e47b2-128">Omitir los dispositivos de seguridad de red duplicados</span><span class="sxs-lookup"><span data-stu-id="e47b2-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="e47b2-p105">Existen tres categorías de tráfico de red para Office 365: Optimizar, Permitir y Predeterminado. El tráfico de tipo Optimizar y Permitir es tráfico de red de confianza que se cifra y protege en los puntos de conexión y está destinado a los centros de datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p105">There are three categories of network traffic for Office 365: Optimize, Allow, and Default. Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for Microsoft datacenters.</span></span>

<span data-ttu-id="e47b2-131">Contoso decidió usar la salida de Internet directa para el tráfico de las categorías Optimizar y Permitir, y reenviar todo el tráfico de la categoría Predeterminado a la conexión de Internet de la central en París.</span><span class="sxs-lookup"><span data-stu-id="e47b2-131">Contoso decided to use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

<span data-ttu-id="e47b2-132">Decidieron implementar dispositivos SD-WAN en cada una de las oficinas como una forma sencilla de seguir estos principios y obtener un rendimiento de red óptimo para los servicios basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e47b2-132">They decided to deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="e47b2-p106">Los dispositivos SD-WAN tienen un puerto LAN para la red de la oficina local y varios puertos WAN. Un puerto WAN se conecta a su red MPLS, mientras que otros puertos WAN se conectan a los circuitos del ISP local. El dispositivo SD-WAN enruta el tráfico de red de las categorías “Optimizar” y “Permitir” a los vínculos del ISP.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p106">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports. One WAN port connects to their MPLS network and other WAN ports connect to local ISP circuits. The SD-WAN device routes Optimize and Allow category network traffic to the ISP links.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="e47b2-136">Infraestructura de aplicaciones de línea de negocio de Contoso</span><span class="sxs-lookup"><span data-stu-id="e47b2-136">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="e47b2-137">Contoso ha diseñado su infraestructura de servidores y aplicaciones de línea de negocio para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e47b2-137">Contoso has architected its line of business application and server infrastructure for the following:</span></span>

- <span data-ttu-id="e47b2-138">En las oficinas satélite se usan servidores de almacenamiento en caché locales para almacenar documentos y sitios web internos a los que se accede frecuentemente.</span><span class="sxs-lookup"><span data-stu-id="e47b2-138">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="e47b2-p107">En los centros regionales se usan servidores de aplicaciones regionales para las oficinas regionales y satélite. Estos servidores se sincronizan con los de la sede de París.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="e47b2-141">Los centros de datos que contienen los servidores de aplicaciones centralizados que sirven a toda la organización se encuentran en las instalaciones de París.</span><span class="sxs-lookup"><span data-stu-id="e47b2-141">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="e47b2-142">En la ilustración 2, se muestra el porcentaje de tráfico de red cuando se obtiene acceso a los servidores de la intranet de Contoso.</span><span class="sxs-lookup"><span data-stu-id="e47b2-142">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![](./media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="e47b2-143">**Ilustración 2: Infraestructura de Contoso para aplicaciones internas**</span><span class="sxs-lookup"><span data-stu-id="e47b2-143">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="e47b2-p108">Para los usuarios de oficinas de centros regionales o satélite, el 60 % de los recursos que necesitan los empleados pueden obtenerse de los servidores de oficinas de concentradores regionales o satélite. El 40 % adicional de solicitudes de recursos debe realizarse a través del vínculo WAN a las instalaciones de París.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="e47b2-146">Análisis de red de Contoso y preparación de su red para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e47b2-146">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e47b2-p109">La adopción correcta de los servicios de Microsoft 365 Enterprise por parte de los usuarios de Contoso depende de la alta disponibilidad y del rendimiento de la conectividad a Internet, o bien directamente a los servicios en la nube de Microsoft. Contoso siguió estos pasos para planear e implementar la conectividad optimizada a los servicios en la nube de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="e47b2-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="e47b2-149">Creación de un diagrama de red WAN de la empresa para ayudar con la planificación</span><span class="sxs-lookup"><span data-stu-id="e47b2-149">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="e47b2-p110">Contoso inició la planificación de la red creando un diagrama en el que se muestran sus ubicaciones, la conectividad de red y los dispositivos perimetrales de red existentes, y las clases de servicio que se administran en la red. Usaron este diagrama en todos los pasos siguientes de la planificación e implementación de la conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="e47b2-152">Crear un plan para la conectividad de red de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e47b2-152">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="e47b2-153">Contoso usó los [principios de conectividad de red de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) y proporcionó arquitecturas de red de referencia para determinar SD-WAN como su topología preferida para la conectividad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e47b2-153">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD-WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="e47b2-154">Se analizó el uso de la conexión a Internet y el ancho de banda WAN MPLS en cada oficina y se aumentó el ancho de banda si era necesario.</span><span class="sxs-lookup"><span data-stu-id="e47b2-154">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="e47b2-155">En todas las oficinas se analizó el uso actual y se aumentaron los circuitos para que el tráfico basado en la nube de Microsoft 365 pronosticado fuera operativo con una media del 20 % de la capacidad sin usar.</span><span class="sxs-lookup"><span data-stu-id="e47b2-155">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="e47b2-156">Optimización del rendimiento para los servicios de red de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e47b2-156">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="e47b2-p111">Contoso determinó el conjunto de puntos de conexión de Office 365, Intune y Azure, y configuró firewalls, dispositivos de seguridad y otros sistemas en la ruta de Internet para obtener un rendimiento óptimo. Se configuraron puntos de conexión para el tráfico de las categorías “Optimizar” y “Permitir” de Office 365 en los dispositivos SD-WAN que proporcionaban acceso directo a Internet.</span><span class="sxs-lookup"><span data-stu-id="e47b2-p111">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance. Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices that provided direct Internet access.</span></span>

5. <span data-ttu-id="e47b2-159">Configuración de DNS interno</span><span class="sxs-lookup"><span data-stu-id="e47b2-159">Configured internal DNS</span></span>

   <span data-ttu-id="e47b2-160">DNS debe ser funcional y buscarse de forma local para el tráfico de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e47b2-160">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="e47b2-161">Validación de los puntos de conexión de red y la conectividad de los puertos</span><span class="sxs-lookup"><span data-stu-id="e47b2-161">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="e47b2-162">Contoso ejecutó herramientas de pruebas de conectividad de red proporcionadas por Microsoft para validar la conectividad de los servicios en la nube de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e47b2-162">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="e47b2-163">Optimización de los equipos de los empleados para la conectividad de red</span><span class="sxs-lookup"><span data-stu-id="e47b2-163">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="e47b2-164">Los equipos se comprobaron de forma individual para asegurarse de que se habían instalado las actualizaciones del sistema operativo más recientes y que la supervisión de la seguridad de los puntos de conexión estaba activa en todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="e47b2-164">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="e47b2-165">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e47b2-165">Next step</span></span>

<span data-ttu-id="e47b2-166">[Obtenga información sobre](contoso-identity.md) cómo aprovecha Contoso su proveedor de identidades local en la nube para la autenticación de federación y empleados para los clientes y socios empresariales.</span><span class="sxs-lookup"><span data-stu-id="e47b2-166">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises identity provider in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="e47b2-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="e47b2-167">See also</span></span>

[<span data-ttu-id="e47b2-168">Redes para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e47b2-168">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="e47b2-169">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="e47b2-169">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e47b2-170">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="e47b2-170">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
