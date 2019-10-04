---
title: 'Paso 2: Configurar conexiones a Internet locales para cada oficina'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure su resolución DNS para mejorar el rendimiento.
ms.openlocfilehash: b47131b9a5f854c630f5d54bd4d3b4738ed953b3
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370307"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="a7561-103">Paso 2: Configurar conexiones a Internet locales para cada oficina</span><span class="sxs-lookup"><span data-stu-id="a7561-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="a7561-104">*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a7561-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1-Red](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="a7561-p101">En el paso 2, se asegura de que todas las oficinas tienen conexión local a Internet y usan servidores DNS locales. Estos dos elementos son necesarios para reducir la latencia de la conexión y asegurarse de que los equipos cliente locales establecen conexiones con el punto de entrada más próximo a los servicios basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7561-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="a7561-108">En las redes tradicionales para grandes organizaciones, el tráfico de Internet se desplaza por la red troncal a una conexión a Internet central.</span><span class="sxs-lookup"><span data-stu-id="a7561-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="a7561-109">Esto no es adecuado para optimizar el rendimiento de una infraestructura de Software como Servicio (SaaS) distribuida globalmente, que incluye los productos Office 365 e Intune en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7561-109">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="a7561-110">La Red Global de Microsoft incluye una infraestructura de *Servicio Front End Distribuido*, un perímetro de red altamente disponible y escalable con ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="a7561-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="a7561-111">Termina las conexiones de usuario final en un servidor front-end y enruta eficazmente el tráfico de usuario final en la Red Global de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7561-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![La Red Global de Microsoft](./media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="a7561-113">Para obtener el mejor rendimiento, los clientes locales deben acceder a un servidor front-end que esté geográficamente más próximo a ellos, en lugar de enviar el tráfico a través de una red troncal al servidor front-end más próximo a la conexión de Internet central de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7561-113">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="a7561-114">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7561-114">Here’s an example.</span></span>

![Ejemplo de uso de la Red Global de Microsoft](./media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="a7561-116">Cuando un usuario de la sucursal de París desea tener acceso a un sitio de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a7561-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="a7561-117">Envía una consulta DNS para resolver un nombre, como contoso.sharepoint.com.</span><span class="sxs-lookup"><span data-stu-id="a7561-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="a7561-118">El servidor DNS que proporcionó el ISP reenvía esa consulta a un servidor DNS de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7561-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="a7561-119">Los servidores DNS de Microsoft coinciden con la dirección IP de origen de la consulta DNS reenviada a la región del mundo asignada a la dirección.</span><span class="sxs-lookup"><span data-stu-id="a7561-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="a7561-120">El servidor DNS de Microsoft responde con la dirección IP del servidor front-end de la red de Microsoft más cercana en Europa.</span><span class="sxs-lookup"><span data-stu-id="a7561-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="a7561-121">El servidor DNS de ISP envía esta dirección IP al usuario.</span><span class="sxs-lookup"><span data-stu-id="a7561-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="a7561-122">El usuario inicia una conexión con el servidor de SharePoint a través del servidor front-end de Europa.</span><span class="sxs-lookup"><span data-stu-id="a7561-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="a7561-123">Para dirigir una solicitud de cliente al servidor front-end más cercano geográficamente, los servidores DNS de Microsoft usan las consultas DNS correspondientes a la solicitud de conexión inicial del cliente. </span><span class="sxs-lookup"><span data-stu-id="a7561-123">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span> <span data-ttu-id="a7561-124">Por tanto, para obtener la latencia de red más baja:</span><span class="sxs-lookup"><span data-stu-id="a7561-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="a7561-125">Todas las oficinas de la organización deben tener conexiones locales a Internet para el tráfico de red de la categoría [Optimizar](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="a7561-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="a7561-126">Todas las conexiones locales a Internet deben usar un servidor DNS local de la región para el tráfico de Internet saliente desde esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="a7561-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="a7561-127">Para obtener más información, vea [Conexiones de red de salida de forma local](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="a7561-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="a7561-128">Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step2) de este paso.</span><span class="sxs-lookup"><span data-stu-id="a7561-128">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a7561-129">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="a7561-129">Next step</span></span>

|||
|:-------|:-----|
|![Paso 3](./media/stepnumbers/Step3.png)|[<span data-ttu-id="a7561-131">Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="a7561-131">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
