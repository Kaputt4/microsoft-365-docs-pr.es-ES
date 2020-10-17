---
title: Paso 2. Proporcionar acceso remoto a los servicios y aplicaciones locales
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Asegúrese de que los trabajadores remotos puedan tener acceso a los recursos locales y optimizar el acceso a los servicios en la nube de Microsoft 365.
ms.openlocfilehash: 0e44dad5172672cbe06c0690bcfee27ea153c6c3
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445994"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="2cc53-104">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="2cc53-104">Step 2.</span></span> <span data-ttu-id="2cc53-105">Proporcionar acceso remoto a los servicios y aplicaciones locales</span><span class="sxs-lookup"><span data-stu-id="2cc53-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="2cc53-106">Si en su organización se usa una solución de VPN de acceso remoto, habitualmente una con los servidores VPN en el perímetro de la red y los clientes de VPN se instalados en los dispositivos de los usuarios, los usuarios pueden usar conexiones VPN de acceso remoto para tener acceso a los servidores y aplicaciones locales.</span><span class="sxs-lookup"><span data-stu-id="2cc53-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="2cc53-107">Pero es posible que necesite optimizar el tráfico a los servicios basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cc53-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="2cc53-108">Si los usuarios no usan una solución de VPN, puede usar el proxy de aplicación de Azure Active Directory (Azure AD) y la VPN de punto a sitio de Azure (P2S) para ofrecer acceso en función de si todas las aplicaciones se basan en la web.</span><span class="sxs-lookup"><span data-stu-id="2cc53-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="2cc53-109">Existen tres configuraciones principales:</span><span class="sxs-lookup"><span data-stu-id="2cc53-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="2cc53-110">Ya está usando una solución de VPN de acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="2cc53-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="2cc53-111">No está usando una solución de VPN de acceso remoto, tiene una identidad híbrida y solo necesita el acceso remoto a aplicaciones locales basadas en la web.</span><span class="sxs-lookup"><span data-stu-id="2cc53-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="2cc53-112">No está usando una solución de VPN de acceso remoto y necesita tener acceso a aplicaciones locales, algunas de las cuales no se basan en la web.</span><span class="sxs-lookup"><span data-stu-id="2cc53-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="2cc53-113">Vea este diagrama de flujo para ver las opciones de configuración de acceso remoto descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2cc53-113">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Diagrama de flujo de configuración de acceso remoto](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="2cc53-115">Con conexiones de acceso remoto, también puede usar [Escritorio remoto](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) para conectar a los usuarios a un equipo local.</span><span class="sxs-lookup"><span data-stu-id="2cc53-115">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="2cc53-116">Por ejemplo, un trabajador remoto puede usar Escritorio remoto para conectarse al equipo en su oficina desde su dispositivo Windows, iOS o Android.</span><span class="sxs-lookup"><span data-stu-id="2cc53-116">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="2cc53-117">Una vez que estén conectados de forma remota, podrán usarlo como si estuvieran sentados frente a él.</span><span class="sxs-lookup"><span data-stu-id="2cc53-117">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="2cc53-118">Optimizar el rendimiento de los clientes VPN de acceso remoto a los servicios en la nube de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2cc53-118">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="2cc53-119">Si los trabajadores remotos usan un cliente VPN tradicional para obtener acceso remoto a la red de su organización, compruebe que el cliente VPN tiene compatibilidad de túnel dividido.</span><span class="sxs-lookup"><span data-stu-id="2cc53-119">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="2cc53-120">Sin el túnel dividido, todo el tráfico de trabajo remoto se envía por la conexión VPN, donde debe reenviarse a los dispositivos perimetrales de la organización, procesarse y, después, enviarse por Internet.</span><span class="sxs-lookup"><span data-stu-id="2cc53-120">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Tráfico de red de clientes de VPN sin túneles](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="2cc53-122">El tráfico de Microsoft 365 debe tomar una ruta indirecta en la organización, lo que puede reenviarse a un punto de entrada de la red de Microsoft lejos de la ubicación física del cliente de VPN.</span><span class="sxs-lookup"><span data-stu-id="2cc53-122">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="2cc53-123">Esta ruta indirecta agrega latencia al tráfico de red y reduce el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="2cc53-123">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="2cc53-124">Con el túnel dividido, puede configurar el cliente VPN para excluir determinados tipos de tráfico de la conexión VPN a la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="2cc53-124">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="2cc53-125">Para optimizar el acceso a los recursos en la nube de Microsoft 365, configure los clientes VPN de túnel dividido para excluir el tráfico a los puntos de conexión de Microsoft 365 de la categoría **Optimizar** por la conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="2cc53-125">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="2cc53-126">Para obtener más información, consulte [Office 365 endpoint categories](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories) (Categorías de puntos de conexión de Office 365).</span><span class="sxs-lookup"><span data-stu-id="2cc53-126">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="2cc53-127">Vea la lista de puntos de conexión de la categoría Optimizar [aquí](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="2cc53-127">See the list of Optimize category endpoints [here](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

![Tráfico de red de clientes de VPN sin túneles](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="2cc53-129">Esto permite que el cliente VPN envíe y reciba tráfico esencial de servicio en la nube de Microsoft 365 directamente por Internet y al punto de entrada más cercano a la red de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cc53-129">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="2cc53-130">Para obtener más información e instrucciones, consulte [Optimizar la conectividad de Office 365 para usuarios remotos usando el túnel dividido de VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel??).</span><span class="sxs-lookup"><span data-stu-id="2cc53-130">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel??).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="2cc53-131">Implementación del acceso remoto cuando todas las aplicaciones son aplicaciones web y tiene una identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="2cc53-131">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="2cc53-132">Si los trabajadores remotos no usan un cliente VPN tradicional y las cuentas de usuario y los grupos locales se sincronizan con Azure AD, puede usar el proxy de la aplicación de Azure AD para proporcionar acceso remoto seguro para aplicaciones basadas en web que se encuentren en servidores de intranet.</span><span class="sxs-lookup"><span data-stu-id="2cc53-132">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="2cc53-133">Entre las aplicaciones basadas en web se incluyen los sitios de SharePoint, los servidores de Outlook Web Access, o cualquier otra línea de aplicaciones empresariales basada en web.</span><span class="sxs-lookup"><span data-stu-id="2cc53-133">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="2cc53-134">Estos son los componentes del proxy de la aplicación Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2cc53-134">Here are the components of Azure AD Application Proxy.</span></span>

![Componentes del proxy de la aplicación Azure AD](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="2cc53-136">Para obtener más información, vea este [resumen sobre el proxy de aplicación de Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) y la [tercera parte del vídeo sobre el uso del proxy de aplicación de Azure AD](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security).</span><span class="sxs-lookup"><span data-stu-id="2cc53-136">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) and the [Part 3 video on using Azure AD Application Proxy](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security).</span></span>

>[!Note]
><span data-ttu-id="2cc53-137">El proxy de aplicación de Azure AD no está incluido en una suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cc53-137">Azure AD Application Proxy is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="2cc53-138">Debe pagar para usarlo con una suscripción de Azure por separado.</span><span class="sxs-lookup"><span data-stu-id="2cc53-138">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="2cc53-139">Implementar el acceso remoto cuando no todas las aplicaciones son aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="2cc53-139">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="2cc53-140">Si los trabajadores remotos no usan un cliente VPN tradicional y cualquiera de las aplicaciones no está basada en web, puede usar una red privada virtual punto a sitio (P2S) de Azure.</span><span class="sxs-lookup"><span data-stu-id="2cc53-140">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="2cc53-141">Una conexión VPN de P2S crea una conexión segura desde el dispositivo de un trabajador remoto a la red de la organización a través de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="2cc53-141">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Componentes de la red privada virtual de Azure P2S](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="2cc53-143">Para obtener más información, vea esta [introducción a la red virtual privada de P2S](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="2cc53-143">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

>[!Note]
><span data-ttu-id="2cc53-144">La VPN de Azure P2S no está incluida en una suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cc53-144">Azure P2S VPN is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="2cc53-145">Debe pagar para usarlo con una suscripción de Azure por separado.</span><span class="sxs-lookup"><span data-stu-id="2cc53-145">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="2cc53-146">Implementación de Windows Virtual Desktop para proporcionar acceso remoto para trabajadores remotos con dispositivos personales</span><span class="sxs-lookup"><span data-stu-id="2cc53-146">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="2cc53-147">Para dar servicio a los trabajadores remotos que solo pueden usar sus dispositivos personales y no administrados, use Windows Virtual Desktop en Azure para crear y asignar escritorios virtuales para que los usuarios puedan usarlos desde casa.</span><span class="sxs-lookup"><span data-stu-id="2cc53-147">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span> <span data-ttu-id="2cc53-148">Los equipos virtualizados pueden funcionar exactamente igual que los equipos conectados a la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="2cc53-148">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

![Componentes de Azure en Windows Virtual Desktop](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

<span data-ttu-id="2cc53-150">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="2cc53-150">For more information, see:</span></span> 

- <span data-ttu-id="2cc53-151">[Este resumen sobre Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="2cc53-151">[This overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>
- <span data-ttu-id="2cc53-152">[La segunda parte del vídeo sobre el uso de Windows Virtual Desktop para los trabajadores remotos](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity).</span><span class="sxs-lookup"><span data-stu-id="2cc53-152">[The Part 2 video on using Windows Virtual Desktop for remote workers](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity).</span></span>

>[!Note]
><span data-ttu-id="2cc53-153">Windows Virtual Desktop no está incluido en una suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cc53-153">Windows Virtual Desktop is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="2cc53-154">Debe pagar para usarlo con una suscripción de Azure por separado.</span><span class="sxs-lookup"><span data-stu-id="2cc53-154">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a><span data-ttu-id="2cc53-155">Proteja las conexiones de los servicios de escritorio remoto con la puerta de enlace de servicios de escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="2cc53-155">Protect your Remote Desktop Services connections with the Remote Desktop Services Gateway</span></span>

<span data-ttu-id="2cc53-156">Si usa los servicios de escritorio remoto (RDS) para permitir que los empleados se conecten a equipos con Windows de su red local, debería usar una puerta de enlace de servicios de escritorio remoto de Microsoft en su red perimetral.</span><span class="sxs-lookup"><span data-stu-id="2cc53-156">If you are using Remote Desktop Services (RDS) to allow employees to connect into Windows-based computers on your on-premises network, you should use a Microsoft Remote Desktop Services gateway in your edge network.</span></span> <span data-ttu-id="2cc53-157">La puerta de enlace usa una capa de sockets seguros (SSL) para cifrar las comunicaciones y evitar que el sistema que hospeda los RDS se exponga directamente a Internet.</span><span class="sxs-lookup"><span data-stu-id="2cc53-157">The gateway uses Secure Sockets Layer (SSL) to encrypt communications and prevents the system hosting RDS from being directly exposed to the Internet.</span></span>

![Conexiones de los servicios de escritorio remoto con la puerta de enlace de servicios de escritorio remoto](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

<span data-ttu-id="2cc53-159">Vea [este artículo](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2cc53-159">See [this article](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) for more information.</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="2cc53-160">Recursos técnicos administrativos para el acceso remoto</span><span class="sxs-lookup"><span data-stu-id="2cc53-160">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="2cc53-161">Cómo optimizar rápidamente el tráfico de Office 365 para el personal remoto y reducir la carga de su infraestructura</span><span class="sxs-lookup"><span data-stu-id="2cc53-161">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="2cc53-162">Optimizar la conectividad de Office 365 para usuarios remotos que usan túnel dividido de VPN</span><span class="sxs-lookup"><span data-stu-id="2cc53-162">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?)

## <a name="results-of-step-2"></a><span data-ttu-id="2cc53-163">Resultados del paso 2</span><span class="sxs-lookup"><span data-stu-id="2cc53-163">Results of Step 2</span></span>

<span data-ttu-id="2cc53-164">Después de implementar una solución de acceso remoto para los trabajadores remotos:</span><span class="sxs-lookup"><span data-stu-id="2cc53-164">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="2cc53-165">Configuración de acceso remoto</span><span class="sxs-lookup"><span data-stu-id="2cc53-165">Remote access configuration</span></span> | <span data-ttu-id="2cc53-166">Resultados</span><span class="sxs-lookup"><span data-stu-id="2cc53-166">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="2cc53-167">Se ha establecido una solución de VPN de acceso remoto</span><span class="sxs-lookup"><span data-stu-id="2cc53-167">A remote access VPN solution is in place</span></span> | <span data-ttu-id="2cc53-168">Se configuró el cliente VPN de acceso remoto para túnel dividido y para la categoría Optimizar de los puntos de conexión de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cc53-168">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="2cc53-169">No cuenta con una solución de VPN de acceso remoto y solo necesita el acceso remoto a aplicaciones locales basadas en la web</span><span class="sxs-lookup"><span data-stu-id="2cc53-169">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="2cc53-170">Configuró el proxy de aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="2cc53-170">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="2cc53-171">No está usando una solución de VPN de acceso remoto y necesita tener acceso a las aplicaciones locales, algunas de las cuales no se basan en la web</span><span class="sxs-lookup"><span data-stu-id="2cc53-171">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="2cc53-172">Configuró la red privada virtual de P2S de Azure.</span><span class="sxs-lookup"><span data-stu-id="2cc53-172">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="2cc53-173">Los trabajadores remotos usan sus dispositivos personales desde casa</span><span class="sxs-lookup"><span data-stu-id="2cc53-173">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="2cc53-174">Configuró Windows Virtual Desktop.</span><span class="sxs-lookup"><span data-stu-id="2cc53-174">You have configured Windows Virtual Desktop.</span></span> |
| <span data-ttu-id="2cc53-175">Los trabajadores remotos usan conexiones de RDS a sistemas locales</span><span class="sxs-lookup"><span data-stu-id="2cc53-175">Remote workers are using RDS connections to on-premises systems</span></span> | <span data-ttu-id="2cc53-176">Ha implementado una puerta de enlace de servicios de escritorio remoto en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="2cc53-176">You have deployed a Remote Desktop Services gateway in your edge network.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="2cc53-177">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2cc53-177">Next step</span></span>

<span data-ttu-id="2cc53-178">[![Paso 3: Implementar los servicios de cumplimiento y seguridad de Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="2cc53-178">[![Step 3: Deploy Microsoft 365 security and compliance services](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span></span>

<span data-ttu-id="2cc53-179">Continúe con el [paso 3](empower-people-to-work-remotely-security-compliance.md) para implementar los servicios de seguridad y cumplimiento de Microsoft 365 para proteger sus aplicaciones, datos y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2cc53-179">Continue with [Step 3](empower-people-to-work-remotely-security-compliance.md) to deploy Microsoft 365 security and compliance services to protect your apps, data, and devices.</span></span>

