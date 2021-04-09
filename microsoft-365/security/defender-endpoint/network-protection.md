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
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: 2ef3fbeec65be512dfe07f1d533df4d8e9b31532
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644505"
---
# <a name="protect-your-network"></a>Proteger la red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

La protección de red ayuda a reducir la superficie de ataque de los dispositivos a partir de eventos basados en Internet. Impide que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet. La protección de red expande el ámbito de [SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) de Microsoft Defender para bloquear todo el tráfico HTTP saliente que intente conectarse a orígenes de baja reputación (según el dominio o el nombre de host).

La protección de red se admite en Windows, a partir de Windows 10, versión 1709. 

Para obtener más información acerca de cómo habilitar la protección de red, vea [Enable network protection](enable-network-protection.md). Use directivas de grupo, PowerShell o CSP mdm para habilitar y administrar la protección de red en la red.

> [!TIP]
> Consulta el sitio de prueba de ATP de Microsoft Defender en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para ver cómo funciona la protección de red.

La protección de red funciona mejor con [Microsoft Defender para endpoint,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)lo que le ofrece informes detallados sobre eventos y bloques de protección contra vulnerabilidades como parte de escenarios de [investigación de alertas.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Cuando la protección de red bloquea una conexión, se muestra una notificación desde el Centro de acciones. El equipo de operaciones de seguridad [puede personalizar la notificación](customize-attack-surface-reduction.md#customize-the-notification) con los detalles de la organización y la información de contacto. Además, las reglas de reducción de superficie de ataque individuales se pueden habilitar y personalizar para adaptarse a determinadas técnicas que se deben supervisar.

También puede usar el modo [de auditoría para](audit-windows-defender.md) evaluar cómo afectaría la protección de red a su organización si estuviera habilitada.

## <a name="requirements"></a>Requisitos

La protección de red requiere Windows 10 Pro o Enterprise y la protección en tiempo real del Antivirus de Microsoft Defender.

| Versión de Windows | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10 versión 1709 o posterior <p>Windows Server 1803 o posterior | [La protección en tiempo real de Antivirus](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) de Microsoft Defender y la protección [en](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) la nube deben estar habilitadas |

Después de habilitar los servicios, es posible que deba configurar la red o firewall para permitir las conexiones entre los servicios y los dispositivos (también denominados puntos de conexión).  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Revisar los eventos de protección de red en el Centro de seguridad de Microsoft Defender para endpoints

Microsoft Defender para endpoint proporciona informes detallados sobre eventos y bloques como parte de sus escenarios de [investigación de alertas.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Puede consultar datos de punto de conexión de Microsoft Defender mediante [búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection). Si usa el modo [de auditoría,](audit-windows-defender.md)puede usar la búsqueda avanzada para ver cómo la configuración de protección de red afectaría al entorno si estuvieran habilitadas.

Esta es una consulta de ejemplo

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revisar eventos de protección de red en el Visor de eventos de Windows

Puedes revisar el registro de eventos de Windows para ver los eventos que se crean cuando la protección de red bloquea (o audita) el acceso a un dominio o IP malintencionado:

1. [Copie el XML directamente](event-views.md).

2. Elija **Aceptar**.

Este procedimiento crea una vista personalizada que filtra para mostrar solo los siguientes eventos relacionados con la protección de red:

| Id. de evento | Descripción |
|:---|:---|
| 5007 | Evento cuando se cambia la configuración |
| 1125 | Evento cuando la protección de red se dispara en modo auditoría |
| 1126 | Evento cuando la protección de red se desen llamas en modo de bloqueo |

## <a name="network-protection-troubleshooting"></a>Solución de problemas de protección de red

Debido al entorno en el que se ejecuta Network Protection, Es posible que Microsoft no pueda detectar la configuración de proxy del sistema operativo. En algunos casos, los clientes de Protección de red no pueden llegar al servicio en la nube. Para resolver el problema de conectividad, los clientes con licencias E5 deben configurar una de las siguientes claves del Registro de Defender:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>Artículos relacionados

- [Evaluar la protección de](evaluate-network-protection.md) red | Realice un escenario rápido que demuestre cómo funciona la característica y qué eventos se crearían normalmente.

- [Habilitar la protección de](enable-network-protection.md) red | Use directivas de grupo, PowerShell o CSP mdm para habilitar y administrar la protección de red en la red.
