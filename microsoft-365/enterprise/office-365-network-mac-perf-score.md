---
title: Evaluación de red de Microsoft 365
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
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
description: Evaluación de red de Microsoft 365
ms.openlocfilehash: 641b1b756872a6addfa5050276cc78cc257e4c86
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68169417"
---
# <a name="microsoft-365-network-assessment"></a>Evaluación de red de Microsoft 365

En la conectividad de red del Centro de Administración de Microsoft 365, **las evaluaciones de red** destilan un agregado de muchas métricas de rendimiento de red en una instantánea del estado del perímetro de la red empresarial. Una evaluación de red le indica cuánto afecta el diseño de red responsable del cliente Office 365 experiencia del usuario. Las evaluaciones de red se limitan a todo el inquilino y a cada ubicación geográfica desde la que los usuarios se conectan al inquilino. Las evaluaciones proporcionan a los administradores de Microsoft 365 una manera fácil de obtener al instante una idea del estado de la red de la empresa y explorar en profundidad rápidamente un informe detallado para cualquier ubicación de la oficina global.

El valor de los puntos de evaluación de red es de 0 a 100 y es un promedio de latencia TCP, velocidad de descarga y métricas de calidad de la conexión UDP. Estas métricas se compilan una vez al día. Estas mediciones no incluyen las métricas de rendimiento de las redes propiedad de Microsoft, con el fin de garantizar que los resultados de la evaluación sean inequívocos y específicos de la red corporativa.

> [!div class="mx-imgBorder"]
> ![Valor de evaluación de red.](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Un valor de evaluación de red muy bajo sugiere que los clientes de Microsoft 365 tendrán problemas importantes para conectarse al inquilino o mantener una experiencia de usuario con capacidad de respuesta. Un valor alto indica una red configurada correctamente con pocos problemas de rendimiento habituales. Un valor del 80 % representa una base aceptable. Por encima de este valor no debería esperar recibir quejas de usuarios sobre la conectividad o capacidad de respuesta de Microsoft 365 causadas por el rendimiento de la red. A medida que se realicen mejoras iterativas de conectividad de red, este valor aumentará y la experiencia del usuario será superior.

| Evaluación de la red | Experiencia de usuario esperada |
| :----------------- | :----------------------- |
| 100                | Procedimientos                     |
| 80                 | Cumple las recomendaciones    |
| 60                 | Es aceptable               |
| 40                 | Los usuarios pueden tener problemas |
| 20                 | Los usuarios pueden quejarse ocasionalmente       |
| 0                  | Los usuarios se quejan habitualmente de problemas de red |

## <a name="network-assessment-panel"></a>Panel de evaluación de red

Cada evaluación de red, ya sea en el ámbito del inquilino o en una ubicación de oficina específica, muestra un panel con detalles sobre la evaluación. En este panel hay un gráfico de barras que muestra la evaluación (tanto en porcentaje como en puntos totales) de cada carga de trabajo de componente. Incluye solo las cargas de trabajo en las que se recibieron datos de mediciones. Para una evaluación de la red de ubicación de la oficina, también mostramos una comparación con el porcentaje de clientes de Microsoft 365 en cada uno de los cinco quintiles que notificaron datos en la misma ciudad que la ubicación de la oficina.

> [!div class="mx-imgBorder"]
> ![Valor de evaluación de red de ejemplo.](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

El **desglose evaluación** del panel muestra la evaluación de cada una de las cargas de trabajo de componentes.

El **historial de evaluación** muestra los últimos 30 días de la evaluación y la prueba comparativa. También puede informar sobre el historial de métricas de cualquier ubicación de oficina durante un máximo de dos años mediante la pestaña Historial. La pestaña Historial permite seleccionar los atributos de los que se va a informar. Al elegir un período de tiempo del que informar, puede destacar el impacto de un proyecto de actualización de red y ver la mejora en la evaluación de red.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Evaluaciones de red de inquilinos y evaluaciones de red de ubicación de oficina

Una evaluación de red mide el diseño del perímetro de red de una ubicación de oficina a la red de Microsoft. Las mejoras en el perímetro de red se realizan mejor en cada ubicación de la oficina.

Se muestra un valor de evaluación de red para todo el inquilino de Microsoft 365 en la página de información general sobre el rendimiento de la red. Este valor es un promedio ponderado de las evaluaciones de red para todas las ubicaciones de oficina. También hay un valor de evaluación de red específico para cada ubicación de oficina detectada en la página de resumen de esa ubicación.

## <a name="exchange-online"></a>Exchange Online

Por Exchange Online, se mide la latencia TCP de la máquina cliente a la puerta principal del servicio Exchange. Esta latencia puede verse afectada por la distancia que la red recorre a través de la LAN y WAN de los clientes. También puede verse afectado por dispositivos o servicios intermediarios de red, que retrasan la conectividad o hacen que los paquetes se resientan. Y se ve afectado por la distancia a la que se encuentra la puerta principal del servicio exchange más cercano. La mediana (también conocida como percentil 50 o medida P50) se toma para todas las mediciones de los tres días anteriores.

La evaluación Exchange Online se realiza mediante la tabla siguiente. Cualquier número de latencia TCP entre los umbrales se asigna linealmente dentro de la banda.

| Latencia de TCP   | Points |
| :------------ | :----- |
| 10 ms o menos  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms o más | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Para SharePoint Online, se mide la velocidad de descarga disponible para que un usuario acceda a un documento desde SharePoint o OneDrive. Esto puede verse afectado por el ancho de banda disponible en los circuitos de red entre la máquina cliente y la red de Microsoft. A menudo también se ve afectado por la congestión de la red que existe en cuellos de botella en dispositivos de red complejos o en una cobertura deficiente Wi-Fi áreas. La velocidad de descarga se mide en megabytes por segundo, que es aproximadamente una décima parte de un circuito clasificado megabits por segundo. La unidad MegaByte por segundo es útil porque puede ver directamente qué archivo de tamaño se puede descargar en 1 segundo. El percentil 25 (también conocido como medida P25) se toma para todas las medidas de los tres días anteriores. Este percentil 25 ayuda a reducir el impacto de una congestión variable a lo largo del tiempo.

La evaluación de SharePoint Online se realiza mediante la tabla siguiente. Cualquier número de velocidad de descarga entre los umbrales se asigna linealmente dentro de la banda.

| Velocidad de descarga | Points |
| :------------- | :----- |
| 20 MBps o más | 100    |
| 14 MBps         | 80     |
| 8Mbps          | 60     |
| 4Mbps          | 40     |
| 2Mbps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Para Microsoft Teams, la calidad de red se mide como latencia UDP, vibración UDP y pérdida de paquetes UDP. El UDP se usa para la conectividad multimedia de audio y vídeo de llamadas y conferencias para Microsoft Teams. Esto puede verse afectado por los mismos factores que la latencia y la velocidad de descarga, además de las brechas de conectividad en la compatibilidad con UDP de una red, ya que el UDP se configura de forma separada al protocolo TCP, que es más común. La mediana (también conocida como percentil 50 o medida P50) se toma para todas las mediciones de los tres días anteriores. 

Calculamos una puntuación media de opinión a partir de estas medidas UDP para una escala de uno a cinco. A continuación, lo asignamos a la escala de 0 a 100 puntos para la evaluación de red de Microsoft Teams.  En general, una puntuación positiva es superior a 87,5 puntos y una negativa es inferior a 50 puntos.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de Administración de Microsoft 365](office-365-network-mac-perf-overview.md)

[Información sobre el rendimiento de red de Microsoft 365](office-365-network-mac-perf-insights.md)

[Prueba de conectividad de red de Microsoft 365](office-365-network-mac-perf-onboarding-tool.md)

[Servicios de ubicación de conectividad de red de Microsoft 365](office-365-network-mac-location-services.md)
