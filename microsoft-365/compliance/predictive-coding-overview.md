---
title: Módulo de codificación predictiva para eDiscovery (Premium) (versión preliminar)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: El nuevo módulo de codificación predictiva de eDiscovery (Premium) usa el aprendizaje automático para analizar los elementos de un conjunto de revisión para predecir qué elementos son relevantes para su caso o investigación.
ms.openlocfilehash: 3ea3d59aa2387b1a762e66fd11942ed96a6288a2
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625047"
---
# <a name="learn-about-predictive-coding-in-ediscovery-premium-preview"></a>Más información sobre la codificación predictiva en eDiscovery (Premium) (versión preliminar)

El módulo de codificación predictiva de eDiscovery (Premium) usa las funcionalidades de aprendizaje automático inteligentes para ayudarle a reducir la cantidad de contenido que se va a revisar. La codificación predictiva le ayuda a reducir y seleccionar grandes volúmenes de contenido de casos en un conjunto pertinente de elementos que puede priorizar para su revisión. Esto se logra mediante la creación y el entrenamiento de sus propios modelos de codificación predictiva que le ayudan a priorizar la revisión de los elementos más relevantes de un conjunto de revisión.

El módulo de codificación predictiva está diseñado para simplificar la complejidad de la administración de un modelo dentro de un conjunto de revisión y proporcionar un enfoque iterativo para entrenar el modelo para que pueda empezar a trabajar más rápido con las funcionalidades de aprendizaje automático en eDiscovery (Premium). Para empezar, puede crear un modelo, etiquetar tan solo 50 elementos como pertinentes o no pertinentes. El sistema usa este entrenamiento para aplicar puntuaciones de predicción a cada elemento del conjunto de revisión. Esto le permite filtrar los elementos en función de la puntuación de predicción, lo que le permite revisar primero los elementos más relevantes (o no relevantes). Si desea entrenar modelos con mayores precisiónes y tasas de recuperación, puede seguir etiquetando elementos en rondas de entrenamiento posteriores hasta que el modelo se estabilice.  

## <a name="the-predictive-coding-workflow"></a>Flujo de trabajo de codificación predictiva

A continuación se muestra información general y descripción de cada flujo de trabajo de codificación predictiva de cada paso. Para obtener una descripción más detallada de los conceptos y terminología del proceso de codificación predictiva, consulte [Referencia de codificación predictiva](predictive-coding-reference.md).

![Flujo de trabajo de codificación predictiva.](..\media\PredictiveCodingWorkflow.png)

1. **Cree un nuevo modelo de codificación predictiva en el conjunto de revisión**. El primer paso consiste en crear un nuevo modelo de codificación predictiva en el conjunto de revisión. Debe tener al menos 2000 elementos en el conjunto de revisión para crear un modelo. Después de crear un modelo, el sistema determinará el número de elementos que se usarán como *conjunto de controles*. El conjunto de controles se usa durante el proceso de entrenamiento para evaluar las puntuaciones de predicción que el modelo asigna a los elementos con el etiquetado que se realiza durante las rondas de entrenamiento. El tamaño del conjunto de controles se basa en el número de elementos del conjunto de revisión y en el nivel de confianza y el margen de los valores de error que se establecen al crear el modelo. Los elementos del conjunto de controles nunca cambian y no son identificables para los usuarios.

   Para obtener más información, consulte [Creación de un modelo de codificación predictiva](predictive-coding-create-model.md).

2. **Complete la primera ronda de entrenamiento etiquetando los elementos como pertinentes o no pertinentes**. El siguiente paso consiste en entrenar el modelo iniciando la primera ronda de entrenamiento. Al iniciar una ronda de entrenamiento, el modelo selecciona aleatoriamente elementos adicionales del conjunto de revisión, que se denomina conjunto de *entrenamiento*. Estos elementos (tanto del conjunto de control como del conjunto de entrenamiento) se presentan para que pueda etiquetar cada uno de ellos como "pertinente" o "no relevante". La relevancia se basa en el contenido del elemento y no en ninguno de los metadatos del documento. Después de completar el proceso de etiquetado en la ronda de entrenamiento, el modelo "aprenderá" en función de cómo haya etiquetado los elementos en el conjunto de entrenamiento. En función de este entrenamiento, el modelo procesará los elementos del conjunto de revisión y aplicará una puntuación de predicción a cada uno.

   Para obtener más información, consulte [Entrenamiento de un modelo de codificación predictiva](predictive-coding-train-model.md).

3. **Aplique el filtro de puntuación de predicción a los elementos del conjunto de revisión**. Una vez completado el paso de entrenamiento anterior, el siguiente paso es aplicar el filtro de puntuación de predicción a los elementos de la revisión para mostrar que los elementos que el modelo ha determinado son "más relevantes" (como alternativa, también podría usar un filtro de predicción para mostrar elementos que "no son pertinentes"). Cuando se aplica el filtro de predicción, se especifica un intervalo de puntuaciones de predicción que se van a filtrar. El intervalo de puntuaciones de predicción se encuentra entre **0** y **1**, siendo **0** "no relevante" y **1** relevante. En general, los elementos con puntuaciones de predicción entre **0** y **0,5** se consideran "no relevantes" y los elementos con puntuaciones de predicción entre **0,5** y **1** se consideran pertinentes.

   Para obtener más información, vea [Aplicar un filtro de predicción a un conjunto de revisión](predictive-coding-apply-prediction-filter.md).

4. **Realice más rondas de entrenamiento hasta que el modelo se estabilice**. Puede realizar rondas de entrenamiento adicionales si desea crear un modelo con una mayor precisión de predicción y mayores tasas de recuperación. *La tasa de recuperación* mide la proporción de elementos que el modelo predicho era relevante entre los elementos que son realmente pertinentes (los que ha marcado como pertinentes durante el entrenamiento). La puntuación de velocidad de recuperación oscila entre **0** y **1**. Una puntuación más cercana a **1** indica que el modelo identificará elementos más relevantes. En una nueva ronda de entrenamiento, se etiquetan elementos adicionales en un nuevo conjunto de entrenamiento. Después de completar esa ronda de entrenamiento, el modelo se actualiza en función del nuevo aprendizaje de la última ronda de elementos de etiquetado del conjunto de entrenamiento. El modelo procesará de nuevo los elementos del conjunto de revisión y aplicará nuevas puntuaciones de predicción. Puede seguir realizando rondas de entrenamiento hasta que el modelo se estabilice. Un modelo se considera estabilizado cuando la tasa de abandono después de la última ronda de entrenamiento es inferior al 5 %. *La tasa de abandono* se define como porcentaje de elementos de un conjunto de revisión donde la puntuación de predicción cambió entre las rondas de entrenamiento. El panel de codificación predictiva muestra información y estadísticas que le ayudan a evaluar la estabilidad de un modelo.

5. **Aplique el filtro de puntuación de predicción "final" para revisar los elementos establecidos para priorizar la revisión**. Después de completar todas las rondas de entrenamiento y estabilizar el modelo, el último paso es aplicar la puntuación de predicción final al conjunto de revisión para priorizar la revisión de los elementos pertinentes y no pertinentes. Esta es la misma tarea que realizó en el paso 3, pero en este momento el modelo es estable y no tiene previsto ejecutar más rondas de entrenamiento.
