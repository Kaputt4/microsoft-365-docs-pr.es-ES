---
title: Referencia de reglas de reducción de superficie de ataque
description: Enumera detalles sobre las reglas de reducción de superficie de ataque por regla.
keywords: Reglas de reducción de superficie de ataque, ASR, reglas asr, hips, sistema de prevención de intrusiones de host, reglas de protección, reglas antiexploit, antiexploit, reglas de vulnerabilidad, reglas de prevención de infecciones, Pertahanan Microsoft untuk Titik Akhir, configurar reglas ASR, descripción de regla ASR
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar,
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.date: 02/04/2022
ms.openlocfilehash: 377ae12eb2436dcafe84e521fd4b35d712283e74
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64637992"
---
# <a name="attack-surface-reduction-rules-reference"></a>Referencia de reglas de reducción de superficie de ataque

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En este artículo se proporciona información sobre las reglas de reducción de ataques:

- [Versiones de sistema operativo compatibles](#supported-operating-systems)
- [Sistemas de administración de configuración compatibles](#supported-configuration-management-systems)
- [Detalles de alertas y notificaciones por regla](#per-rule-alert-and-notification-details)
- [Reglas ASR y matriz de GUID](#asr-rules-and-guids-matrix)
- [Modos de regla ASR](#asr-rule-modes)
- [Descripciones por regla](#per-rule-descriptions)
  - Descripciones de reglas
  - Nombres de reglas del sistema de administración de configuración

## <a name="public-preview-supported-operating-systems"></a>Versión preliminar pública: sistemas operativos compatibles

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

En la tabla siguiente se enumeran los sistemas operativos compatibles para las reglas de reducción de superficie de ataque que actualmente son productos de versión preliminar. Las reglas se enumeran en orden alfabético. A&nbsp; menos que se indique lo contrario, la compilación mínima de Windows&nbsp; 10 es la versión 1709 (RS3, compilación 16299) o posterior; la compilación mínima de Windows Server es la versión 1809 o posterior.

> [!NOTE]
> Las reglas de reducción de superficie de ataque de Windows&nbsp; Server2012R2&nbsp;&nbsp; y Windows&nbsp; Server2016&nbsp; están disponibles para dispositivos incorporados mediante el paquete de soluciones unificado moderno. Para obtener más información, vea [New functionality in the modern unified solution for Windows Server 2012 R2 and 2016 Preview](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview).
>

| Nombre de regla | &nbsp;Windows Server 2016 <sup>[[1](#fn1)]<sup></sup> | &nbsp;Windows Server 2012 R2 <sup>[[1](#fn1)]<sup></sup> |
|---|:---:|:---:|
|[Bloquear el uso indebido de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) | v | v |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | v | v |
|[Bloquear todas Office aplicaciones de creación de procesos secundarios](#block-all-office-applications-from-creating-child-processes) | v | v |
|[Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | v | v |
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) | v | v |
|[Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | v | v |
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) | v | v |
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | N | N |
|[Bloquear Office aplicaciones de creación de contenido ejecutable](#block-office-applications-from-creating-executable-content) | v | v |
|[Bloquear Office aplicaciones para que no inyecten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes)  | v | v |
|[Bloquear Office de comunicación para que no cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) | v | v |
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) \* _No se admiten exclusiones de archivos y carpetas._ | N | N |
|[Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) | v | v |
|[Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | v | v |
|[Bloquear llamadas a la API de Win32 desde Office macros](#block-win32-api-calls-from-office-macros) | N | N |
|[Usar protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | v | v |
|  |  |  |

(<a id="fn1">1</a>) Hace referencia a la solución moderna y unificada para Windows Server 2012 y 2016. Para obtener más información, [vea Onboard Windows Servers to the Defender for Endpoint service](configure-server-endpoints.md).

_End Public Preview: Sistemas operativos compatibles_

## <a name="supported-operating-systems"></a>Sistemas operativos compatibles 

En la tabla siguiente se enumeran los sistemas operativos compatibles para las reglas que actualmente se liberan a disponibilidad general. Las reglas se enumeran en orden alfabético.

> [!Note]
>
> A&nbsp; menos que se indique lo contrario, la compilación mínima de Windows&nbsp; 10 es la versión 1709 (RS3, compilación 16299) o posterior; la compilación mínima de Windows Server es la versión 1809 o posterior.
>

|Nombre de regla|&nbsp;Windows 10|&nbsp;Windows Server 2019|&nbsp;Windows Server|
|---|:---:|:---:|:---:|
|[Bloquear el uso indebido de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) | v | v | v <br><br> versión 1803 (canal semianual) o posterior |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | Versión Y 1809 o posterior | v | v  <br><br> |
|[Bloquear todas Office aplicaciones de creación de procesos secundarios](#block-all-office-applications-from-creating-child-processes) | v | v | v <br><br> |
|[Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Versión Y 1803 o posterior | v <br><br> | v <br><br> |
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) | v | v <br><br> | v <br><br> |
|[Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Versión Y 1803 o posterior | v <br><br> | v <br><br> |
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) | v | v <br><br> | v <br><br> |
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | v | v <br><br> | v <br><br> |
|[Bloquear Office aplicaciones de creación de contenido ejecutable](#block-office-applications-from-creating-executable-content) | v | v <br><br> | v <br><br> |
|[Bloquear Office aplicaciones para que no inyecten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes)  | v | v <br><br> | v <br><br> |
|[Bloquear Office de comunicación para que no cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) | v | v <br><br> | v <br><br> |
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) <br><br> \*_No se admiten exclusiones de archivos y carpetas._ | Versión Y 1903 (compilación 18362) o posterior| v | v <br><br> versión 1903 (compilación 18362) o posterior |
|[Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) | Versión Y 1803 o posterior | v <br><br> | v <br><br>  |
|[Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | v | v <br><br> | v <br><br> |
|[Bloquear llamadas a la API de Win32 desde Office macros](#block-win32-api-calls-from-office-macros) | v | v <br><br> | v <br><br> |
|[Usar protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | Versión Y 1803 o posterior | v <br><br> | v <br><br> |
|  |  |  |  |

## <a name="supported-configuration-management-systems"></a>Sistemas de administración de configuración compatibles

Los vínculos a información sobre las versiones del sistema de administración de configuración a las que se hace referencia en esta tabla se enumeran debajo de esta tabla.

|Nombre de regla | Intune | Microsoft Endpoint Manager |Microsoft Endpoint Configuration Manager |<sup>directiva de grupo[[1](#fn1)]<sup></sup> | PowerShell<sup>[[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|:---:|
|[Bloquear el uso indebido de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) | v  | Y MEM OMA-URI |   | v  |  v  |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | v |   |  | v  | v  |
|[Bloquear todas Office aplicaciones de creación de procesos secundarios](#block-all-office-applications-from-creating-child-processes) | v |   |v <br><br> CB 1710 | v  | v  |
|[Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | v  |   | v <br><br>CB 1802 | v  | v  |
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) | v |  |v <br><br> CB 1710 | v | v  |
|[Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | v |   | v <br><br> CB 1802 |  v |  v |
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) | v |   |  v  <br><br> CB 1710 | v  | v  |
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | v |   | v <br><br> CB 1710 | v  | v  |
|[Bloquear Office aplicaciones de creación de contenido ejecutable](#block-office-applications-from-creating-executable-content) | v |  |v <br><br> CB 1710 | v  | v  |
|[Bloquear Office aplicaciones para que no inyecten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes) | v |  | v <br><br> CB 1710 | v  | v  |
|[Bloquear Office de comunicación para que no cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) | v |  |v <br><br> CB 1710 | v  | v  |
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) |  |  |  |v   | v  |
|[Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) | v |   |   |  v | v  |
|[Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | v |   |v <br><br> CB 1802  | v  | v  |
|[Bloquear llamadas a la API de Win32 desde Office macros](#block-win32-api-calls-from-office-macros) | v |   | v <br><br> CB 1710  | v  |  v |
|[Usar protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | v |   | v <br><br> CB 1802 | v  | v  |
|  |  |  |  |  |  |

  (<a id="fn1">1</a>) Puede configurar reglas de reducción de superficie de ataque por regla mediante el GUID de cualquier regla.

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager (SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_SCCM ya está Microsoft Endpoint Configuration Manager._

## <a name="per-rule-alert-and-notification-details"></a>Detalles de alertas y notificaciones por regla

Las notificaciones del sistema se generan para todas las reglas en modo de bloqueo. Las reglas de cualquier otro modo no generarán notificaciones del sistema

Para las reglas con el "Estado de regla" especificado:

- Las reglas ASR con \<ASR Rule, Rule State\> combinaciones se usan para las alertas de superficie (notificaciones del sistema) en Pertahanan Microsoft untuk Titik Akhir solo para dispositivos en el nivel de bloque de nube alta. Los dispositivos que no están en el nivel de bloque de nube alta no generarán alertas para ninguna regla <ASR, las combinaciones de> reglas
- EDR alertas se generan para las reglas ASR en los estados especificados, pero solo para dispositivos en el nivel de bloque de nube alta.

| Nombre de regla: | Estado de regla: | Genera alertas en EDR? <br> (Sí&nbsp;\|&nbsp;No) | ¿Genera notificaciones del sistema? <br> (Sí&nbsp;\|&nbsp;No) |
|---|:---:|:---:|:---:|
|   |   |  _Solo para dispositivos en nivel de bloque de nube alta_ | _Solo en modo de bloqueo_ |
|[Bloquear el uso indebido de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) |   | N  | v |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | Bloquear  | v <br> Requiere dispositivo en el nivel de bloque de nube alta  | v <br> Requiere dispositivo en el nivel de bloque de nube alta |
|[Bloquear todas Office aplicaciones de creación de procesos secundarios](#block-all-office-applications-from-creating-child-processes) |   | N | v |
|[Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) |   | N | v |
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) |   | v <br> Requiere dispositivo en el nivel de bloque de nube alta | v <br> Requiere dispositivo en el nivel de bloque de nube alta |
|[Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) |   | N | v |
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> Requiere dispositivo en el nivel de bloque de nube alta  | N \| Y <br> Requiere dispositivo en el nivel de bloque de nube alta |
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Bloquear | v <br> Requiere dispositivo en el nivel de bloque de nube alta  | v <br> Requiere dispositivo en el nivel de bloque de nube alta |
|[Bloquear Office aplicaciones de creación de contenido ejecutable](#block-office-applications-from-creating-executable-content) |   | N | v |
|[Bloquear Office aplicaciones para que no inyecten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes)  |   | N | v |
|[Bloquear Office de comunicación para que no cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) |  |  N | v |
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> Requiere dispositivo en el nivel de bloque de nube alta  | N \| Y <br> Requiere dispositivo en el nivel de bloque de nube alta |
|[Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) |   | N | v |
|[Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> Requiere dispositivo en el nivel de bloque de nube alta  | N \| Y <br> Requiere dispositivo en el nivel de bloque de nube alta |
|[Bloquear llamadas a la API de Win32 desde Office macros](#block-win32-api-calls-from-office-macros) |   | N | v |
|[Usar protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> Requiere dispositivo en el nivel de bloque de nube alta  | N \| Y <br> Requiere dispositivo en el nivel de bloque de nube alta |
|   |   |   |   |
  
## <a name="asr-rules-and-guids-matrix"></a>Reglas ASR y matriz de GUID

| Nombre de la regla | GUID de regla |
|:-----|:-----|
| Bloquear el uso indebido de controladores firmados vulnerables explotados | 56a863a9-875e-4185-98a7-b882c64b5ce5 |
| Impedir que Adobe Reader cree procesos secundarios | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c |
| Bloquear todas Office aplicaciones de creación de procesos secundarios | d4f940ab-401b-4efc-aadc-ad5f3c50688a |
| Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe) | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 |
| Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web | be9ba2d9-53ea-4cdc-84e5-9b1eeee46550 |
| Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza | 01443614-cd74-433a-b99e-2ecdc07bfc25 |
| Bloquear la ejecución de scripts potencialmente ofuscados | 5beb7efe-fd9a-4556-801d-275e5ffc04cc |
| Impedir que JavaScript o VBScript inicien contenido ejecutable descargado | d3e037e1-3eb8-44c8-a917-57927947596d |
| Bloquear Office aplicaciones de creación de contenido ejecutable | 3b576869-a4ec-4529-8536-b80a7769e899 |
| Bloquear Office aplicaciones para que no inyecten código en otros procesos | 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84 |
| Bloquear Office de comunicación para que no cree procesos secundarios | 26190899-1602-49e8-8b27-eb1d0a1ce869 |
| Bloquear la persistencia a través de la suscripción de eventos WMI <br>* No se admiten exclusiones de archivos y carpetas. | e6db77e5-3df2-4cf1-b95a-636979351e5b |
| Bloquear creaciones de proceso que se originen en comandos PSExec y WMI | d1e49aac-8f56-4280-b9ba-993a6d77406c |
| Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4 |
| Bloquear llamadas a la API de Win32 desde Office macros | 92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b |
| Usar protección avanzada contra ransomware | c1db55ab-c21a-4637-bb3f-a12568109d35 |

## <a name="asr-rule-modes"></a>Modos de regla ASR

- **No configurado** o **Deshabilitado**: este es el estado en el que la regla ASR no se ha habilitado o se ha deshabilitado. El código de este estado = 0.
- **Bloque**: este es el estado en el que está habilitada la regla ASR. El código de este estado es 1.
- **Auditoría**: este es el estado en el que se evalúa la regla ASR por su comportamiento impactivo hacia la organización o el entorno en el que se implementa. El código de este estado es 2.
- **Advertir** Este es el estado en el que la regla ASR está habilitada y presenta una notificación al usuario final, pero permite al usuario final omitir el bloque. El código de este estado es 6.

_El modo de_ advertencia es un tipo de modo de bloqueo que alerta a los usuarios sobre acciones potencialmente arriesgadas. Los usuarios pueden elegir omitir el mensaje de advertencia de bloqueo y permitir la acción subyacente. Los usuarios pueden seleccionar **Aceptar** para aplicar el bloque o seleccionar la opción de **omisión - Desbloquear** - a través de la notificación del sistema emergente del usuario final que se genera en el momento del bloque. Después de desbloquear la advertencia, la operación se permite hasta la próxima vez que se produzca el mensaje de advertencia, momento en el que el usuario final tendrá que volver a realizar la acción.

Si se hace clic en el botón permitir, el bloque se suprimirá durante 24 horas. Después de 24 horas, el usuario final tendrá que volver a permitir el bloque. El modo de advertencia para reglas ASR solo es compatible con dispositivos RS5+ (1809+). Si la omisión se asigna a reglas ASR en dispositivos con versiones anteriores, la regla estará en modo bloqueado.

También puede establecer una regla en modo de advertencia a través de PowerShell simplemente especificando el AttackSurfaceReductionRules_Actions como "Warn". Por ejemplo:

```powershell
-command "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Warn"} 
```

## <a name="per-rule-descriptions"></a>Descripciones por regla

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Bloquear el uso indebido de controladores firmados vulnerables explotados

Esta regla impide que una aplicación escriba un controlador firmado vulnerable en el disco. Las aplicaciones locales que \- tienen privilegios suficientes para obtener acceso al kernel pueden aprovechar los controladores _firmados vulnerables_ \- en el medio natural. Los controladores firmados vulnerables permiten a los atacantes deshabilitar o eludir las soluciones de seguridad, lo que finalmente provoca un riesgo para el sistema.

La **regla Bloquear el uso indebido de controladores firmados vulnerables** no bloquea la carga de un controlador que ya existe en el sistema.

> [!NOTE]
>
> Puede configurar esta regla con MEM OMA-URI. Consulte [MEM OMA-URI](enable-attack-surface-reduction.md#mem) para configurar reglas personalizadas.
>
> También puede configurar esta regla con [PowerShell](enable-attack-surface-reduction.md#powershell).
>
> Para que se examine un controlador, use este sitio web para [enviar un controlador para su análisis](https://www.microsoft.com/en-us/wdsi/driversubmission).

<!--The above link is the 'only link' that exists for having drivers examined. The 'en-us' component is required to make the link work. Any alterations to this link will result in a 404.
-->

Intune nombre: `Block abuse of exploited vulnerable signed drivers` (aún no disponible)

Configuration Manager: Aún no disponible
  
GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

<!-- Hide this intro with no subsequent list items
Advanced hunting action type:
-->

<!-- 
Dependencies: none provided by engineering
-->

### <a name="block-adobe-reader-from-creating-child-processes"></a>Impedir que Adobe Reader cree procesos secundarios

Esta regla evita los ataques al bloquear Adobe Reader para crear procesos.

A través de la ingeniería social o vulnerabilidades, el malware puede descargar e iniciar cargas y salir de Adobe Reader. Al impedir que Adobe Reader genere procesos secundarios, se impide que el malware que intenta usarlo como vector se propague.

Intune nombre:`Process creation from Adobe Reader (beta)`

Configuration Manager: Aún no disponible

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

Tipo de acción de búsqueda avanzada:

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

Dependencias: MDAV

### <a name="block-all-office-applications-from-creating-child-processes"></a>Bloquear todas Office aplicaciones de creación de procesos secundarios

Esta regla impide que Office aplicaciones creen procesos secundarios. Office aplicaciones incluyen Word, Excel, PowerPoint, OneNote y Access.

Crear procesos secundarios malintencionados es una estrategia de malware común. El malware que abusa Office como vector a menudo ejecuta macros de VBA y aprovecha el código para descargar e intentar ejecutar más cargas. Sin embargo, algunas aplicaciones legítimas de línea de negocio también pueden generar procesos secundarios con fines benignos; como generar un símbolo del sistema o usar PowerShell para configurar la configuración del Registro.

Intune nombre:`Office apps launching child processes`

Configuration Manager nombre:`Block Office application from creating child processes`

GUID: `d4f940ab-401b-4efc-aadc-ad5f3c50688a`

Tipo de acción de búsqueda avanzada:

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

Dependencias: MDAV

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local

Esta regla ayuda a evitar el robo de credenciales bloqueando el Servicio de subsistema de autoridad de seguridad local (LSASS).

LSASS autentica a los usuarios que inician sesión en un Windows equipo. Credential Guard de Microsoft Defender en Windows normalmente impide los intentos de extraer credenciales de LSASS. Sin embargo, algunas organizaciones no pueden habilitar Credential Guard en todos sus equipos debido a problemas de compatibilidad con controladores de tarjeta inteligente personalizados u otros programas que se cargan en la Autoridad de seguridad local (LSA). En estos casos, los atacantes pueden usar herramientas de pirateo como Mimikatz para raspar contraseñas de texto no cifrado y hash NTLM de LSASS.

> [!NOTE]
> En algunas aplicaciones, el código enumera todos los procesos en ejecución e intenta abrirlos con permisos exhaustivos. Esta regla deniega la acción de apertura del proceso de la aplicación y registra los detalles en el registro de eventos de seguridad. Esta regla puede generar mucho ruido. Si tienes una aplicación que simplemente enumera LSASS, pero no tiene ningún impacto real en la funcionalidad, no es necesario agregarla a la lista de exclusión. Por sí mismo, esta entrada de registro de eventos no indica necesariamente una amenaza malintencionada.
  
> [!IMPORTANT]
> El estado predeterminado de la regla de reducción de superficie de ataque (ASR) Windows "Bloquear el robo de credenciales del subsistema de autoridad de seguridad local (lsass.exe)" cambiará de No  configurado a Configurado  y el modo predeterminado establecido en **Bloquear**. Todas las demás reglas ASR permanecerán en su estado predeterminado: **No configurado**. La lógica de filtrado adicional ya se ha incorporado en la regla para reducir las notificaciones del usuario final. Los clientes pueden configurar la regla en **los modos Auditoría**, **Advertencia** o Deshabilitado, lo que invalidará el modo predeterminado. La funcionalidad de esta regla es la misma, tanto si la regla está configurada en el modo predeterminado, como si habilita manualmente el modo de bloqueo.  

Intune nombre:`Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager nombre:`Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

Tipo de acción de búsqueda avanzada:

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

Dependencias: MDAV

### <a name="block-executable-content-from-email-client-and-webmail"></a>Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web

Esta regla bloquea el inicio de los siguientes tipos de archivo desde el correo electrónico abierto dentro de la aplicación de Microsoft Outlook, o Outlook.com y otros proveedores de correo web populares:

- Archivos ejecutables (como .exe, .dll o .scr)
- Archivos de script (como un archivo .ps de PowerShell, Visual Basic .vbs o un archivo .js JavaScript)

Intune nombre:`Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager nombre:`Block executable content from email client and webmail`

GUID: `be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

Tipo de acción de búsqueda avanzada:

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

Dependencias: MDAV

> [!NOTE]
> La regla **Bloquear contenido ejecutable del cliente de correo electrónico y el correo web** tiene las siguientes descripciones alternativas, según la aplicación que use:
>
> - Intune (perfiles de configuración): la ejecución de contenido ejecutable (exe, dll, ps, js, vbs, etc.) se ha eliminado del correo electrónico (cliente de correo web o correo) (sin excepciones).
> - Endpoint Manager: bloquear la descarga de contenido ejecutable de clientes de correo electrónico y correo web.
> - directiva de grupo: bloquear el contenido ejecutable del cliente de correo electrónico y el correo web.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza

Esta regla bloquea el inicio de archivos ejecutables, como .exe, .dll o .scr. Por lo tanto, iniciar archivos ejecutables desconocidos o no de confianza puede ser arriesgado, ya que es posible que no esté claro inicialmente si los archivos son malintencionados.

> [!IMPORTANT]
> Debe habilitar [la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) para usar esta regla.
>
> La regla Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia **, antigüedad** o lista de confianza con GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` es propiedad de Microsoft y los administradores no los especifican. Esta regla usa la protección entregada en la nube para actualizar su lista de confianza con regularidad.
>
> Puede especificar archivos o carpetas individuales (con rutas de carpeta o nombres de recursos completos), pero no puede especificar a qué reglas o exclusiones se aplican.

Intune nombre:`Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager nombre:`Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

Tipo de acción de búsqueda avanzada:

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

Dependencias: MDAV, Cloud Protection

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Bloquear la ejecución de scripts potencialmente ofuscados

Esta regla detecta propiedades sospechosas dentro de un script ofuscado.

La ofuscación de scripts es una técnica común que usan tanto los autores de malware como las aplicaciones legítimas para ocultar la propiedad intelectual o disminuir los tiempos de carga de scripts. Los autores de malware también usan la ofuscación para hacer que el código malintencionado sea más difícil de leer, lo que evita el escrutinio cercano por parte de los humanos y el software de seguridad.

Intune nombre:`Obfuscated js/vbs/ps/macro code`

Configuration Manager nombre:`Block execution of potentially obfuscated scripts`

GUID: `5beb7efe-fd9a-4556-801d-275e5ffc04cc`

Tipo de acción de búsqueda avanzada:

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

Dependencias: MDAV, AMSI

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Impedir que JavaScript o VBScript inicien contenido ejecutable descargado

Esta regla impide que los scripts inicien contenido descargado potencialmente malintencionado. El malware escrito en JavaScript o VBScript a menudo actúa como descargador para capturar e iniciar otro malware desde Internet.

Aunque no son comunes, las aplicaciones de línea de negocio a veces usan scripts para descargar e iniciar instaladores.

Intune nombre:`js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager nombre:`Block JavaScript or VBScript from launching downloaded executable content`

GUID: `d3e037e1-3eb8-44c8-a917-57927947596d`

Tipo de acción de búsqueda avanzada:

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

Dependencias: MDAV, AMSI

### <a name="block-office-applications-from-creating-executable-content"></a>Bloquear Office aplicaciones de creación de contenido ejecutable

Esta regla impide que Office aplicaciones, incluidas Word, Excel y PowerPoint, creen contenido ejecutable potencialmente malintencionado, al bloquear que el código malintencionado se escriba en el disco.

El malware que abusa Office como vector puede intentar salir de Office y guardar componentes malintencionados en el disco. Estos componentes malintencionados sobrevivirían a un reinicio del equipo y persistiría en el sistema. Por lo tanto, esta regla se defiende contra una técnica de persistencia común.

Intune nombre:`Office apps/macros creating executable content`

Nombre SCCM: `Block Office applications from creating executable content`

GUID: `3b576869-a4ec-4529-8536-b80a7769e899`

Tipo de acción de búsqueda avanzada:

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

Dependencias: MDAV, RPC

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Bloquear Office aplicaciones para que no inyecten código en otros procesos

Esta regla bloquea los intentos de inserción de código Office aplicaciones en otros procesos.

Los atacantes pueden intentar usar Office aplicaciones para migrar código malintencionado a otros procesos mediante la inyección de código, por lo que el código puede enmascararse como un proceso limpio.

No hay propósitos empresariales legítimos conocidos para usar la inyección de código.

Esta regla se aplica a Word, Excel y PowerPoint.

Intune nombre:`Office apps injecting code into other processes (no exceptions)`

Configuration Manager nombre:`Block Office applications from injecting code into other processes`

GUID: `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

Tipo de acción de búsqueda avanzada:

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

Dependencias: MDAV

### <a name="block-office-communication-application-from-creating-child-processes"></a>Bloquear Office de comunicación para que no cree procesos secundarios

Esta regla impide que Outlook procesos secundarios, a la vez que permite funciones Outlook legítimas.

Esta regla protege contra los ataques de ingeniería social e impide que el código de explotación abuse de vulnerabilidades en Outlook. También protege contra las Outlook y las vulnerabilidades de formulario [que los atacantes](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) pueden usar cuando las credenciales de un usuario están en peligro.

> [!NOTE]
> Esta regla bloquea las sugerencias de directiva DLP y las sugerencias de herramientas en Outlook. Esta regla solo se aplica Outlook y Outlook.com.

Intune nombre:`Process creation from Office communication products (beta)`

Configuration Manager: No disponible

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

Tipo de acción de búsqueda avanzada:

- AsrOfficeCommAppChildProcessAudited
- AsrOfficeCommAppChildProcessBlocked

Dependencias: MDAV

### <a name="block-persistence-through-wmi-event-subscription"></a>Bloquear la persistencia a través de la suscripción de eventos WMI

Esta regla impide que el malware abuse de WMI para lograr persistencia en un dispositivo.

> [!IMPORTANT]
> Las exclusiones de archivos y carpetas no se aplican a esta regla de reducción de superficie de ataque.

Las amenazas sin archivo emplean varias tácticas para permanecer ocultas, evitar ser detectadas en el sistema de archivos y obtener el control de la ejecución periódica. Algunas amenazas pueden abusar del repositorio WMI y el modelo de eventos para permanecer ocultas.

Intune: No disponible

Configuration Manager: No disponible

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

Tipo de acción de búsqueda avanzada:

- AsrPersistenceThroughWmiAudited
- AsrPersistenceThroughWmiBlocked

Dependencias: MDAV, RPC

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Bloquear creaciones de proceso que se originen en comandos PSExec y WMI

Esta regla bloquea la ejecución de los procesos [creados a través de PsExec](/sysinternals/downloads/psexec) [y WMI](/windows/win32/wmisdk/about-wmi) . Tanto PsExec como WMI pueden ejecutar código de forma remota, por lo que existe el riesgo de que el malware abuse de esta funcionalidad con fines de comando y control, o de propagar una infección a través de la red de una organización.

> [!WARNING]
> Solo usa esta regla si estás administrando tus dispositivos [con](/intune) Intune u otra solución MDM. Esta regla es incompatible con la administración [a través de Microsoft Endpoint Configuration Manager](/configmgr) porque esta regla bloquea los comandos WMI que el Configuration Manager usa para funcionar correctamente.

Intune nombre:`Process creation from PSExec and WMI commands`

Configuration Manager: No aplicable

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

Tipo de acción de búsqueda avanzada:

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

Dependencias: MDAV

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB

Con esta regla, los administradores pueden impedir que los archivos ejecutables sin signo o que no son de confianza se ejecuten desde unidades extraíbles USB, incluidas las tarjetas SD. Los tipos de archivo bloqueados incluyen archivos ejecutables (como .exe, .dll o .scr)

Intune nombre:`Untrusted and unsigned processes that run from USB`

Configuration Manager nombre:`Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

Tipo de acción de búsqueda avanzada:

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

Dependencias: MDAV

### <a name="block-win32-api-calls-from-office-macros"></a>Bloquear llamadas a la API de Win32 desde Office macros

Esta regla impide que las macros de VBA llamen a las API de Win32.

Office VBA habilita las llamadas a la API de Win32. El malware puede abusar de esta funcionalidad, como llamar a las [API de Win32 para iniciar el código de shell malintencionado](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) sin escribir nada directamente en el disco. La mayoría de las organizaciones no dependen de la capacidad de llamar a las API de Win32 en su funcionamiento diario, incluso si usan macros de otras maneras.

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

Dependencias: MDAV, AMSI

### <a name="use-advanced-protection-against-ransomware"></a>Usar protección avanzada contra ransomware

Esta regla proporciona una capa adicional de protección contra ransomware. Usa heurística de cliente y nube para determinar si un archivo se parece a ransomware. Esta regla no bloquea los archivos que tienen una o varias de las siguientes características:

- Ya se ha encontrado que el archivo no es compartido en la nube de Microsoft.
- El archivo es un archivo firmado válido.
- El archivo es lo suficientemente frecuente como para no considerarse ransomware.

La regla tiende a errar en el lado de la precaución para evitar ransomware.

> [!NOTE]
> Debe habilitar [la protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) para usar esta regla.

Intune nombre:`Advanced ransomware protection`

Configuration Manager nombre:`Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

Tipo de acción de búsqueda avanzada:

- AsrRansomwareAudited
- AsrRansomwareBlocked

Dependencias: MDAV, Cloud Protection
