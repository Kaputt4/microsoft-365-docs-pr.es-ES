---
title: Información general de la detección de dispositivo
description: Obtenga información sobre cómo aprovechar la detección de puntos de conexión en Microsoft 365 Defender para buscar dispositivos no administrados en la red
keywords: detección, detección, pasiva, proactiva, red, visibilidad, servidor, estación de trabajo, dispositivos incorporados y no administrados
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: siosulli
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365-initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f6046576fcea2fe961e73e88168c6254a2d95a40
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665060"
---
# <a name="device-discovery-overview"></a>Información general de la detección de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

La protección del entorno requiere realizar un inventario de los dispositivos que se encuentran en la red. Sin embargo, la asignación de dispositivos en una red a menudo puede ser costosa, complicada y lenta.

Microsoft Defender para punto de conexión proporciona una funcionalidad de detección de dispositivos que le ayuda a encontrar dispositivos no administrados conectados a la red corporativa sin necesidad de dispositivos adicionales ni cambios en los procesos engorrosos. La detección de dispositivos usa puntos de conexión incorporados en la red para recopilar, sondear o examinar la red para detectar dispositivos no administrados. La funcionalidad de detección de dispositivos le permite detectar:

- Enterprise puntos de conexión (estaciones de trabajo, servidores y dispositivos móviles) que aún no están incorporados a Microsoft Defender para punto de conexión
- Dispositivos de red como enrutadores y conmutadores
- Dispositivos IoT como impresoras y cámaras

Los dispositivos desconocidos y no administrados presentan riesgos significativos para la red, ya sea una impresora sin revisiones, dispositivos de red con configuraciones de seguridad débiles o un servidor sin controles de seguridad. Una vez detectados los dispositivos, puede hacer lo siguiente:

- Incorporación de puntos de conexión no administrados al servicio, lo que aumenta la visibilidad de seguridad sobre ellos.
- Reduzca la superficie expuesta a ataques mediante la identificación y evaluación de vulnerabilidades y la detección de brechas de configuración.

Vea este vídeo para obtener información general rápida sobre cómo detección de dispositivos:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWORdQ]

Junto con esta funcionalidad, hay disponible una recomendación de seguridad para incorporar dispositivos a Microsoft Defender para punto de conexión como parte de la experiencia de Administración de amenazas y vulnerabilidades existente.

## <a name="discovery-methods"></a>Métodos de detección

Puede elegir el modo de detección que usarán los dispositivos incorporados. El modo controla el nivel de visibilidad que puede obtener para los dispositivos no administrados en la red corporativa.

Hay dos modos de detección disponibles:

- **Detección básica**: en este modo, los puntos de conexión recopilarán eventos de forma pasiva en la red y extraerán información del dispositivo de ellos. La detección básica usa el binario SenseNDR.exe para la recopilación pasiva de datos de red y no se iniciará ningún tráfico de red. Los puntos de conexión simplemente extraerán datos de cada tráfico de red que vea un dispositivo incorporado. Con la detección básica, solo obtendrá visibilidad limitada de los puntos de conexión no administrados en la red.

- **Detección estándar** (recomendado): este modo permite a los puntos de conexión encontrar dispositivos de forma activa en la red para enriquecer los datos recopilados y detectar más dispositivos, lo que le ayuda a crear un inventario de dispositivos confiable y coherente. Además de los dispositivos que se observaron mediante el método pasivo, el modo estándar también aprovecha los protocolos de detección comunes que usan consultas de multidifusión en la red para encontrar aún más dispositivos. El modo estándar usa sondeos activos y inteligentes para detectar información adicional sobre los dispositivos observados para enriquecer la información existente del dispositivo. Cuando el modo Estándar está habilitado, las herramientas de supervisión de red de su organización podrían observar la actividad de red mínima y insignificante generada por el sensor de detección.

Puede cambiar y personalizar la configuración de detección. Para obtener más información, consulte [Configuración de la detección de dispositivos](configure-device-discovery.md).

> [!IMPORTANT]
> La detección estándar es el modo predeterminado para todos los clientes a partir del 19 de julio de 2021. Puede optar por cambiar esta configuración a básica a través de la página de configuración. Si elige el modo básico, solo obtendrá visibilidad limitada de los puntos de conexión no administrados en la red.

> [!NOTE]
> El motor de detección distingue entre los eventos de red que se reciben en la red corporativa y fuera de la red corporativa. Los dispositivos que no están conectados a redes corporativas no se detectarán ni se mostrarán en el inventario de dispositivos.

## <a name="device-inventory"></a>Inventario de dispositivos

Los dispositivos que se han detectado pero que aún no se han incorporado y protegido por Microsoft Defender para punto de conexión aparecerán en el inventario de dispositivos en la pestaña Equipos y dispositivos móviles.

Para evaluar estos dispositivos, puede usar un filtro en la lista de inventario de dispositivos denominado Estado de incorporación, que puede tener cualquiera de los siguientes valores:

- Incorporado: el punto de conexión se incorpora a Microsoft Defender para punto de conexión.
- Se puede incorporar: el punto de conexión se detectó en la red y el sistema operativo se identificó como uno compatible con Microsoft Defender para punto de conexión, pero no está incorporado actualmente. Se recomienda encarecidamente incorporar estos dispositivos.
- No compatible: el punto de conexión se detectó en la red, pero no es compatible con Microsoft Defender para punto de conexión.
- Información insuficiente: el sistema no pudo determinar la compatibilidad del dispositivo. Habilitar la detección estándar en más dispositivos de la red puede enriquecer los atributos detectados.

:::image type="content" source="images/2b62255cd3a9dd42f3219e437b956fb9.png" alt-text="Panel de inventario de dispositivos" lightbox="images/2b62255cd3a9dd42f3219e437b956fb9.png":::

> [!TIP]
> Siempre puede aplicar filtros para excluir dispositivos no administrados de la lista de inventario de dispositivos. También puede usar la columna de estado de incorporación en consultas de API para filtrar dispositivos no administrados.

Para obtener más información, consulte [Inventario de dispositivos](machines-view-overview.md).

## <a name="network-device-discovery"></a>Detección de dispositivos de red

El gran número de dispositivos de red no administrados implementados en una organización crea una gran superficie de ataque y representa un riesgo significativo para toda la empresa. Microsoft Defender para punto de conexión funcionalidades de detección de red le ayuda a garantizar que los dispositivos de red se detectan, clasifican con precisión y se agregan al inventario de recursos.

Los dispositivos de red no se administran como puntos de conexión estándar, ya que Defender para punto de conexión no tiene un sensor integrado en los propios dispositivos de red. Estos tipos de dispositivos requieren un enfoque sin agente donde un examen remoto obtendrá la información necesaria de los dispositivos. Para ello, se usará un dispositivo Microsoft Defender para punto de conexión designado en cada segmento de red para realizar exámenes autenticados periódicos de dispositivos de red preconfigurados. Una vez detectado, las capacidades de Administración de amenazas y vulnerabilidades de Defender para punto de conexión proporcionan flujos de trabajo integrados para proteger los conmutadores detectados, enrutadores, controladores WLAN, firewalls y puertas de enlace de VPN.

Para obtener más información, consulte [Dispositivos de red](network-devices.md).

## <a name="device-discovery-integrations"></a>Integraciones de detección de dispositivos

Para abordar el desafío de obtener suficiente visibilidad para localizar, identificar y proteger el inventario de recursos OT/IOT completo Microsoft Defender para punto de conexión ahora admite las siguientes integraciones:

- **Corelight**: Microsoft se ha asociado con Corelight para recibir datos de dispositivos de red corelight. Esto proporciona Microsoft 365 Defender con mayor visibilidad sobre las actividades de red de los dispositivos no administrados, incluida la comunicación con otros dispositivos no administrados o redes externas. Para obtener más información, consulte [Habilitación de la integración de datos de Corelight](corelight-integration.md).

- **Microsoft Defender para IoT**: esta integración combina las funcionalidades de detección de dispositivos de Microsoft Defender para punto de conexión, con las funcionalidades de supervisión sin agente de Microsoft Defender para IoT, para proteger los dispositivos IoT empresariales conectados a una red de TI (por ejemplo, Protocolo de voz a través de Internet (VoIP), impresoras y televisores inteligentes. Para obtener más información, consulte [Habilitación de la integración de Microsoft Defender para IoT](enable-microsoft-defender-for-iot-integration.md).

## <a name="vulnerability-assessment-on-discovered-devices"></a>Evaluación de vulnerabilidades en dispositivos detectados

Las vulnerabilidades y riesgos en los dispositivos, así como en otros dispositivos no administrados detectados en la red, forman parte de los flujos actuales de TVM en "Seguridad Recomendaciones" y se representan en las páginas de entidad en el portal.
Busque recomendaciones de seguridad relacionadas con "SSH" para buscar vulnerabilidades ssh relacionadas con dispositivos no administrados y administrados.

:::image type="content" source="images/1156c82ffadd356ce329d1cf551e806c.png" alt-text="Panel de recomendaciones de seguridad" lightbox="images/1156c82ffadd356ce329d1cf551e806c.png":::


## <a name="use-advanced-hunting-on-discovered-devices"></a>Uso de la búsqueda avanzada en dispositivos detectados

Puede usar consultas de búsqueda avanzada para obtener visibilidad en los dispositivos detectados.
Busque detalles sobre los puntos de conexión detectados en la tabla DeviceInfo o información relacionada con la red sobre esos dispositivos en la tabla DeviceNetworkInfo.

:::image type="content" source="images/f48ba1779eddee9872f167453c24e5c9.png" alt-text="Página Búsqueda avanzada en la que se pueden usar consultas" lightbox="images/f48ba1779eddee9872f167453c24e5c9.png":::

La detección de dispositivos aprovecha Microsoft Defender para punto de conexión dispositivos incorporados como origen de datos de red para atribuir actividades a dispositivos no incorporados. Esto significa que si un Microsoft Defender para punto de conexión dispositivo incorporado se comunica con un dispositivo no incorporado, las actividades del dispositivo no incorporado se pueden ver en la escala de tiempo y a través de la tabla DeviceNetworkEvents de búsqueda avanzada.

Los nuevos eventos se basan en conexiones de Protocolo de control de transmisión (TCP) y se ajustarán al esquema DeviceNetworkEvents actual. Entrada TCP al dispositivo habilitado para Microsoft Defender para punto de conexión desde un dispositivo que no está habilitado para Microsoft Defender para punto de conexión.

También se han agregado los siguientes tipos de acción:

- ConnectionAttempt: intento de establecer una conexión TCP (syn)
- ConnectionAcknowledged: confirmación de que se aceptó una conexión TCP (syn\ack)

Puede probar esta consulta de ejemplo:

```text
DeviceNetworkEvents
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"
| take 10
```

## <a name="next-steps"></a>Siguientes pasos

- [Configuración de la detección de dispositivo](configure-device-discovery.md)
- [Preguntas más frecuentes sobre la detección de dispositivos](device-discovery-faq.md)
