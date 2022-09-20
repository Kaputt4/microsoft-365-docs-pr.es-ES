---
title: Referencia de codificación predictiva
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Obtenga información sobre los conceptos clave y las métricas de la herramienta de codificación predictiva en Microsoft Purview eDiscovery (Premium).
ms.openlocfilehash: 6e49999cca5cbbff1f829997dbb1ef2201bc49cb
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67822559"
---
# <a name="predictive-coding-reference-preview"></a>Referencia de codificación predictiva (versión preliminar)

En este artículo se describen los conceptos clave y las métricas de la herramienta de codificación predictiva en Microsoft Purview eDiscovery (Premium). Las secciones del artículo se enumeran en orden alfabético.

## <a name="confidence-level"></a>Nivel de confianza

El nivel de confianza es una configuración avanzada al crear un modelo de codificación predictiva. Define que las métricas de rendimiento del modelo (por ejemplo, riqueza, precisión y recuperación) se encuentran dentro de un intervalo especificado (que determina el margen de error definido para el modelo) que es representativo de los valores verdaderos de las puntuaciones de predicción que el modelo asigna a los elementos del conjunto de revisión. Los valores del nivel de confianza y el margen de error también ayudan a determinar cuántos elementos se incluyen en el conjunto de controles. El valor predeterminado para el nivel de confianza es 0,95 o 95 %.

## <a name="control-set"></a>Conjunto de controles

Un conjunto de controles se usa durante el proceso de entrenamiento de un modelo de codificación predictiva. El conjunto de controles consiste en evaluar las puntuaciones de predicción que el modelo asigna a los elementos con el etiquetado que se realiza durante las rondas de entrenamiento. El tamaño del conjunto de controles se basa en el número de elementos del conjunto de revisión y en el nivel de confianza y el margen de los valores de error que se establecen al crear el modelo. Los elementos del conjunto de controles nunca cambian y no son identificables para los usuarios. El número total de elementos del conjunto de controles se muestra en la página de control flotante de una ronda de entrenamiento.

## <a name="control-set-confusion-matrix"></a>Matriz de confusión del conjunto de controles

Después de completar una ronda de entrenamiento, el modelo asigna una puntuación de predicción a los 10 elementos del conjunto de controles etiquetados durante la ronda de entrenamiento. El modelo compara la puntuación de predicción de estos 10 elementos con la etiqueta real que asignó al elemento durante la ronda de entrenamiento. En función de esta comparación, el modelo identifica las siguientes clasificaciones para evaluar el rendimiento de predicción del modelo:

<br>

****

|Etiqueta|El modelo predice que el elemento es relevante|El modelo predice que el elemento no es relevante|
|---|---|---|
|**Elemento de etiquetas de revisor según corresponda**|Verdadero positivo|Falso positivo|
|**El elemento de etiquetas del revisor no es relevante**|Falso negativo|Verdadero negativo|
|

En función de estas comparaciones, el modelo deriva valores para las métricas de puntuación F, precisión y recuperación y el margen de error de cada una de ellas. El número de cada uno de los tipos de confusión de la matriz se muestra en la página de control flotante de una ronda de entrenamiento.

## <a name="f-score"></a>Puntuación F

La puntuación F es un promedio ponderado de las puntuaciones para las métricas de precisión y recuperación.  El intervalo de puntuaciones de esta métrica es de **0** a **1**. Una puntuación más cercana a **1** indica que el modelo detectará con mayor precisión los elementos pertinentes. La métrica de puntuación F se muestra en el panel del modelo y en la página flotante de cada ronda de entrenamiento.

## <a name="margin-of-error"></a>Margen de error

El margen de error es una configuración avanzada al crear un modo de codificación predictiva. Especifica el grado de error en las métricas de rendimiento (por ejemplo, riqueza, precisión y recuperación) que se deriva del muestreo aleatorio de elementos del conjunto de control. Un margen de error inferior requiere un conjunto de control mayor para asegurarse de que las métricas de rendimiento del modelo se encuentran dentro de un intervalo más pequeño. Los valores del margen de error y el nivel de confianza también ayudan a determinar cuántos elementos se incluyen en el conjunto de controles. El valor predeterminado del margen de error es 0,05 o 5 %.

## <a name="model-stability"></a>Estabilidad del modelo

La estabilidad del modelo indica la capacidad del modelo para predecir con precisión si un documento de un conjunto de revisión es relevante o no. Cuando un modelo es inestable, es posible que sea necesario realizar más rondas de entrenamiento para incluir la estabilidad del modelo. Cuando el modelo es estable, es posible que no sea necesario realizar más rondas de entrenamiento. El panel del modelo indica el estado actual de la estabilidad del modelo. Cuando un modelo es estable, las métricas de rendimiento han alcanzado un nivel que coincide con la configuración del nivel de confianza y el margen de error.

## <a name="overturn-rate"></a>Velocidad de vuelco

La tasa de vuelco es el porcentaje de elementos del conjunto de revisión donde la puntuación de predicción cambió entre las rondas de entrenamiento. Un modelo se considera estable cuando la tasa de vuelco es inferior al 5 %. La métrica de velocidad de vuelco se muestra en el panel del modelo y en la página de control flotante de cada ronda de entrenamiento. La tasa de vuelco de la primera ronda de entrenamiento es cero porque no hay una puntuación de predicción anterior que revertir.

## <a name="precision"></a>Precisión

La métrica de precisión mide la proporción de elementos que son realmente pertinentes entre los elementos que el modelo predicho era relevante. Esto significa que los elementos del conjunto de controles donde el revisor etiqueta como pertinente y predichos como pertinentes por el modelo. El intervalo de puntuaciones de esta métrica es de **0** a **1**. Una puntuación más cercana a **1** indica que el modelo identificará menos elementos no relevantes. La métrica de precisión se muestra en el panel del modelo y en la página de control flotante de cada ronda de entrenamiento.

## <a name="prediction-score"></a>Puntuación de predicción

Esta es la puntuación que un modelo asigna a cada documento de un conjunto de revisión. La puntuación se basa en la relevancia del documento en comparación con el aprendizaje del modelo de las rondas de entrenamiento. En general, los elementos con puntuaciones de predicción entre **0** y **0,5** se consideran no pertinentes y los elementos con puntuaciones de predicción entre **0,5** y **1** se consideran pertinentes. La puntuación de predicción está contenida en un campo de metadatos del documento. Puede usar un filtro de predicción para mostrar los elementos de un conjunto de revisión que se encuentran dentro de un intervalo de predicción especificado.

## <a name="recall"></a>Recordar

La métrica de recuperación mide la proporción de elementos que el modelo predicho era relevante entre los elementos que son realmente pertinentes. Esto significa que los elementos del conjunto de control que predice el modelo eran pertinentes también se etiquetaron como pertinentes por el revisor. El intervalo de puntuaciones de esta métrica es de **0** a **1**. Una puntuación más cercana a **1** indica que el modelo identificará una parte mayor de los elementos pertinentes. La métrica de recuperación se muestra en el panel del modelo y en la página de control flotante de cada ronda de entrenamiento.

## <a name="review-set"></a>Conjunto de revisión:

Un conjunto de revisión proporciona el ámbito de un modelo de codificación predictiva. Al crear un nuevo modelo para el conjunto de revisión, los elementos del conjunto de control y los conjuntos de entrenamiento se seleccionan en el conjunto de revisión. Cuando el modelo asigna puntuaciones de predicción, asigna esas puntuaciones a los elementos de la revisión. Debe agregar todos los elementos al conjunto de revisión antes de crear un modelo de codificación predictiva. Si agrega elementos después de crear un modelo, a esos elementos no se les asignará una puntuación de predicción.

## <a name="richness"></a>Riqueza

La métrica de riqueza mide el porcentaje de elementos del conjunto de revisión que el modelo predice como pertinentes. El intervalo de puntuaciones de esta métrica es de **0** a **1**. La métrica de riqueza se muestra en el panel del modelo.

## <a name="sampled-items"></a>Elementos muestreados

El término *elementos muestreados* es una referencia a una muestra aleatoria de elementos de un conjunto de revisión (que contienen texto) seleccionados y asociados al conjunto de controles al crear un modelo de codificación predictiva. También se selecciona un ejemplo aleatorio de elementos para cada ronda de entrenamiento. Los elementos seleccionados para el conjunto de control de un modelo nunca se incluyen en un conjunto de entrenamiento para ese mismo modelo. Lo contrario también es cierto: los elementos del conjunto de entrenamiento nunca se incluyen en el conjunto de controles.

## <a name="training-set"></a>Conjunto de entrenamiento

El modelo selecciona aleatoriamente los elementos del conjunto de revisión y los agrega a un conjunto de entrenamiento. Durante una ronda de entrenamiento, se le presentan elementos del conjunto de entrenamiento (además de los elementos del conjunto de control) para que pueda etiquetar cada uno de ellos como "pertinente" o "no relevante". Este proceso de etiquetado o "entrenamiento" ayuda al modelo a aprender a predecir qué elementos de la revisión son pertinentes o no pertinentes. Cada vez que se realiza una ronda de entrenamiento, el modelo selecciona más elementos de la revisión y los agrega al conjunto de entrenamiento para esa ronda de entrenamiento. Los elementos del conjunto de controles nunca se seleccionan para un conjunto de entrenamiento.
