---
title: Crear un extractor
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
description: Obtenga información sobre cómo crear un extractor en Microsoft SharePoint Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295461"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="aa058-103">Crear un extractor (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aa058-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="aa058-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="aa058-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="aa058-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="aa058-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="aa058-106">Antes o después de crear un modelo de clasificador para automatizar la identificación y la clasificación de los tipos de documentos específicos, puede elegir opcionalmente agregar extractores al modelo para extraer información específica de estos documentos.</span><span class="sxs-lookup"><span data-stu-id="aa058-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="aa058-107">Por ejemplo, es posible que desee que el modelo no solo identifique todos los documentos de *renovación de contratos* agregados a la biblioteca de documentos, sino que también muestre la fecha de *Inicio del servicio* de cada documento como una columna en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="aa058-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="aa058-108">Debe crear un extractor para cada entidad en el documento que desea extraer.</span><span class="sxs-lookup"><span data-stu-id="aa058-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="aa058-109">En el ejemplo, desea extraer la fecha de *Inicio del servicio* de cada documento de *renovación de contratos* que se identifica por el modelo.</span><span class="sxs-lookup"><span data-stu-id="aa058-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="aa058-110">Esto debe suceder cuando desea ver una vista en la biblioteca de documentos de todos los documentos de *renovación de contratos* con una columna que muestra el valor de fecha de inicio de servicio para cada documento.</span><span class="sxs-lookup"><span data-stu-id="aa058-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="aa058-111">Antes de crear un extractor, debe [Agregar los archivos de ejemplo](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) para ayudar a entrenar el modelo para que identifique la información que desea extraer.</span><span class="sxs-lookup"><span data-stu-id="aa058-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="aa058-112">Use los mismos archivos de ejemplo que usó para crear su clasificador.</span><span class="sxs-lookup"><span data-stu-id="aa058-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="aa058-113">Nombre del extractor</span><span class="sxs-lookup"><span data-stu-id="aa058-113">Name your extractor</span></span>

1. <span data-ttu-id="aa058-114">En el cuadro **crear y entrenar extractor** de la Página principal del modelo, haga clic en **extractor de tren**.</span><span class="sxs-lookup"><span data-stu-id="aa058-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="aa058-115">En la pantalla **nuevo extractor de entidades** , escriba el nombre del extractor en el campo **nombre del extractor nuevo** .</span><span class="sxs-lookup"><span data-stu-id="aa058-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="aa058-116">Por ejemplo, denomine **fecha de inicio del servicio** de ti si desea extraer la fecha de inicio del servicio de cada documento de renovación de contratos.</span><span class="sxs-lookup"><span data-stu-id="aa058-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="aa058-117">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="aa058-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="aa058-118">Agregar una etiqueta</span><span class="sxs-lookup"><span data-stu-id="aa058-118">Add a label</span></span>

<span data-ttu-id="aa058-119">El siguiente paso consiste en etiquetar la información que desea extraer en los archivos de formación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aa058-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="aa058-120">Crear el extractor abre la página extractor.</span><span class="sxs-lookup"><span data-stu-id="aa058-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="aa058-121">Aquí verá una lista de los archivos de ejemplo, con el primer archivo de la lista que se muestra en el visor.</span><span class="sxs-lookup"><span data-stu-id="aa058-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="aa058-122">En el visor, seleccione los datos que desea extraer de los archivos.</span><span class="sxs-lookup"><span data-stu-id="aa058-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="aa058-123">Por ejemplo, si desea extraer la fecha de *Inicio del servicio*, resaltará el valor de fecha en el primer archivo (*lunes, 14 de octubre, 2019*).</span><span class="sxs-lookup"><span data-stu-id="aa058-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="aa058-124">y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa058-124">and then click **Save**.</span></span>  <span data-ttu-id="aa058-125">Debe ver el valor mostrado del archivo en la lista de ejemplos con etiquetas, en la columna **etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="aa058-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="aa058-126">Seleccione **archivo siguiente** para guardar automáticamente y abrir el archivo siguiente de la lista en el visor.</span><span class="sxs-lookup"><span data-stu-id="aa058-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="aa058-127">O bien, seleccione **Guardar** y, a continuación, seleccione otro archivo en la lista de **ejemplos con etiquetas** .</span><span class="sxs-lookup"><span data-stu-id="aa058-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="aa058-128">En el visor, repita los pasos 1 y 2 y, a continuación, repita este procedimiento hasta que haya guardado la etiqueta en los cinco archivos.</span><span class="sxs-lookup"><span data-stu-id="aa058-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Configuración avanzada](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="aa058-130">Agregar un ejemplo negativo</span><span class="sxs-lookup"><span data-stu-id="aa058-130">Add a negative example</span></span>

<span data-ttu-id="aa058-131">De forma similar a como agrega un archivo de ejemplo negativo al crear un clasificador, necesita agregar una muestra negativa para el extractor.</span><span class="sxs-lookup"><span data-stu-id="aa058-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="aa058-132">Debe ser un archivo que no contenga un valor de fecha de "Inicio de servicio".</span><span class="sxs-lookup"><span data-stu-id="aa058-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="aa058-133">En la lista de **ejemplos con etiquetas** , seleccione un ejemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="aa058-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="aa058-134">En el visor que se encuentra en la parte superior del artículo, seleccione **sin etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="aa058-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="aa058-135">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="aa058-135">Click **Save**.</span></span>
 
<span data-ttu-id="aa058-136">Una vez que haya etiquetado cinco archivos, aparecerá un banner de notificación que le informará de que debe cambiar a Training.</span><span class="sxs-lookup"><span data-stu-id="aa058-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="aa058-137">Puede elegir más documentos o avanzar a la formación.</span><span class="sxs-lookup"><span data-stu-id="aa058-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="aa058-138">Agregar una explicación</span><span class="sxs-lookup"><span data-stu-id="aa058-138">Add an explanation</span></span>

<span data-ttu-id="aa058-139">Para el ejemplo, se crea una explicación que proporciona una sugerencia sobre el mismo formato de entidad y las variaciones que puede tener en los documentos de muestra.</span><span class="sxs-lookup"><span data-stu-id="aa058-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="aa058-140">Por ejemplo, un valor de fecha puede estar en varios formatos diferentes, como:</span><span class="sxs-lookup"><span data-stu-id="aa058-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="aa058-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="aa058-141">10/14/2019</span></span>
- <span data-ttu-id="aa058-142">14 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="aa058-142">October 14, 2019</span></span>
- <span data-ttu-id="aa058-143">Lunes, 14 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="aa058-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="aa058-144">Para ayudar a identificar la *fecha de inicio del servicio* , cree una explicación de la trama.</span><span class="sxs-lookup"><span data-stu-id="aa058-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="aa058-145">En la sección explicación, seleccione **nuevo** y escriba un nombre (por ejemplo, *fecha*).</span><span class="sxs-lookup"><span data-stu-id="aa058-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="aa058-146">En tipo, seleccione **lista de tramas**.</span><span class="sxs-lookup"><span data-stu-id="aa058-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="aa058-147">En valor, especifique la variación de fecha tal y como aparece en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aa058-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="aa058-148">Por ejemplo, si tiene formatos de fecha que aparecen como 0/00/0000, especifique cualquier variación que aparezca en los documentos, como:</span><span class="sxs-lookup"><span data-stu-id="aa058-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="aa058-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="aa058-149">0/0/0000</span></span>
    - <span data-ttu-id="aa058-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="aa058-150">0/00/0000</span></span>
    - <span data-ttu-id="aa058-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="aa058-151">00/0/0000</span></span>
    - <span data-ttu-id="aa058-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="aa058-152">00/00/0000</span></span>
4. <span data-ttu-id="aa058-153">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa058-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="aa058-154">Usar la biblioteca de explicación</span><span class="sxs-lookup"><span data-stu-id="aa058-154">Use the Explanation library</span></span>

<span data-ttu-id="aa058-155">Para crear explicaciones de elementos como fechas, es más fácil usar la biblioteca de explicación que especificar manualmente todas las variantes.</span><span class="sxs-lookup"><span data-stu-id="aa058-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="aa058-156">La biblioteca de explicación es un conjunto de frases predefinidas y explicaciones de patrones.</span><span class="sxs-lookup"><span data-stu-id="aa058-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="aa058-157">La biblioteca proporciona todos los formatos para las listas de patrones o frases comunes, como fechas, números de teléfono, código postal, etc.</span><span class="sxs-lookup"><span data-stu-id="aa058-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="aa058-158">Para la muestra de *fecha de inicio de servicio* , es más eficaz usar la explicación predefinida para la *fecha* en la biblioteca de explicación:</span><span class="sxs-lookup"><span data-stu-id="aa058-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="aa058-159">En la **sección explicación**, seleccione **nuevo**y, a continuación, seleccione **de la biblioteca de explicación**.</span><span class="sxs-lookup"><span data-stu-id="aa058-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="aa058-160">En la biblioteca de explicación, seleccione **fecha**.</span><span class="sxs-lookup"><span data-stu-id="aa058-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="aa058-161">Puede ver todas las variaciones de fecha que se reconocen.</span><span class="sxs-lookup"><span data-stu-id="aa058-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="aa058-162">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="aa058-162">Select **Add**.</span></span></br>

    ![Biblioteca de explicación](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="aa058-164">En la página **crear una explicación** , la información de *fecha* de la biblioteca de explicación rellena automáticamente los campos.</span><span class="sxs-lookup"><span data-stu-id="aa058-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="aa058-165">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa058-165">Select **Save**.</span></span></br>

    ![Fecha](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="aa058-167">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="aa058-167">Train the model</span></span> 

<span data-ttu-id="aa058-168">Al guardar la explicación se inicia el curso.</span><span class="sxs-lookup"><span data-stu-id="aa058-168">Saving your explanation start the training.</span></span> <span data-ttu-id="aa058-169">Si el modelo tiene información suficiente para extraer los datos de los archivos de ejemplo con la etiqueta, verá cada archivo con la etiqueta **coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="aa058-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Coincidir](../media/content-understanding/match2.png) 

<span data-ttu-id="aa058-171">Si la explicación no tiene suficiente información para encontrar los datos que desea extraer, los archivos se etiquetarán con una etiqueta que no **coincide**.</span><span class="sxs-lookup"><span data-stu-id="aa058-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="aa058-172">Puede hacer clic en los archivos no **coincidentes** para ver más información sobre los motivos por los que se ha producido un error de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="aa058-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="aa058-173">Agregar otra explicación</span><span class="sxs-lookup"><span data-stu-id="aa058-173">Add another explanation</span></span>

<span data-ttu-id="aa058-174">A menudo, la falta de coincidencia es una indicación de que la explicación proporcionada no proporcionó suficiente información para extraer el valor de fecha de inicio de servicio para que coincida con los archivos etiquetados.</span><span class="sxs-lookup"><span data-stu-id="aa058-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="aa058-175">Es posible que tenga que editarla o agregar otra explicación.</span><span class="sxs-lookup"><span data-stu-id="aa058-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="aa058-176">Para la muestra, observe que la *fecha de inicio del servicio de* la cadena de texto siempre precede al valor real.</span><span class="sxs-lookup"><span data-stu-id="aa058-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="aa058-177">Para ayudar a identificar la fecha de inicio del servicio, debe crear una explicación de la frase.</span><span class="sxs-lookup"><span data-stu-id="aa058-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="aa058-178">En la sección explicación, seleccione **nuevo**y, a continuación, escriba un nombre (por ejemplo, *cadena de prefijo*).</span><span class="sxs-lookup"><span data-stu-id="aa058-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="aa058-179">Para el tipo, seleccione **lista de frases**.</span><span class="sxs-lookup"><span data-stu-id="aa058-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="aa058-180">Use la *fecha de inicio del servicio* como valor.</span><span class="sxs-lookup"><span data-stu-id="aa058-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="aa058-181">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa058-181">Select **Save**.</span></span>

    ![Cadena de prefijo](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="aa058-183">Volver a entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="aa058-183">Train the model again</span></span>

<span data-ttu-id="aa058-184">Al guardar la explicación, se vuelve a iniciar el programa de aprendizaje, esta vez con las explicaciones del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aa058-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="aa058-185">Si el modelo tiene información suficiente para extraer los datos de los archivos de ejemplo con la etiqueta, verá cada archivo con la etiqueta **coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="aa058-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="aa058-186">Si vuelve a recibir una **falta de coincidencia** en los archivos etiquetados, es probable que deba crear otra explicación para proporcionar al modelo más información para identificar el tipo de documento o considerar la posibilidad de realizar cambios en el modelo de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aa058-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="aa058-187">Probar el modelo</span><span class="sxs-lookup"><span data-stu-id="aa058-187">Test your model</span></span>

<span data-ttu-id="aa058-188">Si recibe una coincidencia en los archivos de ejemplo con la etiqueta, ahora puede probar el modelo en los restantes archivos de ejemplo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="aa058-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="aa058-189">En la Página principal del modelo, haga clic en la pestaña **prueba** .  Esto ejecuta el modelo en los archivos de ejemplo sin etiqueta.</span><span class="sxs-lookup"><span data-stu-id="aa058-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="aa058-190">En la lista **archivos de prueba** , se muestran los archivos de ejemplo para mostrar si el modelo puede extraer la información que necesita.</span><span class="sxs-lookup"><span data-stu-id="aa058-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="aa058-191">Use esta información para ayudar a determinar la eficacia del clasificador en la identificación de los documentos.</span><span class="sxs-lookup"><span data-stu-id="aa058-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Probar los archivos](../media/content-understanding/test-filies-extractor.png) 
