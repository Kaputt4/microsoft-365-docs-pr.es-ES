---
title: Cómo recapacitar un clasificador en el cumplimiento de comunicaciones
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
description: Obtenga información sobre cómo proporcionar comentarios a un clasificador capacitado en el cumplimiento de comunicaciones.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752654"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="01934-103">Cómo recapacitar un clasificador en el cumplimiento de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="01934-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="01934-104">Un clasificador entrenado de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar.</span><span class="sxs-lookup"><span data-stu-id="01934-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="01934-105">Una vez preparado, puede usarlo para identificar el elemento para la aplicación de las etiquetas de confidencialidad de Office, las directivas de cumplimiento de comunicaciones y las directivas de etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="01934-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="01934-106">En este artículo se muestra cómo mejorar el rendimiento de los clasificadores que se puede entrenar de forma personalizada y algunos clasificadores previamente entrenados proporcionándoles comentarios adicionales.</span><span class="sxs-lookup"><span data-stu-id="01934-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="01934-107">Para obtener más información acerca de los diferentes tipos de clasificadores, consulte [información sobre los clasificadores](classifier-learn-about.md)que se puedan entrenar.</span><span class="sxs-lookup"><span data-stu-id="01934-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="01934-108">Permissions</span><span class="sxs-lookup"><span data-stu-id="01934-108">Permissions</span></span>

<span data-ttu-id="01934-109">Para acceder a los clasificadores en el centro de cumplimiento de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="01934-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="01934-110">el rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador</span><span class="sxs-lookup"><span data-stu-id="01934-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="01934-111">Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="01934-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="01934-112">Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión</span><span class="sxs-lookup"><span data-stu-id="01934-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="01934-113">Flujo de trabajo general</span><span class="sxs-lookup"><span data-stu-id="01934-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01934-114">Los comentarios se proporcionan en la solución de cumplimiento que usa el clasificador como condición.</span><span class="sxs-lookup"><span data-stu-id="01934-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="01934-115">**Si no tiene una directiva de cumplimiento de comunicaciones que use un clasificador como condición, deténgalo aquí.**</span><span class="sxs-lookup"><span data-stu-id="01934-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="01934-116">Cuando use los clasificadores, es posible que quiera aumentar la precisión de las clasificaciones que están realizando.</span><span class="sxs-lookup"><span data-stu-id="01934-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="01934-117">Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como que coinciden o no coinciden.</span><span class="sxs-lookup"><span data-stu-id="01934-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="01934-118">Después de realizar 30 evaluaciones para un clasificador, se toman esos comentarios y se reforman automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01934-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="01934-119">Para obtener más información sobre el flujo de trabajo general de volver a entrenar un clasificador, consulte [Process Flow for Retraining a Classifier](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="01934-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="01934-120">Un clasificador ya debe estar publicado y en uso antes de que se pueda volver a entrenar.</span><span class="sxs-lookup"><span data-stu-id="01934-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="01934-121">Cómo recapacitar un clasificador en directivas de cumplimiento de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="01934-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="01934-122">Abra la Directiva de cumplimiento de comunicaciones que usa un clasificador como condición y elija uno de los elementos identificados de la lista **pendiente** .</span><span class="sxs-lookup"><span data-stu-id="01934-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="01934-123">Elija los puntos suspensivos y **mejore la clasificación**.</span><span class="sxs-lookup"><span data-stu-id="01934-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="01934-124">En el panel de **comentarios detallado** , si el elemento es un verdadero positivo, elija, **hacer coincidir**.</span><span class="sxs-lookup"><span data-stu-id="01934-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="01934-125">Si el elemento es un falso positivo, es que se incluyó incorrectamente en la categoría, elija **no una coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="01934-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="01934-126">Si hay otro clasificador que sería más apropiado para el elemento, puede elegirlo de la lista **sugerir otros clasificadores** con más formación.</span><span class="sxs-lookup"><span data-stu-id="01934-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="01934-127">Esto hará que se desencadene el otro clasificador para evaluar el elemento.</span><span class="sxs-lookup"><span data-stu-id="01934-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="01934-128">Puede enviar comentarios sobre varios elementos simultáneamente si los elige todos y, a continuación, elige **proporcionar comentarios detallados** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="01934-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="01934-129">Elija **Enviar comentarios** para enviar la evaluación del `match` , `not a match` clasificaciones y sugerir otros clasificadores capacitados.</span><span class="sxs-lookup"><span data-stu-id="01934-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="01934-130">Una vez que haya especificado 30 instancias de comentarios en un clasificador, se volverá a entrenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01934-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="01934-131">La formación puede tardar entre 1-4 horas.</span><span class="sxs-lookup"><span data-stu-id="01934-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="01934-132">Los clasificadores solo se pueden volver a entrenar dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="01934-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01934-133">Esta información va al clasificador en el espacio empresarial, no **se vuelve a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="01934-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="01934-134">Abra la página **clasificación de datos** en el centro de cumplimiento de **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="01934-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="01934-135">Abra **clasificadores** que se van a entrenar.</span><span class="sxs-lookup"><span data-stu-id="01934-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="01934-136">El clasificador que se usó en la Directiva de cumplimiento de comunicaciones aparecerá en el encabezado **de reentrenamiento** .</span><span class="sxs-lookup"><span data-stu-id="01934-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![clasificador en estado de reaprendizaje](../media/classifier-retraining.png)

9. <span data-ttu-id="01934-138">Una vez completada la formación, elija el clasificador para abrir la información general sobre el reentrenamiento.</span><span class="sxs-lookup"><span data-stu-id="01934-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Introducción a los resultados de la formación de clasificadores](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="01934-140">Revise la acción recomendada y las comparaciones de predicción de las versiones recapacitadas y publicadas actualmente del clasificador.</span><span class="sxs-lookup"><span data-stu-id="01934-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="01934-141">Si está de acuerdo con los resultados de la nueva formación, elija **volver a publicar**.</span><span class="sxs-lookup"><span data-stu-id="01934-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="01934-142">Si no está satisfecho con los resultados de la nueva formación, puede elegir proporcionar comentarios adicionales al clasificador en la interfaz de cumplimiento de la comunicación e iniciar otro ciclo de entrenamiento o no hacer nada en cuyo caso la versión publicada actualmente del clasificador seguirá utilizándose.</span><span class="sxs-lookup"><span data-stu-id="01934-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="01934-143">Detalles sobre las recomendaciones para volver a publicar</span><span class="sxs-lookup"><span data-stu-id="01934-143">Details on republishing recommendations</span></span>

<span data-ttu-id="01934-144">A continuación, se muestra una pequeña información sobre cómo formular la recomendación para volver a publicar un clasificador recapacitado o sugerir un nuevo entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="01934-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="01934-145">Esto requiere un conocimiento más profundo de cómo funcionan los clasificadores capacitados.</span><span class="sxs-lookup"><span data-stu-id="01934-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="01934-146">Después de una reformación, se evalúa el rendimiento del clasificador en los elementos con comentarios, así como con los elementos usados originalmente para entrenar al clasificador.</span><span class="sxs-lookup"><span data-stu-id="01934-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="01934-147">Para los modelos integrados, los elementos que se usan para entrenar al clasificador son los elementos que usa Microsoft para compilar el modelo.</span><span class="sxs-lookup"><span data-stu-id="01934-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="01934-148">Para los modelos personalizados, los elementos usados en la formación original del clasificador son de los sitios que ha agregado para probar y revisar.</span><span class="sxs-lookup"><span data-stu-id="01934-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="01934-149">Comparamos los números de rendimiento en ambos conjuntos de elementos del clasificador recapacitado y publicado para proporcionar una recomendación sobre si había mejoras en la publicación.</span><span class="sxs-lookup"><span data-stu-id="01934-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="01934-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="01934-150">See also</span></span>

- [<span data-ttu-id="01934-151">Obtener información sobre los clasificadores capacitados</span><span class="sxs-lookup"><span data-stu-id="01934-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="01934-152">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="01934-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
