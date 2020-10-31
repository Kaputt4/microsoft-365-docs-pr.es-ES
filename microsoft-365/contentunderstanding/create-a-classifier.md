---
title: Crear un clasificador
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Aprenda a crear un clasificador
ms.openlocfilehash: 97a7b28d45499a46d72029d47b422d2c32696a54
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804820"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="81f1f-103">Crear un clasificador en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="81f1f-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="81f1f-104">Un clasificador es un tipo de modelo que se puede usar para automatizar la identificación y la clasificación de un tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="81f1f-105">Por ejemplo, es posible que quiera identificar todas los *renovaciones de contrato* documentos que se agregan a la biblioteca de documentos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="81f1f-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Documento de renovación de contrato](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="81f1f-107">La creación de un clasificador le permite crear un nuevo [ tipo de contenido de SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que se asociará al modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-107">Creating a classifier enables you to create a new [SharePoint content type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="81f1f-108">Al crear el clasificador, debe crear *explicaciones* para definir el modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="81f1f-109">Esto le permite tener en cuenta datos comunes que esperaría encontrar constantemente este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="81f1f-110">Use ejemplos del tipo de documento ("archivos de ejemplo") para "entrenar" al modelo para identificar los archivos que tienen el mismo tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="81f1f-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="81f1f-111">Para crear un clasificador, es necesario:</span><span class="sxs-lookup"><span data-stu-id="81f1f-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="81f1f-112">Nombrar a su modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-112">Name your model.</span></span>
2. <span data-ttu-id="81f1f-113">Añadir sus archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-113">Add your example files.</span></span>
3. <span data-ttu-id="81f1f-114">Etiquetar los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-114">Label your example files.</span></span>
4. <span data-ttu-id="81f1f-115">Agregar una explicación</span><span class="sxs-lookup"><span data-stu-id="81f1f-115">Create an explanation.</span></span>
5. <span data-ttu-id="81f1f-116">Probar el modelo</span><span class="sxs-lookup"><span data-stu-id="81f1f-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="81f1f-117">Aunque el modelo usa un clasificador para identificar y clasificar los tipos de documentos, también puede elegir extraer fragmentos específicos de información de cada archivo identificado por el modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="81f1f-118">Para ello, cree un **extractor** para agregarlo al modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="81f1f-119">Ver [Crear un extractor](create-an-extractor.md)</span><span class="sxs-lookup"><span data-stu-id="81f1f-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="81f1f-120">Nombrar a su modelo</span><span class="sxs-lookup"><span data-stu-id="81f1f-120">Name your model</span></span>

<span data-ttu-id="81f1f-121">El primer paso para crear el modelo es nombrarlo:</span><span class="sxs-lookup"><span data-stu-id="81f1f-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="81f1f-122">En el centro de contenido, seleccione **Nuevo** y, a continuación, **Crear un modelo** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-122">From the content center, select **New** , and then **Create a model** .</span></span>
2. <span data-ttu-id="81f1f-123">En el panel **Documento nuevo comprender el modelo** en el campo **Nombre** escriba el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="81f1f-124">Por ejemplo, si desea identificar documentos de renovación de contratos, puede nombrar al modelo *Renovación de contratos* .</span><span class="sxs-lookup"><span data-stu-id="81f1f-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal* .</span></span>
3. <span data-ttu-id="81f1f-125">Seleccione **Crear** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-125">Choose **Create** .</span></span> <span data-ttu-id="81f1f-126">Esto crea una página principal para el modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-126">This creates a home page for the model.</span></span></br>

    ![Página principal de modelo de clasificador](../media/content-understanding/model-home.png)

<span data-ttu-id="81f1f-128">Cuando se crea un modelo, también se crea un nuevo tipo de contenido para el sitio.</span><span class="sxs-lookup"><span data-stu-id="81f1f-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="81f1f-129">Un tipo de contenido representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular.</span><span class="sxs-lookup"><span data-stu-id="81f1f-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="81f1f-130">Los tipos de contenido de SharePoint se administran en la [Galería de tipos de contenido](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="81f1f-130">SharePoint content types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="81f1f-131">Para este ejemplo, al crear el modelo, va a crear un nuevo *tipo de contenido* Renovación de contrato.</span><span class="sxs-lookup"><span data-stu-id="81f1f-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="81f1f-132">Seleccionar **Configuración avanzada** si quiere asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="81f1f-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="81f1f-133">Los tipos de contenido de empresa se almacenan en el concentrador de tipo de contenido en el centro de administración de SharePoint y se distribuyen en todos los sitios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="81f1f-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="81f1f-134">Tenga en cuenta que, aunque puede usar un tipo de contenido existente para aprovechar su esquema para ayudar con la identificación y la clasificación, aún necesita entrenar el modelo para extraer la información de los archivos que identifica.</span><span class="sxs-lookup"><span data-stu-id="81f1f-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Configuración avanzada](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="81f1f-136">Añadir sus archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="81f1f-136">Add your example files</span></span>

<span data-ttu-id="81f1f-137">En la Página principal del modelo, agregue los archivos de ejemplo que necesitará para entrenar al modelo para que identifique el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="81f1f-138">Debe usar los mismos archivos tanto para el clasificador como para el[entrenador de extracción](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="81f1f-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="81f1f-139">Siempre queda la opción de agregar más después, pero normalmente se agrega un conjunto completo de archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="81f1f-140">Etiquete algunos para entrenar el modelo y pruebe el resto de los no etiquetados para evaluar la idoneidad del modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="81f1f-141">Para su conjunto de aprendizaje, puede usar ejemplos positivos y negativos:</span><span class="sxs-lookup"><span data-stu-id="81f1f-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="81f1f-142">Ejemplo positivo: documentos que representan el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="81f1f-143">Estos contienen secuencias de datos e información que siempre se encuentran en este tipo de documentos.</span><span class="sxs-lookup"><span data-stu-id="81f1f-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="81f1f-144">Ejemplo negativo: cualquier otro documento que no representa el documento que desea clasificar.</span><span class="sxs-lookup"><span data-stu-id="81f1f-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="81f1f-145">Asegúrese de usar al menos cinco ejemplos positivos y al menos un ejemplo negativo para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="81f1f-146">Se deben crear otros para probar el modelo después del proceso de formación.</span><span class="sxs-lookup"><span data-stu-id="81f1f-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="81f1f-147">Para añadir archivos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="81f1f-147">To add example files:</span></span>

1. <span data-ttu-id="81f1f-148">En la Página principal del modelo, en el cuadro **Añadir archivos de ejemplo** haga clic en **Añadir archivos** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-148">On the model home page, in the **Add example files** tile, click **Add files** .</span></span>
2. <span data-ttu-id="81f1f-149">En la página **seleccionar archivos de ejemplo para el modelo** seleccione los archivos de ejemplo de la biblioteca de archivos de aprendizaje en el centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="81f1f-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="81f1f-150">Si aún no se han cargado allí, elija cargarlos ahora haciendo clic en **Cargar** para copiarlos a la biblioteca de archivos de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="81f1f-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="81f1f-151">Después de seleccionar los archivos de ejemplo que se usarán para entrenar el modelo, haga clic en **Añadir** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-151">After selecting your example files to use to train the model, click **Add** .</span></span>

    ![Seleccionar archivos de ejemplo:](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="81f1f-153">Etiquetar los archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="81f1f-153">Label your example files</span></span>

<span data-ttu-id="81f1f-154">Después de agregar los archivos de ejemplo, debe etiquetarlos como ejemplos positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="81f1f-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="81f1f-155">En la página principal del modelo, en el cuadro **Clasificar archivos y ejecutar el entrenamiento** haga clic en **Clasificador de documentos** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-155">From the model home page, on the **Classify files and run training** tile, click **Train classifier** .</span></span>
   <span data-ttu-id="81f1f-156">Esto muestra la página de etiquetas que contiene un listado de sus archivos de ejemplo, con el primer archivo visible en el visor.</span><span class="sxs-lookup"><span data-stu-id="81f1f-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="81f1f-157">En el visor, en la parte superior del primer archivo de ejemplo, debería ver un texto que pregunta si el archivo es un ejemplo del modelo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="81f1f-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="81f1f-158">Si es un ejemplo positivo, seleccione **sí** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-158">If it is a positive example, select **Yes** .</span></span> <span data-ttu-id="81f1f-159">Si es un ejemplo negativo, seleccione **no** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-159">If it is a negative example, select **No** .</span></span>
3. <span data-ttu-id="81f1f-160">En la lista **Ejemplos etiquetados** en la parte izquierda, seleccione los archivos adicionales que desea usar como ejemplos y asígneles etiquetas.</span><span class="sxs-lookup"><span data-stu-id="81f1f-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Página principal del Clasificador](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="81f1f-162">Etiquete como mínimo cinco ejemplos positivos.</span><span class="sxs-lookup"><span data-stu-id="81f1f-162">Label at least five positive examples.</span></span> <span data-ttu-id="81f1f-163">También debe etiquetar al menos un ejemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="81f1f-164">Crear una explicación</span><span class="sxs-lookup"><span data-stu-id="81f1f-164">Create an explanation</span></span>

<span data-ttu-id="81f1f-165">El siguiente paso consiste en crear una explicación en la página de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="81f1f-166">Una explicación ayuda al modelo a comprender cómo se reconoce el documento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="81f1f-167">Por ejemplo, los documentos de renovación de contrato siempre contienen una *cadena de texto:* solicitud para divulgación adicional.</span><span class="sxs-lookup"><span data-stu-id="81f1f-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="81f1f-168">Cuando se usa con extractores, una explicación identifica la cadena que desea extraer del documento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="81f1f-169">Para crear una explicación:</span><span class="sxs-lookup"><span data-stu-id="81f1f-169">To create an explanation:</span></span>

1. <span data-ttu-id="81f1f-170">En la Página principal del modelo, seleccione la pestaña **Entrenar** para ir a la página de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="81f1f-171">En la página entrenamiento, en la sección **archivos entrenados** debería ver una lista de los archivos de ejemplo que etiquetó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="81f1f-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="81f1f-172">Seleccione uno de los archivos positivos de la lista, y se mostrará en el visor.</span><span class="sxs-lookup"><span data-stu-id="81f1f-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="81f1f-173">En la sección de Explicación, seleccione **Nuevo** y después **En blanco** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-173">In the Explanation section, select **New** and then **Blank** .</span></span>
4. <span data-ttu-id="81f1f-174">En la **página** Crear una explicación:</span><span class="sxs-lookup"><span data-stu-id="81f1f-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="81f1f-175">a.</span><span class="sxs-lookup"><span data-stu-id="81f1f-175">a.</span></span> <span data-ttu-id="81f1f-176">Escriba el **Nombre** (por ejemplo, "bloque de divulgación").</span><span class="sxs-lookup"><span data-stu-id="81f1f-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="81f1f-177">b.</span><span class="sxs-lookup"><span data-stu-id="81f1f-177">b.</span></span> <span data-ttu-id="81f1f-178">Seleccione el **Tipo** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-178">Select the **Type** .</span></span> <span data-ttu-id="81f1f-179">Para la muestra, seleccione **Lista de frases** ,ya que se añade una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="81f1f-179">For the sample, select **Phrase list** , since you add a text string.</span></span></br>
    <span data-ttu-id="81f1f-180">c.</span><span class="sxs-lookup"><span data-stu-id="81f1f-180">c.</span></span> <span data-ttu-id="81f1f-181">En el cuadro **Escriba aquí** , escriba la cadena.</span><span class="sxs-lookup"><span data-stu-id="81f1f-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="81f1f-182">Agregue "solicitud para divulgación adicional" para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81f1f-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="81f1f-183">Puede seleccionar **Distinguir mayúsculas de minúsculas** si la cadena tiene que distinguir mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="81f1f-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="81f1f-184">d.</span><span class="sxs-lookup"><span data-stu-id="81f1f-184">d.</span></span> <span data-ttu-id="81f1f-185">Haga clic en **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="81f1f-185">Click **Save** .</span></span>

    ![Crear una explicación](../media/content-understanding/explanation.png) 
    
5. <span data-ttu-id="81f1f-187">El centro de contenido ahora comprueba si la explicación que ha creado es lo suficientemente completa como para identificar el resto de los archivos de ejemplo con etiquetas correctamente, como ejemplos positivos y negativos.</span><span class="sxs-lookup"><span data-stu-id="81f1f-187">The Content Center now checks to see if the explanation you created is complete enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="81f1f-188">En la sección archivos entrenados, Compruebe la columna **Evaluación** una vez completada la formación para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="81f1f-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="81f1f-189">Los archivos muestran el valor **Coincidencia** , si las explicaciones que ha creado son suficientes como para coincidir con la etiquetada como positiva o negativa.</span><span class="sxs-lookup"><span data-stu-id="81f1f-189">The files show a value of **Match** , if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Valor de coincidencia](../media/content-understanding/match.png) 

<span data-ttu-id="81f1f-191">Si recibe una **No coincidencia** en los archivos etiquetados, es posible que tenga que crear una explicación adicional para proporcionar al modelo más información para identificar el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="81f1f-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="81f1f-192">En ese caso, haga clic en el archivo para obtener más información sobre el motivo por el que se ha producido un error de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="81f1f-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="81f1f-193">Pruebe el modelo</span><span class="sxs-lookup"><span data-stu-id="81f1f-193">Test your model</span></span>

<span data-ttu-id="81f1f-194">Si recibe una coincidencia en sus archivos de muestra etiquetados, ahora puede probar su modelo en los archivos de muestra no etiquetados restantes.</span><span class="sxs-lookup"><span data-stu-id="81f1f-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="81f1f-195">Se trata de un paso opcional, pero resulta útil para evaluar la idoneidad del modelo o determinar si está preparado antes de usarlo, y para ello se prueba en archivos que el modelo no ha visto antes.</span><span class="sxs-lookup"><span data-stu-id="81f1f-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="81f1f-196">En la página principal del modelo, haga clic en la pestaña **Probar** . Esto ejecuta el modelo en sus archivos de muestra sin etiquetar.</span><span class="sxs-lookup"><span data-stu-id="81f1f-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="81f1f-197">En la lista **archivos de prueba** , sus archivos de ejemplo se muestran e indican si el modelo predijo que fueran positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="81f1f-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="81f1f-198">Utilice esta información para ayudar a determinar la eficacia de su clasificador en la identificación de sus documentos.</span><span class="sxs-lookup"><span data-stu-id="81f1f-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Probar archivos sin etiquetar](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="81f1f-200">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81f1f-200">See Also</span></span>
[<span data-ttu-id="81f1f-201">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="81f1f-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="81f1f-202">Información general sobre la comprensión de los documentos</span><span class="sxs-lookup"><span data-stu-id="81f1f-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="81f1f-203">Tipos de explicación</span><span class="sxs-lookup"><span data-stu-id="81f1f-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="81f1f-204">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="81f1f-204">Apply a model</span></span>](apply-a-model.md) 
