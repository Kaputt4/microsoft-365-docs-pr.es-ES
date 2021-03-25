---
title: Ejemplos de comandos de respuesta en directo
description: Aprenda a ejecutar comandos de respuesta en directo básicos o avanzados para Microsoft Defender para endpoint y vea ejemplos sobre cómo se usa.
keywords: ejemplo, command, cli, remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file
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
ms.openlocfilehash: 0e00464b5d5dcf348fcc76a3f093ac8bac373627
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187714"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="fc5fa-104">Ejemplos de comandos de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="fc5fa-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc5fa-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="fc5fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc5fa-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="fc5fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc5fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc5fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fc5fa-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="fc5fa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc5fa-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="fc5fa-110">Obtenga información sobre los comandos comunes usados en la respuesta en directo y vea ejemplos sobre cómo se usan normalmente.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="fc5fa-111">Según el rol que se le haya concedido, puede ejecutar comandos de respuesta en directo básicos o avanzados.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="fc5fa-112">Para obtener más información sobre los comandos básicos y avanzados, vea Investigar entidades en [dispositivos con respuesta en directo.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="fc5fa-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="fc5fa-113">analizar</span><span class="sxs-lookup"><span data-stu-id="fc5fa-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="fc5fa-114">conexiones</span><span class="sxs-lookup"><span data-stu-id="fc5fa-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="fc5fa-115">dir</span><span class="sxs-lookup"><span data-stu-id="fc5fa-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="fc5fa-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="fc5fa-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="fc5fa-117">findfile</span><span class="sxs-lookup"><span data-stu-id="fc5fa-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="fc5fa-118">getfile</span><span class="sxs-lookup"><span data-stu-id="fc5fa-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="fc5fa-119">Los siguientes tipos de **archivo no se** pueden descargar con este comando desde Live Response:</span><span class="sxs-lookup"><span data-stu-id="fc5fa-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="fc5fa-120">Archivos de punto de repetición</span><span class="sxs-lookup"><span data-stu-id="fc5fa-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="fc5fa-121">Archivos dispersos</span><span class="sxs-lookup"><span data-stu-id="fc5fa-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="fc5fa-122">Archivos vacíos</span><span class="sxs-lookup"><span data-stu-id="fc5fa-122">Empty files</span></span>
> * <span data-ttu-id="fc5fa-123">Archivos virtuales o archivos que no están totalmente presentes localmente</span><span class="sxs-lookup"><span data-stu-id="fc5fa-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="fc5fa-124">PowerShell **admite** estos tipos [de archivo.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="fc5fa-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="fc5fa-125">Use PowerShell como alternativa, si tiene problemas al usar este comando desde Live Response.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="fc5fa-126">procesos</span><span class="sxs-lookup"><span data-stu-id="fc5fa-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="fc5fa-127">putfile</span><span class="sxs-lookup"><span data-stu-id="fc5fa-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="fc5fa-128">registro</span><span class="sxs-lookup"><span data-stu-id="fc5fa-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="fc5fa-129">remediate</span><span class="sxs-lookup"><span data-stu-id="fc5fa-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="fc5fa-130">ejecutar</span><span class="sxs-lookup"><span data-stu-id="fc5fa-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

## <a name="scheduledtask"></a><span data-ttu-id="fc5fa-131">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="fc5fa-131">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="fc5fa-132">deshacer</span><span class="sxs-lookup"><span data-stu-id="fc5fa-132">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

