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
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="61b97-104">Inicio rápido: codificación predictiva en Advanced eDiscovery (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="61b97-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="61b97-105">En este artículo se presenta un inicio rápido para usar la codificación predictiva en Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="61b97-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="61b97-106">El módulo de codificación predictiva de Advanced eDiscovery usa las capacidades inteligentes de aprendizaje automático en Advanced eDiscovery para ayudarle a reducir la cantidad de contenido que se va a revisar.</span><span class="sxs-lookup"><span data-stu-id="61b97-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="61b97-107">La codificación predictiva le ayuda a reducir y asignar grandes volúmenes de contenido de caso a un conjunto relevante de elementos que puede priorizar para su revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="61b97-108">Para ello, cree y entrena sus propios modelos de codificación predictiva que le ayudarán a priorizar la revisión de los elementos más relevantes de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="61b97-109">Este es un resumen rápido del proceso de codificación predictiva:</span><span class="sxs-lookup"><span data-stu-id="61b97-109">Here's an a quick overview of the predictive coding process:</span></span>

![Proceso de inicio rápido para codificación de predicción](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="61b97-111">Para empezar, cree un modelo, etiquete como pocos 50 elementos como relevantes o no relevantes.</span><span class="sxs-lookup"><span data-stu-id="61b97-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="61b97-112">A continuación, el sistema usa este aprendizaje para aplicar puntuaciones de predicción a todos los elementos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="61b97-113">Esto le permite filtrar elementos en función de la puntuación de predicción, lo que le permite revisar primero los elementos más relevantes (o no relevantes).</span><span class="sxs-lookup"><span data-stu-id="61b97-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="61b97-114">Si desea entrenar modelos con tasas de recuperación y acutracaciones más altas, puede seguir etiquetando elementos en rondas de aprendizaje posteriores hasta que el modelo se estabilice.</span><span class="sxs-lookup"><span data-stu-id="61b97-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="61b97-115">Una vez estabilizado el modelo, puede aplicar el filtro de predicción final para priorizar los elementos que se deben revisar.</span><span class="sxs-lookup"><span data-stu-id="61b97-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="61b97-116">Para obtener una introducción detallada a la codificación predictiva, vea [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="61b97-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="61b97-117">Paso 1: Crear un nuevo modelo de codificación predictiva</span><span class="sxs-lookup"><span data-stu-id="61b97-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="61b97-118">El primer paso es crear un nuevo modelo de codificación predictiva en el conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="61b97-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="61b97-119">En el centro Microsoft 365 cumplimiento, abra un Advanced eDiscovery caso y, a continuación, seleccione la **pestaña Conjuntos de** revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="61b97-120">Abra un conjunto de opiniones y, a continuación, haga clic **en Analytics Administrar**  >  **codificación predictiva (versión preliminar).**</span><span class="sxs-lookup"><span data-stu-id="61b97-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![Haga clic en el menú desplegable Analizar en el conjunto de revisión para ir a la página Codificación predictiva](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="61b97-122">En la **página Modelos de codificación predictiva (versión preliminar),** haga clic **en Nuevo modelo**.</span><span class="sxs-lookup"><span data-stu-id="61b97-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="61b97-123">En la página desplegable, escriba un nombre para el modelo y una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="61b97-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="61b97-124">Haga **clic en** Guardar para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="61b97-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="61b97-125">El sistema tardaría un par de minutos en preparar el modelo.</span><span class="sxs-lookup"><span data-stu-id="61b97-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="61b97-126">Después de que esté listo, puedes realizar la primera ronda de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="61b97-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="61b97-127">Para obtener instrucciones más detalladas, vea [Create a predictive coding model](predictive-coding-create-model.md).</span><span class="sxs-lookup"><span data-stu-id="61b97-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="61b97-128">Paso 2: Realizar la primera ronda de entrenamiento</span><span class="sxs-lookup"><span data-stu-id="61b97-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="61b97-129">Después de crear el modelo, el siguiente paso es completar la primera ronda de aprendizaje etiquetando los elementos como relevantes o no relevantes.</span><span class="sxs-lookup"><span data-stu-id="61b97-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="61b97-130">Abra el conjunto de opiniones y, a continuación, haga clic **en Analytics**  >  **Administrar codificación predictiva (versión preliminar).**</span><span class="sxs-lookup"><span data-stu-id="61b97-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="61b97-131">En la **página Modelos de codificación predictiva (versión** preliminar), seleccione el modelo que desea entrenar.</span><span class="sxs-lookup"><span data-stu-id="61b97-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="61b97-132">En la **pestaña Información** general, en **Ronda 1,** haga clic **en Iniciar siguiente ronda de aprendizaje.**</span><span class="sxs-lookup"><span data-stu-id="61b97-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="61b97-133">Se **muestra la** pestaña Aprendizaje y contiene 50 elementos para etiquetar.</span><span class="sxs-lookup"><span data-stu-id="61b97-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="61b97-134">Revise cada documento y, a continuación, **seleccione** el botón Relevante o No **relevante** en la parte inferior del panel de lectura para etiquetar.</span><span class="sxs-lookup"><span data-stu-id="61b97-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Etiquetar cada documento como relevante o no relevante](..\media\TrainModel1.png)

5. <span data-ttu-id="61b97-136">Después de etiquetar los 50 elementos, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="61b97-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="61b97-137">El sistema tardaría un par de minutos en "aprender" del etiquetado y actualizar el modelo.</span><span class="sxs-lookup"><span data-stu-id="61b97-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="61b97-138">Una vez completado este proceso, se muestra el estado **Listo** para el modelo en la página Modelos de codificación **predictiva (versión** preliminar).</span><span class="sxs-lookup"><span data-stu-id="61b97-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="61b97-139">Para obtener instrucciones más detalladas, vea [Train a predictive coding model](predictive-coding-train-model.md).</span><span class="sxs-lookup"><span data-stu-id="61b97-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="61b97-140">Paso 3: Aplicar el filtro de puntuación de predicción a los elementos del conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="61b97-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="61b97-141">Después de realizar la concesión de una ronda de aprendizaje, puede aplicar el filtro de puntuación de predicción a los elementos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="61b97-142">Esto le permite revisar los elementos que el modelo ha predicho como relevantes o no relevantes.</span><span class="sxs-lookup"><span data-stu-id="61b97-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="61b97-143">Abra el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-143">Open the review set.</span></span>

   ![Haga clic en Filtros para mostrar la página desplegable Filtros](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="61b97-145">Los filtros predeterminados precargados se muestran en la parte superior de la página del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="61b97-146">Puede dejar estos establecidos en **Any**.</span><span class="sxs-lookup"><span data-stu-id="61b97-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="61b97-147">Haga **clic en** Filtros para mostrar la **página** desplegable Filtros.</span><span class="sxs-lookup"><span data-stu-id="61b97-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="61b97-148">Expanda la **sección & de codificación predictiva** de Analytics para mostrar un conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="61b97-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Filtro de puntuación de predicción en la sección & codificación predictiva de Analytics](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="61b97-150">La convención de nomenclatura para los filtros de puntuación de predicción es **Puntuación de predicción (nombre del modelo).**</span><span class="sxs-lookup"><span data-stu-id="61b97-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="61b97-151">Por ejemplo, el nombre del filtro de puntuación de predicción de un modelo denominado **Modelo A** es **Puntuación de predicción (modelo A).**</span><span class="sxs-lookup"><span data-stu-id="61b97-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="61b97-152">Seleccione el filtro de puntuación de predicción que desea usar y, a continuación, haga clic **en Listo**.</span><span class="sxs-lookup"><span data-stu-id="61b97-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="61b97-153">En la página conjunto de revisión, haga clic en el desplegable del filtro de puntuación de predicción y escriba los valores mínimos y máximos para el intervalo de puntuación de predicción.</span><span class="sxs-lookup"><span data-stu-id="61b97-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="61b97-154">Por ejemplo, la siguiente captura de pantalla muestra un intervalo de puntuación de predicción entre **.5** y **1,0**.</span><span class="sxs-lookup"><span data-stu-id="61b97-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Valores mínimos y máximos para el filtro de puntuación de predicción](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="61b97-156">Haga clic fuera del filtro para aplicar automáticamente el filtro al conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="61b97-157">Se muestra una lista de documentos con una puntuación de predicción dentro del intervalo especificado en la página del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="61b97-158">Para obtener instrucciones más detalladas, vea [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span><span class="sxs-lookup"><span data-stu-id="61b97-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="61b97-159">Paso 4: Realizar más rondas de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="61b97-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="61b97-160">Lo más probable es que tenga que realizar más rondas de aprendizaje para entrenar al módulo para predecir mejor los elementos relevantes y no relevantes del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="61b97-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="61b97-161">En general, entrenarás el modelo suficientes veces hasta que se estabilice lo suficiente como para satisfacer tus requisitos.</span><span class="sxs-lookup"><span data-stu-id="61b97-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="61b97-162">Para obtener más información, vea [Realizar rondas de aprendizaje adicionales](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="61b97-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="61b97-163">Paso 5: Aplicar el filtro de puntuación de predicción final para priorizar la revisión</span><span class="sxs-lookup"><span data-stu-id="61b97-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="61b97-164">Repita las instrucciones del paso 3 para aplicar la puntuación de predicción final al conjunto de revisión para priorizar la revisión de elementos relevantes y no relevantes después de completar todas las rondas de aprendizaje y estabilizar el modelo.</span><span class="sxs-lookup"><span data-stu-id="61b97-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
