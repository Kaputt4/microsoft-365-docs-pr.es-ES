---
title: 'Fase 1: Criterios de salida de la infraestructura de red'
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
description: Asegúrese de que la configuración cumple con los criterios de Microsoft 365 Enterprise sobre la infraestructura de red.
ms.openlocfilehash: 8161fa2b92ffb4c7c4713e9356c0bc1bfec39d07
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871148"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="41fc6-103">Fase 1: Criterios de salida de la infraestructura de red</span><span class="sxs-lookup"><span data-stu-id="41fc6-103">Phase 1: Networking infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="41fc6-104">Si su infraestructura de red cumple con las siguientes condiciones, está listo para pasar a la fase 2.</span><span class="sxs-lookup"><span data-stu-id="41fc6-104">If your networking infrastructure meets the following conditions, you’re ready to move to Phase 2.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="41fc6-105">Obligatorio: la red está preparada para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="41fc6-105">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="41fc6-106">Las oficinas tienen suficiente ancho de banda de Internet para el tráfico de Microsoft 365, incluidas la instalación y las actualizaciones de Office 365, Microsoft Intune y Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="41fc6-106">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="41fc6-107">Oficinas centrales para todo el tráfico de Internet general</span><span class="sxs-lookup"><span data-stu-id="41fc6-107">Central offices for all general Internet traffic</span></span>
- <span data-ttu-id="41fc6-108">Sucursales para el tráfico del punto de conexión de la categoría Optimizar</span><span class="sxs-lookup"><span data-stu-id="41fc6-108">Branch offices for Optimize category endpoint traffic</span></span>
- <span data-ttu-id="41fc6-109">La red general se corresponde a una arquitectura de referencia de Office 365</span><span class="sxs-lookup"><span data-stu-id="41fc6-109">Your overall network maps to an Office 365 reference architecture</span></span>

<span data-ttu-id="41fc6-110">Si es necesario, el [paso 1](networking-provide-bandwidth-cloud-services.md) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="41fc6-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="41fc6-111">Obligatorio: las oficinas locales tienen conexión a Internet local y resolución de nombres</span><span class="sxs-lookup"><span data-stu-id="41fc6-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="41fc6-p101">Ha configurado cada oficina local con acceso a Internet con un ISP local cuyos servidores DNS usan una dirección IP pública local que identifica su ubicación en Internet. Esto asegura el mejor rendimiento posible para los usuarios que accedan a Office 365 e Intune.</span><span class="sxs-lookup"><span data-stu-id="41fc6-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="41fc6-114">Si no usa un ISP local para cada sucursal, puede verse afectado el rendimiento porque el tráfico de red debe recorrer la estructura de una organización o las solicitudes de datos se procesan mediante servidores front-end remotos.</span><span class="sxs-lookup"><span data-stu-id="41fc6-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41fc6-115">Cómo probarlo</span><span class="sxs-lookup"><span data-stu-id="41fc6-115">How to test</span></span>
<span data-ttu-id="41fc6-p102">Use una herramienta o un sitio web desde un dispositivo de esa oficina para determinar la dirección IP pública que está usando el servidor proxy. Por ejemplo, use la página web [What Is My IP Address](https://www.whatismypublicip.com/) (¿Cuál es mi dirección IP?). Esta dirección IP pública asignada por su ISP debería ser geográficamente local. No debe ser de un intervalo de direcciones IP público de una oficina central ni de un proveedor de seguridad de red basado en la nube.</span><span class="sxs-lookup"><span data-stu-id="41fc6-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="41fc6-120">Si es necesario, el [paso 2](networking-dns-resolution-same-location.md) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="41fc6-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unneeded-network-hairpins-are-removed"></a><span data-ttu-id="41fc6-121">Opcional: eliminación de las redirecciones de red innecesarias</span><span class="sxs-lookup"><span data-stu-id="41fc6-121">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="41fc6-p103">Ha examinado las redirecciones de red y ha determinado su impacto en el rendimiento de todas las oficinas. Ha eliminado las redirecciones de red cuando ha sido posible, o bien ha trabajado con su proveedor de red o seguridad de terceros para implementar emparejamiento de Microsoft 365 óptimo para su red.</span><span class="sxs-lookup"><span data-stu-id="41fc6-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="41fc6-124">Si es necesario, el [paso 3](networking-avoid-network-hairpins.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="41fc6-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="41fc6-125">Opcional: ha configurado la omisión de tráfico en los exploradores de Internet y los dispositivos perimetrales</span><span class="sxs-lookup"><span data-stu-id="41fc6-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="41fc6-126">Ha implementado los archivos PAC más recientes en los navegadores de Internet locales para que el tráfico a los nombres de dominio DNS de Microsoft 365 omitan los servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="41fc6-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="41fc6-127">Ha configurado los dispositivos de red perimetrales, como firewalls, la inspección e interrupción SSL y los dispositivos de inspección de paquetes, para usar la omisión de tráfico o procesar de forma mínima el tráfico a las categorías Optimizar y Permitir de los puntos de conexión de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41fc6-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="41fc6-128">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="41fc6-128">How to test</span></span>

<span data-ttu-id="41fc6-129">Use las herramientas de registro de los dispositivos perimetrales de red para asegurarse de que el tráfico a los destinos de Microsoft 365 no se inspecciona, descifra u obstaculiza de otra manera.</span><span class="sxs-lookup"><span data-stu-id="41fc6-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="41fc6-130">Si es necesario, el [paso 4](networking-configure-proxies-firewalls.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="41fc6-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="41fc6-131">Opcional: sus clientes y aplicaciones de Office 365 están configurados para un rendimiento óptimo</span><span class="sxs-lookup"><span data-stu-id="41fc6-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="41fc6-132">Ha optimizado la configuración del Protocolo de control de transmisión (TCP) en los dispositivos cliente y para los servicios de Exchange Online, Skype Empresarial Online, SharePoint Online y Project Online.</span><span class="sxs-lookup"><span data-stu-id="41fc6-132">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="41fc6-133">Si es necesario, el [paso 5](networking-optimize-tcp-performance.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="41fc6-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="next-phase"></a><span data-ttu-id="41fc6-134">Fase siguiente</span><span class="sxs-lookup"><span data-stu-id="41fc6-134">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="41fc6-135">La siguiente fase del proceso de implementación integral de Microsoft 365 Enterprise es la [identidad](identity-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="41fc6-135">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [identity](identity-infrastructure.md).</span></span> |
