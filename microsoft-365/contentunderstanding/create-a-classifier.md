---
title: Crear un clasificador (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtener información sobre cómo crear un clasificador
ms.openlocfilehash: 718d904ca397d43644c578ff6f589b5e5b043e5a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950161"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="ea41a-103">Crear un clasificador (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ea41a-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="ea41a-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="ea41a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="ea41a-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="ea41a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="ea41a-106">Un clasificador es un tipo de modelo que automatiza la identificación y clasificación de un tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="ea41a-107">Por ejemplo, es posible que desee identificar todos los documentos de *renovación de contratos* que se agregan a la biblioteca de documentos, como los siguientes.</span><span class="sxs-lookup"><span data-stu-id="ea41a-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Documento de renovación de contrato](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="ea41a-109">La creación de un clasificador creará un nuevo [tipo de contenido de SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que se asociará al modelo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="ea41a-110">Al crear el clasificador, tiene que crear *explicaciones* que le ayuden a definir el modelo mediante la anotación de datos comunes que esperaría buscar de forma coherente en este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="ea41a-111">Puede usar ejemplos del tipo de documento ("archivos de ejemplo") para "entrenar" su modelo para identificar los archivos que tienen el mismo tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="ea41a-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="ea41a-112">Para crear un clasificador, debe:</span><span class="sxs-lookup"><span data-stu-id="ea41a-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="ea41a-113">Asigne un nombre al modelo</span><span class="sxs-lookup"><span data-stu-id="ea41a-113">Name your model</span></span>
2. <span data-ttu-id="ea41a-114">Adición de los archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea41a-114">Add your example files</span></span>
3. <span data-ttu-id="ea41a-115">Etiquetar los archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea41a-115">Label your example files</span></span>
4. <span data-ttu-id="ea41a-116">Crear una explicación</span><span class="sxs-lookup"><span data-stu-id="ea41a-116">Create an explanation</span></span>
5. <span data-ttu-id="ea41a-117">Probar el modelo</span><span class="sxs-lookup"><span data-stu-id="ea41a-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="ea41a-118">Mientras que el modelo utiliza un clasificador para identificar y clasificar los tipos de documentos, también puede optar por extraer fragmentos específicos de información de cada archivo identificado por el modelo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="ea41a-119">Para ello, cree un **extractor** para agregarlo al modelo y esto se describe en Create a [extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="ea41a-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="ea41a-120">Asigne un nombre al modelo</span><span class="sxs-lookup"><span data-stu-id="ea41a-120">Name your model</span></span>

<span data-ttu-id="ea41a-121">El primer paso consiste en crear el modelo en el centro de contenido asignándole un nombre:</span><span class="sxs-lookup"><span data-stu-id="ea41a-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="ea41a-122">En el centro de contenido, haga clic en **nuevo**y, a continuación, haga clic en **crear un modelo**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="ea41a-123">En el panel **nuevo documento que comprende el modelo** , en el campo **nombre** , escriba el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="ea41a-124">En nuestro ejemplo, si queremos identificar documentos de renovación de contratos, podríamos nombrar esta renovación de *contrato*de modelo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="ea41a-125">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-125">Click **Create**.</span></span> <span data-ttu-id="ea41a-126">De este modo, se creará una página principal para el modelo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-126">This will create a home page for the model.</span></span></br>

    ![Página de inicio del modelo de clasificador](../media/content-understanding/model-home.png)

<span data-ttu-id="ea41a-128">Al crear un modelo, se crea un nuevo tipo de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ea41a-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="ea41a-129">Un tipo de contenido de SharePoint representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular.</span><span class="sxs-lookup"><span data-stu-id="ea41a-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="ea41a-130">Los tipos de contenido de SharePoint se administran a través de la [Galería de tipos de contenido]().</span><span class="sxs-lookup"><span data-stu-id="ea41a-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="ea41a-131">En nuestro ejemplo, cuando creamos el modelo, crearemos un nuevo tipo de contenido de *renovación de contrato* .</span><span class="sxs-lookup"><span data-stu-id="ea41a-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="ea41a-132">Seleccione **Configuración avanzada** si desea asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="ea41a-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="ea41a-133">Tenga en cuenta que, si bien puede usar un tipo de contenido existente para aprovechar su esquema para ayudar con la identificación y clasificación, deberá entrenar el modelo para extraer información de los archivos que identifica.</span><span class="sxs-lookup"><span data-stu-id="ea41a-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Configuración avanzada](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="ea41a-135">Adición de los archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea41a-135">Add your example files</span></span>

<span data-ttu-id="ea41a-136">En la Página principal del modelo, puede Agregar los archivos de ejemplos que necesita para entrenar el modelo para identificar su tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="ea41a-137">Se deben usar los mismos archivos para la formación de clasificador y [extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="ea41a-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="ea41a-138">Siempre tiene la opción de agregar más adelante, pero normalmente debe agregar un conjunto completo de archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="ea41a-139">Deberá etiquetar algunas para entrenar el modelo y probar los restantes no etiquetados para evaluar la idoneidad del modelo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="ea41a-140">Para su conjunto de aprendizaje, querrá usar ejemplos positivos y negativos:</span><span class="sxs-lookup"><span data-stu-id="ea41a-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="ea41a-141">Ejemplo positivo: documentos que representan el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="ea41a-142">Contienen cadenas e información que siempre estaría en este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="ea41a-143">Ejemplo negativo: documentos que no representan el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="ea41a-144">Faltan cadenas e información que debe estar presente en este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="ea41a-145">Querrá usar al menos cinco ejemplos positivos y un ejemplo negativo para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="ea41a-146">Querrá tener otros para probar el modelo después de la formación.</span><span class="sxs-lookup"><span data-stu-id="ea41a-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="ea41a-147">Para agregar archivos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ea41a-147">To add sample files:</span></span>

1. <span data-ttu-id="ea41a-148">En la Página principal del modelo, en el mosaico **biblioteca de ejemplo de compilación** , haga clic en **Agregar archivos**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="ea41a-149">En la página **seleccionar archivos de ejemplo para el modelo** , seleccione los archivos de ejemplo de la biblioteca de archivos de ejemplo en el centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="ea41a-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="ea41a-150">Si aún no se han cargado allí, puede optar por cargarlas ahora haciendo clic en **cargar** para moverlas a la biblioteca de archivos de muestra.</span><span class="sxs-lookup"><span data-stu-id="ea41a-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="ea41a-151">Después de seleccionar los archivos de ejemplo que se usarán para entrenar el modelo, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Seleccionar archivos de ejemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="ea41a-153">Etiquetar los archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea41a-153">Label your example files</span></span>

<span data-ttu-id="ea41a-154">Después de agregar los archivos de ejemplo, debe etiquetarlos como ejemplos positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="ea41a-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="ea41a-155">En la Página principal del modelo, en el icono **clasificar archivos y ejecutar el entrenamiento** , haga clic en **formar clasificador**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="ea41a-156">Se mostrará la página de etiqueta que muestra una lista de los archivos de ejemplo, con el primer archivo visible en el visor.</span><span class="sxs-lookup"><span data-stu-id="ea41a-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="ea41a-157">En el visor, en la parte superior del primer archivo de ejemplo, verá texto que le pregunta si el archivo es un ejemplo del modelo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="ea41a-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="ea41a-158">Si es un ejemplo positivo, seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="ea41a-159">Si es un ejemplo negativo, seleccione **no**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="ea41a-160">En la lista de **ejemplos con etiquetas** de la izquierda, seleccione los archivos adicionales que desee usar como ejemplos y etiquételo también.</span><span class="sxs-lookup"><span data-stu-id="ea41a-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Página de inicio del modelo de clasificador](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="ea41a-162">Etiquete como mínimo cinco ejemplos positivos y un ejemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="ea41a-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="ea41a-163">Crear una explicación</span><span class="sxs-lookup"><span data-stu-id="ea41a-163">Create an explanation</span></span>

<span data-ttu-id="ea41a-164">El siguiente paso es crear una explicación en la página del tren.</span><span class="sxs-lookup"><span data-stu-id="ea41a-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="ea41a-165">Una explicación es una sugerencia o indicio para ayudar a que el modelo comprenda cómo reconocer este documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="ea41a-166">Por ejemplo, los documentos de renovación de contratos siempre contienen una *solicitud para una cadena de texto de divulgación adicional* .</span><span class="sxs-lookup"><span data-stu-id="ea41a-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="ea41a-167">Cuando se usa con extractores, se usa una explicación para identificar la cadena que se desea extraer del documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="ea41a-168">Para crear una explicación:</span><span class="sxs-lookup"><span data-stu-id="ea41a-168">To create an explanation:</span></span>

1. <span data-ttu-id="ea41a-169">En la Página principal del modelo, haga clic en la pestaña **tren** para ir a la página tren.</span><span class="sxs-lookup"><span data-stu-id="ea41a-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="ea41a-170">En la página tren, en la sección **archivos entrenados** , verá una lista de los archivos de ejemplo que ha etiquetado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ea41a-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="ea41a-171">Seleccione uno de los archivos positivos de la lista y se mostrará en el visor.</span><span class="sxs-lookup"><span data-stu-id="ea41a-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="ea41a-172">En la sección explicación, haga clic en **nuevo**y, a continuación, haga clic en **en blanco**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="ea41a-173">En la página **crear una explicación** :</span><span class="sxs-lookup"><span data-stu-id="ea41a-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="ea41a-174">a.</span><span class="sxs-lookup"><span data-stu-id="ea41a-174">a.</span></span> <span data-ttu-id="ea41a-175">Escriba el **nombre** (por ejemplo, "bloque de revelación").</span><span class="sxs-lookup"><span data-stu-id="ea41a-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="ea41a-176">b.</span><span class="sxs-lookup"><span data-stu-id="ea41a-176">b.</span></span> <span data-ttu-id="ea41a-177">Seleccione el **tipo**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-177">Select the **Type**.</span></span> <span data-ttu-id="ea41a-178">En nuestro ejemplo, seleccionaremos **lista de frases**, ya que estamos agregando una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="ea41a-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="ea41a-179">c.</span><span class="sxs-lookup"><span data-stu-id="ea41a-179">c.</span></span> <span data-ttu-id="ea41a-180">En el cuadro **Escriba aquí** , escriba la cadena.</span><span class="sxs-lookup"><span data-stu-id="ea41a-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="ea41a-181">Para nuestro ejemplo, agregaremos "solicitud de divulgación adicional".</span><span class="sxs-lookup"><span data-stu-id="ea41a-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="ea41a-182">Puede seleccionar **mayúsculas** y minúsculas si la cadena debe distinguir mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ea41a-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="ea41a-183">d.</span><span class="sxs-lookup"><span data-stu-id="ea41a-183">d.</span></span> <span data-ttu-id="ea41a-184">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ea41a-184">Click **Save**.</span></span>

    ![Crear explicación](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="ea41a-186">El modelo comprobará ahora si la explicación que ha creado es lo suficientemente buena como para identificar los archivos de ejemplo con la etiqueta que queden correctamente como ejemplos positivos y negativos.</span><span class="sxs-lookup"><span data-stu-id="ea41a-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="ea41a-187">En la sección archivos entrenados, revise la columna **evaluación** después de que se haya completado el entrenamiento para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="ea41a-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="ea41a-188">Los archivos mostrarán un valor de **coincidencia** si la explicación que ha creado es suficiente para coincidir con lo que ha etiquetado como (positivo o negativo).</span><span class="sxs-lookup"><span data-stu-id="ea41a-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Crear explicación](../media/content-understanding/match.png) 

<span data-ttu-id="ea41a-190">Si recibe un error de **coincidencia** con los archivos etiquetados, es posible que deba crear una explicación adicional para proporcionar al modelo más información para identificar el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ea41a-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="ea41a-191">Puede hacer clic en el archivo para obtener más información sobre la razón por la que se produjo la discrepancia.</span><span class="sxs-lookup"><span data-stu-id="ea41a-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="ea41a-192">Probar el modelo</span><span class="sxs-lookup"><span data-stu-id="ea41a-192">Test your model</span></span>

<span data-ttu-id="ea41a-193">Si ha recibido una coincidencia en los archivos de ejemplo con la etiqueta, ahora puede probar el modelo en los restantes archivos de ejemplo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ea41a-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="ea41a-194">En la Página principal del modelo, haga clic en la pestaña **prueba** .  Esto hará que se ejecute el modelo en los archivos de ejemplo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ea41a-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="ea41a-195">En la lista **archivos de prueba** , se mostrarán los archivos de ejemplo y se mostrará si el modelo predictó como ejemplos positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="ea41a-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="ea41a-196">Puede usar esta información para ayudar a determinar la eficacia del clasificador en la identificación de los documentos.</span><span class="sxs-lookup"><span data-stu-id="ea41a-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Prueba de archivos sin etiquetar](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="ea41a-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea41a-198">See Also</span></span>
[<span data-ttu-id="ea41a-199">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="ea41a-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="ea41a-200">Información general sobre el documento</span><span class="sxs-lookup"><span data-stu-id="ea41a-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="ea41a-201">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="ea41a-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="ea41a-202">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="ea41a-202">Apply a model</span></span>](apply-a-model.md) 




