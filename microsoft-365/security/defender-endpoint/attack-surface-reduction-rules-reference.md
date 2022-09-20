---
title: Referencia de reglas de reducción de superficie expuesta a ataques
description: Enumera los detalles sobre las reglas de reducción de superficie expuesta a ataques por regla.
keywords: Reglas de reducción de superficie expuesta a ataques, ASR, reglas de asr, caderas, sistema de prevención de intrusiones del host, reglas de protección, reglas contra vulnerabilidades de seguridad, antiexploit, reglas de vulnerabilidad de seguridad, reglas de prevención de infecciones, Microsoft Defender para punto de conexión, configurar reglas asr, descripción de la regla asr
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar,
manager: dansimp
ms.custom: asr
ms.topic: article
ms.collection: M365-security-compliance
ms.date: 08/10/2022
search.appverid: met150
ms.openlocfilehash: 778e21e2eefb4f0fd457e4c5c179d431225ce6c4
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67811578"
---
# <a name="attack-surface-reduction-rules-reference"></a>Referencia de reglas de reducción de superficie expuesta a ataques

**Se aplica a:**

- [Microsoft Microsoft 365 Defender para el plan de punto de conexión 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas:**

- Windows

En este artículo se proporciona información sobre las reglas de reducción de ataques:

- [Versiones admitidas del sistema operativo](#supported-operating-systems)
- [Sistemas de administración de configuración admitidos](#supported-configuration-management-systems)
- [Detalles de alerta y notificación por regla](#per-rule-alert-and-notification-details)
- [Regla ASR a matriz GUID](#asr-rule-to-guid-matrix)
- [Modos de regla de ASR](#asr-rule-modes)
- [Descripciones por regla](#per-rule-descriptions)

## <a name="supported-operating-systems"></a>Sistemas operativos compatibles 

En la tabla siguiente se enumeran los sistemas operativos admitidos para las reglas que se publican actualmente para la disponibilidad general. Las reglas se enumeran en orden alfabético en esta tabla.

> [!NOTE]
>
> A menos que se indique lo contrario, la compilación mínima de Windows&nbsp;10 es la versión 1709 (RS3, compilación 16299) o posterior; la compilación mínima de Windows&nbsp;Server es la versión 1809 o posterior.
>
> Las reglas de reducción de superficie expuesta a ataques en Windows&nbsp;Server&nbsp;2012&nbsp;R2 y Windows&nbsp;Server&nbsp;2016 están disponibles para los dispositivos incorporados mediante el paquete de solución unificada moderno. Para obtener más información, consulte [Nueva funcionalidad en la solución unificada moderna para Windows Server 2012 R2 y versión preliminar de 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview).

| Nombre de regla| Windows&nbsp;11 <br>y<br> Windows&nbsp;10 | Windows&nbsp;Server <br> 2022 <br>y<br>  Windows&nbsp;Server <br> 2019 | Windows Server | Windows&nbsp;Server <br> 2016 <sup>[[1, 2](#fn1)]<sup></sup> | Windows&nbsp;Server <br> 2012&nbsp;R2 <sup>[[1, 2](#fn1)]<sup></sup> |
|:---|:---:|:---:|:---:|:---:|:---:|
| [Bloquear el abuso de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) | v | v | v <br> versión 1803 (Canal empresarial semestral) o posterior | v | v |
| [Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | v <br> versión 1809 o posterior <sup>[[3](#fn1)]<sup></sup> | v | v | v | v |
| [Impedir que todas las aplicaciones de Office creen procesos secundarios](#block-all-office-applications-from-creating-child-processes) | v | v | v | v | v |
| [Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | v <br> versión 1803 o posterior <sup>[[3](#fn1)]<sup></sup> | v | v | v | v |
| [Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) | v | v | v | v | v |
| [Impedir que los archivos ejecutables se ejecuten a menos que cumplan un criterio de prevalencia, edad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | v <br> versión 1803 o posterior <sup>[[3](#fn1)]<sup></sup> | v | v | v | v |
| [Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) | v | v | v | v | v |
| [Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | v | v | v | N | N |
| [Impedir que las aplicaciones de Office creen contenido ejecutable](#block-office-applications-from-creating-executable-content) | v | v | v | v | v |
| [Impedir que las aplicaciones de Office inserten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes)  | v | v | v | v | v |
| [Impedir que la aplicación de comunicación de Office cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) | v | v | v | v | v |
| [Bloquear la persistencia a través de la suscripción de eventos de Instrumental de administración de Windows (WMI)](#block-persistence-through-wmi-event-subscription) <br> \*_No se admiten las exclusiones de archivos y carpetas._ | v <br> versión 1903 (compilación 18362) o posterior <sup>[[3](#fn1)]<sup></sup> | v | v <br> versión 1903 (compilación 18362) o posterior | N | N |
| [Bloquear las creaciones de procesos que se originen a partir de comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) | v <br> versión 1803 o posterior <sup>[[3](#fn1)]<sup></sup> | v | v | v | v |
| [Bloquear procesos que no son de confianza y no firmados que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | v | v | v | v | v |
| [Bloquear llamadas API de Win32 desde macros de Office](#block-win32-api-calls-from-office-macros) | v | v | v | N | N |
| [Uso de protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | v <br> versión 1803 o posterior <sup>[[3](#fn1)]<sup></sup> | v | v | v | v |

(<a id="fn1">1</a>) Hace referencia a la solución unificada moderna para Windows Server 2012 y 2016. Para obtener más información, vea [Incorporación de servidores Windows al servicio Defender para punto de conexión](configure-server-endpoints.md).

(<a id="fn1">2</a>) Para Windows&nbsp;Server 2016 y Windows&nbsp;Server 2012&nbsp;R2, la versión mínima necesaria del punto de conexión de Microsoft Configuration Manager es la versión 2111.

(<a id="fn1">3</a>) La versión y el número de compilación solo se aplican a Windows&nbsp;10.

## <a name="supported-configuration-management-systems"></a>Sistemas de administración de configuración admitidos

Debajo de esta tabla se enumeran vínculos a información sobre las versiones del sistema de administración de configuración a las que se hace referencia en esta tabla.

|Nombre de regla | Intune | Microsoft Endpoint Manager |Microsoft Endpoint Configuration Manager |<sup>directiva de grupo[[1](#fn1)]<sup></sup> | PowerShell<sup>[[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|:---:|
|[Bloquear el abuso de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) | v  | Y MEM OMA-URI |   | v  |  v  |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | v |   |  | v  | v  |
|[Impedir que todas las aplicaciones de Office creen procesos secundarios](#block-all-office-applications-from-creating-child-processes) | v |   |v <br><br> CB 1710 | v  | v  |
|[Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | v  |   | v <br><br>CB 1802 | v  | v  |
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) | v |  |v <br><br> CB 1710 | v | v  |
|[Impedir que los archivos ejecutables se ejecuten a menos que cumplan un criterio de prevalencia, edad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | v |   | v <br><br> CB 1802 |  v |  v |
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) | v |   |  v  <br><br> CB 1710 | v  | v  |
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | v |   | v <br><br> CB 1710 | v  | v  |
|[Impedir que las aplicaciones de Office creen contenido ejecutable](#block-office-applications-from-creating-executable-content) | v |  |v <br><br> CB 1710 | v  | v  |
|[Impedir que las aplicaciones de Office inserten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes) | v |  | v <br><br> CB 1710 | v  | v  |
|[Impedir que la aplicación de comunicación de Office cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) | v |  |v <br><br> CB 1710 | v  | v  |
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) |  |  |  |v   | v  |
|[Bloquear las creaciones de procesos que se originen a partir de comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) | v |   |   |  v | v  |
|[Bloquear procesos que no son de confianza y no firmados que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | v |   |v <br><br> CB 1802  | v  | v  |
|[Bloquear llamadas API de Win32 desde macros de Office](#block-win32-api-calls-from-office-macros) | v |   | v <br><br> CB 1710  | v  |  v |
|[Uso de protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | v |   | v <br><br> CB 1802 | v  | v  |

  (<a id="fn1">1</a>) Puede configurar reglas de reducción de superficie expuesta a ataques por regla mediante el GUID de cualquier regla.

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager (SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_SCCM ahora es Configuration Manager de punto de conexión de Microsoft._

## <a name="per-rule-alert-and-notification-details"></a>Detalles de alerta y notificación por regla

Las notificaciones del sistema se generan para todas las reglas en modo de bloque. Las reglas de cualquier otro modo no generarán notificaciones del sistema

Para las reglas con el "estado de regla" especificado:

- Las reglas de ASR con \<ASR Rule, Rule State\> combinaciones se usan para exponer alertas (notificaciones del sistema) en Microsoft Defender para punto de conexión solo para dispositivos en el nivel de bloque de alta nube. Los dispositivos que no estén en el nivel de bloque de nube alta no generarán alertas para ninguna <combinación de reglas de ASR, estado de regla>
- Las alertas de EDR se generan para las reglas de ASR en los estados especificados, pero solo para los dispositivos en el nivel de bloque de nube alta.

| Nombre de regla: | Estado de regla: | ¿Genera alertas en EDR? <br> (Sí&nbsp;\|&nbsp;No) | ¿Genera notificaciones del sistema? <br> (Sí&nbsp;\|&nbsp;No) |
|---|:---:|:---:|:---:|
|   |   |  _Solo para dispositivos en el nivel de bloque de nube alta_ | _Solo en modo de bloque_ |
|[Bloquear el abuso de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) |   | N  | v |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | Bloquear  | v <br> Requiere un dispositivo en el nivel de bloque de nube alta  | v <br> Requiere un dispositivo en el nivel de bloque de nube alta |
|[Impedir que todas las aplicaciones de Office creen procesos secundarios](#block-all-office-applications-from-creating-child-processes) |   | N | v |
|[Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) |   | N | v |
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) |   | v <br> Requiere un dispositivo en el nivel de bloque de nube alta | v <br> Requiere un dispositivo en el nivel de bloque de nube alta |
|[Impedir que los archivos ejecutables se ejecuten a menos que cumplan un criterio de prevalencia, edad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) |   | N | v |
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) |  Bloque de auditoría&nbsp;\|&nbsp; | Y \| Y <br> Requiere un dispositivo en el nivel de bloque de nube alta  | N \| Y <br> Requiere un dispositivo en el nivel de bloque de nube alta |
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Bloquear | v <br> Requiere un dispositivo en el nivel de bloque de nube alta  | v <br> Requiere un dispositivo en el nivel de bloque de nube alta |
|[Impedir que las aplicaciones de Office creen contenido ejecutable](#block-office-applications-from-creating-executable-content) |   | N | v |
|[Impedir que las aplicaciones de Office inserten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes)  |   | N | v |
|[Impedir que la aplicación de comunicación de Office cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) |  |  N | v |
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) |  Bloque de auditoría&nbsp;\|&nbsp; | Y \| Y <br> Requiere un dispositivo en el nivel de bloque de nube alta  | N \| Y <br> Requiere un dispositivo en el nivel de bloque de nube alta |
|[Bloquear las creaciones de procesos que se originen a partir de comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) |   | N | v |
|[Bloquear procesos que no son de confianza y no firmados que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Bloque de auditoría&nbsp;\|&nbsp; | Y \| Y <br> Requiere un dispositivo en el nivel de bloque de nube alta  | N \| Y <br> Requiere un dispositivo en el nivel de bloque de nube alta |
|[Bloquear llamadas API de Win32 desde macros de Office](#block-win32-api-calls-from-office-macros) |   | N | v |
|[Uso de protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | Bloque de auditoría&nbsp;\|&nbsp; | Y \| Y <br> Requiere un dispositivo en el nivel de bloque de nube alta  | N \| Y <br> Requiere un dispositivo en el nivel de bloque de nube alta |
  
## <a name="asr-rule-to-guid-matrix"></a>Regla ASR a matriz GUID

| Nombre de la regla | GUID de regla |
|:-----|:-----|
| Bloquear el abuso de controladores firmados vulnerables explotados | 56a863a9-875e-4185-98a7-b882c64b5ce5 |
| Impedir que Adobe Reader cree procesos secundarios | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c |
| Impedir que todas las aplicaciones de Office creen procesos secundarios | d4f940ab-401b-4efc-aadc-ad5f3c50688a |
| Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe) | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 |
| Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web | be9ba2d9-53ea-4cdc-84e5-9b1eeee46550 |
| Impedir que los archivos ejecutables se ejecuten a menos que cumplan un criterio de prevalencia, edad o lista de confianza | 01443614-cd74-433a-b99e-2ecdc07bfc25 |
| Bloquear la ejecución de scripts potencialmente ofuscados | 5beb7efe-fd9a-4556-801d-275e5ffc04cc |
| Impedir que JavaScript o VBScript inicien contenido ejecutable descargado | d3e037e1-3eb8-44c8-a917-57927947596d |
| Impedir que las aplicaciones de Office creen contenido ejecutable | 3b576869-a4ec-4529-8536-b80a7769e899 |
| Impedir que las aplicaciones de Office inserten código en otros procesos | 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84 |
| Impedir que la aplicación de comunicación de Office cree procesos secundarios | 26190899-1602-49e8-8b27-eb1d0a1ce869 |
| Bloquear la persistencia a través de la suscripción de eventos WMI <br>* No se admiten las exclusiones de archivos y carpetas. | e6db77e5-3df2-4cf1-b95a-636979351e5b |
| Bloquear las creaciones de procesos que se originen a partir de comandos PSExec y WMI | d1e49aac-8f56-4280-b9ba-993a6d77406c |
| Bloquear procesos que no son de confianza y no firmados que se ejecutan desde USB | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4 |
| Bloquear llamadas API de Win32 desde macros de Office | 92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b |
| Uso de protección avanzada contra ransomware | c1db55ab-c21a-4637-bb3f-a12568109d35 |

## <a name="asr-rule-modes"></a>Modos de regla de ASR

- **Sin configurar** o **Deshabilitar**: el estado en el que la regla ASR no se ha habilitado o se ha deshabilitado. Código para este estado = 0.
- **Bloquear**: el estado en el que está habilitada la regla ASR. El código de este estado es 1.
- **Auditoría**: el estado en el que se evalúa la regla ASR para el efecto que tendría en la organización o entorno si está habilitada (se establece para bloquear o advertir). El código de este estado es 2.
- **Advertir** Estado en el que está habilitada la regla ASR y presenta una notificación al usuario final, pero permite al usuario final omitir el bloque. El código de este estado es 6.

_El modo de advertencia_ es un tipo de modo de bloque que alerta a los usuarios sobre acciones potencialmente de riesgo. Los usuarios pueden optar por omitir el mensaje de advertencia de bloque y permitir la acción subyacente. Los usuarios pueden seleccionar **Aceptar** para aplicar el bloque o seleccionar la opción de omisión ( **Desbloquear** ) a través de la notificación del sistema emergente del usuario final que se genera en el momento del bloqueo. Una vez desbloqueada la advertencia, la operación se permite hasta la próxima vez que se produce el mensaje de advertencia, momento en el que el usuario final tendrá que volver a ejecutar la acción.

Cuando se hace clic en el botón Permitir, el bloque se suprimirá durante 24 horas. Después de 24 horas, el usuario final tendrá que volver a permitir el bloque. El modo de advertencia para las reglas ASR solo se admite para dispositivos RS5+ (1809+). Si la omisión se asigna a reglas ASR en dispositivos con versiones anteriores, la regla estará en modo bloqueado.

También puede establecer una regla en modo de advertencia a través de PowerShell especificando el AttackSurfaceReductionRules_Actions como "Advertir". Por ejemplo:

```powershell
-command "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Warn"} 
```

## <a name="per-rule-descriptions"></a>Descripciones por regla

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Bloquear el abuso de controladores firmados vulnerables explotados

Esta regla impide que una aplicación escriba un controlador firmado vulnerable en el disco. Las aplicaciones \- locales _que tienen privilegios suficientes_ para obtener acceso al kernel pueden aprovechar los controladores firmados vulnerables \- que están en estado salvaje y vulnerables. Los controladores firmados vulnerables permiten a los atacantes deshabilitar o eludir las soluciones de seguridad, lo que finalmente conduce a un riesgo para el sistema.

La regla **Bloquear abuso de controladores firmados vulnerables vulnerables** no impide que se cargue un controlador que ya existe en el sistema.

> [!NOTE]
>
> Puede configurar esta regla mediante MEM OMA-URI. Consulte [MEM OMA-URI](enable-attack-surface-reduction.md#mem) para configurar reglas personalizadas.
>
> También puede configurar esta regla mediante [PowerShell](enable-attack-surface-reduction.md#powershell).
>
> Para que se examine un controlador, use este sitio web para [enviar un controlador para su análisis](https://www.microsoft.com/en-us/wdsi/driversubmission).

<!--The above link is the 'only link' that exists for having drivers examined. The 'en-us' component is required to make the link work. Any alterations to this link will result in a 404.
-->

nombre de Intune:`Block abuse of exploited vulnerable signed drivers`

Configuration Manager nombre: todavía no disponible
  
GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

Tipo de acción de búsqueda avanzada:

- AsrVulnerableSignedDriverAudited
- AsrVulnerableSignedDriverBlocked

<!-- 
Dependencies: none provided by engineering
-->

### <a name="block-adobe-reader-from-creating-child-processes"></a>Impedir que Adobe Reader cree procesos secundarios

Esta regla evita ataques al impedir que Adobe Reader cree procesos.

El malware puede descargar e iniciar cargas útiles y salir de Adobe Reader a través de ingeniería social o vulnerabilidades de seguridad. Al impedir que Adobe Reader genere procesos secundarios, no se puede propagar el malware que intenta usar Adobe Reader como vector de ataque.

Intune nombre:`Process creation from Adobe Reader (beta)`

Configuration Manager nombre: todavía no disponible

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

Tipo de acción de búsqueda avanzada:

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

Dependencias: Antivirus de Microsoft Defender

### <a name="block-all-office-applications-from-creating-child-processes"></a>Impedir que todas las aplicaciones de Office creen procesos secundarios

Esta regla impide que las aplicaciones de Office creen procesos secundarios. Las aplicaciones de Office incluyen Word, Excel, PowerPoint, OneNote y Access.

La creación de procesos secundarios malintencionados es una estrategia de malware común. El malware que abusa de Office como vector a menudo ejecuta macros de VBA y aprovecha el código para descargar e intentar ejecutar más cargas. Sin embargo, algunas aplicaciones legítimas de línea de negocio también pueden generar procesos secundarios con fines benignos; como generar un símbolo del sistema o usar PowerShell para configurar la configuración del Registro.

Intune nombre:`Office apps launching child processes`

Configuration Manager nombre:`Block Office application from creating child processes`

GUID: `d4f940ab-401b-4efc-aadc-ad5f3c50688a`

Tipo de acción de búsqueda avanzada:

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

Dependencias: Antivirus de Microsoft Defender

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows

Esta regla ayuda a evitar el robo de credenciales mediante el bloqueo del servicio de subsistema de autoridad de seguridad local (LSASS).

LSASS autentica a los usuarios que inician sesión en un equipo Windows. Credential Guard de Microsoft Defender en Windows normalmente impide los intentos de extraer credenciales de LSASS. Algunas organizaciones no pueden habilitar Credential Guard en todos sus equipos debido a problemas de compatibilidad con controladores de tarjeta inteligente personalizados u otros programas que se cargan en la autoridad de seguridad local (LSA). En estos casos, los atacantes pueden usar herramientas como Mimikatz para extraer contraseñas de texto no cifrado y hashES NTLM de LSASS.

> [!NOTE]
> En algunas aplicaciones, el código enumera todos los procesos en ejecución e intenta abrirlos con permisos exhaustivos. Esta regla deniega la acción de apertura del proceso de la aplicación y registra los detalles en el registro de eventos de seguridad. Esta regla puede generar mucho ruido. Si tiene una aplicación que simplemente enumera LSASS, pero no tiene ningún impacto real en la funcionalidad, no es necesario agregarla a la lista de exclusión. Por sí sola, esta entrada del registro de eventos no indica necesariamente una amenaza malintencionada.
  
> [!IMPORTANT]
> El estado predeterminado de la regla reducción de superficie expuesta a ataques (ASR) "Bloquear el robo de credenciales del subsistema de entidad de seguridad local de Windows (lsass.exe)" cambiará de **No configurado** a **Configurado** y el modo predeterminado establecido en **Bloquear**. Todas las demás reglas de ASR permanecerán en su estado predeterminado: **No configurado**. Ya se ha incorporado lógica de filtrado adicional en la regla para reducir las notificaciones del usuario final. Los clientes pueden configurar la regla en los modos **Auditar**, **Advertir** o **Deshabilitado** , lo que invalidará el modo predeterminado. La funcionalidad de esta regla es la misma, tanto si la regla está configurada en el modo de forma predeterminada como si habilita el modo de bloqueo manualmente.

Intune nombre:`Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager nombre:`Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

Tipo de acción de búsqueda avanzada:

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

Dependencias: Antivirus de Microsoft Defender

### <a name="block-executable-content-from-email-client-and-webmail"></a>Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web

Esta regla impide que los siguientes tipos de archivo se inicien desde el correo electrónico abierto dentro de la aplicación Microsoft Outlook, o Outlook.com y otros proveedores de correo web populares:

- Archivos ejecutables (como .exe, .dll o .scr)
- Archivos de script (como un .ps1 de PowerShell, Visual Basic .vbs o un archivo de .js de JavaScript)

Intune nombre:`Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Nombre de microsoft Endpoint Manager:`Block executable content from email client and webmail`

GUID: `be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

Tipo de acción de búsqueda avanzada:

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

Dependencias: Antivirus de Microsoft Defender

> [!NOTE]
> La regla **Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web** tiene las siguientes descripciones alternativas, en función de la aplicación que use:
>
> - Intune (perfiles de configuración): la ejecución del contenido ejecutable (exe, dll, ps, js, vbs, etc.) se ha eliminado del correo electrónico (cliente de correo web/correo) (sin excepciones).
> - Endpoint Manager: bloquear la descarga de contenido ejecutable de clientes de correo electrónico y correo web.
> - directiva de grupo: Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Impedir que los archivos ejecutables se ejecuten a menos que cumplan un criterio de prevalencia, edad o lista de confianza

Esta regla impide que se inicien archivos ejecutables, como .exe, .dll o .scr. Por lo tanto, iniciar archivos ejecutables desconocidos o que no son de confianza puede ser arriesgado, ya que es posible que no esté claro inicialmente si los archivos son malintencionados.

> [!IMPORTANT]
> Debe [habilitar la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) para usar esta regla.
>
> La regla **Impedir que los archivos ejecutables se ejecuten a menos que cumplan un criterio de prevalencia, edad o lista de confianza** con GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` es propiedad de Microsoft y no lo especifican los administradores. Esta regla usa la protección entregada en la nube para actualizar su lista de confianza con regularidad.
>
> Puede especificar archivos o carpetas individuales (mediante rutas de acceso de carpeta o nombres de recursos completos), pero no puede especificar a qué reglas o exclusiones se aplican.

Intune nombre:`Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager nombre:`Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

Tipo de acción de búsqueda avanzada:

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

Dependencias: Antivirus de Microsoft Defender, Protección en la nube

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Bloquear la ejecución de scripts potencialmente ofuscados

Esta regla detecta propiedades sospechosas dentro de un script ofuscado.
  
> [!IMPORTANT]
> Los scripts de PowerShell se han excluido temporalmente de la regla "Bloquear la ejecución de scripts potencialmente ofuscados" debido a los problemas de FP a gran escala que se han enfrentado en el pasado.

La ofuscación de scripts es una técnica común que usan los autores de malware y las aplicaciones legítimas para ocultar la propiedad intelectual o reducir los tiempos de carga de scripts. Los autores de malware también usan ofuscación para dificultar la lectura de código malintencionado, lo que dificulta el examen de cerca por parte de los humanos y el software de seguridad.

> [!IMPORTANT]
> Debido al alto número de falsos positivos, esta regla no detecta actualmente scripts de PowerShell; se trata de una solución temporal. La regla se actualizará y comenzará a volver a detectar scripts de PowerShell pronto.

Intune nombre:`Obfuscated js/vbs/ps/macro code`

Configuration Manager nombre:`Block execution of potentially obfuscated scripts`

GUID: `5beb7efe-fd9a-4556-801d-275e5ffc04cc`

Tipo de acción de búsqueda avanzada:

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

Dependencias: Antivirus de Microsoft Defender, interfaz de examen antimalware (AMSI)

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Impedir que JavaScript o VBScript inicien contenido ejecutable descargado

Esta regla impide que los scripts inicien contenido descargado potencialmente malintencionado. El malware escrito en JavaScript o VBScript a menudo actúa como descargador para capturar e iniciar otro malware desde Internet.

Aunque no es común, las aplicaciones de línea de negocio a veces usan scripts para descargar e iniciar instaladores.

Intune nombre:`js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager nombre:`Block JavaScript or VBScript from launching downloaded executable content`

GUID: `d3e037e1-3eb8-44c8-a917-57927947596d`

Tipo de acción de búsqueda avanzada:

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

Dependencias: Antivirus de Microsoft Defender, AMSI

### <a name="block-office-applications-from-creating-executable-content"></a>Impedir que las aplicaciones de Office creen contenido ejecutable

Esta regla impide que las aplicaciones de Office, incluidos Word, Excel y PowerPoint, creen contenido ejecutable potencialmente malintencionado, bloqueando la escritura de código malintencionado en el disco.

El malware que abusa de Office como vector podría intentar salir de Office y guardar componentes malintencionados en el disco. Estos componentes malintencionados sobrevivirían a un reinicio del equipo y persistirían en el sistema. Por lo tanto, esta regla se defiende frente a una técnica de persistencia común.

Intune nombre:`Office apps/macros creating executable content`

Nombre de SCCM: `Block Office applications from creating executable content`

GUID: `3b576869-a4ec-4529-8536-b80a7769e899`

Tipo de acción de búsqueda avanzada:

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

Dependencias: Antivirus de Microsoft Defender, RPC

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Impedir que las aplicaciones de Office inserten código en otros procesos

Esta regla bloquea los intentos de inyección de código de aplicaciones de Office en otros procesos.

Los atacantes pueden intentar usar aplicaciones de Office para migrar código malintencionado a otros procesos mediante la inyección de código, de modo que el código pueda enmascararse como un proceso limpio.

No hay ningún propósito comercial legítimo conocido para usar la inyección de código.

Esta regla se aplica a Word, Excel y PowerPoint.

Intune nombre:`Office apps injecting code into other processes (no exceptions)`

Configuration Manager nombre:`Block Office applications from injecting code into other processes`

GUID: `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

Tipo de acción de búsqueda avanzada:

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

Dependencias: Antivirus de Microsoft Defender

### <a name="block-office-communication-application-from-creating-child-processes"></a>Impedir que la aplicación de comunicación de Office cree procesos secundarios

Esta regla impide que Outlook cree procesos secundarios, a la vez que permite funciones legítimas de Outlook.

Esta regla protege contra ataques de ingeniería social e impide que el código de explotación abuse de vulnerabilidades en Outlook. También protege contra [las vulnerabilidades de seguridad de formularios y reglas de Outlook](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) que los atacantes pueden usar cuando las credenciales de un usuario están en peligro.

> [!NOTE]
> Esta regla bloquea las sugerencias de directiva DLP y las información sobre herramientas en Outlook. Esta regla solo se aplica a Outlook y Outlook.com.

Intune nombre:`Process creation from Office communication products (beta)`

nombre de Configuration Manager: No disponible

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

Tipo de acción de búsqueda avanzada:

- AsrOfficeCommAppChildProcessAudited
- AsrOfficeCommAppChildProcessBlocked

Dependencias: Antivirus de Microsoft Defender

### <a name="block-persistence-through-wmi-event-subscription"></a>Bloquear la persistencia a través de la suscripción de eventos WMI

Esta regla impide que el malware abuse de WMI para lograr persistencia en un dispositivo.

> [!IMPORTANT]
> Las exclusiones de archivos y carpetas no se aplican a esta regla de reducción de superficie expuesta a ataques.

Las amenazas sin archivo emplean varias tácticas para permanecer ocultas, evitar ser detectadas en el sistema de archivos y obtener el control de la ejecución periódica. Algunas amenazas pueden abusar del repositorio WMI y el modelo de eventos para permanecer ocultas.

Intune nombre: No disponible

nombre de Configuration Manager: No disponible

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

Tipo de acción de búsqueda avanzada:

- AsrPersistenceThroughWmiAudited
- AsrPersistenceThroughWmiBlocked

Dependencias: Antivirus de Microsoft Defender, RPC

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Bloquear las creaciones de procesos que se originen a partir de comandos PSExec y WMI

Esta regla impide que se ejecuten los procesos creados a través de [PsExec](/sysinternals/downloads/psexec) y [WMI](/windows/win32/wmisdk/about-wmi) . PsExec y WMI pueden ejecutar código de forma remota. Existe el riesgo de que el malware abuse de la funcionalidad de PsExec y WMI con fines de comando y control, o de propagar una infección a través de la red de una organización.

> [!WARNING]
> Use esta regla solo si va a administrar los dispositivos con [Intune](/intune) u otra solución MDM. Esta regla no es compatible con la administración a través [del punto de conexión de Microsoft Configuration Manager](/configmgr) porque esta regla bloquea los comandos WMI que el cliente Configuration Manager usa para funcionar correctamente.

Intune nombre:`Process creation from PSExec and WMI commands`

Configuration Manager nombre: no aplicable

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

Tipo de acción de búsqueda avanzada:

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

Dependencias: Antivirus de Microsoft Defender

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Bloquear procesos que no son de confianza y no firmados que se ejecutan desde USB

Con esta regla, los administradores pueden evitar que los archivos ejecutables no firmados o que no son de confianza se ejecuten desde unidades extraíbles USB, incluidas las tarjetas SD. Los tipos de archivo bloqueados incluyen archivos ejecutables (como .exe, .dll o .scr)

> [!IMPORTANT]
> Esta regla bloqueará los archivos copiados desde el USB a la unidad de disco si y cuándo se van a ejecutar en la unidad de disco.

Intune nombre:`Untrusted and unsigned processes that run from USB`

Configuration Manager nombre:`Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

Tipo de acción de búsqueda avanzada:

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

Dependencias: Antivirus de Microsoft Defender

### <a name="block-win32-api-calls-from-office-macros"></a>Bloquear llamadas API de Win32 desde macros de Office

Esta regla impide que las macros de VBA llamen a las API de Win32.

VBA de Office habilita las llamadas API de Win32. El malware puede abusar de esta funcionalidad, como [llamar a las API win32 para iniciar código de shell malintencionado](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) sin escribir nada directamente en el disco. La mayoría de las organizaciones no se basan en la capacidad de llamar a las API win32 en su funcionamiento diario, incluso si usan macros de otras maneras.

Sistemas operativos compatibles:

- [Windows 10, versión 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versión 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune nombre:`Win32 imports from Office macro code`

Configuration Manager nombre:`Block Win32 API calls from Office macros`

GUID: `92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`

Tipo de acción de búsqueda avanzada:

- AsrOfficeMacroWin32ApiCallsAudited
- AsrOfficeMacroWin32ApiCallsBlocked

Dependencias: Antivirus de Microsoft Defender, AMSI

### <a name="use-advanced-protection-against-ransomware"></a>Uso de protección avanzada contra ransomware

Esta regla proporciona una capa adicional de protección contra ransomware. Usa heurística de cliente y nube para determinar si un archivo es similar a un ransomware. Esta regla no bloquea los archivos que tienen una o varias de las características siguientes:

- Ya se ha detectado que el archivo no está en la nube de Microsoft.
- El archivo es un archivo firmado válido.
- El archivo es lo suficientemente frecuente como para no ser considerado como ransomware.

La regla tiende a errar en el lado de la precaución para evitar ransomware.

> [!NOTE]
> Debe [habilitar la protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) para usar esta regla.

Intune nombre:`Advanced ransomware protection`

Configuration Manager nombre:`Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

Tipo de acción de búsqueda avanzada:

- AsrRansomwareAudited
- AsrRansomwareBlocked

Dependencias: Antivirus de Microsoft Defender, Protección en la nube
