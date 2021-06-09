---
title: Entrenar un modelo de codificación predictiva en Advanced eDiscovery
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
ms.openlocfilehash: ef6d1cf23d6cca58f4226696bc63c1dea5816cc1
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822616"
---
# <a name="train-a-predictive-coding-model-preview"></a>Entrenar un modelo de codificación predictiva (versión preliminar)

Después de crear un modelo de codificación predictiva en Advanced eDiscovery, el siguiente paso es realizar la primera ronda de aprendizaje para entrenar el modelo sobre lo que es relevante y contenido no relevante en el conjunto de revisión. Después de completar la primera ronda de aprendizaje, puedes realizar rondas de aprendizaje posteriores para mejorar la capacidad del modelo para predecir contenido relevante y no relevante.

Para revisar el flujo de trabajo de codificación predictiva, vea [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-train-a-model"></a>Antes de entrenar un modelo

- Durante una ronda de aprendizaje, etiquete los elementos como **Relevantes** o **No** relevantes en función de la relevancia del contenido del documento. No base su decisión en los valores de los campos de metadatos. Por ejemplo, para los mensajes de correo electrónico Teams conversaciones, no base la decisión de etiquetado en los participantes del mensaje. 

## <a name="train-a-model-for-the-first-time"></a>Entrenar un modelo por primera vez

1. En el centro Microsoft 365 cumplimiento, abra un Advanced eDiscovery caso y, a continuación, seleccione la **pestaña Conjuntos de** revisión.

2. Abra un conjunto de opiniones y, a continuación, haga clic **en Analytics Administrar**  >  **codificación predictiva (versión preliminar).**

3. En la **página Modelos de codificación predictiva (versión** preliminar), seleccione el modelo que desea entrenar.

4. En la **pestaña Información** general, en **Ronda 1,** haga clic **en Iniciar siguiente ronda de aprendizaje.**

   Se **muestra la** pestaña Aprendizaje y contiene 50 elementos para etiquetar.

5. Revise cada documento y, a continuación, **seleccione** el botón Relevante o No **relevante** en la parte inferior del panel de lectura para etiquetar.

   ![Etiquetar cada documento como relevante o no relevante](..\media\TrainModel1.png)

6. Después de etiquetar los 50 elementos, haga clic en **Finalizar**.

    El sistema tardaría un par de minutos en "aprender" del etiquetado y actualizar el modelo. Una vez completado este proceso, se muestra el estado **Listo** para el modelo en la página Modelos de codificación **predictiva (versión** preliminar).

## <a name="perform-additional-training-rounds"></a>Realizar rondas de aprendizaje adicionales

Después de realizar la primera ronda de aprendizaje, puede realizar rondas de aprendizaje posteriores siguiendo los pasos de la sección anterior. La única diferencia es que el número de la ronda de aprendizaje se actualizará en la pestaña Información **general del** modelo. Por ejemplo, después de realizar la primera ronda de entrenamiento, puedes hacer clic en **Iniciar** la siguiente ronda de entrenamiento para iniciar la segunda ronda de entrenamiento. Y así sucesivamente.

Cada ronda de aprendizaje (tanto las que están en curso  como las que están completas) se muestran en la pestaña Aprendizaje del modelo. Al seleccionar una ronda de aprendizaje, se muestra una página desplegable con información y métricas para la ronda.

## <a name="what-happens-after-you-perform-a-training-round"></a>Qué sucede después de realizar una ronda de entrenamiento

Después de realizar la primera ronda de aprendizaje, se inicia un trabajo que hace lo siguiente:

- En función de cómo etiquetaste los 40 elementos del conjunto de aprendizaje, el modelo aprende del etiquetado y se actualiza para ser más preciso.

- A continuación, el modelo procesa cada elemento de todo el conjunto de revisión y asigna una puntuación de predicción entre **0** (no relevante) y **1** (relevante).  

- El modelo asigna una puntuación de predicción a los 10 elementos del conjunto de controles etiquetados durante la ronda de entrenamiento. El modelo compara la puntuación de predicción de estos 10 elementos con la etiqueta real que asignó al elemento durante la ronda de entrenamiento. Basándose en esta comparación, el modelo identifica la siguiente clasificación (denominada matriz de confusión del conjunto de *controles)* para evaluar el rendimiento de predicción del modelo:
  
  |          |El modelo predice que el elemento es relevante |El modelo predice que el elemento no es relevante |
  |:---------|:---------|:---------|
  |**Elemento de etiquetas de revisor como relevante**| Verdadero positivo| Falso positivo |
  |**Elemento de etiquetas de revisor como no relevante**| Falso negativo |True negativo |
  ||||

  Basándose en estas comparaciones, el modelo deriva valores para las métricas de puntuación F, precisión y recuperación y el margen de error de cada una de ellas. Las puntuaciones de estas métricas de rendimiento del modelo se muestran en una página desplegable de la ronda de aprendizaje. Para obtener una descripción de estas métricas, vea [Referencia de codificación predictiva.](predictive-coding-reference.md)

- Por último, el modelo determina los siguientes 50 elementos que se usarán para la siguiente ronda de aprendizaje. Esta vez, el modelo puede seleccionar 20 elementos del conjunto de controles y 30 elementos nuevos del conjunto de revisión y designarlos como el conjunto de aprendizaje para la siguiente ronda. El muestreo de la siguiente ronda de entrenamiento no se muestra uniformemente. El modelo optimizará la selección de muestreo de elementos del conjunto de revisión para seleccionar elementos donde la predicción es ambigua, lo que significa que la puntuación de predicción está en el intervalo 0,5. Este proceso se conoce como *selección sesgada*.

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>Qué sucede después de realizar rondas de aprendizaje posteriores

Después de realizar rondas de aprendizaje posteriores (después de la primera ronda de aprendizaje), el modelo hace lo siguiente:

- El modelo se actualiza en función de las etiquetas que aplicó al conjunto de aprendizaje en esa ronda de aprendizaje.

- El sistema evalúa la puntuación de predicción del modelo en los elementos del conjunto de controles y comprueba si la puntuación se alinea con la forma en que se etiquetan los elementos del conjunto de controles. La evaluación se realiza en todos los elementos etiquetados del conjunto de controles para todas las rondas de aprendizaje. Los resultados de esta evaluación se incorporan en el panel de **la** pestaña Información general del modelo.

- El modelo actualizado vuelve a procesar todos los elementos del conjunto de revisión y asigna a cada elemento una puntuación de predicción actualizada.

## <a name="next-steps"></a>Pasos siguientes

Después de realizar la primera ronda de aprendizaje, puede realizar más rondas de aprendizaje o aplicar el filtro de puntuación de predicción del modelo al conjunto de revisión para ver los elementos que el modelo ha predicho como relevantes o no relevantes. Para obtener más información, vea [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).
