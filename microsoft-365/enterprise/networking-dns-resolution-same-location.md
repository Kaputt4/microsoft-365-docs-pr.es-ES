---
title: 'Paso 2: Configurar conexiones a Internet locales para cada oficina'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure su resolución DNS para mejorar el rendimiento.
ms.openlocfilehash: 9ccd5c477b4aeda8e7dcf482cc09c8a357f19f40
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871176"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="bc41d-103">Paso 2: Configurar conexiones a Internet locales para cada oficina</span><span class="sxs-lookup"><span data-stu-id="bc41d-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="bc41d-104">*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="bc41d-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="bc41d-p101">En el paso 2, se asegura de que todas las oficinas tienen conexión local a Internet y usan servidores DNS locales. Estos dos elementos son necesarios para reducir la latencia de la conexión y asegurarse de que los equipos cliente locales establecen conexiones con el punto de entrada más próximo a los servicios basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bc41d-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="bc41d-p102">En las redes tradicionales para grandes organizaciones, el tráfico de Internet viaja a través de la red troncal a una conexión a Internet central. Esto no funciona bien para optimizar el rendimiento de una infraestructura de Software como-servicio (SaaS) distribuida de forma global, que incluye los productos Office 365 y Enterprise Mobility + productos Security (EMS) de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bc41d-p102">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="bc41d-p103">La red global de Microsoft incluye servidores front-end para el conjunto de servicios de nube de Microsoft 365 en todo el mundo. Para obtener el mejor rendimiento, los clientes locales deben acceder a un servidor front-end geográficamente más próximo a ellos, en lugar de enviar el tráfico a través de una red troncal al servidor front-end más próximo a la conexión de Internet central de la organización.</span><span class="sxs-lookup"><span data-stu-id="bc41d-p103">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="bc41d-p104">Para dirigir una solicitud cliente al servidor front-end más cercano geográficamente, los servidores DNS de Microsoft usan las consultas DNS correspondientes a la solicitud de conexión inicial del cliente. Por tanto, para obtener la latencia de red más baja:</span><span class="sxs-lookup"><span data-stu-id="bc41d-p104">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="bc41d-113">Todas las oficinas de la organización deben tener conexiones locales a Internet para el tráfico de red de la categoría [Optimizar](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="bc41d-113">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="bc41d-114">Todas las conexiones locales a Internet deben usar un servidor DNS local de la región para el tráfico de Internet saliente desde esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="bc41d-114">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="bc41d-115">Para obtener más información, vea [Conexiones de red de salida de forma local](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="bc41d-115">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="bc41d-116">Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step2) de este paso.</span><span class="sxs-lookup"><span data-stu-id="bc41d-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="bc41d-117">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="bc41d-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="bc41d-118">Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="bc41d-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
