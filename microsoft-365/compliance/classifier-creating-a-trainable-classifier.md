---
title: Crear un clasificador que se pudiera entrenar (versión preliminar)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Use clasificadores que se puedan entrenar cuando uno de los clasificadores de cuadros listos para usar no satisfaga sus necesidades. Un clasificador de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar. En este tema se muestra cómo crear un clasificador personalizado.
ms.openlocfilehash: 1d62b70d821593ff7d8d3889c0da0e0b5cc9809f
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38691083"
---
# <a name="creating-a-trainable-classifier-preview"></a><span data-ttu-id="aa323-105">Creación de un clasificador capacitado (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aa323-105">Creating a trainable classifier (preview)</span></span>

<span data-ttu-id="aa323-106">Use clasificadores que se podrán entrenar cuando uno de los clasificadores de salida no satisfaga sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="aa323-106">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="aa323-107">Un clasificador de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar.</span><span class="sxs-lookup"><span data-stu-id="aa323-107">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="aa323-108">La formación del clasificador implica que, en primer lugar, muestreos de ti que sean de picking humanos y que cumplan la categoría.</span><span class="sxs-lookup"><span data-stu-id="aa323-108">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="aa323-109">A continuación, una vez procesadas las pruebas, pruebe las predicciones dándole una mezcla de muestras positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="aa323-109">Then, after it has processed those, you test the predictions by giving it a mix of positive and negative samples.</span></span>

<span data-ttu-id="aa323-110">Para obtener más información acerca de los diferentes tipos de clasificadores, consulte [Getting Started with trainable Classifiers (Preview)](classifier-getting-started-with.md) .</span><span class="sxs-lookup"><span data-stu-id="aa323-110">To learn more about the different types of classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md)</span></span>

<span data-ttu-id="aa323-111">Esta escala de tiempo refleja una implementación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aa323-111">This timeline reflects a sample deployment.</span></span>

![trainable-Classifier-Timeline](media/trainable-classifier-deployment-timeline_border.png)

## <a name="seed-content"></a><span data-ttu-id="aa323-113">Contenido de inicialización</span><span class="sxs-lookup"><span data-stu-id="aa323-113">Seed content</span></span>

<span data-ttu-id="aa323-114">Cuando quiera que un clasificador capacitado identifique de forma independiente y precisa un elemento en una categoría de contenido concreta, primero tiene que presentarlo con muchos ejemplos del tipo de contenido que se encuentran en la categoría.</span><span class="sxs-lookup"><span data-stu-id="aa323-114">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="aa323-115">Esta alimentación de muestras al clasificador que se pueda entrenar se conoce como *inicialización*.</span><span class="sxs-lookup"><span data-stu-id="aa323-115">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="aa323-116">El contenido de inicialización se selecciona por un hombre y se juzga para representar la categoría de contenido.</span><span class="sxs-lookup"><span data-stu-id="aa323-116">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="aa323-117">Debe tener al menos 50 ejemplos positivos y hasta 500.</span><span class="sxs-lookup"><span data-stu-id="aa323-117">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="aa323-118">El clasificador que se pueda entrenar procesará hasta las muestras creadas más recientes de 500 (según la fecha de creación del archivo y la marca de tiempo).</span><span class="sxs-lookup"><span data-stu-id="aa323-118">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="aa323-119">Cuanto más ejemplos proporcione, más precisas serán las predicciones que realizará el clasificador.</span><span class="sxs-lookup"><span data-stu-id="aa323-119">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

## <a name="testing-content"></a><span data-ttu-id="aa323-120">Pruebas de contenido</span><span class="sxs-lookup"><span data-stu-id="aa323-120">Testing content</span></span>

<span data-ttu-id="aa323-121">Una vez que el clasificador que se puede entrenar haya procesado suficientes ejemplos positivos para crear un modelo de predicción, debe probar las predicciones que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los que no.</span><span class="sxs-lookup"><span data-stu-id="aa323-121">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that do not.</span></span> <span data-ttu-id="aa323-122">Para ello, debe alimentarse en un conjunto de contenido seleccionado, con suerte más grande, que consista en muestras que deben incluirse en la categoría y en ejemplos que no lo hagan.</span><span class="sxs-lookup"><span data-stu-id="aa323-122">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="aa323-123">Una vez que los procese, irá a los resultados manualmente y comprobará si cada predicción es correcta, incorrecta o no está seguro.</span><span class="sxs-lookup"><span data-stu-id="aa323-123">Once it processes those, you will manually go through the results and verify if each prediction is correct, incorrect or you are not sure.</span></span> <span data-ttu-id="aa323-124">El clasificador capacitado usa estos comentarios para mejorar su modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="aa323-124">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="aa323-125">Para obtener los mejores resultados, tenga 10.000 elementos en su conjunto de muestras de prueba con una distribución equitativa de las coincidencias negativas y positivas.</span><span class="sxs-lookup"><span data-stu-id="aa323-125">For best results, have 10,000 items in your test sample set with an even distribution of positive and negative matches.</span></span>

> [!TIP]
> <span data-ttu-id="aa323-126">La suscripción es necesaria la primera vez para los clasificadores que se deben entrenar.</span><span class="sxs-lookup"><span data-stu-id="aa323-126">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="aa323-127">Se necesitan doce días para Microsoft 365 para completar una evaluación de línea de base del contenido de su organización.</span><span class="sxs-lookup"><span data-stu-id="aa323-127">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="aa323-128">Cómo crear un clasificador que se pueda entrenar</span><span class="sxs-lookup"><span data-stu-id="aa323-128">How to create a trainable classifier</span></span>

1. <span data-ttu-id="aa323-129">Recopilar entre 50-500 elementos de contenido de inicialización.</span><span class="sxs-lookup"><span data-stu-id="aa323-129">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="aa323-130">Estos deben ser solo ejemplos que representen de forma segura el tipo de contenido que desea que el clasificador capacitado identifique como en la categoría de clasificación.</span><span class="sxs-lookup"><span data-stu-id="aa323-130">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="aa323-131">Vea las [extensiones de nombre de archivo y los tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo compatibles.</span><span class="sxs-lookup"><span data-stu-id="aa323-131">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa323-132">Los elementos de la muestra de inicialización y de prueba no deben cifrarse y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="aa323-132">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa323-133">Asegúrese de que los elementos del conjunto de SEED son ejemplos **fuertes** de la categoría.</span><span class="sxs-lookup"><span data-stu-id="aa323-133">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="aa323-134">El clasificador que se puede entrenar crea inicialmente su modelo en función de su inicialización.</span><span class="sxs-lookup"><span data-stu-id="aa323-134">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="aa323-135">El clasificador presupone que todas las muestras de inicialización son positivos y no tienen forma de saber si una muestra es una coincidencia débil o negativa con la categoría.</span><span class="sxs-lookup"><span data-stu-id="aa323-135">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="aa323-136">Colocar el contenido de inicialización en una carpeta de SharePoint Online que esté dedicada exclusivamente a contener *el contenido de inicialización*.</span><span class="sxs-lookup"><span data-stu-id="aa323-136">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="aa323-137">Tome nota de la dirección URL del sitio, la biblioteca y la carpeta.</span><span class="sxs-lookup"><span data-stu-id="aa323-137">Make note of the site, library, and folder url.</span></span>

> [!TIP]
> <span data-ttu-id="aa323-138">Si crea un sitio y una carpeta nuevos para los datos de inicialización, deje que se indexe al menos una hora para que esa ubicación se Indice antes de crear el clasificador que va a entrenar que usará esos datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="aa323-138">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="aa323-139">Inicie sesión en el centro de cumplimiento de Microsoft 365 con el administrador de cumplimiento o con el rol de administrador de seguridad y Abra **Microsoft 365 Compliance Center** o la clasificación de > **datos** del **centro de seguridad de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="aa323-139">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="aa323-140">Elija la pestaña **clasificadores** que se puede entrenar.</span><span class="sxs-lookup"><span data-stu-id="aa323-140">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="aa323-141">Elija **crear clasificador capacitado**.</span><span class="sxs-lookup"><span data-stu-id="aa323-141">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="aa323-142">Rellene los valores apropiados para `Name`los campos `Description` y de la categoría de los elementos que desea que identifique este clasificador capacitado.</span><span class="sxs-lookup"><span data-stu-id="aa323-142">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="aa323-143">Escriba la dirección URL del sitio de SharePoint Online, la biblioteca y la carpeta exactas para el sitio de contenido semilla del paso 2.</span><span class="sxs-lookup"><span data-stu-id="aa323-143">Enter the exact SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="aa323-144">Elija `Add`.</span><span class="sxs-lookup"><span data-stu-id="aa323-144">Choose `Add`.</span></span>

8. <span data-ttu-id="aa323-145">Revisa la configuración y elige `Create trainable classifier`.</span><span class="sxs-lookup"><span data-stu-id="aa323-145">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="aa323-146">En un plazo de 24 horas, el clasificador con formación procesará los datos de inicialización y creará un modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="aa323-146">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="aa323-147">El estado del clasificador es `In progress` mientras procesa los datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="aa323-147">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="aa323-148">Cuando el clasificador termina de procesar los datos de inicialización, el `Need test items`estado cambia a.</span><span class="sxs-lookup"><span data-stu-id="aa323-148">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="aa323-149">Ahora puede ver la página de detalles eligiendo el clasificador.</span><span class="sxs-lookup"><span data-stu-id="aa323-149">You can now view the details page by choosing the classifier.</span></span>


![clasificador entrenado preparado para pruebas](media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="aa323-151">Recopile al menos 200 elementos de contenido de prueba.</span><span class="sxs-lookup"><span data-stu-id="aa323-151">Collect at least 200 test content items.</span></span> <span data-ttu-id="aa323-152">Microsoft recomienda 10.000 para obtener los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="aa323-152">Microsoft recommends 10,000 for best results.</span></span> <span data-ttu-id="aa323-153">Debe tratarse de una mezcla de elementos que son fuertes positivos, negativos fuertes y algunos que son un poco menos obvios en su naturaleza.</span><span class="sxs-lookup"><span data-stu-id="aa323-153">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="aa323-154">Vea las [extensiones de nombre de archivo y los tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo compatibles.</span><span class="sxs-lookup"><span data-stu-id="aa323-154">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa323-155">Los elementos de ejemplo no deben estar cifrados y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="aa323-155">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="aa323-156">Colocar el contenido de prueba en una carpeta de SharePoint Online que esté dedicada a contener *el contenido de prueba únicamente*.</span><span class="sxs-lookup"><span data-stu-id="aa323-156">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="aa323-157">Anote la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="aa323-157">Make note of the SharePoint Online site, library and folder url.</span></span>

> [!TIP]
> <span data-ttu-id="aa323-158">Si crea un nuevo sitio y una carpeta para los datos de prueba, permita al menos una hora para indizar esa ubicación antes de crear el clasificador que va a formar parte de la información que usará esos datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="aa323-158">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="aa323-159">Elija `Add items to test`.</span><span class="sxs-lookup"><span data-stu-id="aa323-159">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="aa323-160">Escriba el sitio de SharePoint Online exacto, la biblioteca y la dirección URL de la carpeta para el sitio de contenido de prueba del paso 12.</span><span class="sxs-lookup"><span data-stu-id="aa323-160">Enter the exact SharePoint Online site, library and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="aa323-161">Elija `Add`.</span><span class="sxs-lookup"><span data-stu-id="aa323-161">Choose `Add`.</span></span>

15. <span data-ttu-id="aa323-162">Para finalizar el asistente, `Done`elija.</span><span class="sxs-lookup"><span data-stu-id="aa323-162">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="aa323-163">El clasificador que se pueda entrenar tardará hasta una hora en procesar los archivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="aa323-163">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="aa323-164">Cuando el clasificador que se pueda entrenar termine de procesar los archivos de prueba, el estado de la página `Ready to review`detalles cambiará a.</span><span class="sxs-lookup"><span data-stu-id="aa323-164">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="aa323-165">Si necesita aumentar el tamaño de la muestra de prueba, `Add items to test` elija y permita que el clasificador que se puede entrenar procese los elementos adicionales.</span><span class="sxs-lookup"><span data-stu-id="aa323-165">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![captura de pantalla de listo para revisar](media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="aa323-167">Elija `Tested items to review` Tab para revisar los elementos.</span><span class="sxs-lookup"><span data-stu-id="aa323-167">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="aa323-168">Microsoft 365 presentará 30 elementos a la vez.</span><span class="sxs-lookup"><span data-stu-id="aa323-168">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="aa323-169">Revise y, en el `We predict this item is "Relevant". Do you agree?` cuadro, `Yes` elija o `No` o `Not sure, skip to next item`.</span><span class="sxs-lookup"><span data-stu-id="aa323-169">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="aa323-170">La precisión del modelo se actualiza automáticamente después de cada 30 elementos.</span><span class="sxs-lookup"><span data-stu-id="aa323-170">Model accuracy is automatically updated after every 30 items.</span></span>

![cuadro revisar elementos](media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="aa323-172">Revise *al menos* 200 elementos.</span><span class="sxs-lookup"><span data-stu-id="aa323-172">Review *at least* 200 items.</span></span>

20. <span data-ttu-id="aa323-173">Continuar con la revisión hasta que la precisión alcance al menos el 70 `Publish the classifier` % y `Ready to use`el estado sea.</span><span class="sxs-lookup"><span data-stu-id="aa323-173">Continue to review until the accuracy reaches at least 70% and the `Publish the classifier` status is `Ready to use`.</span></span>

![precisión y lista para publicar](media/classifier-trainable-review-ready-to-publish.png)

21. <span data-ttu-id="aa323-175">Publique el clasificador.</span><span class="sxs-lookup"><span data-stu-id="aa323-175">Publish the classifier.</span></span>

22. <span data-ttu-id="aa323-176">Una vez publicado, el clasificador estará disponible como condición en la [Directiva aplicar automáticamente etiquetas de retención basada en una condición](labels.md#applying-a-retention-label-automatically-based-on-conditions) y en el cumplimiento de la [comunicación](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="aa323-176">Once published your classifier will be available as a condition in the [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and in [Communication compliance](communication-compliance.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="aa323-177">Una vez publicado un clasificador, no puede pasar por ningún entrenamiento adicional, así que asegúrese de que ha probado y revisado el mayor número de elementos posible para asegurarse de que la precisión sea lo más alta posible.</span><span class="sxs-lookup"><span data-stu-id="aa323-177">Once a classifier is published, it can't go through any additional training, so be very sure that you have tested and reviewed as many items as possible to ensure that the accuracy is as high as possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa323-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa323-178">See also</span></span>

- [<span data-ttu-id="aa323-179">Introducción al entrenamiento de clasificadores (vista previa)</span><span class="sxs-lookup"><span data-stu-id="aa323-179">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="aa323-180">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="aa323-180">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
