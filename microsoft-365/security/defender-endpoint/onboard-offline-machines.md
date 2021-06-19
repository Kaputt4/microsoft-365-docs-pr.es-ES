---
title: Incorporar dispositivos sin acceso a Internet a Microsoft Defender para endpoint
ms.reviewer: ''
description: Incorporar dispositivos sin acceso a Internet para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
keywords: onboard, servers, vm, on-premises, oms gateway, log analytics, azure log analytics, mma
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 73110d89c39319825cc8dc8e347d137de52a510a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028384"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="79d34-104">Incorporar dispositivos sin acceso a Internet a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="79d34-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="79d34-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="79d34-105">**Applies to:**</span></span>
- [<span data-ttu-id="79d34-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="79d34-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="79d34-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79d34-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="79d34-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="79d34-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="79d34-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="79d34-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="79d34-110">Para incorporar dispositivos sin acceso a Internet, deberá seguir los siguientes pasos generales:</span><span class="sxs-lookup"><span data-stu-id="79d34-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="79d34-111">Los pasos siguientes solo se aplican a dispositivos que ejecutan versiones anteriores de Windows como: Windows Server 2016 anteriores o anteriores Windows 8.1 versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="79d34-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="79d34-112">Un servidor de puerta de enlace OMS no se puede usar como proxy para dispositivos Windows 10 o Windows Server 2019 desconectados cuando se configura mediante el Registro o GPO de 'TelemetryProxyServer'.</span><span class="sxs-lookup"><span data-stu-id="79d34-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="79d34-113">Para Windows 10 o Windows Server 2019: aunque puede usar TelemetryProxyServer, debe apuntar a un dispositivo o dispositivo proxy estándar.</span><span class="sxs-lookup"><span data-stu-id="79d34-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="79d34-114">Además, Windows 10 o Windows Server 2019 en entornos desconectados deben poder actualizar las listas de confianza de certificados sin conexión a través de un archivo o servidor web interno.</span><span class="sxs-lookup"><span data-stu-id="79d34-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="79d34-115">Para obtener más información acerca de cómo actualizar las CTL sin conexión, vea [Configure a file or web server to download the CTL files](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span><span class="sxs-lookup"><span data-stu-id="79d34-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="79d34-116">Para obtener más información acerca de los métodos de incorporación, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="79d34-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="79d34-117">Incorporar versiones anteriores de Windows</span><span class="sxs-lookup"><span data-stu-id="79d34-117">Onboard previous versions of Windows</span></span>](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="79d34-118">Incorporación de servidores al servicio de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="79d34-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="79d34-119">Configurar las opciones de proxy de dispositivo y de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="79d34-119">Configure device proxy and Internet connectivity settings</span></span>](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premises-devices"></a><span data-ttu-id="79d34-120">Dispositivos locales</span><span class="sxs-lookup"><span data-stu-id="79d34-120">On-premises devices</span></span>

- <span data-ttu-id="79d34-121">Configurar Azure Log Analytics (anteriormente conocido como puerta de enlace OMS) para que actúe como proxy o concentrador:</span><span class="sxs-lookup"><span data-stu-id="79d34-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="79d34-122">Agente de Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="79d34-122">Azure Log Analytics Agent</span></span>](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="79d34-123">[Instalar y configurar el Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) apunta a la clave Defender para endpoint workspace & id.</span><span class="sxs-lookup"><span data-stu-id="79d34-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="79d34-124">Dispositivos sin conexión en la misma red de Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="79d34-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="79d34-125">Configure MMA para que apunte a:</span><span class="sxs-lookup"><span data-stu-id="79d34-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="79d34-126">IP de Azure Log Analytics como proxy</span><span class="sxs-lookup"><span data-stu-id="79d34-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="79d34-127">Identificador de la clave de área de & defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="79d34-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="79d34-128">Máquinas virtuales de Azure</span><span class="sxs-lookup"><span data-stu-id="79d34-128">Azure virtual machines</span></span>
- <span data-ttu-id="79d34-129">Configurar y habilitar el área [de trabajo de Azure Log Analytics](/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="79d34-129">Configure and enable [Azure Log Analytics workspace](/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="79d34-130">Configurar Azure Log Analytics Gateway (anteriormente conocida como puerta de enlace OMS) para que actúe como proxy o concentrador:</span><span class="sxs-lookup"><span data-stu-id="79d34-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="79d34-131">Puerta de enlace de Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="79d34-131">Azure Log Analytics Gateway</span></span>](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="79d34-132">[Instalar y configurar el Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) apunta a la clave Defender para endpoint workspace & id.</span><span class="sxs-lookup"><span data-stu-id="79d34-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="79d34-133">Máquinas virtuales de Azure sin conexión en la misma red de OMS Gateway</span><span class="sxs-lookup"><span data-stu-id="79d34-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="79d34-134">Configurar la IP de Azure Log Analytics como proxy</span><span class="sxs-lookup"><span data-stu-id="79d34-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="79d34-135">Identificador de clave de área de trabajo de Azure Log Analytics & de trabajo</span><span class="sxs-lookup"><span data-stu-id="79d34-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="79d34-136">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="79d34-136">Azure Defender</span></span>
      - [<span data-ttu-id="79d34-137">Área de trabajo de análisis \> de registro de directivas de seguridad</span><span class="sxs-lookup"><span data-stu-id="79d34-137">Security Policy \> Log Analytics Workspace</span></span>](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="79d34-138">Detección de \> amenazas Permitir que Defender for Endpoint acceda a mis datos</span><span class="sxs-lookup"><span data-stu-id="79d34-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="79d34-139">Para obtener más información, vea [Trabajar con directivas de seguridad](/azure/security-center/tutorial-security-policy).</span><span class="sxs-lookup"><span data-stu-id="79d34-139">For more information, see [Working with security policies](/azure/security-center/tutorial-security-policy).</span></span>
