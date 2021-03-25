---
title: Configurar el proxy de dispositivo y la configuración de conexión a Internet
description: Configure el proxy de ATP de Microsoft Defender y la configuración de Internet para habilitar la comunicación con el servicio en la nube.
keywords: configuración, proxy, Internet, conectividad a Internet, configuración, configuración de proxy, netsh, winhttp, servidor proxy
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ce8599556b1d0c8efbd020d525b30ed2cedaa9cb
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165470"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="2ac10-104">Configurar el proxy de dispositivo y la configuración de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="2ac10-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ac10-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2ac10-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ac10-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2ac10-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ac10-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ac10-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2ac10-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2ac10-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2ac10-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2ac10-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="2ac10-110">El sensor Defender for Endpoint requiere Microsoft Windows HTTP (WinHTTP) para informar de los datos del sensor y comunicarse con el servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2ac10-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="2ac10-111">El sensor de Defender for Endpoint incrustado se ejecuta en el contexto del sistema mediante la cuenta LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="2ac10-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="2ac10-112">El sensor usa Servicios HTTP de Microsoft Windows (WinHTTP) para habilitar la comunicación con el servicio en la nube defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="2ac10-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="2ac10-113">Para las organizaciones que usan servidores proxy de reenvío como puerta de enlace a Internet, puede usar la protección de red para investigar lo que ocurre detrás de un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="2ac10-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="2ac10-114">Para obtener más información, vea [Investigar eventos de conexión que ocurren detrás de los servidores proxy de reenvío](investigate-behind-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="2ac10-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="2ac10-115">La configuración de WinHTTP es independiente de la configuración de proxy de exploración de Internet de Windows Internet (WinINet) y solo puede detectar un servidor proxy mediante los siguientes métodos de detección:</span><span class="sxs-lookup"><span data-stu-id="2ac10-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="2ac10-116">Métodos de detección automática:</span><span class="sxs-lookup"><span data-stu-id="2ac10-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="2ac10-117">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="2ac10-117">Transparent proxy</span></span>
  - <span data-ttu-id="2ac10-118">Protocolo de detección automática de proxy web (WPAD)</span><span class="sxs-lookup"><span data-stu-id="2ac10-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="2ac10-119">Si usas proxy transparente o WPAD en la topología de red, no necesitas opciones de configuración especiales.</span><span class="sxs-lookup"><span data-stu-id="2ac10-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="2ac10-120">Para obtener más información sobre las exclusiones de url de extremo de Defender en el proxy, vea Habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión [en el servidor proxy.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="2ac10-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="2ac10-121">Configuración del proxy estático manual:</span><span class="sxs-lookup"><span data-stu-id="2ac10-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="2ac10-122">Configuración basada en el registro</span><span class="sxs-lookup"><span data-stu-id="2ac10-122">Registry based configuration</span></span>
  - <span data-ttu-id="2ac10-123">WinHTTP se configuró con el comando netsh (adecuado solo para dispositivos de escritorio en una topología estable, por ejemplo, un escritorio en una red corporativa detrás del mismo proxy)</span><span class="sxs-lookup"><span data-stu-id="2ac10-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="2ac10-124">Configurar manualmente el servidor proxy mediante un proxy estático basado en el registro</span><span class="sxs-lookup"><span data-stu-id="2ac10-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="2ac10-125">Configure un proxy estático basado en el Registro para permitir que solo el sensor Defender for Endpoint informe de datos de diagnóstico y se comunique con Defender for Endpoint services si un equipo no tiene permiso para conectarse a Internet.</span><span class="sxs-lookup"><span data-stu-id="2ac10-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

<span data-ttu-id="2ac10-126">El proxy estático se puede configurar mediante la directiva de grupo (GP).</span><span class="sxs-lookup"><span data-stu-id="2ac10-126">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="2ac10-127">La directiva de grupo se puede encontrar aquí:</span><span class="sxs-lookup"><span data-stu-id="2ac10-127">The group policy can be found under:</span></span>

- <span data-ttu-id="2ac10-128">Plantillas administrativas > componentes de Windows > recopilación de datos y versiones preliminares > Configurar el uso de proxy autenticado para el servicio de telemetría y experiencia del usuario conectado</span><span class="sxs-lookup"><span data-stu-id="2ac10-128">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="2ac10-129">Estadíla en **Habilitado** y seleccione **Deshabilitar uso de proxy autenticado:** Imagen de configuración de directiva de ![ grupo1](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="2ac10-129">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="2ac10-130">**Plantillas administrativas > componentes de Windows > recopilación** de datos y versiones preliminares > Configurar la telemetría y las experiencias de usuario conectados:</span><span class="sxs-lookup"><span data-stu-id="2ac10-130">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="2ac10-131">Configurar el proxy:</span><span class="sxs-lookup"><span data-stu-id="2ac10-131">Configure the proxy:</span></span><br>
    <span data-ttu-id="2ac10-132">![Imagen de configuración de directiva de grupo2](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="2ac10-132">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="2ac10-133">La directiva establece dos valores del registro `TelemetryProxyServer` como REG_SZ y `DisableEnterpriseAuthProxy` como REG_DWORD en la clave del registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="2ac10-133">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="2ac10-134">El valor del `TelemetryProxyServer` Registro tiene el siguiente formato de cadena:</span><span class="sxs-lookup"><span data-stu-id="2ac10-134">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="2ac10-135">Por ejemplo, 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="2ac10-135">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="2ac10-136">El valor del registro `DisableEnterpriseAuthProxy` debe establecerse en 1.</span><span class="sxs-lookup"><span data-stu-id="2ac10-136">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="2ac10-137">Configurar el servidor proxy manualmente mediante el comando netsh</span><span class="sxs-lookup"><span data-stu-id="2ac10-137">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="2ac10-138">Use netsh para configurar un proxy estático en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="2ac10-138">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="2ac10-139">Esto afectará a todas las aplicaciones, incluidos los servicios de Windows que utilicen WinHTTP con el proxy predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2ac10-139">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="2ac10-140">Los portátiles que cambian la topología (por ejemplo: de la oficina a la casa) no funcionan correctamente con netsh.</span><span class="sxs-lookup"><span data-stu-id="2ac10-140">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="2ac10-141">Use la configuración de proxy estático basada en el registro.</span><span class="sxs-lookup"><span data-stu-id="2ac10-141">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="2ac10-142">Abra un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="2ac10-142">Open an elevated command-line:</span></span>

    <span data-ttu-id="2ac10-143">a.</span><span class="sxs-lookup"><span data-stu-id="2ac10-143">a.</span></span> <span data-ttu-id="2ac10-144">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="2ac10-144">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="2ac10-145">b.</span><span class="sxs-lookup"><span data-stu-id="2ac10-145">b.</span></span> <span data-ttu-id="2ac10-146">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2ac10-146">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2ac10-147">Escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="2ac10-147">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="2ac10-148">Por ejemplo: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="2ac10-148">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="2ac10-149">Para restablecer el proxy winhttp, escriba el siguiente comando y presione **ENTRAR**</span><span class="sxs-lookup"><span data-stu-id="2ac10-149">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="2ac10-150">Para obtener más información, vea [Sintaxis de comando Netsh, contextos y formatos](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="2ac10-150">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="2ac10-151">Habilitar el acceso a las direcciones URL del servicio de punto de conexión de Microsoft Defender en el servidor proxy</span><span class="sxs-lookup"><span data-stu-id="2ac10-151">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="2ac10-152">Si un servidor proxy o firewall bloquea todo el tráfico de forma predeterminada y permite únicamente el acceso a dominios específicos, agregue los dominios que aparecen en la hoja descargable a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="2ac10-152">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="2ac10-153">En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse.</span><span class="sxs-lookup"><span data-stu-id="2ac10-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="2ac10-154">Debe asegurarse de que no hay reglas de filtrado de red o firewall que denieguen el acceso *a* estas direcciones URL, o puede que necesite crear una regla de permitir específicamente para ellas.</span><span class="sxs-lookup"><span data-stu-id="2ac10-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="2ac10-155">**Hoja de cálculo de la lista de dominios**</span><span class="sxs-lookup"><span data-stu-id="2ac10-155">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="2ac10-156">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2ac10-156">**Description**</span></span>|
|:-----|:-----|
|![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión](images/mdatp-urls.png)<br/>  | <span data-ttu-id="2ac10-158">Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2ac10-158">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="2ac10-159">Descargue la hoja de cálculo aquí.</span><span class="sxs-lookup"><span data-stu-id="2ac10-159">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="2ac10-160">Si un servidor proxy o firewall tiene habilitada la detección HTTPS (inspección SSL), excluya los dominios que aparecen en la tabla anterior de la detección HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2ac10-160">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac10-161">settings-win.data.microsoft.com solo es necesario si tienes dispositivos Windows 10 que ejecutan la versión 1803 o anterior.</span><span class="sxs-lookup"><span data-stu-id="2ac10-161">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="2ac10-162">Las direcciones URL que incluyen v20 solo son necesarias si tienes dispositivos Windows 10 que ejecutan la versión 1803 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2ac10-162">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="2ac10-163">Por ejemplo, es necesario para un dispositivo con Windows 10 que ejecute la versión 1803 o posterior y se incorpore a la región de almacenamiento de datos ```us-v20.events.data.microsoft.com``` de ESTADOS UNIDOS.</span><span class="sxs-lookup"><span data-stu-id="2ac10-163">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="2ac10-164">Si usa Antivirus de Microsoft Defender en su entorno, consulte [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="2ac10-164">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="2ac10-165">Si un proxy o firewall bloquea el tráfico anónimo, ya que el sensor Defender for Endpoint se conecta desde el contexto del sistema, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2ac10-165">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="2ac10-166">Microsoft Monitoring Agent (MMA): requisitos de proxy y firewall para versiones anteriores del cliente de Windows o Windows Server</span><span class="sxs-lookup"><span data-stu-id="2ac10-166">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="2ac10-167">La siguiente información enumera la información de configuración de proxy y firewall necesaria para comunicarse con el agente de Log Analytics (a menudo denominado Microsoft Monitoring Agent) para las versiones anteriores de Windows como Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="2ac10-167">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="2ac10-168">Recurso agent</span><span class="sxs-lookup"><span data-stu-id="2ac10-168">Agent Resource</span></span>|<span data-ttu-id="2ac10-169">Puertos</span><span class="sxs-lookup"><span data-stu-id="2ac10-169">Ports</span></span> |<span data-ttu-id="2ac10-170">Dirección</span><span class="sxs-lookup"><span data-stu-id="2ac10-170">Direction</span></span> |<span data-ttu-id="2ac10-171">Omitir inspección HTTPS</span><span class="sxs-lookup"><span data-stu-id="2ac10-171">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="2ac10-172">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="2ac10-172">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="2ac10-173">Puerto 443</span><span class="sxs-lookup"><span data-stu-id="2ac10-173">Port 443</span></span> |<span data-ttu-id="2ac10-174">Salida</span><span class="sxs-lookup"><span data-stu-id="2ac10-174">Outbound</span></span>|<span data-ttu-id="2ac10-175">Sí</span><span class="sxs-lookup"><span data-stu-id="2ac10-175">Yes</span></span> |  
|<span data-ttu-id="2ac10-176">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="2ac10-176">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="2ac10-177">Puerto 443</span><span class="sxs-lookup"><span data-stu-id="2ac10-177">Port 443</span></span> |<span data-ttu-id="2ac10-178">Salida</span><span class="sxs-lookup"><span data-stu-id="2ac10-178">Outbound</span></span>|<span data-ttu-id="2ac10-179">Sí</span><span class="sxs-lookup"><span data-stu-id="2ac10-179">Yes</span></span> |  
|<span data-ttu-id="2ac10-180">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="2ac10-180">\*.blob.core.windows.net</span></span> |<span data-ttu-id="2ac10-181">Puerto 443</span><span class="sxs-lookup"><span data-stu-id="2ac10-181">Port 443</span></span> |<span data-ttu-id="2ac10-182">Salida</span><span class="sxs-lookup"><span data-stu-id="2ac10-182">Outbound</span></span>|<span data-ttu-id="2ac10-183">Sí</span><span class="sxs-lookup"><span data-stu-id="2ac10-183">Yes</span></span> |
|<span data-ttu-id="2ac10-184">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="2ac10-184">\*.azure-automation.net</span></span> |<span data-ttu-id="2ac10-185">Puerto 443</span><span class="sxs-lookup"><span data-stu-id="2ac10-185">Port 443</span></span> |<span data-ttu-id="2ac10-186">Salida</span><span class="sxs-lookup"><span data-stu-id="2ac10-186">Outbound</span></span>|<span data-ttu-id="2ac10-187">Sí</span><span class="sxs-lookup"><span data-stu-id="2ac10-187">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="2ac10-188">Como solución basada en la nube, el intervalo IP puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="2ac10-188">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="2ac10-189">Se recomienda pasar a la configuración de resolución de DNS.</span><span class="sxs-lookup"><span data-stu-id="2ac10-189">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="2ac10-190">Confirmar los requisitos de la dirección URL del servicio de Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="2ac10-190">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="2ac10-191">Consulta las siguientes instrucciones para eliminar el requisito de comodín (\*) para tu entorno específico al usar Microsoft Monitoring Agent (MMA) para versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="2ac10-191">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="2ac10-192">Incorpore un sistema operativo anterior con Microsoft Monitoring Agent (MMA) en Defender for Endpoint (para obtener más información, vea [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="2ac10-192">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="2ac10-193">Asegúrese de que la máquina se está informando correctamente en el portal del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2ac10-193">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="2ac10-194">Ejecute la herramienta TestCloudConnection.exe desde "C:\Program Files\Microsoft Monitoring Agent\Agent" para validar la conectividad y ver las direcciones URL necesarias para su área de trabajo específica.</span><span class="sxs-lookup"><span data-stu-id="2ac10-194">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="2ac10-195">Consulte la lista de direcciones URL de punto de conexión de Microsoft Defender para obtener la lista completa de requisitos para su región (consulte la hoja de cálculo de direcciones URL de [servicio](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span><span class="sxs-lookup"><span data-stu-id="2ac10-195">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![Imagen del administrador en Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="2ac10-197">Los comodines (\*) usados en los puntos de conexión \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com y \*.agentsvc.azure-automation.net URL se pueden reemplazar por el identificador de área de trabajo específico.</span><span class="sxs-lookup"><span data-stu-id="2ac10-197">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="2ac10-198">El identificador de área de trabajo es específico de su entorno y área de trabajo y se puede encontrar en la sección Incorporación de su inquilino en el portal del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2ac10-198">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="2ac10-199">El extremo de dirección URL \*.blob.core.windows.net se puede reemplazar por las direcciones URL mostradas en la sección "Regla de firewall: \*.blob.core.windows.net" de los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="2ac10-199">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="2ac10-200">En el caso de la incorporación a través del Centro de seguridad de Azure (ASC), se pueden usar varias áreas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2ac10-200">In the case of onboarding via Azure Security Center (ASC), multiple workspaces maybe used.</span></span> <span data-ttu-id="2ac10-201">Deberá realizar el procedimiento de TestCloudConnection.exe anterior en una máquina integrada de cada área de trabajo (para determinar si hay cambios en las direcciones URL \*.blob.core.windows.net entre las áreas de trabajo).</span><span class="sxs-lookup"><span data-stu-id="2ac10-201">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-atp-service-urls"></a><span data-ttu-id="2ac10-202">Comprobar la conectividad del cliente con las direcciones URL del servicio ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2ac10-202">Verify client connectivity to Microsoft Defender ATP service URLs</span></span>

<span data-ttu-id="2ac10-203">Compruebe que la configuración del proxy se ha completado correctamente, que WinHTTP puede detectar y comunicarse mediante el servidor proxy en su entorno y que el servidor proxy permite el tráfico a las direcciones URL del servicio de Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2ac10-203">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="2ac10-204">Descargue la herramienta Analizador de cliente [MDATP](https://aka.ms/mdatpanalyzer) en el equipo en el que se ejecuta el sensor defender para el extremo.</span><span class="sxs-lookup"><span data-stu-id="2ac10-204">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="2ac10-205">Extraiga el contenido de MDATPClientAnalyzer.zip en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2ac10-205">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="2ac10-206">Abra un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="2ac10-206">Open an elevated command-line:</span></span>

    <span data-ttu-id="2ac10-207">a.</span><span class="sxs-lookup"><span data-stu-id="2ac10-207">a.</span></span> <span data-ttu-id="2ac10-208">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="2ac10-208">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="2ac10-209">b.</span><span class="sxs-lookup"><span data-stu-id="2ac10-209">b.</span></span>  <span data-ttu-id="2ac10-210">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2ac10-210">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="2ac10-211">Escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="2ac10-211">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="2ac10-212">Reemplace *HardDrivePath* por la ruta de acceso en la que se descargó la herramienta MDATPClientAnalyzer, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2ac10-212">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="2ac10-213">Extraiga el *MDATPClientAnalyzerResult.zip* creado por la herramienta en la carpeta usada en *HardDrivePath*.</span><span class="sxs-lookup"><span data-stu-id="2ac10-213">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="2ac10-214">Abra *MDATPClientAnalyzerResult.txt* y compruebe que ha realizado los pasos de configuración del proxy para habilitar la detección del servidor y tener acceso a las direcciones URL del servicio.</span><span class="sxs-lookup"><span data-stu-id="2ac10-214">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="2ac10-215">La herramienta comprueba la conectividad de las direcciones URL del servicio de Defender para punto de conexión con las que el cliente está configurado para interactuar.</span><span class="sxs-lookup"><span data-stu-id="2ac10-215">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="2ac10-216">Luego, imprime los resultados en el archivo *MDATPClientAnalyzerResult.txt* para cada URL que se puede usar potencialmente para comunicarse con los servicios de Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2ac10-216">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="2ac10-217">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2ac10-217">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="2ac10-218">Si al menos una de las opciones de conectividad devuelve un estado (200), el cliente de Defender para punto de conexión puede comunicarse con la URL probada correctamente con este método de conectividad.</span><span class="sxs-lookup"><span data-stu-id="2ac10-218">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="2ac10-219">Pero si los resultados de la comprobación de conectividad indican un error, se mostrará un error HTTP (vea los códigos de estado HTTP).</span><span class="sxs-lookup"><span data-stu-id="2ac10-219">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="2ac10-220">A continuación, puede usar las direcciones URL de la tabla que se muestra en Habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión [en el servidor proxy](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="2ac10-220">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="2ac10-221">Las direcciones URL que usará dependerán de la región seleccionada durante el procedimiento de incorporación.</span><span class="sxs-lookup"><span data-stu-id="2ac10-221">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac10-222"> La herramienta Analizador de conectividad no es compatible con la regla ASR [Bloquear las creaciones de procesos procedentes de comandos PSExec y WMI](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="2ac10-222">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="2ac10-223">Tendrá que deshabilitar temporalmente esta regla para ejecutar la herramienta de conectividad.</span><span class="sxs-lookup"><span data-stu-id="2ac10-223">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="2ac10-224">Cuando se establece TelemetryProxyServer, en el Registro o a través de la directiva de grupo, Defender for Endpoint volverá a dirigirse si no puede tener acceso al proxy definido.</span><span class="sxs-lookup"><span data-stu-id="2ac10-224">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ac10-225">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2ac10-225">Related topics</span></span>

- [<span data-ttu-id="2ac10-226">Incorporación de dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="2ac10-226">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="2ac10-227">Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2ac10-227">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
