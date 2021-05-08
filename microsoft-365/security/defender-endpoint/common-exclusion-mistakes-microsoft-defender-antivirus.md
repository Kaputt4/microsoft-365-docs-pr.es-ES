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
ms.openlocfilehash: de739ca3c6a4ab305b575fa7e2f419d044d997a8
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274976"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Errores comunes para evitarlos cuando se definen exclusiones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Puede definir una lista de exclusión para los elementos que no desea que Antivirus de Microsoft Defender examinar. Estos elementos excluidos pueden contener amenazas que hacen que el dispositivo sea vulnerable. 

En este artículo se describe un error común que debe evitar al definir exclusiones. 

Antes de definir las listas de exclusión, vea [Recomendaciones para definir exclusiones](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Excluir determinados elementos de confianza

Algunos archivos, tipos de archivo, carpetas o procesos no deben excluirse del examen aunque confíes en que no sean malintencionados. 

No defina exclusiones para las ubicaciones de carpetas, las extensiones de archivo y los procesos que se enumeran en la tabla siguiente:

| Ubicaciones de carpetas | Extensiones de archivo | Procesos |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> Puede optar por excluir tipos de archivo, como , , o si su entorno tiene un software moderno y actualizado con una directiva de actualización estricta para controlar cualquier `.gif` `.jpg` `.jpeg` `.png` vulnerabilidad.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Usar solo el nombre de archivo de la lista de exclusión

Un malware puede tener el mismo nombre que el del archivo en el que confía y desea excluir del examen. Por lo tanto, para evitar excluir un posible malware del examen, use una ruta de acceso completa al archivo que desea excluir en lugar de usar solo el nombre del archivo. Por ejemplo, si desea excluir del examen, use la ruta `Filename.exe` de acceso completa al archivo, como `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Uso de una única lista de exclusión para varias cargas de trabajo de servidor

No use una sola lista de exclusión para definir exclusiones para varias cargas de trabajo de servidor. Divida las exclusiones de diferentes cargas de trabajo de aplicación o servicio en varias listas de exclusión. Por ejemplo, la lista de exclusión de la carga de trabajo de IIS Server debe ser diferente de la lista de exclusión de la SQL Server de trabajo.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Usar variables de entorno incorrectas como caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y nombre de archivo

Antivirus de Microsoft Defender El servicio se ejecuta en el contexto del sistema mediante la cuenta LocalSystem, lo que significa que obtiene información de la variable de entorno del sistema y no de la variable de entorno del usuario. El uso de variables de entorno como comodín en listas de exclusión se limita a las variables del sistema y a las aplicables a los procesos que se ejecutan como una cuenta NT AUTHORITY\SYSTEM. Por lo tanto, no use variables de entorno de usuario como caracteres comodín al agregar Antivirus de Microsoft Defender y exclusiones de procesos. Consulte la tabla de [variables de entorno del sistema](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) para obtener una lista completa de variables de entorno del sistema.

Vea [Usar caracteres comodín en las listas](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) de exclusión de extensión o nombre de archivo para obtener información sobre cómo usar caracteres comodín en listas de exclusión.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar y validar exclusiones en Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones en función de la extensión de archivo y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones para archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar Antivirus de Microsoft Defender exclusiones en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
