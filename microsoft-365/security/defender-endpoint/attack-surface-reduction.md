---
title: Usar reglas de reducción de superficie de ataque para evitar infecciones de malware
description: Las reglas de reducción de superficie de ataque pueden ayudar a evitar que las vulnerabilidades utilicen aplicaciones y scripts para infectar dispositivos con malware.
keywords: Reglas de reducción de superficie de ataque, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: da4b7fce66a6c51da61edd7c44216ee268c3156a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538668"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Usar reglas de reducción de superficie de ataque para evitar infecciones de malware

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>Por qué las reglas de reducción de superficie de ataque son importantes

La superficie de ataque de la organización incluye todos los lugares donde un atacante podría poner en peligro los dispositivos o redes de la organización. Reducir la superficie de ataque significa proteger los dispositivos y la red de la organización, lo que deja a los atacantes con menos formas de realizar ataques. La configuración de reglas de reducción de superficie de ataque en Microsoft Defender para endpoint puede ser útil.

Las reglas de reducción de superficie de ataque se aplican a determinados comportamientos de software, como:

- Iniciar archivos ejecutables y scripts que intenten descargar o ejecutar archivos;
- Ejecutar scripts ofuscados o sospechosos; y
- Comportamientos que las aplicaciones normalmente no inician durante el trabajo diario normal.

Estos comportamientos de software a veces se ven en aplicaciones legítimas; sin embargo, estos comportamientos a menudo se consideran riesgosos porque los atacantes suelen abusar de ellos a través del malware. Las reglas de reducción de superficie de ataque pueden restringir comportamientos riesgosos y ayudar a mantener la seguridad de la organización.

Para obtener más información sobre cómo configurar reglas de reducción de superficie de ataque, consulta [Habilitar reglas de reducción de superficie de ataque](enable-attack-surface-reduction.md).

## <a name="assess-rule-impact-before-deployment"></a>Evaluar el impacto de la regla antes de la implementación

Puedes evaluar cómo una regla de reducción de superficie de ataque puede afectar a la red abriendo la recomendación de seguridad para esa regla en [Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/#tvm).

:::image type="content" source="images/asrrecommendation.png" alt-text="Reco de seguridad para la regla de reducción de superficie de ataque":::

En el panel de detalles de recomendación, comprueba el impacto del usuario para determinar qué porcentaje de dispositivos pueden aceptar una nueva directiva que habilite la regla en modo de bloqueo sin afectar negativamente a la productividad.

## <a name="audit-mode-for-evaluation"></a>Modo auditoría para evaluación

Usa [el modo de auditoría](audit-windows-defender.md) para evaluar cómo afectarían las reglas de reducción de superficie de ataque a tu organización si estuvieran habilitadas. Ejecute primero todas las reglas en el modo de auditoría para que pueda comprender cómo afectan a las aplicaciones de línea de negocio. Muchas aplicaciones de línea de negocio se escriben con problemas de seguridad limitados y pueden realizar tareas de maneras que parezcan similares al malware. Al supervisar los datos de auditoría y [agregar exclusiones](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) para las aplicaciones necesarias, puedes implementar reglas de reducción de superficie de ataque sin reducir la productividad.

## <a name="warn-mode-for-users"></a>Modo de advertencia para usuarios

(**¡NUEVO!)** Antes de las capacidades del modo de advertencia, las reglas de reducción de superficie de ataque habilitadas podrían establecerse en modo auditoría o modo de bloqueo. Con el nuevo modo de advertencia, siempre que una regla de reducción de superficie de ataque bloquee el contenido, los usuarios verán un cuadro de diálogo que indica que el contenido está bloqueado. El cuadro de diálogo también ofrece al usuario una opción para desbloquear el contenido. A continuación, el usuario puede reintentar su acción y se completa la operación. Cuando un usuario desbloquea el contenido, el contenido permanece desbloqueado durante 24 horas y, a continuación, el bloqueo se reanuda.

El modo de advertencia ayuda a la organización a tener reglas de reducción de superficie de ataques sin impedir que los usuarios accedan al contenido que necesitan para realizar sus tareas.

### <a name="requirements-for-warn-mode-to-work"></a>Requisitos para que funcione el modo de advertencia

El modo de advertencia se admite en dispositivos que ejecutan las siguientes versiones de Windows:

- [Windows 10 versión 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) o posterior
- [Windows server, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) o posterior

Antivirus de Microsoft Defender debe ejecutarse con protección en tiempo real en [modo activo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).

Además, asegúrate de [que Antivirus de Microsoft Defender y las actualizaciones de antimalware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) estén instaladas.

- Requisito mínimo de versión de plataforma: `4.18.2008.9`
- Requisito mínimo de versión del motor: `1.1.17400.5`

Para obtener más información y obtener las actualizaciones, vea [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).

### <a name="cases-where-warn-mode-is-not-supported"></a>Casos en los que no se admite el modo de advertencia

El modo de advertencia no es compatible con tres reglas de reducción de superficie de ataque al configurarlas en Microsoft Endpoint Manager. (Si usas la directiva de grupo para configurar las reglas de reducción de superficie de ataque, se admite el modo de advertencia). Las tres reglas que no admiten el modo de advertencia al configurarlas en Microsoft Endpoint Manager son las siguientes:

- [Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID) `d3e037e1-3eb8-44c8-a917-57927947596d`
- [Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription) (GUID) `e6db77e5-3df2-4cf1-b95a-636979351e5b`
- [Usar protección avanzada contra ransomware](#use-advanced-protection-against-ransomware) (GUID) `c1db55ab-c21a-4637-bb3f-a12568109d35`

Además, el modo de advertencia no se admite en dispositivos que ejecutan versiones anteriores de Windows. En esos casos, las reglas de reducción de superficie de ataque configuradas para ejecutarse en modo de advertencia se ejecutarán en modo de bloqueo.

## <a name="notifications-and-alerts"></a>Notificaciones y alertas

Cada vez que se desencadena una regla de reducción de superficie de ataque, se muestra una notificación en el dispositivo. Puede personalizar [la notificación con los](customize-attack-surface-reduction.md#customize-the-notification) detalles de su empresa y la información de contacto.

Además, cuando se desencadenan determinadas reglas de reducción de superficie de ataque, se generan alertas.

Las notificaciones y las alertas que se generan se pueden ver en el Centro de seguridad de Microsoft Defender ( ) y en el centro de seguridad de Microsoft 365 [https://securitycenter.windows.com](https://securitycenter.windows.com) ( [https://security.microsoft.com](https://security.microsoft.com) ).

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Eventos avanzados de reducción de superficie de búsqueda y ataque

Puedes usar la búsqueda avanzada para ver eventos de reducción de superficie de ataque. Para simplificar el volumen de datos entrantes, solo se pueden ver procesos únicos para cada hora con búsqueda avanzada. La hora de un evento de reducción de superficie de ataque es la primera vez que se ve ese evento dentro de la hora.

Por ejemplo, supongamos que se produce un evento de reducción de superficie de ataque en 10 dispositivos durante la hora de las 2:00 p.m. Supongamos que el primer evento se produjo a las 2:15 y el último a las 2:45. Con la búsqueda avanzada, verás una instancia de ese evento (aunque realmente se produjo en 10 dispositivos) y su marca de tiempo será las 2:15 p.m.

Para obtener más información acerca de la búsqueda avanzada, vea [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Características de reducción de superficie de ataque en Windows versiones

Puedes establecer reglas de reducción de superficie de ataque para dispositivos que ejecutan cualquiera de las siguientes ediciones y versiones de Windows:

- Windows 10 Pro versión [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise, versión [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows Servidor, [versión 1803 (canal semianual)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Aunque las reglas de reducción de superficie de ataque no requieren una licencia [Windows E5,](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses)si tienes Windows E5, obtienes capacidades de administración avanzadas. Estas funcionalidades disponibles solo en Windows E5 incluyen supervisión, análisis y flujos de trabajo disponibles en [Defender para](microsoft-defender-endpoint.md)endpoint, así como capacidades de informes y configuración en el centro de seguridad de [Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center) Estas funcionalidades avanzadas no están disponibles con una licencia Windows Professional o Windows E3; sin embargo, si tienes esas licencias, puedes usar el Visor de eventos y los Antivirus de Microsoft Defender para revisar los eventos de la regla de reducción de superficie de ataque.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a>Revisar los eventos de reducción de superficie de ataque en el Centro de seguridad de Microsoft Defender

Defender for Endpoint proporciona informes detallados para eventos y bloques como parte de escenarios de investigación de alertas.

Puede consultar los datos del extremo de Defender mediante la [búsqueda avanzada](advanced-hunting-query-language.md). Si estás ejecutando el modo [de auditoría,](audit-windows-defender.md)puedes usar la búsqueda avanzada para comprender cómo las reglas de reducción de superficie de ataque podrían afectar al entorno.

A continuación se muestra una consulta de ejemplo:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Revisar los eventos de reducción de superficie de ataque Windows visor de eventos

Puedes revisar el registro de eventos Windows para ver los eventos generados por las reglas de reducción de superficie de ataque:

1. Descargue el [paquete de evaluación](https://aka.ms/mp7z2w) y extraiga el archivo *cfa-events.xml* a una ubicación de fácil acceso en el dispositivo.
2. Escriba las palabras, *Visor de eventos*, en el menú Inicio para abrir el Windows de eventos.
3. En **Acciones,** seleccione **Importar vista personalizada...**.
4. Seleccione el archivo *cfa-events.xml* desde donde se extrajo. Como alternativa, [copie el XML directamente](event-views.md).
5. Seleccione **Aceptar**.

Puede crear una vista personalizada que filtra los eventos para mostrar solo los siguientes eventos, todos ellos relacionados con el acceso controlado a carpetas:

|Id. de evento|Descripción|
|---|---|
|5007|Evento cuando se cambia la configuración|
|1121|Evento cuando la regla se dispara en modo bloque|
|1122|Evento cuando la regla se dispara en modo auditoría|
|

La "versión del motor" que aparece para los eventos de reducción de superficie de ataque en el registro de eventos, la genera Defender for Endpoint, no el sistema operativo. Defender para endpoint está integrado con Windows 10, por lo que esta característica funciona en todos los dispositivos Windows 10 instalados.

## <a name="attack-surface-reduction-rules"></a>Reglas de reducción de la superficie expuesta a ataques

En la tabla y subsecciones siguientes se describe cada una de las 15 reglas de reducción de superficie de ataque. Las reglas de reducción de superficie de ataque se enumeran en orden alfabético, por nombre de regla.

Si está configurando reglas de reducción de superficie de ataque mediante la directiva de grupo o PowerShell, necesitará los GUID. Por otra parte, si usa Microsoft Endpoint Manager o Microsoft Intune, no necesita los GUID.

|Nombre de regla|GUID|Exclusiones & carpetas de archivos|Sistema operativo mínimo compatible|
|---|:---:|---|---|
|[Bloquear el uso indebido de controladores firmados vulnerables explotados](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior) |
|[Impedir que Adobe Reader cree procesos secundarios](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear todas Office aplicaciones de creación de procesos secundarios](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear la ejecución de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear Office aplicaciones de creación de contenido ejecutable](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear Office aplicaciones para que no inyecten código en otros procesos](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear Office de comunicación para que no cree procesos secundarios](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear la persistencia a través de la suscripción de eventos WMI](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|No se admite|[Windows 10 versión 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (compilación 18362) o posterior|
|[Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Bloquear llamadas a la API de Win32 desde Office macros](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|[Usar protección avanzada contra ransomware](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|Compatible|[Windows 10 versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, compilación 16299) o posterior|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Bloquear el uso indebido de controladores firmados vulnerables explotados

Esta regla impide que una aplicación escriba un controlador con firma vulnerable en el disco. Las aplicaciones locales que tienen privilegios suficientes para obtener acceso al kernel pueden aprovechar los controladores \- _firmados vulnerables_ en \- el medio natural. Los controladores firmados vulnerables permiten a los atacantes deshabilitar o eludir las soluciones de seguridad, lo que finalmente provoca un riesgo para el sistema.

Esta regla no bloquea la carga de un controlador que ya existe en el sistema.

>[!NOTE]
>
> Esta regla se puede configurar con [OMA-URI](enable-attack-surface-reduction.md#mem) de MEM para la información de procedimientos de reglas personalizadas de MEM OMA-URI.
>
> Esta regla también se puede configurar con [PowerShell](enable-attack-surface-reduction.md#powershell).
>
> Puede usar este sitio web para [enviar un controlador para su análisis.](https://www.microsoft.com/en-us/wdsi/driversubmission)

Esta regla se admite en todas las versiones en las que se admite ASR; que es:

- [Windows 10 Pro versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- [Windows 10 Enterprise versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- [Windows server, versión 1803 (canal semianual)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Nombre de Intune: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>Impedir que Adobe Reader cree procesos secundarios

Esta regla evita los ataques al bloquear Adobe Reader para crear procesos.

A través de la ingeniería social o vulnerabilidades, el malware puede descargar e iniciar cargas y salir de Adobe Reader. Al impedir que Adobe Reader genere procesos secundarios, se impide que el malware que intenta usarlo como vector se propague.

Esta regla se introdujo en:

- [Windows 10, versión 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Nombre de Intune: `Process creation from Adobe Reader (beta)`

Nombre de Configuration Manager: Aún no disponible

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Bloquear todas Office aplicaciones de creación de procesos secundarios

Esta regla impide que Office aplicaciones creen procesos secundarios. Office aplicaciones incluyen Word, Excel, PowerPoint, OneNote y Access.

Crear procesos secundarios malintencionados es una estrategia de malware común. El malware que abusa Office como vector a menudo ejecuta macros de VBA y aprovecha el código para descargar e intentar ejecutar más cargas. Sin embargo, algunas aplicaciones legítimas de línea de negocio también pueden generar procesos secundarios con fines benignos, como generar un símbolo del sistema o usar PowerShell para configurar la configuración del Registro.

Esta regla se introdujo en:

- [Windows 10, versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Office apps launching child processes`

Nombre de Configuration Manager: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local

Esta regla ayuda a evitar el robo de credenciales, bloqueando el Servicio de subsistema de autoridad de seguridad local (LSASS).

LSASS autentica a los usuarios que inician sesión en un Windows equipo. Credential Guard de Microsoft Defender en Windows 10 normalmente impide los intentos de extraer credenciales de LSASS. Sin embargo, algunas organizaciones no pueden habilitar Credential Guard en todos sus equipos debido a problemas de compatibilidad con controladores de tarjeta inteligente personalizados u otros programas que se cargan en la Autoridad de seguridad local (LSA). En estos casos, los atacantes pueden usar herramientas de pirateo como Mimikatz para raspar contraseñas de texto no cifrado y hash NTLM de LSASS.

> [!NOTE]
> En algunas aplicaciones, el código enumera todos los procesos en ejecución e intenta abrirlos con permisos exhaustivos. Esta regla deniega la acción de apertura del proceso de la aplicación y registra los detalles en el registro de eventos de seguridad. Esta regla puede generar mucho ruido. Si tienes una aplicación que simplemente enumera LSASS, pero no tiene ningún impacto real en la funcionalidad, no es necesario agregarla a la lista de exclusión. Por sí mismo, esta entrada de registro de eventos no indica necesariamente una amenaza malintencionada.

Esta regla se introdujo en:

- [Windows 10, versión 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Flag credential stealing from the Windows local security authority subsystem`

Nombre de Configuration Manager: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web

Esta regla impide que los siguientes tipos de archivo se inicien desde el correo electrónico abierto dentro de la aplicación de Microsoft Outlook o Outlook.com y otros proveedores de correo web populares:

- Archivos ejecutables (como .exe, .dll o .scr)
- Archivos de script (como un archivo .ps de PowerShell, Visual Basic .vbs o un archivo .js JavaScript)

Esta regla se introdujo en:

- [Windows 10, versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager nombre:`Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> La regla **Bloquear contenido ejecutable del** cliente de correo electrónico y el correo web tiene las siguientes descripciones alternativas, según la aplicación que use:
>
> - Intune (perfiles de configuración): la ejecución de contenido ejecutable (exe, dll, ps, js, vbs, etc.) se ha eliminado del correo electrónico (cliente de correo web o correo) (sin excepciones).
> - Endpoint Manager: bloquear la descarga de contenido ejecutable de clientes de correo electrónico y correo web.
> - Directiva de grupo: bloquear el contenido ejecutable del cliente de correo electrónico y el correo web.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza

Esta regla bloquea el inicio de los siguientes tipos de archivo a menos que cumplan criterios de prevalencia o edad, o estén en una lista de confianza o una lista de exclusión:

- Archivos ejecutables (como .exe, .dll o .scr)

El inicio de archivos ejecutables desconocidos o no de confianza puede ser arriesgado, ya que puede que no esté claro inicialmente si los archivos son malintencionados.

> [!IMPORTANT]
> Debe habilitar [la protección entregada en la nube](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) para usar esta regla.
>
> La regla Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de **prevalencia, antigüedad** o lista de confianza con GUID es propiedad de Microsoft y los administradores no `01443614-cd74-433a-b99e-2ecdc07bfc25` los especifican. Esta regla usa la protección entregada en la nube para actualizar su lista de confianza con regularidad.
>
> Puede especificar archivos o carpetas individuales (con rutas de carpeta o nombres de recursos completos), pero no puede especificar a qué reglas o exclusiones se aplican.

Esta regla se introdujo en:

- [Windows 10, versión 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Executables that don't meet a prevalence, age, or trusted list criteria`

Nombre de Configuration Manager: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Bloquear la ejecución de scripts potencialmente ofuscados

Esta regla detecta propiedades sospechosas dentro de un script ofuscado.

La ofuscación de scripts es una técnica común que usan tanto los autores de malware como las aplicaciones legítimas para ocultar la propiedad intelectual o disminuir los tiempos de carga de scripts. Los autores de malware también usan la ofuscación para hacer que el código malintencionado sea más difícil de leer, lo que evita el escrutinio cercano por parte de los humanos y el software de seguridad.

Esta regla se introdujo en:

- [Windows 10, versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Obfuscated js/vbs/ps/macro code`

Nombre de Configuration Manager: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Impedir que JavaScript o VBScript inicien contenido ejecutable descargado

Esta regla impide que los scripts inicien contenido descargado potencialmente malintencionado. El malware escrito en JavaScript o VBScript a menudo actúa como descargador para capturar e iniciar otro malware desde Internet.

Aunque no son comunes, las aplicaciones de línea de negocio a veces usan scripts para descargar e iniciar instaladores.

Esta regla se introdujo en:

- [Windows 10, versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `js/vbs executing payload downloaded from Internet (no exceptions)`

Nombre de Configuration Manager: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Bloquear Office aplicaciones de creación de contenido ejecutable

Esta regla impide que Office aplicaciones, incluidas Word, Excel y PowerPoint, creen contenido ejecutable potencialmente malintencionado, al bloquear que el código malintencionado se escriba en el disco.

El malware que abusa Office como vector puede intentar salir de Office y guardar componentes malintencionados en el disco. Estos componentes malintencionados sobrevivirían a un reinicio del equipo y persistiría en el sistema. Por lo tanto, esta regla se defiende contra una técnica de persistencia común.

Esta regla se introdujo en:

- [Windows 10, versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM ya está Microsoft Endpoint Configuration Manager)

Nombre de Intune: `Office apps/macros creating executable content`

Nombre SCCM: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Bloquear Office aplicaciones para que no inyecten código en otros procesos

Esta regla bloquea los intentos de inyección de código Office aplicaciones en otros procesos.

Los atacantes pueden intentar usar Office aplicaciones para migrar código malintencionado a otros procesos mediante la inyección de código, por lo que el código puede enmascararse como un proceso limpio.

No hay propósitos empresariales legítimos conocidos para usar la inyección de código.

Esta regla se aplica a Word, Excel y PowerPoint.

Esta regla se introdujo en:

- [Windows 10, versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Office apps injecting code into other processes (no exceptions)`

Nombre de Configuration Manager: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Bloquear Office de comunicación para que no cree procesos secundarios

Esta regla impide que Outlook procesos secundarios, a la vez que permite funciones Outlook legítimas.

Esta regla protege contra los ataques de ingeniería social e impide que el código de explotación abuse de vulnerabilidades en Outlook. También protege contra las Outlook y las vulnerabilidades de formulario [que](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) los atacantes pueden usar cuando las credenciales de un usuario están en peligro.

> [!NOTE]
> Esta regla se aplica solo Outlook y Outlook.com.

Esta regla se introdujo en:

- [Windows 10, versión 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Nombre de Intune: `Process creation from Office communication products (beta)`

Nombre de Configuration Manager: No disponible

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Bloquear la persistencia a través de la suscripción de eventos WMI

Esta regla evita que el malware abuse de WMI para lograr la persistencia en un dispositivo.

> [!IMPORTANT]
> Las exclusiones de archivos y carpetas no se aplican a esta regla de reducción de superficie de ataque.

Las amenazas sin archivos emplean varias tácticas para mantenerse ocultas, para evitar que se vean en el sistema de archivos y para obtener un control de ejecución periódico. Algunas amenazas pueden abusar del repositorio WMI y el modelo de eventos para mantenerse oculto.

Esta regla se introdujo en:

- [Windows 10, versión 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Servidor 1903](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Nombre de Intune: no disponible

Nombre de Configuration Manager: No disponible

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Bloquear creaciones de proceso que se originen en comandos PSExec y WMI

Esta regla bloquea la ejecución de los procesos [creados a través](https://docs.microsoft.com/sysinternals/downloads/psexec) de PsExec [y WMI.](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) Tanto PsExec como WMI pueden ejecutar código de forma remota, por lo que existe el riesgo de que el malware abuse de esta funcionalidad con fines de comando y control, o de propagar una infección a través de la red de una organización.

> [!WARNING]
> Solo usa esta regla si estás administrando tus dispositivos con [Intune](https://docs.microsoft.com/intune) u otra solución MDM. Esta regla es incompatible con la administración a [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) porque esta regla bloquea los comandos WMI que el cliente de Configuration Manager usa para funcionar correctamente.

Esta regla se introdujo en:

- [Windows 10, versión 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Nombre de Intune: `Process creation from PSExec and WMI commands`

Nombre de Configuration Manager: no aplicable

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB

Con esta regla, los administradores pueden impedir que los archivos ejecutables sin signo o que no son de confianza se ejecuten desde unidades extraíbles USB, incluidas las tarjetas SD. Los tipos de archivo bloqueados incluyen archivos ejecutables (como .exe, .dll o .scr)

Esta regla se introdujo en:

- [Windows 10, versión 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Untrusted and unsigned processes that run from USB`

Nombre de Configuration Manager: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Bloquear llamadas a la API de Win32 desde Office macros

Esta regla impide que las macros de VBA llamen a las API de Win32.

Office VBA habilita las llamadas a la API de Win32. El malware puede abusar de esta funcionalidad, como llamar a las API de [Win32](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) para iniciar el código de shell malintencionado sin escribir nada directamente en el disco. La mayoría de las organizaciones no dependen de la capacidad de llamar a las API de Win32 en su funcionamiento diario, incluso si usan macros de otras maneras.

Esta regla se introdujo en:

- [Windows 10, versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Win32 imports from Office macro code`

Nombre de Configuration Manager: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Usar protección avanzada contra ransomware

Esta regla proporciona una capa adicional de protección contra ransomware. Usa heurística de cliente y nube para determinar si un archivo se parece a ransomware. Esta regla no bloquea los archivos que tienen una o varias de las siguientes características:

- Ya se ha encontrado que el archivo no es compartido en la nube de Microsoft.
- El archivo es un archivo firmado válido.
- El archivo es lo suficientemente frecuente como para no considerarse ransomware.

La regla tiende a errar en el lado de la precaución para evitar ransomware.

> [!NOTE]
> Debe habilitar [la protección entregada en la nube](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) para usar esta regla.

Esta regla se introdujo en:

- [Windows 10, versión 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versión 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nombre de Intune: `Advanced ransomware protection`

Nombre de Configuration Manager: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

## <a name="see-also"></a>Consulte también

- [Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction-faq.md)
- [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)
- [Evaluar las reglas de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
- [Compatibilidad de Antivirus de Microsoft Defender con otras soluciones antivirus/antimalware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
