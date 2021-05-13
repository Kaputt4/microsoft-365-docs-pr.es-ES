---
title: Microsoft 365 Network Insights
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights
ms.openlocfilehash: 10b1c66a8f9aae555c2841b2b290f341bec3c7ec
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470573"
---
# <a name="microsoft-365-network-insights"></a>Microsoft 365 Network Insights

**Los conocimientos de** red son métricas de rendimiento recopiladas Microsoft 365 inquilino y disponibles para que solo las puedan ver los usuarios administrativos de su inquilino. Las perspectivas se muestran en el Centro Microsoft 365 administración en <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Las perspectivas están diseñadas para ayudar a diseñar perímetros de red para las ubicaciones de la oficina. Cada información proporciona detalles en directo sobre las características de rendimiento de un problema común específico para cada ubicación geográfica en la que los usuarios tienen acceso a su espacio empresarial.

Hay seis perspectivas de red específicas que se pueden mostrar para cada ubicación de la oficina:

- [Salida de red backhauled](#backhauled-network-egress)
- [Dispositivo intermediario de red](#network-intermediary-device)
- [Mejor rendimiento detectado para clientes cercanos](#better-performance-detected-for-customers-near-you)
- [Uso de una puerta principal Exchange Online servicio no óptimo](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso de una puerta principal de servicio SharePoint en línea no óptima](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Baja velocidad de descarga desde SharePoint puerta principal](#low-download-speed-from-sharepoint-front-door)
- [Salida óptima de red del usuario de China](#china-user-optimal-network-egress)

Hay dos perspectivas de red de nivel de inquilino que se pueden mostrar para el inquilino. También aparecen en las páginas de puntuación de productividad:

- [Exchange conexiones muestreadas afectadas por problemas de conectividad](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint conexiones muestreadas afectadas por problemas de conectividad](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Los conocimientos de red, las recomendaciones de rendimiento y las evaluaciones del Centro de administración de Microsoft 365 se encuentran actualmente en estado de vista previa y solo están disponibles para los inquilinos Microsoft 365 que se han inscrito en el programa de vista previa de características.

## <a name="backhauled-network-egress"></a>Salida de red backhauled

Esta información se mostrará si el servicio de información de red detecta que la distancia desde una ubicación de usuario determinada a la salida de red es mayor que 500 millas (800 kilómetros), lo que indica que el tráfico de Microsoft 365 se está backhauled a un proxy o dispositivo perimetral de Internet común.

Esta información se abrevia como "Egress" en algunas vistas de resumen.

> [!div class="mx-imgBorder"]
> ![Salida de red backhauled](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Esto identifica que la distancia entre la ubicación de la oficina y la salida de red es de más de 500 millas (800 kilómetros). La ubicación de la oficina se identifica mediante una ubicación del equipo cliente ofuscado y la ubicación de salida de red se identifica mediante la dirección IP inversa a las bases de datos de ubicación. La ubicación de la oficina puede ser inexacta si Windows location services está deshabilitada en las máquinas. La ubicación de salida de red puede ser inexacta si la información de la base de datos de direcciones IP inversa es inexacta.

Los detalles de esta información incluyen la ubicación de la oficina, el porcentaje estimado del total de inquilinos en la ubicación, la ubicación de salida de red actual, la relevancia de la ubicación de salida, la distancia entre la ubicación y el punto de salida actual, la fecha en que se detectó la condición por primera vez y la fecha en que se resolvió la condición.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Para esta información, recomendamos la salida de red más cerca de la ubicación de la oficina para que la conectividad pueda enrutar de forma óptima a la red global de Microsoft y a la puerta principal del servicio de Microsoft 365 más cercana. Tener una salida de red cercana a las ubicaciones de oficina de los usuarios también permite mejorar el rendimiento en el futuro, ya que Microsoft expande tanto los puntos de presencia de red como Microsoft 365 puertas frontales del servicio en el futuro.

Para obtener más información acerca de cómo resolver este problema, vea [Egress conexiones](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) de red localmente en [Office 365 principios](microsoft-365-network-connectivity-principles.md)de conectividad de red .

## <a name="network-intermediary-device"></a>Dispositivo intermediario de red

Esta información se mostrará si detectamos dispositivos entre los usuarios y la red de Microsoft que pueden afectar a la Office 365 usuario. Se recomienda omitir estos datos para el tráfico de red Microsoft 365 específico destinado a centros de datos de Microsoft. Esta recomendación se describe además en [Microsoft 365 principios de conectividad de red](microsoft-365-network-connectivity-principles.md). 

Una información intermediaria de red que mostramos es la interrupción e inspección de SSL cuando los puntos de conexión de red críticos de Office 365 para Exchange, SharePoint y Teams son interceptados y descifrados por dispositivos intermediarios de red.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Los dispositivos intermediarios de red como servidores proxy, VPN y dispositivos de prevención de pérdida de datos pueden afectar al rendimiento y la estabilidad de Microsoft 365 clientes en los que el tráfico está intermedio.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Configure el dispositivo intermediario de red que se detectó para omitir el procesamiento Microsoft 365 tráfico de red.

## <a name="better-performance-detected-for-customers-near-you"></a>Mejor rendimiento detectado para clientes cercanos

Esta información se mostrará si el servicio de información de red detecta que un número significativo de clientes de su área metropolitana tienen un mejor rendimiento que los usuarios de su organización en esta ubicación de oficina.

Esta información se abrevia como "Peers" en algunas vistas de resumen.

> [!div class="mx-imgBorder"]
> ![Rendimiento relativo de la red](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Esta información examina el rendimiento agregado de Microsoft 365 clientes en la misma ciudad que esta ubicación de oficina. Esta información se muestra si la latencia media de los usuarios es un 10 % mayor que la latencia media de los inquilinos vecinos.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Puede haber muchas razones para esta condición, como la latencia en su red corporativa o ISP, cuellos de botella o problemas de diseño de arquitectura. Examine la latencia entre cada salto de la ruta entre la red de oficina y la puerta Microsoft 365 puerta principal. Para obtener más información, [vea Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Uso de una puerta principal Exchange Online servicio no óptimo

Esta información se mostrará si el servicio de información de red detecta que los usuarios de una ubicación específica no se conectan a una puerta Exchange Online servicio óptimo.

Esta información se abrevia como "Enrutamiento" en algunas vistas de resumen.

> [!div class="mx-imgBorder"]
> ![Puerta frontal exo no óptima](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Enumeramos Exchange Online puertas frontales de servicio adecuados para su uso desde la ciudad de la ubicación de la oficina con un buen rendimiento. Si la prueba actual muestra el uso de una puerta Exchange Online de servicio no en esta lista, llamamos a esta recomendación.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

El uso de una puerta principal de servicio de Exchange Online no óptima podría deberse al backhaul de red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa. También podría deberse al uso de un servidor de resolución recursiva dns remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva DNS con la salida de red.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Uso de una puerta principal de servicio SharePoint en línea no óptima

Esta información se mostrará si el servicio de información de red detecta que los usuarios de una ubicación específica no se conectan a la puerta principal del servicio en línea SharePoint más cercana.

Esta información se abrevia como "Afd" en algunas vistas de resumen.

> [!div class="mx-imgBorder"]
> ![Puerta principal de SPO no óptima](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Identificamos la puerta SharePoint servicio en línea a la que se conecta el cliente de prueba. A continuación, para la ciudad de ubicación de la oficina, lo comparamos con la puerta SharePoint de servicio en línea esperada para esa ciudad. Si no coincide, hacemos esta recomendación.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

El uso de una puerta principal del servicio SharePoint Online no óptimo podría deberse a la retrohaulción de la red antes de la salida de la red corporativa, en cuyo caso se recomienda la salida de red local y directa. También podría deberse al uso de un servidor de resolución recursiva dns remoto, en cuyo caso se recomienda alinear el servidor de resolución recursiva DNS con la salida de red.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Baja velocidad de descarga desde SharePoint puerta principal

Esta información se mostrará si el servicio de información de red detecta que el ancho de banda entre la ubicación específica de la oficina y SharePoint Online es inferior a 1 MBps.

Esta información se abrevia como "Rendimiento" en algunas vistas de resumen.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

La velocidad de descarga que un usuario puede obtener de SharePoint Online y OneDrive para la Empresa las puertas frontales del servicio se mide en megabytes por segundo (MBps). Si este valor es menor que 1 MBps, proporcionamos esta información.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Para mejorar las velocidades de descarga, es posible que sea necesario aumentar el ancho de banda. Como alternativa, puede haber congestión de red entre las máquinas de usuario en la ubicación de la oficina y la puerta principal SharePoint servicio en línea. Esto a veces se denomina pérdida congestiva y restringe la velocidad de descarga disponible para los usuarios incluso si hay suficiente ancho de banda disponible.

## <a name="china-user-optimal-network-egress"></a>Salida óptima de red del usuario de China

Esta información se mostrará si su organización tiene usuarios en China que se conectan a su Microsoft 365 en otras ubicaciones geográficas. 

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Si su organización tiene conectividad WAN privada, se recomienda configurar un circuito WAN de red desde sus ubicaciones de oficina en China que tenga salida de red a Internet en cualquiera de las siguientes ubicaciones:

- Hong Kong
- Japón
- Taiwán
- Corea del Sur
- Singapur
- Malasia

La salida de Internet más lejos de los usuarios que estas ubicaciones reducirá el rendimiento y la salida en China puede provocar problemas de latencia y conectividad elevados debido a la congestión transfronteriza.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Para obtener más información acerca de cómo mitigar los problemas de rendimiento relacionados con esta información, vea Microsoft 365 [global tenant performance optimization for China users](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Exchange conexiones muestreadas afectadas por problemas de conectividad

Esta información mostrará cuándo se afecta al 50 % o más de las conexiones muestreadas. El impacto se define mediante la evaluación Exchange inferior al 60 % para cada muestra.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Es una indicación de que es probable que la mayoría de los usuarios experimente problemas de experiencia de usuario con Outlook conectarse a Exchange Online. El porcentaje de muestras probablemente representa el porcentaje de usuarios que muestran menos de 60 puntos.  

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Habilite la visibilidad de la conectividad de red de ubicación de oficina si aún no lo ha hecho. Desea identificar qué oficinas se verán afectadas por la mala conectividad de red que está afectando a Exchange y buscar formas de mejorar el perímetro de red en cada una de las que conecte a los usuarios a la red de Microsoft.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>SharePoint conexiones muestreadas afectadas por problemas de conectividad

Esta información mostrará cuándo se afecta al 50 % o más de las conexiones muestreadas. El impacto se define mediante la evaluación SharePoint por debajo del 40 % para cada muestra.

### <a name="what-does-this-mean"></a>¿Qué significa esto?

Es una indicación de que es probable que la mayoría de los usuarios experimente problemas de experiencia de usuario con SharePoint y OneDrive. El porcentaje de muestras probablemente representa el porcentaje de usuarios que muestran menos de 40 puntos.  

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Habilite la visibilidad de la conectividad de red de ubicación de oficina si aún no lo ha hecho. Desea identificar qué oficinas se verán afectadas por la mala conectividad de red que está afectando a SharePoint y buscar formas de mejorar el perímetro de red en cada una de las que conecte a los usuarios a la red de Microsoft.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro Microsoft 365 administración (versión preliminar)](office-365-network-mac-perf-overview.md)

[Microsoft 365 de red (versión preliminar)](office-365-network-mac-perf-score.md)

[Microsoft 365 de prueba de conectividad de red (versión preliminar)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Servicios de ubicación de conectividad de red (versión preliminar)](office-365-network-mac-location-services.md)
