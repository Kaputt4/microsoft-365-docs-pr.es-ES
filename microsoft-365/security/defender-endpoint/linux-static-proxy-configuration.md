---
title: Detección de proxy estático de ATP de Microsoft Defender para Linux
ms.reviewer: ''
description: Describe cómo configurar ATP de Microsoft Defender para la detección de proxy estático.
keywords: microsoft, defender, atp, linux, instalación, proxy
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 93d654773fc73903cbe0c5de289dcfdf9fd34f9f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687858"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a><span data-ttu-id="b144c-104">Configurar Microsoft Defender para endpoint en Linux para la detección de proxy estático</span><span class="sxs-lookup"><span data-stu-id="b144c-104">Configure Microsoft Defender for Endpoint on Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b144c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b144c-105">**Applies to:**</span></span>
- [<span data-ttu-id="b144c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b144c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b144c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b144c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b144c-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b144c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b144c-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b144c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b144c-110">ATP de Microsoft Defender puede detectar un servidor proxy mediante la ```HTTPS_PROXY``` variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="b144c-110">Microsoft Defender ATP can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="b144c-111">Esta configuración debe configurarse **tanto en** el momento de la instalación como después de instalar el producto.</span><span class="sxs-lookup"><span data-stu-id="b144c-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="b144c-112">Configuración de tiempo de instalación</span><span class="sxs-lookup"><span data-stu-id="b144c-112">Installation time configuration</span></span>

<span data-ttu-id="b144c-113">Durante la instalación, la ```HTTPS_PROXY``` variable de entorno debe pasarse al administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="b144c-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="b144c-114">El administrador de paquetes puede leer esta variable de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="b144c-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="b144c-115">La ```HTTPS_PROXY``` variable se define con la siguiente ```/etc/environment``` línea:</span><span class="sxs-lookup"><span data-stu-id="b144c-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="b144c-116">La `HTTPS_PROXY` variable se define en la configuración global del administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="b144c-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="b144c-117">Por ejemplo, en Ubuntu 18.04, puede agregar la siguiente línea a `/etc/apt/apt.conf.d/proxy.conf` :</span><span class="sxs-lookup"><span data-stu-id="b144c-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="b144c-118">Tenga en cuenta que los dos métodos anteriores podrían definir el proxy que se usará para otras aplicaciones del sistema.</span><span class="sxs-lookup"><span data-stu-id="b144c-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="b144c-119">Use este método con precaución o solo si está pensado para ser una configuración global general.</span><span class="sxs-lookup"><span data-stu-id="b144c-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="b144c-120">La `HTTPS_PROXY` variable se antepone a los comandos de instalación o desinstalación.</span><span class="sxs-lookup"><span data-stu-id="b144c-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="b144c-121">Por ejemplo, con el administrador de paquetes de APT, anteponer la variable de la siguiente manera al instalar Microsoft Defender para endpoint:</span><span class="sxs-lookup"><span data-stu-id="b144c-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="b144c-122">No agregue sudo entre la definición de variable de entorno y apt, de lo contrario, la variable no se propagará.</span><span class="sxs-lookup"><span data-stu-id="b144c-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="b144c-123">La variable de entorno puede definirse de forma `HTTPS_PROXY` similar durante la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="b144c-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="b144c-124">Tenga en cuenta que la instalación y desinstalación no necesariamente producirán errores si se requiere un proxy pero no está configurado.</span><span class="sxs-lookup"><span data-stu-id="b144c-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="b144c-125">Sin embargo, la telemetría no se envía y la operación podría tardar mucho más tiempo debido a los tiempos de espera de la red.</span><span class="sxs-lookup"><span data-stu-id="b144c-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="b144c-126">Configuración posterior a la instalación</span><span class="sxs-lookup"><span data-stu-id="b144c-126">Post installation configuration</span></span>
  
<span data-ttu-id="b144c-127">Después de la instalación, `HTTPS_PROXY` la variable de entorno debe definirse en el archivo de servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="b144c-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="b144c-128">Para ello, abra `/lib/systemd/system/mdatp.service` en un editor de texto mientras se ejecuta como usuario raíz.</span><span class="sxs-lookup"><span data-stu-id="b144c-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="b144c-129">A continuación, puede propagar la variable al servicio de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="b144c-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="b144c-130">Descomprima la línea `#Environment="HTTPS_PROXY=http://address:port"` y especifica la dirección de proxy estática.</span><span class="sxs-lookup"><span data-stu-id="b144c-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="b144c-131">Agregar una línea `EnvironmentFile=/path/to/env/file` .</span><span class="sxs-lookup"><span data-stu-id="b144c-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="b144c-132">Esta ruta de acceso puede apuntar a o a un archivo personalizado, cualquiera de los `/etc/environment` cuales necesita agregar la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="b144c-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="b144c-133">Después de modificar el `mdatp.service` archivo, guárdelo y cierre.</span><span class="sxs-lookup"><span data-stu-id="b144c-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="b144c-134">Reinicie el servicio para que se puedan aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b144c-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="b144c-135">En Ubuntu, esto implica dos comandos:</span><span class="sxs-lookup"><span data-stu-id="b144c-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
