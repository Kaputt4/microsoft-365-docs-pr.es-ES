---
title: Errores comunes para evitarlos cuando se definen exclusiones
description: Evite errores comunes al definir exclusiones para Antivirus de Microsoft Defender análisis.
keywords: exclusiones, archivos, extensión, tipo de archivo, nombre de carpeta, nombre de archivo, exámenes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/17/2021
ms.openlocfilehash: d10343538c995534878196cc57092c37fd2dcf7b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538068"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="980e2-104">Errores comunes para evitarlos cuando se definen exclusiones</span><span class="sxs-lookup"><span data-stu-id="980e2-104">Common mistakes to avoid when defining exclusions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="980e2-105">Puede definir una lista de exclusión para los elementos que no desea que Antivirus de Microsoft Defender examinar.</span><span class="sxs-lookup"><span data-stu-id="980e2-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="980e2-106">Estos elementos excluidos pueden contener amenazas que hacen que el dispositivo sea vulnerable.</span><span class="sxs-lookup"><span data-stu-id="980e2-106">Such excluded items could contain threats that make your device vulnerable.</span></span> 

<span data-ttu-id="980e2-107">En este artículo se describe un error común que debe evitar al definir exclusiones.</span><span class="sxs-lookup"><span data-stu-id="980e2-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="980e2-108">Antes de definir las listas de exclusión, vea [Recomendaciones para definir exclusiones](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span><span class="sxs-lookup"><span data-stu-id="980e2-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="980e2-109">Excluir determinados elementos de confianza</span><span class="sxs-lookup"><span data-stu-id="980e2-109">Excluding certain trusted items</span></span>

<span data-ttu-id="980e2-110">Algunos archivos, tipos de archivo, carpetas o procesos no deben excluirse del examen aunque confíes en que no sean malintencionados.</span><span class="sxs-lookup"><span data-stu-id="980e2-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="980e2-111">No defina exclusiones para las ubicaciones de carpetas, las extensiones de archivo y los procesos que se enumeran en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="980e2-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="980e2-112">Ubicaciones de carpetas</span><span class="sxs-lookup"><span data-stu-id="980e2-112">Folder locations</span></span>
- <span data-ttu-id="980e2-113">Extensiones de archivo</span><span class="sxs-lookup"><span data-stu-id="980e2-113">File extensions</span></span>
- <span data-ttu-id="980e2-114">Procesos</span><span class="sxs-lookup"><span data-stu-id="980e2-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="980e2-115">Ubicaciones de carpetas</span><span class="sxs-lookup"><span data-stu-id="980e2-115">Folder locations</span></span>

<span data-ttu-id="980e2-116">En general, no defina exclusiones para las siguientes ubicaciones de carpeta:</span><span class="sxs-lookup"><span data-stu-id="980e2-116">In general, do not define exclusions for the following folder locations:</span></span>

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

<span data-ttu-id="980e2-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`Tenga en cuenta la siguiente **excepción para SharePoint**: No excluir al usar la protección antivirus de nivel de archivo en `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="980e2-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="980e2-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`Tenga en cuenta la siguiente **excepción para SharePoint**: No excluir al usar la protección antivirus de nivel de archivo en `C:\Users\Default\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="980e2-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a><span data-ttu-id="980e2-119">Extensiones de archivo</span><span class="sxs-lookup"><span data-stu-id="980e2-119">File extensions</span></span>

<span data-ttu-id="980e2-120">En general, no defina exclusiones para las siguientes extensiones de archivo:</span><span class="sxs-lookup"><span data-stu-id="980e2-120">In general, do not define exclusions for the following file extensions:</span></span>

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a><span data-ttu-id="980e2-121">Procesos</span><span class="sxs-lookup"><span data-stu-id="980e2-121">Processes</span></span> 

<span data-ttu-id="980e2-122">En general, no defina exclusiones para los siguientes procesos:</span><span class="sxs-lookup"><span data-stu-id="980e2-122">In general, do not define exclusions for the following processes:</span></span>

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`  

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> <span data-ttu-id="980e2-123">Puede optar por excluir tipos de archivo, como , , o si su entorno tiene un software moderno y actualizado con una directiva de actualización estricta para controlar cualquier `.gif` `.jpg` `.jpeg` `.png` vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="980e2-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="980e2-124">Usar solo el nombre de archivo de la lista de exclusión</span><span class="sxs-lookup"><span data-stu-id="980e2-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="980e2-125">Un malware puede tener el mismo nombre que el del archivo en el que confía y desea excluir del examen.</span><span class="sxs-lookup"><span data-stu-id="980e2-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="980e2-126">Por lo tanto, para evitar excluir un posible malware del examen, use una ruta de acceso completa al archivo que desea excluir en lugar de usar solo el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="980e2-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="980e2-127">Por ejemplo, si desea excluir del examen, use la ruta `Filename.exe` de acceso completa al archivo, como `C:\program files\contoso\Filename.exe` .</span><span class="sxs-lookup"><span data-stu-id="980e2-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="980e2-128">Uso de una única lista de exclusión para varias cargas de trabajo de servidor</span><span class="sxs-lookup"><span data-stu-id="980e2-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="980e2-129">No use una sola lista de exclusión para definir exclusiones para varias cargas de trabajo de servidor.</span><span class="sxs-lookup"><span data-stu-id="980e2-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="980e2-130">Divida las exclusiones de diferentes cargas de trabajo de aplicación o servicio en varias listas de exclusión.</span><span class="sxs-lookup"><span data-stu-id="980e2-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="980e2-131">Por ejemplo, la lista de exclusión de la carga de trabajo de IIS Server debe ser diferente de la lista de exclusión de la SQL Server de trabajo.</span><span class="sxs-lookup"><span data-stu-id="980e2-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="980e2-132">Usar variables de entorno incorrectas como caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="980e2-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="980e2-133">Antivirus de Microsoft Defender El servicio se ejecuta en el contexto del sistema mediante la cuenta LocalSystem, lo que significa que obtiene información de la variable de entorno del sistema y no de la variable de entorno del usuario.</span><span class="sxs-lookup"><span data-stu-id="980e2-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="980e2-134">El uso de variables de entorno como comodín en listas de exclusión se limita a las variables del sistema y a las aplicables a los procesos que se ejecutan como una cuenta NT AUTHORITY\SYSTEM.</span><span class="sxs-lookup"><span data-stu-id="980e2-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="980e2-135">Por lo tanto, no use variables de entorno de usuario como caracteres comodín al agregar Antivirus de Microsoft Defender y exclusiones de procesos.</span><span class="sxs-lookup"><span data-stu-id="980e2-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="980e2-136">Consulte la tabla de [variables de entorno del sistema](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) para obtener una lista completa de variables de entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="980e2-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="980e2-137">Vea [Usar caracteres comodín en las listas](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) de exclusión de extensión o nombre de archivo para obtener información sobre cómo usar caracteres comodín en listas de exclusión.</span><span class="sxs-lookup"><span data-stu-id="980e2-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

## <a name="related-articles"></a><span data-ttu-id="980e2-138">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="980e2-138">Related articles</span></span>

- [<span data-ttu-id="980e2-139">Configurar y validar exclusiones en Antivirus de Microsoft Defender exámenes</span><span class="sxs-lookup"><span data-stu-id="980e2-139">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="980e2-140">Configurar y validar exclusiones en función de la extensión de archivo y la ubicación de la carpeta</span><span class="sxs-lookup"><span data-stu-id="980e2-140">Configure and validate exclusions based on file extension and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="980e2-141">Configurar y validar exclusiones para archivos abiertos por procesos</span><span class="sxs-lookup"><span data-stu-id="980e2-141">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="980e2-142">Configurar Antivirus de Microsoft Defender exclusiones en Windows Server</span><span class="sxs-lookup"><span data-stu-id="980e2-142">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
