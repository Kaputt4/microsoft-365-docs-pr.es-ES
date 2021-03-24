---
title: Preguntas más frecuentes sobre la reducción de superficie de ataque (FAQ)
description: Encuentre respuestas a las preguntas más frecuentes sobre las reglas de reducción de superficie de ataque de ATP de Microsoft Defender.
keywords: Reglas de reducción de superficie de ataque, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 7685bd70d85ecebe759ade762b78ee2c3639cea8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069835"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>Preguntas más frecuentes sobre la reducción de superficie de ataque (FAQ)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>¿La reducción de superficie de ataque (ASR) es parte de Windows?

ASR era originalmente una característica del conjunto de características de protección contra vulnerabilidades introducida como una actualización importante de Antivirus de Microsoft Defender, en Windows 10, versión 1709. Antivirus de Microsoft Defender es el componente antimalware nativo de Windows. Sin embargo, el conjunto de características completo de ASR solo está disponible con una licencia de empresa de Windows. Tenga en cuenta también que las exclusiones de reglas ASR se administran por separado de las exclusiones de Antivirus de Microsoft Defender.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>¿Necesito tener una licencia de empresa para ejecutar reglas ASR?

El conjunto completo de reglas y características de ASR solo se admite si tienes una licencia de empresa para Windows 10. Un número limitado de reglas puede funcionar sin una licencia de empresa. Si tiene Microsoft 365 Empresa, establezca Antivirus de Microsoft Defender como solución de seguridad principal y habilite las reglas a través de PowerShell. Sin embargo, el uso de ASR sin una licencia de empresa no se admite oficialmente y las capacidades completas de ASR no estarán disponibles.

Para obtener más información sobre las licencias de Windows, consulta [Licencias de Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) y obtén la Guía de licencias por [volumen para Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>¿Se admite ASR si tengo una licencia E3?

Sí. ASR es compatible con Windows Enterprise E3 y versiones posteriores. 

## <a name="which-features-are-supported-with-an-e5-license"></a>¿Qué características se admiten con una licencia E5?

Todas las reglas admitidas con E3 también se admiten con E5.

E5 también agregó una mayor integración con Defender for Endpoint. Con E5, puede usar [Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender/monitor-devices?view=o365-worldwide&preserve-view=true#monitor-and-manage-asr-rule-deployment-and-detections) para supervisar y revisar el análisis de alertas en tiempo real, ajustar exclusiones de reglas, configurar reglas ASR y ver listas de informes de eventos.

## <a name="what-are-the-currently-supported-asr-rules"></a>¿Cuáles son las reglas ASR admitidas actualmente?

ASR admite actualmente todas las reglas siguientes:

* [Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [Impedir que todas las aplicaciones de Office creen procesos secundarios](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Impedir que las aplicaciones de Office creen contenido ejecutable](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Impedir que las aplicaciones de Office inyecten código en otros procesos](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [Bloquear la ejecución de scripts potencialmente ofuscados](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Bloquear llamadas a la API de Win32 desde la macro de Office](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [Usar protección avanzada contra ransomware](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Bloquear el robo de credenciales del subsistema de](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) autoridad de seguridad local de Windows (lsass.exe)
* [Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [Bloquear la ejecución de archivos ejecutables a menos que cumplan con criterios de prevalencia, antigüedad o lista de confianza](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Impedir que las aplicaciones de comunicación de Office creen procesos secundarios](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Impedir que Adobe Reader cree procesos secundarios](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [Bloquear la persistencia a través de la suscripción de eventos WMI](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>¿Cuáles son algunas recomendaciones para empezar a trabajar con ASR?

Pruebe cómo afectarán las reglas ASR a su organización antes de habilitarlas ejecutando reglas ASR en modo auditoría durante un breve período de tiempo. Mientras ejecuta las reglas en modo auditoría, puede identificar cualquier aplicación de línea de negocio que pueda bloquearse erróneamente y excluirlas de ASR.

Las organizaciones más grandes deben considerar la posibilidad de implementar reglas ASR en "anillos", mediante la auditoría y habilitación de reglas en subconjuntos de dispositivos cada vez más amplios. Puede organizar los dispositivos de su organización en anillos mediante Intune o una herramienta de administración de directivas de grupo.

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>¿Cuánto tiempo debo probar una regla ASR en modo auditoría antes de habilitarla?

Mantenga la regla en modo auditoría durante unos 30 días para obtener una buena línea base de cómo funcionará la regla una vez que entre en funcionamiento en toda la organización. Durante el período de auditoría, puede identificar cualquier aplicación de línea de negocio que pueda bloquearse por la regla y configurar la regla para excluirlas.

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>Estoy cambiando de una solución de seguridad de terceros a Defender for Endpoint. ¿Hay una forma "fácil" de exportar reglas de otra solución de seguridad a ASR?

En la mayoría de los casos, es más fácil y mejor empezar con las recomendaciones de línea base sugeridas por [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) que intentar importar reglas de otra solución de seguridad. A continuación, usa herramientas como el modo de auditoría, la supervisión y el análisis para configurar la nueva solución para que se adapte a tus necesidades únicas. 

La configuración predeterminada para la mayoría de las reglas ASR, combinada con la protección en tiempo real de Defender for Endpoint, protegerá contra un gran número de vulnerabilidades y vulnerabilidades.

Desde Defender para endpoint, puedes actualizar tus defensas con indicadores personalizados para permitir y bloquear determinados comportamientos de software. ASR también permite algunas personalizaciones de reglas, en forma de exclusiones de archivos y carpetas. Como regla general, es mejor auditar una regla durante un período de tiempo y configurar exclusiones para cualquier aplicación de línea de negocio que pueda bloquearse.

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>¿ASR admite exclusiones de archivos o carpetas que incluyen variables del sistema y caracteres comodín en la ruta de acceso?

Sí. Consulte [Exclude files and folders from ASR rules](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) para obtener más información sobre la exclusión de archivos o carpetas de reglas ASR, y Configure and validate exclusions based on file extension and folder location para obtener más información sobre cómo usar variables del sistema y caracteres comodín en rutas de acceso de archivo [excluidas.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

## <a name="do-asr-rules-cover-all-applications-by-default"></a>¿Las reglas ASR cubren todas las aplicaciones de forma predeterminada?

Depende de la regla. La mayoría de las reglas ASR cubren el comportamiento de Microsoft Office productos y servicios, como Word, Excel, PowerPoint y OneNote, o Outlook. Ciertas reglas ASR, como Bloquear la ejecución de scripts potencialmente *ofuscados,* son más generales en el ámbito.

## <a name="does-asr-support-third-party-security-solutions"></a>¿ASR admite soluciones de seguridad de terceros?

ASR usa Antivirus de Microsoft Defender para bloquear aplicaciones. No es posible configurar ASR para usar otra solución de seguridad para el bloqueo en este momento.

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>Tengo una licencia E5 y he habilitado algunas reglas ASR junto con Defender para Endpoint. ¿Es posible que un evento ASR no se muestre en absoluto en la escala de tiempo de eventos de Defender para Endpoint?

Siempre que una regla ASR desencadena localmente una notificación, también se envía un informe sobre el evento al portal de Defender for Endpoint. Si tienes problemas para encontrar el evento, puedes filtrar la escala de tiempo de eventos mediante el cuadro de búsqueda. También puedes ver eventos ASR visitando **Ir** a la administración de superficie de ataque, desde el icono **Administración de** configuración de la barra de tareas del Centro de seguridad. La página de administración de superficie de ataque incluye una pestaña para detecciones de informes, que incluye una lista completa de eventos de regla ASR notificados a Defender para endpoint.

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>He aplicado una regla con GPO. Ahora, cuando intento comprobar las opciones de indización de la regla en Microsoft Outlook, aparece un mensaje que indica "Acceso denegado".

Intenta abrir las opciones de indización directamente desde Windows 10.

1. Selecciona el **icono Buscar** en la barra de tareas de Windows.

1. Escriba **Opciones de indización** en el cuadro de búsqueda.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>¿Los criterios usados por la regla, "Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza", son configurables por un administrador?

No. La protección en la nube de Microsoft mantiene los criterios usados por esta regla para mantener la lista de confianza actualizada constantemente con los datos recopilados de todo el mundo. Los administradores locales no tienen acceso de escritura para modificar estos datos. Si desea configurar esta regla para adaptarla a su empresa, puede agregar determinadas aplicaciones a la lista de exclusiones para evitar que se desencadene la regla.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>He habilitado la regla ASR, Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de *prevalencia, antigüedad* o lista de confianza . Después de un tiempo, actualizó un fragmento de software y la regla ahora lo está bloqueando, aunque no lo haya hecho antes. ¿Algo salió mal?

Esta regla se basa en que cada aplicación tiene una reputación conocida, medida por prevalencia, edad o inclusión en una lista de aplicaciones de confianza. La decisión de la regla de bloquear o permitir una aplicación se determina en última instancia por la evaluación de estos criterios por parte de La protección en la nube de Microsoft.

Por lo general, la protección en la nube puede determinar que una nueva versión de una aplicación es lo suficientemente similar a las versiones anteriores que no es necesario volver a realizar una nueva evaluación a lo largo. Sin embargo, la aplicación puede tardar algún tiempo en crear reputación después de cambiar de versión, especialmente después de una actualización importante. Mientras tanto, puede agregar la aplicación a la lista de exclusiones para evitar que esta regla bloquee aplicaciones importantes. Si está actualizando y trabajando con frecuencia con nuevas versiones de aplicaciones, puede optar en su lugar por ejecutar esta regla en modo auditoría.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>He habilitado recientemente la regla ASR, Bloquear el robo de credenciales del subsistema de autoridad de seguridad *local de Windows (lsass.exe)* y estoy recibiendo un gran número de notificaciones. ¿Qué pasa?

Una notificación generada por esta regla no indica necesariamente actividad malintencionada; sin embargo, esta regla sigue siendo útil para bloquear la actividad malintencionada, ya que el malware suele lsass.exe para obtener acceso ilícito a las cuentas. El lsass.exe almacena las credenciales de usuario en la memoria después de que un usuario haya iniciado sesión. Windows usa estas credenciales para validar usuarios y aplicar directivas de seguridad locales.

Dado que muchos procesos legítimos a lo largo de un día típico lsass.exe para obtener credenciales, esta regla puede ser especialmente ruidosa. Si una aplicación legítima conocida hace que esta regla genere un número excesivo de notificaciones, puede agregarla a la lista de exclusión. La mayoría de las demás reglas ASR generarán un número relativamente menor de notificaciones, en comparación con esta, ya que llamar a lsass.exe es típico del funcionamiento normal de muchas aplicaciones.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>¿Es una buena idea habilitar la regla, Bloquear el robo de credenciales del subsistema de autoridad de seguridad *local de Windows (lsass.exe),* junto con la protección de LSA?

Habilitar esta regla no proporcionará protección adicional si también tiene habilitada la protección [LSA.](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) Tanto la regla como la protección de LSA funcionan de la misma manera, por lo que tener ambos ejecutándose al mismo tiempo sería redundante. Sin embargo, a veces es posible que no pueda habilitar la protección de LSA. En esos casos, puede habilitar esta regla para proporcionar protección equivalente contra malware destinado a lsass.exe.

## <a name="see-also"></a>Ver también

* [Introducción a la reducción de superficie de ataque](attack-surface-reduction.md)
* [Evaluar reglas de reducción de superficie de ataque](evaluate-attack-surface-reduction.md)
* [Personalizar reglas de reducción de superficie de ataque](customize-attack-surface-reduction.md)
* [Habilitar reglas de reducción de superficie de ataque](enable-attack-surface-reduction.md)
* [Compatibilidad de Microsoft Defender con otros antivirus/antimalware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
