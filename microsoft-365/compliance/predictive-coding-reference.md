---
title: Referencia de codificación predictiva
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
description: ''
ms.openlocfilehash: 90c76fade54c109fc02e145a49bbe93d11ad8b79
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822589"
---
# <a name="predictive-coding-reference-preview"></a>Referencia de codificación predictiva (versión preliminar)

En este artículo se describen los conceptos y métricas clave de la herramienta de codificación predictiva en Advanced eDiscovery. Las secciones del artículo se enumeran en orden alfabético.

## <a name="confidence-level"></a>Nivel de confianza

El nivel de confianza es una configuración avanzada al crear un modelo de codificación predictiva. Define que las métricas de rendimiento del modelo (por ejemplo, riqueza, precisión y recuperación) se encuentran dentro de un intervalo especificado (que determina el margen de error definido para el modelo) que representa los valores verdaderos de las puntuaciones de predicción que el modelo asigna a los elementos del conjunto de revisión. Los valores del nivel de confianza y el margen de error también ayudan a determinar cuántos elementos se incluyen en el conjunto de controles. El valor predeterminado del nivel de confianza es 0,95 o 95%.

## <a name="control-set"></a>Conjunto de controles

Se usa un conjunto de controles durante el proceso de aprendizaje de un modelo de codificación predictiva. El conjunto de controles es evaluar las puntuaciones de predicción que el modelo asigna a los elementos con el etiquetado que se realiza durante las rondas de aprendizaje. El tamaño del conjunto de controles se basa en el número de elementos del conjunto de revisión y el nivel de confianza y el margen de error que se establecen al crear el modelo. Los elementos del conjunto de controles nunca cambian y no son identificables para los usuarios. El número total de elementos del conjunto de controles se muestra en la página desplegable de una ronda de aprendizaje.

## <a name="control-set-confusion-matrix"></a>Matriz de confusión de conjunto de controles

Después de completar una ronda de aprendizaje, el modelo asigna una puntuación de predicción a los 10 elementos del conjunto de control que etiquetaste durante la ronda de entrenamiento. El modelo compara la puntuación de predicción de estos 10 elementos con la etiqueta real que asignó al elemento durante la ronda de entrenamiento. Basándose en esta comparación, el modelo identifica las siguientes clasificaciones para evaluar el rendimiento de predicción del modelo:
  
  |          |El modelo predice que el elemento es relevante |El modelo predice que el elemento no es relevante |
  |:---------|:---------|:---------|
  |**Elemento de etiquetas de revisor como relevante**| Verdadero positivo| Falso positivo |
  |**Elemento de etiquetas de revisor como no relevante**| Falso negativo |True negativo |
  ||||

  Basándose en estas comparaciones, el modelo deriva valores para las métricas de puntuación F, precisión y recuperación y el margen de error de cada una de ellas. El número de cada uno de los tipos de confusión de la matriz se muestra en la página desplegable de una ronda de entrenamiento.

## <a name="f-score"></a>Puntuación F

La puntuación F es un promedio ponderado de las puntuaciones de las métricas de precisión y recuperación.  El intervalo de puntuaciones de esta métrica va de **0** a **1**. Una puntuación más cercana a **1** indica que el modelo detectará con mayor precisión los elementos relevantes. La métrica de puntuación F se muestra en el panel del modelo y en la página desplegable de cada ronda de aprendizaje.

## <a name="margin-of-error"></a>Margen de error

El margen de error es una configuración avanzada al crear un modo de codificación predictiva. Especifica el grado de error en las métricas de rendimiento (por ejemplo, riqueza, precisión y recuperación) que se deriva del muestreo aleatorio de elementos del conjunto de controles. Un margen de error inferior requiere un conjunto de control más grande para garantizar que las métricas de rendimiento del modelo se encuentran dentro de un intervalo más pequeño. Los valores del margen de error y el nivel de confianza también ayudan a determinar cuántos elementos se incluyen en el conjunto de controles. El valor predeterminado del margen de error es 0,05 o 5%.

## <a name="model-stability"></a>Estabilidad del modelo

La estabilidad del modelo indica la capacidad del modelo para predecir con precisión si un documento de un conjunto de revisión es relevante o no es relevante. Cuando un modelo es inestable, es posible que deba realizarse más rondas de aprendizaje para incluir la estabilidad del modelo. Cuando el modelo es estable, no es necesario realizar más rondas de aprendizaje. El panel del modelo indica el estado actual de la estabilidad del modelo. Cuando un modelo es estable, las métricas de rendimiento han alcanzado un nivel que coincide con la configuración del nivel de confianza y el margen de error.

## <a name="overturn-rate"></a>Tasa de vuelco

La tasa de volcado es el porcentaje de elementos del conjunto de revisión donde la puntuación de predicción cambió entre rondas de entrenamiento. Un modelo se considera estable cuando la tasa de vuelco es inferior al 5 %. La métrica de velocidad de vuelco se muestra en el panel del modelo y en la página desplegable de cada ronda de aprendizaje. La tasa de vuelco de la primera ronda de entrenamiento es cero porque no hay una puntuación de predicción anterior para volcar.

## <a name="precision"></a>Precisión

La métrica de precisión mide la proporción de elementos que son realmente relevantes entre los elementos que el modelo predijo eran relevantes. Esto significa que los elementos del conjunto de controles donde la etiqueta es relevante para el revisor y se predicen como relevantes para el modelo. El intervalo de puntuaciones de esta métrica va de **0** a **1**. Una puntuación más cercana a **1** indica que el modelo identificará menos elementos no relevantes. La métrica de precisión se muestra en el panel del modelo y en la página flotante de cada ronda de aprendizaje.

## <a name="prediction-score"></a>Puntuación de predicción

Esta es la puntuación que un modelo asigna a cada documento de un conjunto de revisión. La puntuación se basa en la relevancia del documento en comparación con el aprendizaje del modelo de las rondas de aprendizaje. En general, los elementos con puntuaciones de predicción entre **0** y **0,5** se consideran no relevantes y los elementos con puntuaciones de predicción entre **0,5** y **1** se consideran relevantes. La puntuación de predicción se encuentra en un campo de metadatos de documento. Puede usar un filtro de predicción para mostrar los elementos de un conjunto de revisión que se encuentran dentro de un intervalo de predicción especificado.

## <a name="recall"></a>Recuperación

La métrica de recuperación mide la proporción de elementos que predijo que el modelo era relevante entre los elementos que son realmente relevantes. Esto significa que los elementos del conjunto de controles que el modelo pronosticado eran relevantes también se etiquetaron como relevantes para el revisor. El intervalo de puntuaciones de esta métrica va de **0** a **1**. Una puntuación más cercana a **1** indica que el modelo identificará una parte mayor de los elementos relevantes. La métrica de recuperación se muestra en el panel del modelo y en la página desplegable de cada ronda de aprendizaje.

## <a name="review-set"></a>Conjunto de revisión:

Un conjunto de revisión proporciona el ámbito de un modelo de codificación predictiva. Al crear un nuevo modelo para el conjunto de revisión, los elementos del conjunto de controles y los conjuntos de aprendizaje se seleccionan del conjunto de revisión. Cuando el modelo asigna puntuaciones de predicción, asigna a esas puntuaciones los elementos de la revisión. Debe agregar todos los elementos al conjunto de revisión antes de crear un modelo de codificación predictiva. Si agrega elementos después de crear un modelo, no se asignará una puntuación de predicción a esos elementos.

## <a name="richness"></a>Riqueza

La métrica de riqueza mide el porcentaje de elementos del conjunto de revisión que el modelo predice como relevantes. El intervalo de puntuaciones de esta métrica va de **0** a **1**. La métrica de riqueza se muestra en el panel del modelo.

## <a name="sampled-items"></a>Elementos muestreados

El término *elementos* muestreados es una referencia a una muestra aleatoria de elementos de un conjunto de revisión (que contienen texto) que se seleccionan y se asocian con el conjunto de controles al crear un modelo de codificación predictiva. También se selecciona una muestra aleatoria de elementos para cada ronda de aprendizaje. Los elementos seleccionados para el conjunto de controles de un modelo nunca se incluyen en un conjunto de aprendizaje para ese mismo modelo. Lo contrario también es cierto: los elementos del conjunto de aprendizaje nunca se incluyen en el conjunto de controles.

## <a name="training-set"></a>Conjunto de aprendizaje

El modelo selecciona aleatoriamente los elementos del conjunto de revisión y los agrega a un conjunto de aprendizaje. Durante una ronda de aprendizaje, se presentan los elementos del conjunto de aprendizaje (además de los elementos del conjunto de control) para que pueda etiquetar cada uno como "relevante" o "no relevante". Este proceso de etiquetado o "aprendizaje" ayuda al modelo a aprender a predecir qué elementos de la revisión son relevantes o no relevantes. Cada vez que realiza una ronda de aprendizaje, el modelo selecciona más elementos de la revisión y los agrega al conjunto de aprendizaje para esa ronda de aprendizaje. Los elementos del conjunto de controles nunca se seleccionan para un conjunto de aprendizaje.
