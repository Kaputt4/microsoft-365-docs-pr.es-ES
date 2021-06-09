---
title: 'Codificación predictiva en Advanced eDiscovery: inicio rápido'
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
description: Obtenga información sobre cómo empezar a usar el módulo de codificación predictiva en Advanced eDiscovery. Este artículo le guiará por el proceso completo de usar la codificación predictiva para identificar el contenido de un conjunto de revisión que sea más relevante para la investigación.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822624"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>Inicio rápido: codificación predictiva en Advanced eDiscovery (versión preliminar)

En este artículo se presenta un inicio rápido para usar la codificación predictiva en Advanced eDiscovery. El módulo de codificación predictiva de Advanced eDiscovery usa las capacidades inteligentes de aprendizaje automático en Advanced eDiscovery para ayudarle a reducir la cantidad de contenido que se va a revisar. La codificación predictiva le ayuda a reducir y asignar grandes volúmenes de contenido de caso a un conjunto relevante de elementos que puede priorizar para su revisión. Para ello, cree y entrena sus propios modelos de codificación predictiva que le ayudarán a priorizar la revisión de los elementos más relevantes de un conjunto de revisión.

Este es un resumen rápido del proceso de codificación predictiva:

![Proceso de inicio rápido para codificación de predicción](..\media\PredictiveCodingQuickStartProcess.png)

Para empezar, cree un modelo, etiquete como pocos 50 elementos como relevantes o no relevantes. A continuación, el sistema usa este aprendizaje para aplicar puntuaciones de predicción a todos los elementos del conjunto de revisión. Esto le permite filtrar elementos en función de la puntuación de predicción, lo que le permite revisar primero los elementos más relevantes (o no relevantes). Si desea entrenar modelos con tasas de recuperación y acutracaciones más altas, puede seguir etiquetando elementos en rondas de aprendizaje posteriores hasta que el modelo se estabilice. Una vez estabilizado el modelo, puede aplicar el filtro de predicción final para priorizar los elementos que se deben revisar.

Para obtener una introducción detallada a la codificación predictiva, vea [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).

## <a name="step-1-create-a-new-predictive-coding-model"></a>Paso 1: Crear un nuevo modelo de codificación predictiva

El primer paso es crear un nuevo modelo de codificación predictiva en el conjunto de revisión

1. En el centro Microsoft 365 cumplimiento, abra un Advanced eDiscovery caso y, a continuación, seleccione la **pestaña Conjuntos de** revisión.

2. Abra un conjunto de opiniones y, a continuación, haga clic **en Analytics Administrar**  >  **codificación predictiva (versión preliminar).**

   ![Haga clic en el menú desplegable Analizar en el conjunto de revisión para ir a la página Codificación predictiva](..\media\ManagePredictiveCoding.png)

3. En la **página Modelos de codificación predictiva (versión preliminar),** haga clic **en Nuevo modelo**.

4. En la página desplegable, escriba un nombre para el modelo y una descripción opcional.

5. Haga **clic en** Guardar para crear el modelo.

   El sistema tardaría un par de minutos en preparar el modelo. Después de que esté listo, puedes realizar la primera ronda de aprendizaje.

Para obtener instrucciones más detalladas, vea [Create a predictive coding model](predictive-coding-create-model.md).

## <a name="step-2-perform-the-first-training-round"></a>Paso 2: Realizar la primera ronda de entrenamiento

Después de crear el modelo, el siguiente paso es completar la primera ronda de aprendizaje etiquetando los elementos como relevantes o no relevantes.

1. Abra el conjunto de opiniones y, a continuación, haga clic **en Analytics**  >  **Administrar codificación predictiva (versión preliminar).**

2. En la **página Modelos de codificación predictiva (versión** preliminar), seleccione el modelo que desea entrenar.

3. En la **pestaña Información** general, en **Ronda 1,** haga clic **en Iniciar siguiente ronda de aprendizaje.**

   Se **muestra la** pestaña Aprendizaje y contiene 50 elementos para etiquetar.

4. Revise cada documento y, a continuación, **seleccione** el botón Relevante o No **relevante** en la parte inferior del panel de lectura para etiquetar.

   ![Etiquetar cada documento como relevante o no relevante](..\media\TrainModel1.png)

5. Después de etiquetar los 50 elementos, haga clic en **Finalizar**.

    El sistema tardaría un par de minutos en "aprender" del etiquetado y actualizar el modelo. Una vez completado este proceso, se muestra el estado **Listo** para el modelo en la página Modelos de codificación **predictiva (versión** preliminar).

Para obtener instrucciones más detalladas, vea [Train a predictive coding model](predictive-coding-train-model.md).

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>Paso 3: Aplicar el filtro de puntuación de predicción a los elementos del conjunto de revisión

Después de realizar la concesión de una ronda de aprendizaje, puede aplicar el filtro de puntuación de predicción a los elementos del conjunto de revisión. Esto le permite revisar los elementos que el modelo ha predicho como relevantes o no relevantes.   

1. Abra el conjunto de revisión.

   ![Haga clic en Filtros para mostrar la página desplegable Filtros](..\media\PredictionScoreFilter0.png)

   Los filtros predeterminados precargados se muestran en la parte superior de la página del conjunto de revisión. Puede dejar estos establecidos en **Any**.

2. Haga **clic en** Filtros para mostrar la **página** desplegable Filtros.

3. Expanda la **sección & de codificación predictiva** de Analytics para mostrar un conjunto de filtros.

      ![Filtro de puntuación de predicción en la sección & codificación predictiva de Analytics](..\media\PredictionScoreFilter1.png)

   La convención de nomenclatura para los filtros de puntuación de predicción es **Puntuación de predicción (nombre del modelo).** Por ejemplo, el nombre del filtro de puntuación de predicción de un modelo denominado **Modelo A** es **Puntuación de predicción (modelo A).**

4. Seleccione el filtro de puntuación de predicción que desea usar y, a continuación, haga clic **en Listo**.

5. En la página conjunto de revisión, haga clic en el desplegable del filtro de puntuación de predicción y escriba los valores mínimos y máximos para el intervalo de puntuación de predicción. Por ejemplo, la siguiente captura de pantalla muestra un intervalo de puntuación de predicción entre **.5** y **1,0**.

   ![Valores mínimos y máximos para el filtro de puntuación de predicción](..\media\PredictionScoreFilter2.png)

6. Haga clic fuera del filtro para aplicar automáticamente el filtro al conjunto de revisión.

  Se muestra una lista de documentos con una puntuación de predicción dentro del intervalo especificado en la página del conjunto de revisión.

Para obtener instrucciones más detalladas, vea [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).

## <a name="step-4-perform-more-training-rounds"></a>Paso 4: Realizar más rondas de aprendizaje

Lo más probable es que tenga que realizar más rondas de aprendizaje para entrenar al módulo para predecir mejor los elementos relevantes y no relevantes del conjunto de revisión. En general, entrenarás el modelo suficientes veces hasta que se estabilice lo suficiente como para satisfacer tus requisitos.

Para obtener más información, vea [Realizar rondas de aprendizaje adicionales](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>Paso 5: Aplicar el filtro de puntuación de predicción final para priorizar la revisión

Repita las instrucciones del paso 3 para aplicar la puntuación de predicción final al conjunto de revisión para priorizar la revisión de elementos relevantes y no relevantes después de completar todas las rondas de aprendizaje y estabilizar el modelo.
