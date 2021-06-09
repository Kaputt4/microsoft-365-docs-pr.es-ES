---
title: Módulo Retiro de relevancia en Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: El módulo relevancia en Advanced eDiscovery se retirará el 10 de marzo de 2021. En este artículo se explica qué hacer antes de retirar relevancia. En concreto, para finalizar cualquier modelo sin terminar, ejecute el cálculo por lotes para que pueda conservar los metadatos del modelo.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822002"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="7acc3-105">Retiro del módulo Relevancia en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7acc3-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="7acc3-106">El 10 de marzo de 2021, retiraremos el módulo Relevancia en Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7acc3-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="7acc3-107">Esta retirada significa que las organizaciones ya no tendrán acceso al módulo Relevancia (yendo a Administrar el conjunto de revisión Relevancia en un caso Advanced eDiscovery) ni podrán tener acceso a los modelos de  >   relevancia existentes.</span><span class="sxs-lookup"><span data-stu-id="7acc3-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="7acc3-108">El módulo de relevancia actual que se está retirando se reemplazará por una nueva solución de codificación predictiva en el segundo trimestre de CY 2021.</span><span class="sxs-lookup"><span data-stu-id="7acc3-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="7acc3-109">Esta nueva funcionalidad permitirá a las organizaciones crear sus propios modelos de codificación predictiva en un flujo de trabajo más fácil e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="7acc3-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="7acc3-110">Para prepararse para esta próxima retirada, se recomienda que las organizaciones que usan el módulo Relevancia exporten los resultados de su modelo antes de la fecha de retiro ejecutando un cálculo por lotes para todos los modelos existentes.</span><span class="sxs-lookup"><span data-stu-id="7acc3-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="7acc3-111">Todas las puntuaciones de relevancia del modelo se almacenarán permanentemente en el conjunto de revisión correspondiente y se podrá acceder a ellos cuando se exporten documentos.</span><span class="sxs-lookup"><span data-stu-id="7acc3-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="7acc3-112">Las puntuaciones de relevancia también se conservan como metadatos en el archivo de carga.</span><span class="sxs-lookup"><span data-stu-id="7acc3-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="7acc3-113">Además, podrás filtrar el contenido del conjunto de revisión en función de la puntuación de relevancia y tener acceso a todos los metadatos producidos por los modelos de relevancia.</span><span class="sxs-lookup"><span data-stu-id="7acc3-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="7acc3-114">Modelos completos sin terminar</span><span class="sxs-lookup"><span data-stu-id="7acc3-114">Complete unfinished models</span></span>

<span data-ttu-id="7acc3-115">Para cualquier modelo de relevancia sin terminar, complete la evaluación, el aprendizaje y el cálculo por lotes para que pueda aplicar el modelo a los documentos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="7acc3-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="7acc3-116">Al completar el cálculo por lotes, se conservará la información después de la fecha de retiro del módulo Relevancia.</span><span class="sxs-lookup"><span data-stu-id="7acc3-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="7acc3-117">Estos son los pasos para completar cualquier modelo sin terminar:</span><span class="sxs-lookup"><span data-stu-id="7acc3-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="7acc3-118">Entrena el modelo hasta que esté estabilizado y listo para el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="7acc3-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="7acc3-119">Consulte [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="7acc3-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="7acc3-120">En la siguiente captura de pantalla se muestra un módulo que está listo para un cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="7acc3-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="7acc3-121">Observe que la evaluación y el aprendizaje se han completado y el siguiente paso es ejecutar el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="7acc3-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Captura de pantalla del modelo listo para el cálculo por lotes](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="7acc3-123">Ejecute el cálculo batch.</span><span class="sxs-lookup"><span data-stu-id="7acc3-123">Run the Batch calculation.</span></span> <span data-ttu-id="7acc3-124">Vea [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span><span class="sxs-lookup"><span data-stu-id="7acc3-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="7acc3-125">Compruebe que el cálculo por lotes se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7acc3-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="7acc3-126">Vea [Resultados del cálculo por lotes](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span><span class="sxs-lookup"><span data-stu-id="7acc3-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="7acc3-127">Para obtener ayuda con la finalización de modelos de relevancia sin terminar, póngase en contacto con el Soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7acc3-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
