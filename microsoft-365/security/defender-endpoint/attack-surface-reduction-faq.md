---
title: Preguntas más frecuentes sobre la reducción de superficie de ataque (FAQ)
description: Encuentre respuestas a las preguntas más frecuentes sobre las reglas de reducción de superficie de ataque de Microsoft Defender para endpoint.
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ca429ca1fea125450fdbb8d1f3a0e3a745513d8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245701"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>Preguntas más frecuentes sobre la reducción de superficie de ataque (FAQ)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>¿La reducción de superficie de ataque (ASR) forma parte de Windows?

ASR era originalmente una característica del conjunto de características de protección contra vulnerabilidades introducida como una actualización principal de Antivirus de Microsoft Defender, en Windows 10, versión 1709. Antivirus de Microsoft Defender es el componente antimalware nativo de Windows. Sin embargo, el conjunto completo de características de ASR solo está disponible con una Windows de empresa. Tenga en cuenta también que las exclusiones de reglas ASR se administran de forma independiente Antivirus de Microsoft Defender exclusiones.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>¿Necesito tener una licencia de empresa para ejecutar reglas ASR?

El conjunto completo de reglas y características de ASR solo se admite si tiene una licencia de empresa para Windows 10. Un número limitado de reglas puede funcionar sin una licencia de empresa. Si ha Microsoft 365 Empresa, establezca Antivirus de Microsoft Defender como la solución de seguridad principal y habilite las reglas a través de PowerShell. El uso de ASR sin una licencia de empresa no se admite oficialmente y no podrá usar todas las funcionalidades de ASR.

Para obtener más información sobre Windows licencias, consulte [Windows 10 Licensing y](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) obtenga la Guía de licencias por volumen para [Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>¿Se admite ASR si tengo una licencia E3?

Sí. ASR es compatible con Windows Enterprise E3 y versiones posteriores. 

## <a name="which-features-are-supported-with-an-e5-license"></a>¿Qué características se admiten con una licencia E5?

Todas las reglas admitidas con E3 también se admiten con E5.

E5 agrega una mayor integración con Defender para endpoint. Con E5, puede ver alertas en tiempo real, ajustar exclusiones de reglas, configurar reglas ASR y ver listas de informes de eventos.

## <a name="what-are-the-currently-supported-asr-rules"></a>¿Cuáles son las reglas ASR admitidas actualmente?
ASR admite actualmente todas las reglas siguientes.

## <a name="what-rules-to-enable-all-or-can-i-turn-on-individual-rules"></a>¿Qué reglas habilitar? ¿Todo o puedo activar reglas individuales?
Para ayudarle a averiguar qué es lo mejor para su entorno, le recomendamos que habilite las reglas ASR en el [modo de auditoría.](audit-windows-defender.md) Con este enfoque, determinará el posible efecto para su organización. Por ejemplo, las aplicaciones de línea de negocio.

## <a name="how-do-asr-rules-exclusions-work"></a>¿Cómo funcionan las exclusiones de reglas ASR?
Para las reglas ASR, si agrega una exclusión, afectará a todas las reglas ASR.
Las dos reglas específicas siguientes no admiten exclusiones:

|Nombre de regla|GUID|Exclusiones & carpetas de archivos|
|:--|:--|:--|
|Impedir que JavaScript o VBScript inicien contenido ejecutable descargado|D3E037E1-3EB8-44C8-A917-57927947596D|No se admite|
|Bloquear la persistencia a través de la suscripción de eventos WMI|e6db77e5-3df2-4cf1-b95a-636979351e5b|No se admite|

Las exclusiones de reglas ASR admiten caracteres comodín, rutas de acceso y variables de entorno. Para obtener más información sobre cómo usar caracteres comodín en reglas ASR, vea [configure and validate exclusions based on file extension and folder location](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus).

Tenga en cuenta los siguientes elementos sobre las exclusiones de reglas ASR (incluidos caracteres comodín y env. variables):

- Las exclusiones de reglas ASR son independientes de las exclusiones de Antivirus de Defender
- Los caracteres comodín no se pueden usar para definir una letra de unidad
- Si desea excluir más de una carpeta, en una ruta de acceso, use varias instancias de \ para indicar varias carpetas anidadas \* (por ejemplo, c:\Folder \* \* \Test)
- Microsoft Endpoint Configuration Manager *admite* caracteres comodín (* o ?)
- Si desea excluir un archivo, que contiene caracteres aleatorios (generación automática de archivos), puede usar el símbolo '?' (por ejemplo, C:\Folder\fileversion?.docx)
- Las exclusiones de ASR en la directiva de grupo no admiten comillas (el motor controlará de forma nativa rutas largas, espacios, etc., por lo que no es necesario usar comillas)
- Las reglas ASR se ejecutan en la cuenta NT AUTHORITY\SYSTEM, por lo que las variables de entorno se limitan a las variables de máquina.

## <a name="how-do-i-know-what-i-need-to-exclude"></a>¿Cómo sé lo que necesito excluir?
Las reglas ASR diferentes tendrán flujos de protección diferentes. Piense siempre en lo que protege la regla de ASR contra la que está configurando y en cómo se desatensa el flujo de ejecución real.

Ejemplo: bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows Leer directamente desde el proceso del subsistema de autoridad de seguridad **local** (LSASS) puede ser un riesgo de seguridad, ya que podría exponer credenciales corporativas.

Esta regla impide que los procesos que no son de confianza tengan acceso directo a la memoria de LSASS. Siempre que un proceso intente usar la función OpenProcess() para obtener acceso a LSASS, con un derecho de acceso de PROCESS_VM_READ, la regla bloqueará específicamente ese derecho de acceso.

:::image type="content" source="images/asrfaq1.png" alt-text="bloquear el robo de credenciales LSASS":::

En el ejemplo anterior, si realmente tuviera que crear una excepción para el proceso en el que se bloqueó el derecho de acceso, agregar el nombre de archivo junto con la ruta de acceso completa excluiría que no se bloqueara y después de permitir el acceso a la memoria del proceso de LSASS. El valor de 0 significa que las reglas ASR omitirán este archivo/proceso y no lo bloquearán ni auditarán.

:::image type="content" source="images/asrfaq2.png" alt-text="excluir archivos asr":::

## <a name="what-are-the-rules-microsoft-recommends-enabling"></a>¿Cuáles son las reglas que Microsoft recomienda habilitar?

Se recomienda habilitar todas las reglas posibles. Sin embargo, hay algunos casos en los que no debe habilitar una regla. Por ejemplo, no recomendamos habilitar la regla Bloquear creaciones de proceso que se originen a partir de los comandos PSExec y WMI, si usa Microsoft Endpoint Configuration Manager (o, System Center Configuration Manager - SCCM) para administrar los puntos de conexión.

Le recomendamos encarecidamente que lea cada información o advertencias específicas de la regla, que están disponibles en nuestra [documentación pública.](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md)
abarcando varios pilares de protección, como Office, credenciales, scripts, correo electrónico, etc. Todas las reglas ASR, excepto la persistencia de bloque a través de la suscripción a eventos WMI, se admiten en Windows 1709 y versiones posteriores:

* [Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [Bloquear todas Office aplicaciones de creación de procesos secundarios](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Bloquear Office aplicaciones de creación de contenido ejecutable](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Bloquear Office aplicaciones para que no inyecten código en otros procesos](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [Bloquear la ejecución de scripts potencialmente ofuscados](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Bloquear llamadas a la API de Win32 desde Office macro](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [Usar protección avanzada contra ransomware](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Bloquear el robo de credenciales del subsistema Windows autoridad de](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) seguridad local (lsass.exe)
* [Bloquear creaciones de proceso que se originen en comandos PSExec y WMI](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [Bloquear la ejecución de archivos ejecutables a menos que cumplan con criterios de prevalencia, antigüedad o lista de confianza](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Bloquear Office aplicaciones de comunicación para que no creen procesos secundarios](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
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

Intente abrir las opciones de indización directamente desde Windows 10.

1. Seleccione el **icono Buscar** en la Windows de tareas.

1. Escriba **Opciones de indización** en el cuadro de búsqueda.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>¿Los criterios usados por la regla, "Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de prevalencia, antigüedad o lista de confianza", son configurables por un administrador?

No. La protección en la nube de Microsoft mantiene los criterios usados por esta regla para mantener la lista de confianza actualizada constantemente con los datos recopilados de todo el mundo. Los administradores locales no tienen acceso de escritura para modificar estos datos. Si desea configurar esta regla para adaptarla a su empresa, puede agregar determinadas aplicaciones a la lista de exclusiones para evitar que se desencadene la regla.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>He habilitado la regla ASR, Bloquear la ejecución de archivos ejecutables a menos que cumplan un criterio de *prevalencia, antigüedad* o lista de confianza . Después de un tiempo, actualizó un fragmento de software y la regla ahora lo está bloqueando, aunque no lo haya hecho antes. ¿Algo salió mal?

Esta regla se basa en que cada aplicación tiene una reputación conocida, medida por prevalencia, edad o inclusión en una lista de aplicaciones de confianza. La decisión de la regla de bloquear o permitir una aplicación se determina en última instancia por la evaluación de estos criterios por parte de La protección en la nube de Microsoft.

Por lo general, la protección en la nube puede determinar que una nueva versión de una aplicación es lo suficientemente similar a las versiones anteriores que no es necesario volver a realizar una nueva evaluación a lo largo. Sin embargo, la aplicación puede tardar algún tiempo en crear reputación después de cambiar de versión, especialmente después de una actualización importante. Mientras tanto, puede agregar la aplicación a la lista de exclusiones para evitar que esta regla bloquee aplicaciones importantes. Si está actualizando y trabajando con frecuencia con nuevas versiones de aplicaciones, puede optar en su lugar por ejecutar esta regla en modo auditoría.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>He habilitado recientemente la regla ASR, Bloquear el robo de credenciales del subsistema de autoridad de seguridad *local (lsass.exe)* de Windows y estoy recibiendo un gran número de notificaciones. ¿Qué pasa?

Una notificación generada por esta regla no indica necesariamente actividad malintencionada; sin embargo, esta regla sigue siendo útil para bloquear la actividad malintencionada, ya que el malware suele lsass.exe para obtener acceso ilícito a las cuentas. El lsass.exe almacena las credenciales de usuario en la memoria después de que un usuario haya iniciado sesión. Windows estas credenciales para validar usuarios y aplicar directivas de seguridad locales.

Dado que muchos procesos legítimos a lo largo de un día típico lsass.exe para obtener credenciales, esta regla puede ser especialmente ruidosa. Si una aplicación legítima conocida hace que esta regla genere un número excesivo de notificaciones, puede agregarla a la lista de exclusión. La mayoría de las demás reglas ASR generarán un número relativamente menor de notificaciones, en comparación con esta, ya que llamar a lsass.exe es típico del funcionamiento normal de muchas aplicaciones.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>¿Es una buena idea habilitar la regla Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad *local (lsass.exe),* junto con la protección de LSA?

Habilitar esta regla no proporcionará protección adicional si también tiene habilitada la protección [LSA.](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) Tanto la regla como la protección de LSA funcionan de la misma manera, por lo que tener ambos ejecutándose al mismo tiempo sería redundante. Sin embargo, a veces es posible que no pueda habilitar la protección de LSA. En esos casos, puede habilitar esta regla para proporcionar protección equivalente contra malware destinado a lsass.exe.

## <a name="see-also"></a>Vea también

* [Introducción a la reducción de superficie de ataque](attack-surface-reduction.md)
* [Evaluar las reglas de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
* [Personalizar las reglas de la reducción de superficie expuesta a ataques](customize-attack-surface-reduction.md)
* [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)
* [Compatibilidad de Microsoft Defender con otros antivirus/antimalware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)


