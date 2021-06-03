---
title: Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para Endpoint en Linux.
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2242d195f4a4ea4b8f0c345d82fa0ad1f947bfa2
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730767"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="76875-104">Microsoft Defender para punto de conexión en Linux</span><span class="sxs-lookup"><span data-stu-id="76875-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="76875-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="76875-105">**Applies to:**</span></span>
- [<span data-ttu-id="76875-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="76875-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76875-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76875-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="76875-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="76875-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76875-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="76875-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="76875-110">En este tema se describe cómo instalar, configurar, actualizar y usar Microsoft Defender para Endpoint en Linux.</span><span class="sxs-lookup"><span data-stu-id="76875-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="76875-111">Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Microsoft Defender para Endpoint en Linux lleve a problemas de rendimiento y efectos secundarios impredecibles.</span><span class="sxs-lookup"><span data-stu-id="76875-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="76875-112">Si la protección de extremo que no es de Microsoft es un requisito absoluto en su entorno, puede aprovechar de forma segura la funcionalidad de Defender para endpoint en Linux EDR después de configurar la funcionalidad antivirus para que se ejecute en modo [pasivo](linux-preferences.md#enable--disable-passive-mode).</span><span class="sxs-lookup"><span data-stu-id="76875-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="76875-113">Cómo instalar Microsoft Defender para Endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="76875-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="76875-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="76875-114">Prerequisites</span></span>

- <span data-ttu-id="76875-115">Acceso al portal de Centro de seguridad de Microsoft Defender web</span><span class="sxs-lookup"><span data-stu-id="76875-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="76875-116">Distribución de Linux con [el administrador del](https://systemd.io/) sistema con sistema</span><span class="sxs-lookup"><span data-stu-id="76875-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="76875-117">Experiencia de nivel principiante en scripts de Linux y BASH</span><span class="sxs-lookup"><span data-stu-id="76875-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="76875-118">Privilegios administrativos en el dispositivo (en caso de implementación manual)</span><span class="sxs-lookup"><span data-stu-id="76875-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="76875-119">El agente de Microsoft Defender para Endpoint en Linux es independiente [del agente OMS](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span><span class="sxs-lookup"><span data-stu-id="76875-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="76875-120">Microsoft Defender para endpoint se basa en su propia canalización de telemetría independiente.</span><span class="sxs-lookup"><span data-stu-id="76875-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="76875-121">Microsoft Defender para Endpoint en Linux aún no está integrado en Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="76875-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="76875-122">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="76875-122">Installation instructions</span></span>

<span data-ttu-id="76875-123">Existen varios métodos y herramientas de implementación que puede usar para instalar y configurar Microsoft Defender para Endpoint en Linux.</span><span class="sxs-lookup"><span data-stu-id="76875-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="76875-124">En general, debe seguir los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="76875-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="76875-125">Asegúrese de que tiene una suscripción de Microsoft Defender para endpoint y de que tiene acceso al portal de [Microsoft Defender para endpoint](microsoft-defender-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="76875-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="76875-126">Implemente Microsoft Defender para Endpoint en Linux mediante uno de los siguientes métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="76875-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="76875-127">La herramienta de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="76875-127">The command-line tool:</span></span>
    - [<span data-ttu-id="76875-128">Implementación manual</span><span class="sxs-lookup"><span data-stu-id="76875-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="76875-129">Herramientas de administración de terceros:</span><span class="sxs-lookup"><span data-stu-id="76875-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="76875-130">Implementar con la herramienta de administración de configuración de Puppet</span><span class="sxs-lookup"><span data-stu-id="76875-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="76875-131">Implementar con una herramienta de administración de configuración de Ansible</span><span class="sxs-lookup"><span data-stu-id="76875-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="76875-132">Si experimenta algún error de instalación, consulte [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="76875-132">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="76875-133">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="76875-133">System requirements</span></span>

- <span data-ttu-id="76875-134">Distribuciones de servidor Linux compatibles y versiones x64 (AMD64/EM64T):</span><span class="sxs-lookup"><span data-stu-id="76875-134">Supported Linux server distributions and x64 (AMD64/EM64T) versions:</span></span>

  - <span data-ttu-id="76875-135">Red Hat Enterprise Linux 7.2 o posterior</span><span class="sxs-lookup"><span data-stu-id="76875-135">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="76875-136">CentOS 7.2 o superior</span><span class="sxs-lookup"><span data-stu-id="76875-136">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="76875-137">Ubuntu 16,04 LTS o superior LTS</span><span class="sxs-lookup"><span data-stu-id="76875-137">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="76875-138">Debian 9 o posterior</span><span class="sxs-lookup"><span data-stu-id="76875-138">Debian 9 or higher</span></span>
  - <span data-ttu-id="76875-139">SUSE Linux Enterprise Server 12 o posterior</span><span class="sxs-lookup"><span data-stu-id="76875-139">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="76875-140">Oracle Linux 7.2 o posterior</span><span class="sxs-lookup"><span data-stu-id="76875-140">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="76875-141">Las distribuciones y las versiones que no se enumeran explícitamente no son compatibles (incluso si se derivan de las distribuciones admitidas oficialmente).</span><span class="sxs-lookup"><span data-stu-id="76875-141">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="76875-142">Versión mínima del kernel 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="76875-142">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="76875-143">La `fanotify` opción kernel debe estar habilitada</span><span class="sxs-lookup"><span data-stu-id="76875-143">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="76875-144">No se admite la ejecución de Defender para Endpoint en Linux en paralelo con otras soluciones de seguridad `fanotify` basadas en.</span><span class="sxs-lookup"><span data-stu-id="76875-144">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="76875-145">Puede dar lugar a resultados impredecibles, incluida la suspensión del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="76875-145">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="76875-146">Espacio en disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="76875-146">Disk space: 1 GB</span></span>

- <span data-ttu-id="76875-147">/opt/microsoft/mdatp/sbin/wdavdaemon requiere permiso ejecutable.</span><span class="sxs-lookup"><span data-stu-id="76875-147">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="76875-148">Para obtener más información, vea "Asegúrese de que el demonio tiene permiso ejecutable" en Solucionar problemas de instalación de [Microsoft Defender para Endpoint en Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span><span class="sxs-lookup"><span data-stu-id="76875-148">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="76875-149">Memoria: 1 GB</span><span class="sxs-lookup"><span data-stu-id="76875-149">Memory: 1 GB</span></span>

    > [!NOTE]
    > <span data-ttu-id="76875-150">Asegúrese de que tiene espacio libre en disco en /var.</span><span class="sxs-lookup"><span data-stu-id="76875-150">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="76875-151">Actualmente, la solución proporciona protección en tiempo real para los siguientes tipos de sistema de archivos:</span><span class="sxs-lookup"><span data-stu-id="76875-151">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="76875-152">Después de habilitar el servicio, es posible que deba configurar la red o el firewall para permitir conexiones salientes entre él y los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="76875-152">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="76875-153">El marco de auditoría ( `auditd` ) debe estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="76875-153">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="76875-154">Los eventos del sistema capturados por las reglas agregadas se agregarán a (s) y pueden afectar a la auditoría de host y `/etc/audit/rules.d/` `audit.log` a la colección ascendente.</span><span class="sxs-lookup"><span data-stu-id="76875-154">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="76875-155">Los eventos agregados por Microsoft Defender para Endpoint en Linux se etiquetarán con `mdatp` clave.</span><span class="sxs-lookup"><span data-stu-id="76875-155">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="76875-156">Conexiones de red</span><span class="sxs-lookup"><span data-stu-id="76875-156">Network connections</span></span>

<span data-ttu-id="76875-157">En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse.</span><span class="sxs-lookup"><span data-stu-id="76875-157">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="76875-158">Debe asegurarse de que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="76875-158">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="76875-159">Si lo hay, es posible que deba crear una regla *de* permitir específicamente para ellos.</span><span class="sxs-lookup"><span data-stu-id="76875-159">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="76875-160">Hoja de cálculo de la lista de dominios</span><span class="sxs-lookup"><span data-stu-id="76875-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="76875-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="76875-161">Description</span></span> |
|:-----|:-----|
|![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión](images/mdatp-urls.png)<br/>  | <span data-ttu-id="76875-163">Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="76875-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="76875-164">Descargue la hoja de cálculo aquí.</span><span class="sxs-lookup"><span data-stu-id="76875-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="76875-165">Para obtener una lista de direcciones URL más específica, vea [Configure proxy and Internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="76875-165">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="76875-166">Defender for Endpoint puede detectar un servidor proxy mediante los siguientes métodos de detección:</span><span class="sxs-lookup"><span data-stu-id="76875-166">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="76875-167">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="76875-167">Transparent proxy</span></span>
- <span data-ttu-id="76875-168">Configuración manual de proxy estático</span><span class="sxs-lookup"><span data-stu-id="76875-168">Manual static proxy configuration</span></span>

<span data-ttu-id="76875-169">Si un proxy o firewall bloquea el tráfico anónimo, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="76875-169">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="76875-170">Para los servidores proxy transparentes, no se necesita ninguna configuración adicional para Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="76875-170">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="76875-171">Para proxy estático, siga los pasos descritos en [Configuración manual de proxy estático.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="76875-171">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="76875-172">Pac, WPAD y proxies autenticados no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="76875-172">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="76875-173">Asegúrese de que solo se usa un proxy estático o un proxy transparente.</span><span class="sxs-lookup"><span data-stu-id="76875-173">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="76875-174">Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="76875-174">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="76875-175">Configure una excepción para la inspección SSL y el servidor proxy para pasar directamente los datos de Defender para Endpoint en Linux a las direcciones URL relevantes sin interceptación.</span><span class="sxs-lookup"><span data-stu-id="76875-175">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="76875-176">Agregar el certificado de interceptación al almacén global no permitirá la interceptación.</span><span class="sxs-lookup"><span data-stu-id="76875-176">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="76875-177">Para ver los pasos de solución de problemas, consulte [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="76875-177">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="76875-178">Cómo actualizar Microsoft Defender para endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="76875-178">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="76875-179">Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.</span><span class="sxs-lookup"><span data-stu-id="76875-179">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="76875-180">Para actualizar Microsoft Defender para Endpoint en Linux, consulte [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span><span class="sxs-lookup"><span data-stu-id="76875-180">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="76875-181">Cómo configurar Microsoft Defender para endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="76875-181">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="76875-182">Las instrucciones sobre cómo configurar el producto en entornos empresariales están disponibles en Establecer preferencias para [Microsoft Defender para Endpoint en Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="76875-182">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="76875-183">Recursos</span><span class="sxs-lookup"><span data-stu-id="76875-183">Resources</span></span>

- <span data-ttu-id="76875-184">Para obtener más información sobre el registro, la desinstalación u otros temas, vea [Resources](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="76875-184">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
