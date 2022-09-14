---
title: Microsoft 365 Network Insights
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/06/2021
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights
ms.openlocfilehash: 3f5413d0fe4b55a74b06d743e454da2eb76c0f5b
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67672323"
---
# <a name="microsoft-365-network-insights"></a>Microsoft 365 Network Insights

**Network Insights** son métricas de rendimiento recopiladas del inquilino de Microsoft 365 y están disponibles para que solo los usuarios administrativos del inquilino las vean. Las conclusiones se muestran en el Centro de Administración de Microsoft 365 en <https://portal.microsoft.com/adminportal/home#/networkperformance>.

Conclusiones está concebido para ayudar a diseñar perímetros de red para las ubicaciones de las oficinas. Cada conclusión proporciona detalles en tiempo real de las características de rendimiento de un problema específico y común para cada ubicación geográfica en la que los usuarios acceden al espacio empresarial.

Hay seis conclusiones de red específicas que se pueden mostrar para cada ubicación de office:

- [Salida de red de backhauled](#backhauled-network-egress)
- [Dispositivo intermediario de red](#network-intermediary-device)
- [Se detectó un mejor rendimiento para los clientes cercanos](#better-performance-detected-for-customers-near-you)
- [Uso de una puerta de servicio de Exchange Online no óptima](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso de una puerta de servicio de SharePoint Online no óptima](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Baja velocidad de descarga de SharePoint front door](#low-download-speed-from-sharepoint-front-door)
- [Salida de red óptima del usuario de China](#china-user-optimal-network-egress)

Hay dos conclusiones de red de nivel de inquilino que se pueden mostrar para el inquilino:

- [Conexiones muestreadas de Exchange afectadas por problemas de conectividad](#exchange-sampled-connections-affected-by-connectivity-issues)
- [Conexiones muestreadas de SharePoint afectadas por problemas de conectividad](#sharepoint-sampled-connections-affected-by-connectivity-issues)

Estas conclusiones también aparecen en las páginas de puntuación de productividad.

>[!IMPORTANT]
>Información de red, recomendaciones de rendimiento y evaluaciones en el Centro de Administración de Microsoft 365 está actualmente en estado de versión preliminar y solo está disponible para los inquilinos de Microsoft 365 que se han inscrito en el programa de versión preliminar de características.

## <a name="backhauled-network-egress"></a>Salida de red de backhauled

Esta información se mostrará si el servicio network insights detecta que la distancia entre una ubicación de usuario determinada y la salida de la red es superior a 500 millas (800 kilómetros). Esto puede indicar que el tráfico de Microsoft 365 se está devolviendo a un dispositivo perimetral o proxy de Internet común.

Esta información se abrevia como "Salida" en algunas vistas de resumen.

> [!div class="mx-imgBorder"]
> ![Salida de red de backhauled.](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Esto identifica que la distancia entre la ubicación de la oficina y la salida de la red es superior a 500 millas (800 kilómetros). La ubicación de la oficina se identifica mediante una ubicación de máquina cliente ofuscada y la ubicación de salida de red se identifica mediante la dirección IP inversa a las bases de datos de ubicación. La ubicación de la oficina puede ser inexacta si Windows Location Services está deshabilitado en las máquinas. La ubicación de salida de red puede ser inexacta si la información de la base de datos de direcciones IP inversa es inexacta.

Entre los detalles de esta información se incluyen:

- Ubicación de la oficina
- Porcentaje estimado del usuario total del inquilino en la ubicación
- Ubicación de salida de red actual
- Relevancia de la ubicación de salida
- Distancia entre la ubicación y el punto de salida actual
- La fecha en que se detectó la condición por primera vez
- La fecha en que se resolvió la condición

### <a name="what-should-i-do"></a>¿Qué debo hacer?

Se recomienda la salida de la red lo más cerca posible de la ubicación de la oficina.  El tráfico de Microsoft 365 debe enrutarse de forma óptima a la red global de Microsoft y a la puerta principal del servicio de Microsoft 365 más cercana. Tener una salida de red cercana a las ubicaciones de oficina de los usuarios también permite mejorar el rendimiento, ya que Microsoft expande tanto los puntos de presencia de red como las puertas frontales del servicio de Microsoft 365 en el futuro.

Para obtener más información sobre cómo resolver este problema, consulte [Conexiones de red de salida localmente](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) en [Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md).

## <a name="network-intermediary-device"></a>Dispositivo intermediario de red

Esta información se mostrará si detectamos dispositivos entre los usuarios y la red de Microsoft. Se recomienda que el tráfico de red de Microsoft 365 sensible a la latencia omita estos dispositivos. Esta recomendación se describe además en [Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md).

Una información intermediaria de red que se muestra es la interrupción y la inspección de SSL cuando los dispositivos intermedios de red interceptan y descifran puntos de conexión de red críticos de Microsoft 365 para Exchange, SharePoint y Teams.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Los dispositivos intermediarios de red, como servidores proxy, VPN y dispositivos de prevención de pérdida de datos, pueden afectar al rendimiento y la estabilidad de los clientes de Microsoft 365 donde se intermedia el tráfico.

### <a name="what-should-i-do"></a>¿Qué debo hacer?

Configure el dispositivo intermediario de red que se detectó para omitir el procesamiento del tráfico de red de Microsoft 365.

## <a name="better-performance-detected-for-customers-near-you"></a>Se detectó un mejor rendimiento para los clientes cercanos

Esta información se mostrará si el servicio network insights detecta que un número significativo de clientes del área metropolitana tienen un mejor rendimiento que los usuarios de esta ubicación de la oficina.

Esta información se abrevia como "Peers" en algunas vistas de resumen.

> [!div class="mx-imgBorder"]
> ![Rendimiento de red relativo.](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Esta información examina el rendimiento agregado de los clientes de Microsoft 365 en la misma ciudad que esta ubicación de oficina. Esta información se muestra si la latencia media de los usuarios es un 10 % mayor que la latencia media de los inquilinos vecinos.

### <a name="what-should-i-do"></a>¿Qué debo hacer?

Puede haber muchas razones para esta condición, incluida la latencia en la red corporativa o isp, cuellos de botella o problemas de diseño de arquitectura. Examine la latencia entre cada salto de la ruta entre la red de office y la puerta principal actual de Microsoft 365. Para obtener más información, consulte [Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Uso de una puerta de servicio de Exchange Online no óptima

Esta información se mostrará si el servicio network insights detecta que los usuarios de una ubicación específica no se conectan a una puerta de servicio Exchange Online óptima.

Esta información se abrevia como "Enrutamiento" en algunas vistas de resumen.

> [!div class="mx-imgBorder"]
> ![Puerta frontal EXO no óptima.](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Enumeramos Exchange Online puertas frontales de servicio que son adecuadas para su uso desde la ciudad de ubicación de la oficina. Si la prueba actual muestra el uso de una puerta de servicio de Exchange Online que no está en esta lista, llamamos a esta recomendación.

### <a name="what-should-i-do"></a>¿Qué debo hacer?

El uso de una puerta de servicio de Exchange Online no óptima podría deberse a un backhaul de red, en cuyo caso se recomienda la salida de la red local y directa. Si ha implementado un servidor de resolución recursiva dns remoto, se recomienda alinear la configuración del servidor con la salida de red.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Uso de una puerta de servicio de SharePoint Online no óptima

Esta información se mostrará si el servicio network insights detecta que los usuarios de una ubicación específica no se conectan al servicio de SharePoint Online más cercano.

Esta información se abrevia como "Afd" en algunas vistas de resumen.

> [!div class="mx-imgBorder"]
> ![Puerta frontal de SPO no óptima.](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Identificamos la puerta principal del servicio SharePoint Online al que se conecta el cliente de prueba. A continuación, para la ciudad de ubicación de la oficina lo comparamos con la puerta principal del servicio de SharePoint Online esperado para esa ciudad. Si no coincide, hacemos esta recomendación.

### <a name="what-should-i-do"></a>¿Qué debo hacer?

El uso de una puerta de servicio de SharePoint Online no óptima podría deberse a un backhaul de red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa. También podría deberse al uso de un servidor de resolución recursiva dns remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva dns con la salida de red.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Baja velocidad de descarga de SharePoint front door

Esta información se mostrará si el servicio network insights detecta que el ancho de banda entre la ubicación de oficina específica y SharePoint Online es menor que 1 MBps.

Esta información se abrevia como "Rendimiento" en algunas vistas de resumen.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

La velocidad de descarga que un usuario puede obtener de SharePoint Online y OneDrive para la Empresa puertas frontales del servicio se mide en megabytes por segundo (MBps). Si este valor es menor que 1 MBps, proporcionamos esta información.

### <a name="what-should-i-do"></a>¿Qué debo hacer?

Para mejorar las velocidades de descarga, es posible que sea necesario aumentar el ancho de banda. Como alternativa, puede haber congestión de red entre los equipos en la ubicación de la oficina y la puerta principal del servicio SharePoint Online. Esta condición restringe la velocidad de descarga disponible para los usuarios incluso si hay suficiente ancho de banda disponible.

## <a name="china-user-optimal-network-egress"></a>Salida de red óptima del usuario de China

Esta información se mostrará si su organización tiene usuarios en China que se conectan a su inquilino de Microsoft 365 en otras ubicaciones geográficas.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Si su organización tiene conectividad WAN privada, se recomienda configurar un circuito WAN de red desde las ubicaciones de su oficina en China que tenga salida de red a Internet en cualquiera de las siguientes ubicaciones:

- Hong Kong
- Japón
- Taiwán
- Corea del Sur
- Singapur
- Malasia

La salida de Internet más lejos de los usuarios que estas ubicaciones reducirá el rendimiento, y la salida en China puede causar problemas de conectividad y latencia elevados debido a la congestión transfronteriza.

### <a name="what-should-i-do"></a>¿Qué debo hacer?

Para obtener más información sobre cómo mitigar los problemas de rendimiento relacionados con esta información, consulte [Optimización del rendimiento de inquilinos globales de Microsoft 365 para usuarios de China](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-affected-by-connectivity-issues"></a>Conexiones muestreadas de Exchange afectadas por problemas de conectividad

Esta información mostrará cuándo se ven afectadas el 50 % o más de las conexiones muestreadas. El impacto se define mediante la evaluación de Exchange que está por debajo del 60 % para cada ejemplo.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Esto indica que es probable que la mayoría de los usuarios experimenten problemas con la conexión de Outlook a Exchange Online. El porcentaje de muestras representa el porcentaje de usuarios que muestran menos de 60 puntos.  

### <a name="what-should-i-do"></a>¿Qué debo hacer?

Habilite la visibilidad de conectividad de red de ubicación de office si aún no lo ha hecho. Identifique qué oficinas se ven afectadas por una conectividad de red deficiente y busque formas de mejorar el perímetro de red en cada una de las que conecta a los usuarios a la red de Microsoft.

## <a name="sharepoint-sampled-connections-affected-by-connectivity-issues"></a>Conexiones muestreadas de SharePoint afectadas por problemas de conectividad

Esta información mostrará cuándo se ven afectadas el 50 % o más de las conexiones muestreadas. El impacto se define mediante la evaluación de SharePoint que está por debajo del 40 % para cada ejemplo.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Esto indica que es probable que la mayoría de los usuarios experimenten problemas con SharePoint y OneDrive. El porcentaje de muestras representa el porcentaje de usuarios que muestran menos de 40 puntos.  

### <a name="what-should-i-do"></a>¿Qué debo hacer?

Habilite la visibilidad de conectividad de red de ubicación de office si aún no lo ha hecho. Identifique qué oficinas se ven afectadas por una conectividad de red deficiente y busque formas de mejorar el perímetro de red en cada una de las que conecta a los usuarios a la red de Microsoft.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de Administración de Microsoft 365](office-365-network-mac-perf-overview.md)

[Evaluación de red de Microsoft 365](office-365-network-mac-perf-score.md)

[Prueba de conectividad de red de Microsoft 365](office-365-network-mac-perf-onboarding-tool.md)

[Servicios de ubicación de conectividad de red de Microsoft 365](office-365-network-mac-location-services.md)
