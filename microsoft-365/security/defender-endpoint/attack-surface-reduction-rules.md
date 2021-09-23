---
title: Reglas de reducción de la superficie expuesta a ataques
description: Enumera detalles sobre las reglas de reducción de superficie de ataque por regla.
keywords: Reglas de reducción de superficie de ataque, ASR, reglas asr, hips, sistema de prevención de intrusiones de host, reglas de protección, reglas antiexploit, antiexploit, reglas de vulnerabilidad, reglas de prevención de infecciones, Microsoft Defender para endpoint, configurar reglas ASR, descripción de regla ASR
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 5fdabb81541de9cec5b35641d25c6c10098015ca
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490146"
---
# <a name="attack-surface-reduction-rules"></a>Reglas de reducción de la superficie expuesta a ataques

En este artículo se proporciona información sobre las reglas de reducción de ataques:

- [Versiones de sistema operativo compatibles](#supported-operating-systems)
- [Sistemas de administración de configuración compatibles](#supported-configuration-management-systems)
- [Descripciones por regla](#per-rule-descriptions)
  - Descripciones de reglas
  - GUID
  - Nombres de reglas del sistema de administración de configuración

## <a name="supported-operating-systems"></a>Sistemas operativos compatibles 

En la tabla siguiente se enumeran las reglas de reducción de superficie de ataque en orden alfabético. Una marca de verificación indica que la regla es compatible con el sistema operativo enumerado en esa columna.

> [!Note]
>
> - A menos que se indique lo contrario, la compilación mínima Windows 10 es la &nbsp; versión 1709 (RS3, compilación 16299) o posterior; la compilación mínima de Windows Server es &nbsp; la versión 1809 o posterior.
>
> - \* Todas las reglas admiten exclusiones de archivos y carpetas, a menos que se indique lo contrario.

|Nombre de regla|&nbsp;Windows 10|&nbsp;Windows Server 2019|&nbsp;Windows Servidor|&nbsp;Windows Server 2016|&nbsp;Windows Server 2012 R2|
|---|:---:|:---:|:---:|:---:|:---:|
|[Bloquear el uso indebido de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) | v | v | Versión Y 1803 (canal semianual) o posterior |  |  |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | Versión Y 1809 o posterior | v | v  <br><br> |  |  |
|[Bloquear todas Office aplicaciones de creación de procesos secundarios](#block-all-office-applications-from-creating-child-processes) | v | v | v <br><br> |  |  |
|[Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Versión Y 1803 o posterior | v <br><br> | v <br><br> |  |  |
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) | v | v <br><br> | v <br><br> |  |  |
|[Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Versión Y 1803 o posterior | v <br><br> | v <br><br> |  |  |
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) | v | v <br><br> | v <br><br> |  |  |
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | v | v <br><br> | v <br><br> |  |  |
|[Bloquear Office aplicaciones de creación de contenido ejecutable](#block-office-applications-from-creating-executable-content) | v | v <br><br> | v <br><br> |  |  |
|[Bloquear Office aplicaciones para que no inyecten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes)  | v | v <br><br> | v <br><br> |  |  |
|[Bloquear Office de comunicación para que no cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) | v | v <br><br> | v <br><br> |  |  |
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) <br><br> \*_No se admiten exclusiones de archivos y carpetas._ | Versión Y 1903 (compilación 18362) o posterior| v | v <br><br> versión 1903 (compilación 18362) o posterior |  |  |
|[Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) | Versión Y 1803 o posterior | v <br><br> | v <br><br>  |  |  |
|[Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | v | v <br><br> | v <br><br> |  |  |
|[Bloquear llamadas a la API de Win32 desde Office macros](#block-win32-api-calls-from-office-macros) | v | v <br><br> | v <br><br> |  |  |
|[Usar protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | Versión Y 1803 o posterior | v <br><br> | v <br><br> |  |  |
| **Nombre de la regla** |  **&nbsp;Windows 10** | **&nbsp;Windows Server 2019** | **&nbsp;Windows Servidor** | **&nbsp;Windows Server 2016** | **&nbsp;Windows Server 2012 R2** |

## <a name="supported-configuration-management-systems"></a>Sistemas de administración de configuración compatibles

Los vínculos a información sobre las versiones del sistema de administración de configuración a las que se hace referencia en esta tabla se enumeran debajo de esta tabla.

|Nombre de regla | Intune | Microsoft Endpoint Manager |Microsoft Endpoint Configuration Manager |Directiva de <sup> grupo [[1](#fn1)]<sup></sup> | PowerShell <sup> [[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|:---:|
|[Bloquear el uso indebido de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers) | ![Soporte técnico.](images/checkmark.png) <br><br>  |  ![compatible](images/checkmark.png) <br><br> MEM OMA-URI |   | ![Soporte técnico.](images/checkmark.png) <br><br>  |  ![compatible](images/checkmark.png) <br><br> |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes) | ![Soporte técnico.](images/checkmark.png) |   | ![compatible](images/checkmark.png) | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear todas Office aplicaciones de creación de procesos secundarios](#block-all-office-applications-from-creating-child-processes) | ![Soporte técnico.](images/checkmark.png) |   | ![compatible](images/checkmark.png) <br><br> CB 1710 | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | ![Soporte técnico.](images/checkmark.png)  |   |  ![compatible](images/checkmark.png) <br><br> CB 1802 | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail) | ![Soporte técnico.](images/checkmark.png) |  | ![compatible](images/checkmark.png) <br><br> CB 1710 | ![compatible](images/checkmark.png) | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | ![Soporte técnico.](images/checkmark.png) |   | ![compatible](images/checkmark.png) <br><br> CB 1802 |  ![Soporte técnico.](images/checkmark.png) <br><br> |  ![Soporte técnico.](images/checkmark.png) <br><br> |
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) | ![Soporte técnico.](images/checkmark.png) |   |  ![compatible](images/checkmark.png)  <br><br> CB 1710 | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | ![Soporte técnico.](images/checkmark.png) |   |  ![compatible](images/checkmark.png) <br><br> CB 1710 | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear Office aplicaciones de creación de contenido ejecutable](#block-office-applications-from-creating-executable-content) | ![Soporte técnico.](images/checkmark.png) <br><br> |  | ![compatible](images/checkmark.png) <br><br> CB 1710 <br><br> | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear Office aplicaciones para que no inyecten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes) | ![Soporte técnico.](images/checkmark.png) |  |  ![compatible](images/checkmark.png) <br><br> CB 1710 | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear Office de comunicación para que no cree procesos secundarios](#block-office-communication-application-from-creating-child-processes) | ![Soporte técnico.](images/checkmark.png) |  | ![compatible](images/checkmark.png) <br><br>  CB 1710 | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) |  |  |  |![Soporte técnico.](images/checkmark.png) <br><br>   | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) | ![compatible](images/checkmark.png) |   |   |  ![Soporte técnico.](images/checkmark.png) <br><br> | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | ![Soporte técnico.](images/checkmark.png) |   | ![compatible](images/checkmark.png) <br><br> CB 1802 <br><br> | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |
|[Bloquear llamadas a la API de Win32 desde Office macros](#block-win32-api-calls-from-office-macros) | ![Soporte técnico.](images/checkmark.png) |   | ![compatible](images/checkmark.png) <br><br> CB 1710 <br><br> | ![Soporte técnico.](images/checkmark.png) <br><br>  |  ![Soporte técnico.](images/checkmark.png) <br><br> |
|[Usar protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) | ![Soporte técnico.](images/checkmark.png) |   |  ![compatible](images/checkmark.png) <br><br>  CB 1802 | ![Soporte técnico.](images/checkmark.png) <br><br>  | ![Soporte técnico.](images/checkmark.png) <br><br>  |

  (<a id="fn1">1</a>) Puede configurar reglas de reducción de superficie de ataque por regla mediante el GUID de cualquier regla.

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager (SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_SCCM ya está Microsoft Endpoint Configuration Manager._

## <a name="per-rule-descriptions"></a>Descripciones por regla

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Bloquear el uso indebido de controladores firmados vulnerables explotados

Esta regla impide que una aplicación escriba un controlador firmado vulnerable en el disco. Las aplicaciones locales que tienen privilegios suficientes para obtener acceso al kernel pueden aprovechar los controladores \- _firmados vulnerables_ en \- el medio natural. Los controladores firmados vulnerables permiten a los atacantes deshabilitar o eludir las soluciones de seguridad, lo que finalmente provoca un riesgo para el sistema.

La regla Bloquear el uso indebido de controladores **firmados vulnerables** no bloquea la carga de un controlador que ya existe en el sistema.

> [!NOTE]
>
> Puede configurar esta regla con MEM OMA-URI. Consulte [MEM OMA-URI](enable-attack-surface-reduction.md#mem) para configurar reglas personalizadas.
>
> También puede configurar esta regla con [PowerShell](enable-attack-surface-reduction.md#powershell).
>
> Para que se examine un controlador, use este sitio web para [enviar un controlador para su análisis.](https://www.microsoft.com/wdsi/driversubmission)

Nombre de Intune: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

<!-- Hide this intro with no subsequent list items
Advanced hunting action type:
-->

### <a name="block-adobe-reader-from-creating-child-processes"></a>Impedir que Adobe Reader cree procesos secundarios

Esta regla evita los ataques al bloquear Adobe Reader para crear procesos.

A través de la ingeniería social o vulnerabilidades, el malware puede descargar e iniciar cargas y salir de Adobe Reader. Al impedir que Adobe Reader genere procesos secundarios, se impide que el malware que intenta usarlo como vector se propague.

Nombre de Intune: `Process creation from Adobe Reader (beta)`

Nombre de Configuration Manager: Aún no disponible

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

Tipo de acción de búsqueda avanzada:

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

### <a name="block-all-office-applications-from-creating-child-processes"></a>Bloquear todas Office aplicaciones de creación de procesos secundarios

Esta regla impide que Office aplicaciones creen procesos secundarios. Office aplicaciones incluyen Word, Excel, PowerPoint, OneNote y Access.

Crear procesos secundarios malintencionados es una estrategia de malware común. El malware que abusa Office como vector a menudo ejecuta macros de VBA y aprovecha el código para descargar e intentar ejecutar más cargas. Sin embargo, algunas aplicaciones legítimas de línea de negocio también pueden generar procesos secundarios con fines benignos; como generar un símbolo del sistema o usar PowerShell para configurar la configuración del Registro.

Nombre de Intune: `Office apps launching child processes`

Nombre de Configuration Manager: `Block Office application from creating child processes`

GUID: `d4f940ab-401b-4efc-aadc-ad5f3c50688a`

Tipo de acción de búsqueda avanzada:

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local

Esta regla ayuda a evitar el robo de credenciales bloqueando el Servicio de subsistema de autoridad de seguridad local (LSASS).

LSASS autentica a los usuarios que inician sesión en un Windows equipo. Credential Guard de Microsoft Defender en Windows 10 normalmente impide los intentos de extraer credenciales de LSASS. Sin embargo, algunas organizaciones no pueden habilitar Credential Guard en todos sus equipos debido a problemas de compatibilidad con controladores de tarjeta inteligente personalizados u otros programas que se cargan en la Autoridad de seguridad local (LSA). En estos casos, los atacantes pueden usar herramientas de pirateo como Mimikatz para raspar contraseñas de texto no cifrado y hash NTLM de LSASS.

> [!NOTE]
> En algunas aplicaciones, el código enumera todos los procesos en ejecución e intenta abrirlos con permisos exhaustivos. Esta regla deniega la acción de apertura del proceso de la aplicación y registra los detalles en el registro de eventos de seguridad. Esta regla puede generar mucho ruido. Si tienes una aplicación que simplemente enumera LSASS, pero no tiene ningún impacto real en la funcionalidad, no es necesario agregarla a la lista de exclusión. Por sí mismo, esta entrada de registro de eventos no indica necesariamente una amenaza malintencionada.

Nombre de Intune: `Flag credential stealing from the Windows local security authority subsystem`

Nombre de Configuration Manager: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

Tipo de acción de búsqueda avanzada:

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

### <a name="block-executable-content-from-email-client-and-webmail"></a>Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web

Esta regla impide que los siguientes tipos de archivo se inicien desde el correo electrónico abierto dentro de la aplicación de Microsoft Outlook o Outlook.com y otros proveedores de correo web populares:

- Archivos ejecutables (como .exe, .dll o .scr)
- Archivos de script (como un archivo .ps de PowerShell, Visual Basic .vbs o un archivo .js JavaScript)

Nombre de Intune: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager nombre:`Block executable content from email client and webmail`

GUID: `be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

Tipo de acción de búsqueda avanzada:

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

> [!NOTE]
> La regla **Bloquear contenido ejecutable del** cliente de correo electrónico y el correo web tiene las siguientes descripciones alternativas, según la aplicación que use:
>
> - Intune (perfiles de configuración): la ejecución de contenido ejecutable (exe, dll, ps, js, vbs, etc.) se ha eliminado del correo electrónico (cliente de correo web o correo) (sin excepciones).
> - Endpoint Manager: bloquear la descarga de contenido ejecutable de clientes de correo electrónico y correo web.
> - Directiva de grupo: bloquear el contenido ejecutable del cliente de correo electrónico y el correo web.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza

Esta regla bloquea el inicio de archivos ejecutables, como .exe, .dll o .scr, a menos que se cumple cualquiera de las siguientes condiciones:

- Prevalencia: los archivos ejecutables se encuentran en más de 1.000 puntos de conexión
- Edad: los archivos ejecutables se publicaron hace más de 24 horas
- Ubicación: los archivos ejecutables se incluyen en una lista de confianza o una lista de exclusión

El inicio de archivos ejecutables desconocidos o no de confianza puede ser arriesgado, ya que podría no estar claro inicialmente si los archivos son malintencionados.

> [!IMPORTANT]
> Debe habilitar [la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) para usar esta regla.
>
> La regla Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de **prevalencia, antigüedad** o lista de confianza con GUID es propiedad de Microsoft y los administradores no `01443614-cd74-433a-b99e-2ecdc07bfc25` los especifican. Esta regla usa la protección entregada en la nube para actualizar su lista de confianza con regularidad.
>
> Puede especificar archivos o carpetas individuales (con rutas de carpeta o nombres de recursos completos), pero no puede especificar a qué reglas o exclusiones se aplican.

Nombre de Intune: `Executables that don't meet a prevalence, age, or trusted list criteria`

Nombre de Configuration Manager: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

Tipo de acción de búsqueda avanzada:

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Bloquear la ejecución de scripts potencialmente ofuscados

Esta regla detecta propiedades sospechosas dentro de un script ofuscado.

La ofuscación de scripts es una técnica común que usan tanto los autores de malware como las aplicaciones legítimas para ocultar la propiedad intelectual o disminuir los tiempos de carga de scripts. Los autores de malware también usan la ofuscación para hacer que el código malintencionado sea más difícil de leer, lo que evita el escrutinio cercano por parte de los humanos y el software de seguridad.

Nombre de Intune: `Obfuscated js/vbs/ps/macro code`

Nombre de Configuration Manager: `Block execution of potentially obfuscated scripts`

GUID: `5beb7efe-fd9a-4556-801d-275e5ffc04cc`

Tipo de acción de búsqueda avanzada:

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Impedir que JavaScript o VBScript inicien contenido ejecutable descargado

Esta regla impide que los scripts inicien contenido descargado potencialmente malintencionado. El malware escrito en JavaScript o VBScript a menudo actúa como descargador para capturar e iniciar otro malware desde Internet.

Aunque no son comunes, las aplicaciones de línea de negocio a veces usan scripts para descargar e iniciar instaladores.

Nombre de Intune: `js/vbs executing payload downloaded from Internet (no exceptions)`

Nombre de Configuration Manager: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `d3e037e1-3eb8-44c8-a917-57927947596d`

Tipo de acción de búsqueda avanzada:

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

### <a name="block-office-applications-from-creating-executable-content"></a>Bloquear Office aplicaciones de creación de contenido ejecutable

Esta regla impide que Office aplicaciones, incluidas Word, Excel y PowerPoint, creen contenido ejecutable potencialmente malintencionado, al bloquear que el código malintencionado se escriba en el disco.

El malware que abusa Office como vector puede intentar salir de Office y guardar componentes malintencionados en el disco. Estos componentes malintencionados sobrevivirían a un reinicio del equipo y persistiría en el sistema. Por lo tanto, esta regla se defiende contra una técnica de persistencia común.

Nombre de Intune: `Office apps/macros creating executable content`

Nombre SCCM: `Block Office applications from creating executable content`

GUID: `3b576869-a4ec-4529-8536-b80a7769e899`

Tipo de acción de búsqueda avanzada:

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Bloquear Office aplicaciones para que no inyecten código en otros procesos

Esta regla bloquea los intentos de inyección de código Office aplicaciones en otros procesos.

Los atacantes pueden intentar usar Office aplicaciones para migrar código malintencionado a otros procesos mediante la inyección de código, por lo que el código puede enmascararse como un proceso limpio.

No hay propósitos empresariales legítimos conocidos para usar la inyección de código.

Esta regla se aplica a Word, Excel y PowerPoint.

Nombre de Intune: `Office apps injecting code into other processes (no exceptions)`

Nombre de Configuration Manager: `Block Office applications from injecting code into other processes`

GUID: `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

Tipo de acción de búsqueda avanzada:

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

### <a name="block-office-communication-application-from-creating-child-processes"></a>Bloquear Office de comunicación para que no cree procesos secundarios

Esta regla impide que Outlook procesos secundarios, a la vez que permite funciones Outlook legítimas.

Esta regla protege contra los ataques de ingeniería social e impide que el código de explotación abuse de vulnerabilidades en Outlook. También protege contra las Outlook y las vulnerabilidades de formulario [que](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) los atacantes pueden usar cuando las credenciales de un usuario están en peligro.

> [!NOTE]
> Esta regla bloquea las sugerencias de directiva DLP y las sugerencias de herramientas en Outlook. Esta regla se aplica solo Outlook y Outlook.com.

Nombre de Intune: `Process creation from Office communication products (beta)`

Nombre de Configuration Manager: No disponible

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

Tipo de acción de búsqueda avanzada:

- AsrOfficeCommAppChildProcessAudited
- AsrOfficeCommAppChildProcessBlocked

### <a name="block-persistence-through-wmi-event-subscription"></a>Bloquear la persistencia a través de la suscripción de eventos WMI

Esta regla evita que el malware abuse de WMI para lograr la persistencia en un dispositivo.

> [!IMPORTANT]
> Las exclusiones de archivos y carpetas no se aplican a esta regla de reducción de superficie de ataque.

Las amenazas sin archivos emplean varias tácticas para mantenerse ocultas, para evitar que se vean en el sistema de archivos y para obtener un control de ejecución periódico. Algunas amenazas pueden abusar del repositorio WMI y el modelo de eventos para mantenerse oculto.

Nombre de Intune: no disponible

Nombre de Configuration Manager: No disponible

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

Tipo de acción de búsqueda avanzada:

- AsrPersistenceThroughWmiAudited
- AsrPersistenceThroughWmiBlocked

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Bloquear creaciones de proceso que se originen en comandos PSExec y WMI

Esta regla bloquea la ejecución de los procesos [creados a través](/sysinternals/downloads/psexec) de PsExec [y WMI.](/windows/win32/wmisdk/about-wmi) Tanto PsExec como WMI pueden ejecutar código de forma remota, por lo que existe el riesgo de que el malware abuse de esta funcionalidad con fines de comando y control, o de propagar una infección a través de la red de una organización.

> [!WARNING]
> Solo usa esta regla si estás administrando tus dispositivos con [Intune](/intune) u otra solución MDM. Esta regla es incompatible con la administración a [Microsoft Endpoint Configuration Manager](/configmgr) porque esta regla bloquea los comandos WMI que el cliente de Configuration Manager usa para funcionar correctamente.

Nombre de Intune: `Process creation from PSExec and WMI commands`

Nombre de Configuration Manager: no aplicable

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

Tipo de acción de búsqueda avanzada:

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB

Con esta regla, los administradores pueden impedir que los archivos ejecutables sin signo o que no son de confianza se ejecuten desde unidades extraíbles USB, incluidas las tarjetas SD. Los tipos de archivo bloqueados incluyen archivos ejecutables (como .exe, .dll o .scr)

Nombre de Intune: `Untrusted and unsigned processes that run from USB`

Nombre de Configuration Manager: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

Tipo de acción de búsqueda avanzada:

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

### <a name="block-win32-api-calls-from-office-macros"></a>Bloquear llamadas a la API de Win32 desde Office macros

Esta regla impide que las macros de VBA llamen a las API de Win32.

Office VBA habilita las llamadas a la API de Win32. El malware puede abusar de esta funcionalidad, como llamar a las API de [Win32](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) para iniciar el código de shell malintencionado sin escribir nada directamente en el disco. La mayoría de las organizaciones no dependen de la capacidad de llamar a las API de Win32 en su funcionamiento diario, incluso si usan macros de otras maneras.

Sistemas operativos compatibles:

- [Windows 10, versión 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versión 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nombre de Intune: `Win32 imports from Office macro code`

Nombre de Configuration Manager: `Block Win32 API calls from Office macros`

GUID: `92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`

Tipo de acción de búsqueda avanzada:

- AsrOfficeMacroWin32ApiCallsAudited
- AsrOfficeMacroWin32ApiCallsBlocked

### <a name="use-advanced-protection-against-ransomware"></a>Usar protección avanzada contra ransomware

Esta regla proporciona una capa adicional de protección contra ransomware. Usa heurística de cliente y nube para determinar si un archivo se parece a ransomware. Esta regla no bloquea los archivos que tienen una o varias de las siguientes características:

- Ya se ha encontrado que el archivo no es compartido en la nube de Microsoft.
- El archivo es un archivo firmado válido.
- El archivo es lo suficientemente frecuente como para no considerarse ransomware.

La regla tiende a errar en el lado de la precaución para evitar ransomware.

> [!NOTE]
> Debe habilitar [la protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) para usar esta regla.

Nombre de Intune: `Advanced ransomware protection`

Nombre de Configuration Manager: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

Tipo de acción de búsqueda avanzada:

- AsrRansomwareAudited
- AsrRansomwareBlocked
