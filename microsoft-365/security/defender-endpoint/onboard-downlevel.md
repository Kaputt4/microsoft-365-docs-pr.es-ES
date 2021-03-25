---
title: Incorporación de versiones anteriores de Windows en ATP de Microsoft Defender
description: Incorporación de versiones anteriores compatibles de dispositivos Windows para que puedan enviar datos de sensor al sensor atp de Microsoft Defender
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.openlocfilehash: b180e7555bb3339324d3b99956d8f8ad73dc13c3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186394"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="8fda1-104">Incorporación de versiones anteriores de Windows</span><span class="sxs-lookup"><span data-stu-id="8fda1-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8fda1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8fda1-105">**Applies to:**</span></span>
- [<span data-ttu-id="8fda1-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8fda1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8fda1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fda1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8fda1-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="8fda1-108">**Platforms**</span></span>
- <span data-ttu-id="8fda1-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8fda1-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="8fda1-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="8fda1-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="8fda1-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="8fda1-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="8fda1-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8fda1-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="8fda1-113">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8fda1-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="8fda1-114">[Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="8fda1-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="8fda1-115">Defender for Endpoint amplía la compatibilidad para incluir sistemas operativos de nivel inferior, lo que proporciona capacidades avanzadas de detección de ataques e investigación en versiones compatibles de Windows.</span><span class="sxs-lookup"><span data-stu-id="8fda1-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="8fda1-116">Para incorporar puntos de conexión de cliente de Windows de nivel inferior a Defender for Endpoint, tendrás que:</span><span class="sxs-lookup"><span data-stu-id="8fda1-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="8fda1-117">Configurar y actualizar clientes de System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="8fda1-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="8fda1-118">Instale y configure Microsoft Monitoring Agent (MMA) para informar de los datos del sensor a Defender for Endpoint como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="8fda1-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="8fda1-119">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="8fda1-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="8fda1-120">Para obtener más información, vea [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="8fda1-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="8fda1-121">Configurar y actualizar clientes de System Center Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="8fda1-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="8fda1-122">Este paso solo es necesario si su organización usa System Center Endpoint Protection (SCEP).</span><span class="sxs-lookup"><span data-stu-id="8fda1-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="8fda1-123">Defender for Endpoint se integra con System Center Endpoint Protection para proporcionar visibilidad a las detecciones de malware y detener la propagación de un ataque en la organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.</span><span class="sxs-lookup"><span data-stu-id="8fda1-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="8fda1-124">Se requieren los siguientes pasos para habilitar esta integración:</span><span class="sxs-lookup"><span data-stu-id="8fda1-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="8fda1-125">Instalar la actualización de la plataforma antimalware de enero de [2017 para clientes de Endpoint Protection](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="8fda1-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="8fda1-126">Configurar la pertenencia del servicio de protección en la nube del cliente SCEP a la **configuración** Avanzada</span><span class="sxs-lookup"><span data-stu-id="8fda1-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="8fda1-127">Configure la red para permitir conexiones a la nube de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="8fda1-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="8fda1-128">Para obtener más información, vea [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="8fda1-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="8fda1-129">Instalar y configurar Microsoft Monitoring Agent (MMA) para informar de los datos del sensor a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="8fda1-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="8fda1-130">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8fda1-130">Before you begin</span></span>
<span data-ttu-id="8fda1-131">Revise los siguientes detalles para comprobar los requisitos mínimos del sistema:</span><span class="sxs-lookup"><span data-stu-id="8fda1-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="8fda1-132">Instalar el paquete acumulativo de actualizaciones [mensuales de febrero de 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="8fda1-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="8fda1-133">Solo se aplica a Windows 7 SP1 Enterprise y Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="8fda1-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="8fda1-134">Instalar la actualización [para la experiencia del cliente y telemetría de diagnóstico](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="8fda1-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="8fda1-135">Instalar [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="8fda1-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="8fda1-136">Solo se aplica a Windows 7 SP1 Enterprise y Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="8fda1-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="8fda1-137">No instales .NET Framework 4.0.x, ya que anulará la instalación anterior.</span><span class="sxs-lookup"><span data-stu-id="8fda1-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="8fda1-138">Cumpla los requisitos mínimos del sistema del agente de Azure Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="8fda1-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="8fda1-139">Para obtener más información, vea [Recopilar datos de equipos en su entorno con Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="8fda1-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="8fda1-140">Descargue el archivo de instalación del agente: agente de [Windows 64 bits](https://go.microsoft.com/fwlink/?LinkId=828603) o agente de [Windows 32 bits](https://go.microsoft.com/fwlink/?LinkId=828604).</span><span class="sxs-lookup"><span data-stu-id="8fda1-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="8fda1-141">Obtenga el identificador del área de trabajo:</span><span class="sxs-lookup"><span data-stu-id="8fda1-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="8fda1-142">En el panel de navegación Defender para endpoint, seleccione **Configuración > Administración de dispositivos > incorporación**</span><span class="sxs-lookup"><span data-stu-id="8fda1-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="8fda1-143">Seleccionar **Windows 7 SP1 y 8.1** como sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8fda1-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="8fda1-144">Copiar el identificador del área de trabajo y la clave del área de trabajo</span><span class="sxs-lookup"><span data-stu-id="8fda1-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="8fda1-145">Con el identificador de área de trabajo y la clave Área de trabajo, elija cualquiera de los siguientes métodos de instalación para instalar el agente:</span><span class="sxs-lookup"><span data-stu-id="8fda1-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="8fda1-146">[Instale manualmente el agente mediante el programa de instalación](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="8fda1-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="8fda1-147">En la **página Opciones de configuración del agente,** seleccione Conectar el agente a Azure Log Analytics **(OMS)**</span><span class="sxs-lookup"><span data-stu-id="8fda1-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="8fda1-148">[Instale el agente mediante la línea de comandos](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="8fda1-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="8fda1-149">[Configure el agente mediante un script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="8fda1-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="8fda1-150">Si es cliente de [Us Government](gov.md), en "Azure Cloud" tendrá que elegir "Azure US Government" si usa el asistente para la instalación, o si usa una línea de comandos o un script: establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.</span><span class="sxs-lookup"><span data-stu-id="8fda1-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="8fda1-151">Si usa un proxy para conectarse a Internet, consulte la sección Configurar opciones de proxy.</span><span class="sxs-lookup"><span data-stu-id="8fda1-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="8fda1-152">Una vez completado, debería ver puntos de conexión incorporados en el portal en una hora.</span><span class="sxs-lookup"><span data-stu-id="8fda1-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="8fda1-153">Configuración de proxy y conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="8fda1-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="8fda1-154">Cada extremo de Windows debe poder conectarse a Internet mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8fda1-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="8fda1-155">Esta conexión puede ser directa, mediante un proxy o a través de la puerta [de enlace OMS](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span><span class="sxs-lookup"><span data-stu-id="8fda1-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="8fda1-156">Si un proxy o firewall bloquea todo el tráfico de forma predeterminada y permite solo dominios específicos a través o el examen HTTPS (inspección SSL) está habilitado, asegúrese de habilitar el acceso a las direcciones URL del servicio [defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)para puntos de conexión .</span><span class="sxs-lookup"><span data-stu-id="8fda1-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="8fda1-157">Extremos de cliente offboard</span><span class="sxs-lookup"><span data-stu-id="8fda1-157">Offboard client endpoints</span></span>
<span data-ttu-id="8fda1-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span><span class="sxs-lookup"><span data-stu-id="8fda1-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="8fda1-159">Después de salir del agente, el punto de conexión ya no enviará datos del sensor a Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8fda1-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="8fda1-160">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8fda1-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="8fda1-161">[Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span><span class="sxs-lookup"><span data-stu-id="8fda1-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

