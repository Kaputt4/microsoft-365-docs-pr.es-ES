---
title: Usar reglas de reducción de la superficie expuesta a ataques para evitar la infección de malware
description: Las reglas de reducción de superficie de ataque pueden ayudar a evitar que las vulnerabilidades utilicen aplicaciones y scripts para infectar dispositivos con malware.
keywords: Reglas de reducción de superficie de ataque, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
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
ms.technology: mde
ms.topic: article
ms.collection: m365initiative-m365-defender
ms.date: 1/18/2022
ms.openlocfilehash: 3f3daaa068f067c8d4ffbbf40a4d8ba1d32d04b9
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766446"
---
# <a name="attack-surface-reduction-rules-overview"></a>Introducción a las reglas de reducción de superficie de ataque

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>Por qué las reglas de reducción de superficie de ataque son importantes

La superficie de ataque de la organización incluye todos los lugares donde un atacante podría poner en peligro los dispositivos o redes de la organización. Reducir la superficie de ataque significa proteger los dispositivos y la red de la organización, lo que deja a los atacantes con menos formas de realizar ataques. La configuración de reglas de reducción de superficie de ataque en Microsoft Defender para endpoint puede ser útil.

Las reglas de reducción de superficie de ataque se aplican a determinados comportamientos de software, como:

- Iniciar archivos ejecutables y scripts que intenten descargar o ejecutar archivos
- Ejecución de scripts ofuscados o sospechosos
- Comportamientos que las aplicaciones normalmente no inician durante el trabajo diario normal

Estos comportamientos de software a veces se ven en aplicaciones legítimas. Sin embargo, estos comportamientos suelen considerarse riesgosos porque los atacantes suelen abusar de ellos a través del malware. Las reglas de reducción de superficie de ataque pueden restringir los comportamientos de riesgo basados en software y ayudar a mantener la organización segura.

Para obtener más información sobre cómo configurar reglas de reducción de superficie de ataque, consulta [Habilitar reglas de reducción de superficie de ataque](enable-attack-surface-reduction.md).

## <a name="assess-rule-impact-before-deployment"></a>Evaluar el impacto de la regla antes de la implementación

Puedes evaluar cómo una regla de reducción de superficie de ataque puede afectar a la red abriendo la recomendación de seguridad para esa regla en [Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/#tvm).

:::image type="content" source="images/asrrecommendation.png" alt-text="Reco de seguridad para la regla de reducción de superficie de ataque.":::

En el panel de detalles de recomendación, comprueba el impacto del usuario para determinar qué porcentaje de dispositivos pueden aceptar una nueva directiva que habilite la regla en modo de bloqueo sin afectar negativamente a la productividad.

Consulta [Requisitos](enable-attack-surface-reduction.md#requirements) en el artículo "Habilitar reglas de reducción de superficie de ataque" para obtener información sobre los sistemas operativos compatibles y la información de requisitos adicional.

## <a name="audit-mode-for-evaluation"></a>Modo auditoría para evaluación

Usa [el modo de auditoría](audit-windows-defender.md) para evaluar cómo afectarían las reglas de reducción de superficie de ataque a tu organización si se habilitan. Ejecute primero todas las reglas en el modo de auditoría para que pueda comprender cómo afectan a las aplicaciones de línea de negocio. Muchas aplicaciones de línea de negocio se escriben con problemas de seguridad limitados y pueden realizar tareas de maneras que parezcan similares al malware. Al supervisar los datos de auditoría y [agregar exclusiones](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) para las aplicaciones necesarias, puedes implementar reglas de reducción de superficie de ataque sin reducir la productividad.

## <a name="warn-mode-for-users"></a>Modo de advertencia para usuarios

(**¡NUEVO**!) Antes de las capacidades del modo de advertencia, las reglas de reducción de superficie de ataque habilitadas podrían establecerse en modo auditoría o modo de bloqueo. Con el nuevo modo de advertencia, siempre que una regla de reducción de superficie de ataque bloquee el contenido, los usuarios verán un cuadro de diálogo que indica que el contenido está bloqueado. El cuadro de diálogo también ofrece al usuario una opción para desbloquear el contenido. A continuación, el usuario puede reintentar su acción y se completa la operación. Cuando un usuario desbloquea el contenido, el contenido permanece desbloqueado durante 24 horas y, a continuación, el bloqueo se reanuda.

El modo de advertencia ayuda a la organización a tener reglas de reducción de superficie de ataques sin impedir que los usuarios accedan al contenido que necesitan para realizar sus tareas.

### <a name="requirements-for-warn-mode-to-work"></a>Requisitos para que funcione el modo de advertencia

El modo de advertencia se admite en dispositivos que ejecutan las siguientes versiones de Windows:

- [Windows 10, versión 1809](/windows/whats-new/whats-new-windows-10-version-1809) o posterior
- Windows 11
- [Windows server, versión 1809](/windows-server/get-started/whats-new-in-windows-server-1809) o posterior

Antivirus de Microsoft Defender debe ejecutarse con protección en tiempo real en [modo activo](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).

Además, asegúrese de [que Antivirus de Microsoft Defender y las actualizaciones de antimalware](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) están instaladas.

- Requisito mínimo de versión de plataforma: `4.18.2008.9`
- Requisito mínimo de versión del motor: `1.1.17400.5`

Para obtener más información y obtener las actualizaciones, vea [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).

### <a name="cases-where-warn-mode-is-not-supported"></a>Casos en los que no se admite el modo de advertencia

El modo de advertencia no se admite para tres reglas de reducción de superficie de ataque al configurarlas en Microsoft Endpoint Manager. (Si usas la directiva de grupo para configurar las reglas de reducción de superficie de ataque, se admite el modo de advertencia). Las tres reglas que no admiten el modo de advertencia al configurarlas en Microsoft Endpoint Manager son las siguientes:

- [Impedir que JavaScript o VBScript inicien contenido ejecutable descargado](attack-surface-reduction-rules-reference.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)
- [Bloquear la persistencia a través de la suscripción de eventos WMI](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)
- [Usar protección avanzada contra ransomware](attack-surface-reduction-rules-reference.md#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)

Además, el modo de advertencia no se admite en dispositivos que ejecutan versiones anteriores de Windows. En esos casos, las reglas de reducción de superficie de ataque configuradas para ejecutarse en modo de advertencia se ejecutarán en modo de bloqueo.

## <a name="notifications-and-alerts"></a>Notificaciones y alertas

Cada vez que se desencadena una regla de reducción de superficie de ataque, se muestra una notificación en el dispositivo. Puede [personalizar la notificación](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) con los detalles de la empresa y la información de contacto.

Además, cuando se desencadenan ciertas reglas de reducción de superficie de ataque, se generan alertas.

Las notificaciones y las alertas que se generan se pueden ver en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender web</a>.

Para obtener detalles específicos sobre la funcionalidad de notificación y alerta, consulta: Por alerta de regla y detalles [de](attack-surface-reduction-rules-reference.md#per-rule-alert-and-notification-details) notificación, en el artículo Referencia de reglas de reducción **de superficie de ataque**.

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Eventos avanzados de reducción de superficie de búsqueda y ataque

Puedes usar la búsqueda avanzada para ver eventos de reducción de superficie de ataque. Para simplificar el volumen de datos entrantes, solo se pueden ver procesos únicos para cada hora con búsqueda avanzada. La hora de un evento de reducción de superficie de ataque es la primera vez que se ve ese evento dentro de la hora.

Por ejemplo, supongamos que se produce un evento de reducción de superficie de ataque en 10 dispositivos durante la hora de las 2:00 p.m. Supongamos que el primer evento se produjo a las 2:15 y el último a las 2:45. Con la búsqueda avanzada, verás una instancia de ese evento (aunque realmente se produjo en 10 dispositivos) y su marca de tiempo será las 2:15 p.m.

Para obtener más información acerca de la búsqueda avanzada, vea [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Características de reducción de superficie de ataque en Windows versiones

Puedes establecer reglas de reducción de superficie de ataque para dispositivos que ejecutan cualquiera de las siguientes ediciones y versiones de Windows:

- Windows 10 Pro versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows server, [versión 1803 (canal semianual)](/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

  >[!NOTE]
  >Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse con las instrucciones de [Onboard Windows servers](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) para que esta característica funcione.

Aunque las reglas de reducción de superficie de ataque no requieren una [licencia Windows E5](/windows/deployment/deploy-enterprise-licenses), si Windows E5, obtienes capacidades de administración avanzadas. Las funcionalidades avanzadas, disponibles solo en Windows E5, incluyen:

- La supervisión, el análisis y los flujos de trabajo disponibles [en Defender for Endpoint](microsoft-defender-endpoint.md)
- Las capacidades de informes y configuración de [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

Estas funcionalidades avanzadas no están disponibles con una licencia Windows Professional o Windows E3. Sin embargo, si tienes esas licencias, puedes usar el Visor de eventos y los Antivirus de Microsoft Defender para revisar los eventos de la regla de reducción de superficie de ataque.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>Revisar los eventos de reducción de superficie de ataque en el portal Microsoft 365 Defender ataque

Defender for Endpoint proporciona informes detallados para eventos y bloques como parte de escenarios de investigación de alertas.

Puede consultar los datos del extremo de Defender [en Microsoft 365 Defender](microsoft-defender-endpoint.md) mediante la [búsqueda avanzada](/microsoft-365/security/defender/advanced-hunting-query-language). 

A continuación le mostramos un ejemplo de consulta:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Revisar los eventos de reducción de superficie de ataque Windows visor de eventos

Puedes revisar el registro de eventos Windows para ver los eventos generados por las reglas de reducción de superficie de ataque:

1. Descargue el [paquete de evaluación](https://aka.ms/mp7z2w) y extraiga el archivo *cfa-events.xml* a una ubicación fácilmente accesible en el dispositivo.

2. Escriba las palabras, *Visor de* eventos, en el menú Inicio para abrir el visor Windows eventos.

3. En **Acciones**, seleccione **Importar vista personalizada...**.

4. Seleccione el archivo *cfa-events.xml* desde donde se extrajo. Como alternativa, [copie el XML directamente](event-views.md).

5. Seleccione **Aceptar**.

Puede crear una vista personalizada que filtra los eventos para mostrar solo los siguientes eventos, todos ellos relacionados con el acceso controlado a carpetas:

|Id. de evento|Descripción|
|---|---|
|5007|Evento cuando se cambia la configuración|
|1121|Evento cuando la regla se dispara en modo bloque|
|1122|Evento cuando la regla se dispara en modo auditoría|

La "versión del motor" que aparece para los eventos de reducción de superficie de ataque en el registro de eventos, la genera Defender for Endpoint, no el sistema operativo. Defender para endpoint está integrado con Windows 10 y Windows 11, por lo que esta característica funciona en todos los dispositivos con Windows 10 o Windows 11 instalados.
