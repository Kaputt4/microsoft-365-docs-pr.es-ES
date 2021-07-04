---
title: Configurar el proxy de dispositivo y la configuración de conexión a Internet
description: Configure la configuración de Microsoft Defender para proxy de extremo e Internet para habilitar la comunicación con el servicio en la nube.
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: af50e3c2a6db1a09d546bfa06b26c80dcf4481e5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290092"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="8edae-104">Configurar las opciones de proxy de dispositivo y de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="8edae-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8edae-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8edae-105">**Applies to:**</span></span>
- [<span data-ttu-id="8edae-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8edae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8edae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8edae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8edae-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8edae-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8edae-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="8edae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="8edae-110">El sensor Defender for Endpoint requiere que Microsoft Windows HTTP (WinHTTP) informe de los datos del sensor y se comunique con el servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8edae-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="8edae-111">El sensor de Defender for Endpoint incrustado se ejecuta en el contexto del sistema mediante la cuenta LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="8edae-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="8edae-112">El sensor usa Microsoft Windows HTTP Services (WinHTTP) para habilitar la comunicación con el servicio en la nube de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8edae-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

> [!TIP]
> <span data-ttu-id="8edae-113">Para las organizaciones que usan servidores proxy de reenvío como puerta de enlace a Internet, puede usar la protección de red para investigar lo que ocurre detrás de un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="8edae-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="8edae-114">Para obtener más información, vea [Investigar eventos de conexión que ocurren detrás de los servidores proxy de reenvío](investigate-behind-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="8edae-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="8edae-115">La configuración de WinHTTP es independiente de la configuración de proxy de exploración de Internet de Windows (WinINet) y solo puede detectar un servidor proxy mediante los siguientes métodos de detección:</span><span class="sxs-lookup"><span data-stu-id="8edae-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="8edae-116">Métodos de detección automática:</span><span class="sxs-lookup"><span data-stu-id="8edae-116">Auto-discovery methods:</span></span>

  - <span data-ttu-id="8edae-117">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="8edae-117">Transparent proxy</span></span>

  - <span data-ttu-id="8edae-118">Protocolo de detección automática de proxy web (WPAD)</span><span class="sxs-lookup"><span data-stu-id="8edae-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="8edae-119">Si usas proxy transparente o WPAD en la topología de red, no necesitas opciones de configuración especiales.</span><span class="sxs-lookup"><span data-stu-id="8edae-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="8edae-120">Para obtener más información sobre las exclusiones de url de extremo de Defender en el proxy, vea Habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión [en el servidor proxy.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="8edae-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="8edae-121">Configuración del proxy estático manual:</span><span class="sxs-lookup"><span data-stu-id="8edae-121">Manual static proxy configuration:</span></span>

  - <span data-ttu-id="8edae-122">Configuración basada en el registro</span><span class="sxs-lookup"><span data-stu-id="8edae-122">Registry based configuration</span></span>

  - <span data-ttu-id="8edae-123">WinHTTP se configuró con el comando netsh (adecuado solo para dispositivos de escritorio en una topología estable, por ejemplo, un escritorio en una red corporativa detrás del mismo proxy)</span><span class="sxs-lookup"><span data-stu-id="8edae-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="8edae-124">Configurar manualmente el servidor proxy mediante un proxy estático basado en el registro</span><span class="sxs-lookup"><span data-stu-id="8edae-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="8edae-125">Configure un proxy estático basado en el Registro para permitir que solo el sensor Defender for Endpoint informe datos de diagnóstico y se comunique con Defender for Endpoint services si un equipo no tiene permiso para conectarse a Internet.</span><span class="sxs-lookup"><span data-stu-id="8edae-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not permitted to connect to the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="8edae-126">Al usar esta opción en Windows 10 o Windows Server 2019, se recomienda tener la siguiente compilación (o posterior) y el paquete acumulativo de actualizaciones acumulativas:</span><span class="sxs-lookup"><span data-stu-id="8edae-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span>
>
> - <span data-ttu-id="8edae-127">Windows 10, versión 1809 o Windows Server 2019 :https://support.microsoft.com/kb/5001384</span><span class="sxs-lookup"><span data-stu-id="8edae-127">Windows 10, version 1809 or Windows Server 2019 - https://support.microsoft.com/kb/5001384</span></span>
> - <span data-ttu-id="8edae-128">Windows 10, versión 1909 -https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="8edae-128">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span>
> - <span data-ttu-id="8edae-129">Windows 10, versión 2004 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="8edae-129">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span>
> - <span data-ttu-id="8edae-130">Windows 10, versión 20H2 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="8edae-130">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span>
>
> <span data-ttu-id="8edae-131">Estas actualizaciones mejoran la conectividad y la confiabilidad del canal CnC (comando y control).</span><span class="sxs-lookup"><span data-stu-id="8edae-131">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span>

<span data-ttu-id="8edae-132">El proxy estático se puede configurar mediante la directiva de grupo (GP).</span><span class="sxs-lookup"><span data-stu-id="8edae-132">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="8edae-133">La directiva de grupo se puede encontrar aquí:</span><span class="sxs-lookup"><span data-stu-id="8edae-133">The group policy can be found under:</span></span>

- <span data-ttu-id="8edae-134">**Plantillas administrativas > Windows componentes > recopilación de datos y versiones preliminares > Configurar el uso de proxy autenticado para el servicio de telemetría y experiencia del usuario conectado**</span><span class="sxs-lookup"><span data-stu-id="8edae-134">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

  <span data-ttu-id="8edae-135">Estabilizelo **en Habilitado** y seleccione **Deshabilitar el uso de proxy autenticado.**</span><span class="sxs-lookup"><span data-stu-id="8edae-135">Set it to **Enabled** and select **Disable Authenticated Proxy usage**.</span></span>

  ![Imagen de configuración de directiva de grupo1](images/atp-gpo-proxy1.png)

- <span data-ttu-id="8edae-137">**Plantillas administrativas > Windows componentes > recopilación** de datos y compilaciones de vista previa > Configurar la telemetría y las experiencias de usuario conectadas:</span><span class="sxs-lookup"><span data-stu-id="8edae-137">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

  <span data-ttu-id="8edae-138">Configurar el servidor proxy</span><span class="sxs-lookup"><span data-stu-id="8edae-138">Configure the proxy</span></span>

  ![Imagen de configuración de directiva de grupo2](images/atp-gpo-proxy2.png)

  <span data-ttu-id="8edae-140">La directiva establece dos valores del Registro, `TelemetryProxyServer` como REG_SZ y como `DisableEnterpriseAuthProxy` REG_DWORD, en la clave del Registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection` .</span><span class="sxs-lookup"><span data-stu-id="8edae-140">The policy sets two registry values, `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD, under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

  <span data-ttu-id="8edae-141">El valor del `TelemetryProxyServer` Registro tiene el siguiente formato de cadena:</span><span class="sxs-lookup"><span data-stu-id="8edae-141">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

  ```text
  <server name or ip>:<port>
  ```

  <span data-ttu-id="8edae-142">Por ejemplo, 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="8edae-142">For example: 10.0.0.6:8080</span></span>

  <span data-ttu-id="8edae-143">El valor del registro `DisableEnterpriseAuthProxy` debe establecerse en 1.</span><span class="sxs-lookup"><span data-stu-id="8edae-143">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="8edae-144">Configurar el servidor proxy manualmente mediante el comando netsh</span><span class="sxs-lookup"><span data-stu-id="8edae-144">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="8edae-145">Use netsh para configurar un proxy estático en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="8edae-145">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="8edae-146">Esto afectará a todas las aplicaciones, incluidos los servicios de Windows que utilicen WinHTTP con el proxy predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8edae-146">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="8edae-147">Los portátiles que cambian la topología (por ejemplo: de la oficina a la casa) no funcionan correctamente con netsh.</span><span class="sxs-lookup"><span data-stu-id="8edae-147">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="8edae-148">Use la configuración de proxy estático basada en el registro.</span><span class="sxs-lookup"><span data-stu-id="8edae-148">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="8edae-149">Abra un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="8edae-149">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="8edae-150">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="8edae-150">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="8edae-151">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="8edae-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="8edae-152">Escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="8edae-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="8edae-153">Por ejemplo: `netsh winhttp set proxy 10.0.0.6:8080`</span><span class="sxs-lookup"><span data-stu-id="8edae-153">For example: `netsh winhttp set proxy 10.0.0.6:8080`</span></span>

<span data-ttu-id="8edae-154">Para restablecer el servidor proxy winhttp, escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="8edae-154">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="8edae-155">Para obtener más información, vea [Sintaxis de comando Netsh, contextos y formatos](/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="8edae-155">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="8edae-156">Habilitar el acceso a las direcciones URL del servicio de punto de conexión de Microsoft Defender en el servidor proxy</span><span class="sxs-lookup"><span data-stu-id="8edae-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="8edae-157">Si un servidor proxy o firewall bloquea todo el tráfico de forma predeterminada y permite únicamente el acceso a dominios específicos, agregue los dominios que aparecen en la hoja descargable a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="8edae-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="8edae-158">En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse.</span><span class="sxs-lookup"><span data-stu-id="8edae-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="8edae-159">Debe asegurarse de que no hay reglas de filtrado de red o firewall que denieguen el acceso *a* estas direcciones URL, o puede que necesite crear una regla de permitir específicamente para ellas.</span><span class="sxs-lookup"><span data-stu-id="8edae-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="8edae-160">Hoja de cálculo de la lista de dominios</span><span class="sxs-lookup"><span data-stu-id="8edae-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="8edae-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="8edae-161">Description</span></span> |
|:-----|:-----|
|![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión](images/mdatp-urls.png)<br/>  | <span data-ttu-id="8edae-163">Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8edae-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="8edae-164">Descargue la hoja de cálculo aquí.</span><span class="sxs-lookup"><span data-stu-id="8edae-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

<span data-ttu-id="8edae-165">Si un servidor proxy o firewall tiene habilitada la detección HTTPS (inspección SSL), excluya los dominios que aparecen en la tabla anterior de la detección HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8edae-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="8edae-166">settings-win.data.microsoft.com solo es necesario si tienes Windows 10 dispositivos que ejecutan la versión 1803 o anterior.</span><span class="sxs-lookup"><span data-stu-id="8edae-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>
>
> <span data-ttu-id="8edae-167">Las direcciones URL que incluyen v20 solo son necesarias si Windows 10 dispositivos que ejecutan la versión 1803 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8edae-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="8edae-168">Por ejemplo, es necesario para un dispositivo Windows 10 que ejecute la versión 1803 o posterior y se incorpore a la región de datos `us-v20.events.data.microsoft.com` Storage ESTADOS UNIDOS.</span><span class="sxs-lookup"><span data-stu-id="8edae-168">For example, `us-v20.events.data.microsoft.com` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>
>
> <span data-ttu-id="8edae-169">Si está usando Antivirus de Microsoft Defender en su entorno, vea [Configure network connections to the Antivirus de Microsoft Defender cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="8edae-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="8edae-170">Si un proxy o firewall bloquea el tráfico anónimo, ya que el sensor Defender for Endpoint se conecta desde el contexto del sistema, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8edae-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="8edae-171">Microsoft Monitoring Agent (MMA): requisitos de proxy y firewall para versiones anteriores de Windows cliente o Windows server</span><span class="sxs-lookup"><span data-stu-id="8edae-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="8edae-172">La siguiente información enumera la información de configuración de proxy y firewall necesaria para comunicarse con el agente de Log Analytics (a menudo denominado Microsoft Monitoring Agent) para las versiones anteriores de Windows como Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="8edae-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="8edae-173">Recurso del agente</span><span class="sxs-lookup"><span data-stu-id="8edae-173">Agent Resource</span></span>|<span data-ttu-id="8edae-174">Puertos</span><span class="sxs-lookup"><span data-stu-id="8edae-174">Ports</span></span> |<span data-ttu-id="8edae-175">Dirección</span><span class="sxs-lookup"><span data-stu-id="8edae-175">Direction</span></span> |<span data-ttu-id="8edae-176">Omitir la inspección HTTP</span><span class="sxs-lookup"><span data-stu-id="8edae-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|
|<span data-ttu-id="8edae-177">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="8edae-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="8edae-178">Puerto 443</span><span class="sxs-lookup"><span data-stu-id="8edae-178">Port 443</span></span> |<span data-ttu-id="8edae-179">Salida</span><span class="sxs-lookup"><span data-stu-id="8edae-179">Outbound</span></span>|<span data-ttu-id="8edae-180">Yes</span><span class="sxs-lookup"><span data-stu-id="8edae-180">Yes</span></span> |  
|<span data-ttu-id="8edae-181">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="8edae-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="8edae-182">Puerto 443</span><span class="sxs-lookup"><span data-stu-id="8edae-182">Port 443</span></span> |<span data-ttu-id="8edae-183">Salida</span><span class="sxs-lookup"><span data-stu-id="8edae-183">Outbound</span></span>|<span data-ttu-id="8edae-184">Yes</span><span class="sxs-lookup"><span data-stu-id="8edae-184">Yes</span></span> |  
|<span data-ttu-id="8edae-185">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="8edae-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="8edae-186">Puerto 443</span><span class="sxs-lookup"><span data-stu-id="8edae-186">Port 443</span></span> |<span data-ttu-id="8edae-187">Salida</span><span class="sxs-lookup"><span data-stu-id="8edae-187">Outbound</span></span>|<span data-ttu-id="8edae-188">Yes</span><span class="sxs-lookup"><span data-stu-id="8edae-188">Yes</span></span> |
|<span data-ttu-id="8edae-189">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="8edae-189">\*.azure-automation.net</span></span> |<span data-ttu-id="8edae-190">Puerto 443</span><span class="sxs-lookup"><span data-stu-id="8edae-190">Port 443</span></span> |<span data-ttu-id="8edae-191">Salida</span><span class="sxs-lookup"><span data-stu-id="8edae-191">Outbound</span></span>|<span data-ttu-id="8edae-192">Yes</span><span class="sxs-lookup"><span data-stu-id="8edae-192">Yes</span></span> |  

> [!NOTE]
> <span data-ttu-id="8edae-193">Como solución basada en la nube, el intervalo IP puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="8edae-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="8edae-194">Se recomienda pasar a la configuración de resolución de DNS.</span><span class="sxs-lookup"><span data-stu-id="8edae-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="8edae-195">Confirmar Microsoft Monitoring Agent url de servicio (MMA)</span><span class="sxs-lookup"><span data-stu-id="8edae-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="8edae-196">Consulte las siguientes instrucciones para eliminar el requisito de comodín (\*) para su entorno específico al usar el Microsoft Monitoring Agent (MMA) para versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="8edae-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1. <span data-ttu-id="8edae-197">Incorporar un sistema operativo anterior con el Microsoft Monitoring Agent (MMA) en Defender para endpoint (para obtener más información, vea [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="8edae-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2. <span data-ttu-id="8edae-198">Asegúrese de que la máquina se está informando correctamente en el portal Centro de seguridad de Microsoft Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="8edae-198">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3. <span data-ttu-id="8edae-199">Ejecute la herramienta TestCloudConnection.exe desde "C:\Program Files\Microsoft Monitoring Agent\Agent" para validar la conectividad y ver las direcciones URL necesarias para su área de trabajo específica.</span><span class="sxs-lookup"><span data-stu-id="8edae-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4. <span data-ttu-id="8edae-200">Consulte la lista de direcciones URL de punto de conexión de Microsoft Defender para obtener la lista completa de requisitos para su región (consulte la hoja de cálculo de direcciones URL de [servicio](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span><span class="sxs-lookup"><span data-stu-id="8edae-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

    ![Imagen del administrador en Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="8edae-202">Los caracteres comodín ( ) usados en los extremos de dirección \* \* URL \* .ods.opinsights.azure.com, .oms.opinsights.azure.com y .agentsvc.azure-automation.net se pueden reemplazar por el identificador de área de \* trabajo específico.</span><span class="sxs-lookup"><span data-stu-id="8edae-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="8edae-203">El identificador de área de trabajo es específico de su entorno y área de trabajo y se puede encontrar en la sección Incorporación del espacio empresarial en el portal Centro de seguridad de Microsoft Defender área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8edae-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="8edae-204">El extremo de dirección URL .blob.core.windows.net se puede reemplazar por las direcciones URL mostradas en la sección "Regla de \* firewall: \* .blob.core.windows.net" de los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="8edae-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the "Firewall Rule: \*.blob.core.windows.net" section of the test results.</span></span>

> [!NOTE]
> <span data-ttu-id="8edae-205">En el caso de la incorporación a través de Azure Defender, se pueden usar varias áreas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8edae-205">In the case of onboarding via Azure Defender, multiple workspaces maybe used.</span></span> <span data-ttu-id="8edae-206">Deberá realizar el procedimiento de TestCloudConnection.exe anterior en una máquina integrada de cada área de trabajo (para determinar si hay cambios en las direcciones URL \*.blob.core.windows.net entre las áreas de trabajo).</span><span class="sxs-lookup"><span data-stu-id="8edae-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="8edae-207">Comprobar la conectividad del cliente a Microsoft Defender para las direcciones URL del servicio endpoint</span><span class="sxs-lookup"><span data-stu-id="8edae-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="8edae-208">Compruebe que la configuración del proxy se ha completado correctamente, que WinHTTP puede detectar y comunicarse mediante el servidor proxy en su entorno y que el servidor proxy permite el tráfico a las direcciones URL del servicio de Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8edae-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="8edae-209">Descargue la herramienta Analizador de cliente [MDATP](https://aka.ms/mdatpanalyzer) en el equipo en el que se ejecuta el sensor defender para el extremo.</span><span class="sxs-lookup"><span data-stu-id="8edae-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="8edae-210">Extraiga el contenido de MDATPClientAnalyzer.zip en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8edae-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="8edae-211">Abra un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="8edae-211">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="8edae-212">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="8edae-212">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="8edae-213">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="8edae-213">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="8edae-214">Escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="8edae-214">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="8edae-215">Reemplace *HardDrivePath* por la ruta de acceso en la que se descargó la herramienta MDATPClientAnalyzer, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8edae-215">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example:</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="8edae-216">Extraiga el *MDATPClientAnalyzerResult.zip* creado por la herramienta en la carpeta usada en *HardDrivePath*.</span><span class="sxs-lookup"><span data-stu-id="8edae-216">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="8edae-217">Abra *MDATPClientAnalyzerResult.txt* y compruebe que ha realizado los pasos de configuración del proxy para habilitar la detección del servidor y tener acceso a las direcciones URL del servicio.</span><span class="sxs-lookup"><span data-stu-id="8edae-217">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>

   <span data-ttu-id="8edae-218">La herramienta comprueba la conectividad de las direcciones URL del servicio de Defender para punto de conexión con las que el cliente está configurado para interactuar.</span><span class="sxs-lookup"><span data-stu-id="8edae-218">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="8edae-219">Luego, imprime los resultados en el archivo *MDATPClientAnalyzerResult.txt* para cada URL que se puede usar potencialmente para comunicarse con los servicios de Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8edae-219">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="8edae-220">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8edae-220">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="8edae-221">Si al menos una de las opciones de conectividad devuelve un estado (200), el cliente de Defender para punto de conexión puede comunicarse con la URL probada correctamente con este método de conectividad.</span><span class="sxs-lookup"><span data-stu-id="8edae-221">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span>

<span data-ttu-id="8edae-222">Pero si los resultados de la comprobación de conectividad indican un error, se mostrará un error HTTP (vea los códigos de estado HTTP).</span><span class="sxs-lookup"><span data-stu-id="8edae-222">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="8edae-223">A continuación, puede usar las direcciones URL de la tabla que se muestra en Habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión [en el servidor proxy](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="8edae-223">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="8edae-224">Las direcciones URL que usará dependerán de la región seleccionada durante el procedimiento de incorporación.</span><span class="sxs-lookup"><span data-stu-id="8edae-224">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="8edae-225">[ La herramienta Analizador de conectividad no es compatible con la regla ASR ](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)Bloquear las creaciones de procesos procedentes de comandos PSExec y WMI.</span><span class="sxs-lookup"><span data-stu-id="8edae-225">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="8edae-226">Tendrá que deshabilitar temporalmente esta regla para ejecutar la herramienta de conectividad.</span><span class="sxs-lookup"><span data-stu-id="8edae-226">You will need to temporarily disable this rule to run the connectivity tool.</span></span>
>
> <span data-ttu-id="8edae-227">Cuando se establece TelemetryProxyServer, en el Registro o a través de la directiva de grupo, Defender for Endpoint volverá a dirigirse si no puede tener acceso al proxy definido.</span><span class="sxs-lookup"><span data-stu-id="8edae-227">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8edae-228">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8edae-228">Related topics</span></span>

- [<span data-ttu-id="8edae-229">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="8edae-229">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="8edae-230">Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8edae-230">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
