---
title: Incorporación de servidores de Windows al servicio microsoft defender para puntos de conexión
description: Incorpore los servidores Windows para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoints.
keywords: servidor incorporado, servidor, 2012r2, 2016, 2019, incorporación de servidores, administración de dispositivos, configuración de servidores de Windows ATP, incorporación de servidores de Microsoft Defender para endpoints, incorporación de servidores de Microsoft Defender para endpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bd92b44892b49a007316acb97296a44514db0578
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069739"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="c3bb5-104">Incorporación de servidores de Windows al servicio microsoft defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="c3bb5-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c3bb5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c3bb5-105">**Applies to:**</span></span>

- <span data-ttu-id="c3bb5-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="c3bb5-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="c3bb5-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c3bb5-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="c3bb5-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c3bb5-108">Windows Server 2016</span></span>
- <span data-ttu-id="c3bb5-109">Windows Server (SAC) versión 1803 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c3bb5-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="c3bb5-110">Windows Server 2019 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c3bb5-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="c3bb5-111">Edición principal de Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c3bb5-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="c3bb5-112">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c3bb5-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3bb5-113">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


<span data-ttu-id="c3bb5-114">Defender for Endpoint amplía la compatibilidad para incluir también el sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="c3bb5-115">Esta compatibilidad proporciona capacidades avanzadas de detección de ataques e investigación sin problemas a través de la consola del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="c3bb5-116">Para obtener instrucciones prácticas sobre lo que debe haber para las licencias y la infraestructura, consulta Protección de los servidores [windows con Defender para endpoint.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="c3bb5-117">Para obtener instrucciones sobre cómo descargar y usar líneas base de seguridad de Windows para servidores Windows, consulta [Líneas base de seguridad de Windows](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="c3bb5-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 y Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c3bb5-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="c3bb5-119">Puedes incorporar Windows Server 2008 R2 SP1, Windows Server 2012 R2 y Windows Server 2016 a Defender para endpoint mediante cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="c3bb5-120">**Opción 1:** [Incorporación mediante la instalación y configuración de Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="c3bb5-121">**Opción 2:** [Incorporación a través del Centro de seguridad de Azure](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="c3bb5-122">**Opción 3:** [Incorporación a través de Microsoft Endpoint Manager versión 2002 y versiones posteriores](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>


<span data-ttu-id="c3bb5-123">Después de completar los pasos de incorporación con cualquiera de las opciones proporcionadas, deberá configurar y actualizar los clientes de [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>


> [!NOTE]
> <span data-ttu-id="c3bb5-124">La licencia de servidor independiente de Defender for Endpoint es necesaria, por nodo, para incorporar un servidor Windows a través de Microsoft Monitoring Agent (opción 1) o a través de Microsoft Endpoint Manager (opción 3).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="c3bb5-125">Como alternativa, se requiere una licencia de Azure Defender para servidores, por nodo, para incorporar un servidor Windows a través del Centro de seguridad de Azure (opción 2), consulte Características admitidas disponibles en [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="c3bb5-126">Opción 1: Incorporación mediante la instalación y configuración de Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>
<span data-ttu-id="c3bb5-127">Tendrás que instalar y configurar MMA para que los servidores Windows informen los datos del sensor a Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="c3bb5-128">Para obtener más información, vea [Recopilar datos de registro con el agente de Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="c3bb5-129">Si ya está usando System Center Operations Manager (SCOM) o Azure Monitor (anteriormente conocido como Operations Management Suite (OMS)), adjunte Microsoft Monitoring Agent (MMA) para informar al área de trabajo de Defender para Endpoint mediante la compatibilidad con multiconsulta.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="c3bb5-130">En general, deberá seguir los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-130">In general, you'll need to take the following steps:</span></span>
1. <span data-ttu-id="c3bb5-131">Cumpla los requisitos de incorporación descritos en **la sección Antes de comenzar.**</span><span class="sxs-lookup"><span data-stu-id="c3bb5-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="c3bb5-132">Active la supervisión del servidor desde el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="c3bb5-133">Instale y configure MMA para que el servidor informe los datos del sensor a Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="c3bb5-134">Configurar y actualizar clientes de System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-134">Configure and update System Center Endpoint Protection clients.</span></span>


> [!TIP]
> <span data-ttu-id="c3bb5-135">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="c3bb5-136">Para obtener más información, vea [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>


#### <a name="before-you-begin"></a><span data-ttu-id="c3bb5-137">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c3bb5-137">Before you begin</span></span> 
<span data-ttu-id="c3bb5-138">Realice los siguientes pasos para cumplir los requisitos de incorporación:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

 - <span data-ttu-id="c3bb5-139">Para Windows Server 2008 R2 SP1 o Windows Server 2012 R2, asegúrese de instalar la siguiente revisión:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>
    - [<span data-ttu-id="c3bb5-140">Actualización de la experiencia del cliente y telemetría de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c3bb5-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - <span data-ttu-id="c3bb5-141">Además, para Windows Server 2008 R2 SP1, asegúrate de cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-141">In addition, for Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>
    - <span data-ttu-id="c3bb5-142">Instalar el paquete [acumulativo de actualizaciones mensuales de febrero](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
    - <span data-ttu-id="c3bb5-143">Instalar [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

 - <span data-ttu-id="c3bb5-144">Para Windows Server 2008 R2 SP1 y Windows Server 2012 R2: Configurar y actualizar clientes de [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-144">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3bb5-145">Este paso solo es necesario si su organización usa System Center Endpoint Protection (SCEP) y está incorporando Windows Server 2008 R2 SP1 y Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-145">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="c3bb5-146">Instalar y configurar Microsoft Monitoring Agent (MMA) para informar de los datos del sensor a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c3bb5-146">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="c3bb5-147">Descargue el archivo de instalación del agente: agente de [Windows 64 bits](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-147">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="c3bb5-148">Con el identificador de área de trabajo y la clave área de trabajo obtenidas en el procedimiento anterior, elija cualquiera de los siguientes métodos de instalación para instalar el agente en el servidor Windows:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-148">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="c3bb5-149">[Instale manualmente el agente mediante el programa de instalación](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-149">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
    <span data-ttu-id="c3bb5-150">En la **página Opciones de configuración del** agente, elija Conectar el agente a Azure Log Analytics **(OMS).**</span><span class="sxs-lookup"><span data-stu-id="c3bb5-150">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="c3bb5-151">[Instale el agente mediante la línea de comandos](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-151">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="c3bb5-152">[Configure el agente mediante un script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-152">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="c3bb5-153">Si es cliente de [Us Government](gov.md), en "Azure Cloud" tendrá que elegir "Azure US Government" si usa el asistente para la instalación, o si usa una línea de comandos o un script: establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-153">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="c3bb5-154">Configurar el proxy del servidor Windows y la configuración de conectividad a Internet si es necesario</span><span class="sxs-lookup"><span data-stu-id="c3bb5-154">Configure Windows server proxy and Internet connectivity settings if needed</span></span>
<span data-ttu-id="c3bb5-155">Si los servidores necesitan usar un proxy para comunicarse con Defender for Endpoint, use uno de los métodos siguientes para configurar la MMA para usar el servidor proxy:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-155">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>


- [<span data-ttu-id="c3bb5-156">Configurar la MMA para usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="c3bb5-156">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="c3bb5-157">Configurar Windows para usar un servidor proxy para todas las conexiones</span><span class="sxs-lookup"><span data-stu-id="c3bb5-157">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="c3bb5-158">Si hay un proxy o firewall en uso, asegúrese de que los servidores puedan tener acceso a todas las direcciones URL del servicio de Microsoft Defender para endpoints directamente y sin interceptación SSL.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-158">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="c3bb5-159">Para obtener más información, vea [habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-159">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="c3bb5-160">El uso de la interceptación SSL impedirá que el sistema se comunique con el servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-160">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span> 

<span data-ttu-id="c3bb5-161">Una vez completado, deberías ver los servidores de Windows incorporados en el portal en una hora.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-161">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="c3bb5-162">Opción 2: Incorporar servidores windows a través del Centro de seguridad de Azure</span><span class="sxs-lookup"><span data-stu-id="c3bb5-162">Option 2: Onboard Windows servers through Azure Security Center</span></span>
1. <span data-ttu-id="c3bb5-163">En el panel de navegación del Centro de seguridad de Microsoft Defender, seleccione **Configuración**  >  **Incorporación de administración de**  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-163">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="c3bb5-164">Selecciona **Windows Server 2008 R2 SP1, 2012 R2 y 2016** como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-164">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="c3bb5-165">Haga **clic en Servidores integrados en El Centro de seguridad de Azure**.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-165">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="c3bb5-166">Siga las instrucciones de incorporación en [Microsoft Defender para Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-166">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

<span data-ttu-id="c3bb5-167">Después de completar los pasos de incorporación, deberá configurar y actualizar los clientes de [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-167">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> - <span data-ttu-id="c3bb5-168">Para que la incorporación a través de Azure Defender para servidores (anteriormente Azure Security Center Standard Edition) funcione como se esperaba, el servidor debe tener una clave y un área de trabajo adecuadas configuradas dentro de la configuración de Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-168">For onboarding via Azure Defender for Servers (previously Azure Security Center Standard Edition) to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="c3bb5-169">Una vez configurado, el módulo de administración de nube adecuado se implementa en el equipo y el proceso de sensor (MsSenseS.exe) se implementará e iniciará.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-169">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span> 
> - <span data-ttu-id="c3bb5-170">Esto también es necesario si el servidor está configurado para usar un servidor de puerta de enlace OMS como proxy.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-170">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="c3bb5-171">Opción 3: Incorporar servidores windows a través de Microsoft Endpoint Manager versión 2002 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c3bb5-171">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>
<span data-ttu-id="c3bb5-172">Puedes incorporar Windows Server 2012 R2 y Windows Server 2016 con Microsoft Endpoint Manager versión 2002 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-172">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="c3bb5-173">Para obtener más información, vea [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-173">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="c3bb5-174">Después de completar los pasos de incorporación, deberá configurar y actualizar los clientes de [System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-174">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="c3bb5-175">Windows Server (SAC) versión 1803, Windows Server 2019 y Windows Server 2019 Core edition</span><span class="sxs-lookup"><span data-stu-id="c3bb5-175">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>
<span data-ttu-id="c3bb5-176">Puedes incorporar Windows Server (SAC) versión 1803, Windows Server 2019 o Windows Server 2019 Core Edition mediante los siguientes métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-176">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="c3bb5-177">Script local</span><span class="sxs-lookup"><span data-stu-id="c3bb5-177">Local script</span></span>](configure-endpoints-script.md) 
- [<span data-ttu-id="c3bb5-178">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="c3bb5-178">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="c3bb5-179">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c3bb5-179">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="c3bb5-180">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="c3bb5-180">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="c3bb5-181">Scripts de incorporación de VDI para dispositivos no persistentes</span><span class="sxs-lookup"><span data-stu-id="c3bb5-181">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
> - <span data-ttu-id="c3bb5-182">El paquete de incorporación para Windows Server 2019 a través de Microsoft Endpoint Manager actualmente incluye un script.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-182">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="c3bb5-183">Para obtener más información sobre cómo implementar scripts en Configuration Manager, vea [Paquetes y programas en Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-183">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="c3bb5-184">Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-184">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="c3bb5-185">Para una implementación de producción, se recomienda usar la directiva de grupo o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-185">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="c3bb5-186">La compatibilidad con Windows Server proporciona información más detallada sobre las actividades del servidor, la cobertura para la detección de ataques de kernel y memoria y habilita acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-186">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="c3bb5-187">Configura Defender para la incorporación de puntos de conexión en el servidor Windows con las mismas herramientas y métodos para dispositivos Con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-187">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="c3bb5-188">Para obtener más información, [consulta Incorporación de dispositivos Windows 10](configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-188">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="c3bb5-189">Si está ejecutando una solución antimalware de terceros, deberá aplicar la siguiente configuración del modo pasivo antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-189">If you're running a third-party antimalware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="c3bb5-190">Compruebe que se configuró correctamente:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-190">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="c3bb5-191">Establezca la siguiente entrada del Registro:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-191">Set the following registry entry:</span></span>
       - <span data-ttu-id="c3bb5-192">Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="c3bb5-192">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="c3bb5-193">Nombre: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="c3bb5-193">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="c3bb5-194">Tipo: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c3bb5-194">Type: REG_DWORD</span></span>
       - <span data-ttu-id="c3bb5-195">Value: 1</span><span class="sxs-lookup"><span data-stu-id="c3bb5-195">Value: 1</span></span>

    1. <span data-ttu-id="c3bb5-196">Ejecute el siguiente comando de PowerShell para comprobar que se configuró el modo pasivo:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-196">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="c3bb5-197">Confirme que se encuentra un evento reciente que contiene el evento de modo pasivo:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-197">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Imagen del resultado de comprobación del modo pasivo](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="c3bb5-199">Ejecute el siguiente comando para comprobar si Microsoft Defender AV está instalado:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-199">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="c3bb5-200">Si el resultado es "El servicio especificado no existe como servicio instalado", tendrá que instalar Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-200">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="c3bb5-201">Para obtener más información, [consulta Antivirus de Microsoft Defender en Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-201">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>
    
    <span data-ttu-id="c3bb5-202">Para obtener información sobre cómo usar la directiva de grupo para configurar y administrar Antivirus de Microsoft Defender en los servidores windows, consulta Usar la configuración de directiva de grupo para configurar y administrar [Antivirus de Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-202">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

<br>

## <a name="integration-with-azure-security-center"></a><span data-ttu-id="c3bb5-203">Integración con Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="c3bb5-203">Integration with Azure Security Center</span></span>
<span data-ttu-id="c3bb5-204">Defender for Endpoint se puede integrar con Azure Security Center para proporcionar una solución completa de protección de windows server.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-204">Defender for Endpoint can integrate with Azure Security Center to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="c3bb5-205">Con esta integración, Azure Security Center puede usar la potencia de Defender para Endpoint para proporcionar una mejor detección de amenazas para servidores Windows.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-205">With this integration, Azure Security Center can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="c3bb5-206">En esta integración se incluyen las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-206">The following capabilities are included in this integration:</span></span>
- <span data-ttu-id="c3bb5-207">Incorporación automatizada: el sensor defender para puntos de conexión se habilita automáticamente en los servidores Windows que están incorporados al Centro de seguridad de Azure.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-207">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Security Center.</span></span> <span data-ttu-id="c3bb5-208">Para obtener más información sobre la incorporación de Azure Security Center, consulte [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-208">For more information on Azure Security Center onboarding, see [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3bb5-209">La incorporación automatizada solo se aplica a Windows Server 2008 R2 SP1, Windows Server 2012 R2 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-209">Automated onboarding is only applicable for Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016.</span></span>

- <span data-ttu-id="c3bb5-210">Los servidores windows supervisados por Azure Security Center también estarán disponibles en Defender para endpoint: El Centro de seguridad de Azure se conecta perfectamente al inquilino de Defender for Endpoint, lo que proporciona una vista única entre clientes y servidores.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-210">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="c3bb5-211">Además, las alertas de Defender for Endpoint estarán disponibles en la consola del Centro de seguridad de Azure.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-211">In addition, Defender for Endpoint alerts will be available in the Azure Security Center console.</span></span>
- <span data-ttu-id="c3bb5-212">Investigación del servidor: los clientes del Centro de seguridad de Azure pueden acceder al Centro de seguridad de Microsoft Defender para realizar una investigación detallada para descubrir el ámbito de una posible infracción.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-212">Server investigation -  Azure Security Center customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="c3bb5-213">Cuando usa Azure Security Center para supervisar los servidores, se crea automáticamente un inquilino de Defender for Endpoint (en Estados Unidos para usuarios estadounidenses, en la UE para usuarios europeos y británicos).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-213">When you use Azure Security Center to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="c3bb5-214">Los datos recopilados por Defender para endpoint se almacenan en la ubicación geográfica del inquilino tal como se identifica durante el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-214">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="c3bb5-215">Si usa Defender para endpoint antes de usar Azure Security Center, los datos se almacenarán en la ubicación que especificó al crear el espacio empresarial, incluso si se integra con Azure Security Center más adelante.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-215">If you use Defender for Endpoint before using Azure Security Center, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Security Center at a later time.</span></span>
> - <span data-ttu-id="c3bb5-216">Una vez configurado, no se puede cambiar la ubicación donde se almacenan los datos.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-216">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="c3bb5-217">Si necesita mover los datos a otra ubicación, póngase en contacto con el soporte técnico de Microsoft para restablecer el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-217">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="c3bb5-218">La supervisión de extremo de servidor que utiliza esta integración se ha deshabilitado para los clientes GCC de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-218">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="c3bb5-219">Configurar y actualizar clientes de System Center Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="c3bb5-219">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="c3bb5-220">Defender for Endpoint se integra con System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-220">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="c3bb5-221">La integración proporciona visibilidad a las detecciones de malware y para detener la propagación de un ataque en la organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-221">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="c3bb5-222">Se requieren los siguientes pasos para habilitar esta integración:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-222">The following steps are required to enable this integration:</span></span>
- <span data-ttu-id="c3bb5-223">Instale la actualización de la plataforma antimalware de enero de [2017 para los clientes de Endpoint Protection](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-223">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="c3bb5-224">[Configure la pertenencia al servicio de protección](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) en la nube del cliente SCEP a la **configuración** Avanzada.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-224">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

<br>

## <a name="offboard-windows-servers"></a><span data-ttu-id="c3bb5-225">Servidores de Windows fuera de la tabla</span><span class="sxs-lookup"><span data-stu-id="c3bb5-225">Offboard Windows servers</span></span>
<span data-ttu-id="c3bb5-226">Puedes salir de Windows Server (SAC), Windows Server 2019 y Windows Server 2019 Core edition en el mismo método disponible para dispositivos cliente de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-226">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="c3bb5-227">Para otras versiones de Windows Server, tienes dos opciones para salir de los servidores windows desde el servicio:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-227">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>
- <span data-ttu-id="c3bb5-228">Desinstalar el agente mma</span><span class="sxs-lookup"><span data-stu-id="c3bb5-228">Uninstall the MMA agent</span></span>
- <span data-ttu-id="c3bb5-229">Quitar la configuración del área de trabajo de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3bb5-229">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="c3bb5-230">La offboarding hace que el servidor Windows deje de enviar datos del sensor al portal, pero los datos del servidor Windows, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-230">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="c3bb5-231">Desinstalar servidores windows desinstalando el agente mma</span><span class="sxs-lookup"><span data-stu-id="c3bb5-231">Uninstall Windows servers by uninstalling the MMA agent</span></span>
<span data-ttu-id="c3bb5-232">Para salir del servidor Windows, puedes desinstalar el agente mma del servidor Windows o desasoyérselo de los informes a tu área de trabajo de Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-232">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="c3bb5-233">Después de desactivar el agente, el servidor Windows ya no enviará datos del sensor a Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-233">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="c3bb5-234">Para obtener más información, vea [Para deshabilitar un agente](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span><span class="sxs-lookup"><span data-stu-id="c3bb5-234">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="c3bb5-235">Quitar la configuración del área de trabajo de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3bb5-235">Remove the Defender for Endpoint workspace configuration</span></span>
<span data-ttu-id="c3bb5-236">Para salir del servidor Windows, puedes usar cualquiera de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-236">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="c3bb5-237">Quitar la configuración del área de trabajo de Defender for Endpoint del agente mma</span><span class="sxs-lookup"><span data-stu-id="c3bb5-237">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="c3bb5-238">Ejecutar un comando de PowerShell para quitar la configuración</span><span class="sxs-lookup"><span data-stu-id="c3bb5-238">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="c3bb5-239">Quitar la configuración del área de trabajo de Defender for Endpoint del agente mma</span><span class="sxs-lookup"><span data-stu-id="c3bb5-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="c3bb5-240">En las **propiedades del agente de supervisión de Microsoft,** seleccione la pestaña Azure Log Analytics **(OMS).**</span><span class="sxs-lookup"><span data-stu-id="c3bb5-240">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="c3bb5-241">Seleccione el área de trabajo Defender para extremo y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-241">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Imagen de las propiedades del agente de supervisión de Microsoft](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="c3bb5-243">Ejecutar un comando de PowerShell para quitar la configuración</span><span class="sxs-lookup"><span data-stu-id="c3bb5-243">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="c3bb5-244">Obtener el id. de área de trabajo:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-244">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="c3bb5-245">En el panel de navegación, seleccione **Configuración**  >  **incorporación**.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-245">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="c3bb5-246">Selecciona **Windows Server 2008 R2 SP1, 2012 R2 y 2016** como sistema operativo y obtén el identificador de área de trabajo:</span><span class="sxs-lookup"><span data-stu-id="c3bb5-246">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Imagen de incorporación de windows server](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="c3bb5-248">Abra un PowerShell con privilegios elevados y ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-248">Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id="c3bb5-249">Use el identificador de área de trabajo que obtuvo y reemplace `WorkspaceID` :</span><span class="sxs-lookup"><span data-stu-id="c3bb5-249">Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a><span data-ttu-id="c3bb5-250">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c3bb5-250">Related topics</span></span>
- [<span data-ttu-id="c3bb5-251">Incorporación de dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3bb5-251">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="c3bb5-252">Incorporación de dispositivos que no son de Windows</span><span class="sxs-lookup"><span data-stu-id="c3bb5-252">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="c3bb5-253">Configuración de proxy y conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="c3bb5-253">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="c3bb5-254">Ejecutar una prueba de detección en un dispositivo Defender for Endpoint recién incorporado</span><span class="sxs-lookup"><span data-stu-id="c3bb5-254">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="c3bb5-255">Solución de problemas de incorporación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="c3bb5-255">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
