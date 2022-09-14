---
title: Investigar eventos de conexión que ocurren tras los servidores proxy de reenvío
description: Aprenda a usar la supervisión avanzada de nivel HTTP a través de la protección de red en Microsoft Defender para punto de conexión, que expone un destino real, en lugar de un proxy.
keywords: proxy, protección de red, proxy de reenvío, eventos de red, auditoría, bloque, nombres de dominio, dominio
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 24e427685063b3de02ed160890ce2a76d166494f
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67690310"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>Investigar eventos de conexión que ocurren tras los servidores proxy de reenvío

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Defender for Endpoint admite la supervisión de conexiones de red desde distintos niveles de la pila de red. Un caso difícil es cuando la red usa un proxy de reenvío como puerta de enlace a Internet.

El proxy actúa como si fuera el punto de conexión de destino. En estos casos, los monitores de conexión de red simples auditarán las conexiones con el proxy que son correctas pero tienen un valor de investigación inferior.

Defender for Endpoint admite la supervisión avanzada de nivel HTTP a través de la protección de red. Cuando está activado, aparece un nuevo tipo de evento que expone los nombres de dominio de destino reales.

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>Uso de la protección de red para supervisar la conexión de red detrás de un firewall

La supervisión de la conexión de red detrás de un proxy de reenvío es posible debido a otros eventos de red que se originan en la protección de red. Para verlos en una escala de tiempo del dispositivo, active la protección de red (como mínimo en modo de auditoría).

La protección de red se puede controlar mediante los modos siguientes:

- **Bloquear**: los usuarios o aplicaciones no podrán conectarse a dominios peligrosos. Podrá ver esta actividad en Microsoft 365 Defender.
- **Auditoría**: no se bloqueará la conexión de usuarios o aplicaciones a dominios peligrosos. Sin embargo, seguirá viendo esta actividad en Microsoft 365 Defender.


Si desactiva la protección de red, no se bloqueará la conexión de usuarios o aplicaciones a dominios peligrosos. No verá ninguna actividad de red en Microsoft 365 Defender.

Si no lo configura, el bloqueo de red se desactivará de forma predeterminada.

Para obtener más información, consulte [Habilitación de la protección de red](enable-network-protection.md).

## <a name="investigation-impact"></a>Impacto en la investigación

Cuando se activa la protección de red, verá que, en la escala de tiempo de un dispositivo, la dirección IP seguirá representando el proxy, mientras que la dirección de destino real aparece.

:::image type="content" source="images/atp-proxy-investigation.png" alt-text="Eventos de red en la escala de tiempo del dispositivo" lightbox="images/atp-proxy-investigation.png":::

Otros eventos desencadenados por la capa de protección de red ahora están disponibles para exponer los nombres de dominio reales incluso detrás de un proxy.

Información del evento:

:::image type="content" source="images/atp-proxy-investigation-event.png" alt-text="Direcciones URL de un único evento de red" lightbox="images/atp-proxy-investigation-event.png":::

## <a name="hunt-for-connection-events-using-advanced-hunting"></a>Búsqueda de eventos de conexión mediante la búsqueda avanzada

Todos los nuevos eventos de conexión están disponibles para que usted pueda buscar a través de la búsqueda avanzada también. Dado que estos eventos son eventos de conexión, puede encontrarlos en la tabla DeviceNetworkEvents en el `ConnecionSuccess` tipo de acción.

El uso de esta consulta simple le mostrará todos los eventos pertinentes:

```console
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess"
| take 10
```

:::image type="content" source="images/atp-proxy-investigation-ah.png" alt-text="Consulta de búsqueda avanzada" lightbox="images/atp-proxy-investigation-ah.png":::

También puede filtrar los eventos relacionados con la conexión con el propio proxy.

Use la consulta siguiente para filtrar las conexiones al proxy:

```console
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"
| take 10
```

## <a name="related-topics"></a>Temas relacionados

- [Aplicación de la protección de red con GP: CSP de directiva](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
