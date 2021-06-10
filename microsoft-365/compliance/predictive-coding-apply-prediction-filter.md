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
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="b1c2f-103">Aplicar un filtro de puntuación de predicción a un conjunto de opiniones (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b1c2f-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="b1c2f-104">Después de crear un modelo de codificación predictiva en Advanced eDiscovery y entrenarlo hasta el punto en que es estable, puede aplicar el filtro de puntuación de predicción para mostrar los elementos del conjunto de revisión que el modelo ha determinado que son relevantes (o no son relevantes).</span><span class="sxs-lookup"><span data-stu-id="b1c2f-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="b1c2f-105">Al crear un modelo, también se crea un filtro de puntuación de predicción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="b1c2f-106">Puede usar este filtro para mostrar los elementos asignados a una puntuación de predicción dentro de un intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="b1c2f-107">En general, las puntuaciones de predicción **entre 0** y **.5** se asignan a los elementos que el modelo ha predicho no son relevantes.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="b1c2f-108">Los elementos asignados a puntuaciones de predicción entre **.5** y **1,0** son elementos que el modelo ha predicho son relevantes.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="b1c2f-109">Estas son dos maneras de usar el filtro de puntuación de predicción:</span><span class="sxs-lookup"><span data-stu-id="b1c2f-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="b1c2f-110">Priorizar la revisión de los elementos de un conjunto de revisión que el modelo ha predicho son relevantes.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="b1c2f-111">Los elementos Cull del conjunto de revisión que ha predicho el modelo no son relevantes.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="b1c2f-112">Como alternativa, puede usar el filtro de puntuación de predicción para des priorizar la revisión de elementos no relevantes.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="b1c2f-113">Antes de aplicar un filtro de puntuación de predicción</span><span class="sxs-lookup"><span data-stu-id="b1c2f-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="b1c2f-114">Cree un modelo de codificación predictiva para que se cree un filtro de puntuación de predicción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="b1c2f-115">Puedes aplicar un filtro de puntuación de predicción después de cualquiera de las rondas de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="b1c2f-116">Pero es posible que desee esperar después de realizar varias rondas o hasta que el modelo sea estable antes de usar el filtro de puntuación de predicción.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="b1c2f-117">Aplicar un filtro de puntuación de predicción</span><span class="sxs-lookup"><span data-stu-id="b1c2f-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="b1c2f-118">En el Microsoft 365 de cumplimiento, abra el Advanced eDiscovery caso, seleccione la pestaña Conjuntos de revisión y, a continuación, abra el conjunto de revisión. </span><span class="sxs-lookup"><span data-stu-id="b1c2f-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![Haga clic en Filtros para mostrar la página desplegable Filtros](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="b1c2f-120">Los filtros predeterminados precargados se muestran en la parte superior de la página del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="b1c2f-121">Puede dejar estos establecidos en **Any**.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="b1c2f-122">Haga **clic en** Filtros para mostrar la **página** desplegable Filtros.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="b1c2f-123">Expanda la **sección & de codificación predictiva** de Analytics para mostrar un conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filtro de puntuación de predicción en la sección & codificación predictiva de Analytics](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="b1c2f-125">La convención de nomenclatura para los filtros de puntuación de predicción es **Puntuación de predicción (nombre del modelo).**</span><span class="sxs-lookup"><span data-stu-id="b1c2f-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="b1c2f-126">Por ejemplo, el nombre del filtro de puntuación de predicción de un modelo denominado **Modelo A** es **Puntuación de predicción (modelo A).**</span><span class="sxs-lookup"><span data-stu-id="b1c2f-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="b1c2f-127">Seleccione el filtro de puntuación de predicción que desea usar y, a continuación, haga clic **en Listo**.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="b1c2f-128">En la página conjunto de revisión, haga clic en el desplegable del filtro de puntuación de predicción y escriba los valores mínimos y máximos para el intervalo de puntuación de predicción.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="b1c2f-129">Por ejemplo, la siguiente captura de pantalla muestra un intervalo de puntuación de predicción entre **.5** y **1,0**.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Valores mínimos y máximos para el filtro de puntuación de predicción](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="b1c2f-131">Haga clic fuera del filtro para aplicar automáticamente el filtro al conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="b1c2f-132">Se muestra una lista de documentos con una puntuación de predicción dentro del intervalo especificado en la página del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="b1c2f-133">Para ver la puntuación de predicción real que se asigna a un documento, puede hacer clic en la pestaña **Metadatos** del panel de lectura.</span><span class="sxs-lookup"><span data-stu-id="b1c2f-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="b1c2f-134">Las puntuaciones de predicción de todos los modelos del conjunto de revisión se muestran en la **propiedad de metadatos RelevanceScores.**</span><span class="sxs-lookup"><span data-stu-id="b1c2f-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="b1c2f-135">Más información</span><span class="sxs-lookup"><span data-stu-id="b1c2f-135">More information</span></span>

- <span data-ttu-id="b1c2f-136">Para obtener más información acerca del uso de filtros, vea [Consulta y contenido de filtro en un conjunto de revisión.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="b1c2f-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
