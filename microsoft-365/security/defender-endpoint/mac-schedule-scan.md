---
title: Cómo programar exámenes con Microsoft Defender para endpoint en macOS
description: Obtenga información sobre cómo programar un tiempo de examen automático para Microsoft Defender para Endpoint en macOS para proteger mejor los activos de su organización.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, exámenes, antivirus
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
ms.openlocfilehash: 2c1dc16dc3fbb61a77e1d7348d47fdfd778c56e2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934518"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="5d0e1-104">Programar exámenes con Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="5d0e1-104">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d0e1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5d0e1-105">**Applies to:**</span></span>
- [<span data-ttu-id="5d0e1-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5d0e1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5d0e1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d0e1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5d0e1-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="5d0e1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5d0e1-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5d0e1-110">Aunque puede iniciar un examen de amenazas en cualquier momento con Microsoft Defender para endpoint, su empresa puede beneficiarse de exámenes programados o programados.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="5d0e1-111">Por ejemplo, puede programar un examen para que se ejecute al principio de cada día laborable o semana.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="5d0e1-112">Programar un examen con *inicio*</span><span class="sxs-lookup"><span data-stu-id="5d0e1-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="5d0e1-113">Puedes crear una programación de análisis mediante el demonio que *se* inicia en un dispositivo macOS.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="5d0e1-114">El código siguiente muestra el esquema que debe usar para programar un examen.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="5d0e1-115">Abra un editor de texto y use este ejemplo como guía para su propio archivo de examen programado.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="5d0e1-116">Para obtener más información sobre el formato *de archivo .plist* que se usa aquí, consulta Acerca [de los archivos](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) de lista de propiedades de información en el sitio web oficial para desarrolladores de Apple.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="5d0e1-117">Guarde el archivo *como com.microsoft.wdav.schedquickscan.plist*.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="5d0e1-118">Para ejecutar un examen completo en lugar de un examen rápido, cambie la línea 12, , para usar la opción en lugar de (es decir, ) y guarde el archivo como `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* en lugar de *com.microsoft.wdav.sched **quick** scan.plist*.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="5d0e1-119">Abra **terminal**.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="5d0e1-120">Escriba los siguientes comandos para cargar el archivo:</span><span class="sxs-lookup"><span data-stu-id="5d0e1-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="5d0e1-121">El examen programado se ejecutará en la fecha, hora y frecuencia definidas en la lista p.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="5d0e1-122">En el ejemplo, el examen se ejecuta a las 2:00 a.m. todos los viernes.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="5d0e1-123">El `Weekday` valor de usa un entero para indicar el quinto día de la `StartCalendarInterval` semana, o viernes.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="5d0e1-124">Los agentes ejecutados *con el inicio* no se ejecutarán en la hora programada mientras el dispositivo está dormido.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="5d0e1-125">En su lugar, se ejecutarán una vez que el dispositivo reanude el modo de suspensión.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="5d0e1-126">Si el dispositivo está desactivado, el examen se ejecutará en la próxima hora programada del examen.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="5d0e1-127">Programar un examen con Intune</span><span class="sxs-lookup"><span data-stu-id="5d0e1-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="5d0e1-128">También puede programar exámenes con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="5d0e1-129">El [script runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell disponible en Scripts para Microsoft Defender para [Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) persistirá cuando el dispositivo reanude el modo de suspensión.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="5d0e1-130">Consulta [Usar scripts de shell en dispositivos macOS en Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) para obtener instrucciones más detalladas sobre cómo usar este script en tu empresa.</span><span class="sxs-lookup"><span data-stu-id="5d0e1-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
