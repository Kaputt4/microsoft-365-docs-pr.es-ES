---
title: Usar la protección de red para ayudar a evitar conexiones a sitios con problemas
description: Proteger la red evitando que los usuarios accedan a direcciones de red malintencionadas y sospechosas conocidas
keywords: Protección de red, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.openlocfilehash: 44f75b2912a8e54df6584a8f97d0f6e76cac6b15
ms.sourcegitcommit: ea4bc3b005d86b029700e56015a47b8cc6dca2a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2021
ms.locfileid: "58509874"
---
# <a name="protect-your-network"></a>Proteger la red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="overview-of-network-protection"></a>Información general sobre la protección de red

La protección de red ayuda a proteger los dispositivos de eventos basados en Internet. La protección de red es una capacidad de reducción de superficie de ataque. Ayuda a evitar que los empleados accedan a dominios peligrosos a través de aplicaciones. Los dominios que hospedan estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet se consideran peligrosos. La protección de red expande el ámbito de [SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) para bloquear todo el tráfico HTTP saliente que intente conectarse a orígenes de reputación baja (según el dominio o el nombre de host).

La protección de red amplía la protección de [la protección web](web-protection-overview.md) al nivel del sistema operativo. Proporciona funcionalidad de protección web en Edge a otros exploradores compatibles y aplicaciones que no son exploradores. Además, la protección de red proporciona visibilidad y bloqueo de indicadores de peligro (IIC) cuando se usa con detección [y respuesta de extremos.](overview-endpoint-detection-response.md) Por ejemplo, la protección de red funciona con los indicadores [personalizados](manage-indicators.md) que puede usar para bloquear dominios o nombres de host específicos.

> [!TIP]
> Consulta el sitio de prueba de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para ver cómo funciona la protección de red.

## <a name="requirements-for-network-protection"></a>Requisitos para la protección de red

La protección de red Windows 10 Pro o Enterprise y Antivirus de Microsoft Defender protección en tiempo real.

<br>

****

|Versión de Windows|Antivirus de Microsoft Defender|
|---|---|
|Windows 10 versión 1709 o posterior <p> Windows Servidor 1803 o posterior|[Antivirus de Microsoft Defender la protección en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md) y la protección [en](enable-cloud-protection-microsoft-defender-antivirus.md) la nube deben estar habilitadas|
|

Después de habilitar los servicios, es posible que deba configurar la red o firewall para permitir las conexiones entre los servicios y los dispositivos (también denominados puntos de conexión).

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="configuring-network-protection"></a>Configuración de la protección de red

Para obtener más información acerca de cómo habilitar la protección de red, vea **[Enable network protection](enable-network-protection.md)**. Use directivas de grupo, PowerShell o CSP mdm para habilitar y administrar la protección de red en la red.

## <a name="viewing-network-protection-events"></a>Visualización de eventos de protección de red

La protección de red funciona mejor con [Microsoft Defender para endpoint,](microsoft-defender-endpoint.md)lo que le ofrece informes detallados sobre eventos y bloques de protección contra vulnerabilidades como parte de escenarios de [investigación de alertas.](investigate-alerts.md)

Cuando la protección de red bloquea una conexión, se muestra una notificación desde el Centro de acciones. El equipo de operaciones de seguridad [puede personalizar la notificación](customize-attack-surface-reduction.md#customize-the-notification) con los detalles de la organización y la información de contacto. Además, las reglas de reducción de superficie de ataque individuales se pueden habilitar y personalizar para adaptarse a determinadas técnicas que se deben supervisar.

También puede usar el modo [de auditoría para](audit-windows-defender.md) evaluar cómo afectaría la protección de red a su organización si estuviera habilitada.

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>Revisar los eventos de protección de red en el portal de Microsoft 365 Defender web

Microsoft Defender para endpoint proporciona informes detallados sobre eventos y bloques como parte de sus escenarios de [investigación de alertas.](investigate-alerts.md) Puede ver estos detalles en el portal de Microsoft 365 Defender ( ) en la cola de alertas [https://security.microsoft.com](https://security.microsoft.com) o mediante la búsqueda [avanzada](advanced-hunting-overview.md). [](review-alerts.md) Si usa el modo [de auditoría,](audit-windows-defender.md)puede usar la búsqueda avanzada para ver cómo la configuración de protección de red afectaría al entorno si estuvieran habilitadas.

Esta es una consulta de ejemplo para la búsqueda avanzada:

```kusto
DeviceEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revisar eventos de protección de red en Windows visor de eventos

Puede revisar el registro Windows eventos para ver los eventos que se crean cuando la protección de red bloquea (o audita) el acceso a una IP o dominio malintencionado:

1. [Copie el XML directamente](event-views.md).

2. Seleccione **Aceptar**.

Este procedimiento crea una vista personalizada que filtra para mostrar solo los siguientes eventos relacionados con la protección de red:

<br>

****

|Id. de evento|Descripción|
|---|---|
|5007|Evento cuando se cambia la configuración|
|1125|Evento cuando la protección de red se dispara en modo auditoría|
|1126|Evento cuando la protección de red se desen llamas en modo de bloqueo|
|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>Protección de red y el protocolo de enlace triple TCP

Con la protección de red, la determinación de si se permite o bloquea el acceso a un sitio se realiza después de la finalización del protocolo de enlace triple a través de [TCP/IP](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip). Por lo tanto, cuando la protección de red bloquea un sitio, es posible que vea un tipo de acción debajo en el portal de Microsoft 365 Defender, aunque el sitio se haya `ConnectionSuccess` `NetworkConnectionEvents` bloqueado realmente. `NetworkConnectionEvents` se notifican desde la capa TCP y no desde la protección de red. Una vez completado el protocolo de enlace triple, la protección de red permite o bloquea el acceso al sitio.

Este es un ejemplo de cómo funciona:

1. Supongamos que un usuario intenta acceder a un sitio web en su dispositivo. El sitio se hospeda en un dominio peligroso y la protección de red debe bloquearlo.  

2. Comienza el protocolo de enlace triple a través de TCP/IP. Antes de que se complete, se registra una acción `NetworkConnectionEvents` y su aparece como `ActionType` `ConnectionSuccess` . Sin embargo, tan pronto como se complete el proceso de protocolo de enlace triple, la protección de red bloquea el acceso al sitio. Todo esto sucede muy rápidamente. Se produce un proceso similar con [SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview); es cuando se completa el protocolo de enlace triple que se determina y se bloquea o se permite el acceso a un sitio.

3. En el portal Microsoft 365 Defender, una alerta aparece en la cola [de alertas](alerts-queue.md). Los detalles de esa alerta incluyen ambos `NetworkConnectionEvents` y `AlertEvents` . Puede ver que el sitio se bloqueó, aunque también tenga un `NetworkConnectionEvents` elemento con actiontype de `ConnectionSuccess` .

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Consideraciones para Windows escritorio virtual que se Windows 10 Enterprise multi-sesión

Debido a la naturaleza de varios usuarios de Windows 10 Enterprise, tenga en cuenta los siguientes puntos:

1. La protección de red es una característica de todo el dispositivo y no se puede dirigir a sesiones de usuario específicas.

2. Las directivas de filtrado de contenido web también están en todo el dispositivo.

3. Si necesita diferenciar entre grupos de usuarios, considere la posibilidad de crear asignaciones Windows grupos de host de Escritorio virtual.

4. Pruebe la protección de red en modo auditoría para evaluar su comportamiento antes de implementarla.

5. Considere la posibilidad de redimensionar la implementación si tiene un gran número de usuarios o un gran número de sesiones de varios usuarios.

### <a name="alternative-option-for-network-protection"></a>Opción alternativa para la protección de red

Para Windows 10 Enterprise Multi-Session 1909 y versiones 2010, que se usan en Windows Virtual Desktop en Azure, la protección de red para Microsoft Edge puede habilitarse mediante el siguiente método:

1. Use [Activar la protección de red](enable-network-protection.md) y siga las instrucciones para aplicar la directiva.

2. Ejecute el siguiente comando de PowerShell: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>Solución de problemas de protección de red

Debido al entorno donde se ejecuta la protección de red, Es posible que Microsoft no pueda detectar la configuración de proxy del sistema operativo. En algunos casos, los clientes de protección de red no pueden llegar al servicio en la nube. Para resolver el problema de conectividad, los clientes con licencias E5 deben configurar una de las siguientes claves del Registro de Defender:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="see-also"></a>Ver también

- [Evaluar la protección de](evaluate-network-protection.md) red | Realice un escenario rápido que demuestre cómo funciona la característica y qué eventos se crearían normalmente.
- [Habilitar la protección de](enable-network-protection.md) red | Use directivas de grupo, PowerShell o CSP mdm para habilitar y administrar la protección de red en la red.
- [Configuración de capacidades de reducción de superficie de ataque en Microsoft Intune](/mem/intune/protect/endpoint-security-asr-policy)
