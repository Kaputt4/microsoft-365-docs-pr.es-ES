---
title: Cómo volver a entrenar un clasificador en el explorador de contenido
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
description: Aprende a proporcionar comentarios a un clasificador que se puede entrenar en el explorador de contenido.
ms.openlocfilehash: 786ebb682e9cdd96c0c6503294bd4f316f777f68
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752628"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="37ca1-103">Cómo volver a entrenar un clasificador en el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="37ca1-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="37ca1-104">Un clasificador que se puede entrenar de Microsoft 365 es una herramienta que puede entrenar para reconocer distintos tipos de contenido, ya que le proporciona ejemplos para que los vea.</span><span class="sxs-lookup"><span data-stu-id="37ca1-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="37ca1-105">Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="37ca1-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="37ca1-106">En este artículo se muestra cómo mejorar el rendimiento de los clasificadores que se pueden entrenar personalizados y algunos clasificadores previamente formados proporcionando comentarios adicionales.</span><span class="sxs-lookup"><span data-stu-id="37ca1-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="37ca1-107">Para obtener más información acerca de los distintos tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="37ca1-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="37ca1-108">Permissions</span><span class="sxs-lookup"><span data-stu-id="37ca1-108">Permissions</span></span>

<span data-ttu-id="37ca1-109">Para acceder a clasificadores en el Centro de cumplimiento de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="37ca1-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="37ca1-110">El rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador</span><span class="sxs-lookup"><span data-stu-id="37ca1-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="37ca1-111">Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="37ca1-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="37ca1-112">Escenario de directiva de etiquetas de retención: roles administración de registros y administración de retención</span><span class="sxs-lookup"><span data-stu-id="37ca1-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="37ca1-113">Flujo de trabajo general</span><span class="sxs-lookup"><span data-stu-id="37ca1-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37ca1-114">Proporciona comentarios en el explorador de contenido para aplicar automáticamente directivas de etiquetas de retención a los elementos de Exchange y usa el clasificador como condición.</span><span class="sxs-lookup"><span data-stu-id="37ca1-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="37ca1-115">**Si no tiene una directiva de retención que aplique automáticamente una etiqueta de retención a los elementos de Exchange y use un clasificador como condición, detén esto.**</span><span class="sxs-lookup"><span data-stu-id="37ca1-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="37ca1-116">A medida que use los clasificadores, es posible que desee aumentar la precisión de las clasificaciones que están realizando.</span><span class="sxs-lookup"><span data-stu-id="37ca1-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="37ca1-117">Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como coincidencia o no.</span><span class="sxs-lookup"><span data-stu-id="37ca1-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="37ca1-118">Después de realizar 30 evaluaciones para un clasificador, toma ese comentario y se vuelve a entrenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="37ca1-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="37ca1-119">Para obtener más información sobre el flujo de trabajo general de volver a entrenar un clasificador, vea Flujo de proceso para volver a entrenar [un clasificador.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="37ca1-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="37ca1-120">Un clasificador ya debe estar publicado y en uso para poder volver a entrenarse.</span><span class="sxs-lookup"><span data-stu-id="37ca1-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="37ca1-121">Cómo volver a entrenar un clasificador en el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="37ca1-121">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="37ca1-122">Inicie sesión en el Centro de cumplimiento de Microsoft 365 con acceso al rol de administrador de seguridad o administrador de cumplimiento y abra el explorador de contenido de clasificación de datos del Centro de cumplimiento de **Microsoft 365.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="37ca1-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="37ca1-123">En la **lista Filtro de etiquetas, tipos** de información o categorías, expanda **Clasificadores que se pueden entrenar.**</span><span class="sxs-lookup"><span data-stu-id="37ca1-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37ca1-124">Los elementos agregados pueden tardar hasta ocho días en aparecer bajo el encabezado clasificadores que se pueden entrenar.</span><span class="sxs-lookup"><span data-stu-id="37ca1-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="37ca1-125">Elija el clasificador que usó para aplicar automáticamente la directiva de etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="37ca1-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="37ca1-126">Este es el clasificador que se puede entrenar sobre el que darás comentarios.</span><span class="sxs-lookup"><span data-stu-id="37ca1-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="37ca1-127">Si un elemento tiene una entrada en la columna **Etiqueta de** retención, significa que el elemento se ha clasificado como `match` un .</span><span class="sxs-lookup"><span data-stu-id="37ca1-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="37ca1-128">Si un elemento no tiene una  entrada en la columna Etiqueta de retención, significa que se ha clasificado como `close match` un .</span><span class="sxs-lookup"><span data-stu-id="37ca1-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="37ca1-129">Puedes mejorar la precisión del clasificador más proporcionando comentarios sobre `close match` los elementos.</span><span class="sxs-lookup"><span data-stu-id="37ca1-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="37ca1-130">Elija un elemento y ábralo.</span><span class="sxs-lookup"><span data-stu-id="37ca1-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="37ca1-131">Puedes proporcionar comentarios sobre varios elementos simultáneamente eligiendo todos ellos y luego eligiendo Mejorar clasificación **en** la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="37ca1-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="37ca1-132">Elija **Proporcionar comentarios.**</span><span class="sxs-lookup"><span data-stu-id="37ca1-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="37ca1-133">En el **panel comentarios detallados,** si el elemento es un verdadero positivo, elija **Coincidir**.</span><span class="sxs-lookup"><span data-stu-id="37ca1-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="37ca1-134">Si el elemento es un falso positivo, es decir, se incluyó incorrectamente en la categoría, elija **No coincidir.**</span><span class="sxs-lookup"><span data-stu-id="37ca1-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="37ca1-135">Si hay otro clasificador que sería más apropiado para el elemento, puedes elegirlo en la lista Sugerir otros clasificadores que se pueden **entrenar.**</span><span class="sxs-lookup"><span data-stu-id="37ca1-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="37ca1-136">Esto desencadenará que el otro clasificador evalúe el elemento.</span><span class="sxs-lookup"><span data-stu-id="37ca1-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="37ca1-137">Elige **Enviar comentarios** para enviar tu evaluación de las `match` clasificaciones y sugerir otros `not a match` clasificadores que se puedan entrenar.</span><span class="sxs-lookup"><span data-stu-id="37ca1-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="37ca1-138">Cuando hayas proporcionado 30 instancias de comentarios a un clasificador, se volverá a entrenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="37ca1-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="37ca1-139">La readaptación puede tardar de una a cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="37ca1-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="37ca1-140">Los clasificadores solo se pueden volver a entrenar dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="37ca1-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37ca1-141">Esta información va al clasificador de su espacio empresarial, **no vuelve a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="37ca1-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="37ca1-142">Abra **clasificadores que se pueden entrenar.**</span><span class="sxs-lookup"><span data-stu-id="37ca1-142">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="37ca1-143">El clasificador que se usó en la directiva de cumplimiento de comunicaciones aparecerá bajo el **encabezado De nuevo** aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="37ca1-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![clasificador en el estado de reentrenamiento](../media/classifier-retraining.png)

11. <span data-ttu-id="37ca1-145">Una vez completada la nueva formación, elija el clasificador para abrir la información general sobre el reentrenamiento.</span><span class="sxs-lookup"><span data-stu-id="37ca1-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Introducción a los resultados de la nueva formación de clasificadores](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="37ca1-147">Revise la acción recomendada y las comparaciones de predicción de las versiones actualizadas y publicadas actualmente del clasificador.</span><span class="sxs-lookup"><span data-stu-id="37ca1-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="37ca1-148">Si está satisfecho con los resultados de la readaptación, elija **Volver a publicar.**</span><span class="sxs-lookup"><span data-stu-id="37ca1-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="37ca1-149">Si no está satisfecho con los resultados de la nueva formación, puede proporcionar comentarios adicionales al clasificador en la interfaz de cumplimiento de comunicaciones e iniciar otro ciclo de reentrenamiento o no hacer nada en cuyo caso se seguirá usando la versión publicada actualmente del clasificador.</span><span class="sxs-lookup"><span data-stu-id="37ca1-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="37ca1-150">Detalles sobre las recomendaciones para volver a publicar</span><span class="sxs-lookup"><span data-stu-id="37ca1-150">Details on republishing recommendations</span></span>

<span data-ttu-id="37ca1-151">Aquí tiene un poco de información sobre cómo formulamos la recomendación de volver a publicar un clasificador reentrenado o sugerir una nueva formación.</span><span class="sxs-lookup"><span data-stu-id="37ca1-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="37ca1-152">Esto requiere un conocimiento más profundo de cómo funcionan los clasificadores que se pueden entrenar.</span><span class="sxs-lookup"><span data-stu-id="37ca1-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="37ca1-153">Después de una nueva formación, se evalúa el rendimiento del clasificador tanto en los elementos con comentarios como en los elementos usados originalmente para entrenar al clasificador.</span><span class="sxs-lookup"><span data-stu-id="37ca1-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="37ca1-154">Para los modelos integrados, los elementos usados para entrenar al clasificador son los elementos usados por Microsoft para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="37ca1-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="37ca1-155">Para los modelos personalizados, los elementos usados en el entrenamiento original el clasificador son de los sitios que ha agregado para su prueba y revisión.</span><span class="sxs-lookup"><span data-stu-id="37ca1-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="37ca1-156">Comparamos los números de rendimiento en ambos conjuntos de elementos para el clasificador reedidores y publicados para proporcionar una recomendación sobre si hubo alguna mejora para volver a publicar.</span><span class="sxs-lookup"><span data-stu-id="37ca1-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="37ca1-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="37ca1-157">See also</span></span>

- [<span data-ttu-id="37ca1-158">Obtenga información sobre los clasificadores entrenables</span><span class="sxs-lookup"><span data-stu-id="37ca1-158">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="37ca1-159">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="37ca1-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
