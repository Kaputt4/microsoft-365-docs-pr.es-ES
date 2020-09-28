---
title: Crear un clasificador
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtener información sobre cómo crear un clasificador
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294907"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="a4047-103">Crear un clasificador en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="a4047-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="a4047-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="a4047-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="a4047-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="a4047-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="a4047-106">Un clasificador es un tipo de modelo que puede usar para automatizar la identificación y clasificación de un tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="a4047-107">Por ejemplo, es posible que desee identificar todos los documentos de *renovación de contratos* que se agregan a la biblioteca de documentos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="a4047-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Documento de renovación de contrato](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="a4047-109">La creación de un clasificador permite crear un nuevo [tipo de contenido de SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que se asociará al modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="a4047-110">Al crear el clasificador, debe crear *explicaciones* para definir el modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="a4047-111">Esto le permite anotar datos comunes que espera que encuentren de forma coherente este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="a4047-112">Use ejemplos del tipo de documento ("archivos de ejemplo") para "entrenar" su modelo para identificar los archivos que tienen el mismo tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="a4047-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="a4047-113">Para crear un clasificador, debe:</span><span class="sxs-lookup"><span data-stu-id="a4047-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="a4047-114">Asigne un nombre al modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-114">Name your model.</span></span>
2. <span data-ttu-id="a4047-115">Agregue los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a4047-115">Add your example files.</span></span>
3. <span data-ttu-id="a4047-116">Etiquete los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a4047-116">Label your example files.</span></span>
4. <span data-ttu-id="a4047-117">Cree una explicación.</span><span class="sxs-lookup"><span data-stu-id="a4047-117">Create an explanation.</span></span>
5. <span data-ttu-id="a4047-118">Pruebe el modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="a4047-119">Aunque el modelo usa un clasificador para identificar y clasificar los tipos de documentos, también puede optar por extraer fragmentos específicos de información de cada archivo identificado por el modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="a4047-120">Para ello, cree un **extractor** para agregarlo al modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="a4047-121">Consulte [Create a extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="a4047-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="a4047-122">Asigne un nombre al modelo</span><span class="sxs-lookup"><span data-stu-id="a4047-122">Name your model</span></span>

<span data-ttu-id="a4047-123">El primer paso para crear el modelo es darle un nombre:</span><span class="sxs-lookup"><span data-stu-id="a4047-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="a4047-124">En el centro de contenido, seleccione **nuevo**y, a continuación, **cree un modelo**.</span><span class="sxs-lookup"><span data-stu-id="a4047-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="a4047-125">En el panel **nuevo documento que comprende el modelo** , en el campo **nombre** , escriba el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="a4047-126">Por ejemplo, si desea identificar documentos de renovación de contratos, puede asignar un nombre a la *renovación del contrato*del modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="a4047-127">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a4047-127">Choose **Create**.</span></span> <span data-ttu-id="a4047-128">Esto crea una página principal para el modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-128">This creates a home page for the model.</span></span></br>

    ![Página de inicio del modelo de clasificador](../media/content-understanding/model-home.png)

<span data-ttu-id="a4047-130">Al crear un modelo, también se crea un nuevo tipo de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a4047-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="a4047-131">Un tipo de contenido de SharePoint representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular.</span><span class="sxs-lookup"><span data-stu-id="a4047-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="a4047-132">Los tipos de contenido de SharePoint se administran a través de la [Galería de tipos de contenido](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="a4047-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="a4047-133">En este ejemplo, al crear el modelo, se crea un nuevo tipo de contenido de *renovación de contrato* .</span><span class="sxs-lookup"><span data-stu-id="a4047-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="a4047-134">Seleccione **Configuración avanzada** si desea asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="a4047-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="a4047-135">Tenga en cuenta que, aunque puede usar un tipo de contenido existente para aprovechar su esquema para ayudar con la identificación y clasificación, debe entrenar el modelo para extraer información de los archivos que identifica.</span><span class="sxs-lookup"><span data-stu-id="a4047-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Configuración avanzada](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="a4047-137">Adición de los archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4047-137">Add your example files</span></span>

<span data-ttu-id="a4047-138">En la Página principal del modelo, agregue los archivos de ejemplos que necesitará para entrenar el modelo para identificar el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="a4047-139">Debe usar los mismos archivos para la formación de clasificador y [extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="a4047-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="a4047-140">Siempre tiene la opción de agregar más adelante, pero normalmente agrega un conjunto completo de archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a4047-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="a4047-141">Etiquete algunos para entrenar el modelo y pruebe los restantes no etiquetados para evaluar la idoneidad del modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="a4047-142">Para su conjunto de aprendizaje, desea usar ejemplos positivos y negativos:</span><span class="sxs-lookup"><span data-stu-id="a4047-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="a4047-143">Ejemplo positivo: documentos que representan el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="a4047-144">Contienen cadenas e información que siempre estaría en este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="a4047-145">Ejemplo negativo: documentos que no representan el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="a4047-146">Faltan cadenas e información que deben estar presentes en este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="a4047-147">Asegúrese de usar al menos cinco ejemplos positivos y al menos un ejemplo negativo para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="a4047-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="a4047-148">Desea crear otros para probar el modelo después del proceso de formación.</span><span class="sxs-lookup"><span data-stu-id="a4047-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="a4047-149">Para agregar archivos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a4047-149">To add sample files:</span></span>

1. <span data-ttu-id="a4047-150">En la Página principal del modelo, en el mosaico **biblioteca de ejemplo de compilación** , haga clic en **Agregar archivos**.</span><span class="sxs-lookup"><span data-stu-id="a4047-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="a4047-151">En la página **seleccionar archivos de ejemplo para el modelo** , seleccione los archivos de ejemplo de la biblioteca de archivos de ejemplo en el centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="a4047-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="a4047-152">Si todavía no los ha cargado, elija cargarlos ahora haciendo clic en **cargar** para moverlos a la biblioteca de archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a4047-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="a4047-153">Después de seleccionar los archivos de ejemplo que se usarán para entrenar el modelo, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a4047-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Seleccionar archivos de ejemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="a4047-155">Etiquetar los archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4047-155">Label your example files</span></span>

<span data-ttu-id="a4047-156">Después de agregar los archivos de ejemplo, debe etiquetarlos como ejemplos positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="a4047-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="a4047-157">En el cuadro **clasificar archivos y ejecutar formación** de la Página principal del modelo, haga clic en **formar clasificador**.</span><span class="sxs-lookup"><span data-stu-id="a4047-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="a4047-158">Se muestra la página de etiqueta que muestra una lista de los archivos de ejemplo, con el primer archivo visible en el visor.</span><span class="sxs-lookup"><span data-stu-id="a4047-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="a4047-159">En el visor de la parte superior del primer archivo de ejemplo, debería ver texto que le preguntará si el archivo es un ejemplo del modelo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="a4047-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="a4047-160">Si es un ejemplo positivo, seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="a4047-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="a4047-161">Si es un ejemplo negativo, seleccione **no**.</span><span class="sxs-lookup"><span data-stu-id="a4047-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="a4047-162">En la lista de **ejemplos con etiquetas** de la izquierda, seleccione archivos adicionales que desee usar como ejemplos y etiquételo.</span><span class="sxs-lookup"><span data-stu-id="a4047-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Página principal del clasificador](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="a4047-164">Etiquete como mínimo cinco ejemplos positivos y un ejemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="a4047-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="a4047-165">Crear una explicación</span><span class="sxs-lookup"><span data-stu-id="a4047-165">Create an explanation</span></span>

<span data-ttu-id="a4047-166">El paso siguiente es para crear una explicación en la página del tren.</span><span class="sxs-lookup"><span data-stu-id="a4047-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="a4047-167">Una explicación ayuda a que el modelo comprenda cómo reconocer el documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="a4047-168">Por ejemplo, los documentos de renovación de contratos siempre contienen una *solicitud de cadena de texto de divulgación adicional* .</span><span class="sxs-lookup"><span data-stu-id="a4047-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="a4047-169">Cuando se usa con extractores, una explicación identifica la cadena que se desea extraer del documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="a4047-170">Para crear una explicación:</span><span class="sxs-lookup"><span data-stu-id="a4047-170">To create an explanation:</span></span>

1. <span data-ttu-id="a4047-171">En la Página principal del modelo, seleccione la ficha **tren** para ir a la página tren.</span><span class="sxs-lookup"><span data-stu-id="a4047-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="a4047-172">En la página tren, en la sección **archivos entrenados** , verá una lista de los archivos de ejemplo etiquetados previamente.</span><span class="sxs-lookup"><span data-stu-id="a4047-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="a4047-173">Seleccione uno de los archivos positivos de la lista y se muestra en el visor.</span><span class="sxs-lookup"><span data-stu-id="a4047-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="a4047-174">En la sección explicación, seleccione **nuevo** y, a continuación, **en blanco**.</span><span class="sxs-lookup"><span data-stu-id="a4047-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="a4047-175">En la página **crear una explicación** :</span><span class="sxs-lookup"><span data-stu-id="a4047-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="a4047-176">a.</span><span class="sxs-lookup"><span data-stu-id="a4047-176">a.</span></span> <span data-ttu-id="a4047-177">Escriba el **nombre** (por ejemplo, "bloque de revelación").</span><span class="sxs-lookup"><span data-stu-id="a4047-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="a4047-178">b.</span><span class="sxs-lookup"><span data-stu-id="a4047-178">b.</span></span> <span data-ttu-id="a4047-179">Seleccione el **tipo**.</span><span class="sxs-lookup"><span data-stu-id="a4047-179">Select the **Type**.</span></span> <span data-ttu-id="a4047-180">Para el ejemplo, seleccione **lista de frases**, ya que agrega una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="a4047-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="a4047-181">c.</span><span class="sxs-lookup"><span data-stu-id="a4047-181">c.</span></span> <span data-ttu-id="a4047-182">En el cuadro **Escriba aquí** , escriba la cadena.</span><span class="sxs-lookup"><span data-stu-id="a4047-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="a4047-183">Para ver el ejemplo, agregue "solicitud de divulgación adicional".</span><span class="sxs-lookup"><span data-stu-id="a4047-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="a4047-184">Puede seleccionar **mayúsculas** y minúsculas si la cadena debe distinguir mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a4047-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="a4047-185">d.</span><span class="sxs-lookup"><span data-stu-id="a4047-185">d.</span></span> <span data-ttu-id="a4047-186">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="a4047-186">Click **Save**.</span></span>

    ![Crear explicación](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="a4047-188">Ahora, el modelo comprueba si la explicación que ha creado fue lo suficientemente buena como para identificar correctamente los archivos de ejemplo con etiquetas restantes como ejemplos positivos y negativos.</span><span class="sxs-lookup"><span data-stu-id="a4047-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="a4047-189">En la sección archivos entrenados, revise la columna **evaluación** después de que se haya completado el entrenamiento para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="a4047-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="a4047-190">Los archivos muestran un valor de **coincidencia**si las explicaciones que ha creado son suficientes para coincidir con lo que ha etiquetado como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="a4047-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Valor de coincidencia](../media/content-understanding/match.png) 

<span data-ttu-id="a4047-192">Si recibe un error de **coincidencia** con los archivos etiquetados, es posible que deba crear una explicación adicional para proporcionar al modelo más información para identificar el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="a4047-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="a4047-193">Si esto ocurre, haga clic en el archivo para obtener más información acerca de por qué se ha producido un error de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="a4047-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="a4047-194">Probar el modelo</span><span class="sxs-lookup"><span data-stu-id="a4047-194">Test your model</span></span>

<span data-ttu-id="a4047-195">Si ha recibido una coincidencia en los archivos de ejemplo con la etiqueta, ahora puede probar el modelo en los restantes archivos de ejemplo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a4047-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="a4047-196">En la Página principal del modelo, seleccione la pestaña **prueba** .  Esto ejecuta el modelo en los archivos de ejemplo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a4047-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="a4047-197">En la lista **archivos de prueba** , los archivos de ejemplo muestran y muestran si el modelo predictó para ser positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="a4047-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="a4047-198">Use esta información para ayudar a determinar la eficacia del clasificador en la identificación de los documentos.</span><span class="sxs-lookup"><span data-stu-id="a4047-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Prueba de archivos sin etiquetar](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="a4047-200">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4047-200">See Also</span></span>
[<span data-ttu-id="a4047-201">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="a4047-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="a4047-202">Información general sobre el documento</span><span class="sxs-lookup"><span data-stu-id="a4047-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="a4047-203">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="a4047-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="a4047-204">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="a4047-204">Apply a model</span></span>](apply-a-model.md) 
