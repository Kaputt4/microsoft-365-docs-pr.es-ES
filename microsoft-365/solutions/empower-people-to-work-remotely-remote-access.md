---
title: Paso 2. Proporcionar acceso remoto a los servicios y aplicaciones locales
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Asegúrese de que los trabajadores remotos puedan tener acceso a los recursos locales y optimizar el acceso a los servicios en la nube de Microsoft 365.
ms.openlocfilehash: fb91451b52c55f2cad1e0efefe19a044ce1cc37b
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002918"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="5296b-104">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="5296b-104">Step 2.</span></span> <span data-ttu-id="5296b-105">Proporcionar acceso remoto a los servicios y aplicaciones locales</span><span class="sxs-lookup"><span data-stu-id="5296b-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="5296b-106">Si en su organización se usa una solución de VPN de acceso remoto, habitualmente una con los servidores VPN en el perímetro de la red y los clientes de VPN se instalados en los dispositivos de los usuarios, los usuarios pueden usar conexiones VPN de acceso remoto para tener acceso a los servidores y aplicaciones locales.</span><span class="sxs-lookup"><span data-stu-id="5296b-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="5296b-107">Pero es posible que necesite optimizar el tráfico a los servicios basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5296b-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="5296b-108">Si los usuarios no usan una solución de VPN, puede usar el proxy de aplicación de Azure Active Directory (Azure AD) y la VPN de punto a sitio de Azure (P2S) para ofrecer acceso en función de si todas las aplicaciones se basan en la web.</span><span class="sxs-lookup"><span data-stu-id="5296b-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="5296b-109">Existen tres configuraciones principales:</span><span class="sxs-lookup"><span data-stu-id="5296b-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="5296b-110">Ya está usando una solución de VPN de acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="5296b-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="5296b-111">No está usando una solución de VPN de acceso remoto, tiene una identidad híbrida y solo necesita el acceso remoto a aplicaciones locales basadas en la web.</span><span class="sxs-lookup"><span data-stu-id="5296b-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="5296b-112">No está usando una solución de VPN de acceso remoto y necesita tener acceso a las aplicaciones locales, algunas de las cuales no se basan en la web.</span><span class="sxs-lookup"><span data-stu-id="5296b-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="5296b-113">Con conexiones de acceso remoto, también puede usar [Escritorio remoto](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) para conectar a los usuarios a un equipo local.</span><span class="sxs-lookup"><span data-stu-id="5296b-113">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="5296b-114">Por ejemplo, un trabajador remoto puede usar Escritorio remoto para conectarse al equipo en su oficina desde su dispositivo Windows, iOS o Android.</span><span class="sxs-lookup"><span data-stu-id="5296b-114">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="5296b-115">Una vez que estén conectados de forma remota, podrán usarlo como si estuvieran sentados frente a él.</span><span class="sxs-lookup"><span data-stu-id="5296b-115">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="5296b-116">Optimizar el rendimiento de los clientes VPN de acceso remoto a los servicios en la nube de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5296b-116">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="5296b-117">Si los trabajadores remotos usan un cliente VPN tradicional para obtener acceso remoto a la red de su organización, compruebe que el cliente VPN tiene compatibilidad de túnel dividido.</span><span class="sxs-lookup"><span data-stu-id="5296b-117">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="5296b-118">Sin el túnel dividido, todo el tráfico de trabajo remoto se envía por la conexión VPN, donde debe reenviarse a los dispositivos perimetrales de la organización, procesarse y, después, enviarse por Internet.</span><span class="sxs-lookup"><span data-stu-id="5296b-118">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Tráfico de red de clientes de VPN sin túneles](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="5296b-120">El tráfico de Microsoft 365 debe tomar una ruta indirecta en la organización, lo que puede reenviarse a un punto de entrada de la red de Microsoft lejos de la ubicación física del cliente de VPN.</span><span class="sxs-lookup"><span data-stu-id="5296b-120">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="5296b-121">Esta ruta indirecta agrega latencia al tráfico de red y reduce el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="5296b-121">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="5296b-122">Con el túnel dividido, puede configurar el cliente VPN para excluir determinados tipos de tráfico de la conexión VPN a la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="5296b-122">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="5296b-123">Para optimizar el acceso a los recursos en la nube de Microsoft 365, configure los clientes VPN de túnel dividido para excluir el tráfico a los puntos de conexión de Microsoft 365 de la categoría **Optimizar** por la conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="5296b-123">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="5296b-124">Para obtener más información, consulte [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) (Categorías de puntos de conexión de Office 365).</span><span class="sxs-lookup"><span data-stu-id="5296b-124">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="5296b-125">Vea la lista de puntos de conexión de la categoría Optimizar [aquí](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="5296b-125">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![Tráfico de red de clientes de VPN sin túneles](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="5296b-127">Esto permite que el cliente VPN envíe y reciba tráfico esencial de servicio en la nube de Microsoft 365 directamente por Internet y al punto de entrada más cercano a la red de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5296b-127">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="5296b-128">Para obtener más información e instrucciones, consulte [Optimizar la conectividad de Office 365 para usuarios remotos usando el túnel dividido de VPN](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="5296b-128">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="5296b-129">Implementación del acceso remoto cuando todas las aplicaciones son aplicaciones web y tiene una identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="5296b-129">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="5296b-130">Si los trabajadores remotos no usan un cliente VPN tradicional y las cuentas de usuario y los grupos locales se sincronizan con Azure AD, puede usar el proxy de la aplicación de Azure AD para proporcionar acceso remoto seguro para aplicaciones basadas en web que se encuentren en servidores de intranet.</span><span class="sxs-lookup"><span data-stu-id="5296b-130">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="5296b-131">Entre las aplicaciones basadas en web se incluyen los sitios de SharePoint, los servidores de Outlook Web Access, o cualquier otra línea de aplicaciones empresariales basada en web.</span><span class="sxs-lookup"><span data-stu-id="5296b-131">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="5296b-132">Estos son los componentes del proxy de la aplicación Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5296b-132">Here are the components of Azure AD Application Proxy.</span></span>

![Componentes del proxy de la aplicación Azure AD](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="5296b-134">Para más información, vea esta [información general sobre el proxy de aplicación de Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="5296b-134">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="5296b-135">Implementar el acceso remoto cuando no todas las aplicaciones son aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="5296b-135">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="5296b-136">Si los trabajadores remotos no usan un cliente VPN tradicional y cualquiera de las aplicaciones no está basada en web, puede usar una red privada virtual punto a sitio (P2S) de Azure.</span><span class="sxs-lookup"><span data-stu-id="5296b-136">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="5296b-137">Una conexión VPN de P2S crea una conexión segura desde el dispositivo de un trabajador remoto a la red de la organización a través de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="5296b-137">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Componentes de la red privada virtual de Azure P2S](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="5296b-139">Para obtener más información, vea esta [introducción a la red virtual privada de P2S](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="5296b-139">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="5296b-140">Implementación de Windows Virtual Desktop para proporcionar acceso remoto para trabajadores remotos con dispositivos personales</span><span class="sxs-lookup"><span data-stu-id="5296b-140">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="5296b-141">Para dar servicio a los trabajadores remotos que solo pueden usar sus dispositivos personales y no administrados, use Windows Virtual Desktop en Azure para crear y asignar escritorios virtuales para que los usuarios puedan usarlos desde casa.</span><span class="sxs-lookup"><span data-stu-id="5296b-141">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="5296b-142">Los equipos virtualizados pueden funcionar exactamente igual que los equipos conectados a la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="5296b-142">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="5296b-143">Para obtener más información, consulte [esta introducción a Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="5296b-143">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="5296b-144">Recursos técnicos administrativos para el acceso remoto</span><span class="sxs-lookup"><span data-stu-id="5296b-144">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="5296b-145">Cómo optimizar rápidamente el tráfico de Office 365 para el personal remoto y reducir la carga de su infraestructura</span><span class="sxs-lookup"><span data-stu-id="5296b-145">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="5296b-146">Optimizar la conectividad de Office 365 para usuarios remotos que usan túnel dividido de VPN</span><span class="sxs-lookup"><span data-stu-id="5296b-146">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="5296b-147">Resultados del paso 2</span><span class="sxs-lookup"><span data-stu-id="5296b-147">Results of Step 2</span></span>

<span data-ttu-id="5296b-148">Después de implementar una solución de acceso remoto para los trabajadores remotos:</span><span class="sxs-lookup"><span data-stu-id="5296b-148">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="5296b-149">Configuración de acceso remoto</span><span class="sxs-lookup"><span data-stu-id="5296b-149">Remote access configuration</span></span> | <span data-ttu-id="5296b-150">Resultados</span><span class="sxs-lookup"><span data-stu-id="5296b-150">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="5296b-151">Se ha establecido una solución de VPN de acceso remoto</span><span class="sxs-lookup"><span data-stu-id="5296b-151">A remote access VPN solution is in place</span></span> | <span data-ttu-id="5296b-152">Se configuró el cliente VPN de acceso remoto para túnel dividido y para la categoría Optimizar de los puntos de conexión de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5296b-152">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="5296b-153">No cuenta con una solución de VPN de acceso remoto y solo necesita el acceso remoto a aplicaciones locales basadas en la web</span><span class="sxs-lookup"><span data-stu-id="5296b-153">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="5296b-154">Configuró el proxy de aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="5296b-154">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="5296b-155">No está usando una solución de VPN de acceso remoto y necesita tener acceso a las aplicaciones locales, algunas de las cuales no se basan en la web</span><span class="sxs-lookup"><span data-stu-id="5296b-155">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="5296b-156">Configuró la red privada virtual de P2S de Azure.</span><span class="sxs-lookup"><span data-stu-id="5296b-156">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="5296b-157">Los trabajadores remotos usan sus dispositivos personales desde casa</span><span class="sxs-lookup"><span data-stu-id="5296b-157">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="5296b-158">Configuró Windows Virtual Desktop.</span><span class="sxs-lookup"><span data-stu-id="5296b-158">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="5296b-159">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5296b-159">Next step</span></span>

<span data-ttu-id="5296b-160">Continúe con el [Paso 3](empower-people-to-work-remotely-manage-endpoints.md) para administrar los dispositivos, equipos y otros puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="5296b-160">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
