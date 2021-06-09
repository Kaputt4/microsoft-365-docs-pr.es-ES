---
title: Módulo de codificación predictiva para Advanced eDiscovery (versión preliminar)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: El nuevo módulo de codificación predictiva de Advanced eDiscovery usa el aprendizaje automático para analizar elementos de un conjunto de revisión para predictiva cuáles son los elementos relevantes para su caso o investigación.
ms.openlocfilehash: 3c8fbd75bd585dd6ae722bf17deea906611d8df6
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822047"
---
# <a name="learn-about-predictive-coding-in-advanced-ediscovery-preview"></a>Obtenga información sobre la codificación predictiva en Advanced eDiscovery (versión preliminar)

El módulo de codificación predictiva Advanced eDiscovery las capacidades inteligentes de aprendizaje automático para ayudarle a reducir la cantidad de contenido que se va a revisar. La codificación predictiva le ayuda a reducir y asignar grandes volúmenes de contenido de caso a un conjunto relevante de elementos que puede priorizar para su revisión. Para ello, cree y entrena sus propios modelos de codificación predictiva que le ayudarán a priorizar la revisión de los elementos más relevantes de un conjunto de revisión.

El módulo de codificación predictiva está diseñado para simplificar la complejidad de administrar un modelo dentro de un conjunto de revisión y proporcionar un enfoque iterativo para entrenar el modelo para que pueda empezar más rápido con las capacidades de aprendizaje automático en Advanced eDiscovery. Para empezar, puede crear un modelo, etiquetar hasta 50 elementos como relevantes o no relevantes. El sistema usa este aprendizaje para aplicar puntuaciones de predicción a todos los elementos del conjunto de revisión. Esto le permite filtrar elementos en función de la puntuación de predicción, lo que le permite revisar primero los elementos más relevantes (o no relevantes). Si desea entrenar modelos con tasas de recuperación y acutracaciones más altas, puede seguir etiquetando elementos en rondas de aprendizaje posteriores hasta que el modelo se estabilice.  

## <a name="the-predictive-coding-workflow"></a>Flujo de trabajo de codificación predictiva

A continuación se ofrece información general y una descripción de cada flujo de trabajo de codificación predictiva de cada paso. Para obtener una descripción más detallada de los conceptos y terminología del proceso de codificación [predictiva,](predictive-coding-reference.md)vea Predictive coding reference .

![Flujo de trabajo de codificación predictiva](..\media\PredictiveCodingWorkflow.png)

1. **Cree un nuevo modelo de codificación predictiva en el conjunto de revisión**. El primer paso es crear un nuevo modelo de codificación predictiva en el conjunto de revisión. Debe tener al menos 2.000 elementos en el conjunto de revisión para crear un modelo. Después de crear un modelo, el sistema determinará el número de elementos que se van a usar como un *conjunto de controles*. El conjunto de controles se usa durante el proceso de aprendizaje para evaluar las puntuaciones de predicción que el modelo asigna a los elementos con el etiquetado que se realiza durante las rondas de aprendizaje. El tamaño del conjunto de controles se basa en el número de elementos del conjunto de revisión y el nivel de confianza y el margen de error que se establecen al crear el modelo. Los elementos del conjunto de controles nunca cambian y no son identificables para los usuarios.

   Para obtener más información, vea [Create a predictive coding model](predictive-coding-create-model.md).

2. **Complete la primera ronda de aprendizaje etiquetando los elementos como relevantes o no relevantes**. El siguiente paso es entrenar el modelo iniciando la primera ronda de aprendizaje. Al iniciar una ronda de aprendizaje, el modelo selecciona aleatoriamente elementos adicionales del conjunto de revisión, que se denomina conjunto *de aprendizaje*. Estos elementos (tanto del conjunto de controles como del conjunto de aprendizaje) se presentan para que pueda etiquetar cada uno como "relevante" o "no relevante". La relevancia se basa en el contenido del elemento y no en ninguno de los metadatos del documento. Después de completar el proceso de etiquetado en la ronda de aprendizaje, el modelo "aprenderá" en función de cómo se etiquetaron los elementos del conjunto de aprendizaje. En función de este aprendizaje, el modelo procesará los elementos del conjunto de revisión y aplicará una puntuación de predicción a cada uno de ellos.

   Para obtener más información, vea [Train a predictive coding model](predictive-coding-train-model.md).

3. **Aplicar el filtro de puntuación de predicción a los elementos del conjunto de revisión**. Una vez completado el paso de aprendizaje anterior, el siguiente paso es aplicar el filtro de puntuación de predicción a los elementos de la revisión para mostrar los elementos que el modelo ha determinado que son "más relevantes" (como alternativa, también podría usar un filtro de predicción para mostrar elementos que "no son relevantes"). Al aplicar el filtro de predicción, se especifica un intervalo de puntuaciones de predicción para filtrar. El intervalo de puntuaciones de predicción se encuentra entre **0** y **1,** siendo **0** "no relevante" y **1** relevante. En general, los elementos con puntuaciones de predicción entre **0** y **0,5** se consideran "no relevantes" y los elementos con puntuaciones de predicción entre **0,5** y **1** se consideran relevantes.

   Para obtener más información, vea [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).

4. **Realice más rondas de aprendizaje hasta que el modelo se estabilice**. Puedes realizar rondas de aprendizaje adicionales si quieres crear un modelo con mayor precisión de predicción y mayores tasas de recuperación. *La tasa de* recuperación mide la proporción de elementos que predijo que el modelo era relevante entre los elementos que son realmente relevantes (los que marcó como relevantes durante el aprendizaje). La puntuación de velocidad de recuperación oscila **entre 0** y **1**. Una puntuación más cercana a **1** indica que el modelo identificará elementos más relevantes. En una nueva ronda de aprendizaje, se etiquetan elementos adicionales en un nuevo conjunto de aprendizaje. Después de completar esa ronda de aprendizaje, el modelo se actualiza en función del nuevo aprendizaje de la ronda más reciente de elementos de etiquetado del conjunto de aprendizaje. El modelo procesará los elementos del conjunto de revisión de nuevo y aplicará nuevas puntuaciones de predicción. Puedes seguir realizando rondas de aprendizaje hasta que el modelo se estabilice. Un modelo se considera estabilizado cuando la tasa de renovación después de la última ronda de aprendizaje es inferior al 5 %. *La tasa de rotación* se define como porcentaje de elementos de un conjunto de revisión donde la puntuación de predicción cambió entre rondas de entrenamiento. El panel de codificación predictiva muestra información y estadísticas que le ayudarán a evaluar la estabilidad de un modelo.

5. **Aplicar el filtro de puntuación de predicción "final" para revisar los elementos establecidos para priorizar la revisión**. Después de completar todas las rondas de aprendizaje y estabilizar el modelo, el último paso consiste en aplicar la puntuación de predicción final al conjunto de revisión para priorizar la revisión de elementos relevantes y no relevantes. Esta es la misma tarea que realizó en el paso 3, pero en este momento el modelo es estable y no tiene previsto ejecutar más rondas de aprendizaje.
