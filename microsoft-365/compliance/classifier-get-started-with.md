---
title: Introducción a los clasificadores que se pueden entrenar
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
description: Un clasificador de Microsoft 365 es una herramienta que puede entrenar para reconocer varios tipos de contenido, ya que le proporciona ejemplos para que los vea. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo volver a entrenarlos para aumentar la precisión.
ms.openlocfilehash: a73acd7665cd23f13329bb5db4e890b0f3b0d861
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423299"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="b9593-104">Introducción a los clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="b9593-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="b9593-105">Un clasificador entrenable de Microsoft 365 es una herramienta que puede entrenar para reconocer varios tipos de contenido, ya que le proporciona ejemplos para que los vea.</span><span class="sxs-lookup"><span data-stu-id="b9593-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="b9593-106">Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="b9593-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="b9593-107">Crear un clasificador personalizado para entrenar primero implica darle muestras que son humanas seleccionada y coinciden positivamente con la categoría.</span><span class="sxs-lookup"><span data-stu-id="b9593-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="b9593-108">A continuación, después de procesarlos, se prueba la capacidad de los clasificadores para predecir al darle una combinación de muestras positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="b9593-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="b9593-109">En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo mejorar el rendimiento de clasificadores personalizados y clasificadores previamente formados a lo largo de su vida a través de la readaptación.</span><span class="sxs-lookup"><span data-stu-id="b9593-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="b9593-110">Para obtener más información sobre los diferentes tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="b9593-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="b9593-111">Vea este vídeo para ver un resumen rápido de la creación de un clasificador que se puede entrenar.</span><span class="sxs-lookup"><span data-stu-id="b9593-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="b9593-112">Todavía tendrá que leer este artículo completo para obtener los detalles.</span><span class="sxs-lookup"><span data-stu-id="b9593-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="b9593-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b9593-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="b9593-114">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="b9593-114">Licensing requirements</span></span>

<span data-ttu-id="b9593-115">Los clasificadores son una característica de cumplimiento de Microsoft 365 E5 o E5.</span><span class="sxs-lookup"><span data-stu-id="b9593-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="b9593-116">Debe tener una de estas suscripciones para poder usarlas.</span><span class="sxs-lookup"><span data-stu-id="b9593-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="b9593-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="b9593-117">Permissions</span></span>

<span data-ttu-id="b9593-118">Para obtener acceso a clasificadores en la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="b9593-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="b9593-119">El administrador global debe participar para que el inquilino cree clasificadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="b9593-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="b9593-120">El rol Administrador de cumplimiento es necesario para entrenar a un clasificador.</span><span class="sxs-lookup"><span data-stu-id="b9593-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="b9593-121">Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="b9593-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="b9593-122">Escenario de directiva de etiqueta de retención: roles de administración de registros y administración de retención</span><span class="sxs-lookup"><span data-stu-id="b9593-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="b9593-123">Escenario de directiva de etiqueta de confidencialidad: Administrador de seguridad, Administrador de cumplimiento, Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b9593-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="b9593-124">Escenario de directiva de cumplimiento de comunicaciones: Administrador de administración de riesgos de Insider, Administrador de revisión de supervisión</span><span class="sxs-lookup"><span data-stu-id="b9593-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b9593-125">De forma predeterminada, solo el usuario que crea un clasificador personalizado puede entrenar y revisar las previsiones realizadas por ese clasificador.</span><span class="sxs-lookup"><span data-stu-id="b9593-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="b9593-126">Prepararse para un clasificador personalizado que se puede entrenar</span><span class="sxs-lookup"><span data-stu-id="b9593-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="b9593-127">Es útil comprender lo que implica la creación de un clasificador personalizado para entrenar antes de profundizar.</span><span class="sxs-lookup"><span data-stu-id="b9593-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="b9593-128">Escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="b9593-128">Timeline</span></span>

<span data-ttu-id="b9593-129">Esta escala de tiempo refleja una implementación de ejemplo de clasificadores entrenables.</span><span class="sxs-lookup"><span data-stu-id="b9593-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="b9593-131">El opt-in es necesario la primera vez para clasificadores que se pueden entrenar.</span><span class="sxs-lookup"><span data-stu-id="b9593-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="b9593-132">Microsoft 365 tarda doce días en completar una evaluación de línea base del contenido de la organización.</span><span class="sxs-lookup"><span data-stu-id="b9593-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="b9593-133">Póngase en contacto con el administrador global para iniciar el proceso de suscripción.</span><span class="sxs-lookup"><span data-stu-id="b9593-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="b9593-134">Flujo de trabajo general</span><span class="sxs-lookup"><span data-stu-id="b9593-134">Overall workflow</span></span>

<span data-ttu-id="b9593-135">Para obtener más información sobre el flujo de trabajo general de creación de clasificadores personalizados, vea [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span><span class="sxs-lookup"><span data-stu-id="b9593-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="b9593-136">Contenido de la ed.</span><span class="sxs-lookup"><span data-stu-id="b9593-136">Seed content</span></span>

<span data-ttu-id="b9593-137">Cuando desea que un clasificador entrenable identifique de forma independiente y precisa un elemento como una categoría concreta de contenido, primero debe presentarlo con muchas muestras del tipo de contenido que hay en la categoría.</span><span class="sxs-lookup"><span data-stu-id="b9593-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="b9593-138">Esta alimentación de muestras al clasificador que se puede entrenar se conoce como *edificación*.</span><span class="sxs-lookup"><span data-stu-id="b9593-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="b9593-139">Un humano selecciona el contenido de la seed y se considera que representa la categoría de contenido.</span><span class="sxs-lookup"><span data-stu-id="b9593-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="b9593-140">Debe tener al menos 50 muestras positivas y hasta 500.</span><span class="sxs-lookup"><span data-stu-id="b9593-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="b9593-141">El clasificador que se puede entrenar procesará hasta los 500 ejemplos creados más recientes (por marca de fecha y hora creada por archivo).</span><span class="sxs-lookup"><span data-stu-id="b9593-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="b9593-142">Entre más muestras proporciones, más precisas serán las previsiones que realizará el clasificador.</span><span class="sxs-lookup"><span data-stu-id="b9593-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="b9593-143">Probar contenido</span><span class="sxs-lookup"><span data-stu-id="b9593-143">Testing content</span></span>

<span data-ttu-id="b9593-144">Una vez que el clasificador capacitado haya procesado suficientes ejemplos positivos para crear un modelo de predicción, debe probar las previsiones que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los elementos que no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="b9593-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="b9593-145">Para ello, selecciona otro conjunto de contenido seleccionado por humanos, que se espera que sea más grande, que consta de muestras que deben incluirse en la categoría y muestras que no lo hagan.</span><span class="sxs-lookup"><span data-stu-id="b9593-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="b9593-146">Debe probar con datos diferentes a los datos iniciales de inicialización que proporcionó por primera vez.</span><span class="sxs-lookup"><span data-stu-id="b9593-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="b9593-147">Una vez que los procesa, se pasan manualmente por los resultados y se comprueba si cada predicción es correcta, incorrecta o no está seguro.</span><span class="sxs-lookup"><span data-stu-id="b9593-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="b9593-148">El clasificador que puede entrenar usa estos comentarios para mejorar su modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="b9593-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="b9593-149">Para obtener mejores resultados, tenga al menos 200 elementos en el conjunto de muestras de prueba con una distribución uniforme de coincidencias positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="b9593-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="b9593-150">Cómo crear un clasificador que se puede entrenar</span><span class="sxs-lookup"><span data-stu-id="b9593-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="b9593-151">Recopilar entre 50 y 500 elementos de contenido de ed.</span><span class="sxs-lookup"><span data-stu-id="b9593-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="b9593-152">Estos deben ser solo ejemplos que representen fuertemente el tipo de contenido que desea que el clasificador capacitado identifique positivamente como en la categoría de clasificación.</span><span class="sxs-lookup"><span data-stu-id="b9593-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="b9593-153">Consulte Extensiones de nombre de archivo rastreadas predeterminadas y tipos de archivo analizadas en [SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo admitidos.</span><span class="sxs-lookup"><span data-stu-id="b9593-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b9593-154">Los elementos de ejemplo de seed y test no deben cifrarse y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="b9593-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b9593-155">Asegúrese de que los elementos del conjunto de posiciones **son ejemplos** sólidos de la categoría.</span><span class="sxs-lookup"><span data-stu-id="b9593-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="b9593-156">El clasificador que se puede entrenar crea inicialmente su modelo en función de con qué lo edificó.</span><span class="sxs-lookup"><span data-stu-id="b9593-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="b9593-157">El clasificador asume que todas las muestras de ed.0 son positivos fuertes y no tiene forma de saber si una muestra es una coincidencia débil o negativa con la categoría.</span><span class="sxs-lookup"><span data-stu-id="b9593-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="b9593-158">Coloque el contenido de la ed.ed en una carpeta de SharePoint Online dedicada a mantener *el contenido de ed.*</span><span class="sxs-lookup"><span data-stu-id="b9593-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="b9593-159">Anote la dirección URL del sitio, la biblioteca y la carpeta.</span><span class="sxs-lookup"><span data-stu-id="b9593-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="b9593-160">Si crea un nuevo sitio y una carpeta para los datos de edificadores, permita al menos una hora para que esa ubicación se indexe antes de crear el clasificador que se puede entrenar que usará los datos de ed.</span><span class="sxs-lookup"><span data-stu-id="b9593-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="b9593-161">Inicie sesión en el Centro de cumplimiento de Microsoft 365 con acceso al rol de administrador de seguridad o administrador de cumplimiento y abra el Centro de cumplimiento de **Microsoft 365** o la clasificación de datos del centro de seguridad de **Microsoft 365.**  >  </span><span class="sxs-lookup"><span data-stu-id="b9593-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="b9593-162">Elija la **pestaña Clasificadores que se pueden entrenar.**</span><span class="sxs-lookup"><span data-stu-id="b9593-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="b9593-163">Elija **Create trainable classifier**.</span><span class="sxs-lookup"><span data-stu-id="b9593-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="b9593-164">Rellene los valores adecuados para los campos y de la categoría de elementos que desea que identifique este `Name` `Description` clasificador entrenable.</span><span class="sxs-lookup"><span data-stu-id="b9593-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="b9593-165">Elija la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online para el sitio de contenido de ed. del paso 2.</span><span class="sxs-lookup"><span data-stu-id="b9593-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="b9593-166">Elija `Add` .</span><span class="sxs-lookup"><span data-stu-id="b9593-166">Choose `Add`.</span></span>

8. <span data-ttu-id="b9593-167">Revise la configuración y elija `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="b9593-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="b9593-168">En un plazo de 24 horas, el clasificador que se puede entrenar procesará los datos de ed. y compilará un modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="b9593-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="b9593-169">El estado del clasificador `In progress` es mientras procesa los datos de ed.</span><span class="sxs-lookup"><span data-stu-id="b9593-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="b9593-170">Cuando el clasificador termina de procesar los datos de ed. `Need test items`</span><span class="sxs-lookup"><span data-stu-id="b9593-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="b9593-171">Ahora puede ver la página de detalles eligiendo el clasificador.</span><span class="sxs-lookup"><span data-stu-id="b9593-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9593-172">![clasificador trainable listo para pruebas](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="b9593-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="b9593-173">Recopile al menos 200 elementos de contenido de prueba (10 000 como máximo) para obtener mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="b9593-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="b9593-174">Estos deben ser una combinación de elementos que son positivos fuertes, negativos fuertes y algunos que son un poco menos obvios en su naturaleza.</span><span class="sxs-lookup"><span data-stu-id="b9593-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="b9593-175">Consulte Extensiones de nombre de archivo rastreadas predeterminadas y tipos de archivo analizadas en [SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo admitidos.</span><span class="sxs-lookup"><span data-stu-id="b9593-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b9593-176">Los elementos de ejemplo no deben cifrarse y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="b9593-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="b9593-177">Coloque el contenido de prueba en una carpeta de SharePoint Online dedicada únicamente a contener *el contenido de prueba.*</span><span class="sxs-lookup"><span data-stu-id="b9593-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="b9593-178">Anote la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b9593-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="b9593-179">Si crea un nuevo sitio y una carpeta para los datos de prueba, permita al menos una hora para que esa ubicación se indexe antes de crear el clasificador que se puede entrenar que usará los datos de ed.</span><span class="sxs-lookup"><span data-stu-id="b9593-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="b9593-180">Elija `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="b9593-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="b9593-181">Seleccione la dirección URL del sitio, biblioteca y carpeta de SharePoint Online para el sitio de contenido de prueba del paso 12.</span><span class="sxs-lookup"><span data-stu-id="b9593-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="b9593-182">Elija `Add` .</span><span class="sxs-lookup"><span data-stu-id="b9593-182">Choose `Add`.</span></span>

15. <span data-ttu-id="b9593-183">Para finalizar el asistente, elija `Done` .</span><span class="sxs-lookup"><span data-stu-id="b9593-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="b9593-184">El clasificador que se puede entrenar llevará hasta una hora procesar los archivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="b9593-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="b9593-185">Cuando el clasificador capacitado termine de procesar los archivos de prueba, el estado de la página de detalles cambiará a `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="b9593-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="b9593-186">Si necesita aumentar el tamaño de la muestra de prueba, elija y permita que el clasificador capacitado `Add items to test` procese los elementos adicionales.</span><span class="sxs-lookup"><span data-stu-id="b9593-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9593-187">![listo para revisar la captura de pantalla](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="b9593-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="b9593-188">Elija `Tested items to review` la pestaña para revisar los elementos.</span><span class="sxs-lookup"><span data-stu-id="b9593-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="b9593-189">Microsoft 365 presentará 30 elementos a la vez.</span><span class="sxs-lookup"><span data-stu-id="b9593-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="b9593-190">Repase y, en `We predict this item is "Relevant". Do you agree?` el cuadro, `Yes` elija o `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="b9593-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="b9593-191">La precisión del modelo se actualiza automáticamente después de cada 30 elementos.</span><span class="sxs-lookup"><span data-stu-id="b9593-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9593-192">![cuadro revisar elementos](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="b9593-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="b9593-193">Revise *al menos* 200 elementos.</span><span class="sxs-lookup"><span data-stu-id="b9593-193">Review *at least* 200 items.</span></span> <span data-ttu-id="b9593-194">Una vez estabilizada la puntuación de precisión, la **opción de** publicación estará disponible y el estado del clasificador dirá `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="b9593-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9593-195">![puntuación de precisión y lista para publicar](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="b9593-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="b9593-196">Publique el clasificador.</span><span class="sxs-lookup"><span data-stu-id="b9593-196">Publish the classifier.</span></span>

21. <span data-ttu-id="b9593-197">Una vez publicado, el clasificador estará disponible como una condición en el etiquetado automático de [Office](apply-sensitivity-label-automatically.md)con etiquetas de confidencialidad, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automáticamente la directiva de etiquetas de retención según una condición y en Cumplimiento de [comunicaciones.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="b9593-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
