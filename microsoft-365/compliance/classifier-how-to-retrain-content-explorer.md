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
description: Obtenga información sobre cómo proporcionar comentarios a un clasificador que se puede entrenar en el Explorador de contenido.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793069"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="6fba8-103">Cómo volver a entrenar un clasificador en el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="6fba8-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="6fba8-104">Un Microsoft 365 clasificador que se puede entrenar es una herramienta que puede entrenar para reconocer varios tipos de contenido, ya que le proporciona ejemplos para que los vea.</span><span class="sxs-lookup"><span data-stu-id="6fba8-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="6fba8-105">Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de Office de confidencialidad, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="6fba8-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="6fba8-106">En este artículo se muestra cómo mejorar el rendimiento de los clasificadores personalizados y algunos clasificadores previamente formados proporcionando comentarios adicionales.</span><span class="sxs-lookup"><span data-stu-id="6fba8-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="6fba8-107">Para obtener más información sobre los diferentes tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="6fba8-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="6fba8-108">Vea este vídeo para obtener un resumen rápido del proceso de ajuste y reciclaje.</span><span class="sxs-lookup"><span data-stu-id="6fba8-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="6fba8-109">Todavía tendrá que leer este artículo completo para obtener los detalles.</span><span class="sxs-lookup"><span data-stu-id="6fba8-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="6fba8-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="6fba8-110">Permissions</span></span>

<span data-ttu-id="6fba8-111">Para obtener acceso a clasificadores en el centro de Microsoft 365 cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="6fba8-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="6fba8-112">el rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador</span><span class="sxs-lookup"><span data-stu-id="6fba8-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="6fba8-113">Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="6fba8-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="6fba8-114">Escenario de directiva de etiqueta de retención: roles de administración de registros y administración de retención</span><span class="sxs-lookup"><span data-stu-id="6fba8-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="6fba8-115">Flujo de trabajo general</span><span class="sxs-lookup"><span data-stu-id="6fba8-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fba8-116">Proporciona comentarios en el explorador de contenido para aplicar automáticamente directivas de etiquetas de retención a Exchange elementos y usa el clasificador como condición.</span><span class="sxs-lookup"><span data-stu-id="6fba8-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="6fba8-117">**Si no tiene una directiva de retención que aplique automáticamente una etiqueta de retención a los elementos Exchange y use un clasificador como condición, detén aquí.**</span><span class="sxs-lookup"><span data-stu-id="6fba8-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="6fba8-118">Al usar los clasificadores, es posible que desee aumentar la precisión de las clasificaciones que están realizando.</span><span class="sxs-lookup"><span data-stu-id="6fba8-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="6fba8-119">Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como una coincidencia o no una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="6fba8-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="6fba8-120">Después de realizar 30 evaluaciones para un clasificador, toma los comentarios y se vuelve a entrenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6fba8-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="6fba8-121">Para obtener más información sobre el flujo de trabajo general de reentrenamiento de un clasificador, vea Flujo de proceso para volver a entrenar [un clasificador](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="6fba8-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="6fba8-122">Un clasificador ya debe publicarse y usarse para poder volver a entrenarlo.</span><span class="sxs-lookup"><span data-stu-id="6fba8-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="6fba8-123">Cómo volver a entrenar un clasificador en el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="6fba8-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="6fba8-124">Inicie sesión en el Microsoft 365 de cumplimiento con el acceso a roles de administrador de seguridad o administración de cumplimiento y **abra** Microsoft 365 explorador de contenido de clasificación  >  **de** datos del  >  **centro de cumplimiento.**</span><span class="sxs-lookup"><span data-stu-id="6fba8-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="6fba8-125">En la **lista Filtrar por etiquetas, tipos** de información o categorías, expanda **Clasificadores que se pueden entrenar.**</span><span class="sxs-lookup"><span data-stu-id="6fba8-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fba8-126">Los elementos agregados pueden tardar hasta ocho días en aparecer bajo el encabezado clasificadores que se pueden entrenar.</span><span class="sxs-lookup"><span data-stu-id="6fba8-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="6fba8-127">Elija el clasificador que usó para aplicar automáticamente la directiva de etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="6fba8-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="6fba8-128">Este es el clasificador que se puede entrenar en el que darás comentarios.</span><span class="sxs-lookup"><span data-stu-id="6fba8-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="6fba8-129">Si un elemento tiene una entrada en la columna **Etiqueta** de retención, significa que el elemento se clasificó como `match` .</span><span class="sxs-lookup"><span data-stu-id="6fba8-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="6fba8-130">Si un elemento no tiene una entrada en la columna **Etiqueta** de retención, significa que se clasificó como `close match` .</span><span class="sxs-lookup"><span data-stu-id="6fba8-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="6fba8-131">Puedes mejorar la precisión del clasificador más proporcionando comentarios sobre `close match` los elementos.</span><span class="sxs-lookup"><span data-stu-id="6fba8-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="6fba8-132">Elija un elemento y ábralo.</span><span class="sxs-lookup"><span data-stu-id="6fba8-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="6fba8-133">Puede proporcionar comentarios sobre varios elementos al mismo tiempo eligiendo todos ellos y, a continuación, eligiendo Mejorar la **clasificación** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="6fba8-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="6fba8-134">Elija **Proporcionar comentarios**.</span><span class="sxs-lookup"><span data-stu-id="6fba8-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="6fba8-135">En el **panel Comentarios detallados,** si el elemento es un verdadero positivo, elija **Match**.</span><span class="sxs-lookup"><span data-stu-id="6fba8-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="6fba8-136">Si el elemento es un falso positivo, es decir, se incluyó incorrectamente en la categoría, elija **No coincidir.**</span><span class="sxs-lookup"><span data-stu-id="6fba8-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="6fba8-137">Si hay otro clasificador que sería más adecuado para el elemento, puede elegirlo en la lista Sugerir otros **clasificadores entrenables.**</span><span class="sxs-lookup"><span data-stu-id="6fba8-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="6fba8-138">Esto desencadenará el otro clasificador para evaluar el elemento.</span><span class="sxs-lookup"><span data-stu-id="6fba8-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="6fba8-139">Elija **Enviar comentarios** para enviar la evaluación de las `match` clasificaciones , y sugerir otros `not a match` clasificadores entrenables.</span><span class="sxs-lookup"><span data-stu-id="6fba8-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="6fba8-140">Cuando haya proporcionado 30 instancias de comentarios a un clasificador, se volverá a entrenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6fba8-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="6fba8-141">El reentrenamiento puede tardar de una a cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="6fba8-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="6fba8-142">Los clasificadores solo se pueden volver a entrenar dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="6fba8-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fba8-143">Esta información va al clasificador en el espacio empresarial, **no vuelve a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6fba8-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="6fba8-144">Abra **clasificadores trainables**.</span><span class="sxs-lookup"><span data-stu-id="6fba8-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="6fba8-145">El clasificador que se usó en la directiva de cumplimiento de comunicaciones aparecerá en el **encabezado Volver a entrenar.**</span><span class="sxs-lookup"><span data-stu-id="6fba8-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![clasificador en estado de reentrenamiento](../media/classifier-retraining.png)

11. <span data-ttu-id="6fba8-147">Una vez completado el reentrenamiento, elija el clasificador para abrir la introducción al reentrenamiento.</span><span class="sxs-lookup"><span data-stu-id="6fba8-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Introducción a los resultados de reentrenamiento de clasificadores](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="6fba8-149">Revise la acción recomendada y las comparaciones de predicción de las versiones reentrenadas y publicadas actualmente del clasificador.</span><span class="sxs-lookup"><span data-stu-id="6fba8-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="6fba8-150">Si está satisfecho con los resultados de la readaptación, elija **Volver a publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fba8-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="6fba8-151">Si no está satisfecho con los resultados de la readaptación, puede elegir proporcionar comentarios adicionales al clasificador en la interfaz del Explorador de contenido e iniciar otro ciclo de reentrenamiento o no hacer nada en cuyo caso se seguirá usando la versión publicada actualmente del clasificador.</span><span class="sxs-lookup"><span data-stu-id="6fba8-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Content Explorer interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="6fba8-152">Detalles sobre recomendaciones de reedición</span><span class="sxs-lookup"><span data-stu-id="6fba8-152">Details on republishing recommendations</span></span>

<span data-ttu-id="6fba8-153">Esta es una pequeña información sobre cómo formulamos la recomendación de volver a publicar un clasificador reentrenado o sugerir más reciclaje.</span><span class="sxs-lookup"><span data-stu-id="6fba8-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="6fba8-154">Esto requiere una comprensión un poco más profunda de cómo funcionan los clasificadores entrenables.</span><span class="sxs-lookup"><span data-stu-id="6fba8-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="6fba8-155">Después de un reentrenamiento, se evalúa el rendimiento del clasificador tanto en los elementos con comentarios como en los elementos usados originalmente para entrenar al clasificador.</span><span class="sxs-lookup"><span data-stu-id="6fba8-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="6fba8-156">Para los modelos integrados, los elementos usados para entrenar al clasificador son los elementos usados por Microsoft para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="6fba8-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="6fba8-157">Para los modelos personalizados, los elementos usados en el aprendizaje original el clasificador son de los sitios que ha agregado para la prueba y revisión.</span><span class="sxs-lookup"><span data-stu-id="6fba8-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="6fba8-158">Comparamos los números de rendimiento en ambos conjuntos de elementos para el clasificador reentrenado y publicado para proporcionar una recomendación sobre si hubo mejoras para volver a publicar.</span><span class="sxs-lookup"><span data-stu-id="6fba8-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="6fba8-159">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6fba8-159">See also</span></span>

- [<span data-ttu-id="6fba8-160">Obtenga información sobre los clasificadores entrenables</span><span class="sxs-lookup"><span data-stu-id="6fba8-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="6fba8-161">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="6fba8-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)