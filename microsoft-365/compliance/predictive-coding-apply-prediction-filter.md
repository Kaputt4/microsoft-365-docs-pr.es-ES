---
title: Aplicación del filtro de puntuación de predicción a un conjunto de revisión
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
description: Use un filtro de puntuación de predicción para mostrar los elementos que un modelo de codificación predictiva predijo como pertinentes o no pertinentes.
ms.openlocfilehash: 64abac8b9f53baa9afb869d77296089544919fea
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096620"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>Aplicar un filtro de puntuación de predicción a un conjunto de revisión (versión preliminar)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Después de crear un modelo de codificación predictiva en Microsoft Purview eDiscovery (Premium) y entrenarlo hasta el punto en que sea estable, puede aplicar el filtro de puntuación de predicción para mostrar los elementos de conjunto de revisión que el modelo ha determinado son pertinentes (o no pertinentes). Al crear un modelo, también se crea un filtro de puntuación de predicción correspondiente. Puede usar este filtro para mostrar los elementos asignados a una puntuación de predicción dentro de un intervalo especificado. En general, las puntuaciones de predicción entre **0** y **.5** se asignan a elementos que el modelo ha predicho no son pertinentes. Las puntuaciones de predicción asignadas a elementos entre **.5** y **1.0** son elementos que el modelo ha predicho que son pertinentes.

Estas son dos maneras de usar el filtro de puntuación de predicción:

- Priorice la revisión de los elementos de un conjunto de revisión que el modelo ha predicho que son pertinentes.

- Los elementos del conjunto de revisión que el modelo ha predicho no son pertinentes. Como alternativa, puede usar el filtro de puntuación de predicción para anular la prioridad de la revisión de elementos no relevantes.

## <a name="before-you-apply-a-prediction-score-filter"></a>Antes de aplicar un filtro de puntuación de predicción

- Cree un modelo de codificación predictiva para que se cree un filtro de puntuación de predicción correspondiente.

- Puede aplicar un filtro de puntuación de predicción después de cualquiera de las rondas de entrenamiento. Pero es posible que desee esperar después de realizar varias rondas o hasta que el modelo sea estable antes de usar el filtro de puntuación de predicción.

## <a name="apply-a-prediction-score-filter"></a>Aplicación de un filtro de puntuación de predicción

1. En el portal de cumplimiento de Microsoft Purview, abra el caso de eDiscovery (Premium), seleccione la pestaña **Conjuntos de revisión** y, a continuación, abra el conjunto de revisiones.

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

  > [!TIP]
  > Para ver la puntuación de predicción real que se asigna a un documento, puede hacer clic en la pestaña **Metadatos** del panel de lectura. Las puntuaciones de predicción de todos los modelos del conjunto de revisión se muestran en la propiedad de **metadatos RelevanceScores** .

## <a name="more-information"></a>Más información

- Para obtener más información sobre el uso de filtros, consulte [Consulta y filtrado de contenido en un conjunto de revisión](review-set-search.md).
