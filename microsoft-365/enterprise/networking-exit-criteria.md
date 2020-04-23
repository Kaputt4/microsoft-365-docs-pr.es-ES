---
title: 'Fase 1: Criterios de salida de la infraestructura de red'
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
description: Asegúrese de que la configuración cumple con los criterios de Microsoft 365 Enterprise sobre la infraestructura de red.
ms.openlocfilehash: 6d9133fa6f3c993efe88ea53b412b9a272c1b98b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631494"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="bcced-103">Fase 1: Criterios de salida de la infraestructura de red</span><span class="sxs-lookup"><span data-stu-id="bcced-103">Phase 1: Networking infrastructure exit criteria</span></span>

![Fase 1-Red](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="bcced-105">Asegúrese de que su infraestructura de red cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="bcced-105">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="bcced-106">Obligatorio: la red está preparada para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bcced-106">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="bcced-107">Las oficinas tienen suficiente ancho de banda de internet para el tráfico de Microsoft 365, incluidas la instalación y las actualizaciones de Office 365, Microsoft Intune y Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bcced-107">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates.</span></span>
- <span data-ttu-id="bcced-108">La red general se corresponde a una [arquitectura de referencia de Microsoft 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span><span class="sxs-lookup"><span data-stu-id="bcced-108">Your overall network maps to an [Microsoft 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="bcced-109">Los cambios de la red han sido pilotados y probados y cumplen con los requisitos de latencia de tráfico.</span><span class="sxs-lookup"><span data-stu-id="bcced-109">Your network changes have been piloted and tested and meet with your traffic latency requirements.</span></span>

<span data-ttu-id="bcced-110">Si es necesario, el [paso 1](networking-provide-bandwidth-cloud-services.md) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="bcced-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="bcced-111">Obligatorio: las oficinas locales tienen conexión a Internet local y resolución de nombres</span><span class="sxs-lookup"><span data-stu-id="bcced-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="bcced-p101">Ha configurado cada oficina local con acceso a Internet con un ISP local cuyos servidores DNS usan una dirección IP pública local que identifica su ubicación en Internet. Esto asegura el mejor rendimiento posible para los usuarios que accedan a los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bcced-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="bcced-114">Si no usa un ISP local para cada sucursal, puede verse afectado el rendimiento porque el tráfico de red debe recorrer la estructura de una organización o las solicitudes de datos se procesan mediante servidores front-end remotos.</span><span class="sxs-lookup"><span data-stu-id="bcced-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bcced-115">Cómo probarlo</span><span class="sxs-lookup"><span data-stu-id="bcced-115">How to test</span></span>
<span data-ttu-id="bcced-p102">Use una herramienta o un sitio web desde un dispositivo de esa oficina para determinar la dirección IP pública que está usando el servidor proxy. Por ejemplo, use la página web [What Is My IP Address](https://www.whatismypublicip.com/) (¿Cuál es mi dirección IP?). Esta dirección IP pública asignada por su ISP debería ser geográficamente local. No debe ser de un intervalo de direcciones IP público de una oficina central ni de un proveedor de seguridad de red basado en la nube.</span><span class="sxs-lookup"><span data-stu-id="bcced-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="bcced-120">Si es necesario, el [paso 2](networking-dns-resolution-same-location.md) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="bcced-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a><span data-ttu-id="bcced-121">Opcional: quitar las redirecciones de red innecesarias</span><span class="sxs-lookup"><span data-stu-id="bcced-121">Optional: Unnecessary network hairpins are removed</span></span>

<span data-ttu-id="bcced-p103">Ha examinado las redirecciones de red y ha determinado su impacto en el rendimiento de todas las oficinas. Ha eliminado las redirecciones de red cuando ha sido posible, o bien ha trabajado con su proveedor de red o seguridad de terceros para implementar emparejamiento de Microsoft 365 óptimo para su red.</span><span class="sxs-lookup"><span data-stu-id="bcced-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="bcced-124">Si es necesario, el [paso 3](networking-avoid-network-hairpins.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="bcced-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="bcced-125">Opcional: ha configurado la omisión de tráfico en los exploradores de Internet y los dispositivos perimetrales</span><span class="sxs-lookup"><span data-stu-id="bcced-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="bcced-126">Ha implementado los archivos PAC más recientes en los navegadores de Internet locales para que el tráfico a los nombres de dominio DNS de Microsoft 365 omitan los servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="bcced-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="bcced-127">Ha configurado los dispositivos de red perimetrales, como firewalls, la inspección e interrupción SSL y los dispositivos de inspección de paquetes, para usar la omisión de tráfico o procesar de forma mínima el tráfico a las categorías Optimizar y Permitir de los puntos de conexión de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bcced-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="bcced-128">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="bcced-128">How to test</span></span>

<span data-ttu-id="bcced-129">Use las herramientas de registro de los dispositivos perimetrales de red para asegurarse de que el tráfico a los destinos de Microsoft 365 no se inspecciona, descifra u obstaculiza de otra manera.</span><span class="sxs-lookup"><span data-stu-id="bcced-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="bcced-130">Si es necesario, el [paso 4](networking-configure-proxies-firewalls.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="bcced-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-microsoft-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="bcced-131">Opcional: sus clientes y aplicaciones de Microsoft 365 están configurados para un rendimiento óptimo</span><span class="sxs-lookup"><span data-stu-id="bcced-131">Optional: Your clients and Microsoft 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="bcced-132">Ha optimizado la configuración del Protocolo de control de transmisión (TCP) en los dispositivos de cliente y para los servicios de Exchange Online, Skype Empresarial Online, SharePoint Online y Project Online.</span><span class="sxs-lookup"><span data-stu-id="bcced-132">You have optimized the Transmission Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="bcced-133">Si necesita ayuda con esta opción, vea el [paso 5](networking-optimize-tcp-performance.md).</span><span class="sxs-lookup"><span data-stu-id="bcced-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="bcced-134">Resultados y pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bcced-134">Results and next steps</span></span>

<span data-ttu-id="bcced-135">Los usuarios de la intranet ya están listos para usar los servicios en la nube de Microsoft 365 a través de una ruta de red eficiente y a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="bcced-135">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![Fase 2-Identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="bcced-137">Si sigue las fases de la implementación de extremo a extremo de Microsoft 365 Enterprise, la siguiente fase es la [identidad](identity-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="bcced-137">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
