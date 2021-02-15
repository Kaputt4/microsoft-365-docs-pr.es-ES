---
title: Cómo volver a entrenar un clasificador en el cumplimiento de las comunicaciones
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo proporcionar comentarios a un clasificador que se puede entrenar en el cumplimiento de las comunicaciones.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752654"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="2483a-103">Cómo volver a entrenar un clasificador en el cumplimiento de las comunicaciones</span><span class="sxs-lookup"><span data-stu-id="2483a-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="2483a-104">Un clasificador que se puede entrenar de Microsoft 365 es una herramienta que puede entrenar para reconocer distintos tipos de contenido, ya que le proporciona ejemplos para que los vea.</span><span class="sxs-lookup"><span data-stu-id="2483a-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="2483a-105">Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="2483a-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="2483a-106">En este artículo se muestra cómo mejorar el rendimiento de los clasificadores que se pueden entrenar personalizados y algunos clasificadores previamente formados proporcionando comentarios adicionales.</span><span class="sxs-lookup"><span data-stu-id="2483a-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="2483a-107">Para obtener más información acerca de los distintos tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="2483a-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="2483a-108">Permissions</span><span class="sxs-lookup"><span data-stu-id="2483a-108">Permissions</span></span>

<span data-ttu-id="2483a-109">Para acceder a clasificadores en el Centro de cumplimiento de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="2483a-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="2483a-110">El rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador</span><span class="sxs-lookup"><span data-stu-id="2483a-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="2483a-111">Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="2483a-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="2483a-112">Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión</span><span class="sxs-lookup"><span data-stu-id="2483a-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="2483a-113">Flujo de trabajo general</span><span class="sxs-lookup"><span data-stu-id="2483a-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2483a-114">Proporciona comentarios en la solución de cumplimiento que usa el clasificador como condición.</span><span class="sxs-lookup"><span data-stu-id="2483a-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="2483a-115">**Si no tiene una directiva de cumplimiento de comunicaciones que use un clasificador como condición, detén esto.**</span><span class="sxs-lookup"><span data-stu-id="2483a-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="2483a-116">A medida que use los clasificadores, es posible que desee aumentar la precisión de las clasificaciones que están realizando.</span><span class="sxs-lookup"><span data-stu-id="2483a-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="2483a-117">Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como coincidencia o no.</span><span class="sxs-lookup"><span data-stu-id="2483a-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="2483a-118">Después de realizar 30 evaluaciones para un clasificador, toma ese comentario y se vuelve a entrenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2483a-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="2483a-119">Para obtener más información sobre el flujo de trabajo general de volver a entrenar un clasificador, vea Flujo de proceso para volver a entrenar [un clasificador.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="2483a-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="2483a-120">Un clasificador ya debe estar publicado y en uso para poder volver a entrenarse.</span><span class="sxs-lookup"><span data-stu-id="2483a-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="2483a-121">Cómo volver a entrenar un clasificador en las directivas de cumplimiento de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="2483a-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="2483a-122">Abra la directiva de cumplimiento de comunicaciones que usa un clasificador como condición y elija uno de los elementos identificados en la **lista Pendiente.**</span><span class="sxs-lookup"><span data-stu-id="2483a-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="2483a-123">Elija los puntos suspensivos y **mejore la clasificación.**</span><span class="sxs-lookup"><span data-stu-id="2483a-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="2483a-124">En el **panel comentarios detallados,** si el elemento es un verdadero positivo, elija **Coincidir**.</span><span class="sxs-lookup"><span data-stu-id="2483a-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="2483a-125">Si el elemento es un falso positivo, es decir, se incluyó incorrectamente en la categoría, elija **No coincidir.**</span><span class="sxs-lookup"><span data-stu-id="2483a-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="2483a-126">Si hay otro clasificador que sería más apropiado para el elemento, puedes elegirlo en la lista Sugerir otros clasificadores que se pueden **entrenar.**</span><span class="sxs-lookup"><span data-stu-id="2483a-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="2483a-127">Esto desencadenará que el otro clasificador evalúe el elemento.</span><span class="sxs-lookup"><span data-stu-id="2483a-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="2483a-128">Puedes proporcionar comentarios sobre varios elementos simultáneamente eligiendo todos ellos y, a continuación, eligiendo **Proporcionar** comentarios detallados en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="2483a-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="2483a-129">Elige **Enviar comentarios** para enviar tu evaluación de las `match` clasificaciones y sugerir otros `not a match` clasificadores que se puedan entrenar.</span><span class="sxs-lookup"><span data-stu-id="2483a-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="2483a-130">Cuando hayas proporcionado 30 instancias de comentarios a un clasificador, se volverá a entrenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2483a-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="2483a-131">La readaptación puede tardar de 1 a 4 horas.</span><span class="sxs-lookup"><span data-stu-id="2483a-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="2483a-132">Los clasificadores solo se pueden volver a entrenar dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="2483a-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2483a-133">Esta información va al clasificador de su espacio empresarial, **no vuelve a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="2483a-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="2483a-134">Abra la **página Clasificación de** datos en el Centro de cumplimiento de Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="2483a-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="2483a-135">Abra **clasificadores que se pueden entrenar.**</span><span class="sxs-lookup"><span data-stu-id="2483a-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="2483a-136">El clasificador que se usó en la directiva de cumplimiento de comunicaciones aparecerá bajo el **encabezado De nuevo** aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="2483a-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![clasificador en el estado de reentrenamiento](../media/classifier-retraining.png)

9. <span data-ttu-id="2483a-138">Una vez completada la nueva formación, elija el clasificador para abrir la información general sobre el reentrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2483a-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Introducción a los resultados de la nueva formación de clasificadores](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="2483a-140">Revise la acción recomendada y las comparaciones de predicción de las versiones actualizadas y publicadas actualmente del clasificador.</span><span class="sxs-lookup"><span data-stu-id="2483a-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="2483a-141">Si está satisfecho con los resultados de la readaptación, elija **Volver a publicar.**</span><span class="sxs-lookup"><span data-stu-id="2483a-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="2483a-142">Si no está satisfecho con los resultados de la nueva formación, puede proporcionar comentarios adicionales al clasificador en la interfaz de cumplimiento de comunicaciones e iniciar otro ciclo de reentrenamiento o no hacer nada en cuyo caso se seguirá usando la versión publicada actualmente del clasificador.</span><span class="sxs-lookup"><span data-stu-id="2483a-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="2483a-143">Detalles sobre las recomendaciones para volver a publicar</span><span class="sxs-lookup"><span data-stu-id="2483a-143">Details on republishing recommendations</span></span>

<span data-ttu-id="2483a-144">Aquí tiene un poco de información sobre cómo formulamos la recomendación de volver a publicar un clasificador reentrenado o sugerir una nueva formación.</span><span class="sxs-lookup"><span data-stu-id="2483a-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="2483a-145">Esto requiere un conocimiento más profundo de cómo funcionan los clasificadores que se pueden entrenar.</span><span class="sxs-lookup"><span data-stu-id="2483a-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="2483a-146">Después de una nueva formación, se evalúa el rendimiento del clasificador tanto en los elementos con comentarios como en los elementos usados originalmente para entrenar al clasificador.</span><span class="sxs-lookup"><span data-stu-id="2483a-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="2483a-147">Para los modelos integrados, los elementos usados para entrenar al clasificador son los elementos usados por Microsoft para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="2483a-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="2483a-148">Para los modelos personalizados, los elementos usados en el entrenamiento original el clasificador son de los sitios que ha agregado para su prueba y revisión.</span><span class="sxs-lookup"><span data-stu-id="2483a-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="2483a-149">Comparamos los números de rendimiento en ambos conjuntos de elementos para el clasificador reedidores y publicados para proporcionar una recomendación sobre si hubo alguna mejora para volver a publicar.</span><span class="sxs-lookup"><span data-stu-id="2483a-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2483a-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="2483a-150">See also</span></span>

- [<span data-ttu-id="2483a-151">Obtenga información sobre los clasificadores entrenables</span><span class="sxs-lookup"><span data-stu-id="2483a-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="2483a-152">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="2483a-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
