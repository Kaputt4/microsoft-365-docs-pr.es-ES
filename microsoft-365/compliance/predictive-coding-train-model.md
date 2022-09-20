---
title: Entrenamiento de un modelo de codificación predictiva en eDiscovery (Premium)
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
description: Obtenga información sobre cómo realizar la primera ronda de entrenamiento para la codificación predictiva.
ms.openlocfilehash: a08113a953e4e9a9df47cca7724122cb27007e2b
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67825376"
---
# <a name="train-a-predictive-coding-model-preview"></a>Entrenamiento de un modelo de codificación predictiva (versión preliminar)

Después de crear un modelo de codificación predictiva en Microsoft Purview eDiscovery (Premium), el siguiente paso consiste en realizar la primera ronda de entrenamiento para entrenar el modelo sobre el contenido relevante y no relevante del conjunto de revisión. Después de completar la primera ronda de entrenamiento, puede realizar rondas de entrenamiento posteriores para mejorar la capacidad del modelo de predecir contenido relevante y no relevante.

Para revisar el flujo de trabajo de codificación predictiva, consulte [Información sobre la codificación predictiva en eDiscovery (Premium)](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-train-a-model"></a>Antes de entrenar un modelo

- Durante una ronda de entrenamiento, etiquete los elementos como **Pertinentes** o **No pertinentes** en función de la relevancia del contenido del documento. No base su decisión en los valores de los campos de metadatos. Por ejemplo, para mensajes de correo electrónico o conversaciones de Teams, no base la decisión de etiquetado en los participantes del mensaje.

## <a name="train-a-model-for-the-first-time"></a>Entrenamiento de un modelo por primera vez

1. En el portal de cumplimiento Microsoft Purview, abra un caso de exhibición de documentos electrónicos (Premium) y, a continuación, seleccione la pestaña **Conjuntos de revisión**.

2. Abra un conjunto de revisión y, a continuación, haga clic en **Análisis** > **Administrar codificación predictiva (versión preliminar).**

3. En la página **Modelos de codificación predictiva (versión preliminar),** seleccione el modelo que desea entrenar.

4. En la pestaña **Información general** , en **Ronda 1**, haga clic en **Iniciar siguiente ronda de entrenamiento**.

   Se muestra la pestaña **Entrenamiento** y contiene 50 elementos para etiquetar.

5. Revise cada documento y, a continuación, seleccione el botón **Pertinente** o **No relevante** en la parte inferior del panel de lectura para etiquetarlo.

   ![Etiquete cada documento como pertinente o no relevante.](..\media\TrainModel1.png)

6. Después de etiquetar los 50 elementos, haga clic en **Finalizar**.

    El sistema tardará un par de minutos en "aprender" del etiquetado y actualizar el modelo. Una vez completado este proceso, se muestra un estado **Listo** para el modelo en la página **Modelos de codificación predictiva (versión preliminar).**

## <a name="perform-additional-training-rounds"></a>Realizar rondas de entrenamiento adicionales

Después de realizar la primera ronda de entrenamiento, puede realizar rondas de entrenamiento posteriores siguiendo los pasos de la sección anterior. La única diferencia es que el número de la ronda de entrenamiento se actualizará en la pestaña **Información general** del modelo. Por ejemplo, después de realizar la primera ronda de entrenamiento, puede hacer clic en **Iniciar siguiente ronda de entrenamiento** para iniciar la segunda ronda de entrenamiento. Y así sucesivamente.

Cada ronda de entrenamiento (tanto las que están en curso como las completadas) se muestra en la pestaña **Entrenamiento** del modelo. Al seleccionar una ronda de entrenamiento, se muestra una página de control flotante con información y métricas para la ronda.

## <a name="what-happens-after-you-perform-a-training-round"></a>¿Qué ocurre después de realizar una ronda de entrenamiento?

Después de realizar la primera ronda de entrenamiento, se inicia un trabajo que hace lo siguiente:

- En función de cómo ha etiquetado los 40 elementos del conjunto de entrenamiento, el modelo aprende de su etiquetado y se actualiza a sí mismo para que sea más preciso.

- A continuación, el modelo procesa cada elemento de todo el conjunto de revisión y asigna una puntuación de predicción entre **0** (no relevante) y **1** (relevante).

- El modelo asigna una puntuación de predicción a los 10 elementos del conjunto de controles que ha etiquetado durante la ronda de entrenamiento. El modelo compara la puntuación de predicción de estos 10 elementos con la etiqueta real que asignó al elemento durante la ronda de entrenamiento. En función de esta comparación, el modelo identifica la siguiente clasificación (denominada *matriz de confusión del conjunto de control*) para evaluar el rendimiento de predicción del modelo:

  <br>

  ****

  |Etiqueta|El modelo predice que el elemento es relevante|El modelo predice que el elemento no es relevante|
  |---|---|---|
  |**Elemento de etiquetas de revisor según corresponda**|Verdadero positivo|Falso positivo|
  |**El elemento de etiquetas del revisor no es relevante**|Falso negativo|Verdadero negativo|
  |

  En función de estas comparaciones, el modelo deriva valores para las métricas de puntuación F, precisión y recuperación y el margen de error de cada una de ellas. Las puntuaciones de estas métricas de rendimiento del modelo se muestran en una página flotante para la ronda de entrenamiento. Para obtener una descripción de estas métricas, consulte [Referencia de codificación predictiva](predictive-coding-reference.md).

- Por último, el modelo determina los siguientes 50 elementos que se usarán para la siguiente ronda de entrenamiento. Esta vez, el modelo podría seleccionar 20 elementos del conjunto de control y 30 nuevos elementos del conjunto de revisión y designarlos como el conjunto de entrenamiento para la siguiente ronda. El muestreo de la siguiente ronda de entrenamiento no se muestrea uniformemente. El modelo optimizará la selección de muestreo de elementos del conjunto de revisión para seleccionar los elementos donde la predicción es ambigua, lo que significa que la puntuación de predicción está en el intervalo 0,5. Este proceso se conoce como *selección sesgada*.

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>¿Qué ocurre después de realizar rondas de entrenamiento posteriores?

Después de realizar rondas de entrenamiento posteriores (después de la primera ronda de entrenamiento), el modelo hace lo siguiente:

- El modelo se actualiza en función de las etiquetas que aplicó al conjunto de entrenamiento en esa ronda de entrenamiento.

- El sistema evalúa la puntuación de predicción del modelo en los elementos del conjunto de controles y comprueba si la puntuación se alinea con la forma en que etiquetaste los elementos del conjunto de controles. La evaluación se realiza en todos los elementos etiquetados del conjunto de control para todas las rondas de entrenamiento. Los resultados de esta evaluación se incorporan en el panel de la pestaña **Información general** del modelo.

- El modelo actualizado vuelve a procesar todos los elementos del conjunto de revisión y asigna a cada elemento una puntuación de predicción actualizada.

## <a name="next-steps"></a>Pasos siguientes

Después de realizar la primera ronda de entrenamiento, puede realizar más rondas de entrenamiento o aplicar el filtro de puntuación de predicción del modelo al conjunto de revisión para ver los elementos que el modelo ha predicho como pertinentes o no pertinentes. Para obtener más información, vea [Aplicar un filtro de puntuación de predicción a un conjunto de revisión](predictive-coding-apply-prediction-filter.md).
