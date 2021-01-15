---
title: Configurar la conexión a Internet y el proxy del dispositivo para la DLP de punto de conexión
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo configurar la conexión a Internet y el proxy del dispositivo para la DLP de punto de conexión.
ms.openlocfilehash: 1e723adfbf16ba1180558e34b0fe4867e6337c57
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841654"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="44f28-103">Configurar la conexión a Internet y el proxy del dispositivo para la DLP de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="44f28-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="44f28-104">La DLP de punto de conexión de Microsoft usa Microsoft Windows HTTP (WinHTTP) para notificar datos y comunicarse con el servicio en la nube del punto de conexión de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44f28-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="44f28-105">La DLP de punto de conexión insertada se ejecuta en el contexto del sistema con la cuenta LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="44f28-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="44f28-106">Para las organizaciones que usan servidores proxy de reenvío como puerta de enlace a Internet, puede usar la protección de red para investigar lo que ocurre detrás de un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="44f28-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="44f28-107">Para obtener más información, vea [Investigar eventos de conexión que ocurren detrás de los servidores proxy de reenvío](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span><span class="sxs-lookup"><span data-stu-id="44f28-107">For more information, see [Investigate connection events that occur behind forward proxies](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="44f28-108">La configuración de WinHTTP es independiente de la configuración de proxy de exploración de Internet de Windows Internet (WinINet) y solo puede detectar un servidor proxy mediante los siguientes métodos de detección automática:</span><span class="sxs-lookup"><span data-stu-id="44f28-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="44f28-109">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="44f28-109">Transparent proxy</span></span>
- <span data-ttu-id="44f28-110">Protocolo de detección automática de proxy web (WPAD)</span><span class="sxs-lookup"><span data-stu-id="44f28-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="44f28-111">Si usa un proxy transparente o WPAD en la topología de red, no necesitará una configuración especial.</span><span class="sxs-lookup"><span data-stu-id="44f28-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="44f28-112">Para obtener más información sobre las exclusiones de URL de Defender para punto de conexión en el servidor proxy, vea [Habilitar el acceso a las direcciones URL del servicio en la nube de DLP para punto de conexión el servidor proxy](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="44f28-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="44f28-113">Configuración del proxy estático manual:</span><span class="sxs-lookup"><span data-stu-id="44f28-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="44f28-114">Configuración basada en el registro</span><span class="sxs-lookup"><span data-stu-id="44f28-114">Registry based configuration</span></span>
    - <span data-ttu-id="44f28-115">WinHTTP se configuró con el comando netsh (adecuado solo para dispositivos de escritorio en una topología estable, por ejemplo, un escritorio en una red corporativa detrás del mismo proxy)</span><span class="sxs-lookup"><span data-stu-id="44f28-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="44f28-116">Configurar manualmente el servidor proxy mediante un proxy estático basado en el registro</span><span class="sxs-lookup"><span data-stu-id="44f28-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="44f28-117">Para los dispositivos de punto de conexión a los que no se permite conectarse a Internet, debe configurar un proxy estático basado en el registro.</span><span class="sxs-lookup"><span data-stu-id="44f28-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="44f28-118">Debe configurar esta opción para permitir que solo DLP de punto de conexión de Microsoft notifique datos de diagnóstico y se comunique con el servicio en la nube de punto de conexión de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44f28-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="44f28-119">El proxy estático se puede configurar mediante la directiva de grupo (GP).</span><span class="sxs-lookup"><span data-stu-id="44f28-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="44f28-120">La directiva de grupo se puede encontrar aquí:</span><span class="sxs-lookup"><span data-stu-id="44f28-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="44f28-121">Abra **Plantillas administrativas > Componentes de Windows > Recopilación de datos y versiones preliminares > Configurar el uso del proxy autenticado para el servicio de Experiencia del usuario y telemetría asociadas**.</span><span class="sxs-lookup"><span data-stu-id="44f28-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="44f28-122">Establece la opción en **Habilitado** y seleccione **Deshabilitar el uso de proxy autenticado**:</span><span class="sxs-lookup"><span data-stu-id="44f28-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![Imagen de la configuración de directiva de grupo 1](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="44f28-124">Abra **Plantillas administrativas > Componentes de Windows > Recopilación de datos y versiones preliminares > Configurar Experiencia del usuario y telemetría asociadas**:</span><span class="sxs-lookup"><span data-stu-id="44f28-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="44f28-125">Configurar el servidor proxy</span><span class="sxs-lookup"><span data-stu-id="44f28-125">Configure the proxy</span></span>

![Imagen de la configuración de directiva de grupo 2](../media/atp-gpo-proxy2.png)

<span data-ttu-id="44f28-127">La directiva establece dos valores del registro `TelemetryProxyServer` como REG_SZ y `DisableEnterpriseAuthProxy` como REG_DWORD en la clave del registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="44f28-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="44f28-128">El valor del registro TelemetryProxyServer está en este formato \<server name or ip\>:\<port\>.</span><span class="sxs-lookup"><span data-stu-id="44f28-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="44f28-129">Por ejemplo, **10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="44f28-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="44f28-130">El valor del registro `DisableEnterpriseAuthProxy` debe establecerse en 1.</span><span class="sxs-lookup"><span data-stu-id="44f28-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="44f28-131">Configure el servidor proxy manualmente con el comando "netsh".</span><span class="sxs-lookup"><span data-stu-id="44f28-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="44f28-132">Use netsh para configurar un proxy estático en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="44f28-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="44f28-133">Esto afectará a todas las aplicaciones, incluidos los servicios de Windows que utilicen WinHTTP con el proxy predeterminado.</span><span class="sxs-lookup"><span data-stu-id="44f28-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="44f28-134">- Los equipos portátiles que cambien de topología (por ejemplo: entre oficina a casa) no funcionarán correctamente con netsh.</span><span class="sxs-lookup"><span data-stu-id="44f28-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="44f28-135">Use la configuración de proxy estático basada en el registro.</span><span class="sxs-lookup"><span data-stu-id="44f28-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="44f28-136">Abra un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="44f28-136">Open an elevated command-line:</span></span>
    1. <span data-ttu-id="44f28-137">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="44f28-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="44f28-138">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="44f28-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="44f28-139">Escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="44f28-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="44f28-140">Por ejemplo: **netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="44f28-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="44f28-141">Para restablecer el servidor proxy winhttp, escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="44f28-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="44f28-142">Para obtener más información, vea [Sintaxis de comando Netsh, contextos y formatos](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="44f28-142">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="44f28-143">Habilitar el acceso a las direcciones URL del servicio en la nube de DLP de punto de conexión en el servidor proxy</span><span class="sxs-lookup"><span data-stu-id="44f28-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="44f28-144">Si un servidor proxy o firewall bloquea todo el tráfico de forma predeterminada y permite únicamente el acceso a dominios específicos, agregue los dominios que aparecen en la hoja descargable a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="44f28-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="44f28-145">Esta [hoja de cálculo descargable](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/security/threat-protection/microsoft-defender-atp/downloads/mdatp-urls.xlsx) muestra los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse.</span><span class="sxs-lookup"><span data-stu-id="44f28-145">This [downloadable spreadsheet](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/security/threat-protection/microsoft-defender-atp/downloads/mdatp-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="44f28-146">Debe asegurarse de que no haya ninguna regla de filtrado de red o firewall que deniegue el acceso a estas direcciones URL o puede que necesite crear una regla de permiso específica para ellas.</span><span class="sxs-lookup"><span data-stu-id="44f28-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="44f28-147">Si un servidor proxy o firewall tiene habilitada la detección HTTPS (inspección SSL), excluya los dominios que aparecen en la tabla anterior de la detección HTTPS.</span><span class="sxs-lookup"><span data-stu-id="44f28-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="44f28-148">Si un servidor proxy o firewall bloquea el tráfico anónimo, como la DLP de punto de conexión se conecta desde el contexto del sistema, asegúrese de que se permite el tráfico anónimo en las direcciones URL indicadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="44f28-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="44f28-149">Comprobar la conectividad del cliente con las direcciones URL del servicio en la nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="44f28-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="44f28-150">Compruebe que la configuración del proxy se ha completado correctamente, que WinHTTP puede detectar y comunicarse mediante el servidor proxy en su entorno y que el servidor proxy permite el tráfico a las direcciones URL del servicio de Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="44f28-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="44f28-151">Descargue la [herramienta MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) en el equipo en el que se ejecuta la DLP de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="44f28-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="44f28-152">Extraiga el contenido de MDATPClientAnalyzer.zip en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44f28-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="44f28-153">Abra un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="44f28-153">Open an elevated command-line:</span></span>
    1. <span data-ttu-id="44f28-154">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="44f28-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="44f28-155">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="44f28-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="44f28-156">Escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="44f28-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="44f28-157">Reemplace *HardDrivePath* por la ruta de acceso en la que se descargó la herramienta MDATPClientAnalyzer, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="44f28-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="44f28-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="44f28-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="44f28-159">Extraiga el archivo **MDATPClientAnalyzerResult.zip** _ que creó la herramienta en la carpeta usada en _HardDrivePath\*.</span><span class="sxs-lookup"><span data-stu-id="44f28-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="44f28-160">Abra **MDATPClientAnalyzerResult.txt** y compruebe que ha realizado los pasos de configuración del proxy para habilitar la detección del servidor y tener acceso a las direcciones URL del servicio.</span><span class="sxs-lookup"><span data-stu-id="44f28-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="44f28-161">La herramienta comprueba la conectividad de las direcciones URL del servicio de Defender para punto de conexión con las que el cliente está configurado para interactuar.</span><span class="sxs-lookup"><span data-stu-id="44f28-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="44f28-162">Luego, imprime los resultados en el archivo **MDATPClientAnalyzerResult.txt** para cada URL que se puede usar potencialmente para comunicarse con los servicios de Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="44f28-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="44f28-163">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="44f28-163">For example:</span></span>

    <span data-ttu-id="44f28-164">**Testing URL : https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command line proxy: Doesn't exist**</span><span class="sxs-lookup"><span data-stu-id="44f28-164">**Testing URL : https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="44f28-165">Si al menos una de las opciones de conectividad devuelve un estado (200), el cliente de Defender para punto de conexión puede comunicarse con la URL probada correctamente con este método de conectividad.</span><span class="sxs-lookup"><span data-stu-id="44f28-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="44f28-166">Pero si los resultados de la comprobación de conectividad indican un error, se mostrará un error HTTP (vea los códigos de estado HTTP).</span><span class="sxs-lookup"><span data-stu-id="44f28-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="44f28-167">Luego, puede usar las direcciones URL de la tabla que se muestra en [Habilitar el acceso a las direcciones URL del servicio en la nube de DLP de punto de conexión en el servidor proxy](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="44f28-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="44f28-168">Las direcciones URL que vaya a usar dependerán de la región seleccionada durante el procedimiento de incorporación.</span><span class="sxs-lookup"><span data-stu-id="44f28-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="44f28-169"> La herramienta Analizador de conectividad no es compatible con la regla ASR [Bloquear las creaciones de procesos procedentes de comandos PSExec y WMI](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="44f28-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="44f28-170">Tendrá que deshabilitar temporalmente esta regla para ejecutar la herramienta de conectividad.</span><span class="sxs-lookup"><span data-stu-id="44f28-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="44f28-171">Cuando se establece TelemetryProxyServer, en el registro o a través de la directiva de grupo, Defender para punto de conexión se revertirá a directo si no puede obtener acceso al proxy definido.</span><span class="sxs-lookup"><span data-stu-id="44f28-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="44f28-172">Temas relacionados • Dispositivos de Windows 10 integrados • Solucionar problemas de incorporación de DLP de punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="44f28-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="44f28-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44f28-173">See also</span></span>

- [<span data-ttu-id="44f28-174">Obtenga información sobre la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="44f28-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="44f28-175">Uso de la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="44f28-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="44f28-176">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="44f28-176">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="44f28-177">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="44f28-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="44f28-178">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="44f28-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="44f28-179">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="44f28-179">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- <span data-ttu-id="44f28-180">[Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="44f28-180">[Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="44f28-181">Suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44f28-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="44f28-182">Dispositivos de Azure AD Unidos</span><span class="sxs-lookup"><span data-stu-id="44f28-182">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="44f28-183">Descargar el nuevo Microsoft Edge basado en Chromium</span><span class="sxs-lookup"><span data-stu-id="44f28-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
