---
title: 'Puntuación de adopción de Microsoft: reuniones (nuevas)'
f1.keywords: NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
ms.reviewer: ''
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- scotvorg
- highpri
ms.custom: ''
search.appverid: MET150
description: 'Detalles de la nueva puntuación de conclusiones de reuniones: la puntuación de adopción de las experiencias de las personas.'
ms.openlocfilehash: 7e4dd45a5ec8bec72a5ddaa4beb3bd1223b98a0c
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2022
ms.locfileid: "68566411"
---
# <a name="meetings-insights-score--people-experiences-new"></a>Puntuación de conclusiones de reuniones: experiencias Personas (nuevas)

La Puntuación de adopción proporciona información sobre el recorrido de transformación digital de su organización a través de su uso de Microsoft 365 y las experiencias tecnológicas que la admiten. La puntuación de su organización refleja las mediciones de la experiencia de las personas y la tecnología y se puede comparar con las pruebas comparativas de organizaciones similares a las suyas. La categoría de reuniones forma parte de las medidas de experiencia de las personas. Para obtener más información, consulte la [introducción a la puntuación de adopción](adoption-score.md) y lea [la Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="prerequisites"></a>Requisitos previos

Para empezar a trabajar con meetings insights, los usuarios de su organización deben tener licencia para:

- Microsoft Teams

Para obtener más información, consulte [Asignación de licencias a usuarios](../manage/assign-licenses-to-users.md).

Una vez que las personas hayan estado activas en Teams al menos una vez en los últimos 28 días, comenzará a ver la información.

## <a name="why-your-organizations-meetings-score-matters"></a>Por qué importa la puntuación de las reuniones de su organización

Las reuniones, en las que los usuarios exploran ideas, planean, resuelven problemas y toman decisiones, son un pilar fundamental para la productividad de la organización. La investigación indica que, cuando los usuarios usan las herramientas de reunión en línea de forma eficaz, tienden a ahorrar hasta 104 minutos a la semana.

## <a name="how-we-calculate-the-meetings-score"></a>Cómo calculamos la puntuación de las reuniones

Microsoft Teams se integra con el calendario de Outlook y proporciona una gran variedad de funcionalidades para que las reuniones sean más atractivas y eficaces. Proporcionamos una puntuación general para reuniones y, a continuación, sub puntuaciones para cada uno de los procedimientos recomendados en las secciones Configurar, Reunirse y Seguimiento.

## <a name="overall-score"></a>Puntuación general

La puntuación general de la reunión se calcula promediando las puntuaciones en las tres fases, es decir, Configurar, Reunirse y Seguimiento. Tenemos en cuenta el número de asistentes y la duración de la reunión al contabilizar las puntuaciones medias finales.

Para cada reunión:

1. Calculamos las tres puntuaciones secundarias (Pre, During, Post), promediando las características para cada reunión. Por ejemplo, Configurar: 30, Reunirse: 40, Seguimiento: 20
1. A continuación, calculamos el promedio de las tres puntuaciones secundarias de la reunión. En el ejemplo anterior, 30+40+20/3 = 30
1. Calculamos el peso de cada reunión en función de la duración de la reunión y el tamaño de la reunión. Cuanto más larga o mayor sea una reunión, más impacto tendrá en la puntuación final.
1. A continuación, se realiza un promedio de suma ponderado en las puntuaciones de todas las reuniones del inquilino en función de los pesos de las reuniones para calcular la puntuación final de la reunión para el inquilino.

:::image type="content" source="../../media/adoption-score-meetings.jpg" alt-text="Captura de pantalla: Puntuación de reunión para reuniones de Microsoft Teams":::

1. **Encabezado**: muestra la puntuación, de 100, en función del promedio de las fases de configuración, reunión y seguimiento de las reuniones en línea en Microsoft Teams celebradas en los últimos 28 días.
1. **Cuerpo**: proporciona más información sobre cómo el uso eficaz de las herramientas de reuniones en línea puede hacer que las reuniones sean más eficaces.
1. **Visualización (estado actual):** en este gráfico de barras horizontal, la parte azul (coloreada) representa la puntuación (de 100) que se muestra en el encabezado.

## <a name="trend-visualization-of-the-score"></a>Visualización de tendencias de la puntuación

En el gráfico siguiente se muestra la línea de tendencia de la puntuación durante el período seleccionado. Cada punto de datos del gráfico de líneas es un agregado de actividad de los últimos 28 días.

:::image type="content" source="../../media/meetings-time-trend.jpg" alt-text="Captura de pantalla: Gráfico de tendencias de tiempo para la puntuación de la reunión":::

## <a name="what-makes-up-my-score"></a>¿Qué constituye mi puntuación?

Le proporcionamos datos de soporte técnico sobre cada una de las fases de configuración, reunión y seguimiento. La puntuación de cada información se calcula de 100.

## <a name="set-up"></a>Configurar

Esto representa la fase que implica programar y compartir los detalles de la reunión y los participantes que se unen a la reunión.

:::image type="content" source="../../media/meetings-set-up.jpg" alt-text="Captura de pantalla: sección Configurar fase para la puntuación de la reunión":::

- **Comunicación compartida con antelación**: representa la puntuación de las reuniones de Microsoft Teams que tenían un chat de reunión de conversación de Teams iniciado antes de llevar a cabo la reunión. Para realizar un seguimiento de esto, un usuario debe ir al chat de la reunión con los participantes y enviar un mensaje a los participantes, antes de la hora programada de la reunión.
- **Programado con un aviso de al menos 24 horas**: representa la puntuación de las reuniones de Microsoft Teams programadas al menos 24 horas antes de su hora de inicio.
- **Invitación aceptada a una tasa alta (>50 %)**: esto representa la puntuación de las reuniones de Microsoft Teams que tenían más del 50 % de los participantes invitados que aceptan la invitación a la reunión.
- **Unido en un plazo de 5 minutos a la hora de inicio (>50 %)**: esto representa la puntuación de las reuniones de Microsoft Teams que tenían más del 50 % de los participantes invitados que se unen a la reunión en un plazo de 5 minutos a partir de la hora de inicio.

## <a name="meet-up"></a>Reunirse

Esto representa la fase de cuando los asistentes están en la reunión.

:::image type="content" source="../../media/meetings-meet-up.jpg" alt-text="Captura de pantalla: Sección de la fase de reunión para obtener la puntuación de la reunión":::

- **Se usa al menos una característica interactiva**: representa la puntuación de las reuniones de Microsoft Teams que han hecho que los asistentes usen al menos una característica interactiva. Estas características interactivas incluyen levantar la mano, enviar un mensaje de chat de reunión o enviar una reacción en la reunión. La puntuación se calcula de 100.
- **Participar con audio o chat a una velocidad alta (>33 %)**: esto representa la puntuación de las reuniones de Microsoft Teams que tenían más del 33 % de los participantes, ya sea hablar en una reunión, enviar un chat de reunión o ambos. La puntuación se calcula de 100.
- **Contenido visual compartido**: representa la puntuación de las reuniones de Microsoft Teams que hicieron que los asistentes compartiesen cualquier contenido visual de la reunión activando el vídeo, la pantalla de uso compartido o ambos. La puntuación se calcula de 100.

## <a name="follow-up"></a>Seguimiento

:::image type="content" source="../../media/meetings-follow-up.jpg" alt-text="Captura de pantalla: Sección de fase de seguimiento para la puntuación de la reunión":::

- **Grabación creada**: representa la puntuación de las reuniones de Microsoft Teams que grabaron la reunión. La puntuación se calcula de 100.
- **Comunicación posterior a la reunión enviada**: representa la puntuación de las reuniones de Microsoft Teams que tenían asistentes a compartir cualquier mensaje de chat en el subproceso de chat de reunión después de la conclusión de esa reunión. La puntuación se calcula de 100.

## <a name="how-can-i-impact-my-score"></a>¿Cómo puedo afectar a mi puntuación?

Esta sección ayuda a comprender dos conclusiones de la organización:

1. **Crecimiento más significativo**: en esta sección se muestra la parte de la puntuación que tuvo el mayor crecimiento en los últimos 28 días.
1. **Área más importante para la mejora**: en esta sección se muestra la parte de la puntuación que tiene el mayor espacio para mejorar e afectar la puntuación de adopción de la organización en el futuro.

## <a name="dig-deeper-into-meetings"></a>Profundizar en las reuniones

Esta sección consta de tres subsesiones:

1. **Información adicional**: aquí proporcionamos información adicional que ayuda a las organizaciones a identificar tendencias y comportamientos de usuario en las reuniones.
1. **Conclusiones interesantes**: aquí proporcionamos algunos datos interesantes sobre las reuniones que se llevan a cabo en la organización.
1. **Investigación de Microsoft**: aquí hacemos referencia a blogs de Microsoft e investigaciones públicas que proporcionan prácticas recomendadas y sus impactos para tener reuniones eficaces.

> [!NOTE]
> La sección "Profundizar más en las reuniones" no contribuye a la puntuación general de la página reuniones en la puntuación de adopción Personas experiencias, sin embargo, algunas conclusiones de esta sección pueden expandirse en una información principal que se usa para calcular una puntuación.

## <a name="related-content"></a>Contenido relacionado

[Estado de las aplicaciones de Microsoft 365: experiencias tecnológicas](apps-health.md) (artículo)\
[Comunicación: experiencias de Personas](communication.md) (artículo)\
[Colaboración de contenido: experiencias de Personas](content-collaboration.md) (artículo)\
[Movilidad: experiencias de Personas](mobility.md) (artículo)\
[Controles de privacidad para la puntuación de adopción](privacy.md) (artículo)\
[Trabajo en equipo: experiencias de Personas](teamwork.md) (artículo)
