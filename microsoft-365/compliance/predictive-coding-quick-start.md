---
title: 'Codificación predictiva en eDiscovery (Premium): inicio rápido'
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
description: Obtenga información sobre cómo empezar a usar el módulo de codificación predictiva en eDiscovery (Premium). Este artículo le guiará por el proceso de un extremo a otro de usar la codificación predictiva para identificar el contenido de un conjunto de revisión que es más relevante para la investigación.
ms.openlocfilehash: ddf1762545765424891108f50cceea17999f0920
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625091"
---
# <a name="quick-start-predictive-coding-in-ediscovery-premium-preview"></a>Inicio rápido: Codificación predictiva en eDiscovery (Premium) (versión preliminar)

En este artículo se presenta un inicio rápido para usar la codificación predictiva en Microsoft Purview eDiscovery (Premium). El módulo de codificación predictiva usa funcionalidades inteligentes de aprendizaje automático para ayudarle a eliminar grandes volúmenes de contenido de casos que no son relevantes para la investigación. Esto se logra mediante la creación y el entrenamiento de sus propios modelos de codificación predictiva que le ayudan a priorizar los elementos más relevantes para su revisión.

Esta es una introducción rápida al proceso de codificación predictiva:

![Proceso de inicio rápido para la codificación de predicción.](..\media\PredictiveCodingQuickStartProcess.png)

Para empezar, cree un modelo, etiquete tan solo 50 elementos como pertinentes o no pertinentes. A continuación, el sistema usa este entrenamiento para aplicar puntuaciones de predicción a cada elemento del conjunto de revisión. Esto le permite filtrar los elementos en función de la puntuación de predicción, lo que le permite revisar primero los elementos más relevantes (o no relevantes). Si desea entrenar modelos con mayores precisiónes y tasas de recuperación, puede seguir etiquetando elementos en rondas de entrenamiento posteriores hasta que el modelo se estabilice. Una vez estabilizado el modelo, puede aplicar el filtro de predicción final para priorizar los elementos que se van a revisar.

Para obtener información general detallada sobre la codificación predictiva, consulte [Información sobre la codificación predictiva en eDiscovery (Premium).](predictive-coding-overview.md)

## <a name="step-1-create-a-new-predictive-coding-model"></a>Paso 1: Crear un nuevo modelo de codificación predictiva

El primer paso consiste en crear un nuevo modelo de codificación predictiva en el conjunto de revisión.

1. En el portal de cumplimiento Microsoft Purview, abra un caso de exhibición de documentos electrónicos (Premium) y, a continuación, seleccione la pestaña **Conjuntos de revisión**.

2. Abra un conjunto de revisión y, a continuación, haga clic en **Análisis** > **Administrar codificación predictiva (versión preliminar).**

   ![Haga clic en el menú desplegable Analizar del conjunto de revisión para ir a la página Codificación predictiva.](..\media\ManagePredictiveCoding.png)

3. En la página **Modelos de codificación predictiva (versión preliminar),** haga clic en **Nuevo modelo**.

4. En la página de control flotante, escriba un nombre para el modelo y una descripción opcional.

5. Haga clic en **Guardar** para crear el modelo.

   El sistema tardará un par de minutos en preparar el modelo. Una vez listo, puede realizar la primera ronda de entrenamiento.

Para obtener instrucciones más detalladas, consulte [Creación de un modelo de codificación predictiva](predictive-coding-create-model.md).

## <a name="step-2-perform-the-first-training-round"></a>Paso 2: Realizar la primera ronda de entrenamiento

Después de crear el modelo, el siguiente paso es completar la primera ronda de entrenamiento etiquetando los elementos como pertinentes o no pertinentes.

1. Abra el conjunto de revisión y, a continuación, haga clic en **Análisis** > **Administrar codificación predictiva (versión preliminar).**

2. En la página **Modelos de codificación predictiva (versión preliminar),** seleccione el modelo que desea entrenar.

3. En la pestaña **Información general** , en **Ronda 1**, haga clic en **Iniciar siguiente ronda de entrenamiento**.

   Se muestra la pestaña **Entrenamiento** y contiene 50 elementos para etiquetar.

4. Revise cada documento y, a continuación, seleccione el botón **Pertinente** o **No relevante** en la parte inferior del panel de lectura para etiquetarlo.

   ![Etiquete cada documento como pertinente o no relevante.](..\media\TrainModel1.png)

5. Después de etiquetar los 50 elementos, haga clic en **Finalizar**.

    El sistema tardará un par de minutos en "aprender" del etiquetado y actualizar el modelo. Una vez completado este proceso, se muestra un estado **Listo** para el modelo en la página **Modelos de codificación predictiva (versión preliminar).**

Para obtener instrucciones más detalladas, consulte [Entrenamiento de un modelo de codificación predictiva](predictive-coding-train-model.md).

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>Paso 3: Aplicar el filtro de puntuación de predicción a los elementos del conjunto de revisión

Después de realizar durante la concesión una ronda de entrenamiento, puede aplicar el filtro de puntuación de predicción a los elementos del conjunto de revisión. Esto le permite revisar los elementos que el modelo ha predicho como pertinentes o no pertinentes.   

1. Abra el conjunto de revisión.

   ![Haga clic en Filtros para mostrar la página desplegable Filtros.](..\media\PredictionScoreFilter0.png)

   Los filtros predeterminados cargados previamente se muestran en la parte superior de la página del conjunto de revisiones. Puede dejar estos valores establecidos en **Cualquiera**.

2. Haga clic en **Filtros** para mostrar la página desplegable **Filtros** .

3. Expanda la sección **Análisis & codificación predictiva** para mostrar un conjunto de filtros.

      ![Filtro de puntuación de predicción en la sección De analytics & codificación predictiva.](..\media\PredictionScoreFilter1.png)

   La convención de nomenclatura para los filtros de puntuación de predicción es **Puntuación de predicción (nombre del modelo).** Por ejemplo, el nombre del filtro de puntuación de predicción para un modelo denominado **Modelo A** es **Puntuación de predicción (modelo A).**

4. Seleccione el filtro de puntuación de predicción que desea usar y, a continuación, haga clic en **Listo**.

5. En la página conjunto de revisión, haga clic en la lista desplegable del filtro de puntuación de predicción y escriba los valores mínimo y máximo para el intervalo de puntuación de predicción. Por ejemplo, en la captura de pantalla siguiente se muestra un intervalo de puntuación de predicción entre **.5** y **1.0**.

   ![Valores mínimos y máximos para el filtro de puntuación de predicción.](..\media\PredictionScoreFilter2.png)

6. Haga clic fuera del filtro para aplicar automáticamente el filtro al conjunto de revisión.

  En la página del conjunto de revisiones se muestra una lista de documentos con una puntuación de predicción dentro del intervalo especificado.

Para obtener instrucciones más detalladas, vea [Aplicar un filtro de predicción a un conjunto de revisión](predictive-coding-apply-prediction-filter.md).

## <a name="step-4-perform-more-training-rounds"></a>Paso 4: Realizar más rondas de entrenamiento

Lo más probable es que tenga que realizar más rondas de entrenamiento para entrenar el módulo con el fin de predecir mejor los elementos pertinentes y no pertinentes del conjunto de revisión. En general, entrenará el modelo los tiempos suficientes hasta que se estabilice lo suficiente para satisfacer sus requisitos.

Para obtener más información, vea [Realizar rondas de entrenamiento adicionales](predictive-coding-train-model.md#perform-additional-training-rounds).

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>Paso 5: Aplicar el filtro de puntuación de predicción final para priorizar la revisión

Repita las instrucciones del paso 3 para aplicar la puntuación de predicción final al conjunto de revisión para priorizar la revisión de elementos pertinentes y no relevantes después de completar todas las rondas de entrenamiento y estabilizar el modelo.
