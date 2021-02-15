---
title: Retirada del módulo relevancia en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: El módulo relevancia en eDiscovery avanzado se retirará el 10 de marzo de 2021. En este artículo se explica qué hacer antes de retirar Relevancia. En concreto, para finalizar los modelos sin terminar, ejecute el cálculo por lotes para que pueda conservar los metadatos del modelo.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122539"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="b1043-105">Retirada del módulo Relevancia en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="b1043-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="b1043-106">El 10 de marzo de 2021, retiraremos el módulo relevancia en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="b1043-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="b1043-107">Esta retirada significa que las organizaciones ya no tendrán acceso al módulo Relevancia (yendo a Administrar relevancia del conjunto de revisión en un caso de eDiscovery avanzado) ni podrán acceder a los modelos de relevancia  >   existentes.</span><span class="sxs-lookup"><span data-stu-id="b1043-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="b1043-108">El módulo de relevancia actual que se está retirando se reemplazará por una nueva solución de codificación predictiva en el segundo trimestre de CY 2021.</span><span class="sxs-lookup"><span data-stu-id="b1043-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="b1043-109">Esta nueva funcionalidad permitirá a las organizaciones crear sus propios modelos de codificación predictiva en un flujo de trabajo más sencillo e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="b1043-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="b1043-110">Para prepararse para esta próxima retirada, se recomienda que las organizaciones que usen el módulo Relevancia exporten los resultados de su modelo antes de la fecha de retirada mediante la ejecución de un cálculo por lotes para todos los modelos existentes.</span><span class="sxs-lookup"><span data-stu-id="b1043-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="b1043-111">Todas las puntuaciones de relevancia del modelo se almacenarán permanentemente en el conjunto de revisión correspondiente y se podrá tener acceso a ellos cuando se exporten los documentos.</span><span class="sxs-lookup"><span data-stu-id="b1043-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="b1043-112">Las puntuaciones de relevancia también se conservan como metadatos en el archivo de carga.</span><span class="sxs-lookup"><span data-stu-id="b1043-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="b1043-113">Además, podrá filtrar el contenido del conjunto de revisión en función de la puntuación de relevancia y tener acceso a todos los metadatos producidos por los modelos de relevancia.</span><span class="sxs-lookup"><span data-stu-id="b1043-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="b1043-114">Modelos sin terminar completos</span><span class="sxs-lookup"><span data-stu-id="b1043-114">Complete unfinished models</span></span>

<span data-ttu-id="b1043-115">Para cualquier modelo de relevancia sin terminar, complete la evaluación, el aprendizaje y el cálculo por lotes para que pueda aplicar el modelo a los documentos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b1043-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="b1043-116">Al completar el cálculo por lotes se conservará la información después de la fecha de retirada del módulo relevancia.</span><span class="sxs-lookup"><span data-stu-id="b1043-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="b1043-117">Estos son los pasos para completar los modelos sin terminar:</span><span class="sxs-lookup"><span data-stu-id="b1043-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="b1043-118">Entrena el modelo hasta que esté estabilizado y listo para el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="b1043-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="b1043-119">Vea [el curso de etiquetado y relevancia.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="b1043-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="b1043-120">La siguiente captura de pantalla muestra un módulo que está listo para un cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="b1043-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="b1043-121">Observe que la evaluación y el aprendizaje se han completado y el siguiente paso es ejecutar el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="b1043-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Captura de pantalla del modelo listo para el cálculo por lotes](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="b1043-123">Ejecute el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="b1043-123">Run the Batch calculation.</span></span> <span data-ttu-id="b1043-124">Vea [Realizar cálculos por lotes.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="b1043-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="b1043-125">Compruebe que el cálculo por lotes se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b1043-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="b1043-126">Vea los [resultados del cálculo por lotes.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)</span><span class="sxs-lookup"><span data-stu-id="b1043-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="b1043-127">Para obtener ayuda con la finalización de modelos de relevancia sin terminar, póngase en contacto con el Soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1043-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
