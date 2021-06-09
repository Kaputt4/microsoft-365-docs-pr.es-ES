---
title: Aplicar el filtro de puntuación de predicción a los elementos de un conjunto de revisión
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
description: Use un filtro de puntuación de predicción para mostrar los elementos que un modelo de codificación predictiva predice como relevantes o no relevantes.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822592"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>Aplicar un filtro de puntuación de predicción a un conjunto de opiniones (versión preliminar)

Después de crear un modelo de codificación predictiva en Advanced eDiscovery y entrenarlo hasta el punto en que es estable, puede aplicar el filtro de puntuación de predicción para mostrar los elementos del conjunto de revisión que el modelo ha determinado que son relevantes (o no son relevantes). Al crear un modelo, también se crea un filtro de puntuación de predicción correspondiente. Puede usar este filtro para mostrar los elementos asignados a una puntuación de predicción dentro de un intervalo especificado. En general, las puntuaciones de predicción **entre 0** y **.5** se asignan a los elementos que el modelo ha predicho no son relevantes. Los elementos asignados a puntuaciones de predicción entre **.5** y **1,0** son elementos que el modelo ha predicho son relevantes.

Estas son dos maneras de usar el filtro de puntuación de predicción:

- Priorizar la revisión de los elementos de un conjunto de revisión que el modelo ha predicho son relevantes.

- Los elementos Cull del conjunto de revisión que ha predicho el modelo no son relevantes. Como alternativa, puede usar el filtro de puntuación de predicción para des priorizar la revisión de elementos no relevantes.

## <a name="before-you-apply-a-prediction-score-filter"></a>Antes de aplicar un filtro de puntuación de predicción

- Cree un modelo de codificación predictiva para que se cree un filtro de puntuación de predicción correspondiente.

- Puedes aplicar un filtro de puntuación de predicción después de cualquiera de las rondas de entrenamiento. Pero es posible que desee esperar después de realizar varias rondas o hasta que el modelo sea estable antes de usar el filtro de puntuación de predicción.

## <a name="apply-a-prediction-score-filter"></a>Aplicar un filtro de puntuación de predicción

1. En el Microsoft 365 de cumplimiento, abra el Advanced eDiscovery caso, seleccione la pestaña Conjuntos de revisión y, a continuación, abra el conjunto de revisión. 

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

  > [!TIP]
  > Para ver la puntuación de predicción real que se asigna a un documento, puede hacer clic en la pestaña **Metadatos** del panel de lectura. Las puntuaciones de predicción de todos los modelos del conjunto de revisión se muestran en la **propiedad de metadatos RelevanceScores.**

## <a name="more-information"></a>Más información

- Para obtener más información acerca del uso de filtros, vea [Consulta y contenido de filtro en un conjunto de revisión.](review-set-search.md)
