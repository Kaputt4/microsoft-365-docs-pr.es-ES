---
title: Registro de diagnóstico
description: Registros que pueden recopilarse de dispositivos durante la solución de problemas y cómo se almacenan
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 808ce2e426a0540c95195f26c9872f569e595715
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825426"
---
# <a name="diagnostic-logs"></a>Registro de diagnóstico

Tanto si ha notificado un problema como si nuestro servicio ha identificado un problema, es posible que deba recopilar determinados registros de diagnóstico del dispositivo sin intervención del usuario.

No recopilamos ningún contenido o información generado por el usuario de directorios de usuario. Solo recopilamos datos de diagnóstico y registro que tienen que ver con el estado y el estado del dispositivo.

Almacenamos los registros recopilados durante 28 días y, a continuación, los eliminamos. Procesamos los registros recopilados desde un dispositivo siguiendo nuestros [estándares de tratamiento de datos](privacy-personal-data.md).

## <a name="data-collected"></a>Datos recopilados

Esta lista siguiente incluye todas las carpetas, registros de eventos, ejecutables o ubicaciones del Registro de las que Microsoft Managed Desktop puede recopilar registros de diagnóstico. Los datos reales recopilados serán un subconjunto de esta lista y dependen del problema identificado.

### <a name="registry-keys"></a>Claves del Registro

- HKLMSYSTEMCurrentControlSetServices\\\\\\
- HKLMSOFTWAREMicrosoftSurface\\\\\\
- HKLMSOFTWAREPoliciesMicrosoft\\\\\\\\ Windows\\ WindowsUpdate
- HKLMSYSTEMCurrentControlSetControlMUIUILanguages\\\\\\\\\\
- HKLMSoftwarePoliciesMicrosoftWindowsStore\\\\\\\\
- HKLMSoftwareMicrosoft\\\\\\ Windows\\ CurrentVersionWindowsStoreWindowsUpdate\\\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows NTCurrentVersion\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows NTCurrentVersion\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows\\ CurrentVersionAppModel\\
- HKLMSYSTEMCurrentControlSetControlFirmwareResources\\\\\\\\
- HKLMSOFTWAREMicrosoftWindowsSelfhost\\\\\\
- HKLMSOFTWAREMicrosoftWindowsUpdate\\\\\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows\\ CurrentVersionAppx\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows NTCurrentVersionSuperfetch\\\\
- HKLMSYSTEMSetup\\\\
- HKLMSoftwareMicrosoftIntuneManagementExtension\\\\\\
- HKLMSOFTWAREMicrosoftSystemCertificatesAuthRoot\\\\\\\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows Protección contra amenazas avanzada
- HKLMSOFTWAREMicrosoft\\\\\\ Windows\\ CurrentVersionAuthenticationLogonUI\\\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows\\ CurrentVersionInternet\\ Configuración
- HKLMSoftwareMicrosoft\\\\\\ Windows\\ CurrentVersionUninstall\\
- HKLMSoftwarePolicies\\\\
- HKLMSOFTWAREPoliciesMicrosoftCryptographyConfigurationSSL\\\\\\\\\\\\
- HKLMSOFTWAREPoliciesMicrosoft\\\\\\\\ Windows Protección contra amenazas avanzada
- HKLMSOFTWAREWOW6432NodeMicrosoft\\\\\\\\ Windows\\ CurrentVersionUninstall\\
- HKLMSYSTEMCurrentControlSetControlSecurityProvidersSCHANNEL\\\\\\\\\\

### <a name="commands"></a>Comandos

- %programfiles%\\windows defender\\mpcmdrun.exe -GetFiles
- %windir%\\system32\\certutil.exe -store
- %windir%\\system32\\certutil.exe -store -user my
- %windir%\\system32\\Dsregcmd.exe /status
- %windir%\\system32\\ipconfig.exe /all
- %windir%\\system32\\ipconfig.exe /displaydns
- %windir%\\system32\\mdmdiagnosticstool.exe
- %windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnosticsmsinfo32.log\\
- %windir%\\system32\\netsh.exe advfirewall mostrar allprofiles
- %windir%\\system32\\netsh.exe advfirewall mostrar global
- %windir%\\system32\\netsh.exe perfiles de presentación de lan
- %windir%\\system32\\netsh.exe winhttp show proxy
- %windir%\\system32\\netsh.exe perfiles de presentación wlan
- %windir%\\system32\\netsh.exe wlan show wlanreport
- %windir%\\system32\\ping.exe -n 50 localhost
- %windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html
- %windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShell comandos:
    - Get-appxpackage -allusers
    - Paquete Get-appxpackage -packagetype
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32product\_
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32PnPSignedDriver\_

### <a name="event-logs"></a>Registros de eventos

- Aplicación
- Microsoft-Windows-AppLocker/EXE y DLL
- Microsoft-Windows-AppLocker/MSI y script
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/Packaged app-Execution
- Administración de Microsoft-Windows-Bitlocker/BitLocker
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- Instalación
- Sistema

### <a name="files"></a>Archivos

- %ProgramData%\\MicrosoftDiagnosticLogCSPCollectors.etl\\\\\\\*
- %ProgramData%\\MicrosoftIntuneManagementExtensionLogs\\\\\\\*.\*
- %ProgramData%\\Microsoft\\ Windows Defender\\ Support\\MpSupportFiles.cab
- %ProgramData%\\Microsoft\\ Windows\\ WlanReport\\wlan-report-latest.html
- %ProgramData%\\Microsoft\\ Windows\\ WlanReport -SourceFileName wlan-report-latest.html
- %windir%\\ccmlogs.log\\\*
- %windir%\\ccmsetuplogs.log\\\*
- %windir%\\logsCBScbs.log\\\\
- %windir%\\logsmeasuredboot\*\\.\*
- %windir%\\LogsWindowsUpdate.etl\\\*
- %windir%\\inf.log\\\*
- %windir%\\servicingsessions\\\\ActionList.xml
- %windir%\\servicingsessions\\\\Sessions.xml
- %windir%\\SoftwareDistributionDataStoreLogsedb.log\\\\\\
- %windir%\\SoftwareDistributionDataStoreDataStore.edb\\\\
- %windir%\\logsdismdism.log\\\\
- %SystemRoot%\\System32WinevtLogs\\\\\\
- %appdata%\\Microsoft\\ Teams\\ media-stack.blog\\\*
- %appdata%\\Microsoft\\ Teams\\ skylib.blog\\\*
- %appdata%\\Microsoft\\ Teams\\ media-stack.etl\\\*
- %appdata%\\Microsoft\\ Teams\\logs.txt
- %windir%\\Windows System32winevt\\\\\*.\\\*