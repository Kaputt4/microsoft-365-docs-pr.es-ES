---
title: Errores comunes para evitarlos cuando se definen exclusiones
description: Evite errores comunes al definir exclusiones para exámenes de Antivirus de Microsoft Defender.
keywords: exclusiones, archivos, extensión, tipo de archivo, nombre de carpeta, nombre de archivo, exámenes
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 10/19/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: b5dc8832839c86fee98e9f27264b70e6a63f380c
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790710"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Errores comunes para evitarlos cuando se definen exclusiones

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender 

**Plataformas**
- Windows
- macOS
- Linux

Puede definir una lista de exclusión para los elementos que no desea que Antivirus de Microsoft Defender examinen. Estos elementos excluidos podrían contener amenazas que hacen que el dispositivo sea vulnerable. En este artículo se describe algún error común que debe evitar al definir exclusiones.

Antes de definir las listas de exclusión, consulte [Recomendaciones para definir exclusiones](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Exclusión de determinados elementos de confianza

Determinados archivos, tipos de archivos, carpetas o procesos no deben excluirse del examen aunque confíe en que no sean malintencionados.

No defina exclusiones para las ubicaciones de carpetas, las extensiones de archivo y los procesos que aparecen en las secciones siguientes:
- Ubicaciones de carpeta
- Extensiones de archivo
- Procesos

### <a name="folder-locations"></a>Ubicaciones de carpeta

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

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Tenga en cuenta la siguiente excepción para SharePoint**: Excluir `C:\Users\ServiceAccount\AppData\Local\Temp` al usar [la protección antivirus de nivel de archivo en SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Tenga en cuenta la siguiente excepción para SharePoint**: Excluir `C:\Users\Default\AppData\Local\Temp` al usar [la protección antivirus de nivel de archivo en SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

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

#### <a name="linux-and-macos-platforms"></a>Plataformas Linux y macOS

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

En general, no defina exclusiones para los procesos siguientes:

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

#### <a name="linux-and-macos-platforms"></a>Plataformas Linux y macOS

`bash`

`sh`

`python` y `python3`

`java`

`zsh`

> [!NOTE]
> Puede optar por excluir tipos de archivo, como `.gif`, `.jpg`, `.jpeg`o `.png` si el entorno tiene un software moderno y actualizado con una directiva de actualización estricta para controlar las vulnerabilidades.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Usar solo el nombre de archivo en la lista de exclusión

Es posible que el malware tenga el mismo nombre que el de un archivo en el que confía y que desea excluir del examen. Por lo tanto, para evitar excluir el posible malware del examen, use una ruta de acceso completa al archivo que desea excluir en lugar de usar solo el nombre de archivo. Por ejemplo, si desea excluir `Filename.exe` del examen, use la ruta de acceso completa al archivo, como `C:\program files\contoso\Filename.exe`.

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Uso de una lista de exclusión única para varias cargas de trabajo de servidor

No use una sola lista de exclusión para definir exclusiones para varias cargas de trabajo de servidor. Divida las exclusiones de diferentes cargas de trabajo de aplicación o servicio en varias listas de exclusión. Por ejemplo, la lista de exclusión de la carga de trabajo del servidor IIS debe ser diferente de la lista de exclusión de la carga de trabajo de SQL Server.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Uso de variables de entorno incorrectas como caracteres comodín en el nombre de archivo y la ruta de acceso de carpeta o las listas de exclusión de extensiones

Antivirus de Microsoft Defender servicio se ejecuta en el contexto del sistema mediante la cuenta LocalSystem, lo que significa que obtiene información de la variable de entorno del sistema y no de la variable de entorno de usuario. El uso de variables de entorno como carácter comodín en las listas de exclusión se limita a las variables del sistema y las aplicables a los procesos que se ejecutan como una cuenta NT AUTHORITY\SYSTEM. Por lo tanto, no use variables de entorno de usuario como caracteres comodín al agregar Antivirus de Microsoft Defender exclusiones de carpetas y procesos. Consulte la tabla en [Variables de entorno del sistema](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) para obtener una lista completa de las variables de entorno del sistema.

Consulte [Uso de caracteres comodín en las listas de exclusión de extensiones o ruta de acceso de carpeta y nombre de archivo](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) para obtener información sobre cómo usar caracteres comodín en las listas de exclusión.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
