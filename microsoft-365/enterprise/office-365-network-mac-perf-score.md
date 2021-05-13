---
title: Microsoft 365 de red
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
description: Microsoft 365 de red
ms.openlocfilehash: c09e34b1bc3a8bf0f82a4a1e3c72e67f320abd43
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470489"
---
# <a name="microsoft-365-network-assessment"></a>Microsoft 365 de red

En la conectividad de Microsoft 365 de red del Centro de administración, las evaluaciones de red agregan un agregado de muchas **métricas** de rendimiento de red en una instantánea del estado perimetral de la red empresarial. Una evaluación de red le indica cuánto está afectando el diseño de red responsable del cliente Office 365 experiencia del usuario. Las evaluaciones de red están en el ámbito de todo el espacio empresarial y en cada ubicación geográfica desde la que los usuarios se conectan al espacio empresarial. Las evaluaciones proporcionan a Microsoft 365 administradores una forma sencilla de obtener una idea instantánea del estado de la red de la empresa y profundizar rápidamente en un informe detallado para cualquier ubicación de oficina global.

El valor de puntos de evaluación de red va de 0 a 100 y es un promedio de métricas de latencia TCP, velocidad de descarga y calidad de conexión UDP. Estas métricas se compilan una vez al día. Las métricas de rendimiento de las redes propiedad de Microsoft se excluyen de estas medidas para garantizar que los resultados de la evaluación sean inequívocos y específicos para la red corporativa.

> [!div class="mx-imgBorder"]
> ![Valor de evaluación de red](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Un valor de evaluación de red muy bajo sugiere que Microsoft 365 clientes tendrán problemas importantes para conectarse al inquilino o mantener una experiencia de usuario con capacidad de respuesta. Un valor alto indica una red configurada correctamente con pocos problemas de rendimiento continuos. Un valor del 80 % representa una línea base en buen estado, por encima de la cual no debería esperar recibir quejas de usuarios regulares sobre la conectividad Microsoft 365 capacidad de respuesta debido al rendimiento de la red. A medida que se realizan mejoras de conectividad de red iterativa, este valor aumentará junto con la experiencia del usuario.

| Evaluación de la red | Experiencia de usuario esperada |
| :----------------- | :----------------------- |
| 100                | Procedimientos                     |
| 80                 | Cumple recomendaciones    |
| 60                 | Aceptable               |
| 40                 | Los usuarios pueden experimentar problemas |
| 20                 | Los usuarios pueden quejarse       |
| 0                  | Problemas de red un tema común de discusión |

>[!IMPORTANT]
>Los conocimientos de red, las recomendaciones de rendimiento y las evaluaciones del Centro de administración de Microsoft 365 se encuentran actualmente en estado de vista previa y solo están disponibles para los inquilinos Microsoft 365 que se han inscrito en el programa de vista previa de características.

## <a name="network-assessment-panel"></a>Panel de evaluación de red

Cada evaluación de red, ya sea en el ámbito del inquilino o en una ubicación de oficina específica, muestra un panel con detalles sobre la evaluación. Este panel muestra un gráfico de barras de la evaluación como porcentaje y como puntos totales de cada carga de trabajo de componentes, incluidas solo las cargas de trabajo donde se recibieron los datos de medida. Para una evaluación de red de ubicación de oficina, también mostramos una comparación con el porcentaje de clientes de Microsoft 365 en cada uno de los cinco quintos que informaron de datos en la misma ciudad que la ubicación de la oficina.

> [!div class="mx-imgBorder"]
> ![Valor de evaluación de red de ejemplo](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

El **desglose de evaluación** del panel muestra la evaluación de cada una de las cargas de trabajo del componente.

El **historial de evaluaciones** muestra los últimos 30 días de la evaluación y el punto de referencia. También puede informar sobre el historial de métricas de cualquier ubicación de la oficina durante un máximo de dos años mediante la pestaña historial. La pestaña historial permite seleccionar los atributos en los que se va a informar. Al elegir un período de tiempo de informe, puede resaltar el impacto de un proyecto de actualización de red y ver la mejora en la evaluación de la red.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Evaluaciones de red de inquilinos y evaluaciones de red de ubicación de oficina

Una evaluación de red mide el diseño del perímetro de red de una ubicación de oficina en la red de Microsoft. Las mejoras en el perímetro de red se realizan mejor en cada ubicación de oficina.

Mostramos un valor de evaluación de red para todo Microsoft 365 inquilino en la página introducción al rendimiento de la red. Este valor es un promedio ponderado de las evaluaciones de red para todas las ubicaciones de oficina. También hay un valor de evaluación de red específico para cada ubicación de oficina detectada en la página de resumen de esa ubicación.

## <a name="exchange-online"></a>Exchange Online

Por Exchange Online, se mide la latencia TCP desde el equipo cliente hasta Exchange puerta principal del servicio. Esta latencia se puede ver afectada por la distancia que recorre la red a través de la LAN y wan de los clientes. También puede verse afectado por los servicios o dispositivos intermediarios de red, que retrasan la conectividad o hacen que los paquetes se resienten. Y se impacta por lo lejos que se encuentra la puerta Exchange de servicio más cercana. La mediana (también conocida como percentil 50 o medida P50) se toma para todas las medidas de los tres días anteriores.

La Exchange Online se realiza con la siguiente tabla. Cualquier número de latencia TCP entre los umbrales se asignan puntos linealmente dentro de la banda.

| Latencia TCP   | Points |
| :------------ | :----- |
| 10 ms o menos  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms o más | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Para SharePoint Online, se mide la velocidad de descarga disponible para que un usuario obtenga acceso a un documento SharePoint o OneDrive. Esto se puede ver afectado por el ancho de banda disponible en los circuitos de red entre el equipo cliente y la red de Microsoft. También se ve afectada a menudo por la congestión de la red que existe en cuellos de botella en dispositivos de red complejos o en áreas de Wi-Fi deficiente. La velocidad de descarga se mide en megabytes por segundo, que es aproximadamente una décima parte de un megabits clasificados por circuitos por segundo. La unidad MegaByte por segundo es útil porque puede ver directamente qué archivo de tamaño se puede descargar en 1 segundo. El percentil 25 (también conocido como medida P25) se toma para todas las medidas de los tres días anteriores. Este percentil 25 ayuda a reducir el impacto de la congestión variable con el tiempo.

La SharePoint online se realiza con la siguiente tabla. Cualquier número de velocidad de descarga entre los umbrales se asignan puntos linealmente dentro de la banda.

| Velocidad de descarga | Points |
| :------------- | :----- |
| 20MBps o más | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Por Microsoft Teams la calidad de la red se mide como latencia UDP, vibración UDP y pérdida de paquetes UDP. UDP se usa para la conectividad de medios de audio y vídeo de llamadas y conferencias para Microsoft Teams. Esto se puede ver afectado por los mismos factores que para la velocidad de latencia y descarga, además de las diferencias de conectividad en la compatibilidad udp de una red, ya que UDP se configura por separado para el protocolo TCP más común. La mediana (también conocida como percentil 50 o medida P50) se toma para todas las medidas de los tres días anteriores. 

Calculamos una puntuación media de opinión a partir de estas medidas UDP para una escala de uno a cinco. A continuación, se asigna a la escala de 0 a 100 puntos para la Microsoft Teams de red.  El bien general supera los 87,5 puntos y el valor malo general está por debajo de los 50 puntos.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro Microsoft 365 administración (versión preliminar)](office-365-network-mac-perf-overview.md)

[Microsoft 365 de rendimiento de red (versión preliminar)](office-365-network-mac-perf-insights.md)

[Microsoft 365 de prueba de conectividad de red (versión preliminar)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Servicios de ubicación de conectividad de red (versión preliminar)](office-365-network-mac-location-services.md)
