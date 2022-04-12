---
title: Uso de la protección de red para evitar conexiones a sitios incorrectos
description: Proteja la red evitando que los usuarios accedan a direcciones de red malintencionadas y sospechosas conocidas.
keywords: Protección de red, vulnerabilidades de seguridad, sitio web malintencionado, ip, dominio, dominios
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: ''
ms.openlocfilehash: f58c7afe9c6f532f7f6420d58bcd681778483680
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789346"
---
# <a name="protect-your-network"></a>Proteger la red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="overview-of-network-protection"></a>Introducción a la protección de red

La protección de red ayuda a proteger los dispositivos frente a eventos basados en Internet. La protección de red es una capacidad de reducción de la superficie expuesta a ataques. Ayuda a evitar que los empleados accedan a dominios peligrosos a través de aplicaciones. Los dominios que hospedan estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet se consideran peligrosos. La protección de red expande el ámbito de [SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) para bloquear todo el tráfico HTTP saliente que intenta conectarse a orígenes de baja reputación (en función del dominio o el nombre de host).

La protección de red amplía la protección de la [protección web](web-protection-overview.md) al nivel del sistema operativo. Proporciona funcionalidad de protección web en Edge a otros exploradores y aplicaciones que no son de explorador compatibles. Además, la protección de red proporciona visibilidad y bloqueo de indicadores de riesgo (IOC) cuando se usa con [la detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md). Por ejemplo, la protección de red funciona con [los indicadores personalizados](manage-indicators.md) que puede usar para bloquear dominios o nombres de host específicos.

> [!TIP]
> Consulte Microsoft Defender para punto de conexión sitio de prueba en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para ver cómo funciona la protección de red.

> [!NOTE]
> El sitio de demostración de Defender para punto de conexión en demo.wd.microsoft.com está obsoleto y se eliminará en el futuro.

## <a name="requirements-for-network-protection"></a>Requisitos para la protección de red

La protección de red requiere Windows 10 Pro o Enterprise y Antivirus de Microsoft Defender protección en tiempo real.

<br>

****

|Versión de Windows|Antivirus de Microsoft Defender|
|---|---|
|Windows 10 versión 1709 o posterior <p> Windows 11 <p> Windows Server 1803 o posterior|[Antivirus de Microsoft Defender protección en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md) y [protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) deben estar habilitadas|
|

Después de habilitar los servicios, es posible que deba configurar la red o el firewall para permitir las conexiones entre los servicios y los dispositivos (también denominados puntos de conexión).

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="configuring-network-protection"></a>Configuración de la protección de red

Para obtener más información sobre cómo habilitar la protección de red, consulte **[Habilitación de la protección de red](enable-network-protection.md)**. Use los CSP de directiva de grupo, PowerShell o MDM para habilitar y administrar la protección de red en la red.

## <a name="viewing-network-protection-events"></a>Visualización de eventos de protección de red

La protección de red funciona mejor con [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md), lo que proporciona informes detallados sobre eventos y bloques de protección contra vulnerabilidades como parte de [escenarios de investigación de alertas](investigate-alerts.md).

Cuando la protección de red bloquea una conexión, se muestra una notificación desde el Centro de acciones. El equipo de operaciones de seguridad puede [personalizar la notificación con los](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) detalles de la organización y la información de contacto. Además, las reglas de reducción de superficie expuesta a ataques individuales se pueden habilitar y personalizar para adaptarse a ciertas técnicas de supervisión.

También puede usar [el modo de auditoría](audit-windows-defender.md) para evaluar cómo afectaría la protección de red a su organización si estuviera habilitada.

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>Revisión de eventos de protección de red en el portal de Microsoft 365 Defender

Microsoft Defender para punto de conexión proporciona informes detallados sobre eventos y bloques como parte de sus escenarios de investigación de [alertas](investigate-alerts.md). Puede ver estos detalles en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) de la cola de [alertas](review-alerts.md) o mediante la [búsqueda avanzada](advanced-hunting-overview.md). Si usa el [modo de auditoría](audit-windows-defender.md), puede usar la búsqueda avanzada para ver cómo afectaría la configuración de protección de red a su entorno si estuvieran habilitadas.

Esta es una consulta de ejemplo para la búsqueda avanzada:

```kusto
DeviceNetworkEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked', 'ConnectionSuccess')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revisión de eventos de protección de red en Windows Visor de eventos

Puede revisar el registro de eventos Windows para ver los eventos que se crean cuando la protección de red bloquea (o audita) el acceso a una dirección IP o dominio malintencionados:

1. [Copie el XML directamente](event-views.md).

2. Seleccione **Aceptar**.

Este procedimiento crea una vista personalizada que filtra para mostrar solo los siguientes eventos relacionados con la protección de red:

<br>

****

|Id. de evento|Descripción|
|---|---|
|5007|Evento cuando se cambia la configuración|
|1125|Evento cuando se activa la protección de red en modo de auditoría|
|1126|Evento cuando se activa la protección de red en modo de bloque|
|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>Protección de red y protocolo de enlace de tres vías TCP

Con la protección de red, la determinación de si permitir o bloquear el acceso a un sitio se realiza después de la finalización del [protocolo de enlace triple a través de TCP/IP](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip). Por lo tanto, cuando la protección de red bloquea un sitio, es posible que vea un tipo de acción de `ConnectionSuccess` `NetworkConnectionEvents` en en el portal de Microsoft 365 Defender, aunque el sitio se haya bloqueado realmente. `NetworkConnectionEvents` se notifican desde la capa TCP y no desde la protección de red. Una vez completado el protocolo de enlace triple, la protección de red permite o bloquea el acceso al sitio.

Este es un ejemplo de cómo funciona:

1. Supongamos que un usuario intenta acceder a un sitio web en su dispositivo. El sitio se hospeda en un dominio peligroso y debe estar bloqueado por la protección de red.  

2. Comienza el protocolo de enlace triple a través de TCP/IP. Antes de que se complete, se registra una `NetworkConnectionEvents` acción y su `ActionType` aparece como `ConnectionSuccess`. Sin embargo, tan pronto como se complete el proceso de protocolo de enlace de tres vías, la protección de red bloquea el acceso al sitio. Todo esto sucede muy rápidamente. Se produce un proceso similar con [SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview); es cuando se completa el protocolo de enlace triple que se realiza una determinación y se bloquea o se permite el acceso a un sitio.

3. En el portal de Microsoft 365 Defender, se muestra una alerta en la cola de [alertas](alerts-queue.md). Los detalles de esa alerta incluyen tanto `NetworkConnectionEvents` como `AlertEvents`. Puede ver que el sitio se bloqueó, aunque también tenga un `NetworkConnectionEvents` elemento con actiontype de `ConnectionSuccess`.

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Consideraciones para Windows escritorio virtual que ejecuta Windows 10 Enterprise sesión múltiple

Debido a la naturaleza multiusuario de Windows 10 Enterprise, tenga en cuenta los siguientes puntos:

1. La protección de red es una característica de todo el dispositivo y no se puede dirigir a sesiones de usuario específicas.

2. Las directivas de filtrado de contenido web también están en todo el dispositivo.

3. Si necesita diferenciar entre grupos de usuarios, considere la posibilidad de crear asignaciones y grupos de hosts de Virtual Desktop independientes Windows.

4. Pruebe la protección de red en modo de auditoría para evaluar su comportamiento antes de su implementación.

5. Considere la posibilidad de cambiar el tamaño de la implementación si tiene un gran número de usuarios o un gran número de sesiones de varios usuarios.

### <a name="alternative-option-for-network-protection"></a>Opción alternativa para la protección de red

Para Windows 10 Enterprise multisesión 1909 o posterior, que se usa en Windows Virtual Desktop en Azure, la protección de red para Microsoft Edge se puede habilitar mediante el método siguiente:

1. Use [Activar la protección de red](enable-network-protection.md) y siga las instrucciones para aplicar la directiva.

2. Ejecute los siguientes comandos de PowerShell:
  - `Set-MpPreference -EnableNetworkProtection Enabled`
  - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
  - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
  - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>Solución de problemas de protección de red

Debido al entorno donde se ejecuta la protección de red, es posible que Microsoft no pueda detectar la configuración del proxy del sistema operativo. En algunos casos, los clientes de protección de red no pueden acceder a Cloud Service. Para resolver el problema de conectividad, los clientes con licencias E5 deben configurar una de las siguientes claves del Registro:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="see-also"></a>Vea también

- [Evaluación de la protección de red](evaluate-network-protection.md) | Realice un escenario rápido que muestre cómo funciona la característica y qué eventos se crearían normalmente.
- [Habilitar la protección de red](enable-network-protection.md) | Use los CSP de directiva de grupo, PowerShell o MDM para habilitar y administrar la protección de red en la red.
- [Configuración de capacidades de reducción de superficie expuesta a ataques en Microsoft Intune](/mem/intune/protect/endpoint-security-asr-policy)
