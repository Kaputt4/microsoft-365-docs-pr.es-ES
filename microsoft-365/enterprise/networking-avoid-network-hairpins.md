---
title: 'Paso 3: Evitar las redirecciones de red'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información y elimine las redirecciones de red para mejorar el rendimiento.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583430"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="a03b1-103">Paso 3: Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="a03b1-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="a03b1-104">*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a03b1-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1-Red](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="a03b1-106">Una [redirección de red](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) ocurre cuando el tráfico vinculado a un destino se dirige por primera vez a otra ubicación intermedia, como una pila de seguridad local, un agente de acceso a la nube o una puerta de enlace web basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="a03b1-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="a03b1-107">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a03b1-107">Here is an example.</span></span>

![Ejemplo de una redirección de red](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="a03b1-109">Una redirección de red también puede deberse a un bajo enrutamiento en Internet debido a los proveedores de servicios de red.</span><span class="sxs-lookup"><span data-stu-id="a03b1-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="a03b1-110">Una redirección de red agrega latencia y puede redirigir potencialmente el tráfico a una localización geográficamente lejana.</span><span class="sxs-lookup"><span data-stu-id="a03b1-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="a03b1-p102">Para optimizar el rendimiento del tráfico a los servicios basados en la nube de Microsoft 365, compruebe si el ISP que proporciona la conexión local a Internet tiene una relación de emparejamiento directa con la Red global de Microsoft cerca de esa ubicación. Estas conexiones no tienen redirecciones de red.</span><span class="sxs-lookup"><span data-stu-id="a03b1-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="a03b1-p103">Si usa servicios de red o seguridad basados en la nube para el tráfico de Microsoft 365, asegúrese de que se evalúa el efecto de la redirección de red y que se entiende su impacto en el rendimiento. Examine lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a03b1-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="a03b1-115">El número y las ubicaciones de los proveedores de servicios a través de los que se reenvía el tráfico en relación con las sucursales y los puntos de emparejamiento de la red global de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a03b1-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="a03b1-116">La calidad de la relación de emparejamiento de red del proveedor de servicios con el ISP y Microsoft</span><span class="sxs-lookup"><span data-stu-id="a03b1-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="a03b1-117">Impacto en el rendimiento del redireccionamiento en la infraestructura del proveedor de servicios</span><span class="sxs-lookup"><span data-stu-id="a03b1-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="a03b1-118">Siempre que sea posible, configure los enrutadores perimetrales para enviar directamente el tráfico de Microsoft 365 de confianza, en lugar de a través de un proxy o túnel mediante un proveedor de seguridad de red de terceros en la nube o basado en la nube que procesa el tráfico de Internet.</span><span class="sxs-lookup"><span data-stu-id="a03b1-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Ejemplo de cómo evitar una redirección de red](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="a03b1-120">Para probar lo cerca que está de un punto de entrada para la red global de Microsoft y lo cerca que está del punto en que la red de su organización se conecta a su Proveedor de servicios de Internet (ISP), use la [Herramienta de integración de red de Office 365](https://connectivity.office.com/).</span><span class="sxs-lookup"><span data-stu-id="a03b1-120">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="a03b1-121">Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step3) de este paso.</span><span class="sxs-lookup"><span data-stu-id="a03b1-121">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a03b1-122">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="a03b1-122">Next step</span></span>

|||
|:-------|:-----|
|![Paso 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="a03b1-124">Configurar la omisión de tráfico</span><span class="sxs-lookup"><span data-stu-id="a03b1-124">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
