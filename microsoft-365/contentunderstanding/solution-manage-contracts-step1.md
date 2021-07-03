---
title: Paso 1. Usar SharePoint Syntex para identificar archivos de contrato y extraer datos
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Obtenga información sobre cómo usar SharePoint Syntex para identificar archivos de contrato y extraer datos mediante una Microsoft 365 solución.
ms.openlocfilehash: b73f7b96a1f1a9159770fb1bfb20bf2718f08c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287358"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="fa2ff-104">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-104">Step 1.</span></span> <span data-ttu-id="fa2ff-105">Usar SharePoint Syntex para identificar archivos de contrato y extraer datos</span><span class="sxs-lookup"><span data-stu-id="fa2ff-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="fa2ff-106">Su organización necesita una forma de identificar y clasificar todos los documentos de contrato de los muchos archivos que recibe.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="fa2ff-107">También desea poder ver rápidamente varios elementos clave en cada uno de los archivos de contrato identificados (por ejemplo, *Client*, *Contractor* y *Fee amount*).</span><span class="sxs-lookup"><span data-stu-id="fa2ff-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="fa2ff-108">Para ello, use [SharePoint Syntex](index.md) para crear un modelo de descripción de documentos y aplicarlo a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="fa2ff-109">Información general del proceso</span><span class="sxs-lookup"><span data-stu-id="fa2ff-109">Overview of the process</span></span>

<span data-ttu-id="fa2ff-110">[La comprensión de](document-understanding-overview.md) documentos usa modelos de inteligencia artificial (IA) para automatizar la clasificación de archivos y la extracción de información.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="fa2ff-111">Los modelos de comprensión de documentos también son óptimos para extraer información de documentos no estructurados y semiestructurados donde la información que necesita no está contenida en tablas o formularios, como contratos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span> 

<span data-ttu-id="fa2ff-112">En los modelos de comprensión mediante documentos se usa la tecnología de reconocimiento óptico de caracteres (OCR) para digitalizar archivos PDF, imágenes y archivos TIFF, tanto al entrenar un modelo con archivos de ejemplo como al ejecutar el modelo en archivos de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-112">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

1. <span data-ttu-id="fa2ff-113">En primer lugar, debe buscar al menos cinco archivos de ejemplo que pueda usar para "entrenar" el modelo para buscar características específicas del tipo de contenido que está intentando identificar (un contrato).</span><span class="sxs-lookup"><span data-stu-id="fa2ff-113">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="fa2ff-114">Con SharePoint Syntex, cree un nuevo modelo de comprensión de documentos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-114">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="fa2ff-115">Con los archivos de ejemplo, debe [crear un clasificador](create-a-classifier.md).</span><span class="sxs-lookup"><span data-stu-id="fa2ff-115">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="fa2ff-116">Al entrenar al clasificador con los archivos de ejemplo, se le enseña a buscar características específicas de lo que vería en los contratos de su empresa.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-116">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="fa2ff-117">Por ejemplo, [cree una "explicación"](create-a-classifier.md#create-an-explanation) que busque cadenas específicas que estén en sus contratos, como *Contrato* de servicio, *Términos* de contrato y *Compensación*.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-117">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="fa2ff-118">Incluso puede entrenar su explicación para buscar estas cadenas en secciones específicas del documento o ubicadas junto a otras cadenas.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-118">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="fa2ff-119">Cuando piense que ha formado al clasificador con la información que necesita, puede probar el modelo en un conjunto de ejemplos de archivos de ejemplo para ver su eficacia.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-119">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="fa2ff-120">Después de realizar las pruebas, si es necesario, puede elegir realizar cambios en sus explicaciones para hacerlos más eficientes.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-120">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="fa2ff-121">En el modelo, puede crear [un extractor](create-an-extractor.md) para extraer partes específicas de datos de cada contrato.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-121">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="fa2ff-122">Por ejemplo, para cada contrato, la información que más le preocupa es quién es el cliente, el nombre del contratista y el costo total.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-122">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="fa2ff-123">Después de crear correctamente el modelo, [apliquenlo a](apply-a-model.md)una biblioteca SharePoint documentos .</span><span class="sxs-lookup"><span data-stu-id="fa2ff-123">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="fa2ff-124">Al cargar documentos en la biblioteca de documentos, el modelo de descripción de documentos se ejecutará e identificará y clasificará todos los archivos que coincidan con el tipo de contenido de contratos definido en el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-124">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="fa2ff-125">Todos los archivos clasificados como contratos se mostrarán en una vista de biblioteca personalizada.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-125">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="fa2ff-126">Los archivos también mostrarán los valores de cada contrato definido en el extractor.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-126">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Contratos en la biblioteca de documentos](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="fa2ff-128">Si tiene requisitos de retención o seguridad para sus contratos, también [](apply-a-sensitivity-label-to-a-model.md) puede usar el modelo para aplicar una etiqueta de retención o una etiqueta de confidencialidad que impedirá que los contratos se eliminen durante un período de tiempo especificado o para restringir quién puede acceder [a](apply-a-retention-label-to-a-model.md) los contratos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-128">If you have retention or security requirements for your contracts, you can also use your model to apply a [retention label](apply-a-retention-label-to-a-model.md) or a [sensitivity label](apply-a-sensitivity-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time or to restrict who can access the contracts.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="fa2ff-129">Pasos para crear y entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="fa2ff-129">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="fa2ff-130">Para estos pasos, puede usar los archivos de ejemplo en el repositorio activos de solución de administración [de contratos](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span><span class="sxs-lookup"><span data-stu-id="fa2ff-130">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="fa2ff-131">Los ejemplos de este repositorio contienen tanto los archivos del modelo de descripción de documentos como los archivos usados para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-131">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="fa2ff-132">Crear un modelo de contrato</span><span class="sxs-lookup"><span data-stu-id="fa2ff-132">Create a Contract model</span></span>

<span data-ttu-id="fa2ff-133">El primer paso es crear el modelo de contrato.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-133">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="fa2ff-134">En el centro de contenido, seleccione **Nuevo** y, a continuación, **Crear un modelo**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-134">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="fa2ff-135">En el **panel Nuevo modelo de comprensión** de documentos, en el campo **Nombre,** escriba el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-135">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="fa2ff-136">Para esta solución de administración de contratos, puede nombrar el modelo *Contract*.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-136">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="fa2ff-137">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-137">Choose **Create**.</span></span> <span data-ttu-id="fa2ff-138">Esto crea una página principal para el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-138">This creates a home page for the model.</span></span></br>

    ![Captura de pantalla de la página principal del contrato.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="fa2ff-140">Entrenar al modelo para clasificar un tipo de archivo</span><span class="sxs-lookup"><span data-stu-id="fa2ff-140">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="fa2ff-141">Agregar archivos de ejemplo para el modelo</span><span class="sxs-lookup"><span data-stu-id="fa2ff-141">Add example files for your model</span></span>

<span data-ttu-id="fa2ff-142">Debe agregar al menos cinco archivos de ejemplo que sean documentos de contrato y un archivo de ejemplo que no sea un documento de contrato (por ejemplo, una instrucción de trabajo).</span><span class="sxs-lookup"><span data-stu-id="fa2ff-142">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="fa2ff-143">En la **página Modelos > Contrato,** en **Acciones** clave Agregar  >  **archivos de** ejemplo, seleccione **Agregar archivos**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-143">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Captura de pantalla que muestra la página Contratos con la opción Agregar archivos de ejemplo resaltada.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="fa2ff-145">En la **página Seleccionar archivos de ejemplo para el** modelo, abra la carpeta Contrato, seleccione los archivos que desea usar y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-145">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="fa2ff-146">Si no tiene archivos de ejemplo, **seleccione Upload** para agregarlos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-146">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="fa2ff-147">Etiquetar los archivos como ejemplos positivos o negativos</span><span class="sxs-lookup"><span data-stu-id="fa2ff-147">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="fa2ff-148">En la **página Modelos > contrato,** en **Acciones** clave Clasificar archivos y ejecutar  >  **aprendizaje,** seleccione **Clasificador de aprendizaje**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-148">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Captura de pantalla que muestra la página Contratos con Clasificar archivos y ejecutar la opción de aprendizaje resaltada.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="fa2ff-150">En  la página Clasificador > contrato > Contrato, en el visor de la parte superior del primer archivo de ejemplo, verá texto preguntando si el archivo es un ejemplo del modelo de contrato que creó.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-150">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="fa2ff-151">Si es un ejemplo positivo, seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-151">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="fa2ff-152">Si es un ejemplo negativo, seleccione **no**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-152">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="fa2ff-153">En la **lista Ejemplos etiquetados** de la izquierda, seleccione otros archivos que desee usar como ejemplos y rótulos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-153">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Página principal del Clasificador](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;fa2ff-155&quot;>Agregar al menos una explicación para entrenar al clasificador</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fa2ff-155&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;fa2ff-156&quot;>En la **página > modelo > clasificador** de contrato, seleccione la **pestaña** Entrenar.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fa2ff-156&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;fa2ff-157&quot;>En la **sección Archivos entrenados,** verá una lista de los archivos de ejemplo etiquetados anteriormente.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fa2ff-157&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;fa2ff-158&quot;>Seleccione uno de los archivos positivos de la lista para mostrarlo en el visor.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fa2ff-158&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;fa2ff-159&quot;>En la **sección Explicaciones,** seleccione **Nuevo** y, a continuación, **En blanco**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fa2ff-159&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;fa2ff-160&quot;>En la **página** Crear una explicación:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fa2ff-160&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;fa2ff-161&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fa2ff-161&quot;>a.</span></span> <span data-ttu-id=&quot;fa2ff-162&quot;>En el **campo** Nombre, escriba el nombre de la explicación (por ejemplo, &quot;Contrato").</span><span class="sxs-lookup"><span data-stu-id="fa2ff-162">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="fa2ff-163">b.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-163">b.</span></span> <span data-ttu-id="fa2ff-164">En el **campo Tipo de explicación,** seleccione **Lista de frases**, porque agrega una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-164">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="fa2ff-165">c.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-165">c.</span></span> <span data-ttu-id="fa2ff-166">En el **cuadro de lista** Frase, escriba la cadena (por ejemplo, "AGREEMENT").</span><span class="sxs-lookup"><span data-stu-id="fa2ff-166">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="fa2ff-167">Puede seleccionar Distingue **mayúsculas de** minúsculas si la cadena debe distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-167">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="fa2ff-168">d.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-168">d.</span></span> <span data-ttu-id="fa2ff-169">Seleccione **Guardar y entrenar**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-169">Select **Save and train**.</span></span>

    ![Captura de pantalla del panel Crear una explicación.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="fa2ff-171">Pruebe el modelo</span><span class="sxs-lookup"><span data-stu-id="fa2ff-171">Test your model</span></span>

<span data-ttu-id="fa2ff-172">Puede probar el modelo de contrato en archivos de ejemplo que no haya visto antes.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-172">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="fa2ff-173">Esto es opcional, pero puede ser un procedimiento recomendado útil.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-173">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="fa2ff-174">En la **página Modelos > clasificador de > contrato,** seleccione la **pestaña** Prueba. Esto ejecuta el modelo en los archivos de ejemplo sin etiquetar.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-174">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="fa2ff-175">En la **lista Archivos de** prueba, los archivos de ejemplo se muestran y muestran si el modelo predijo que son positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-175">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="fa2ff-176">Utilice esta información para ayudar a determinar la eficacia de su clasificador en la identificación de sus documentos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-176">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Captura de pantalla de los archivos sin etiquetar en la lista Archivos de texto](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="fa2ff-178">Cuando haya terminado, seleccione **Salir del aprendizaje**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-178">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="fa2ff-179">Crear y entrenar un extractor</span><span class="sxs-lookup"><span data-stu-id="fa2ff-179">Create and train an extractor</span></span>

1. <span data-ttu-id="fa2ff-180">En la **página Modelos > contrato,** en **Acciones** clave Crear y entrenar  >  **extractores,** seleccione Crear **extractor**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-180">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Captura de pantalla que muestra la página Contratos con la opción Crear y entrenar extractores resaltada.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="fa2ff-182">En el **panel Nuevo extractor de entidades,** en el campo Nuevo **nombre,** escriba el nombre del extractor.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-182">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="fa2ff-183">Por ejemplo, descóyenlo *Cliente* si desea extraer el nombre del cliente de cada contrato.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-183">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="fa2ff-184">Cuando haya terminado, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-184">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="fa2ff-185">Etiquetar la entidad que desea extraer</span><span class="sxs-lookup"><span data-stu-id="fa2ff-185">Label the entity you want to extract</span></span>

<span data-ttu-id="fa2ff-186">Al crear el extractor, se abre la página del extractor.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-186">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="fa2ff-187">Aquí puede ver una lista de sus archivos de muestra, con el primer archivo de la lista mostrado en el visor.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-187">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Captura de pantalla de la página Ejemplos etiquetados del extractor de cliente.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="fa2ff-189">Para etiquetar la entidad:</span><span class="sxs-lookup"><span data-stu-id="fa2ff-189">To label the entity:</span></span>

1. <span data-ttu-id="fa2ff-190">En el visor, seleccione los datos que desea extraer de los archivos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-190">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="fa2ff-191">Por ejemplo, si desea extraer el *client*, resalte el valor de cliente en el primer archivo (en este ejemplo, *Best For You Organics*) y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-191">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="fa2ff-192">Verá el valor que se muestra en el archivo en la lista **Ejemplos etiquetados,** en la **columna Etiqueta.**</span><span class="sxs-lookup"><span data-stu-id="fa2ff-192">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="fa2ff-193">Seleccione **Siguiente archivo** para guardar automáticamente y abra el siguiente archivo de la lista en el visor.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-193">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="fa2ff-194">O **bien, seleccione Guardar** y, a continuación, seleccione otro archivo de la **lista Ejemplos etiquetados.**</span><span class="sxs-lookup"><span data-stu-id="fa2ff-194">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="fa2ff-195">En el visor, repita los pasos 1 y 2 y repita hasta que guarde la etiqueta en todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-195">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="fa2ff-196">Después de etiquetar los archivos, se muestra un banner de notificación que le informa de que debe pasar al aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-196">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="fa2ff-197">Puede elegir etiquetar más documentos o avanzar a la formación.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-197">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="fa2ff-198">Agregue una explicación</span><span class="sxs-lookup"><span data-stu-id="fa2ff-198">Add an explanation</span></span>

<span data-ttu-id="fa2ff-199">Puede crear una explicación que proporciona una sugerencia sobre el propio formato de entidad y las variaciones que puede tener en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-199">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="fa2ff-200">Por ejemplo, un valor de fecha puede estar en muchos formatos diferentes, como:</span><span class="sxs-lookup"><span data-stu-id="fa2ff-200">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="fa2ff-201">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="fa2ff-201">10/14/2019</span></span>
- <span data-ttu-id="fa2ff-202">14 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="fa2ff-202">October 14, 2019</span></span>
- <span data-ttu-id="fa2ff-203">Lunes 14 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="fa2ff-203">Monday, October 14, 2019</span></span>

<span data-ttu-id="fa2ff-204">Para ayudar a identificar la *fecha de inicio del contrato,* puede crear una explicación de patrón.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-204">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="fa2ff-205">En la **sección Explicaciones,** seleccione **Nuevo** y, a continuación, **En blanco**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-205">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="fa2ff-206">En la **página** Crear una explicación:</span><span class="sxs-lookup"><span data-stu-id="fa2ff-206">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="fa2ff-207">a.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-207">a.</span></span> <span data-ttu-id="fa2ff-208">En el **campo** Nombre, escriba el nombre de la explicación (por *ejemplo, Fecha).*</span><span class="sxs-lookup"><span data-stu-id="fa2ff-208">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="fa2ff-209">b.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-209">b.</span></span> <span data-ttu-id="fa2ff-210">En el **campo Tipo de explicación,** seleccione **Lista patrón**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-210">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="fa2ff-211">c.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-211">c.</span></span> <span data-ttu-id="fa2ff-212">En el **campo** Valor, proporcione la variación de fecha tal como aparecen en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-212">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="fa2ff-213">Por ejemplo, si tiene formatos de fecha que aparecen como 0/00/0000, introduzca cualquier variación que aparezca en sus documentos, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fa2ff-213">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="fa2ff-214">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="fa2ff-214">0/0/0000</span></span>
    - <span data-ttu-id="fa2ff-215">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="fa2ff-215">0/00/0000</span></span>
    - <span data-ttu-id="fa2ff-216">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="fa2ff-216">00/0/0000</span></span>
    - <span data-ttu-id="fa2ff-217">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="fa2ff-217">00/00/0000</span></span>

4. <span data-ttu-id="fa2ff-218">Seleccione **Guardar y entrenar**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-218">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="fa2ff-219">Vuelva a probar el modelo</span><span class="sxs-lookup"><span data-stu-id="fa2ff-219">Test your model again</span></span>

<span data-ttu-id="fa2ff-220">Puede probar el modelo de contrato en archivos de ejemplo que no haya visto antes.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-220">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="fa2ff-221">Esto es opcional, pero puede ser un procedimiento recomendado útil.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-221">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="fa2ff-222">En la **página Modelos > clasificador de > contrato,** seleccione la **pestaña** Prueba. Esto ejecuta el modelo en los archivos de ejemplo sin etiquetar.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-222">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="fa2ff-223">En la **lista Archivos de** prueba, los archivos de ejemplo se muestran y muestran si el modelo puede extraer la información que necesita.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-223">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="fa2ff-224">Utilice esta información para ayudar a determinar la eficacia de su clasificador en la identificación de sus documentos.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-224">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="fa2ff-225">Cuando haya terminado, seleccione **Salir del aprendizaje**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-225">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="fa2ff-226">Aplicar el modelo a una biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="fa2ff-226">Apply your model to a document library</span></span>

<span data-ttu-id="fa2ff-227">Para aplicar el modelo a una SharePoint de documentos:</span><span class="sxs-lookup"><span data-stu-id="fa2ff-227">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="fa2ff-228">En la **página Modelos > contrato,** en **Acciones** clave Aplicar modelo  >  **a bibliotecas,** seleccione **Aplicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-228">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Captura de pantalla que muestra la página Contratos con la opción Aplicar modelo a bibliotecas resaltada.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="fa2ff-230">En el panel **Agregar contrato,** seleccione el SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-230">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="fa2ff-231">Si el sitio no aparece en la lista, use el cuadro de búsqueda para encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-231">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="fa2ff-232">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-232">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa2ff-233">Debe tener permisos de *Administración de lista* o de *Edición* en la biblioteca de documentos a la que va a aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-233">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="fa2ff-234">Después de seleccionar el sitio, seleccione la biblioteca de documentos a la que desea aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-234">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="fa2ff-235">Dado que el modelo está asociado a un tipo de contenido, al aplicarlo a la biblioteca, agregará el tipo de contenido y su vista con las etiquetas extraídas que se muestran como columnas.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-235">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="fa2ff-236">Esta vista es la vista predeterminada de la biblioteca de forma predeterminada, pero opcionalmente  puede elegir  que no sea la vista predeterminada seleccionando Configuración avanzada y desactivando la casilla Establecer esta nueva vista como predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-236">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="fa2ff-237">Seleccione **Agregar** para aplicar el modelo a la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-237">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="fa2ff-238">En la **página Modelos > contrato,** en la sección **Bibliotecas** con este modelo, verá la dirección URL del sitio SharePoint lista.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-238">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Captura de pantalla de la página principal del contrato que muestra la sección Bibliotecas con este modelo.](../media/content-understanding/contract-libraries-with-this-model.png)

7. <span data-ttu-id="fa2ff-240">En **Configuración**  >  **configuración de biblioteca:**</span><span class="sxs-lookup"><span data-stu-id="fa2ff-240">Under **Settings** > **Library settings**:</span></span>

   - <span data-ttu-id="fa2ff-241">Agregue una columna denominada **Status** y seleccione **Choice** como tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-241">Add a column named **Status** and select **Choice** as the column type.</span></span>
   - <span data-ttu-id="fa2ff-242">Aplique los **valores En revisión,** **Aprobado** y **Rechazado.**</span><span class="sxs-lookup"><span data-stu-id="fa2ff-242">Apply the **In review**, **Approved**, and **Rejected** values.</span></span>

<span data-ttu-id="fa2ff-243">Después de aplicar el modelo a la biblioteca de documentos, puede empezar a cargar documentos en el sitio y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="fa2ff-243">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="fa2ff-244">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="fa2ff-244">Next step</span></span>

[<span data-ttu-id="fa2ff-245">Paso 2. Usar Microsoft Teams para crear el canal de administración de contratos</span><span class="sxs-lookup"><span data-stu-id="fa2ff-245">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)