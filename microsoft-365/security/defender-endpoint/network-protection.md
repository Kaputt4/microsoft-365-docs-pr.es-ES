---
title: Uso de la protección de red para evitar conexiones a sitios incorrectos
description: Proteja la red evitando que los usuarios accedan a direcciones de red malintencionadas y sospechosas conocidas.
keywords: Protección de red, vulnerabilidades de seguridad, sitio web malintencionado, ip, dominio, dominios, comando y control, SmartScreen, notificación del sistema
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 10/20/2022
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.subservice: mde
ms.topic: overview
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 99d1d4bfbbce6a010f9823071b2c3be8920aa409
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68815559"
---
# <a name="protect-your-network"></a>Proteger la red

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**

- Windows
- macOS
- Linux

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="overview-of-network-protection"></a>Introducción a la protección de red

La protección de red ayuda a proteger los dispositivos frente a eventos basados en Internet. La protección de red es una capacidad de reducción de la superficie expuesta a ataques. Ayuda a evitar que los empleados accedan a dominios peligrosos a través de aplicaciones. Los dominios que hospedan estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet se consideran peligrosos. La protección de red expande el ámbito de [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) para bloquear todo el tráfico HTTP saliente que intenta conectarse a orígenes de baja reputación (en función del dominio o el nombre de host).

La protección de red amplía la protección de la [protección web](web-protection-overview.md) al nivel del sistema operativo y es un componente principal para el filtrado de contenido web (WCF). Proporciona la funcionalidad de protección web que se encuentra en Microsoft Edge a otros exploradores compatibles y aplicaciones que no son de explorador. La protección de red también proporciona visibilidad y bloqueo de indicadores de riesgo (IOC) cuando se usan con la [detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md). Por ejemplo, la protección de red funciona con [los indicadores personalizados](manage-indicators.md) que puede usar para bloquear dominios o nombres de host específicos.

### <a name="network-protection-coverage"></a>Cobertura de protección de red

En la tabla siguiente se resumen las áreas de cobertura de protección de red.

| Característica | Microsoft Edge | Exploradores de terceros | Procesos que no son del explorador <br> (por ejemplo, PowerShell) |
|:---|:---|:---|:---|
| Protección contra amenazas web | SmartScreen debe estar habilitado | NP tiene que estar en modo de bloque | NP tiene que estar en modo de bloque |
| Indicadores personalizados | SmartScreen debe estar habilitado | NP tiene que estar en modo de bloque | NP tiene que estar en modo de bloque |
| Filtrado de contenido web | SmartScreen debe estar habilitado | NP tiene que estar en modo de bloque | No compatible |

> [!NOTE]
> La protección de red no supervisa msedge.exe en dispositivos Windows.
> Para Mac y Linux, debe tener protección de red en modo de bloque para obtener compatibilidad con estas características en Edge.
> En el caso de procesos distintos de Microsoft Edge e Internet Explorer, los escenarios de protección web aprovechan la protección de red para la inspección y el cumplimiento:
> - Ip es compatible con los tres protocolos (TCP, HTTP y HTTPS (TLS)).
> - Solo se admiten direcciones IP únicas (sin bloques CIDR ni intervalos IP) en indicadores personalizados.
> - Las direcciones URL cifradas (ruta de acceso completa) solo se pueden bloquear en exploradores de primera entidad (Internet Explorer, Edge).
> - Las direcciones URL cifradas (solo FQDN) se pueden bloquear en exploradores de terceros (es decir, distintas de Internet Explorer, Edge).
> - Los bloques de ruta de acceso de dirección URL completa se pueden aplicar a direcciones URL sin cifrar.
>
> Puede haber hasta 2 horas de latencia (normalmente menos) entre el momento en que se realiza la acción y la dirección URL y la dirección IP bloqueadas.

Vea este vídeo para obtener información sobre cómo la protección de red ayuda a reducir la superficie expuesta a ataques de los dispositivos frente a estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad y otro contenido malintencionado.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yZ]

## <a name="requirements-for-network-protection"></a>Requisitos para la protección de red

La protección de red requiere Windows 10 o 11 (Pro o Enterprise), Windows Server versión 1803 o posterior, macOS versión 11 o posterior, o versiones de Linux compatibles con Defender y Microsoft Defender protección antivirus en tiempo real.

| Versión de Windows | Antivirus de Microsoft Defender |
|:---|:---|
| Windows 10 versión 1709 o posterior, Windows 11, Windows Server 1803 o posterior | Asegúrese de que [Microsoft Defender protección antivirus en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md) y [protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) estén habilitadas (activas) |
| Windows Server 2012 R2 y Windows Server 2016 con el agente unificado | Platform Update versión 4.18.2001.x.x o posterior |

## <a name="why-network-protection-is-important"></a>Por qué es importante la protección de red

La protección de red forma parte del grupo de soluciones de reducción de superficie expuesta a ataques en Microsoft Defender para punto de conexión. La protección de red habilita la capa de red de direcciones URL de bloqueo y direcciones IP. La protección de red puede impedir que se acceda a las direcciones URL mediante determinados exploradores y conexiones de red estándar. De forma predeterminada, la protección de red protege los equipos de direcciones URL malintencionadas conocidas mediante la fuente SmartScreen, que bloquea las direcciones URL malintencionadas de forma similar a SmartScreen en el explorador Microsoft Edge. La funcionalidad de protección de red se puede ampliar a:

- Bloquear direcciones IP/URL de su propia inteligencia sobre amenazas ([indicadores](indicator-ip-domain.md))
- Bloquear los servicios no autorizadas de [Microsoft Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps)
- Bloquear sitios en función de la categoría ([filtrado de contenido web](web-content-filtering.md))

La protección de red es una parte fundamental de la pila de protección y respuesta de Microsoft.

> [!TIP]
> Para obtener más información sobre la protección de red para Windows Server, Linux, MacOS y Mobile Threat Defense (MTD), consulte [Búsqueda proactiva de amenazas con búsqueda avanzada](advanced-hunting-overview.md).

### <a name="block-command-and-control-attacks"></a>Bloquear ataques de comando y control

Los equipos de servidor de comandos y control (C2) los usan usuarios malintencionados para enviar comandos a sistemas en peligro por malware y, a continuación, ejercen algún tipo de control sobre sistemas en peligro. Los ataques C2 normalmente se ocultan en servicios basados en la nube, como el uso compartido de archivos y los servicios de correo web, lo que permite que los servidores C2 eviten la detección combinando con el tráfico típico.

Los servidores C2 se pueden usar para iniciar comandos que pueden:

- Robar datos (por ejemplo, mediante phishing)
- Control de equipos en peligro en una botnet
- Interrupción de aplicaciones legítimas
- Propagar malware, como ransomware

El componente de protección de red de Defender para punto de conexión identifica y bloquea las conexiones a las infraestructuras C2 usadas en ataques de ransomware operados por personas, mediante técnicas como el aprendizaje automático y la identificación inteligente del indicador de riesgo (IoC).

#### <a name="network-protection-c2-detection-and-remediation"></a>Protección de red: detección y corrección de C2

En su forma inicial, ransomware es una amenaza de mercancía, preprogramada y centrada en resultados limitados y específicos (por ejemplo, el cifrado de un equipo). Sin embargo, el ransomware ha evolucionado hasta convertirse en una amenaza sofisticada controlada por el ser humano, adaptable y centrada en resultados a mayor escala y más extendidos, como mantener los recursos o datos de toda una organización para el rescate.

La compatibilidad con servidores de comandos y control (C2) es una parte clave de esta evolución de ransomware y es lo que permite que estos ataques se adapten al entorno al que se dirigen. La interrupción del vínculo a la infraestructura de comandos y control detiene la progresión de un ataque a su siguiente fase. Para obtener más información sobre la detección y corrección de C2, consulte [Detección y corrección de ataques de comando y control en la capa de red](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/detecting-and-remediating-command-and-control-attacks-at-the/ba-p/3650607).

#### <a name="network-protection-new-toast-notifications"></a>Protección de red: nuevas notificaciones del sistema

| Nueva asignación  | Categoría de respuesta  | Fuentes |
| :--- | :--- | :--- |
| suplantación de identidad (phishing) | Suplantación de identidad (phishing) | SmartScreen |
| Maliciosos | Malintencionado | SmartScreen |
| comando y control | C2 | SmartScreen |
| comando y control | COCO | SmartScreen |
| Maliciosos | Untrusted | SmartScreen |
| por el administrador de TI | CustomBlockList |   |
| por el administrador de TI | CustomPolicy |   |

> [!NOTE]
> **customAllowList** no genera notificaciones en los puntos de conexión.

### <a name="new-notifications-for-network-protection-determination"></a>Nuevas notificaciones para la determinación de la protección de red

Una nueva funcionalidad disponible públicamente en la protección de red usa funciones en SmartScreen para bloquear las actividades de suplantación de identidad (phishing) de sitios de control y comandos malintencionados.

Cuando un usuario final intenta visitar un sitio web en un entorno en el que está habilitada la protección de red, son posibles tres escenarios:

- La dirección URL tiene una **buena reputación conocida** : en este caso, el usuario tiene acceso permitido sin obstrucción y no se presenta ninguna notificación del sistema en el punto de conexión. De hecho, el dominio o la dirección URL se establecen en _Permitido_.
- La dirección URL tiene una **reputación desconocida o incierta** : el acceso del usuario está bloqueado, pero con la capacidad de eludir (desbloquear) el bloque. De hecho, el dominio o la dirección URL se establece en _Auditar_.
- La dirección URL tiene una **reputación mal conocida (malintencionada):** se impide el acceso al usuario. De hecho, el dominio o la dirección URL se establece en _Bloquear_.

#### <a name="warn-experience"></a>Experiencia de advertencia

Un usuario visita un sitio web:

- Si la dirección URL tiene una reputación desconocida o incierta, una notificación del sistema presentará al usuario las siguientes opciones:

  - **Aceptar** : la notificación del sistema se publica (se quita) y el intento de acceder al sitio finaliza.
  - **Desbloquear**: el usuario no tendrá que acceder al portal Windows Defender Security Intelligence (WDSI) para obtener acceso al sitio. El usuario tendrá acceso al sitio durante 24 horas; momento en el que el bloque se vuelve a habilitar durante otras 24 horas. El usuario puede seguir usando **Desbloquear** para acceder al sitio hasta el momento en que el administrador prohíba (bloquea) el sitio, lo que elimina la opción **de Desbloquear**.
  - **Comentarios** : la notificación del sistema presenta al usuario un vínculo para enviar una incidencia, que el usuario puede usar para enviar comentarios al administrador en un intento de justificar el acceso al sitio.

    :::image type="content" source="images/network-protection-phishing-warn-2.png" alt-text="Muestra una notificación de advertencia de contenido de phishing de protección de red.":::

  > [!NOTE]
  > Las imágenes que se muestran aquí para la experiencia de advertencia y la experiencia de bloqueo (a continuación) muestran **"url bloqueada"** como texto de marcador de posición de ejemplo; en un entorno que funciona, se mostrará la dirección URL o el dominio reales.  

#### <a name="block-experience"></a>Experiencia en bloques

Un usuario visita un sitio web:

- Si la dirección URL tiene mala reputación, una notificación del sistema presentará al usuario las siguientes opciones:
  - **Vale** La notificación del sistema se publica (quita) y finaliza el intento de acceder al sitio.
  - **Comentarios** La notificación del sistema presenta al usuario un vínculo para enviar una incidencia, que el usuario puede usar para enviar comentarios al administrador en un intento de justificar el acceso al sitio.

    :::image type="content" source="images/network-protection-phishing-blocked.png" alt-text="Muestra una notificación de bloqueo de contenido de phishing conocido de protección de red." lightbox="images/network-protection-phishing-blocked.png":::

## <a name="smartscreen-unblock"></a>Desbloqueo de SmartScreen

Con los indicadores de Defender para punto de conexión, los administradores pueden permitir que los usuarios finales omitan las advertencias que se generan para algunas direcciones URL e direcciones IP. En función de por qué se bloqueó la dirección URL, cuando se encuentra un bloque SmartScreen, puede ofrecer a los administradores la capacidad de desbloquear el sitio durante un máximo de 24 horas. En tales casos, aparecerá una notificación del sistema de Seguridad de Windows, lo que permite al usuario final **desbloquear** la dirección URL o la dirección IP durante el período de tiempo definido.  

:::image type="content" source="images/network-protection-smart-screen-block-notification.png" alt-text="Seguridad de Windows notificación para la protección de red.":::

Microsoft Defender para punto de conexión administradores pueden configurar la funcionalidad Desbloquee SmartScreen en el [portal de Microsoft 365 Defender](https://security.microsoft.com) mediante un indicador de "permitir" para direcciones IP, direcciones URL y dominios.

:::image type="content" source="images/network-protection-smart-screen-block-configuration.png" alt-text="SmartScreen de protección de red bloquea la configuración de ULR y el formulario IP.":::

Consulte [Creación de indicadores para direcciones IP y direcciones URL/dominios](indicator-ip-domain.md).

## <a name="using-network-protection"></a>Uso de la protección de red

La protección de red está habilitada por dispositivo, que normalmente se realiza mediante la infraestructura de administración. Para ver los métodos admitidos, consulte [Activar la protección de red](enable-network-protection.md).

> [!NOTE]
> Microsoft Defender Antivirus debe estar activo para habilitar la protección de red.

Puede habilitar la protección de red en modo **auditoría** o **modo de bloqueo** . Si desea evaluar el impacto de habilitar la protección de red antes de bloquear realmente direcciones IP o direcciones URL, puede habilitar la protección de red en el modo auditoría durante el tiempo necesario para recopilar datos sobre lo que se bloquearía. Registros de modo de auditoría cuando los usuarios finales se han conectado a una dirección o sitio que, de lo contrario, habrían sido bloqueados por la protección de red. Tenga en cuenta que para que los indicadores de peligro (IoC) o el filtrado de contenido web (WCF) funcionen, la protección de red debe estar en "Modo de bloqueo".

Para obtener información sobre la protección de red para Linux y macOS, consulte Protección [de red para Linux](network-protection-linux.md) y [Protección de red para macOS](network-protection-macos.md).

## <a name="advanced-hunting"></a>Búsqueda avanzada de amenazas

Si usa la búsqueda avanzada para identificar eventos de auditoría, tendrá un historial de hasta 30 días disponible en la consola. Consulte [Búsqueda avanzada](advanced-hunting-overview.md).

Puede encontrar los datos de auditoría en **Búsqueda avanzada** en el portal de Defender para punto de conexión ([https://security.microsoft.com](https://security.microsoft.com)).  

Los eventos se encuentran en DeviceEvents con un ActionType de `ExploitGuardNetworkProtectionAudited`. Los bloques se muestran mediante `ExploitGuardNetworkProtectionBlocked`.  

En el ejemplo siguiente se incluyen las acciones bloqueadas:

```kusto

DeviceEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')

```

:::image type="content" source="images/network-protection-advanced-hunting.png" alt-text="Búsqueda avanzada de eventos de auditoría e identificación." lightbox="images/network-protection-advanced-hunting.png":::

> [!TIP]
> Estas entradas tienen datos en la columna **AdditionalFields** , lo que proporciona una gran información sobre la acción; si expande **AdditionalFields** , también puede obtener los campos **IsAudit**, **ResponseCategory** y **DisplayName**.

Este es otro ejemplo:

```kusto

DeviceEvents:

|where ActionType contains "ExploitGuardNetworkProtection"
|extend ParsedFields=parse_json(AdditionalFields)
|project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, IsAudit=tostring(ParsedFields.IsAudit), ResponseCategory=tostring(ParsedFields.ResponseCategory), DisplayName=tostring(ParsedFields.DisplayName)
|sort by Timestamp desc

```

La categoría Respuesta indica qué causó el evento, por ejemplo:

| ResponseCategory | Característica responsable del evento |
|:---|:---|
| CustomPolicy |  Wcf  |
| CustomBlockList  |   Indicadores personalizados   |
| CasbPolicy   |   Defender for Cloud Apps   |
| Malintencionado   |   Amenazas web  |
| Suplantación de identidad (phishing)  |   Amenazas web  |

Para obtener más información, consulte [Solución de problemas de bloques de puntos de conexión](web-protection-overview.md#troubleshoot-endpoint-blocks).

Puede usar la lista resultante de direcciones URL e direcciones IP para determinar qué se habría bloqueado si el dispositivo estuviera en modo de bloque y qué característica las bloqueó. Revise cada elemento de la lista para identificar direcciones URL o direcciones IP si son necesarias para su entorno. Si encuentra entradas auditadas que son críticas para su entorno, cree un indicador para permitirlas en la red. Los indicadores de dirección URL/IP permitidos tienen prioridad sobre cualquier bloque.

Una vez que haya creado un indicador, puede examinar la resolución del problema subyacente:

- SmartScreen: revisión de solicitudes
- Indicador: modificación del indicador existente
- MCA: revisión de una aplicación no autorizada
- WCF: recategorización de solicitudes

Con estos datos, puede tomar una decisión informada sobre la habilitación de la protección de red en modo de bloque. Consulte [Orden de precedencia de los bloques de protección de red](web-protection-overview.md#order-of-precedence).

> [!NOTE]
> Dado que se trata de una configuración por dispositivo si hay dispositivos que no pueden pasar al modo de bloqueo, simplemente puede dejarlos en auditoría hasta que pueda rectificar el desafío y seguirá recibiendo los eventos de auditoría.

Para obtener información sobre cómo notificar falsos positivos, vea [Notificar falsos positivos](web-protection-overview.md#report-false-positives).

Para obtener más información sobre cómo crear sus propios informes de Power BI, consulte [Creación de informes personalizados con Power BI](api-power-bi.md).

## <a name="configuring-network-protection"></a>Configuración de la protección de red

Para obtener más información sobre cómo habilitar la protección de red, consulte **[Habilitación de la protección de red](enable-network-protection.md)**. Use los CSP de directiva de grupo, PowerShell o MDM para habilitar y administrar la protección de red en la red.

Después de habilitar los servicios, es posible que tenga que configurar la red o el firewall para permitir las conexiones entre los servicios y los dispositivos (también conocidos como puntos de conexión).

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="viewing-network-protection-events"></a>Visualización de eventos de protección de red

La protección de red funciona mejor con [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md), lo que proporciona informes detallados sobre eventos y bloques de protección contra vulnerabilidades como parte de [escenarios de investigación de alertas](investigate-alerts.md).

Cuando la protección de red bloquea una conexión, se muestra una notificación desde el Centro de acciones. El equipo de operaciones de seguridad puede [personalizar la notificación con los](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) detalles de la organización y la información de contacto. Además, las reglas de reducción de superficie expuesta a ataques individuales se pueden habilitar y personalizar para adaptarse a ciertas técnicas de supervisión.

También puede usar [el modo de auditoría](audit-windows-defender.md) para evaluar cómo afectaría la protección de red a su organización si estuviera habilitada.

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>Revisión de eventos de protección de red en el portal de Microsoft 365 Defender

Defender para punto de conexión proporciona informes detallados sobre eventos y bloques como parte de sus [escenarios de investigación de alertas](investigate-alerts.md). Puede ver estos detalles en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) de la cola de [alertas](review-alerts.md) o mediante la [búsqueda avanzada](advanced-hunting-overview.md). Si usa el [modo de auditoría](audit-windows-defender.md), puede usar la búsqueda avanzada para ver cómo afectaría la configuración de protección de red a su entorno si estuvieran habilitadas.

Esta es una consulta de ejemplo para la búsqueda avanzada:

```kusto

DeviceNetworkEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')

```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revise los eventos de protección de red en Windows Visor de eventos

Puede revisar el registro de eventos de Windows para ver los eventos que se crean cuando la protección de red bloquea (o audita) el acceso a una dirección IP o dominio malintencionados:

1. [Copie el XML directamente](event-views.md).

2. Seleccione **Aceptar**.

Este procedimiento crea una vista personalizada que filtra para mostrar solo los siguientes eventos relacionados con la protección de red:

|Id. de evento|Descripción|
|---|---|
|5007|Evento cuando se cambia la configuración|
|1125|Evento cuando se activa la protección de red en modo de auditoría|
|1126|Evento cuando se activa la protección de red en modo de bloque|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>Protección de red y protocolo de enlace de tres vías TCP

Con la protección de red, la determinación de si permitir o bloquear el acceso a un sitio se realiza después de la finalización del [protocolo de enlace triple a través de TCP/IP](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip). Por lo tanto, cuando la protección de red bloquea un sitio, es posible que vea un tipo de acción de `ConnectionSuccess` `NetworkConnectionEvents` en en el portal de Microsoft 365 Defender, aunque el sitio esté bloqueado. `NetworkConnectionEvents` se notifican desde la capa TCP y no desde la protección de red. Una vez completado el protocolo de enlace triple, la protección de red permite o bloquea el acceso al sitio.

Este es un ejemplo de cómo funciona:

1. Supongamos que un usuario intenta acceder a un sitio web en su dispositivo. El sitio se hospeda en un dominio peligroso y debe estar bloqueado por la protección de red.  

2. Comienza el protocolo de enlace triple a través de TCP/IP. Antes de que se complete, se registra una `NetworkConnectionEvents` acción y su `ActionType` aparece como `ConnectionSuccess`. Sin embargo, tan pronto como se complete el proceso de protocolo de enlace de tres vías, la protección de red bloquea el acceso al sitio. Todo esto sucede rápidamente. Se produce un proceso similar con [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview); es cuando se completa el protocolo de enlace triple que se realiza una determinación y se bloquea o se permite el acceso a un sitio.

3. En el portal de Microsoft 365 Defender, se muestra una alerta en la cola de [alertas](alerts-queue.md). Los detalles de esa alerta incluyen tanto `NetworkConnectionEvents` como `AlertEvents`. Puede ver que el sitio se bloqueó, aunque también tenga un `NetworkConnectionEvents` elemento con actiontype de `ConnectionSuccess`.

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Consideraciones para el escritorio virtual Windows que ejecuta Windows 10 Enterprise multisesión

Debido a la naturaleza multiusuario de Windows 10 Enterprise, tenga en cuenta los siguientes puntos:

1. La protección de red es una característica de todo el dispositivo y no se puede dirigir a sesiones de usuario específicas.

2. Las directivas de filtrado de contenido web también están en todo el dispositivo.

3. Si necesita diferenciar entre grupos de usuarios, considere la posibilidad de crear asignaciones y grupos de hosts de Windows Virtual Desktop independientes.

4. Pruebe la protección de red en modo de auditoría para evaluar su comportamiento antes de su implementación.

5. Considere la posibilidad de cambiar el tamaño de la implementación si tiene un gran número de usuarios o un gran número de sesiones de varios usuarios.

### <a name="alternative-option-for-network-protection"></a>Opción alternativa para la protección de red

Para el cliente MDE unificado de Windows Server 2012R2/2016, Windows Server versión 1803 o posterior, Windows Server 2019 o posterior, y Windows 10 Enterprise Multi-Session 1909 y versiones posteriores, que se usan en Windows Virtual Desktop en Azure, la protección de red para Microsoft Edge se puede habilitar mediante el método siguiente:

1. Use [Activar la protección de red](enable-network-protection.md) y siga las instrucciones para aplicar la directiva.

2. Ejecute los siguientes comandos de PowerShell:

   - `Set-MpPreference -EnableNetworkProtection Enabled`
   - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
   - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
   - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

> [!NOTE]
> En algunos casos, dependiendo de la infraestructura, el volumen de tráfico y otras condiciones, `Set-MpPreference -AllowDatagramProcessingOnWinServer 1` pueden tener un efecto en el rendimiento de la red.

### <a name="network-protection-for-windows-servers"></a>Protección de red para servidores Windows Server

A continuación se muestra información específica de Servidores Windows.

#### <a name="verify-that-network-protection-is-enabled"></a>Comprobación de que la protección de red está habilitada

Compruebe si la protección de red está habilitada en un dispositivo local mediante el Editor del Registro.

1. Seleccione el botón **Iniciar** en la barra de tareas y escriba **regedit** para abrir el Editor del Registro.
1. Seleccione **HKEY_LOCAL_MACHINE** en el menú lateral.
1. Navegue por los menús anidados a **Directivas** >  **de SOFTWARE** > **Microsoft** > **Windows Defender** >  **Windows Defender Protección de red de Protección contra vulnerabilidades** >  de **seguridad**.

   (Si la clave no está presente, vaya a **SOFTWARE.** >  **Microsoft** >   >  Windows Defender **Windows Defender Protección contra vulnerabilidades de seguridad** > **de red**)

4. Seleccione **EnableNetworkProtection** para ver el estado actual de la protección de red en el dispositivo:

   - 0 = Desactivado
   - 1 = Activado (habilitado)
   - 2 = Modo auditoría

Para obtener más información, consulte: [Activar la protección de red](enable-network-protection.md).

##### <a name="network-protection-suggestion"></a>Sugerencia de protección de red

Para el cliente MDE unificado de Windows Server 2012R2/2016, Windows Server versión 1803 o posterior, Windows Server 2019 o posterior, y Windows 10 Enterprise Multi-Session 1909 y versiones posteriores (que se usan en Windows Virtual Desktop en Azure), hay claves del Registro adicionales que deben estar habilitadas:

**HKEY_LOCAL_MACHINE**\* *SOFTWARE**\** Directivas **\**Microsoft**\* *Windows Defender**\** Windows Defender Protección contra vulnerabilidades de seguridad **\**Protección de red**

**AllowNetworkProtectionDownLevel** (dword) 1 (hexadecimal) **AllowNetworkProtectionOnWinServer** (dword) 1 (hexadecimal) **EnableNetworkProtection** (dword) 1 (hexadecimal)

> [!NOTE]
> En función de la infraestructura, el volumen del tráfico y otras condiciones, **HKEY_LOCAL_MACHINE**\\**directivas**\\\\**de SOFTWARE**\\**Microsoft**\\ **Windows Defender** \\**IPS** de **los consumidores** **NIS**\\ - **AllowDatagramProcessingOnWinServer (dword) 1 (hexadecimal)** puede tener un efecto en el rendimiento de la red.

Para obtener más información, consulte: [Activar la protección de red](enable-network-protection.md).

#### <a name="windows-servers-and-windows-multi-session-configuration-requires-powershell"></a>La configuración de servidores Windows y windows multisesión requiere PowerShell

En el caso de los servidores Windows y las sesiones múltiples de Windows, hay elementos adicionales que debe habilitar mediante cmdlets de PowerShell. Para el cliente MDE unificado de Windows Server 2012R2/2016, Windows Server versión 1803 o posterior, Windows Server 2019 o posterior, y Windows 10 Enterprise Multi-Session 1909 y versiones posteriores, que se usan en Windows Virtual Desktop en Azure.

1. Set-MpPreference -EnableNetworkProtection habilitado
1. Set-MpPreference -AllowNetworkProtectionOnWinServer 1
1. Set-MpPreference -AllowNetworkProtectionDownLevel 1
1. Set-MpPreference -AllowDatagramProcessingOnWinServer 1

> [!NOTE]
> En algunos casos, en función de la infraestructura, el volumen del tráfico y otras condiciones, **Set-MpPreference -AllowDatagramProcessingOnWinServer 1** puede tener un efecto en el rendimiento de la red.


## <a name="network-protection-troubleshooting"></a>Solución de problemas de protección de red

Debido al entorno donde se ejecuta la protección de red, es posible que Microsoft no pueda detectar la configuración del proxy del sistema operativo. En algunos casos, los clientes de protección de red no pueden acceder al servicio en la nube. Para resolver el problema de conectividad, [configure un proxy estático para Microsoft Defender Antivirus](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus).

## <a name="optimizing-network-protection-performance"></a>Optimización del rendimiento de la protección de red

La protección de red ahora tiene una optimización del rendimiento que permite al modo de bloqueo iniciar la inspección asincrónica de conexiones largas después de que SmartScreen las valide y permita, lo que podría proporcionar una posible reducción del costo que la inspección tiene en el ancho de banda y también puede ayudar con los problemas de compatibilidad de aplicaciones. Esta funcionalidad de optimización está activada de forma predeterminada. Puede desactivar esta funcionalidad mediante el siguiente cmdlet de PowerShell:

`Set-MpPreference -AllowSwitchToAsyncInspection $false`

## <a name="see-also"></a>Vea también

- [Evaluación de la protección de red](evaluate-network-protection.md) | Realice un escenario rápido que muestre cómo funciona la característica y qué eventos se crearían normalmente.
- [Habilitar la protección de red](enable-network-protection.md) | Use los CSP de directiva de grupo, PowerShell o MDM para habilitar y administrar la protección de red en la red.
- [Configuración de capacidades de reducción de superficie expuesta a ataques en Microsoft Intune](/mem/intune/protect/endpoint-security-asr-policy)
- [Protección de red para linux](network-protection-linux.md) | Para obtener información sobre el uso de la protección de Microsoft Network para dispositivos Linux.
- [Protección de red para macOS](network-protection-macos.md) | Para obtener más información sobre la protección de red de Microsoft para macOS
