---
title: Introducción a los clasificadores que se capacitan
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Un clasificador de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo volver a entrenarlos para aumentar la precisión.
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752664"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="672fe-104">Introducción a los clasificadores que se capacitan</span><span class="sxs-lookup"><span data-stu-id="672fe-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="672fe-105">Un clasificador entrenado de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar.</span><span class="sxs-lookup"><span data-stu-id="672fe-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="672fe-106">Una vez preparado, puede usarlo para identificar el elemento para la aplicación de las etiquetas de confidencialidad de Office, las directivas de cumplimiento de comunicaciones y las directivas de etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="672fe-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="672fe-107">La creación de un clasificador personalizado personalizado en primer lugar implica dar a los ejemplos que se seleccionan y que cumplen de forma positiva la categoría.</span><span class="sxs-lookup"><span data-stu-id="672fe-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="672fe-108">A continuación, después de procesarlos, pruebe la capacidad de los clasificadores para predecir dándole una mezcla de muestras positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="672fe-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="672fe-109">En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo mejorar el rendimiento de los clasificadores capacitados personalizados y los clasificadores preparados previamente durante su ciclo de vida mediante la formación.</span><span class="sxs-lookup"><span data-stu-id="672fe-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="672fe-110">Para obtener más información acerca de los diferentes tipos de clasificadores, consulte [información sobre los clasificadores](classifier-learn-about.md)que se puedan entrenar.</span><span class="sxs-lookup"><span data-stu-id="672fe-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="672fe-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="672fe-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="672fe-112">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="672fe-112">Licensing requirements</span></span>

<span data-ttu-id="672fe-113">Los clasificadores son una característica de cumplimiento de Microsoft 365 E5 o E5.</span><span class="sxs-lookup"><span data-stu-id="672fe-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="672fe-114">Debe tener una de estas suscripciones para poder usarla.</span><span class="sxs-lookup"><span data-stu-id="672fe-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="672fe-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="672fe-115">Permissions</span></span>

<span data-ttu-id="672fe-116">Para acceder a los clasificadores en la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="672fe-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="672fe-117">el administrador global debe participar en el inquilino para crear clasificadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="672fe-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="672fe-118">El rol de administrador de cumplimiento es necesario para entrenar a un clasificador.</span><span class="sxs-lookup"><span data-stu-id="672fe-118">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="672fe-119">Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="672fe-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="672fe-120">Escenario de directiva de etiqueta de retención: funciones de administración de registros y retención</span><span class="sxs-lookup"><span data-stu-id="672fe-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="672fe-121">Escenario de directiva de etiqueta de confidencialidad: administrador de seguridad, administrador de cumplimiento, administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="672fe-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="672fe-122">Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión</span><span class="sxs-lookup"><span data-stu-id="672fe-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="672fe-123">De forma predeterminada, solo el usuario que crea un clasificador personalizado puede entrenar y revisar las predicciones realizadas por ese clasificador.</span><span class="sxs-lookup"><span data-stu-id="672fe-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="672fe-124">Preparar un clasificador personalizado para la formación</span><span class="sxs-lookup"><span data-stu-id="672fe-124">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="672fe-125">Es útil comprender lo que implica la creación de un clasificador que se puede personalizar de forma personalizada antes de profundizar.</span><span class="sxs-lookup"><span data-stu-id="672fe-125">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="672fe-126">Escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="672fe-126">Timeline</span></span>

<span data-ttu-id="672fe-127">Esta escala de tiempo refleja una implementación de ejemplo de clasificadores que se capacitan.</span><span class="sxs-lookup"><span data-stu-id="672fe-127">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-Classifier-Timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="672fe-129">La suscripción es necesaria la primera vez para los clasificadores que se deben entrenar.</span><span class="sxs-lookup"><span data-stu-id="672fe-129">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="672fe-130">Se necesitan doce días para Microsoft 365 para completar una evaluación de línea de base del contenido de su organización.</span><span class="sxs-lookup"><span data-stu-id="672fe-130">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="672fe-131">Póngase en contacto con el administrador global para que inicie el proceso de suscripción.</span><span class="sxs-lookup"><span data-stu-id="672fe-131">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="672fe-132">Flujo de trabajo general</span><span class="sxs-lookup"><span data-stu-id="672fe-132">Overall workflow</span></span>

<span data-ttu-id="672fe-133">Para obtener más información acerca del flujo de trabajo general sobre la creación de clasificadores que se puedan entrenar de forma personalizada, vea [flujo del proceso para crear clasificadores capacitados para clientes](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span><span class="sxs-lookup"><span data-stu-id="672fe-133">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="672fe-134">Contenido de inicialización</span><span class="sxs-lookup"><span data-stu-id="672fe-134">Seed content</span></span>

<span data-ttu-id="672fe-135">Cuando quiera que un clasificador capacitado identifique de forma independiente y precisa un elemento en una categoría de contenido concreta, primero tiene que presentarlo con muchos ejemplos del tipo de contenido que se encuentran en la categoría.</span><span class="sxs-lookup"><span data-stu-id="672fe-135">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="672fe-136">Esta alimentación de muestras al clasificador que se pueda entrenar se conoce como *inicialización*.</span><span class="sxs-lookup"><span data-stu-id="672fe-136">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="672fe-137">El contenido de inicialización se selecciona por un hombre y se juzga para representar la categoría de contenido.</span><span class="sxs-lookup"><span data-stu-id="672fe-137">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="672fe-138">Debe tener al menos 50 ejemplos positivos y hasta 500.</span><span class="sxs-lookup"><span data-stu-id="672fe-138">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="672fe-139">El clasificador que se pueda entrenar procesará hasta las muestras creadas más recientes de 500 (según la fecha de creación del archivo y la marca de tiempo).</span><span class="sxs-lookup"><span data-stu-id="672fe-139">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="672fe-140">Cuanto más ejemplos proporcione, más precisas serán las predicciones que realizará el clasificador.</span><span class="sxs-lookup"><span data-stu-id="672fe-140">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="672fe-141">Pruebas de contenido</span><span class="sxs-lookup"><span data-stu-id="672fe-141">Testing content</span></span>

<span data-ttu-id="672fe-142">Una vez que el clasificador que se puede entrenar haya procesado suficientes ejemplos positivos para crear un modelo de predicción, debe probar las predicciones que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los elementos que no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="672fe-142">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="672fe-143">Para ello, seleccione otro conjunto de contenido seleccionado humano que consista en muestras que deben incluirse en la categoría y en ejemplos que no lo hagan.</span><span class="sxs-lookup"><span data-stu-id="672fe-143">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="672fe-144">Debe probar con datos diferentes de los datos de inicialización iniciales que ha proporcionado por primera vez.</span><span class="sxs-lookup"><span data-stu-id="672fe-144">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="672fe-145">Una vez que los procese, revise manualmente los resultados y compruebe si cada predicción es correcta, incorrecta o no está seguro.</span><span class="sxs-lookup"><span data-stu-id="672fe-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="672fe-146">El clasificador capacitado usa estos comentarios para mejorar su modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="672fe-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="672fe-147">Para obtener los mejores resultados, tenga al menos 200 elementos en el conjunto de muestras de prueba con una distribución equitativa de las coincidencias negativas y positivas.</span><span class="sxs-lookup"><span data-stu-id="672fe-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="672fe-148">Cómo crear un clasificador que se pueda entrenar</span><span class="sxs-lookup"><span data-stu-id="672fe-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="672fe-149">Recopilar entre 50-500 elementos de contenido de inicialización.</span><span class="sxs-lookup"><span data-stu-id="672fe-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="672fe-150">Estos deben ser solo ejemplos que representen de forma segura el tipo de contenido que desea que el clasificador capacitado identifique como en la categoría de clasificación.</span><span class="sxs-lookup"><span data-stu-id="672fe-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="672fe-151">Vea las [extensiones de nombre de archivo y los tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo compatibles.</span><span class="sxs-lookup"><span data-stu-id="672fe-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="672fe-152">Los elementos de la muestra de inicialización y de prueba no deben cifrarse y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="672fe-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="672fe-153">Asegúrese de que los elementos del conjunto de SEED son ejemplos **fuertes** de la categoría.</span><span class="sxs-lookup"><span data-stu-id="672fe-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="672fe-154">El clasificador que se puede entrenar crea inicialmente su modelo en función de su inicialización.</span><span class="sxs-lookup"><span data-stu-id="672fe-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="672fe-155">El clasificador presupone que todas las muestras de inicialización son positivos y no tienen forma de saber si una muestra es una coincidencia débil o negativa con la categoría.</span><span class="sxs-lookup"><span data-stu-id="672fe-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="672fe-156">Colocar el contenido de inicialización en una carpeta de SharePoint Online que esté dedicada exclusivamente a contener *el contenido de inicialización*.</span><span class="sxs-lookup"><span data-stu-id="672fe-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="672fe-157">Tome nota de la dirección URL del sitio, la biblioteca y la carpeta.</span><span class="sxs-lookup"><span data-stu-id="672fe-157">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="672fe-158">Si crea un sitio y una carpeta nuevos para los datos de inicialización, deje que se indexe al menos una hora para que esa ubicación se Indice antes de crear el clasificador que va a entrenar que usará esos datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="672fe-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="672fe-159">Inicie sesión en el centro de cumplimiento de Microsoft 365 con el administrador de cumplimiento o con el rol de administrador de seguridad y abra el **centro de cumplimiento** de Microsoft 365 o la clasificación de datos del **centro de seguridad de Microsoft 365**  >  .</span><span class="sxs-lookup"><span data-stu-id="672fe-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="672fe-160">Elija la pestaña **clasificadores** que se puede entrenar.</span><span class="sxs-lookup"><span data-stu-id="672fe-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="672fe-161">Elija **crear clasificador capacitado**.</span><span class="sxs-lookup"><span data-stu-id="672fe-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="672fe-162">Rellene los valores apropiados para `Name` los `Description` campos y de la categoría de elementos que desea que identifique este clasificado que se puede entrenar.</span><span class="sxs-lookup"><span data-stu-id="672fe-162">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="672fe-163">Seleccione el sitio de SharePoint Online, la biblioteca y la dirección URL de la carpeta para el sitio de contenido semilla del paso 2.</span><span class="sxs-lookup"><span data-stu-id="672fe-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="672fe-164">Elija `Add` .</span><span class="sxs-lookup"><span data-stu-id="672fe-164">Choose `Add`.</span></span>

8. <span data-ttu-id="672fe-165">Revisa la configuración y elige `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="672fe-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="672fe-166">En un plazo de 24 horas, el clasificador con formación procesará los datos de inicialización y creará un modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="672fe-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="672fe-167">El estado del clasificador es `In progress` mientras procesa los datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="672fe-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="672fe-168">Cuando el clasificador termina de procesar los datos de inicialización, el estado cambia a `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="672fe-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="672fe-169">Ahora puede ver la página de detalles eligiendo el clasificador.</span><span class="sxs-lookup"><span data-stu-id="672fe-169">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="672fe-170">![clasificador entrenado preparado para pruebas](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="672fe-170">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="672fe-171">Recopile al menos 200 elementos de contenido de prueba (10.000 máx.) para obtener los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="672fe-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="672fe-172">Debe tratarse de una mezcla de elementos que son fuertes positivos, negativos fuertes y algunos que son un poco menos obvios en su naturaleza.</span><span class="sxs-lookup"><span data-stu-id="672fe-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="672fe-173">Vea las [extensiones de nombre de archivo y los tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo compatibles.</span><span class="sxs-lookup"><span data-stu-id="672fe-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="672fe-174">Los elementos de ejemplo no deben estar cifrados y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="672fe-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="672fe-175">Colocar el contenido de prueba en una carpeta de SharePoint Online que esté dedicada a contener *el contenido de prueba únicamente*.</span><span class="sxs-lookup"><span data-stu-id="672fe-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="672fe-176">Anote la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="672fe-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="672fe-177">Si crea un nuevo sitio y una carpeta para los datos de prueba, permita al menos una hora para indizar esa ubicación antes de crear el clasificador que va a formar parte de la información que usará esos datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="672fe-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="672fe-178">Elija `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="672fe-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="672fe-179">Seleccione el sitio de SharePoint Online, la biblioteca y la dirección URL de la carpeta para el sitio de contenido de prueba del paso 12.</span><span class="sxs-lookup"><span data-stu-id="672fe-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="672fe-180">Elija `Add` .</span><span class="sxs-lookup"><span data-stu-id="672fe-180">Choose `Add`.</span></span>

15. <span data-ttu-id="672fe-181">Para finalizar el asistente, elija `Done` .</span><span class="sxs-lookup"><span data-stu-id="672fe-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="672fe-182">El clasificador que se pueda entrenar tardará hasta una hora en procesar los archivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="672fe-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="672fe-183">Cuando el clasificador que se pueda entrenar termine de procesar los archivos de prueba, el estado de la página Detalles cambiará a `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="672fe-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="672fe-184">Si necesita aumentar el tamaño de la muestra de prueba, elija `Add items to test` y permita que el clasificador que se puede entrenar procese los elementos adicionales.</span><span class="sxs-lookup"><span data-stu-id="672fe-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="672fe-185">![captura de pantalla de listo para revisar](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="672fe-185">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="672fe-186">Elija `Tested items to review` Tab para revisar los elementos.</span><span class="sxs-lookup"><span data-stu-id="672fe-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="672fe-187">Microsoft 365 presentará 30 elementos a la vez.</span><span class="sxs-lookup"><span data-stu-id="672fe-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="672fe-188">Revise y, en el `We predict this item is "Relevant". Do you agree?` cuadro, elija `Yes` o `No` o `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="672fe-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="672fe-189">La precisión del modelo se actualiza automáticamente después de cada 30 elementos.</span><span class="sxs-lookup"><span data-stu-id="672fe-189">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="672fe-190">![cuadro revisar elementos](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="672fe-190">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="672fe-191">Revise *al menos* 200 elementos.</span><span class="sxs-lookup"><span data-stu-id="672fe-191">Review *at least* 200 items.</span></span> <span data-ttu-id="672fe-192">Una vez que la puntuación de precisión se ha estabilizado, la opción **publicar** estará disponible y el estado del clasificador se dirá `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="672fe-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="672fe-193">![puntuación de precisión y lista para publicar](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="672fe-193">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="672fe-194">Publique el clasificador.</span><span class="sxs-lookup"><span data-stu-id="672fe-194">Publish the classifier.</span></span>

21. <span data-ttu-id="672fe-195">Una vez publicado el clasificador estará disponible como condición en el [etiquetado automático de Office con etiquetas de confidencialidad](apply-sensitivity-label-automatically.md), [aplicar automáticamente una directiva de etiqueta de retención basada en una condición](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) y en el cumplimiento de la [comunicación](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="672fe-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
