---
title: Registros de diagnóstico
description: Registros que pueden recopilarse de dispositivos durante la solución de problemas y cómo se almacenan
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272900"
---
# <a name="diagnostic-logs"></a>Registros de diagnóstico

Cuando solucionemos un problema en un dispositivo administrado por Escritorio administrado de Microsoft, ya sea uno que haya notificado o uno identificado por nuestro servicio, es posible que tendrán que recopilar ciertos registros de diagnóstico del dispositivo sin intervención del usuario. No recopilamos ningún contenido o información generado por el usuario de directorios de usuario. Solo recopilamos datos de diagnóstico y registro que tienen que ver con el estado y el estado del dispositivo.

Almacenamos los registros recopilados durante 28 días y, a continuación, los eliminamos. Procesamos los registros recopilados desde un dispositivo siguiendo nuestros [estándares de tratamiento de datos.](privacy-personal-data.md)

## <a name="data-collected"></a>Datos recopilados

Esta lista incluye todas las carpetas, registros de eventos, ejecutables o ubicaciones del Registro de las que Escritorio administrado de Microsoft recopilar registros de diagnóstico. Los datos reales recopilados serán un subconjunto de esta lista y dependen del problema identificado.

### <a name="registry-keys"></a>Claves del Registro

- HKLM \\ SYSTEM \\ CurrentControlSet \\ Services
- HKLM \\ SOFTWARE \\ Microsoft \\ Surface
- Directivas de \\ SOFTWARE \\ HKLM \\ Microsoft Windows \\ \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages
- Directivas de software HKLM \\ \\ Microsoft \\ \\ WindowsStore
- HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion \\ Superfetch
- Instalación de \\ HKLM SYSTEM \\
- HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ SOFTWARE Microsoft Windows protección contra amenazas \\ \\ avanzada
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ Autenticación de CurrentVersion \\ \\ LogonUI
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Internet \\ Configuración
- HKLM \\ Software Microsoft Windows \\ \\ \\ Desinstalación de CurrentVersion \\
- Directivas de software hklm \\ \\
- DIRECTIVAS DE SOFTWARE HKLM \\ \\ Microsoft \\ \\ Cryptography Configuration \\ \\ SSL
- Directivas de \\ SOFTWARE \\ HKLM \\ Microsoft Windows Protección contra \\ amenazas avanzada
- HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ Desinstalación de CurrentVersion \\
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>Comandos

- %programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles
- %windir% \\ system32 \\certutil.exe -store
- %windir% \\ system32 \\certutil.exe -store -user my
- %windir% \\ system32 \\Dsregcmd.exe /status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32 \\netsh.exe advfirewall mostrar allprofiles
- %windir% \\ system32 \\netsh.exe advfirewall mostrar global
- %windir% \\ system32 \\netsh.exe perfiles de presentación de lan
- %windir% \\ system32 \\netsh.exe winhttp show proxy
- %windir% \\ system32 \\netsh.exe wlan mostrar perfiles
- %windir% \\ system32 \\netsh.exe wlan show wlanreport
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShell comandos:
    - Get-appxpackage -allusers
    - Paquete Get-appxpackage -packagetype
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32 \_ product
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>Registros de eventos

- Aplicación
- Microsoft-Windows-AppLocker/EXE y DLL
- Microsoft-Windows-AppLocker/MSI y Script
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/Packaged app-Execution
- Administración de Microsoft-Windows-Bitlocker/Bitlocker
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- Instalación
- Sistema

### <a name="files"></a>Archivos

- %ProgramData% \\ \\ Recopiladores de Microsoft DiagnosticLogCSP \\ \\ \* .etl
- %ProgramData% \\ Registros de Microsoft \\ IntuneManagementExtension \\ \\ \* .\*
- %ProgramData% \\ Microsoft Windows Defender Support \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ logs \* .log
- %windir% \\ ccmsetup \\ logs \* .log
- %windir% \\ logs \\ CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- %windir% \\ servicing \\ sessions \\ActionList.xml
- %windir% \\ servicing \\ sessions \\Sessions.xml
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb
- %windir% \\ logs \\ dism \\ dism.log
- %SystemRoot% \\ Registros \\ de Winevt system32 \\\\
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* .\*