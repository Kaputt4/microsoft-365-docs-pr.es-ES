---
title: Cómo recapacitar un clasificador en el explorador de contenido (versión preliminar)
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
description: Obtenga información sobre cómo enviar comentarios a un clasificador capacitado en el explorador de contenido.
ms.openlocfilehash: 0fbce595894cbbf2a017fc1bf657b14a5b812e29
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132359"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="ed54d-103">Cómo recapacitar un clasificador en el explorador de contenido (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ed54d-103">How to retrain a classifier in content explorer (preview)</span></span>

<span data-ttu-id="ed54d-104">Un clasificador entrenado de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar.</span><span class="sxs-lookup"><span data-stu-id="ed54d-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="ed54d-105">Una vez preparado, puede usarlo para identificar el elemento para la aplicación de las etiquetas de confidencialidad de Office, las directivas de cumplimiento de comunicaciones y las directivas de etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="ed54d-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="ed54d-106">En este artículo se muestra cómo mejorar el rendimiento de los clasificadores que se puede entrenar de forma personalizada y algunos clasificadores previamente entrenados proporcionándoles comentarios adicionales.</span><span class="sxs-lookup"><span data-stu-id="ed54d-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="ed54d-107">Para obtener más información acerca de los diferentes tipos de clasificadores, consulte [información sobre los clasificadores que se puedan entrenar (versión preliminar)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="ed54d-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="ed54d-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="ed54d-108">Permissions</span></span>

<span data-ttu-id="ed54d-109">Para acceder a los clasificadores en el centro de cumplimiento de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="ed54d-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="ed54d-110">el rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador</span><span class="sxs-lookup"><span data-stu-id="ed54d-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="ed54d-111">Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="ed54d-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="ed54d-112">Escenario de directiva de etiqueta de retención: funciones de administración de registros y retención</span><span class="sxs-lookup"><span data-stu-id="ed54d-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="ed54d-113">Flujo de trabajo general</span><span class="sxs-lookup"><span data-stu-id="ed54d-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed54d-114">Los comentarios se proporcionan en el explorador de contenido para aplicar automáticamente las directivas de etiquetas de retención a los elementos de Exchange y se usa el clasificador como condición.</span><span class="sxs-lookup"><span data-stu-id="ed54d-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="ed54d-115">**Si no tiene una directiva de retención que aplique automáticamente una etiqueta de retención a los elementos de Exchange y use un clasificador como condición, deténgalo aquí.**</span><span class="sxs-lookup"><span data-stu-id="ed54d-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="ed54d-116">Cuando use los clasificadores, es posible que quiera aumentar la precisión de las clasificaciones que están realizando.</span><span class="sxs-lookup"><span data-stu-id="ed54d-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="ed54d-117">Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como que coinciden o no coinciden.</span><span class="sxs-lookup"><span data-stu-id="ed54d-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="ed54d-118">Después de realizar 30 evaluaciones para un clasificador, se toman esos comentarios y se reforman automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ed54d-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="ed54d-119">Para obtener más información sobre el flujo de trabajo general de volver a entrenar un clasificador, consulte [Process Flow for Retraining a Classifier](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="ed54d-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="ed54d-120">Un clasificador ya debe estar publicado y en uso antes de que se pueda volver a entrenar.</span><span class="sxs-lookup"><span data-stu-id="ed54d-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="ed54d-121">Cómo recapacitar un clasificador en el explorador de contenido (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ed54d-121">How to retrain a classifier in content explorer (preview)</span></span>

1. <span data-ttu-id="ed54d-122">Inicie sesión en el centro de cumplimiento de Microsoft 365 con el administrador de cumplimiento o con el rol de administrador de seguridad y abra el explorador de contenido de clasificación de datos del **centro de cumplimiento de Microsoft 365**  >  **Data classification**  >  **Content explorer**.</span><span class="sxs-lookup"><span data-stu-id="ed54d-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="ed54d-123">En la lista **filtrar por etiquetas, tipos de información o categorías** , expanda **clasificadores**que se pueden entrenar.</span><span class="sxs-lookup"><span data-stu-id="ed54d-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed54d-124">Los elementos agregados pueden tardar hasta ocho días en aparecer en el encabezado clasificadores capacitados.</span><span class="sxs-lookup"><span data-stu-id="ed54d-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="ed54d-125">Elija el clasificador que se puede entrenar que usó en la Directiva de etiquetas de retención que se aplica automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ed54d-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="ed54d-126">Este es el clasificador que se puede entrenar en el que proporcionará Comentarios.</span><span class="sxs-lookup"><span data-stu-id="ed54d-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="ed54d-127">Si un elemento tiene una entrada en la columna de la **etiqueta de retención** , significa que el elemento se clasificó como un `match` .</span><span class="sxs-lookup"><span data-stu-id="ed54d-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="ed54d-128">Si un elemento no tiene una entrada en la columna **etiqueta de retención** , significa que se clasificó como un `close match` .</span><span class="sxs-lookup"><span data-stu-id="ed54d-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="ed54d-129">Puede mejorar la precisión del clasificador con mayor frecuencia si proporciona comentarios sobre `close match` los elementos.</span><span class="sxs-lookup"><span data-stu-id="ed54d-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="ed54d-130">Elija un elemento y ábralo.</span><span class="sxs-lookup"><span data-stu-id="ed54d-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="ed54d-131">Puede enviar comentarios sobre varios elementos simultáneamente si los elige todos y, a continuación, elige **mejorar clasificación** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed54d-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="ed54d-132">Elija **Enviar comentarios**.</span><span class="sxs-lookup"><span data-stu-id="ed54d-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="ed54d-133">En el panel de **comentarios detallado** , si el elemento es un verdadero positivo, elija, **hacer coincidir**.</span><span class="sxs-lookup"><span data-stu-id="ed54d-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="ed54d-134">Si el elemento es un falso positivo, es que se incluyó incorrectamente en la categoría, elija **no una coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="ed54d-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="ed54d-135">Si hay otro clasificador que sería más apropiado para el elemento, puede elegirlo de la lista **sugerir otros clasificadores** con más formación.</span><span class="sxs-lookup"><span data-stu-id="ed54d-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="ed54d-136">Esto hará que se desencadene el otro clasificador para evaluar el elemento.</span><span class="sxs-lookup"><span data-stu-id="ed54d-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="ed54d-137">Elija **Enviar comentarios** para enviar la evaluación del `match` , `not a match` clasificaciones y sugerir otros clasificadores capacitados.</span><span class="sxs-lookup"><span data-stu-id="ed54d-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="ed54d-138">Una vez que haya especificado 30 instancias de comentarios en un clasificador, se volverá a entrenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ed54d-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="ed54d-139">La formación puede tardar entre 1 y 4 horas.</span><span class="sxs-lookup"><span data-stu-id="ed54d-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="ed54d-140">Los clasificadores solo se pueden volver a entrenar dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="ed54d-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed54d-141">Esta información va al clasificador en el espacio empresarial, no **se vuelve a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ed54d-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="ed54d-142">Abra clasificadores que se van a **entrenar (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="ed54d-142">Open **Trainable classifiers (preview)**.</span></span>
10. <span data-ttu-id="ed54d-143">El clasificador que se usó en la Directiva de cumplimiento de comunicaciones aparecerá en el encabezado **de reentrenamiento** .</span><span class="sxs-lookup"><span data-stu-id="ed54d-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![clasificador en estado de reaprendizaje](../media/classifier-retraining.png)

11. <span data-ttu-id="ed54d-145">Una vez completada la formación, elija el clasificador para abrir la información general sobre el reentrenamiento.</span><span class="sxs-lookup"><span data-stu-id="ed54d-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Introducción a los resultados de la formación de clasificadores](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="ed54d-147">Revise la acción recomendada y las comparaciones de predicción de las versiones recapacitadas y publicadas actualmente del clasificador.</span><span class="sxs-lookup"><span data-stu-id="ed54d-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="ed54d-148">Si está de acuerdo con los resultados de la nueva formación, elija **volver a publicar**.</span><span class="sxs-lookup"><span data-stu-id="ed54d-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="ed54d-149">Si no está satisfecho con los resultados de la nueva formación, puede elegir proporcionar comentarios adicionales al clasificador en la interfaz de cumplimiento de la comunicación e iniciar otro ciclo de entrenamiento o no hacer nada en cuyo caso la versión publicada actualmente del clasificador seguirá utilizándose.</span><span class="sxs-lookup"><span data-stu-id="ed54d-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="ed54d-150">Detalles sobre las recomendaciones para volver a publicar</span><span class="sxs-lookup"><span data-stu-id="ed54d-150">Details on republishing recommendations</span></span>

<span data-ttu-id="ed54d-151">A continuación, se muestra una pequeña información sobre cómo formular la recomendación para volver a publicar un clasificador recapacitado o sugerir un nuevo entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="ed54d-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="ed54d-152">Esto requiere un conocimiento más profundo de cómo funcionan los clasificadores capacitados.</span><span class="sxs-lookup"><span data-stu-id="ed54d-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="ed54d-153">Después de una reformación, se evalúa el rendimiento del clasificador en los elementos con comentarios, así como con los elementos usados originalmente para entrenar al clasificador.</span><span class="sxs-lookup"><span data-stu-id="ed54d-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="ed54d-154">Para los modelos integrados, los elementos que se usan para entrenar al clasificador son los elementos que usa Microsoft para compilar el modelo.</span><span class="sxs-lookup"><span data-stu-id="ed54d-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="ed54d-155">Para los modelos personalizados, los elementos usados en la formación original del clasificador son de los sitios que ha agregado para probar y revisar.</span><span class="sxs-lookup"><span data-stu-id="ed54d-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="ed54d-156">Comparamos los números de rendimiento en ambos conjuntos de elementos del clasificador recapacitado y publicado para proporcionar una recomendación sobre si había mejoras en la publicación.</span><span class="sxs-lookup"><span data-stu-id="ed54d-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ed54d-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed54d-157">See also</span></span>

- [<span data-ttu-id="ed54d-158">Obtener información sobre los clasificadores capacitados (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ed54d-158">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="ed54d-159">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="ed54d-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
