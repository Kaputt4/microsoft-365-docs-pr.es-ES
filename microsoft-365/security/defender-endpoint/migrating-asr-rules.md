---
title: Migración de un HIPS de terceros a reglas ASR
description: Describe cómo abordar una migración desde una solución del Sistema de prevención de intrusiones de host (HIPS) de terceros en reglas ASR.
keywords: Reglas de reducción de superficie de ataque, asr, reglas asr, hips, sistema de prevención de intrusiones de host, reglas de protección, antiexploit, exploit, prevención de infecciones, Microsoft Defender para Endpoint
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 0c2ffdde4ff259f2a2ef098a6d715cbcd785dfe4
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "59357636"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Migración de un HIPS de terceros a reglas ASR

Este artículo le ayuda a asignar reglas comunes a Microsoft Defender para endpoint.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Escenarios al migrar desde un producto DE HIPS de terceros a reglas ASR

### <a name="block-creation-of-specific-files"></a>Bloquear la creación de archivos específicos

- **Se aplica a**- Todos los procesos
- **Operación:** creación de archivos
- Ejemplos de **archivos/carpetas, claves/valores del Registro, procesos,** servicios - *.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab
- **Reglas de reducción de** superficie de ataque: las reglas ASR bloquean las técnicas de ataque y no los indicadores de compromiso (IOC). Bloquear una extensión de archivo específica no siempre es útil, ya que no impide que un dispositivo se vea comprometido. Solo frustra parcialmente un ataque hasta que los atacantes crean un nuevo tipo de extensión para la carga.
- **Otras características recomendadas:** se recomienda encarecidamente tener habilitado el antivirus de Microsoft Defender, junto con la protección en la nube y el análisis de comportamiento. Se recomienda usar otra prevención, como la regla ASR "Usar protección avanzada contra ransomware". Esto proporciona un mayor nivel de protección contra ataques de ransomware. Además, muchas de estas claves del Registro son supervisadas por Microsoft Defender para endpoint, como las técnicas ASEP, que desencadenarán alertas específicas. Las claves del Registro usadas requieren un mínimo de privilegios de administrador local o instalador de confianza. Se recomienda usar un entorno bloqueado, con derechos o cuentas administrativas mínimos. Se pueden habilitar otras configuraciones del sistema, como "Deshabilitar SeDebug para roles no obligatorios" que forman parte de nuestras recomendaciones de seguridad más amplias.

### <a name="block-creation-of-specific-registry-keys"></a>Bloquear la creación de claves del Registro específicas

- **Se aplica a**- Todos los procesos
- **Procesos:** N/A
- **Operación:** modificaciones del Registro
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios** -  *\Software*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **Reglas de reducción de** superficie de ataque: las reglas ASR bloquean las técnicas de ataque y no los indicadores de compromiso (IOC). Bloquear una extensión de archivo específica no siempre es útil, ya que no impide que un dispositivo se vea comprometido. Solo frustra parcialmente un ataque hasta que los atacantes crean un nuevo tipo de extensión para la carga.
- **Otras características recomendadas:** se recomienda encarecidamente tener habilitado el antivirus de Microsoft Defender, junto con la protección en la nube y el análisis de comportamiento. Se recomienda usar prevención adicional, como la regla ASR "Usar protección avanzada contra ransomware". Esto proporciona un mayor nivel de protección contra ataques de ransomware. Además, Microsoft Defender para endpoint supervisa varias de estas claves del Registro, como las técnicas ASEP, que desencadenarán alertas específicas. Además, las claves del Registro usadas requieren un mínimo de privilegios de administrador local o instalador de confianza. Se recomienda usar un entorno bloqueado, con derechos o cuentas administrativas mínimos. Se pueden habilitar otras configuraciones del sistema, como "Deshabilitar SeDebug para roles no obligatorios" que forman parte de nuestras recomendaciones de seguridad más amplias.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Impedir que los programas que no son de confianza se ejecuten desde unidades extraíbles

- **Se aplica a:** Programas que no son de confianza desde USB
- **Procesos**: *
- **Operación:** ejecución de procesos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios:-*
- **Reglas** de reducción de surface de ataque: las reglas ASR tienen una regla integrada para impedir el inicio de programas que no son de confianza y que no tienen firma de unidades extraíbles: "Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Otras** características recomendadas: explore controles adicionales para dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint: Cómo controlar dispositivos USB y otros medios extraíbles con [Microsoft Defender para Endpoint](/windows/security/threat-protection/device-control/control-usb-devices-using-intune).

### <a name="block-mshta-from-launching-certain-child-processes"></a>Impedir que Mshta inicie determinados procesos secundarios

- **Se aplica a**- Mshta
- **Procesos:** mshta.exe
- **Operación:** ejecución de procesos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos,** servicios: powershell.exe, cmd.exe, regsvr32.exe
- **Reglas de reducción de** superficie de ataque: las reglas ASR no contienen ninguna regla específica para evitar que los procesos secundarios "mshta.exe". Este control está dentro de las competencias de Protección contra vulnerabilidades o Windows Defender control de aplicaciones.
- **Otras características recomendadas:** habilite Windows Defender control de aplicaciones para evitar mshta.exe que se ejecuten por completo. Si su organización requiere "mshta.exe" para aplicaciones de línea de negocio, configure una regla específica de protección contra vulnerabilidades de Windows Defender, para evitar que mshta.exe iniciar procesos secundarios.

### <a name="block-outlook-from-launching-child-processes"></a>Bloquear Outlook iniciar procesos secundarios

- **Se aplica a**- Outlook
- **Procesos:** outlook.exe
- **Operación:** ejecución de procesos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios**- powershell.exe
- Reglas de reducción de **Surface** de ataque: las reglas ASR tienen una regla integrada para impedir que las aplicaciones de comunicación de Office (Outlook, Skype y Teams) inicien procesos secundarios: Office "Bloquear una aplicación de comunicación para que no cree procesos secundarios", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Otras características recomendadas:** se recomienda habilitar el modo de idioma restringido de PowerShell para minimizar la superficie de ataque de PowerShell.

### <a name="block-office-apps-from-launching-child-processes"></a>Bloquear Office aplicaciones de inicio de procesos secundarios

- **Se aplica a**- Office
- **Procesos:** winword.exe, powerpnt.exe, excel.exe
- **Operación:** ejecución de procesos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos,** servicios: powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- Reglas de reducción de **surface** de ataque: las reglas ASR tienen una regla integrada para impedir que las aplicaciones de Office inicien procesos secundarios: "Impedir que todas las aplicaciones Office creen procesos secundarios", GUID "d4f940ab-401b-4efc-aadc-ad5f3c50688a".
- **Otras características recomendadas:** N/A

### <a name="block-office-apps-from-creating-executable-content"></a>Bloquear Office aplicaciones de creación de contenido ejecutable

- **Se aplica a**- Office
- **Procesos:** winword.exe, powerpnt.exe, excel.exe
- **Operación:** creación de archivos
- **Ejemplos de archivos/carpetas,** Claves y valores del Registro, procesos, servicios: C:\Users *\AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\Temp **.com, C:\Users*\Downloads**.exe, C:\Users *\AppData **.scf, C:\ProgramData**.scf, C:\Users\Public*.exe, C:\Users*\Desktop***.exe
- **Reglas de reducción de superficie de ataque:** N/A.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Impedir que Wscript lea determinados tipos de archivos

- **Se aplica a**- Wscript
- **Procesos:** wscript.exe
- **Operación:** lectura de archivo
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos,** servicios : C:\Users *\AppData**.js, C:\Users*\Downloads**.js
- **Reglas de reducción** de surface de ataque: debido a problemas de confiabilidad y rendimiento, las reglas ASR no tienen la capacidad de impedir que un proceso específico lea un tipo de archivo de script determinado. Tenemos una regla para evitar vectores de ataque que puedan originarse en estos escenarios. El nombre de la regla es "Bloquear JavaScript o VBScript para iniciar contenido ejecutable descargado" (GUID "d3e037e1-3eb8-44c8-a917-57927947596 ") y la "Ejecución de bloqueo de scripts potencialmente ofuscados" (GUID " 5beb7efe-fd9a-4556-801d-275e5ffc04cc").
- Otras características recomendadas: aunque hay reglas ASR específicas que mitigan ciertos vectores de ataque en estos escenarios, es importante mencionar que AV es capaz de inspeccionar scripts (PowerShell, host de script de Windows, JavaScript, VBScript y más) en tiempo real, a través de la Interfaz de examen antimalware (AMSI). Hay más información disponible aquí: Interfaz de [examen antimalware (AMSI).](/windows/win32/amsi/antimalware-scan-interface-portal)

### <a name="block-launch-of-child-processes"></a>Bloquear el inicio de procesos secundarios

- **Se aplica a**- Adobe Acrobat
- **Procesos:** AcroRd32.exe, Acrobat.exe
- **Operación:** ejecución de procesos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos,** servicios: cmd.exe, powershell.exe, wscript.exe
- **Reglas de reducción de surface de** ataque: las reglas ASR permiten impedir que Adobe Reader inicie procesos secundarios. El nombre de regla es "Bloquear Adobe Reader de la creación de procesos secundarios", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".
- **Otras características recomendadas:** N/A

### <a name="block-download-or-creation-of-executable-content"></a>Bloquear la descarga o creación de contenido ejecutable

- **Se aplica a**- CertUtil: Bloquear la descarga o creación de archivos ejecutables
- **Procesos:** certutil.exe
- **Operación:** creación de archivos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos, servicios**- *.exe
- **Reglas de reducción de** superficie de ataque: las reglas ASR no admiten estos escenarios porque forman parte de la Antivirus de Microsoft Defender protección.
- **Otras características recomendadas:** Microsoft Defender AV impide que CertUtil cree o descargue contenido ejecutable.

### <a name="block-processes-from-stopping-critical-system-components"></a>Impedir que los procesos detengan componentes críticos del sistema

- **Se aplica a**- Todos los procesos
- **Procesos**: *
- **Operación:** terminación del proceso
- Ejemplos de **archivos/carpetas, claves/valores del Registro, procesos,** servicios: MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe, etc.
- **Reglas de reducción** de superficie de ataque: las reglas ASR no admiten estos escenarios porque están protegidas con Windows 10 de seguridad integradas.
- **Otras características recomendadas:** ELAM (Early Launch AntiMalware), PPL (Protection Process Light), PPL AntiMalware Light y System Guard.

### <a name="block-specific-launch-process-attempt"></a>Bloquear un intento de proceso de inicio específico

- **Se aplica a**- Procesos específicos
- **Procesos:**"Nombre del proceso"
- **Operación:** ejecución de procesos
- **Ejemplos de archivos/carpetas, claves/valores del Registro, procesos,** servicios: tor.exe, bittorrent.exe, cmd.exe, powershell.exe y mucho más
- **Reglas de reducción de** superficie de ataque: en general, las reglas ASR no están diseñadas para funcionar como administrador de aplicaciones.
- **Otras características recomendadas:** para evitar que los usuarios inicien programas o procesos específicos, se recomienda usar Windows Defender control de aplicaciones. Microsoft Defender para indicadores de archivo de extremo y cert, se puede usar en un escenario de respuesta a incidentes (no debe verse como un mecanismo de control de aplicaciones).

### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Bloquear cambios no autorizados en Antivirus de Microsoft Defender configuraciones

- **Se aplica a**- Todos los procesos
- **Procesos**: *
- **Operación:** modificaciones del Registro
- Ejemplos de **archivos/carpetas, claves/valores del Registro, procesos,** servicios : HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring, y así sucesivamente.
- **Reglas de reducción** de superficie de ataque: las reglas ASR no cubren estos escenarios porque forman parte de la protección integrada de Microsoft Defender para puntos de conexión.
- Otras características recomendadas: la protección contra alteraciones (opt-in, administrada desde Intune) evita cambios no autorizados en las claves del Registro DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring y DisableIOAVProtection (y mucho más).

Ver también

- [Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction-faq.yml)
- [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)
- [Evaluar las reglas de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
