---
title: Crear un modelo de procesamiento de formularios (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Cree un modelo de procesamiento de formularios en Project Cortex.
ms.openlocfilehash: 733baf24d8a484571ba9882fdda2633dc2ce0504
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612779"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="0f62a-103">Crear un modelo de procesamiento de formularios (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="0f62a-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="0f62a-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="0f62a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="0f62a-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="0f62a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="0f62a-106">Uso del [generador de AI](https://docs.microsoft.com/ai-builder/overview) : una característica de Microsoft PowerApps-Project Cortex los usuarios pueden crear un modelo de procesamiento de [formularios](form-processing-overview.md) directamente desde una biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0f62a-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="0f62a-107">La creación de un modelo de procesamiento de formularios implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f62a-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="0f62a-108">Paso 1: crear el modelo de procesamiento para crear el tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="0f62a-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="0f62a-109">Paso 2: agregar y analizar archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f62a-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="0f62a-110">Paso 3: seleccionar los campos de formulario</span><span class="sxs-lookup"><span data-stu-id="0f62a-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="0f62a-111">Paso 4: entrenar y probar el modelo</span><span class="sxs-lookup"><span data-stu-id="0f62a-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="0f62a-112">Paso 5: publicar el modelo</span><span class="sxs-lookup"><span data-stu-id="0f62a-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="0f62a-113">Paso 6: usar el modelo</span><span class="sxs-lookup"><span data-stu-id="0f62a-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="0f62a-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="0f62a-114">Requirements</span></span>

<span data-ttu-id="0f62a-115">Solo se puede crear un modelo de procesamiento de formularios en bibliotecas de documentos de SharePoint en el que esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="0f62a-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="0f62a-116">Si el procesamiento de formularios está habilitado, podrá ver el **generador de AI** **"crear un modelo de procesamiento de formularios"** en el menú **automatizar** de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="0f62a-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="0f62a-117">Si necesita el procesamiento habilitado en la biblioteca de documentos, póngase en contacto con el administrador.</span><span class="sxs-lookup"><span data-stu-id="0f62a-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Crear un modelo de generador de AI](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="0f62a-119">Paso 1: crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="0f62a-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="0f62a-120">El primer paso para crear un modelo de procesamiento de formularios es nombrarlo para crear la vista definir el nuevo tipo de contenido y crear una nueva vista de biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="0f62a-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="0f62a-121">En la biblioteca de documentos, seleccione el menú **automatizar** , seleccione **generador de AI**y, a continuación, seleccione **crear un modelo de procesamiento de formularios**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Crear un modelo de generador de AI](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="0f62a-123">En el panel **nuevo modelo de procesamiento de formularios** , en el campo **nombre** , escriba un nombre para el modelo (por ejemplo, *pedidos de compra*).</span><span class="sxs-lookup"><span data-stu-id="0f62a-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nuevo modelo de procesamiento de formularios](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="0f62a-125">Cuando se crea un modelo de procesamiento de formularios, se crea un nuevo tipo de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0f62a-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="0f62a-126">Un tipo de contenido de SharePoint representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular.</span><span class="sxs-lookup"><span data-stu-id="0f62a-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="0f62a-127">Los tipos de contenido de SharePoint se administran a través de la [Galería de tipos de contenido]().</span><span class="sxs-lookup"><span data-stu-id="0f62a-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="0f62a-128">Seleccione **Configuración avanzada** si desea asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="0f62a-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="0f62a-129">El modelo creará una nueva vista en la biblioteca de documentos para los datos extraídos.</span><span class="sxs-lookup"><span data-stu-id="0f62a-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="0f62a-130">Si no desea que se ajuste a la vista predeterminada, anule **la selección de establecer la vista como predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="0f62a-131">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="0f62a-132">Paso 2: agregar y analizar documentos</span><span class="sxs-lookup"><span data-stu-id="0f62a-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="0f62a-133">Después de crear el nuevo modelo de procesamiento de formularios, el explorador abrirá una nueva página del modelo de procesamiento de formularios de PowerApps AI Builder.</span><span class="sxs-lookup"><span data-stu-id="0f62a-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="0f62a-134">En esta página, puede Agregar y analizar los documentos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0f62a-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="0f62a-135">Al buscar archivos de ejemplo para usar, vea el [modelo de procesamiento de formularios requisitos de documentos de entrada y sugerencias de optimización](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="0f62a-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Generador de AI de Power apps](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="0f62a-137">Haga clic en **agregar documentos** para empezar a agregar documentos de ejemplo que se analizan para determinar qué pares de valor con nombre se pueden extraer.</span><span class="sxs-lookup"><span data-stu-id="0f62a-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="0f62a-138">Puede elegir entre **cargar desde almacenamiento local**, **SharePoint**o almacenamiento de **blobs de Azure**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="0f62a-139">Debe usar al menos cinco archivos para el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="0f62a-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="0f62a-140">Después de agregar los archivos, seleccione **analizar** para comprobar si la información es común en todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="0f62a-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="0f62a-141">Tenga en cuenta que esto puede tardar varios minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="0f62a-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Analizar archivos](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="0f62a-143">Una vez analizados, en la página **Seleccione los campos de formulario que desea guardar** , haga clic en el archivo para ver los campos detectados.</span><span class="sxs-lookup"><span data-stu-id="0f62a-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Selección de campos de formulario](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="0f62a-145">Paso 3: seleccionar los campos de formulario</span><span class="sxs-lookup"><span data-stu-id="0f62a-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="0f62a-146">Después de analizar los documentos para los campos, ahora puede ver qué campos se encontraron y cuáles desea guardar.</span><span class="sxs-lookup"><span data-stu-id="0f62a-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="0f62a-147">Los campos guardados se mostrarán como columnas en la vista de la biblioteca de documentos del modelo y mostrarán los valores extraídos de cada documento.</span><span class="sxs-lookup"><span data-stu-id="0f62a-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="0f62a-148">En la página siguiente se mostrará uno de los archivos de ejemplo y se resaltarán todos los campos comunes detectados automáticamente por el sistema.</span><span class="sxs-lookup"><span data-stu-id="0f62a-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Selección de campos de formulario](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="0f62a-150">Seleccione los campos que desea guardar y active la casilla de verificación para confirmar la selección.</span><span class="sxs-lookup"><span data-stu-id="0f62a-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="0f62a-151">Por ejemplo, en el modelo de pedido de compra, puede elegir seleccionar los campos *fecha*, *po*y *total* .</span><span class="sxs-lookup"><span data-stu-id="0f62a-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="0f62a-152">Tenga en cuenta que también puede cambiar el nombre de un campo si lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="0f62a-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Seleccionar PO #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="0f62a-154">Si el análisis no ha detectado un campo, puede optar por agregarlo.</span><span class="sxs-lookup"><span data-stu-id="0f62a-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="0f62a-155">Resalte la información que desea extraer y, en el cuadro Nombre, escriba el nombre que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="0f62a-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="0f62a-156">A continuación, seleccione la comprobación.</span><span class="sxs-lookup"><span data-stu-id="0f62a-156">Then select the check.</span></span> <span data-ttu-id="0f62a-157">Tenga en cuenta que deberá confirmar los campos no detectados en los archivos de ejemplo restantes.</span><span class="sxs-lookup"><span data-stu-id="0f62a-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="0f62a-158">Haga clic en **confirmar campos** después de haber seleccionado los campos que desea guardar.</span><span class="sxs-lookup"><span data-stu-id="0f62a-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Confirmar campos](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="0f62a-160">En la página **Seleccione los campos de formulario que desea guardar** , se mostrará el número de campos que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0f62a-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="0f62a-161">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="0f62a-162">Paso 4: entrenar y probar el modelo</span><span class="sxs-lookup"><span data-stu-id="0f62a-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="0f62a-163">Después de seleccionar los campos que desea guardar, la página de **Resumen del modelo** le permitirá entrenar y probar el modelo.</span><span class="sxs-lookup"><span data-stu-id="0f62a-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="0f62a-164">En la página de **Resumen del modelo** , los campos guardados se mostrarán en la sección **campos seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="0f62a-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="0f62a-165">Seleccione **entrenar** para empezar a entrenar en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0f62a-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="0f62a-166">Tenga en cuenta que esta operación puede tardar unos minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="0f62a-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="0f62a-167">![Confirmar campos](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="0f62a-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="0f62a-168">Cuando vea la notificación de que se ha completado el entrenamiento, seleccione **ir a la página de detalles**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="0f62a-169">En la página **detalles del modelo** , puede elegir probar el funcionamiento del modelo seleccionando **prueba rápida**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="0f62a-170">Esto le permite arrastrar y soltar archivos a la página y ver si se detectan los campos.</span><span class="sxs-lookup"><span data-stu-id="0f62a-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="0f62a-171">Paso 5: publicar el modelo</span><span class="sxs-lookup"><span data-stu-id="0f62a-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="0f62a-172">Si está satisfecho con los resultados del modelo, seleccione **publicar** para que esté disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="0f62a-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="0f62a-173">Después de publicar el modelo, seleccione **usar modelo**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="0f62a-174">Esto crea un flujo de PowerAutomate que se ejecutará en la biblioteca de documentos de SharePoint y extraerá los campos identificados en el modelo.</span><span class="sxs-lookup"><span data-stu-id="0f62a-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="0f62a-175">Seleccione **Crear flujo**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="0f62a-176">Una vez completado, verá el mensaje el **flujo se ha creado correctamente**.</span><span class="sxs-lookup"><span data-stu-id="0f62a-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="0f62a-177">Paso 6: usar el modelo</span><span class="sxs-lookup"><span data-stu-id="0f62a-177">Step 6: Use your model</span></span>

<span data-ttu-id="0f62a-178">Después de publicar el modelo y crear su flujo de PowerAutomate, puede usar el modelo en la biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0f62a-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="0f62a-179">Después de publicar el modelo, seleccione **ir a SharePoint** para ir a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="0f62a-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="0f62a-180">En la vista del modelo de la biblioteca de documentos, observe que los campos que seleccionó se muestran como columnas.</span><span class="sxs-lookup"><span data-stu-id="0f62a-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Biblioteca de documentos con el modelo aplicado](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="0f62a-182">Además, observe que el vínculo de información que hay junto a los **documentos** tendrá en cuenta que se aplica un modelo de procesamiento de formularios a esta biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="0f62a-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Yendo](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="0f62a-184">Cargar archivos en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="0f62a-184">Upload files to your document library.</span></span> <span data-ttu-id="0f62a-185">Los archivos que el modelo identifica como su tipo de contenido mostrarán los archivos en la vista y mostrarán los datos extraídos en las columnas.</span><span class="sxs-lookup"><span data-stu-id="0f62a-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Yendo](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="0f62a-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f62a-187">See Also</span></span>
  
[<span data-ttu-id="0f62a-188">Documentación automatizada de la energía</span><span class="sxs-lookup"><span data-stu-id="0f62a-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="0f62a-189">Aprendizaje: mejorar el rendimiento empresarial con el generador de AI</span><span class="sxs-lookup"><span data-stu-id="0f62a-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




