---
title: Usar reglas de reducción de la superficie expuesta a ataques para evitar la infección de malware
description: Las reglas de reducción de superficie expuesta a ataques pueden ayudar a evitar que las vulnerabilidades de seguridad usen aplicaciones y scripts para infectar dispositivos con malware.
keywords: Reglas de reducción de superficie expuesta a ataques, asr, caderas, sistema de prevención de intrusiones del host, reglas de protección, anti-vulnerabilidad, antiexploit, vulnerabilidad de seguridad, prevención de infecciones, Microsoft Defender para punto de conexión
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: m365-security
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom:
- asr
- admindeeplinkDEFENDER
ms.topic: article
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 0d8b70adb32cc20f0efc2b0df94ae4d6ebffefd1
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799272"
---
# <a name="attack-surface-reduction-rules-overview"></a>Introducción a las reglas de reducción de superficie expuesta a ataques

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

## <a name="why-attack-surface-reduction-rules-are-important"></a>Por qué son importantes las reglas de reducción de superficie expuesta a ataques

La superficie expuesta a ataques de la organización incluye todos los lugares donde un atacante podría poner en peligro los dispositivos o redes de la organización. Reducir la superficie expuesta a ataques significa proteger los dispositivos y la red de su organización, lo que deja a los atacantes con menos formas de realizar ataques. La configuración de reglas de reducción de superficie expuesta a ataques en Microsoft Defender para punto de conexión puede ayudar.

Las reglas de reducción de superficie expuesta a ataques tienen como objetivo determinados comportamientos de software, como:

- Inicio de archivos ejecutables y scripts que intentan descargar o ejecutar archivos
- Ejecución de scripts ofuscados o sospechosos
- Realizar comportamientos que las aplicaciones no suelen iniciar durante el trabajo diario normal

Estos comportamientos de software a veces se ven en aplicaciones legítimas. Sin embargo, estos comportamientos a menudo se consideran de riesgo porque suelen ser objeto de abuso por parte de los atacantes a través de malware. Las reglas de reducción de la superficie expuesta a ataques pueden restringir los comportamientos de riesgo basados en software y ayudar a mantener la seguridad de la organización.

Para obtener más información sobre cómo configurar reglas de reducción de superficie expuesta a ataques, consulte [Habilitar reglas de reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md).

## <a name="assess-rule-impact-before-deployment"></a>Evaluación del impacto de la regla antes de la implementación

Puede evaluar cómo puede afectar una regla de reducción de superficie expuesta a ataques a la red abriendo la recomendación de seguridad para esa regla en [Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/).

:::image type="content" source="images/asrrecommendation.png" alt-text="La recomendación de ASR" lightbox="images/asrrecommendation.png":::

En el panel de detalles de la recomendación, compruebe el impacto del usuario para determinar qué porcentaje de los dispositivos puede aceptar una nueva directiva que habilite la regla en modo de bloqueo sin afectar negativamente a la productividad.

Consulte [Requisitos](enable-attack-surface-reduction.md#requirements) en el artículo "Habilitar reglas de reducción de superficie expuesta a ataques" para obtener información sobre los sistemas operativos admitidos e información adicional sobre los requisitos.

## <a name="audit-mode-for-evaluation"></a>Modo de auditoría para la evaluación

Use el [modo de auditoría](audit-windows-defender.md) para evaluar cómo afectarían las reglas de reducción de superficie expuesta a ataques a su organización si está habilitada. Ejecute todas las reglas en el modo de auditoría primero para que pueda comprender cómo afectan a las aplicaciones de línea de negocio. Muchas aplicaciones de línea de negocio se escriben con problemas de seguridad limitados y pueden realizar tareas de maneras que parezcan similares al malware. Al supervisar los datos de auditoría y [agregar exclusiones](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) para las aplicaciones necesarias, puede implementar reglas de reducción de superficie expuesta a ataques sin reducir la productividad.

## <a name="warn-mode-for-users"></a>Modo de advertencia para los usuarios

(**¡NUEVO**!) Antes de las funcionalidades del modo de advertencia, las reglas de reducción de superficie expuesta a ataques habilitadas se podían establecer en modo auditoría o modo de bloque. Con el nuevo modo de advertencia, cada vez que una regla de reducción de superficie expuesta a ataques bloquea el contenido, los usuarios ven un cuadro de diálogo que indica que el contenido está bloqueado. El cuadro de diálogo también ofrece al usuario la opción de desbloquear el contenido. A continuación, el usuario puede volver a intentar su acción y la operación se completa. Cuando un usuario desbloquea el contenido, el contenido permanece desbloqueado durante 24 horas y, a continuación, se reanuda el bloqueo.

El modo de advertencia ayuda a la organización a tener reglas de reducción de la superficie expuesta a ataques implementadas sin impedir que los usuarios accedan al contenido que necesitan para realizar sus tareas.

### <a name="requirements-for-warn-mode-to-work"></a>Requisitos para que el modo de advertencia funcione

El modo de advertencia se admite en dispositivos que ejecutan las siguientes versiones de Windows:

- [Windows 10, versión 1809](/windows/whats-new/whats-new-windows-10-version-1809) o posterior
- Windows 11
- [Windows Server, versión 1809](/windows-server/get-started/whats-new-in-windows-server-1809) o posterior

Antivirus de Microsoft Defender debe ejecutarse con protección en tiempo real en [modo activo](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).

Además, asegúrese de que están instaladas [las actualizaciones antivirus y antimalware de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) .

- Requisito mínimo de versión de plataforma: `4.18.2008.9`
- Requisito mínimo de versión del motor: `1.1.17400.5`

Para obtener más información y obtener las actualizaciones, consulte [Actualización para la plataforma antimalware de Microsoft Defender](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).

### <a name="cases-where-warn-mode-is-not-supported"></a>Casos en los que no se admite el modo de advertencia

El modo de advertencia no se admite para tres reglas de reducción de superficie expuesta a ataques al configurarlas en Microsoft Endpoint Manager. (Si usas directiva de grupo para configurar las reglas de reducción de superficie expuesta a ataques, se admite el modo de advertencia). Las tres reglas que no admiten el modo de advertencia al configurarlas en Microsoft Endpoint Manager son las siguientes:

- [Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](attack-surface-reduction-rules-reference.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)
- [Bloquear la persistencia a través de la suscripción de eventos WMI](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)
- [Uso de protección avanzada contra ransomware](attack-surface-reduction-rules-reference.md#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)

Además, el modo de advertencia no se admite en dispositivos que ejecutan versiones anteriores de Windows. En esos casos, las reglas de reducción de superficie expuesta a ataques configuradas para ejecutarse en modo de advertencia se ejecutarán en modo de bloque.

## <a name="notifications-and-alerts"></a>Notificaciones y alertas

Cada vez que se desencadena una regla de reducción de superficie expuesta a ataques, se muestra una notificación en el dispositivo. Puede [personalizar la notificación](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) con los detalles de la empresa y la información de contacto.

Además, cuando se desencadenan determinadas reglas de reducción de superficie expuesta a ataques, se generan alertas.

Las notificaciones y las alertas generadas se pueden ver en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.

Para obtener detalles específicos sobre la funcionalidad de notificaciones y alertas, consulte: [Por alerta de regla y detalles de notificación](attack-surface-reduction-rules-reference.md#per-rule-alert-and-notification-details), en el artículo **Referencia de reglas de reducción de superficie expuesta a ataques**.

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Eventos avanzados de reducción de la superficie expuesta a ataques y búsqueda

Puede usar la búsqueda avanzada para ver eventos de reducción de superficie expuesta a ataques. Para simplificar el volumen de datos entrantes, solo se pueden ver los procesos únicos para cada hora con la búsqueda avanzada. La hora de un evento de reducción de superficie expuesta a ataques es la primera vez que se ve ese evento dentro de la hora.

Por ejemplo, supongamos que se produce un evento de reducción de la superficie expuesta a ataques en 10 dispositivos durante las 2:00 p.m. Supongamos que el primer evento se produjo a las 2:15 y el último a las 2:45. Con la búsqueda avanzada, verá una instancia de ese evento (aunque realmente se haya producido en 10 dispositivos) y su marca de tiempo será a las 2:15 p. m.

Para obtener más información sobre la búsqueda avanzada, vea [Búsqueda proactiva de amenazas con búsqueda avanzada](advanced-hunting-overview.md).

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Características de reducción de superficie expuesta a ataques en versiones de Windows

Puede establecer reglas de reducción de superficie expuesta a ataques para dispositivos que ejecutan cualquiera de las siguientes ediciones y versiones de Windows:

- Windows 10 Pro, [versión 1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise, [versión 1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows Server, [versión 1803 (canal semestral)](/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh801901(v=ws.11))

  >[!NOTE]
  >Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse mediante las instrucciones de [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) para que esta característica funcione.

Aunque las reglas de reducción de superficie expuesta a ataques no requieren una [licencia de Windows E5](/windows/deployment/deploy-enterprise-licenses), si tienes Windows E5, obtienes funcionalidades avanzadas de administración. Las funcionalidades avanzadas , disponibles solo en Windows E5, incluyen:

- Supervisión, análisis y flujos de trabajo disponibles en [Defender para punto de conexión](microsoft-defender-endpoint.md)
- Funcionalidades de generación de informes y configuración en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

Estas funcionalidades avanzadas no están disponibles con una licencia de Windows Professional o Windows E3. Sin embargo, si tiene esas licencias, puede usar Visor de eventos y los registros del Antivirus de Microsoft Defender para revisar los eventos de la regla de reducción de la superficie expuesta a ataques.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>Revisar los eventos de reducción de superficie expuesta a ataques en el portal de Microsoft 365 Defender

Defender para punto de conexión proporciona informes detallados de eventos y bloques como parte de escenarios de investigación de alertas.

Puede consultar datos de Defender para punto de conexión en [Microsoft 365 Defender](microsoft-defender-endpoint.md) mediante la [búsqueda avanzada](/microsoft-365/security/defender/advanced-hunting-query-language). 

A continuación le mostramos un ejemplo de consulta:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Revisar los eventos de reducción de superficie expuesta a ataques en Windows Visor de eventos

Puede revisar el registro de eventos de Windows para ver los eventos generados por las reglas de reducción de superficie expuesta a ataques:

1. Descargue el [paquete de evaluación](https://aka.ms/mp7z2w) y extraiga el archivo *cfa-events.xml* en una ubicación de fácil acceso en el dispositivo.

2. Escriba las palabras *, Visor de eventos*, en el menú Inicio para abrir la Visor de eventos de Windows.

3. En **Acciones**, seleccione **Importar vista personalizada...**.

4. Seleccione el *archivocfa-events.xml* desde el que se extrajo. Como alternativa, [copie el XML directamente](event-views.md).

5. Seleccione **Aceptar**.

Puede crear una vista personalizada que filtre los eventos para mostrar solo los siguientes eventos, todos ellos relacionados con el acceso controlado a carpetas:

|Id. de evento|Descripción|
|---|---|
|5007|Evento cuando se cambia la configuración|
|1121|Evento cuando se activa la regla en modo de bloque|
|1122|Evento cuando se activa la regla en modo auditoría|

La "versión del motor" que aparece para los eventos de reducción de la superficie expuesta a ataques en el registro de eventos la genera Defender for Endpoint, no el sistema operativo. Defender para punto de conexión se integra con Windows 10 y Windows 11, por lo que esta característica funciona en todos los dispositivos con Windows 10 o Windows 11 instalados.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
