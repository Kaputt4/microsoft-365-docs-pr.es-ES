---
title: Módulo de codificación predictiva para exhibición de documentos electrónicos avanzada (versión preliminar)
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
description: El nuevo módulo de codificación predictiva de eDiscovery avanzado usa el aprendizaje automático para analizar documentos en un conjunto de revisión para predictiva cuáles son los documentos relevantes para su caso o investigación.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383006"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="5adfc-103">Módulo de codificación predictiva para exhibición de documentos electrónicos avanzada (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5adfc-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="5adfc-104">Con el nuevo módulo de codificación predictiva de eDiscovery avanzado, puede crear y crear un modelo para priorizar la revisión de documentos a partir de los documentos más relevantes.</span><span class="sxs-lookup"><span data-stu-id="5adfc-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="5adfc-105">Para empezar, puede crear un modelo, etiquetar hasta 50 documentos y, a continuación, filtrar documentos por puntuaciones de predicción del modelo para revisar documentos relevantes no relevantes.</span><span class="sxs-lookup"><span data-stu-id="5adfc-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="5adfc-106">Este es un resumen rápido del flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="5adfc-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="5adfc-107">Abra el módulo de codificación predictiva en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="5adfc-107">Open the predictive coding module in a review set.</span></span>

   ![Haga clic en la lista desplegable Analizar de una revisión para ir al módulo de codificación predictiva](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="5adfc-109">En la **página Modelos de codificación predictiva,** haga clic en **Nuevo modelo** para crear un nuevo modelo de codificación predictiva.</span><span class="sxs-lookup"><span data-stu-id="5adfc-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![Crear un nuevo modelo](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="5adfc-111">Etiquete al menos 50 documentos **como Relevantes** **o No relevantes**.</span><span class="sxs-lookup"><span data-stu-id="5adfc-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="5adfc-112">Este etiquetado se usa para entrenar el sistema.</span><span class="sxs-lookup"><span data-stu-id="5adfc-112">This labeling is used to train the system.</span></span>

   ![Etiquetar documentos como relevantes o no relevantes para entrenar el sistema](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="5adfc-114">Aplica el **filtro de puntuación** de predicción del modelo al conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="5adfc-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="5adfc-115">Para ello:</span><span class="sxs-lookup"><span data-stu-id="5adfc-115">To do this:</span></span>

   1. <span data-ttu-id="5adfc-116">En el conjunto de revisión, haga clic **en Filtros**.</span><span class="sxs-lookup"><span data-stu-id="5adfc-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="5adfc-117">En la **página** desplegable Filtros, expanda la sección  **Análisis/ML** y, a continuación, active la casilla Puntuación de predicción para el modelo que desee aplicar.</span><span class="sxs-lookup"><span data-stu-id="5adfc-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="5adfc-118">En el **filtro Puntuación de** predicción, especifique una puntuación de predicción.</span><span class="sxs-lookup"><span data-stu-id="5adfc-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="5adfc-119">El filtro mostrará los documentos del conjunto de revisión que coincidan con la puntuación de predicción.</span><span class="sxs-lookup"><span data-stu-id="5adfc-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![Especificar una puntuación de predicción para filtrar documentos](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="5adfc-121">Supervise el rendimiento, el estado y la estabilidad del modelo.</span><span class="sxs-lookup"><span data-stu-id="5adfc-121">Monitor the performance, status, and stability of your model.</span></span>

   ![Supervisar el rendimiento, el estado y la estabilidad del modelo](..\media\PredictiveCoding5.png)
