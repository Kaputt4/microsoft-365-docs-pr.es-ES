---
title: Guía básica de redes para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Guía básica para implementar redes de Microsoft 365.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923557"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="0fcdf-103">Guía básica de redes para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0fcdf-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="0fcdf-104">Microsoft 365 para empresas incluye servicios en la nube de colaboración y productividad, Microsoft Intune y muchos servicios de identidad y seguridad de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="0fcdf-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="0fcdf-105">Todos estos servicios en la nube se basan en la seguridad, rendimiento y confiabilidad de conexiones de los dispositivos del cliente a través de Internet o circuitos dedicados.</span><span class="sxs-lookup"><span data-stu-id="0fcdf-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="0fcdf-106">Para hospedar estos servicios y hacer que estén disponibles para los clientes de todo el mundo, Microsoft ha diseñado una infraestructura de red que destaca por el rendimiento e integración.</span><span class="sxs-lookup"><span data-stu-id="0fcdf-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="0fcdf-107">Una parte fundamental de la incorporación de Microsoft 365 es garantizar que las conexiones de red e Internet estén configuradas para un acceso optimizado.</span><span class="sxs-lookup"><span data-stu-id="0fcdf-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="0fcdf-108">La configuración de la red local para tener acceso a una nube de Software como servicio (SaaS) distribuida globalmente es diferente de una red tradicional optimizada para el tráfico a centros de datos locales y una conexión central a Internet.</span><span class="sxs-lookup"><span data-stu-id="0fcdf-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="0fcdf-109">Use estos artículos para comprender las principales diferencias, así como para modificar los dispositivos perimetrales, los equipos cliente y la red local a fin de obtener el mejor rendimiento para sus usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="0fcdf-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="0fcdf-110">Plan</span><span class="sxs-lookup"><span data-stu-id="0fcdf-110">Plan</span></span>

<span data-ttu-id="0fcdf-111">En la fase de planeación de la implementación de redes:</span><span class="sxs-lookup"><span data-stu-id="0fcdf-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="0fcdf-112">Comprender cómo funcionan las redes de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0fcdf-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="0fcdf-113">Evaluar la conectividad de red actual</span><span class="sxs-lookup"><span data-stu-id="0fcdf-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="0fcdf-114">Determinar si ExpressRoute es adecuado para su organización</span><span class="sxs-lookup"><span data-stu-id="0fcdf-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="0fcdf-115">Planear los dispositivos de red</span><span class="sxs-lookup"><span data-stu-id="0fcdf-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="0fcdf-116">Configurar la red para la migración</span><span class="sxs-lookup"><span data-stu-id="0fcdf-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="0fcdf-117">Implementar</span><span class="sxs-lookup"><span data-stu-id="0fcdf-117">Deploy</span></span>

<span data-ttu-id="0fcdf-118">En la fase de implementación de la implementación de red:</span><span class="sxs-lookup"><span data-stu-id="0fcdf-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="0fcdf-119">Asegúrese de que la red empresarial está optimizada para la conectividad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0fcdf-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="0fcdf-120">Agregar los dominios DNS de la organización</span><span class="sxs-lookup"><span data-stu-id="0fcdf-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="0fcdf-121">Optimizar la conectividad con puntos de conexión de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0fcdf-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="0fcdf-122">Optimizar la conectividad de los trabajadores remotos</span><span class="sxs-lookup"><span data-stu-id="0fcdf-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="0fcdf-123">Si es necesario, [configure ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="0fcdf-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="0fcdf-124">Administrar</span><span class="sxs-lookup"><span data-stu-id="0fcdf-124">Manage</span></span>

<span data-ttu-id="0fcdf-125">En la fase de administración de la implementación de redes:</span><span class="sxs-lookup"><span data-stu-id="0fcdf-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="0fcdf-126">Asegúrese de que los dispositivos de red usan los extremos más recientes de Office 365</span><span class="sxs-lookup"><span data-stu-id="0fcdf-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="0fcdf-127">Supervisar y ajustar el rendimiento de las redes</span><span class="sxs-lookup"><span data-stu-id="0fcdf-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="0fcdf-128">Supervisar las conexiones de ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="0fcdf-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="0fcdf-129">Proveedores de equipamiento de red</span><span class="sxs-lookup"><span data-stu-id="0fcdf-129">Network equipment vendors</span></span>

<span data-ttu-id="0fcdf-130">Si es un proveedor de equipamiento de red, únase al Programa de partners de redes [de Microsoft 365](microsoft-365-networking-partner-program.md).</span><span class="sxs-lookup"><span data-stu-id="0fcdf-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="0fcdf-131">Inscríbase en el programa para crear principios de conectividad de red de Microsoft 365 en sus productos y soluciones.</span><span class="sxs-lookup"><span data-stu-id="0fcdf-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="0fcdf-132">Cómo Contoso hizo las redes para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0fcdf-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="0fcdf-133">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [optimizó sus dispositivos de red y conexión a Internet](contoso-networking.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fcdf-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="0fcdf-135">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="0fcdf-135">Next step</span></span>

<span data-ttu-id="0fcdf-136">Inicie la planeación de redes con la introducción a la conectividad de red [de Microsoft 365](microsoft-365-networking-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0fcdf-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>