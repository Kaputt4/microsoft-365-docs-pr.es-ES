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
description: Un clasificador de Microsoft 365 es una herramienta que puede entrenar para reconocer distintos tipos de contenido, ya que le proporciona ejemplos para que los vea. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo volver a entrenarlo para aumentar la precisión.
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752664"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="92ec0-104">Introducción a los clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="92ec0-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="92ec0-105">Un clasificador que se puede entrenar de Microsoft 365 es una herramienta que puede entrenar para reconocer distintos tipos de contenido, ya que le proporciona ejemplos para que los vea.</span><span class="sxs-lookup"><span data-stu-id="92ec0-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="92ec0-106">Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="92ec0-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="92ec0-107">La creación de un clasificador personalizado que se puede entrenar primero implica darle muestras que son de selección humana y que coinciden positivamente con la categoría.</span><span class="sxs-lookup"><span data-stu-id="92ec0-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="92ec0-108">A continuación, después de procesarlos, se prueba la capacidad de los clasificadores para predecir al darle una combinación de muestras positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="92ec0-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="92ec0-109">En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo mejorar el rendimiento de clasificadores y clasificadores formados previamente a lo largo de su ciclo de vida a través de la nueva formación.</span><span class="sxs-lookup"><span data-stu-id="92ec0-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="92ec0-110">Para obtener más información acerca de los distintos tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="92ec0-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92ec0-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="92ec0-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="92ec0-112">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="92ec0-112">Licensing requirements</span></span>

<span data-ttu-id="92ec0-113">Los clasificadores son una característica de cumplimiento de Microsoft 365 E5 o E5.</span><span class="sxs-lookup"><span data-stu-id="92ec0-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="92ec0-114">Debe tener una de estas suscripciones para poder usarlas.</span><span class="sxs-lookup"><span data-stu-id="92ec0-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="92ec0-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="92ec0-115">Permissions</span></span>

<span data-ttu-id="92ec0-116">Para obtener acceso a clasificadores en la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="92ec0-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="92ec0-117">El administrador global debe participar para que el inquilino cree clasificadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="92ec0-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="92ec0-118">El rol de administrador de cumplimiento es necesario para formar a un clasificador.</span><span class="sxs-lookup"><span data-stu-id="92ec0-118">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="92ec0-119">Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="92ec0-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="92ec0-120">Escenario de directiva de etiquetas de retención: roles administración de registros y administración de retención</span><span class="sxs-lookup"><span data-stu-id="92ec0-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="92ec0-121">Escenario de directiva de etiqueta de confidencialidad: Administrador de seguridad, Administrador de cumplimiento, Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="92ec0-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="92ec0-122">Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión</span><span class="sxs-lookup"><span data-stu-id="92ec0-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="92ec0-123">De forma predeterminada, solo el usuario que crea un clasificador personalizado puede entrenar y revisar las predicción realizadas por ese clasificador.</span><span class="sxs-lookup"><span data-stu-id="92ec0-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="92ec0-124">Prepararse para un clasificador personalizado que se puede entrenar</span><span class="sxs-lookup"><span data-stu-id="92ec0-124">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="92ec0-125">Es útil comprender lo que implica la creación de un clasificador personalizado que se puede entrenar antes de profundizar.</span><span class="sxs-lookup"><span data-stu-id="92ec0-125">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="92ec0-126">Escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="92ec0-126">Timeline</span></span>

<span data-ttu-id="92ec0-127">Esta escala de tiempo refleja una implementación de ejemplo de clasificadores que se pueden entrenar.</span><span class="sxs-lookup"><span data-stu-id="92ec0-127">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="92ec0-129">Es necesario participar por primera vez para clasificadores que se pueden entrenar.</span><span class="sxs-lookup"><span data-stu-id="92ec0-129">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="92ec0-130">Microsoft 365 tarda doce días en completar una evaluación de línea base del contenido de la organización.</span><span class="sxs-lookup"><span data-stu-id="92ec0-130">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="92ec0-131">Póngase en contacto con el administrador global para iniciar el proceso de suscripción.</span><span class="sxs-lookup"><span data-stu-id="92ec0-131">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="92ec0-132">Flujo de trabajo general</span><span class="sxs-lookup"><span data-stu-id="92ec0-132">Overall workflow</span></span>

<span data-ttu-id="92ec0-133">Para obtener más información sobre el flujo de trabajo general de creación de clasificadores que se pueden entrenar personalizados, vea Flujo de procesos para crear clasificadores que se pueden entrenar [para el cliente.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="92ec0-133">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="92ec0-134">Contenido de la ed.</span><span class="sxs-lookup"><span data-stu-id="92ec0-134">Seed content</span></span>

<span data-ttu-id="92ec0-135">Si desea que un clasificador que se pueda entrenar identifique de forma independiente y precisa un elemento como parte de una categoría concreta de contenido, primero debe presentarlo con muchos ejemplos del tipo de contenido que se encuentran en la categoría.</span><span class="sxs-lookup"><span data-stu-id="92ec0-135">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="92ec0-136">Esta alimentación de muestras al clasificador que se puede entrenar se conoce como *edificador.*</span><span class="sxs-lookup"><span data-stu-id="92ec0-136">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="92ec0-137">Un ser humano selecciona el contenido de la edr., que representa la categoría de contenido.</span><span class="sxs-lookup"><span data-stu-id="92ec0-137">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="92ec0-138">Debe tener al menos 50 muestras positivas y hasta 500.</span><span class="sxs-lookup"><span data-stu-id="92ec0-138">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="92ec0-139">El clasificador que se puede entrenar procesará hasta las 500 muestras creadas más recientes (por marca de fecha y hora de creación de archivos).</span><span class="sxs-lookup"><span data-stu-id="92ec0-139">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="92ec0-140">Cuando más muestras proporciones, más precisas serán las predicción que realizará el clasificador.</span><span class="sxs-lookup"><span data-stu-id="92ec0-140">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="92ec0-141">Prueba de contenido</span><span class="sxs-lookup"><span data-stu-id="92ec0-141">Testing content</span></span>

<span data-ttu-id="92ec0-142">Una vez que el clasificador que se puede entrenar ha procesado suficientes muestras positivas para crear un modelo de predicción, debes probar las predicción que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los elementos que no.</span><span class="sxs-lookup"><span data-stu-id="92ec0-142">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="92ec0-143">Para ello, selecciona otro conjunto de contenido seleccionado humano, con suerte más grande, que consta de muestras que deben incluirse en la categoría y las muestras que no.</span><span class="sxs-lookup"><span data-stu-id="92ec0-143">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="92ec0-144">Debes probar con datos diferentes de los datos iniciales de inicialización que proporcionaste por primera vez.</span><span class="sxs-lookup"><span data-stu-id="92ec0-144">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="92ec0-145">Una vez que los procesa, se pasan manualmente por los resultados y se comprueba si cada predicción es correcta, incorrecta o no está seguro.</span><span class="sxs-lookup"><span data-stu-id="92ec0-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="92ec0-146">El clasificador que se puede entrenar usa estos comentarios para mejorar su modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="92ec0-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="92ec0-147">Para obtener mejores resultados, tenga al menos 200 elementos en el conjunto de muestras de prueba con una distribución uniforme de coincidencias positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="92ec0-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="92ec0-148">Cómo crear un clasificador que se puede entrenar</span><span class="sxs-lookup"><span data-stu-id="92ec0-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="92ec0-149">Recopile entre 50 y 500 elementos de contenido de ed.</span><span class="sxs-lookup"><span data-stu-id="92ec0-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="92ec0-150">Solo deben ser ejemplos que representen de forma segura el tipo de contenido que desea que el clasificador que se pueda entrenar identifique de forma positiva como si se encontrara en la categoría de clasificación.</span><span class="sxs-lookup"><span data-stu-id="92ec0-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="92ec0-151">Vea las extensiones de nombre de archivo rastreadas predeterminadas y los tipos de archivo analizadas [en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo admitidos.</span><span class="sxs-lookup"><span data-stu-id="92ec0-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="92ec0-152">Los elementos de ejemplo de la ed y la prueba no deben estar cifrados y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="92ec0-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="92ec0-153">Asegúrate de que los elementos del conjunto de elementos de la edr. sean **ejemplos seguros** de la categoría.</span><span class="sxs-lookup"><span data-stu-id="92ec0-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="92ec0-154">Inicialmente, el clasificador que se puede entrenar crea su modelo en función de lo que se inicializa.</span><span class="sxs-lookup"><span data-stu-id="92ec0-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="92ec0-155">El clasificador presupone que todas las muestras de la edar son positivos y no tiene forma de saber si una muestra es una coincidencia débil o negativa con la categoría.</span><span class="sxs-lookup"><span data-stu-id="92ec0-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="92ec0-156">Coloque el contenido de la edr. en una carpeta de SharePoint Online dedicada a contener *solo el contenido de la edr.*</span><span class="sxs-lookup"><span data-stu-id="92ec0-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="92ec0-157">Tome nota de la dirección URL del sitio, la biblioteca y la carpeta.</span><span class="sxs-lookup"><span data-stu-id="92ec0-157">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="92ec0-158">Si crea un nuevo sitio y una carpeta para los datos de edr, permita al menos una hora para que esa ubicación se indexe antes de crear el clasificador que se puede entrenar que usará los datos de edr.</span><span class="sxs-lookup"><span data-stu-id="92ec0-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="92ec0-159">Inicie sesión en el Centro de cumplimiento de Microsoft 365 con acceso al rol de administrador de seguridad o administrador de cumplimiento y abra el Centro de cumplimiento de **Microsoft 365** o la clasificación de datos del Centro de seguridad de **Microsoft 365.**  >  </span><span class="sxs-lookup"><span data-stu-id="92ec0-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="92ec0-160">Elija la **pestaña Clasificadores que se pueden entrenar.**</span><span class="sxs-lookup"><span data-stu-id="92ec0-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="92ec0-161">Elija **Crear clasificador que se pueda entrenar.**</span><span class="sxs-lookup"><span data-stu-id="92ec0-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="92ec0-162">Rellene los valores adecuados para los campos y los campos de la categoría de elementos que desea que identifique `Name` `Description` este clasificador que se puede entrenar.</span><span class="sxs-lookup"><span data-stu-id="92ec0-162">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="92ec0-163">Elija la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online para el sitio de contenido de edr del paso 2.</span><span class="sxs-lookup"><span data-stu-id="92ec0-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="92ec0-164">Elija `Add` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-164">Choose `Add`.</span></span>

8. <span data-ttu-id="92ec0-165">Revise la configuración y elija `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="92ec0-166">En un plazo de 24 horas, el clasificador que se puede entrenar procesará los datos de la edr. y compilará un modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="92ec0-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="92ec0-167">El estado del clasificador es `In progress` mientras procesa los datos de la ed.</span><span class="sxs-lookup"><span data-stu-id="92ec0-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="92ec0-168">Cuando el clasificador termina de procesar los datos de la edr, el estado cambia a `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="92ec0-169">Ahora puede ver la página de detalles eligiendo el clasificador.</span><span class="sxs-lookup"><span data-stu-id="92ec0-169">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="92ec0-170">![clasificador que se puede entrenar listo para pruebas](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="92ec0-170">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="92ec0-171">Recopile al menos 200 elementos de contenido de prueba (10 000 como máximo) para obtener los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="92ec0-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="92ec0-172">Estos deben ser una combinación de elementos que son positivos, negativos fuertes y algunos que son un poco menos obvios en su naturaleza.</span><span class="sxs-lookup"><span data-stu-id="92ec0-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="92ec0-173">Vea las extensiones de nombre de archivo rastreadas predeterminadas y los tipos de archivo analizadas [en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo admitidos.</span><span class="sxs-lookup"><span data-stu-id="92ec0-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="92ec0-174">Los elementos de ejemplo no deben estar cifrados y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="92ec0-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="92ec0-175">Coloque el contenido de prueba en una carpeta de SharePoint Online dedicada a contener *solo el contenido de prueba.*</span><span class="sxs-lookup"><span data-stu-id="92ec0-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="92ec0-176">Tome nota de la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="92ec0-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="92ec0-177">Si crea un nuevo sitio y una carpeta para los datos de prueba, deje al menos una hora para que esa ubicación se indexe antes de crear el clasificador que se puede entrenar que usará los datos de edr.</span><span class="sxs-lookup"><span data-stu-id="92ec0-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="92ec0-178">Elija `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="92ec0-179">Elija la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online para el sitio de contenido de prueba del paso 12.</span><span class="sxs-lookup"><span data-stu-id="92ec0-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="92ec0-180">Elija `Add` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-180">Choose `Add`.</span></span>

15. <span data-ttu-id="92ec0-181">Para finalizar el asistente, elija `Done` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="92ec0-182">El clasificador que se puede entrenar llevará hasta una hora procesar los archivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="92ec0-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="92ec0-183">Cuando el clasificador que se puede entrenar termine de procesar los archivos de prueba, el estado de la página de detalles cambiará a `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="92ec0-184">Si necesitas aumentar el tamaño de la muestra de prueba, elige y permite que el clasificador que se puede `Add items to test` entrenar procese los elementos adicionales.</span><span class="sxs-lookup"><span data-stu-id="92ec0-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="92ec0-185">![captura de pantalla lista para revisar](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="92ec0-185">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="92ec0-186">Elija `Tested items to review` la pestaña para revisar los elementos.</span><span class="sxs-lookup"><span data-stu-id="92ec0-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="92ec0-187">Microsoft 365 presentará 30 elementos a la vez.</span><span class="sxs-lookup"><span data-stu-id="92ec0-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="92ec0-188">Repase y, `We predict this item is "Relevant". Do you agree?` en el cuadro, elija `Yes` uno `No` o `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="92ec0-189">La precisión del modelo se actualiza automáticamente después de cada 30 elementos.</span><span class="sxs-lookup"><span data-stu-id="92ec0-189">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="92ec0-190">![cuadro de elementos de revisión](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="92ec0-190">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="92ec0-191">Revise *al menos* 200 elementos.</span><span class="sxs-lookup"><span data-stu-id="92ec0-191">Review *at least* 200 items.</span></span> <span data-ttu-id="92ec0-192">Una vez que se ha estabilizado la puntuación de precisión, la opción **de** publicación estará disponible y el estado del clasificador dirá `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="92ec0-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="92ec0-193">![puntuación de precisión y listo para publicar](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="92ec0-193">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="92ec0-194">Publique el clasificador.</span><span class="sxs-lookup"><span data-stu-id="92ec0-194">Publish the classifier.</span></span>

21. <span data-ttu-id="92ec0-195">Una vez publicado, el clasificador estará disponible como una condición en el etiquetado automático de [Office](apply-sensitivity-label-automatically.md)con etiquetas de confidencialidad, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automáticamente la directiva de etiqueta de retención en función de una condición y en el cumplimiento de las [comunicaciones.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="92ec0-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
