---
title: Solucionar problemas de rendimiento de Microsoft Defender para Endpoint en macOS
description: Solucionar problemas de rendimiento en Microsoft Defender para endpoint en macOS.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 8dfaf1dbf2c3742cc97060c7f9e811c83d0cb023
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698225"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="13ef9-104">Solucionar problemas de rendimiento de Microsoft Defender para Endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="13ef9-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="13ef9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="13ef9-105">**Applies to:**</span></span>

- [<span data-ttu-id="13ef9-106">Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="13ef9-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="13ef9-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="13ef9-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="13ef9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13ef9-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="13ef9-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="13ef9-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="13ef9-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="13ef9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="13ef9-111">En este tema se proporcionan algunos pasos generales que se pueden usar para limitar los problemas de rendimiento relacionados con Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="13ef9-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="13ef9-112">La protección en tiempo real (RTP) es una característica de Microsoft Defender para Endpoint en macOS que supervisa y protege continuamente el dispositivo contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="13ef9-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint on macOS that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="13ef9-113">Consiste en la supervisión de archivos y procesos y otras heurísticas.</span><span class="sxs-lookup"><span data-stu-id="13ef9-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="13ef9-114">Según las aplicaciones que ejecutes y las características del dispositivo, es posible que experimentes un rendimiento subóptimo al ejecutar Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="13ef9-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="13ef9-115">En particular, las aplicaciones o los procesos del sistema que tienen acceso a muchos recursos en un período de tiempo corto pueden provocar problemas de rendimiento en Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="13ef9-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="13ef9-116">Se pueden usar los siguientes pasos para solucionar y mitigar estos problemas:</span><span class="sxs-lookup"><span data-stu-id="13ef9-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="13ef9-117">Deshabilite la protección en tiempo real con uno de los siguientes métodos y observe si el rendimiento mejora.</span><span class="sxs-lookup"><span data-stu-id="13ef9-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="13ef9-118">Este enfoque ayuda a limitar si Microsoft Defender para Endpoint en macOS está contribuyendo a los problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="13ef9-118">This approach helps narrow down whether Microsoft Defender for Endpoint on macOS is contributing to the performance issues.</span></span>

      <span data-ttu-id="13ef9-119">Si su organización no administra el dispositivo, la protección en tiempo real se puede deshabilitar mediante una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="13ef9-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="13ef9-120">Desde la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="13ef9-120">From the user interface.</span></span> <span data-ttu-id="13ef9-121">Abra Microsoft Defender para endpoint en macOS y vaya a **Administrar configuración**.</span><span class="sxs-lookup"><span data-stu-id="13ef9-121">Open Microsoft Defender for Endpoint on macOS and navigate to **Manage settings**.</span></span>

      ![Administrar la captura de pantalla de protección en tiempo real](images/mdatp-36-rtp.png)

    - <span data-ttu-id="13ef9-123">Desde el terminal.</span><span class="sxs-lookup"><span data-stu-id="13ef9-123">From the Terminal.</span></span> <span data-ttu-id="13ef9-124">Por motivos de seguridad, esta operación requiere elevación.</span><span class="sxs-lookup"><span data-stu-id="13ef9-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="13ef9-125">Si su organización administra el dispositivo, el administrador puede deshabilitar la protección en tiempo real con las instrucciones de Establecer preferencias para Microsoft Defender para endpoint [en macOS](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="13ef9-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>
      
      <span data-ttu-id="13ef9-126">Si el problema de rendimiento persiste mientras la protección en tiempo real está desactivada, el origen del problema podría ser el componente de detección y respuesta del extremo.</span><span class="sxs-lookup"><span data-stu-id="13ef9-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="13ef9-127">En este caso, póngase en contacto con el servicio de soporte al cliente para obtener más instrucciones y mitigación.</span><span class="sxs-lookup"><span data-stu-id="13ef9-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="13ef9-128">Abra Finder y vaya a  >  **Utilidades de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="13ef9-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="13ef9-129">Abra **El Monitor de** actividad y analice qué aplicaciones usan los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="13ef9-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="13ef9-130">Algunos ejemplos típicos son los actualizadores de software y los compiladores.</span><span class="sxs-lookup"><span data-stu-id="13ef9-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="13ef9-131">Para buscar las aplicaciones que están desencadenando la mayoría de los exámenes, puedes usar estadísticas en tiempo real recopiladas por Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="13ef9-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="13ef9-132">Esta característica está disponible en la versión 100.90.70 o posterior.</span><span class="sxs-lookup"><span data-stu-id="13ef9-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="13ef9-133">Esta característica está habilitada de forma predeterminada en los canales **Dogfood** **e InsiderFast.**</span><span class="sxs-lookup"><span data-stu-id="13ef9-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="13ef9-134">Si usa un canal de actualización diferente, esta característica se puede habilitar desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="13ef9-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="13ef9-135">Esta característica requiere protección en tiempo real para habilitarse.</span><span class="sxs-lookup"><span data-stu-id="13ef9-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="13ef9-136">Para comprobar el estado de la protección en tiempo real, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="13ef9-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="13ef9-137">Compruebe que la **real_time_protection_enabled** es true.</span><span class="sxs-lookup"><span data-stu-id="13ef9-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="13ef9-138">De lo contrario, ejecute el siguiente comando para habilitarlo:</span><span class="sxs-lookup"><span data-stu-id="13ef9-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="13ef9-139">Para recopilar estadísticas actuales, ejecute:</span><span class="sxs-lookup"><span data-stu-id="13ef9-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      > [!NOTE]
      > <span data-ttu-id="13ef9-140">El **uso de --output json** (tenga en cuenta el guión doble) garantiza que el formato de salida esté listo para el análisis.</span><span class="sxs-lookup"><span data-stu-id="13ef9-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="13ef9-141">El resultado de este comando mostrará todos los procesos y su actividad de examen asociada.</span><span class="sxs-lookup"><span data-stu-id="13ef9-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="13ef9-142">En el sistema Mac, descargue el analizador python de ejemplo high_cpu_parser.py mediante el comando:</span><span class="sxs-lookup"><span data-stu-id="13ef9-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="13ef9-143">El resultado de este comando debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="13ef9-143">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. <span data-ttu-id="13ef9-144">A continuación, escriba los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="13ef9-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="13ef9-145">El resultado de lo anterior es una lista de los principales colaboradores de problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="13ef9-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="13ef9-146">La primera columna es el identificador de proceso (PID), la segunda columna es el nombre del proceso y la última columna es el número de archivos examinados, ordenados por impacto.</span><span class="sxs-lookup"><span data-stu-id="13ef9-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="13ef9-147">Por ejemplo, el resultado del comando será algo parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="13ef9-147">For example, the output of the command will be something like the below:</span></span>

      ```output
        ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
        27432 None 76703
        73467 actool     1249
        73914 xcodebuild 1081
        73873 bash 1050
        27475 None 836
        1    launchd    407
        73468 ibtool     344
        549  telemetryd_v1   325
        4764 None 228
        125  CrashPlanService 164
      ```

      <span data-ttu-id="13ef9-148">Para mejorar el rendimiento de Defender para Endpoint en Mac, busca el que tiene el número más alto en la fila Total de archivos analizados y agrega una exclusión para él.</span><span class="sxs-lookup"><span data-stu-id="13ef9-148">To improve the performance of Defender for Endpoint on Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="13ef9-149">Para obtener más información, vea [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span><span class="sxs-lookup"><span data-stu-id="13ef9-149">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="13ef9-150">La aplicación almacena estadísticas en la memoria y solo realiza un seguimiento de la actividad del archivo desde que se inició y se ha habilitado la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="13ef9-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="13ef9-151">Los procesos que se iniciaron antes o durante períodos en los que la protección en tiempo real estaba desactivada no se cuentan.</span><span class="sxs-lookup"><span data-stu-id="13ef9-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="13ef9-152">Además, solo se cuentan los eventos que desencadenaron exámenes.</span><span class="sxs-lookup"><span data-stu-id="13ef9-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="13ef9-153">Configure Microsoft Defender para endpoint en macOS con exclusiones para los procesos o ubicaciones de disco que contribuyen a los problemas de rendimiento y vuelva a habilitar la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="13ef9-153">Configure Microsoft Defender for Endpoint on macOS with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="13ef9-154">Consulta [Configurar y validar exclusiones para Microsoft Defender para Endpoint en macOS](mac-exclusions.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="13ef9-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint on macOS](mac-exclusions.md) for details.</span></span>
