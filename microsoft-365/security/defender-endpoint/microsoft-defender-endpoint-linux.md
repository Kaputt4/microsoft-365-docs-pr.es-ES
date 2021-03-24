---
title: ATP de Microsoft Defender para Linux
ms.reviewer: ''
description: Describe cómo instalar y usar ATP de Microsoft Defender para Linux.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: ce7b15a727ddfa9b0d2bc68b7901f2e79aaf0721
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073000"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="6ab58-104">Microsoft Defender para endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="6ab58-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6ab58-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6ab58-105">**Applies to:**</span></span>
- [<span data-ttu-id="6ab58-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6ab58-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6ab58-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ab58-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6ab58-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="6ab58-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6ab58-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6ab58-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6ab58-110">En este tema se describe cómo instalar, configurar, actualizar y usar Microsoft Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="6ab58-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="6ab58-111">Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Microsoft Defender para Endpoint para Linux cause problemas de rendimiento y errores impredecibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="6ab58-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="6ab58-112">Cómo instalar Microsoft Defender para Endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="6ab58-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6ab58-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6ab58-113">Prerequisites</span></span>

- <span data-ttu-id="6ab58-114">Acceso al portal del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6ab58-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="6ab58-115">Distribución de Linux con [el administrador del](https://systemd.io/) sistema con sistema</span><span class="sxs-lookup"><span data-stu-id="6ab58-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="6ab58-116">Experiencia de nivel principiante en scripts de Linux y BASH</span><span class="sxs-lookup"><span data-stu-id="6ab58-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="6ab58-117">Privilegios administrativos en el dispositivo (en caso de implementación manual)</span><span class="sxs-lookup"><span data-stu-id="6ab58-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="6ab58-118">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="6ab58-118">Installation instructions</span></span>

<span data-ttu-id="6ab58-119">Existen varios métodos y herramientas de implementación que puede usar para instalar y configurar Microsoft Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="6ab58-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="6ab58-120">En general, debe seguir los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="6ab58-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="6ab58-121">Asegúrese de que tiene una suscripción de Microsoft Defender para endpoint y de que tiene acceso al portal de [Microsoft Defender para endpoint](microsoft-defender-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="6ab58-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="6ab58-122">Implemente Microsoft Defender para Endpoint para Linux con uno de los siguientes métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="6ab58-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="6ab58-123">La herramienta de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="6ab58-123">The command-line tool:</span></span>
    - [<span data-ttu-id="6ab58-124">Implementación manual</span><span class="sxs-lookup"><span data-stu-id="6ab58-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="6ab58-125">Herramientas de administración de terceros:</span><span class="sxs-lookup"><span data-stu-id="6ab58-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="6ab58-126">Implementar con la herramienta de administración de configuración de Puppet</span><span class="sxs-lookup"><span data-stu-id="6ab58-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="6ab58-127">Implementar con una herramienta de administración de configuración de Ansible</span><span class="sxs-lookup"><span data-stu-id="6ab58-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="6ab58-128">Si experimenta algún error de instalación, consulte [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="6ab58-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="6ab58-129">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="6ab58-129">System requirements</span></span>

- <span data-ttu-id="6ab58-130">Versiones y distribuciones de servidor Linux compatibles:</span><span class="sxs-lookup"><span data-stu-id="6ab58-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="6ab58-131">Red Hat Enterprise Linux 7.2 o posterior</span><span class="sxs-lookup"><span data-stu-id="6ab58-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="6ab58-132">CentOS 7.2 o superior</span><span class="sxs-lookup"><span data-stu-id="6ab58-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="6ab58-133">Ubuntu 16,04 LTS o superior LTS</span><span class="sxs-lookup"><span data-stu-id="6ab58-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="6ab58-134">Debian 9 o posterior</span><span class="sxs-lookup"><span data-stu-id="6ab58-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="6ab58-135">SUSE Linux Enterprise Server 12 o posterior</span><span class="sxs-lookup"><span data-stu-id="6ab58-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="6ab58-136">Oracle Linux 7.2 o posterior</span><span class="sxs-lookup"><span data-stu-id="6ab58-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="6ab58-137">Versión mínima del kernel 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="6ab58-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="6ab58-138">La `fanotify` opción kernel debe estar habilitada</span><span class="sxs-lookup"><span data-stu-id="6ab58-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="6ab58-139">No se admite la ejecución de Defender para Endpoint para Linux en paralelo con otras soluciones de seguridad `fanotify` basadas en.</span><span class="sxs-lookup"><span data-stu-id="6ab58-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="6ab58-140">Puede dar lugar a resultados impredecibles, incluida la suspensión del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6ab58-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="6ab58-141">Espacio en disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="6ab58-141">Disk space: 1GB</span></span>
- <span data-ttu-id="6ab58-142">Actualmente, la solución proporciona protección en tiempo real para los siguientes tipos de sistema de archivos:</span><span class="sxs-lookup"><span data-stu-id="6ab58-142">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="6ab58-143">Después de habilitar el servicio, es posible que deba configurar la red o el firewall para permitir conexiones salientes entre él y los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="6ab58-143">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="6ab58-144">El marco de auditoría ( `auditd` ) debe estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="6ab58-144">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="6ab58-145">Los eventos del sistema capturados por las reglas agregadas se agregarán a los registros de auditoría y pueden afectar a la auditoría de host y `audit.logs` a la colección ascendente.</span><span class="sxs-lookup"><span data-stu-id="6ab58-145">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="6ab58-146">Los eventos agregados por Microsoft Defender para Endopoint para Linux se etiquetarán con `mdatp` clave.</span><span class="sxs-lookup"><span data-stu-id="6ab58-146">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="6ab58-147">Conexiones de red</span><span class="sxs-lookup"><span data-stu-id="6ab58-147">Network connections</span></span>

<span data-ttu-id="6ab58-148">En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse.</span><span class="sxs-lookup"><span data-stu-id="6ab58-148">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="6ab58-149">Debe asegurarse de que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="6ab58-149">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="6ab58-150">Si lo hay, es posible que deba crear una regla *de* permitir específicamente para ellos.</span><span class="sxs-lookup"><span data-stu-id="6ab58-150">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="6ab58-151">**Hoja de cálculo de la lista de dominios**</span><span class="sxs-lookup"><span data-stu-id="6ab58-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="6ab58-152">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6ab58-152">**Description**</span></span>|
|:-----|:-----|
|![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión](images/mdatp-urls.png)<br/>  | <span data-ttu-id="6ab58-154">Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6ab58-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="6ab58-155">Descargue la hoja de cálculo aquí.</span><span class="sxs-lookup"><span data-stu-id="6ab58-155">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="6ab58-156">Para obtener una lista de direcciones URL más específica, vea [Configure proxy and Internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="6ab58-156">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="6ab58-157">Defender for Endpoint puede detectar un servidor proxy mediante los siguientes métodos de detección:</span><span class="sxs-lookup"><span data-stu-id="6ab58-157">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="6ab58-158">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="6ab58-158">Transparent proxy</span></span>
- <span data-ttu-id="6ab58-159">Configuración manual de proxy estático</span><span class="sxs-lookup"><span data-stu-id="6ab58-159">Manual static proxy configuration</span></span>

<span data-ttu-id="6ab58-160">Si un proxy o firewall bloquea el tráfico anónimo, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6ab58-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="6ab58-161">Para los servidores proxy transparentes, no se necesita ninguna configuración adicional para Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6ab58-161">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="6ab58-162">Para proxy estático, siga los pasos descritos en [Configuración manual de proxy estático.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="6ab58-162">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="6ab58-163">Pac, WPAD y proxies autenticados no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="6ab58-163">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="6ab58-164">Asegúrese de que solo se usa un proxy estático o un proxy transparente.</span><span class="sxs-lookup"><span data-stu-id="6ab58-164">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="6ab58-165">Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6ab58-165">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="6ab58-166">Configure una excepción para la inspección SSL y el servidor proxy para que pasen directamente los datos de Defender for Endpoint for Linux a las direcciones URL relevantes sin interceptación.</span><span class="sxs-lookup"><span data-stu-id="6ab58-166">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="6ab58-167">Agregar el certificado de interceptación al almacén global no permitirá la interceptación.</span><span class="sxs-lookup"><span data-stu-id="6ab58-167">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="6ab58-168">Para ver los pasos de solución de problemas, consulte [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="6ab58-168">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="6ab58-169">Cómo actualizar Microsoft Defender para Endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="6ab58-169">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="6ab58-170">Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.</span><span class="sxs-lookup"><span data-stu-id="6ab58-170">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="6ab58-171">Para actualizar Microsoft Defender para Endpoint para Linux, consulte [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span><span class="sxs-lookup"><span data-stu-id="6ab58-171">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="6ab58-172">Cómo configurar Microsoft Defender para endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="6ab58-172">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="6ab58-173">Las instrucciones sobre cómo configurar el producto en entornos empresariales están disponibles en Establecer preferencias para [Microsoft Defender para Endpoint para Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="6ab58-173">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="6ab58-174">Recursos</span><span class="sxs-lookup"><span data-stu-id="6ab58-174">Resources</span></span>

- <span data-ttu-id="6ab58-175">Para obtener más información sobre el registro, la desinstalación u otros temas, vea [Resources](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="6ab58-175">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
