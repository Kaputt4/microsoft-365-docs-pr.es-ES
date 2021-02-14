---
title: Evaluación de red de Microsoft 365 (versión preliminar)
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
description: Evaluación de red de Microsoft 365 (versión preliminar)
ms.openlocfilehash: 3d80130dbf9ca41342bc1a01fe3ce992303efb48
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200752"
---
# <a name="microsoft-365-network-assessment-preview"></a>Evaluación de red de Microsoft 365 (versión preliminar)

En la conectividad de red del Centro de administración de Microsoft 365, las evaluaciones de red representan un agregado de muchas **métricas** de rendimiento de red en una instantánea del estado perimetral de la red empresarial, representada por un valor de puntos de 0 a 100. Una evaluación de red le indica cuánto el diseño de red responsable del cliente está afectando a la experiencia de usuario de Office 365. Las evaluaciones de red se encuentran en el ámbito de todo el inquilino y de cada ubicación geográfica desde la que los usuarios se conectan a su espacio empresarial, lo que proporciona a los administradores de Microsoft 365 una forma sencilla de comprender al instante el estado de la red de la empresa y explorar rápidamente un informe detallado de cualquier ubicación de oficina global.

El valor de puntos de evaluación de red es un promedio de latencia TCP, velocidad de descarga y métricas de calidad de conexión UDP compiladas una vez al día. Las métricas de rendimiento de las redes propiedad de Microsoft se excluyen de estas medidas para garantizar que los resultados de la evaluación sean inequívocos y específicos para la red corporativa.

![Valor de evaluación de red](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Un valor de evaluación de red muy bajo sugiere que los clientes de Microsoft 365 tendrán problemas importantes para conectarse al inquilino o mantener una experiencia de usuario dinámica, mientras que un valor alto indica una red configurada correctamente con pocos problemas de rendimiento en curso. Un valor del 80 % representa una línea base en buen estado en la que no debería esperar recibir quejas regulares de los usuarios sobre la conectividad o la capacidad de respuesta de Microsoft 365 debido al rendimiento de la red. A medida que se realizan mejoras en la conectividad de red iterativa, este valor aumentará junto con la experiencia del usuario.

| Evaluación de la red | Experiencia de usuario esperada |
| :----------------- | :----------------------- |
| 100                | Procedimientos                     |
| 80                 | Cumple las recomendaciones    |
| 60                 | Aceptable               |
| 40                 | Los usuarios pueden experimentar problemas |
| 20                 | Los usuarios pueden quejarse       |
| 0                  | Problemas de red un tema común de discusión |

>[!IMPORTANT]
>Información de red, recomendaciones de rendimiento y evaluaciones en el Centro de administración de Microsoft 365 se encuentra actualmente en estado de vista previa y solo está disponible para los inquilinos de Microsoft 365 que se han inscrito en el programa de vista previa de características.

## <a name="network-assessment-panel"></a>Panel de evaluación de red

Cada evaluación de red, ya sea en el ámbito del inquilino o en una ubicación de oficina específica, muestra un panel con detalles sobre la evaluación. Este panel muestra un gráfico de barras de la evaluación como porcentaje y como puntos totales de cada carga de trabajo de componentes, incluidas solo las cargas de trabajo en las que se recibieron los datos de medición. Para una evaluación de la red de ubicación de la oficina, también mostramos una comparación con el porcentaje de clientes de Microsoft 365 en cada uno de los cinco idiomas que informaron de datos en la misma ciudad que la ubicación de la oficina.

![Valor de evaluación de red de ejemplo](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

El **desglose de la** evaluación del panel muestra la evaluación de cada una de las cargas de trabajo de componentes.

El **historial de evaluaciones** muestra los últimos 30 días de la evaluación y el banco de pruebas. También puede informar sobre el historial de métricas de cualquier ubicación de la oficina durante un máximo de dos años mediante la pestaña historial. La pestaña historial le permite seleccionar los atributos sobre los que desea informar y, al elegir un período de tiempo de informe, puede resaltar el impacto de un proyecto de actualización de red y ver la mejora de la evaluación de red.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Evaluaciones de red de inquilinos y evaluaciones de red de ubicación de oficinas

Una evaluación de red mide el diseño del perímetro de red de una ubicación de oficina en la red de Microsoft. Las mejoras en el perímetro de red se realizan mejor en cada ubicación de la oficina.

Se muestra un valor de evaluación de red para todo el inquilino de Microsoft 365 en la página de información general sobre el rendimiento de la red, que es un promedio ponderado de las evaluaciones de red para todas las ubicaciones de oficinas. También hay un valor de evaluación de red específico para cada ubicación de oficina detectada en la página de resumen de esa ubicación.

## <a name="exchange-online"></a>Exchange Online

Para Exchange Online, se mide la latencia TCP desde el equipo cliente hasta la puerta frontal del servicio de Exchange. Esto se puede ver afectado por la distancia que recorre la red a través de la LAN y wan de los clientes. También puede verse afectado por los servicios o dispositivos intermediarios de red que retrasan la conectividad o hacen que los paquetes se reenviarán. Y se verán afectados por la distancia a la que se encuentra la puerta de servicio de Exchange más cercana. La mediana (también conocida como percentil 50 o medida P50) se toma para todas las medidas en los tres días anteriores.

La evaluación de Exchange Online se realiza con la tabla siguiente. Cualquier número de latencia TCP entre los umbrales se asignan puntos linealmente dentro de la banda.

| Latencia TCP   | Points |
| :------------ | :----- |
| 10 ms o menos  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms o más | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Para SharePoint Online, se mide la velocidad de descarga disponible para que un usuario obtenga acceso a un documento desde SharePoint o OneDrive. Esto se puede ver afectado por el ancho de banda disponible en los circuitos de red entre el equipo cliente y la red de Microsoft. A menudo también se ve afectado por la congestión de la red que existe en cuellos de botella en dispositivos de red complejos o en una cobertura deficiente Wi-Fi áreas. La velocidad de descarga se mide en megabytes por segundo, que es aproximadamente una décima parte de los megabits clasificados de circuitos por segundo. La unidad MegaByte por segundo es útil porque puedes ver directamente qué archivo de tamaño se puede descargar en 1 segundo. El percentil 25 (también conocido como medida P25) se toma para todas las medidas en los tres días anteriores. Este percentil 25 ayuda a reducir el impacto de la congestión variable con el tiempo.

La evaluación de SharePoint Online se realiza con la tabla siguiente. Cualquier número de velocidad de descarga entre los umbrales se asignan puntos linealmente dentro de la banda.

| Velocidad de descarga | Points |
| :------------- | :----- |
| 20MBps o más | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Para Microsoft Teams, la calidad de la red se mide como latencia UDP, vibración UDP y pérdida de paquetes UDP. UDP se usa para la conectividad de medios de audio y vídeo de llamadas y conferencias para Microsoft Teams. Esto se puede ver afectado por los mismos factores que para la latencia y la velocidad de descarga, además de las diferencias de conectividad en la compatibilidad UDP de una red, ya que UDP se configura por separado para el protocolo TCP más común. La mediana (también conocida como percentil 50 o medida P50) se toma para todas las medidas en los tres días anteriores. 

Calculamos una puntuación de opinión media a partir de estas medidas UDP para una escala de uno a cinco. A continuación, lo asignamos a la escala de 0 a 100 puntos para la evaluación de red de Microsoft Teams.  En general, el valor bueno es de más de 87,5 puntos y el valor general no es bueno por debajo de los 50 puntos.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de administración de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-overview.md)

[Información sobre el rendimiento de la red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-insights.md)

[Herramienta de prueba de conectividad de red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-onboarding-tool.md)

[Servicios de ubicación de conectividad de red de Microsoft 365 (versión preliminar)](office-365-network-mac-location-services.md)
