---
title: Migración de un HIPS de terceros a reglas de ASR
description: Describe cómo abordar una migración desde una solución de sistema de prevención de intrusiones de host (HIPS) de terceros a reglas de ASR.
keywords: Reglas de reducción de superficie expuesta a ataques, asr, reglas de asr, caderas, sistema de prevención de intrusiones del host, reglas de protección, anti-vulnerabilidad, antiexploit, vulnerabilidad de seguridad, prevención de infecciones, Microsoft Defender para punto de conexión
ms.topic: article
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: dansimp
manager: dansimp
ms.custom: asr
ms.subservice: mde
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: aa00aa4652edb3fa253573c451292c199617410e
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67688449"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Migración de un HIPS de terceros a reglas de ASR

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Este artículo le ayuda a asignar reglas comunes a Microsoft Defender para punto de conexión.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Escenarios al migrar desde un producto HIPS de terceros a reglas de ASR

### <a name="block-creation-of-specific-files"></a>Bloquear la creación de archivos específicos

- **Se aplica a** todos los procesos
- **Operación**: creación de archivos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios**- *.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab
- **Reglas de reducción de superficie** expuesta a ataques: las reglas de ASR bloquean las técnicas de ataque y no los indicadores de compromiso (IOC). Bloquear una extensión de archivo específica no siempre es útil, ya que no impide que un dispositivo se ponga en peligro. Solo frustra parcialmente un ataque hasta que los atacantes crean un nuevo tipo de extensión para la carga.
- **Otras características recomendadas**: se recomienda encarecidamente tener habilitado el Antivirus de Microsoft Defender, junto con Cloud Protection y análisis de comportamiento. Se recomienda usar otra prevención, como la regla ASR "Usar protección avanzada contra ransomware". Esto proporciona un mayor nivel de protección contra ataques de ransomware. Además, muchas de estas claves del Registro se supervisan mediante Microsoft Defender para punto de conexión, como técnicas ASEP, que desencadenarán alertas específicas. Las claves del Registro usadas requieren un mínimo de privilegios de Administración local o instalador de confianza. Se recomienda usar un entorno bloqueado, con derechos o cuentas administrativas mínimos. Se pueden habilitar otras configuraciones del sistema, como "Deshabilitar SeDebug para roles no necesarios" que forman parte de nuestras recomendaciones de seguridad más amplias.

### <a name="block-creation-of-specific-registry-keys"></a>Bloquear la creación de claves específicas del Registro

- **Se aplica a** todos los procesos
- **Procesos**: N/A
- **Operación**: modificaciones del Registro
- **Ejemplos de archivos o carpetas, claves o valores del Registro, procesos, servicios**-  *\Software,HKCU*\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **Reglas de reducción de superficie** expuesta a ataques: las reglas de ASR bloquean las técnicas de ataque y no los indicadores de compromiso (IOC). Bloquear una extensión de archivo específica no siempre es útil, ya que no impide que un dispositivo se ponga en peligro. Solo frustra parcialmente un ataque hasta que los atacantes crean un nuevo tipo de extensión para la carga.
- **Otras características recomendadas**: se recomienda encarecidamente tener habilitado el Antivirus de Microsoft Defender, junto con Cloud Protection y análisis de comportamiento. Se recomienda usar la prevención adicional, como la regla ASR "Usar la protección avanzada contra ransomware". Esto proporciona un mayor nivel de protección contra ataques de ransomware. Además, varias de estas claves del Registro se supervisan mediante Microsoft Defender para punto de conexión, como técnicas ASEP, que desencadenarán alertas específicas. Además, las claves del Registro usadas requieren un mínimo de privilegios de Administración local o instalador de confianza. Se recomienda usar un entorno bloqueado, con derechos o cuentas administrativas mínimos. Se pueden habilitar otras configuraciones del sistema, como "Deshabilitar SeDebug para roles no necesarios" que forman parte de nuestras recomendaciones de seguridad más amplias.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Impedir que los programas que no son de confianza se ejecuten desde unidades extraíbles

- **Se aplica a** programas que no son de confianza desde USB
- **Procesos**- *
- **Operación**: ejecución de procesos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios:-*
- **Reglas de reducción de superficie expuesta a ataques**: las reglas asr tienen una regla integrada para evitar el inicio de programas que no son de confianza y no firmados desde unidades extraíbles: "Bloquear procesos que no son de confianza y no firmados que se ejecutan desde USB", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Otras características recomendadas**: explore controles adicionales para dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión:[Cómo controlar dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión](/windows/security/threat-protection/device-control/control-usb-devices-using-intune).

### <a name="block-mshta-from-launching-certain-child-processes"></a>Impedir que Mshta inicie determinados procesos secundarios

- **Se aplica a**- Mshta
- **Procesos**: mshta.exe
- **Operación**: ejecución de procesos
- **Ejemplos de archivos o carpetas, claves o valores del Registro, procesos, servicios** powershell.exe, cmd.exe, regsvr32.exe
- **Reglas de reducción de superficie expuesta a ataques**: las reglas de ASR no contienen ninguna regla específica para evitar que los procesos secundarios "mshta.exe". Este control está dentro de la competencia de Protección contra vulnerabilidades de seguridad o Windows Defender Control de aplicaciones.
- **Otras características recomendadas**: habilite Windows Defender Control de aplicaciones para evitar que mshta.exe se ejecuten por completo. Si su organización requiere "mshta.exe" para las aplicaciones de línea de negocio, configure una regla específica Windows Defender Protección contra vulnerabilidades de seguridad para evitar que mshta.exe inicie procesos secundarios.

### <a name="block-outlook-from-launching-child-processes"></a>Impedir que Outlook inicie procesos secundarios

- **Se aplica a**: Outlook
- **Procesos**: outlook.exe
- **Operación**: ejecución de procesos
- **Ejemplos de archivos o carpetas, claves o valores del Registro, procesos, servicios** powershell.exe
- **Reglas de reducción de superficie de ataque**: las reglas ASR tienen una regla integrada para evitar que las aplicaciones de comunicación de Office (Outlook, Skype y Teams) inicien procesos secundarios: "Bloquear la aplicación de comunicación de Office para crear procesos secundarios", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Otras características recomendadas**: se recomienda habilitar el modo de lenguaje restringido de PowerShell para minimizar la superficie expuesta a ataques desde PowerShell.

### <a name="block-office-apps-from-launching-child-processes"></a>Impedir que las aplicaciones de Office inicien procesos secundarios

- **Se aplica a**- Office
- **Procesos**: winword.exe, powerpnt.exe, excel.exe
- **Operación**: ejecución de procesos
- **Ejemplos de archivos o carpetas, claves o valores del Registro, procesos, servicios** powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- **Reglas de reducción de superficie expuesta a ataques**: las reglas ASR tienen una regla integrada para evitar que las aplicaciones de Office inicien procesos secundarios: "Bloquear que todas las aplicaciones de Office creen procesos secundarios", GUID "d4f940ab-401b-4efc-aadc-ad5f3c50688a".
- **Otras características recomendadas**: N/A

### <a name="block-office-apps-from-creating-executable-content"></a>Impedir que las aplicaciones de Office creen contenido ejecutable

- **Se aplica a**- Office
- **Procesos**: winword.exe, powerpnt.exe, excel.exe
- **Operación**: creación de archivos
- **Ejemplos de archivos o carpetas, Claves o valores del Registro, procesos, servicios**: C:\Users *\AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\**Temp.com, C:\Users*\Downloads**.exe, C:\Users *\AppData.scf **, C:\ProgramData.scf**, C:\Users\Public*.exe, C:\Users*\Desktop***.exe
- **Reglas de reducción de superficie expuesta a ataques**- N/A.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Impedir que Wscript lea determinados tipos de archivos

- **Se aplica a**: Wscript
- **Procesos**: wscript.exe
- **Operación**: lectura de archivos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios**: C:\Users *\AppData**.js, C:\Users*\Downloads**.js
- **Reglas de reducción de superficie expuesta a ataques**: debido a problemas de confiabilidad y rendimiento, las reglas de ASR no tienen la capacidad de impedir que un proceso específico lea un tipo de archivo de script determinado. Tenemos una regla para evitar vectores de ataque que puedan originarse en estos escenarios. El nombre de la regla es "Impedir que JavaScript o VBScript inicien contenido ejecutable descargado" (GUID "d3e037e1-3eb8-44c8-a917-5792794759 " Bloquear la ejecución de scripts potencialmente ofuscados" (GUID " 5beb7efe-fd9a-4556-801d-275e5ffc04cc").
- **Otras características recomendadas**: aunque hay reglas de ASR específicas que mitigan ciertos vectores de ataque dentro de estos escenarios, es importante mencionar que AV es capaz de inspeccionar scripts de forma predeterminada (PowerShell, Host de scripts de Windows, JavaScript, VBScript, etc.) en tiempo real, a través de la interfaz de examen antimalware (AMSI). Más información disponible aquí: [Antimalware Scan Interface (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal).

### <a name="block-launch-of-child-processes"></a>Bloquear el inicio de procesos secundarios

- **Se aplica a** Adobe Acrobat
- **Procesos**: AcroRd32.exe, Acrobat.exe
- **Operación**: ejecución de procesos
- **Ejemplos de archivos o carpetas, claves o valores del Registro, procesos, servicios** cmd.exe, powershell.exe, wscript.exe
- **Reglas de reducción de superficie expuesta a ataques**: las reglas ASR permiten impedir que Adobe Reader inicie procesos secundarios. El nombre de la regla es "Impedir que Adobe Reader cree procesos secundarios", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".
- **Otras características recomendadas**: N/A

### <a name="block-download-or-creation-of-executable-content"></a>Bloquear la descarga o creación de contenido ejecutable

- **Se aplica a** certUtil: bloquear la descarga o creación de un archivo ejecutable
- **Procesos**: certutil.exe
- **Operación**: creación de archivos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios**- *.exe
- **Reglas de reducción de superficie expuesta a ataques**: las reglas de ASR no admiten estos escenarios porque forman parte de la protección antivirus de Microsoft Defender.
- **Otras características recomendadas**: Antivirus de Microsoft Defender impide que CertUtil cree o descargue contenido ejecutable.

### <a name="block-processes-from-stopping-critical-system-components"></a>Impedir que los procesos detengan componentes críticos del sistema

- **Se aplica a** todos los procesos
- **Procesos**- *
- **Operación**: finalización del proceso
- **Ejemplos de archivos o carpetas, claves o valores del Registro, procesos, servicios** MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe, etc.
- **Reglas de reducción de superficie expuesta a ataques**: las reglas de ASR no admiten estos escenarios porque están protegidas con protecciones de seguridad integradas de Windows.
- **Otras características recomendadas**: ELAM (Early Launch AntiMalware), PPL (Protection Process Light), PPL AntiMalware Light y System Guard.

### <a name="block-specific-launch-process-attempt"></a>Bloquear intento de proceso de inicio específico

- **Se aplica a procesos** específicos
- **Procesos**: "Nombre del proceso"
- **Operación**: ejecución de procesos
- **Ejemplos de archivos o carpetas, claves o valores del Registro, procesos, servicios** tor.exe, bittorrent.exe, cmd.exe, powershell.exe, etc.
- **Reglas de reducción de superficie expuesta a ataques**: en general, las reglas de ASR no están diseñadas para funcionar como administrador de aplicaciones.
- **Otras características recomendadas**: para evitar que los usuarios inicien procesos o programas específicos, se recomienda usar Windows Defender Application Control. Microsoft Defender para punto de conexión los indicadores de archivo y certificado, se pueden usar en un escenario de respuesta a incidentes (no debe verse como un mecanismo de control de aplicaciones).

### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Bloquear cambios no autorizados en las configuraciones del Antivirus de Microsoft Defender

- **Se aplica a** todos los procesos
- **Procesos**- *
- **Operación**: modificaciones del Registro
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios**: HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring, etc.
- **Reglas de reducción de superficie expuesta a ataques**: las reglas de ASR no cubren estos escenarios porque forman parte de la Microsoft Defender para punto de conexión protección integrada.
- **Otras características recomendadas**: Protección contra alteraciones (participación, administrada desde Intune) evita cambios no autorizados en las claves del Registro DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring y DisableIOAVProtection (entre otras).

Vea también

- [Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction-faq.yml)
- [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)
- [Evaluar las reglas de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
