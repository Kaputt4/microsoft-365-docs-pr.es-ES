---
title: Crear un extractor
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Obtener información sobre cómo crear un extractor en Microsoft SharePoint Syntex.
ms.openlocfilehash: b957d905f3807f6007ebeb742d9b56d81ea38ac2
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701134"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="02464-103">Crear un extractor en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="02464-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="02464-104">Antes o después de crear un modelo de clasificación para automatizar la identificación y la clasificación de tipos de documentos específicos, puede optar por agregar extractores a su modelo para extraer información específica de estos documentos.</span><span class="sxs-lookup"><span data-stu-id="02464-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="02464-105">Por ejemplo, es posible que desee que su modelo no sólo identifique todos los documentos de *Renovación de contrato* agregados a su biblioteca de documentos, sino que también muestre la *Fecha inicial del servicio* de cada documento como un valor de columna en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="02464-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="02464-106">Es necesario crear un extractor para cada entidad del documento que se desea extraer.</span><span class="sxs-lookup"><span data-stu-id="02464-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="02464-107">En nuestro ejemplo, queremos extraer la  **Fecha inicial del servicio**  para cada  **Renovación de contrato**  de contrato identificado por el modelo.</span><span class="sxs-lookup"><span data-stu-id="02464-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="02464-108">Queremos tener la posibilidad de tener una visión en la biblioteca de documentos de todos los documentos de  **Renovación de contratos** , con una columna que muestre el valor de la fecha de **Inicio del servicio** de cada documento.</span><span class="sxs-lookup"><span data-stu-id="02464-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="02464-109">Para crear un extractor, utilice los mismos archivos que ha subido previamente para entrenar al clasificador.</span><span class="sxs-lookup"><span data-stu-id="02464-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="02464-110">Asigne un nombre a su extractor</span><span class="sxs-lookup"><span data-stu-id="02464-110">Name your extractor</span></span>

1. <span data-ttu-id="02464-111">En la página de inicio del modelo, en el ícono **Crear y entrenar extractores**, haga clic en **Entrenar extractor**.</span><span class="sxs-lookup"><span data-stu-id="02464-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="02464-112">En la pantalla del extractor de **Nueva entidad**, escriba el nombre de su extractor en el campo **Nombre del nuevo extractor**.</span><span class="sxs-lookup"><span data-stu-id="02464-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="02464-113">Por ejemplo, llámelo **Fecha de inicio del servicio** si desea extraer la fecha de inicio del servicio de cada documento de renovación de contrato.</span><span class="sxs-lookup"><span data-stu-id="02464-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="02464-114">También puede optar por reutilizar una columna creada previamente (por ejemplo, una columna de metadatos administrados).</span><span class="sxs-lookup"><span data-stu-id="02464-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
> [!NOTE]
> <span data-ttu-id="02464-115">Si crea un nuevo extractor, seleccione **Nuevo tipo de columna** y elija **Una línea de texto**, el límite máximo de caracteres es 255.</span><span class="sxs-lookup"><span data-stu-id="02464-115">If you create a new extractor, then select **New column type** and choose **Single line of text**, the maximum character limit is 255.</span></span> <span data-ttu-id="02464-116">Cualquier carácter que escriba que exceda el límite se trunca.</span><span class="sxs-lookup"><span data-stu-id="02464-116">Any characters that you type exceeding the limit get truncated.</span></span> 
3. <span data-ttu-id="02464-117">Cuando termine, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="02464-117">When you're done, click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="02464-118">Agregar una etiqueta</span><span class="sxs-lookup"><span data-stu-id="02464-118">Add a label</span></span>

<span data-ttu-id="02464-119">El siguiente paso es etiquetar la entidad que desea extraer en sus archivos de entrenamiento de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02464-119">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="02464-120">Al crear el extractor se abre la página del extractor.</span><span class="sxs-lookup"><span data-stu-id="02464-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="02464-121">Aquí puede ver una lista de sus archivos de muestra, con el primer archivo de la lista mostrado en el visor.</span><span class="sxs-lookup"><span data-stu-id="02464-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="02464-122">En el visor, seleccione los datos que desea extraer de los archivos.</span><span class="sxs-lookup"><span data-stu-id="02464-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="02464-123">Por ejemplo, si se quiere extraer la *Fecha de inicio del servicio*, se resalta el valor de la fecha en el primer archivo (*lunes 14 de octubre de 2019*).</span><span class="sxs-lookup"><span data-stu-id="02464-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="02464-124">luego haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="02464-124">and then click **Save**.</span></span>  <span data-ttu-id="02464-125">Debería ver la visualización del valor del archivo en la lista de ejemplos etiquetados, bajo la columna **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="02464-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="02464-126">Seleccione **Siguiente archivo** para guardarlo automáticamente y abra el siguiente archivo de la lista en el visor.</span><span class="sxs-lookup"><span data-stu-id="02464-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="02464-127">O seleccione **Guardar** y luego seleccione otro archivo de la lista de **Ejemplos etiquetados**.</span><span class="sxs-lookup"><span data-stu-id="02464-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="02464-128">En el visor, repita los pasos 1 y 2, y luego repita hasta que haya guardado la etiqueta en los cinco archivos.</span><span class="sxs-lookup"><span data-stu-id="02464-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Configuración avanzada](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="02464-130">Una vez que etiquetó cinco archivos, se muestra un banner de notificación que le informa de pasar al entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="02464-130">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="02464-131">Puedes elegir entre etiquetar más documentos o avanzar a la formación.</span><span class="sxs-lookup"><span data-stu-id="02464-131">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="02464-132">Agregue una explicación</span><span class="sxs-lookup"><span data-stu-id="02464-132">Add an explanation</span></span>

<span data-ttu-id="02464-133">Para nuestro ejemplo, vamos a crear una explicación que proporciona una pista sobre el formato de la entidad en sí y las variaciones que puede tener en los documentos de muestra.</span><span class="sxs-lookup"><span data-stu-id="02464-133">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="02464-134">Por ejemplo, el valor de una fecha puede estar en varios formatos diferentes, como:</span><span class="sxs-lookup"><span data-stu-id="02464-134">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="02464-135">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="02464-135">10/14/2019</span></span>
- <span data-ttu-id="02464-136">14 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="02464-136">October 14, 2019</span></span>
- <span data-ttu-id="02464-137">Lunes 14 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="02464-137">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="02464-138">Para ayudar a identificar la *Fecha de inicio del servicio*, puede crear una explicación del patrón.</span><span class="sxs-lookup"><span data-stu-id="02464-138">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="02464-139">En la sección de Explicación, seleccione **Nuevo** y escriba un nombre (por ejemplo, *Fecha*).</span><span class="sxs-lookup"><span data-stu-id="02464-139">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="02464-140">Para Tipo, seleccione **Lista de patrones**.</span><span class="sxs-lookup"><span data-stu-id="02464-140">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="02464-141">Para el Valor, proporcione la variación de la fecha tal como aparece en los archivos de muestra.</span><span class="sxs-lookup"><span data-stu-id="02464-141">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="02464-142">Por ejemplo, si tiene formatos de fecha que aparecen como 0/00/0000, introduzca cualquier variación que aparezca en sus documentos, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02464-142">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="02464-143">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="02464-143">0/0/0000</span></span>
    - <span data-ttu-id="02464-144">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="02464-144">0/00/0000</span></span>
    - <span data-ttu-id="02464-145">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="02464-145">00/0/0000</span></span>
    - <span data-ttu-id="02464-146">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="02464-146">00/00/0000</span></span>
4. <span data-ttu-id="02464-147">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="02464-147">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="02464-148">Para obtener más información sobre los tipos de explicación, consulte [Tipos de explicación](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview)..</span><span class="sxs-lookup"><span data-stu-id="02464-148">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="02464-149">Usar la biblioteca de explicación</span><span class="sxs-lookup"><span data-stu-id="02464-149">Use the Explanation library</span></span>

<span data-ttu-id="02464-150">Para crear explicaciones para elementos como las fechas, es más fácil [utilizar la biblioteca de explicaciones ](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library)que introducir manualmente todas las variaciones.</span><span class="sxs-lookup"><span data-stu-id="02464-150">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="02464-151">La biblioteca de explicaciones es un conjunto de explicaciones de frases y patrones pre generados.</span><span class="sxs-lookup"><span data-stu-id="02464-151">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="02464-152">La biblioteca trata de proporcionar todos los formatos de listas, frases o patrones comunes, como fechas, números de teléfono, códigos postales y muchos otros.</span><span class="sxs-lookup"><span data-stu-id="02464-152">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="02464-153">Para la muestra de la *Fecha de inicio del servicio*, es más eficiente usar la explicación pre generada para *Fecha* en la biblioteca de explicaciones:</span><span class="sxs-lookup"><span data-stu-id="02464-153">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="02464-154">En la sección de **Explicación**, seleccione **Nuevo**, y luego seleccione **Desde la biblioteca de explicaciones**.</span><span class="sxs-lookup"><span data-stu-id="02464-154">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="02464-155">En la biblioteca de explicación, seleccione **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="02464-155">From the explanation library, select **Date**.</span></span> <span data-ttu-id="02464-156">Puede ver todas las variaciones de fecha que son reconocidas</span><span class="sxs-lookup"><span data-stu-id="02464-156">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="02464-157">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="02464-157">Select **Add**.</span></span></br>

    ![Biblioteca de explicación](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="02464-159">En la página **Crear una explicación**, la información de la *Fecha* de la biblioteca de explicaciones rellena automáticamente los campos.</span><span class="sxs-lookup"><span data-stu-id="02464-159">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="02464-160">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="02464-160">Select **Save**.</span></span></br>

    ![Fecha](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="02464-162">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="02464-162">Train the model</span></span> 

<span data-ttu-id="02464-163">Guardando su explicación inicio del entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="02464-163">Saving your explanation start the training.</span></span> <span data-ttu-id="02464-164">Si su modelo tiene suficiente información para extraer los datos de los archivos de ejemplo etiquetados, verá cada archivo etiquetado con **Coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="02464-164">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Coincidencia](../media/content-understanding/match2.png) 

<span data-ttu-id="02464-166">Si la explicación no tiene suficiente información para encontrar los datos que quiere extraer, cada archivo será etiquetado con **No coincide**.</span><span class="sxs-lookup"><span data-stu-id="02464-166">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="02464-167">Puede hacer clic en los archivos de **No coincide** para ver más información sobre por qué no coincide.</span><span class="sxs-lookup"><span data-stu-id="02464-167">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="02464-168">Agregar otra explicación</span><span class="sxs-lookup"><span data-stu-id="02464-168">Add another explanation</span></span>

<span data-ttu-id="02464-169">A menudo la no coincidencia es una indicación de que la explicación que dimos no proporcionó suficiente información para extraer el valor de la fecha de inicio del servicio para que coincida con nuestros archivos etiquetados.</span><span class="sxs-lookup"><span data-stu-id="02464-169">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="02464-170">Puede que necesite editarlo, o agregar otra explicación.</span><span class="sxs-lookup"><span data-stu-id="02464-170">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="02464-171">Para nuestro ejemplo, note que la cadena de texto *Fecha de Inicio del servicio de* siempre precede al valor real.</span><span class="sxs-lookup"><span data-stu-id="02464-171">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="02464-172">Para ayudar a identificar la fecha de Inicio del servicio, necesita crear una frase de explicación.</span><span class="sxs-lookup"><span data-stu-id="02464-172">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="02464-173">En la sección de Explicación, seleccione **Nuevo**, y luego escriba un nombre (por ejemplo, *Cadena de prefijos*).</span><span class="sxs-lookup"><span data-stu-id="02464-173">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="02464-174">Para el Tipo, seleccione **Lista de frases**.</span><span class="sxs-lookup"><span data-stu-id="02464-174">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="02464-175">Utilice la *Fecha de inicio del servicio de* como valor.</span><span class="sxs-lookup"><span data-stu-id="02464-175">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="02464-176">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="02464-176">Select **Save**.</span></span>

    ![Cadena de prefijo](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="02464-178">Entrenar el modelo de nuevo</span><span class="sxs-lookup"><span data-stu-id="02464-178">Train the model again</span></span>

<span data-ttu-id="02464-179">Guardando la explicación inicie el entrenamiento de nuevo, esta vez usando ambas explicaciones en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02464-179">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="02464-180">Si su modelo tiene suficiente información para extraer los datos de los archivos de ejemplo etiquetados, verá cada archivo etiquetado con **Coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="02464-180">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="02464-181">Si vuelve a recibir un **No coincidencia** en sus archivos etiquetados, es probable que necesite crear otra explicación para proporcionar al modelo más información para identificar el tipo de documento, o considerar la posibilidad de hacer cambios en los ya existentes.</span><span class="sxs-lookup"><span data-stu-id="02464-181">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="02464-182">Pruebe el modelo</span><span class="sxs-lookup"><span data-stu-id="02464-182">Test your model</span></span>

<span data-ttu-id="02464-183">Si recibe una coincidencia en sus archivos de muestra etiquetados, ahora puede probar su modelo en los archivos de muestra no etiquetados restantes.</span><span class="sxs-lookup"><span data-stu-id="02464-183">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="02464-184">Se trata de un paso opcional, pero resulta útil para evaluar la idoneidad del modelo o determinar si está preparado antes de usarlo, y para ello se prueba en archivos que el modelo no ha visto antes.</span><span class="sxs-lookup"><span data-stu-id="02464-184">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="02464-185">En la página principal del modelo, haga clic en la pestaña **Prueba**. Se ejecutará el modelo en sus archivos de muestra sin etiquetar.</span><span class="sxs-lookup"><span data-stu-id="02464-185">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="02464-186">En la lista de **Archivos de prueba**, sus archivos de ejemplo son presentados para mostrar si el modelo es capaz de extraer la información que necesita.</span><span class="sxs-lookup"><span data-stu-id="02464-186">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="02464-187">Utilice esta información para ayudar a determinar la eficacia de su clasificador en la identificación de sus documentos.</span><span class="sxs-lookup"><span data-stu-id="02464-187">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Prueba en los archivos](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="02464-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02464-189">See Also</span></span>
[<span data-ttu-id="02464-190">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="02464-190">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="02464-191">Tipos de explicación</span><span class="sxs-lookup"><span data-stu-id="02464-191">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="02464-192">Aprovechar la taxonomía del almacén de términos al crear un extractor</span><span class="sxs-lookup"><span data-stu-id="02464-192">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="02464-193">Información general sobre la comprensión mediante documentos</span><span class="sxs-lookup"><span data-stu-id="02464-193">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="02464-194">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="02464-194">Apply a model</span></span>](apply-a-model.md) 
