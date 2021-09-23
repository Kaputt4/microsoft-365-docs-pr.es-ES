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
ms.date: 09/22/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 85c3aee098786d75a7a2f17d1c9c4d11c0c87aeb
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490912"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Errores comunes para evitarlos cuando se definen exclusiones

Puede definir una lista de exclusión para los elementos que no desea que Antivirus de Microsoft Defender examinar. Estos elementos excluidos pueden contener amenazas que hacen que el dispositivo sea vulnerable. En este artículo se describe un error común que debe evitar al definir exclusiones.

Antes de definir las listas de exclusión, vea [Recomendaciones para definir exclusiones](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Excluir determinados elementos de confianza

Algunos archivos, tipos de archivo, carpetas o procesos no deben excluirse del examen aunque confíes en que no sean malintencionados.

No defina exclusiones para las ubicaciones de carpetas, las extensiones de archivo y los procesos que se enumeran en las secciones siguientes:
- Ubicaciones de carpetas
- Extensiones de archivo
- Procesos

### <a name="folder-locations"></a>Ubicaciones de carpetas

En general, no defina exclusiones para las siguientes ubicaciones de carpeta:

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

`C:\Users\<UserProfileName>\AppData\Local\Temp\`Tenga en cuenta la siguiente **excepción para SharePoint**: No excluir al usar la protección antivirus de nivel de archivo en `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`Tenga en cuenta la siguiente **excepción para SharePoint**: No excluir al usar la protección antivirus de nivel de archivo en `C:\Users\Default\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

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

#### <a name="linux-and-macos-platforms"></a>Plataformas linux y macOS

`/`

`/bin`

`/sbin`

`/usr/lib`


### <a name="file-extensions"></a>Extensiones de archivo

En general, no defina exclusiones para las siguientes extensiones de archivo:

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

### <a name="processes"></a>Procesos

En general, no defina exclusiones para los siguientes procesos:

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

`dotnet.exe`

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

#### <a name="linux-and-macos-platforms"></a>Plataformas linux y macOS

`bash`

`sh`

`python` y `python3`

`java`

`zsh`

> [!NOTE]
> Puede optar por excluir tipos de archivo, como , , o si su entorno tiene un software moderno y actualizado con una directiva de actualización estricta para controlar cualquier `.gif` `.jpg` `.jpeg` `.png` vulnerabilidad.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Usar solo el nombre de archivo de la lista de exclusión

Es posible que el malware tenga el mismo nombre que el de un archivo en el que confía y que desea excluir del examen. Por lo tanto, para evitar excluir posibles malware del examen, use una ruta de acceso completa al archivo que desea excluir en lugar de usar solo el nombre del archivo. Por ejemplo, si desea excluir del examen, use la ruta `Filename.exe` de acceso completa al archivo, como `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Uso de una única lista de exclusión para varias cargas de trabajo de servidor

No use una sola lista de exclusión para definir exclusiones para varias cargas de trabajo de servidor. Divida las exclusiones de diferentes cargas de trabajo de aplicación o servicio en varias listas de exclusión. Por ejemplo, la lista de exclusión de la carga de trabajo de IIS Server debe ser diferente de la lista de exclusión de la SQL Server de trabajo.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Usar variables de entorno incorrectas como caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y nombre de archivo

Antivirus de Microsoft Defender El servicio se ejecuta en el contexto del sistema mediante la cuenta LocalSystem, lo que significa que obtiene información de la variable de entorno del sistema y no de la variable de entorno del usuario. El uso de variables de entorno como comodín en listas de exclusión se limita a las variables del sistema y a las aplicables a los procesos que se ejecutan como una cuenta NT AUTHORITY\SYSTEM. Por lo tanto, no use variables de entorno de usuario como caracteres comodín al agregar Antivirus de Microsoft Defender y exclusiones de procesos. Consulte la tabla de [variables de entorno del sistema](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) para obtener una lista completa de variables de entorno del sistema.

Vea [Usar caracteres comodín en las listas](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) de exclusión de extensión o nombre de archivo para obtener información sobre cómo usar caracteres comodín en listas de exclusión.
