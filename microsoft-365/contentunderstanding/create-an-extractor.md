---
title: Crear un extractor (versión preliminar)
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
description: Obtener información sobre cómo crear un extractor
ms.openlocfilehash: 7219726fb385d0b67f7ee0614f5075ba226140ab
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950089"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="c203b-103">Crear un extractor (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c203b-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="c203b-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="c203b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c203b-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c203b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="c203b-106">Ya sea antes o después de crear un modelo de clasificador para automatizar la identificación y clasificación de tipos de documentos específicos, también puede elegir agregar extractores al modelo para extraer información específica de estos documentos.</span><span class="sxs-lookup"><span data-stu-id="c203b-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="c203b-107">Por ejemplo, es posible que desee que el modelo no solo identifique todos los documentos de *renovación de contratos* que se agreguen a la biblioteca de documentos, sino que muestre la fecha de *Inicio del servicio* de cada documento como una columna en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="c203b-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="c203b-108">Debe crear un extractor para cada entidad en el documento que desea extraer.</span><span class="sxs-lookup"><span data-stu-id="c203b-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="c203b-109">En nuestro ejemplo, queremos extraer la fecha de *Inicio del servicio* para cada documento de *renovación de contrato* identificado por el modelo.</span><span class="sxs-lookup"><span data-stu-id="c203b-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="c203b-110">Queremos ver una vista en la biblioteca de documentos de todos los documentos de *renovación de contratos* , con una columna que muestra el valor de fecha de inicio de servicio de cada documento.</span><span class="sxs-lookup"><span data-stu-id="c203b-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="c203b-111">Antes de crear un extractor, debe [Agregar los archivos de ejemplo](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) que necesita para entrenar el modelo para que identifique la información que desea extraer.</span><span class="sxs-lookup"><span data-stu-id="c203b-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="c203b-112">Use los mismos archivos de ejemplo que usó para crear su clasificador.</span><span class="sxs-lookup"><span data-stu-id="c203b-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="c203b-113">Nombre del extractor</span><span class="sxs-lookup"><span data-stu-id="c203b-113">Name your extractor</span></span>

1. <span data-ttu-id="c203b-114">En la Página principal del modelo, en el mosaico **crear y entrenar extractor** , haga clic en **entrenar extractor**.</span><span class="sxs-lookup"><span data-stu-id="c203b-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="c203b-115">En la pantalla **nuevo extractor de entidades** , escriba el nombre del extractor en el campo **nombre del extractor nuevo** .</span><span class="sxs-lookup"><span data-stu-id="c203b-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="c203b-116">Por ejemplo, podemos nombrar la **fecha de inicio del servicio** de ti si queremos extraer la fecha de inicio del servicio de cada documento de renovación de contrato.</span><span class="sxs-lookup"><span data-stu-id="c203b-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="c203b-117">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c203b-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="c203b-118">Agregar una etiqueta</span><span class="sxs-lookup"><span data-stu-id="c203b-118">Add a label</span></span>

<span data-ttu-id="c203b-119">El siguiente paso consiste en etiquetar la información que desea extraer en los archivos de formación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c203b-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="c203b-120">Al crear el extractor se abrirá la página del extractor en la que verá una lista de los archivos de ejemplo, con el primer archivo de la lista que se muestra en el visor.</span><span class="sxs-lookup"><span data-stu-id="c203b-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="c203b-121">En el visor, seleccione los datos que desea extraer de los archivos.</span><span class="sxs-lookup"><span data-stu-id="c203b-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="c203b-122">Por ejemplo, si desea extraer la fecha de *Inicio del servicio*, resaltará el valor de fecha correspondiente en el primer archivo (*lunes, 14 de octubre de 2019*).</span><span class="sxs-lookup"><span data-stu-id="c203b-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="c203b-123">Después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c203b-123">Then click **Save**.</span></span>  <span data-ttu-id="c203b-124">Verá el valor que se muestra para el archivo en la lista de ejemplos con etiquetas en la columna **etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="c203b-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="c203b-125">Seleccione **archivo siguiente** para autoguardar y abra el archivo siguiente de la lista en el visor, o bien, seleccione **Guardar** y seleccione otro archivo en la lista de **ejemplos con etiquetas** .</span><span class="sxs-lookup"><span data-stu-id="c203b-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="c203b-126">En el visor, repita los pasos 1 y 2, y haga esto hasta que haya guardado la etiqueta en cinco archivos.</span><span class="sxs-lookup"><span data-stu-id="c203b-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Configuración avanzada](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="c203b-128">Agregar un ejemplo negativo</span><span class="sxs-lookup"><span data-stu-id="c203b-128">Add a negative example</span></span>

<span data-ttu-id="c203b-129">De forma similar a como se agregaría un archivo de ejemplo negativo al crear un clasificador, necesita agregar un ejemplo negativo para el extractor.</span><span class="sxs-lookup"><span data-stu-id="c203b-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="c203b-130">En nuestro ejemplo, debería ser un archivo que no contenga un valor de fecha de inicio de servicio.</span><span class="sxs-lookup"><span data-stu-id="c203b-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="c203b-131">En la lista de **ejemplos con etiquetas** , seleccione un ejemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="c203b-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="c203b-132">En el visor, en la parte superior del artículo, seleccione **sin etiqueta presente**.</span><span class="sxs-lookup"><span data-stu-id="c203b-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="c203b-133">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c203b-133">Click **Save**.</span></span>
 
<span data-ttu-id="c203b-134">Una vez que haya etiquetado cinco archivos, se mostrará un banner de notificación que le indicará que debe cambiar a aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="c203b-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="c203b-135">Puede elegir más documentos o avanzar a la formación.</span><span class="sxs-lookup"><span data-stu-id="c203b-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="c203b-136">Agregar una explicación</span><span class="sxs-lookup"><span data-stu-id="c203b-136">Add an explanation</span></span>

<span data-ttu-id="c203b-137">En nuestro ejemplo, vamos a crear una explicación que proporcione una sugerencia sobre el mismo formato de entidad y las variantes que puede tener en los documentos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c203b-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="c203b-138">Por ejemplo, un valor de fecha puede estar en varios formatos diferentes, como:</span><span class="sxs-lookup"><span data-stu-id="c203b-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="c203b-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="c203b-139">10/14/2019</span></span>
- <span data-ttu-id="c203b-140">14 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="c203b-140">October 14, 2019</span></span>
- <span data-ttu-id="c203b-141">Lunes, 14 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="c203b-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="c203b-142">Para ayudar a identificar la *fecha de inicio del servicio* , puede crear una explicación de la trama.</span><span class="sxs-lookup"><span data-stu-id="c203b-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="c203b-143">En la sección explicación, seleccione **nuevo**y, a continuación, escriba un nombre (por ejemplo, *fecha*).</span><span class="sxs-lookup"><span data-stu-id="c203b-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="c203b-144">Para el tipo, seleccione la **lista trama**.</span><span class="sxs-lookup"><span data-stu-id="c203b-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="c203b-145">Para el valor, debe proporcionar la variación de fecha a medida que aparecen en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c203b-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="c203b-146">Por ejemplo, si tiene formatos de fecha que aparecen como 0/00/0000, tendría que especificar cualquier variación que aparezca en los documentos, como:</span><span class="sxs-lookup"><span data-stu-id="c203b-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="c203b-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="c203b-147">0/0/0000</span></span>
    - <span data-ttu-id="c203b-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="c203b-148">0/00/0000</span></span>
    - <span data-ttu-id="c203b-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="c203b-149">00/0/0000</span></span>
    - <span data-ttu-id="c203b-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="c203b-150">00/00/0000</span></span>
4. <span data-ttu-id="c203b-151">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c203b-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="c203b-152">Usar la biblioteca de explicación</span><span class="sxs-lookup"><span data-stu-id="c203b-152">Use the Explanation library</span></span>

<span data-ttu-id="c203b-153">Para crear explicaciones para cosas como fechas, es mucho más fácil usar la biblioteca de explicación que especificar manualmente todas las variantes.</span><span class="sxs-lookup"><span data-stu-id="c203b-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="c203b-154">La biblioteca de explicación es un conjunto de frases predefinidas y explicaciones de patrones.</span><span class="sxs-lookup"><span data-stu-id="c203b-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="c203b-155">La biblioteca intenta proporcionar todos los formatos para las listas de patrones o frases comunes, como fechas, números de teléfono, código postal y muchas otras.</span><span class="sxs-lookup"><span data-stu-id="c203b-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="c203b-156">Para nuestro ejemplo de *fecha de inicio de servicio* , es más eficaz usar la explicación predefinida para *Date* en la biblioteca de explicación:</span><span class="sxs-lookup"><span data-stu-id="c203b-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="c203b-157">En la **sección explicación**, \* \* seleccione **nuevo**y, a continuación, seleccione **de la biblioteca de explicación**.</span><span class="sxs-lookup"><span data-stu-id="c203b-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="c203b-158">En la biblioteca de explicación, seleccione **fecha**.</span><span class="sxs-lookup"><span data-stu-id="c203b-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="c203b-159">Puede ver todas las variaciones de fecha que se reconocerán.</span><span class="sxs-lookup"><span data-stu-id="c203b-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="c203b-160">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c203b-160">Select **Add**.</span></span></br>

    ![Biblioteca de explicación](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="c203b-162">En la página **crear una explicación** , la información de *fecha* de la biblioteca de explicación rellenará los campos.</span><span class="sxs-lookup"><span data-stu-id="c203b-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="c203b-163">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c203b-163">Select **Save**.</span></span></br>

    ![Biblioteca de explicación](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="c203b-165">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="c203b-165">Train the model</span></span> 

<span data-ttu-id="c203b-166">Al guardar la explicación se iniciará el curso.</span><span class="sxs-lookup"><span data-stu-id="c203b-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="c203b-167">Si el modelo tiene información suficiente para extraer los datos de los archivos de ejemplo con la etiqueta, verá cada archivo con la etiqueta **coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="c203b-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Biblioteca de explicación](../media/content-understanding/match2.png) 

<span data-ttu-id="c203b-169">Si la explicación no tiene suficiente información para encontrar los datos que desea extraer, los archivos se etiquetarán con una etiqueta que no **coincide**.</span><span class="sxs-lookup"><span data-stu-id="c203b-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="c203b-170">Puede hacer clic en los archivos no coincidentes para ver más información sobre los motivos por los que se ha producido un error de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c203b-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="c203b-171">Agregar otra explicación</span><span class="sxs-lookup"><span data-stu-id="c203b-171">Add another explanation</span></span>

<span data-ttu-id="c203b-172">A menudo, la falta de coincidencia es una indicación de que la explicación proporcionada no proporcionó suficiente información para extraer el valor de fecha de inicio de servicio para que coincida con los archivos etiquetados.</span><span class="sxs-lookup"><span data-stu-id="c203b-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="c203b-173">Es posible que tenga que editarla o agregar otra explicación.</span><span class="sxs-lookup"><span data-stu-id="c203b-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="c203b-174">En nuestro ejemplo, se observa que la *fecha de inicio del servicio de* la cadena de texto siempre precede al valor real.</span><span class="sxs-lookup"><span data-stu-id="c203b-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="c203b-175">Para ayudar a identificar la fecha de inicio del servicio, podemos crear una explicación de la frase.</span><span class="sxs-lookup"><span data-stu-id="c203b-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="c203b-176">En la sección explicación, seleccione **nuevo**y, a continuación, escriba un nombre (por ejemplo, *cadena de prefijo*).</span><span class="sxs-lookup"><span data-stu-id="c203b-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="c203b-177">Para el tipo, seleccione **lista de frases**.</span><span class="sxs-lookup"><span data-stu-id="c203b-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="c203b-178">Use la *fecha de inicio del servicio* como valor.</span><span class="sxs-lookup"><span data-stu-id="c203b-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="c203b-179">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c203b-179">Select **Save**.</span></span>

    ![Biblioteca de explicación](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="c203b-181">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="c203b-181">Train the model</span></span>

<span data-ttu-id="c203b-182">Al guardar la explicación, se iniciará el aprendizaje de nuevo, esta vez con las explicaciones en nuestro ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c203b-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="c203b-183">Si el modelo tiene información suficiente para extraer los datos de los archivos de ejemplo con la etiqueta, verá cada archivo con la etiqueta **coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="c203b-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="c203b-184">Si vuelve a recibir una **falta de coincidencia** en los archivos etiquetados, es posible que tenga que crear otra explicación para proporcionar al modelo más información para identificar el tipo de documento o realizar cambios en los existentes.</span><span class="sxs-lookup"><span data-stu-id="c203b-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="c203b-185">Probar el modelo</span><span class="sxs-lookup"><span data-stu-id="c203b-185">Test your model</span></span>

<span data-ttu-id="c203b-186">Si ha recibido una coincidencia en los archivos de ejemplo con la etiqueta, ahora puede probar el modelo en los restantes archivos de ejemplo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c203b-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="c203b-187">En la Página principal del modelo, haga clic en la pestaña **prueba** .  Esto hará que se ejecute el modelo en los archivos de ejemplo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c203b-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="c203b-188">En la lista **archivos de prueba** , se mostrarán los archivos de ejemplo y se mostrará si el modelo puede extraer la información que necesita.</span><span class="sxs-lookup"><span data-stu-id="c203b-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="c203b-189">Puede usar esta información para ayudar a determinar la eficacia del clasificador en la identificación de los documentos.</span><span class="sxs-lookup"><span data-stu-id="c203b-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Probar los archivos](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="c203b-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c203b-191">See Also</span></span>
  




