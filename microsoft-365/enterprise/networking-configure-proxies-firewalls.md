---
title: 'Paso 4: Configurar la omisión de tráfico'
f1.keywords:
- NOCSH
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
description: Obtenga información y configure los exploradores web y los dispositivos perimetrales para la omisión de tráfico a ubicaciones de confianza de Office 365.
ms.openlocfilehash: 71f62c5e245962f3514c49477e3cdeda17cb6397
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066696"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="1c95d-103">Paso 4: Configurar la omisión de tráfico</span><span class="sxs-lookup"><span data-stu-id="1c95d-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="1c95d-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1c95d-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1-Red](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="1c95d-106">Como el tráfico de Internet general puede ser peligroso, en las redes de organización típicas se aplica la seguridad con dispositivos perimetrales como servidores proxy, Inspección e Interrupción SSL, dispositivos de inspección de paquetes y sistemas de prevención de pérdida de datos. </span><span class="sxs-lookup"><span data-stu-id="1c95d-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="1c95d-107">Lea sobre algunos de los problemas con los dispositivos de intercepción de red en [Usando dispositivos de red de terceros o soluciones en el tráfico de Office 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="1c95d-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="1c95d-p102">Pero los nombres de dominio DNS y las direcciones IP que se usan en los servicios basados en la nube de Microsoft 365 son conocidos. Además, el tráfico y los propios servicios están protegidos con muchas características de seguridad. Como esta protección y seguridad ya está aplicada, no es necesario que los dispositivos perimetrales la dupliquen. Los destinos intermedios y el procesamiento de seguridad duplicado para el tráfico de Microsoft 365 pueden reducir considerablemente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1c95d-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="1c95d-p103">El primer paso para eliminar los destinos intermedios y el procesamiento duplicado de la seguridad consiste en identificar el tráfico de Microsoft 365. Microsoft ha definido los siguientes tipos de nombres de dominio DNS e intervalos de direcciones IP, conocidos como puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="1c95d-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="1c95d-114">**Optimizar**: obligatorios para la conectividad a todos los servicios de Office 365 y representan más del 75 % del ancho de banda, las conexiones y el volumen de datos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c95d-114">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="1c95d-115">Estos puntos de conexión representan escenarios de Microsoft 365 que son más sensibles al rendimiento, la latencia y la disponibilidad de la red.</span><span class="sxs-lookup"><span data-stu-id="1c95d-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency, and availability.</span></span>
- <span data-ttu-id="1c95d-116">**Permitir**: obligatorios para la conectividad a características y servicios específicos de Microsoft 365, pero no son tan sensibles al rendimiento y la latencia de la red como los de la categoría Optimizar.</span><span class="sxs-lookup"><span data-stu-id="1c95d-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="1c95d-117">**Predeterminados**: representan servicios y dependencias de Microsoft 365 que no requieren ninguna optimización.</span><span class="sxs-lookup"><span data-stu-id="1c95d-117">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization.</span></span> <span data-ttu-id="1c95d-118">Puede tratar los puntos de conexión de la categoría Predeterminados como tráfico de Internet normal.</span><span class="sxs-lookup"><span data-stu-id="1c95d-118">You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="1c95d-119">Puede encontrar los nombres de dominio DNS y los intervalos de direcciones IP en [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="1c95d-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="1c95d-120">Microsoft le recomienda:</span><span class="sxs-lookup"><span data-stu-id="1c95d-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="1c95d-121">Use scripts de Configuración Automática de Proxy (PAC) en los exploradores de Internet de los equipos locales para omitir los servidores proxy de los nombres de dominio DNS de los servicios basados en la nube de Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="1c95d-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services.</span></span> <span data-ttu-id="1c95d-122">Para consultar el último script de Microsoft 365 PAC, consulte [Obtener el paquete de archivos del script de PowerShell](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic). </span><span class="sxs-lookup"><span data-stu-id="1c95d-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="1c95d-p107">Analizar los dispositivos perimetrales para determinar el procesamiento duplicado y configurarlos para reenviar el tráfico a puntos de conexión de la categoría Optimizar y Permitir sin procesamiento. Esto se conoce como omisión de tráfico.</span><span class="sxs-lookup"><span data-stu-id="1c95d-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="1c95d-125">A continuación algunas recomendaciones sobre la infraestructura de red.</span><span class="sxs-lookup"><span data-stu-id="1c95d-125">Here are these recommendations in your network infrastructure.</span></span>

![Recomendaciones para optimizar el tráfico local](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="1c95d-127">Los dispositivos perimetrales incluyen firewalls, Inspección e Interrupción SSL, dispositivos de inspección de paquetes y sistemas de prevención de pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="1c95d-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="1c95d-128">Para configurar y actualizar las configuraciones de los dispositivos perimetrales, puede usar un script o una llamada REST para consumir una lista estructurada de puntos de conexión desde el servicio web de Puntos de conexión de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c95d-128">To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service.</span></span> <span data-ttu-id="1c95d-129">Para obtener más información, consulte[Dirección IP de Office 365 y servicio web de URL ](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="1c95d-129">For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="1c95d-p109">Tenga en cuenta que solo se omite el procesamiento de seguridad de red y proxy normal para el tráfico a los puntos de conexión de las categorías Optimizar y Permitir de Microsoft 365. El resto del tráfico general de Internet se dirige a través de un proxy y se somete al procesamiento de seguridad de red existente.</span><span class="sxs-lookup"><span data-stu-id="1c95d-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="1c95d-132">Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step4) de este paso.</span><span class="sxs-lookup"><span data-stu-id="1c95d-132">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="1c95d-133">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="1c95d-133">Next step</span></span>

|||
|:-------|:-----|
|![Paso 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="1c95d-135">Optimizar el rendimiento del servicio de Office 365 y el cliente</span><span class="sxs-lookup"><span data-stu-id="1c95d-135">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



