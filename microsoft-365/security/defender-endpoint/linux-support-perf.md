---
title: Solucionar problemas de rendimiento de ATP de Microsoft Defender para Linux
description: Solucionar problemas de rendimiento en ATP de Microsoft Defender para Linux.
keywords: microsoft, defender, atp, linux, performance
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8865da0c8080213f6a2b82f78a6b31983c50409
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688629"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="36613-104">Solucionar problemas de rendimiento de Microsoft Defender para Endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="36613-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="36613-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="36613-105">**Applies to:**</span></span>
- [<span data-ttu-id="36613-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="36613-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="36613-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36613-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="36613-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="36613-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="36613-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="36613-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="36613-110">En este artículo se proporcionan algunos pasos generales que se pueden usar para limitar los problemas de rendimiento relacionados con Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="36613-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="36613-111">La protección en tiempo real (RTP) es una característica de Defender para Endpoint para Linux que supervisa y protege continuamente el dispositivo contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="36613-111">Real-time protection (RTP) is a feature of Defender for Endpoint for Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="36613-112">Consiste en la supervisión de archivos y procesos y otras heurísticas.</span><span class="sxs-lookup"><span data-stu-id="36613-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="36613-113">Según las aplicaciones que se ejecuten y las características del dispositivo, es posible que experimentes un rendimiento subóptimo al ejecutar Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="36613-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint for Linux.</span></span> <span data-ttu-id="36613-114">En particular, las aplicaciones o los procesos del sistema que tienen acceso a muchos recursos en un período de tiempo corto pueden provocar problemas de rendimiento en Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="36613-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="36613-115">Antes de empezar, **asegúrate de que otros productos de seguridad no se estén ejecutando actualmente en el dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="36613-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="36613-116">Varios productos de seguridad pueden tener conflictos e impactar en el rendimiento del host.</span><span class="sxs-lookup"><span data-stu-id="36613-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="36613-117">Se pueden usar los siguientes pasos para solucionar y mitigar estos problemas:</span><span class="sxs-lookup"><span data-stu-id="36613-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="36613-118">Deshabilite la protección en tiempo real con uno de los siguientes métodos y observe si el rendimiento mejora.</span><span class="sxs-lookup"><span data-stu-id="36613-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="36613-119">Este enfoque ayuda a limitar si Defender for Endpoint para Linux está contribuyendo a los problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="36613-119">This approach helps narrow down whether Defender for Endpoint for Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="36613-120">Si su organización no administra el dispositivo, la protección en tiempo real se puede deshabilitar desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="36613-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="36613-121">Si su organización administra el dispositivo, el administrador puede deshabilitar la protección en tiempo real con las instrucciones de Establecer preferencias para Defender para Endpoint [para Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="36613-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="36613-122">Si el problema de rendimiento persiste mientras la protección en tiempo real está desactivada, el origen del problema podría ser el componente de detección y respuesta del extremo.</span><span class="sxs-lookup"><span data-stu-id="36613-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="36613-123">En este caso, póngase en contacto con el servicio de soporte al cliente para obtener más instrucciones y mitigación.</span><span class="sxs-lookup"><span data-stu-id="36613-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="36613-124">Para buscar las aplicaciones que desencadenan la mayoría de los exámenes, puede usar estadísticas en tiempo real recopiladas por Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="36613-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36613-125">Esta característica está disponible en la versión 100.90.70 o posterior.</span><span class="sxs-lookup"><span data-stu-id="36613-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="36613-126">Esta característica está habilitada de forma predeterminada en los `Dogfood` `InsiderFast` canales y.</span><span class="sxs-lookup"><span data-stu-id="36613-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="36613-127">Si usa un canal de actualización diferente, esta característica se puede habilitar desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="36613-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="36613-128">Esta característica requiere protección en tiempo real para habilitarse.</span><span class="sxs-lookup"><span data-stu-id="36613-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="36613-129">Para comprobar el estado de la protección en tiempo real, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="36613-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="36613-130">Compruebe que la `real_time_protection_enabled` entrada es `true` .</span><span class="sxs-lookup"><span data-stu-id="36613-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="36613-131">De lo contrario, ejecute el siguiente comando para habilitarlo:</span><span class="sxs-lookup"><span data-stu-id="36613-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="36613-132">Para recopilar estadísticas actuales, ejecute:</span><span class="sxs-lookup"><span data-stu-id="36613-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="36613-133">El uso (tenga en cuenta el ```--output json``` guión doble) garantiza que el formato de salida esté listo para el análisis.</span><span class="sxs-lookup"><span data-stu-id="36613-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="36613-134">El resultado de este comando mostrará todos los procesos y su actividad de examen asociada.</span><span class="sxs-lookup"><span data-stu-id="36613-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="36613-135">En el sistema Linux, descargue el analizador python de **ejemplo high_cpu_parser.py** mediante el comando:</span><span class="sxs-lookup"><span data-stu-id="36613-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="36613-136">El resultado de este comando debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="36613-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="36613-137">A continuación, escriba los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="36613-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="36613-138">El resultado de lo anterior es una lista de los principales colaboradores de problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="36613-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="36613-139">La primera columna es el identificador de proceso (PID), la segunda columna es el nombre del proceso y la última columna es el número de archivos examinados, ordenados por impacto.</span><span class="sxs-lookup"><span data-stu-id="36613-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="36613-140">Por ejemplo, el resultado del comando será algo parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="36613-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
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

    <span data-ttu-id="36613-141">Para mejorar el rendimiento de Defender para Endpoint para Linux, busque el que tiene el número más alto debajo de la fila y `Total files scanned` agregue una exclusión para él.</span><span class="sxs-lookup"><span data-stu-id="36613-141">To improve the performance of Defender for Endpoint for Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="36613-142">Para obtener más información, vea [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span><span class="sxs-lookup"><span data-stu-id="36613-142">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="36613-143">La aplicación almacena estadísticas en la memoria y solo realiza un seguimiento de la actividad del archivo desde que se inició y se ha habilitado la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="36613-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="36613-144">Los procesos que se iniciaron antes o durante períodos en los que la protección en tiempo real estaba desactivada no se cuentan.</span><span class="sxs-lookup"><span data-stu-id="36613-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="36613-145">Además, solo se cuentan los eventos que desencadenaron exámenes.</span><span class="sxs-lookup"><span data-stu-id="36613-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="36613-146">Configure ATP de Microsoft Defender para Linux con exclusiones para los procesos o ubicaciones de disco que contribuyen a los problemas de rendimiento y vuelva a habilitar la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="36613-146">Configure Microsoft Defender ATP for Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="36613-147">Para obtener más información, vea [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span><span class="sxs-lookup"><span data-stu-id="36613-147">For more information, see [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span></span>
