---
title: 'Paso 4: Configurar la omisión de tráfico'
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
description: Obtenga información y configure los exploradores web y los dispositivos perimetrales para la omisión de tráfico a ubicaciones de confianza de Office 365.
ms.openlocfilehash: f52921fdc0a5329e3fffae687855a653f7026df6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871556"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="a35b2-103">Paso 4: Configurar la omisión de tráfico</span><span class="sxs-lookup"><span data-stu-id="a35b2-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="a35b2-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a35b2-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="a35b2-p101">Como el tráfico de Internet general puede ser peligroso, en las redes de organización típicas se aplica la seguridad con dispositivos perimetrales como servidores proxy, inspección e interrupción SSL, dispositivos de inspección de paquetes y sistemas de prevención de pérdida de datos. En Uso de dispositivos de red o soluciones de terceros para el tráfico de Office 365 encontrará información sobre algunos de los problemas con los dispositivos de interceptación de red.</span><span class="sxs-lookup"><span data-stu-id="a35b2-p101">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. Read about some of the issues with network interception devices at Using third-party network devices or solutions on Office 365 traffic.</span></span>

<span data-ttu-id="a35b2-p102">Pero los nombres de dominio DNS y las direcciones IP que se usan en los servicios basados en la nube de Microsoft 365 son conocidos. Además, el tráfico y los propios servicios están protegidos con muchas características de seguridad. Como esta protección y seguridad ya está aplicada, no es necesario que los dispositivos perimetrales la dupliquen. Los destinos intermedios y el procesamiento de seguridad duplicado para el tráfico de Microsoft 365 pueden reducir considerablemente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a35b2-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="a35b2-p103">El primer paso para eliminar los destinos intermedios y el procesamiento duplicado de la seguridad consiste en identificar el tráfico de Microsoft 365. Microsoft ha definido los siguientes tipos de nombres de dominio DNS e intervalos de direcciones IP, conocidos como puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="a35b2-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="a35b2-p104">Optimizar: obligatorio para la conectividad a todos los servicios de Office 365 y representa más del 75 % del ancho de banda, las conexiones y el volumen de datos de Microsoft 365. Estos puntos de conexión representan los escenarios de Microsoft 365 más sensibles al rendimiento, la latencia y la disponibilidad de la red.</span><span class="sxs-lookup"><span data-stu-id="a35b2-p104">Optimize - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data. These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span>
- <span data-ttu-id="a35b2-115">Permitir: obligatorio para la conectividad a características y servicios específicos de Microsoft 365, pero no tan sensibles al rendimiento y la latencia de la red como los de la categoría Optimizar.</span><span class="sxs-lookup"><span data-stu-id="a35b2-115">Allow - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="a35b2-p105">Predeterminado: representan los servicios y las dependencias de Microsoft 365 que no requieren ninguna optimización. Puede tratar los puntos de conexión de la categoría Predeterminado como tráfico de Internet normal.</span><span class="sxs-lookup"><span data-stu-id="a35b2-p105">Default - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="a35b2-118">Puede encontrar los nombres de dominio DNS y los intervalos de direcciones IP en [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="a35b2-118">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="a35b2-119">Microsoft le recomienda:</span><span class="sxs-lookup"><span data-stu-id="a35b2-119">Microsoft recommends that you:</span></span>

- <span data-ttu-id="a35b2-p106">Usar scripts de Configuración automática de proxy (PAC) en los exploradores de Internet de los equipos locales para omitir los servidores proxy de los nombres de dominio DNS de los servicios basados en la nube de Microsoft 365. Para obtener el script PAC de Microsoft 365 más reciente, vea el script Get-Pacfile de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a35b2-p106">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services. For the latest Microsoft 365 PAC script, see the Get-Pacfile PowerShell script.</span></span>
- <span data-ttu-id="a35b2-p107">Analizar los dispositivos perimetrales para determinar el procesamiento duplicado y configurarlos para reenviar el tráfico a puntos de conexión de la categoría Optimizar y Permitir sin procesamiento. Esto se conoce como omisión de tráfico.</span><span class="sxs-lookup"><span data-stu-id="a35b2-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 
- 
<span data-ttu-id="a35b2-p108">Los dispositivos perimetrales incluyen firewalls, inspección e interrupción SSL, dispositivos de inspección de paquetes y sistemas de prevención de pérdida de datos. Para configurar y actualizar las configuraciones de los dispositivos perimetrales, puede usar un script o una llamada REST para consumir una lista estructurada de puntos de conexión del servicio web Puntos de conexión de Office 365. Para obtener más información, vea [Dirección IP de Office 365 y servicio web de URL](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="a35b2-p108">Edge devices include firewalls, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service. For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="a35b2-p109">Tenga en cuenta que solo se omite el procesamiento de seguridad de red y proxy normal para el tráfico a los puntos de conexión de las categorías Optimizar y Permitir de Microsoft 365. El resto del tráfico general de Internet se dirige a través de un proxy y se somete al procesamiento de seguridad de red existente.</span><span class="sxs-lookup"><span data-stu-id="a35b2-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="a35b2-129">Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step4) de este paso.</span><span class="sxs-lookup"><span data-stu-id="a35b2-129">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a35b2-130">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a35b2-130">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="a35b2-131">Optimizar el rendimiento del servicio de Office 365 y el cliente</span><span class="sxs-lookup"><span data-stu-id="a35b2-131">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



