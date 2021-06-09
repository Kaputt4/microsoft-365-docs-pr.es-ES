---
title: Configurar la red para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Busque vínculos a artículos con información que le ayuden a configurar la red para Microsoft 365, incluida una introducción a la conectividad de red y una lista de puntos de conexión.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693682"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="0e203-103">Configurar la red para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e203-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="0e203-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0e203-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0e203-105">Una parte importante de la incorporación Microsoft 365 es garantizar que las conexiones de red e Internet estén configuradas para un acceso optimizado.</span><span class="sxs-lookup"><span data-stu-id="0e203-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="0e203-106">La configuración de la red local para tener acceso a una nube de Software como servicio (SaaS) distribuida globalmente es diferente de una red tradicional optimizada para el tráfico a centros de datos locales y una conexión central a Internet.</span><span class="sxs-lookup"><span data-stu-id="0e203-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="0e203-107">Use estos artículos para comprender las principales diferencias, así como para modificar los dispositivos perimetrales, los equipos cliente y la red local a fin de obtener el mejor rendimiento para sus usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="0e203-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="0e203-108">Cómo Microsoft 365 de red</span><span class="sxs-lookup"><span data-stu-id="0e203-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="0e203-109">Vea estos artículos para obtener información general sobre la conectividad para Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="0e203-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="0e203-110">Información general de conectividad de red de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e203-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="0e203-111">Principios de conectividad de red de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e203-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="0e203-112">Evaluar la conectividad de red de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e203-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="0e203-113">Para obtener consejos sobre cómo mejorar el rendimiento, vea [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="0e203-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="0e203-114">Compatibilidad Microsoft 365 redes como proveedor de equipos de red</span><span class="sxs-lookup"><span data-stu-id="0e203-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="0e203-p102">Si es un proveedor de equipos de red, únase al [Programa para partners de redes de Office 365](microsoft-365-networking-partner-program.md). Inscríbase en el programa para compilar principios de conectividad de red de Office 365 en sus productos y soluciones.</span><span class="sxs-lookup"><span data-stu-id="0e203-p102">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="0e203-117">Puntos de conexión de Office 365</span><span class="sxs-lookup"><span data-stu-id="0e203-117">Office 365 endpoints</span></span>

<span data-ttu-id="0e203-118">Los puntos de conexión son el conjunto de direcciones IP de destino, nombres de dominio DNS y URL para el tráfico de Office 365 en Internet.</span><span class="sxs-lookup"><span data-stu-id="0e203-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="0e203-p103">Para optimizar el rendimiento de los servicios basados en la nube de Office 365, algunos puntos de conexión necesitan un tratamiento especial por parte de los exploradores cliente y los dispositivos de la red perimetral. Estos dispositivos incluyen firewalls, inspección e interrupción SSL, dispositivos de inspección de paquetes y sistemas de prevención de pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="0e203-p103">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network. These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="0e203-121">Vea [Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md) para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="0e203-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="0e203-p104">Actualmente, hay cinco nubes diferentes de Office 365. En esta tabla se le indicará la lista de puntos de conexión de cada una.</span><span class="sxs-lookup"><span data-stu-id="0e203-p104">There are currently five different Office 365 clouds. This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="0e203-124">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="0e203-124">Endpoints</span></span> | <span data-ttu-id="0e203-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e203-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="0e203-126">Puntos de conexión mundiales</span><span class="sxs-lookup"><span data-stu-id="0e203-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="0e203-127">Puntos de conexión para suscripciones a Office 365 de todo el mundo, que incluyen Government Community Cloud (GCC) de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="0e203-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="0e203-128">Puntos de conexión de DoD de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="0e203-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="0e203-129">Puntos de conexión para las suscripciones del Department of Defense (DoD) de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="0e203-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="0e203-130">Puntos de conexión de GCC High de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="0e203-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="0e203-131">Puntos de conexión para suscripciones a Government Community Cloud High (GCC High) de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="0e203-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="0e203-132">Puntos de conexión de Office 365 operado por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="0e203-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="0e203-133">Puntos de conexión de Office 365 operado por 21Vianet, que está diseñado para satisfacer las necesidades de Office 365 en China.</span><span class="sxs-lookup"><span data-stu-id="0e203-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="0e203-134">Puntos de conexión de Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="0e203-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="0e203-135">Puntos de conexión de una nube independiente en Europa para los clientes con más regulaciones en Alemania, la Unión Europea (UE) y la Asociación Europea de Libre Comercio (AELC).</span><span class="sxs-lookup"><span data-stu-id="0e203-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="0e203-136">Para automatizar la obtención de la lista más reciente de puntos de conexión para su nube de Office 365, vea [Dirección IP de Office 365 y servicio web de URL](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="0e203-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="0e203-137">Para consultar puntos de conexión adicionales, vea estos artículos:</span><span class="sxs-lookup"><span data-stu-id="0e203-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="0e203-138">Puntos de conexión adicionales no incluidos en el servicio web</span><span class="sxs-lookup"><span data-stu-id="0e203-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="0e203-139">Solicitudes de red en Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="0e203-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="0e203-140">Temas adicionales para Microsoft 365 redes</span><span class="sxs-lookup"><span data-stu-id="0e203-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="0e203-141">Vea estos artículos para obtener temas especializados en Microsoft 365 redes:</span><span class="sxs-lookup"><span data-stu-id="0e203-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="0e203-142">Redes de entrega de contenido</span><span class="sxs-lookup"><span data-stu-id="0e203-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="0e203-143">Compatibilidad con IPv6 en servicios de Office 365</span><span class="sxs-lookup"><span data-stu-id="0e203-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="0e203-144">Compatibilidad de NAT con Office 365</span><span class="sxs-lookup"><span data-stu-id="0e203-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="0e203-145">ExpressRoute para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e203-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="0e203-146">Vea estos artículos para obtener información sobre el uso de ExpressRoute para el tráfico de Office 365:</span><span class="sxs-lookup"><span data-stu-id="0e203-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="0e203-147">Azure ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="0e203-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="0e203-148">Implementación de ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="0e203-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="0e203-149">Planeamiento de red con ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="0e203-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="0e203-150">Enrutamiento con ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="0e203-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
