---
title: Incorporación Windows servidores al servicio de Microsoft Defender para puntos de conexión
description: Incorpore Windows para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint.
keywords: servidor incorporado, servidor, 2012r2, 2016, 2019, incorporación de servidores, administración de dispositivos, configuración de Microsoft Defender para servidores de extremo, incorporación de Servidores de Microsoft Defender para puntos de conexión, incorporación de Microsoft Defender para servidores de extremo
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
ms.openlocfilehash: 47d57e51eca4950f7a8f4284fbc916e9d030b2c7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844339"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="ee7d8-104">Incorporación Windows servidores al servicio de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="ee7d8-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ee7d8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ee7d8-105">**Applies to:**</span></span>

- <span data-ttu-id="ee7d8-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="ee7d8-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="ee7d8-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ee7d8-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="ee7d8-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ee7d8-108">Windows Server 2016</span></span>
- <span data-ttu-id="ee7d8-109">Windows Server (SAC) version 1803 and later</span><span class="sxs-lookup"><span data-stu-id="ee7d8-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="ee7d8-110">Windows Server 2019 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="ee7d8-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="ee7d8-111">Windows Edición principal de Server 2019</span><span class="sxs-lookup"><span data-stu-id="ee7d8-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="ee7d8-112">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ee7d8-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ee7d8-113">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="ee7d8-114">Defender for Endpoint amplía la compatibilidad para incluir también el sistema operativo Windows server.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="ee7d8-115">Esta compatibilidad proporciona capacidades avanzadas de detección de ataques e investigación sin problemas a través de Centro de seguridad de Microsoft Defender consola.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="ee7d8-116">Para obtener instrucciones prácticas sobre lo que debe haber para las licencias y la infraestructura, vea [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="ee7d8-117">Para obtener instrucciones sobre cómo descargar y usar Seguridad de Windows base de datos para Windows servidores, vea [Seguridad de Windows Baselines](/windows/device-security/windows-security-baselines).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="ee7d8-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 y Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ee7d8-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="ee7d8-119">Puede incorporar Windows Server 2008 R2 SP1, Windows Server 2012 R2 y Windows Server 2016 a Defender for Endpoint mediante cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="ee7d8-120">**Opción 1:** Incorporación mediante la instalación y configuración de [Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="ee7d8-121">**Opción 2:** [Incorporación a través del Centro de seguridad de Azure](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="ee7d8-122">**Opción 3:** [Incorporación Microsoft Endpoint Manager versión 2002 y posteriores](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="ee7d8-123">Después de completar los pasos de incorporación con cualquiera de las opciones proporcionadas, deberá configurar y actualizar los [System Center Endpoint Protection cliente.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="ee7d8-124">La licencia de servidor independiente de Defender for Endpoint es necesaria, por nodo, para incorporar un servidor de Windows a través de Microsoft Monitoring Agent (opción 1) o a través de Microsoft Endpoint Manager (opción 3).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="ee7d8-125">Como alternativa, se requiere una licencia de Azure Defender para servidores, por nodo, para incorporar un servidor de Windows a través del Centro de seguridad de Azure (opción 2), consulte Características admitidas disponibles en [Azure Defender](/azure/security-center/security-center-services).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="ee7d8-126">Opción 1: Incorporación mediante la instalación y configuración de Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="ee7d8-127">Deberá instalar y configurar MMA para que los servidores Windows informen los datos del sensor a Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="ee7d8-128">Para obtener más información, vea [Recopilar datos de registro con el agente de Azure Log Analytics](/azure/azure-monitor/platform/log-analytics-agent).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-128">For more information, see [Collect log data with Azure Log Analytics agent](/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="ee7d8-129">Si ya usa System Center Operations Manager (SCOM) o Azure Monitor (anteriormente conocido como Operations Management Suite (OMS)), adjunte el Microsoft Monitoring Agent (MMA) para informar al área de trabajo de Defender para endpoint mediante la compatibilidad con multiconsulta.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="ee7d8-130">En general, deberá seguir los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="ee7d8-131">Cumpla los requisitos de incorporación descritos en **la sección Antes de comenzar.**</span><span class="sxs-lookup"><span data-stu-id="ee7d8-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="ee7d8-132">Active la supervisión del servidor desde el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="ee7d8-133">Instale y configure MMA para que el servidor informe los datos del sensor a Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="ee7d8-134">Configure y actualice System Center Endpoint Protection clientes.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="ee7d8-135">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="ee7d8-136">Para obtener más información, vea [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="ee7d8-137">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ee7d8-137">Before you begin</span></span>

<span data-ttu-id="ee7d8-138">Realice los siguientes pasos para cumplir los requisitos de incorporación:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="ee7d8-139">Para Windows Server 2008 R2 SP1 o Windows Server 2012 R2, asegúrese de instalar la siguiente revisión:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="ee7d8-140">Actualización de la experiencia del cliente y telemetría de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ee7d8-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="ee7d8-141">Para Windows Server 2008 R2 SP1, asegúrese de cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="ee7d8-142">Instalar el paquete [acumulativo de actualizaciones mensuales de febrero](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="ee7d8-143">Instalar [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee7d8-144">Si administra su Windows Server 2008 R2 SP1 con SCCM, el agente cliente de SCCM instala .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="ee7d8-145">Por lo tanto, no es necesario instalar .NET Framework 4.5 (o posterior).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="ee7d8-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="ee7d8-147">Este paso solo es necesario si su organización usa System Center Endpoint Protection (SCEP) y está incorporando Windows Server 2008 R2 SP1 y Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="ee7d8-148">Instalar y configurar Microsoft Monitoring Agent (MMA) para informar de los datos del sensor a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="ee7d8-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="ee7d8-149">Descargue el archivo de instalación del [agente: Windows agente de 64 bits](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="ee7d8-150">Mediante el identificador de área de trabajo y la clave de área de trabajo obtenidas en el procedimiento anterior, elija cualquiera de los siguientes métodos de instalación para instalar el agente en el Windows servidor:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="ee7d8-151">[Instale manualmente el agente mediante el programa de instalación](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-151">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="ee7d8-152">En la **página Opciones de configuración del** agente, elija Conectar el agente a Azure Log Analytics **(OMS).**</span><span class="sxs-lookup"><span data-stu-id="ee7d8-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="ee7d8-153">[Instale el agente mediante la línea de comandos](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-153">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="ee7d8-154">[Configure el agente mediante un script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-154">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="ee7d8-155">Si es cliente de [Us Government](gov.md), en "Azure Cloud" tendrá que elegir "Azure US Government" si usa el asistente para la instalación, o si usa una línea de comandos o un script: establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="ee7d8-156">Configurar Windows proxy de servidor y conectividad a Internet si es necesario</span><span class="sxs-lookup"><span data-stu-id="ee7d8-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="ee7d8-157">Si los servidores necesitan usar un proxy para comunicarse con Defender for Endpoint, use uno de los métodos siguientes para configurar la MMA para usar el servidor proxy:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="ee7d8-158">Configurar la MMA para usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="ee7d8-158">Configure the MMA to use a proxy server</span></span>](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="ee7d8-159">Configurar Windows usar un servidor proxy para todas las conexiones</span><span class="sxs-lookup"><span data-stu-id="ee7d8-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="ee7d8-160">Si hay un proxy o firewall en uso, asegúrese de que los servidores puedan tener acceso a todas las direcciones URL del servicio de Microsoft Defender para endpoints directamente y sin interceptación SSL.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="ee7d8-161">Para obtener más información, vea [habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="ee7d8-162">El uso de la interceptación SSL impedirá que el sistema se comunique con el servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="ee7d8-163">Una vez completado, debería ver los servidores Windows incorporados en el portal en una hora.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="ee7d8-164">Opción 2: Incorporar servidores Windows a través del Centro de seguridad de Azure</span><span class="sxs-lookup"><span data-stu-id="ee7d8-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="ee7d8-165">En el panel Centro de seguridad de Microsoft Defender navegación, **seleccione Configuración** Incorporación de administración  >  **de**  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="ee7d8-166">Seleccione **Windows Server 2008 R2 SP1, 2012 R2 y 2016** como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="ee7d8-167">Haga **clic en Servidores integrados en El Centro de seguridad de Azure**.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="ee7d8-168">Siga las instrucciones de incorporación en [Microsoft Defender para](/azure/security-center/security-center-wdatp) endpoint con Azure Defender y si usa Azure ARC, siga las instrucciones de incorporación en Habilitar la integración de Microsoft Defender para [endpoints](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="ee7d8-169">Después de completar los pasos de incorporación, deberá configurar y actualizar los [System Center Endpoint Protection cliente.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ee7d8-170">Para que la incorporación a través de Azure Defender para servidores funcione según lo esperado, el servidor debe tener una clave y un área de trabajo adecuadas configuradas dentro de la configuración de Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="ee7d8-171">Una vez configurado, el módulo de administración de nube adecuado se implementa en el equipo y el proceso de sensor (MsSenseS.exe) se implementará e iniciará.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="ee7d8-172">Esto también es necesario si el servidor está configurado para usar un servidor de puerta de enlace OMS como proxy.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="ee7d8-173">Opción 3: Incorporar servidores Windows a través Microsoft Endpoint Manager versión 2002 y posteriores</span><span class="sxs-lookup"><span data-stu-id="ee7d8-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="ee7d8-174">Puede incorporar Windows Server 2012 R2 y Windows Server 2016 mediante Microsoft Endpoint Manager versión 2002 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="ee7d8-175">Para obtener más información, vea [Microsoft Defender for Endpoint en Microsoft Endpoint Manager rama actual](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="ee7d8-176">Después de completar los pasos de incorporación, deberá configurar y actualizar los [System Center Endpoint Protection cliente.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="ee7d8-177">Windows Server (SAC) versión 1803, Windows Server 2019 y Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="ee7d8-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="ee7d8-178">Puede incorporar Windows Server (SAC) versión 1803, Windows Server 2019 o Windows Server 2019 Core edition mediante los siguientes métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="ee7d8-179">Script local</span><span class="sxs-lookup"><span data-stu-id="ee7d8-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="ee7d8-180">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="ee7d8-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="ee7d8-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ee7d8-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="ee7d8-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="ee7d8-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="ee7d8-183">Scripts de incorporación de VDI para dispositivos no persistentes</span><span class="sxs-lookup"><span data-stu-id="ee7d8-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="ee7d8-184">El paquete de incorporación para Windows Server 2019 a Microsoft Endpoint Manager envía actualmente un script.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="ee7d8-185">Para obtener más información sobre cómo implementar scripts en Configuration Manager, vea [Paquetes y programas en Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="ee7d8-186">Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="ee7d8-187">Para una implementación de producción, se recomienda usar la directiva de grupo o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="ee7d8-188">La compatibilidad con Windows Server proporciona información más detallada sobre las actividades del servidor, la cobertura para la detección de ataques de kernel y memoria y habilita acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="ee7d8-189">Configure defender para la incorporación de puntos de conexión en el servidor Windows con las mismas herramientas y métodos para Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="ee7d8-190">Para obtener más información, vea [Onboard Windows 10 devices](configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="ee7d8-191">Si estás ejecutando una solución antimalware de terceros, tendrás que aplicar la siguiente configuración del modo pasivo antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="ee7d8-192">Compruebe que se configuró correctamente:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="ee7d8-193">Establezca la siguiente entrada del Registro:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="ee7d8-194">Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="ee7d8-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="ee7d8-195">Nombre: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="ee7d8-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="ee7d8-196">Tipo: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ee7d8-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="ee7d8-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="ee7d8-197">Value: 1</span></span>

    1. <span data-ttu-id="ee7d8-198">Ejecute el siguiente comando de PowerShell para comprobar que se configuró el modo pasivo:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="ee7d8-199">Confirme que se encuentra un evento reciente que contiene el evento de modo pasivo:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Imagen del resultado de comprobación del modo pasivo](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="ee7d8-201">Ejecute el siguiente comando para comprobar si Microsoft Defender AV está instalado:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="ee7d8-202">Si el resultado es "El servicio especificado no existe como servicio instalado", tendrá que instalar Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="ee7d8-203">Para obtener más información, [vea Antivirus de Microsoft Defender en Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-203">For more information, see [Microsoft Defender Antivirus in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="ee7d8-204">Para obtener información sobre cómo usar la directiva de grupo para configurar y administrar Antivirus de Microsoft Defender en los servidores de Windows, vea [Use Group Policy settings to configure and manage Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="ee7d8-205">Integración con Azure Defender</span><span class="sxs-lookup"><span data-stu-id="ee7d8-205">Integration with Azure Defender</span></span>

<span data-ttu-id="ee7d8-206">Defender for Endpoint se puede integrar con Azure Defender para proporcionar una solución completa Windows protección de servidores.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="ee7d8-207">Con esta integración, Azure Defender puede usar la potencia de Defender para endpoint para proporcionar una mejor detección de amenazas para Windows servidores.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="ee7d8-208">En esta integración se incluyen las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="ee7d8-209">Incorporación automatizada: el sensor Defender for Endpoint se habilita automáticamente en los servidores Windows que están incorporados a Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="ee7d8-210">Para obtener más información sobre la incorporación de Azure Defender, consulte [Use the integrated Microsoft Defender for Endpoint license](/azure/security-center/security-center-wdatp).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee7d8-211">La integración entre Azure Defender para servidores y Microsoft Defender para endpoint se ha expandido para admitir [Windows Server 2019 y Windows Virtual Desktop (WVD).](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="ee7d8-212">Windows servidores supervisados por Azure Defender también estarán disponibles en Defender para endpoint: Azure Defender se conecta perfectamente al inquilino de Defender para endpoint, lo que proporciona una vista única entre clientes y servidores.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="ee7d8-213">Además, las alertas de Defender para extremo estarán disponibles en la consola de Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="ee7d8-214">Investigación del servidor: los clientes de Azure Defender pueden acceder a Centro de seguridad de Microsoft Defender realizar una investigación detallada para descubrir el ámbito de una posible infracción.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-214">Server investigation -  Azure Defender customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="ee7d8-215">Cuando usa Azure Defender para supervisar los servidores, se crea automáticamente un inquilino de Defender for Endpoint (en Estados Unidos para usuarios estadounidenses, en la UE para usuarios europeos y británicos).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="ee7d8-216">Los datos recopilados por Defender para endpoint se almacenan en la ubicación geográfica del inquilino tal como se identifica durante el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="ee7d8-217">Si usa Defender para endpoint antes de usar Azure Defender, los datos se almacenarán en la ubicación que especificó al crear el inquilino, incluso si se integra con Azure Defender más adelante.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="ee7d8-218">Una vez configurado, no se puede cambiar la ubicación donde se almacenan los datos.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="ee7d8-219">Si necesita mover los datos a otra ubicación, póngase en contacto con el soporte técnico de Microsoft para restablecer el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="ee7d8-220">La supervisión de extremos de servidor que utiliza esta integración se ha deshabilitado para Office 365 GCC clientes.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="ee7d8-221">Configurar y actualizar System Center Endpoint Protection clientes</span><span class="sxs-lookup"><span data-stu-id="ee7d8-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="ee7d8-222">Defender for Endpoint se integra con System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="ee7d8-223">La integración proporciona visibilidad a las detecciones de malware y para detener la propagación de un ataque en la organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="ee7d8-224">Se requieren los siguientes pasos para habilitar esta integración:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="ee7d8-225">Instale la actualización de la plataforma antimalware de enero de [2017 para Endpoint Protection cliente.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="ee7d8-226">[Configure la pertenencia al servicio de protección](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) en la nube del cliente SCEP a la **configuración** Avanzada.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-226">[Configure the SCEP client Cloud Protection Service membership](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="ee7d8-227">Servidores de Windows offboard</span><span class="sxs-lookup"><span data-stu-id="ee7d8-227">Offboard Windows servers</span></span>

<span data-ttu-id="ee7d8-228">Puede salir de Windows Server (SAC), Windows Server 2019 y Windows Server 2019 Core edition en el mismo método disponible para dispositivos cliente Windows 10 cliente.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="ee7d8-229">Para otras Windows de servidor, tiene dos opciones para salir Windows servidores del servicio:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="ee7d8-230">Desinstalar el agente mma</span><span class="sxs-lookup"><span data-stu-id="ee7d8-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="ee7d8-231">Quitar la configuración del área de trabajo de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee7d8-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="ee7d8-232">La offboarding hace que el servidor Windows deje de enviar datos del sensor al portal, pero los datos del servidor de Windows, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="ee7d8-233">Desinstalar Windows servidores mediante la desinstalación del agente mma</span><span class="sxs-lookup"><span data-stu-id="ee7d8-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="ee7d8-234">Para salir del servidor Windows, puede desinstalar el agente mma del servidor de Windows o desasoyérselo del informe al área de trabajo de Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="ee7d8-235">Después de desactivar el agente, el servidor Windows ya no enviará datos del sensor a Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="ee7d8-236">Para obtener más información, vea [Para deshabilitar un agente](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-236">For more information, see [To disable an agent](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="ee7d8-237">Quitar la configuración del área de trabajo de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee7d8-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="ee7d8-238">Para salir del servidor Windows, puede usar cualquiera de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="ee7d8-239">Quitar la configuración del área de trabajo de Defender for Endpoint del agente mma</span><span class="sxs-lookup"><span data-stu-id="ee7d8-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="ee7d8-240">Ejecutar un comando de PowerShell para quitar la configuración</span><span class="sxs-lookup"><span data-stu-id="ee7d8-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="ee7d8-241">Quitar la configuración del área de trabajo de Defender for Endpoint del agente mma</span><span class="sxs-lookup"><span data-stu-id="ee7d8-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="ee7d8-242">En el **Microsoft Monitoring Agent ,** seleccione la pestaña Azure Log **Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="ee7d8-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="ee7d8-243">Seleccione el área de trabajo Defender para extremo y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Imagen de Microsoft Monitoring Agent propiedades](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="ee7d8-245">Ejecutar un comando de PowerShell para quitar la configuración</span><span class="sxs-lookup"><span data-stu-id="ee7d8-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="ee7d8-246">Obtener el id. de área de trabajo:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="ee7d8-247">En el panel de navegación, **seleccione Configuración**  >  **Incorporación**.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="ee7d8-248">Seleccione **Windows Server 2008 R2 SP1, 2012 R2 y 2016** como sistema operativo y obtenga el identificador de área de trabajo:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Imagen de Windows de servidor](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="ee7d8-250&quot;>Abra un PowerShell con privilegios elevados y ejecute el siguiente comando.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee7d8-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;ee7d8-251&quot;>Use el identificador de área de trabajo que obtuvo y reemplace `WorkspaceID` :</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ee7d8-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="ee7d8-252">Servidores de incorporación sin solución de administración</span><span class="sxs-lookup"><span data-stu-id="ee7d8-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="ee7d8-253">Uso de la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="ee7d8-253">Using Group Policy</span></span>

<span data-ttu-id="ee7d8-254">**Paso 1: Crear los archivos necesarios para copiar en los servidores.**</span><span class="sxs-lookup"><span data-stu-id="ee7d8-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="ee7d8-255">Vaya a c:\windows\sysvol\domain\scripts (podría ser necesario el control de cambio en uno de los controladores de dominio).</span><span class="sxs-lookup"><span data-stu-id="ee7d8-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="ee7d8-256">Cree una carpeta denominada MMA.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="ee7d8-257">Descargue lo siguiente y colócalo en la carpeta MMA:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="ee7d8-258">**Actualización de la telemetría de diagnóstico y experiencia del cliente (Windows Server 2008 R2 y Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="ee7d8-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="ee7d8-259">Para Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="ee7d8-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="ee7d8-260">Para Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="ee7d8-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="ee7d8-261">En este artículo se supone que usa servidores basados en x64 (agente mma .exe x64 nueva versión compatible con [SHA-2](https://go.microsoft.com/fwlink/?LinkId=828603))</span><span class="sxs-lookup"><span data-stu-id="ee7d8-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="ee7d8-262">**Paso 2: Crear un nombre de archivo DeployMMA.cmd (con bloc de notas)** Agregue las siguientes líneas al archivo cmd.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="ee7d8-263">Ten en cuenta que necesitarás el identificador de área de trabajo y la clave.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-263">Note that you'll need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="ee7d8-264">Configuración de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="ee7d8-264">Group Policy Configuration</span></span>

<span data-ttu-id="ee7d8-265">Crea una nueva directiva de grupo específicamente para los dispositivos de incorporación, como "Microsoft Defender para la incorporación de puntos de conexión".</span><span class="sxs-lookup"><span data-stu-id="ee7d8-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="ee7d8-266">Crear una carpeta de directiva de grupo denominada "c:\windows\MMA"</span><span class="sxs-lookup"><span data-stu-id="ee7d8-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="carpetas":::

    <span data-ttu-id="ee7d8-268">**Esto agregará una nueva carpeta en cada servidor que obtiene el GPO aplicado, denominado MMA, y se almacenará en c:\windows. Esto contendrá los archivos de instalación del MMA, los requisitos previos y el script de instalación.**</span><span class="sxs-lookup"><span data-stu-id="ee7d8-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="ee7d8-269">Cree una preferencia de archivos de directiva de grupo para cada uno de los archivos almacenados en el inicio de sesión de red.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="imagen de directiva de grupo1":::

<span data-ttu-id="ee7d8-271">Copia los archivos de DOMAIN\NETLOGON\MMA\filename a C:\windows\MMA\filename, por lo que los archivos de instalación son **locales en el servidor:**</span><span class="sxs-lookup"><span data-stu-id="ee7d8-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="implementar mma cmd":::

<span data-ttu-id="ee7d8-273">Para los dos KB (uno para Windows Server 2008R2/Windows 7 y el otro para Windows Server 2012 R2) repita el proceso pero cree la segmentación de nivel de elemento en la pestaña COMMON, por lo que el archivo solo se copia en la versión de plataforma o sistema operativo correspondiente en el ámbito:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="editor de destino":::

- <span data-ttu-id="ee7d8-275">Para Windows Server 2008 R2 necesita (y solo copiará hacia abajo) Windows6.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="ee7d8-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="ee7d8-276">Para Windows Server 2012 R2 que necesitas (y solo se copiará hacia abajo) Windows8.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="ee7d8-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="ee7d8-277">Una vez hecho esto, deberá crear una directiva de script de inicio:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="propiedades de inicio":::

<span data-ttu-id="ee7d8-279">El nombre del archivo que se va a ejecutar aquí es c:\windows\MMA\DeployMMA.cmd.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="ee7d8-280">Una vez reiniciado el servidor como parte del proceso de inicio, se instalará la actualización de la experiencia del cliente y la telemetría de diagnóstico KB y, a continuación, se instalará el agente mma, mientras se establece el identificador de área de trabajo y la clave, y se incorporará el servidor.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-280">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="ee7d8-281">También puede usar una **tarea inmediata para** ejecutar deployMMA.cmd si no desea reiniciar todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-281">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="ee7d8-282">Esto se podría hacer en dos fases.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-282">This could be done in two phases.</span></span> <span data-ttu-id="ee7d8-283">En primer **lugar,** cree los archivos y la carpeta en GPO: dé tiempo al sistema para asegurarse de que se ha aplicado el GPO y de que todos los servidores tienen los archivos de instalación.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-283">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="ee7d8-284">A continuación, agregue la tarea inmediata.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-284">Then, add the immediate task.</span></span> <span data-ttu-id="ee7d8-285">Esto logrará el mismo resultado sin necesidad de reiniciar.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-285">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="ee7d8-286">Dado que el script tiene un método exit y no se vuelve a ejecutar si está instalado el MMA, también puede usar una tarea programada diariamente para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-286">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="ee7d8-287">De forma similar a una directiva de cumplimiento de Configuration Manager, se comprobará diariamente para asegurarse de que la MMA está presente.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-287">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="tarea de programación":::

:::image type="content" source="images/newtaskprops.png" alt-text="nuevas propiedades de tarea":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="implementar aplicaciones de descarga de mma":::

:::image type="content" source="images/tasksch.png" alt-text="programador de tareas":::

<span data-ttu-id="ee7d8-292">Como se mencionó en la documentación de incorporación de Server específicamente en torno a Server 2008 R2, vea a continuación:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-292">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="ee7d8-293">Para Windows Server 2008 R2 PS1, asegúrese de cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="ee7d8-293">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="ee7d8-294">Instalar el paquete acumulativo de actualizaciones [mensuales de febrero de 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-294">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="ee7d8-295">Instalar [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="ee7d8-295">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="ee7d8-296">Compruebe que los KB están presentes antes de incorporar Windows Server 2008 R2 Este proceso le permite incorporar todos los servidores si no tiene configuration manager managing Servers.</span><span class="sxs-lookup"><span data-stu-id="ee7d8-296">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee7d8-297">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ee7d8-297">Related topics</span></span>

- [<span data-ttu-id="ee7d8-298">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="ee7d8-298">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="ee7d8-299">Incorporar dispositivos que no tienen Windows</span><span class="sxs-lookup"><span data-stu-id="ee7d8-299">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="ee7d8-300">Configurar las opciones del proxy y de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="ee7d8-300">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="ee7d8-301">Ejecutar una prueba de detección en un dispositivo Defender for Endpoint recién incorporado</span><span class="sxs-lookup"><span data-stu-id="ee7d8-301">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="ee7d8-302">Solución de problemas de incorporación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="ee7d8-302">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
