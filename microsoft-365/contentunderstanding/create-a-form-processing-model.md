---
title: Crear un modelo de procesamiento de formularios
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Crear un modelo de procesamiento de formularios en Microsoft SharePoint Syntex.
ms.openlocfilehash: aed918d899fe7c5e3c49b733d2411c178e9b98d0
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087696"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="34577-103">Crear un modelo de procesamiento de formularios en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="34577-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="34577-104">Usar [AI Builder](https://docs.microsoft.com/ai-builder/overview): característica en Microsoft PowerApps - SharePoint Syntex los usuarios pueden crear un [modelo de procesamiento de formularios](form-processing-overview.md) directamente desde una biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="34577-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="34577-105">Crear un modelo de procesamiento de formularios implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34577-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="34577-106">Paso 1: crear el modelo de procesamiento de formularios para crear el tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="34577-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="34577-107">Paso 2: agregar y analizar archivos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="34577-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="34577-108">Paso 3: seleccionar los campos de formulario</span><span class="sxs-lookup"><span data-stu-id="34577-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="34577-109">Paso 4: entrenar y probar el modelo</span><span class="sxs-lookup"><span data-stu-id="34577-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="34577-110">Paso 5: publicar el modelo</span><span class="sxs-lookup"><span data-stu-id="34577-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="34577-111">Paso 6: usar el modelo</span><span class="sxs-lookup"><span data-stu-id="34577-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="34577-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34577-112">Requirements</span></span>

<span data-ttu-id="34577-p101">Solo puede crear un modelo de procesamiento de formularios en las bibliotecas de documentos de SharePoint para las que está habilitado. Si el procesamiento de formularios está habilitado, podrá ver el **AI Builder** **"Crear un modelo de procesamiento de formularios"** en el menú **Automatizar** de la biblioteca de documentos.  Si necesita el procesamiento habilitado en la biblioteca de documentos, debe ponerse en contacto con el Administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="34577-p101">You can only create a form processing model in SharePoint document libraries for which it is enabled. If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.  If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Crear un modelo de AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="34577-117">Paso 1: crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="34577-117">Step 1: Create a form processing model</span></span>

<span data-ttu-id="34577-118">El primer paso para crear un modelo de procesamiento de formularios es asignarle un nombre, crear la definición, crear el nuevo tipo de contenido y crear una nueva vista de la biblioteca de documentos para este.</span><span class="sxs-lookup"><span data-stu-id="34577-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="34577-119">En la biblioteca de documentos, seleccione el menú **Automatizar**, seleccione **AI Builder** y, después elija **Crear un modelo de procesamiento de formularios**.</span><span class="sxs-lookup"><span data-stu-id="34577-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Crear un modelo](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="34577-121">En el panel **Nuevo modelo de procesamiento de formularios**, en el campo **Nombre**, escriba el nombre del modelo (por ejemplo, *Pedidos de compra*).</span><span class="sxs-lookup"><span data-stu-id="34577-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nuevo modelo de procesamiento de formularios](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="34577-p102">Cuando se crea un modelo de procesamiento de formularios, se crea un nuevo tipo de contenido de SharePoint. Un tipo de contenido de SharePoint representa una categoría de documentos con características comunes y comparte una colección de columnas o de propiedades de metadatos para ese contenido concreto. Los tipos de contenido de SharePoint se administran en la [Galería tipos de contenido]().</span><span class="sxs-lookup"><span data-stu-id="34577-p102">When you create a form processing model, you create a new SharePoint content type. A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content. SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="34577-126">Seleccione **Configuración avanzada** si quiere asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="34577-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="34577-p103">El modelo crea una nueva vista de la biblioteca de documentos para los datos extraídos. Si no quiere que aparezca en la vista predeterminada, anule la selección de **Establecer la vista como** predeterminada.</span><span class="sxs-lookup"><span data-stu-id="34577-p103">Your model creates a new view in your document library for your extracted data. If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="34577-129">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="34577-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="34577-130">Paso 2: agregar y analizar documentos</span><span class="sxs-lookup"><span data-stu-id="34577-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="34577-p104">Después de crear el nuevo modelo de procesamiento de formularios, el explorador abrirá una nueva página de modelo de procesamiento de formularios de PowerApps AI Builder. En esta página puede agregar y analizar sus documentos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="34577-p104">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page. On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="34577-133">Al buscar archivos de ejemplo para usar, vea los [requisitos del documento de entrada del modelo de procesamiento de formularios y los consejos de optimización](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="34577-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="34577-p105">Seleccione **Agregar documentos** para empezar a agregar documentos de ejemplo analizados para determinar los pares de valores con nombre que se pueden extraer. A continuación, puede elegir **Carga desde almacenamiento local**, **SharePoint** o **Azure Blob Storage**. Debe usar al menos cinco archivos para el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="34577-p105">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted. You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**. You need to use at least five files for training.</span></span>

2. <span data-ttu-id="34577-p106">Después de agregar archivos, seleccione **Analizar** para comprobar si hay información común en todos los archivos. Esto debería llevar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="34577-p106">After adding files, select **Analyze** to check for any information common is all files. This may take several minutes to complete.</span></span></br> 
 
    ![Analizar archivos](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="34577-141">Después de que se hayan analizados los archivos, en la página **Seleccionar los campos de formulario que quiere guardar** seleccione el archivo para ver los campos detectados.</span><span class="sxs-lookup"><span data-stu-id="34577-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Seleccionar campos de formulario](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="34577-143">Paso 3: seleccionar los campos de formulario</span><span class="sxs-lookup"><span data-stu-id="34577-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="34577-p107">Después de analizar los documentos para los campos, puede ver los campos que encontró e identificar los que quiere guardar. Los campos guardados se muestran como columnas en la vista de la biblioteca de documentos del modelo y muestran los valores obtenidos de cada documento.</span><span class="sxs-lookup"><span data-stu-id="34577-p107">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save. Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="34577-146">En la página siguiente se mostrará uno de los archivos de ejemplo y se resaltarán todos los campos comunes que el sistema detectó automáticamente.</span><span class="sxs-lookup"><span data-stu-id="34577-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Página seleccionar campos](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="34577-p108">Seleccione los campos que desee guardar y marque la casilla para confirmar la selección. Por ejemplo, en el modelo Orden de compra, elija para seleccionar los campos *Fecha*, *OC* y *Total*. Tenga en cuenta que también puede elegir cambiar el nombre de un campo. </span><span class="sxs-lookup"><span data-stu-id="34577-p108">Select the fields that you want to save and select the checkbox to confirm your selection. For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.  Note that you can also choose to rename a field if you choose. </span></span></br>

    ![Seleccionar el n.º de OC](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="34577-p109">Si un análisis no ha detectado un campo, aún puede agregarlo. Resalte la información que desea extraer y, en el cuadro Nombre, escriba el nombre que desee. Después, seleccione la casilla. Tenga en cuenta que necesita confirmar campos no detectados en los archivos de ejemplo restantes.</span><span class="sxs-lookup"><span data-stu-id="34577-p109">If a field was not detected by analysis, you can still choose to add it. Highlight the information you want to extract, and in the name box type in the name you want. Then select the check box. Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="34577-156">Haga clic en **Confirmar campos** después de seleccionar los campos que quiere guardar.</span><span class="sxs-lookup"><span data-stu-id="34577-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Confirmar campos después de seleccionar campos](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="34577-p110">La página **Seleccionar los campos de formulario que quiere guardar**, muestra el número de campos que ha seleccionado. Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="34577-p110">On the **Select the form fields you want to save** page, it shows the number of fields you have selected. Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="34577-160">Paso 4: entrenar y probar el modelo</span><span class="sxs-lookup"><span data-stu-id="34577-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="34577-161">Después de seleccionar los campos que quiere guardar, la página **Resumen del modelo** le permite entrenar y probar el modelo.</span><span class="sxs-lookup"><span data-stu-id="34577-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="34577-p111">En la página **Resumen del modelo**, los campos guardados se mostrarán en la sección **Campos seleccionados**. Seleccione **Entrenar** para comenzar el entrenamiento en sus archivos de ejemplo. Tenga en cuenta que esto puede tardar unos minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="34577-p111">On the **Model Summary** page, the saved fields will show in the **Selected fields** section. Select **Train** to begin training on your example files. Note that this may take a few minutes to complete.</span></span></br>

     ![Seleccionar campos de entrenamiento](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="34577-166">Cuando vea la notificación de que el entrenamiento ha finalizado, seleccione **Ir a la página de detalles**.</span><span class="sxs-lookup"><span data-stu-id="34577-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="34577-p112">En la página **Detalles del modelo**, puede elegir probar el funcionamiento del modelo seleccionando **Prueba rápida**. Esto le permite arrastrar y soltar archivos a la página y ver si los campos se detectan.</span><span class="sxs-lookup"><span data-stu-id="34577-p112">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Confirmar campos](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="34577-170">Cuando vea la notificación de que el entrenamiento ha finalizado, seleccione **Ir a la página de detalles**.</span><span class="sxs-lookup"><span data-stu-id="34577-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="34577-p113">En la página **Detalles del modelo**, puede elegir probar el funcionamiento del modelo seleccionando **Prueba rápida**. Esto le permite arrastrar y soltar archivos a la página y ver si los campos se detectan.</span><span class="sxs-lookup"><span data-stu-id="34577-p113">On the **Model details** page, choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="34577-173">Paso 5: publicar el modelo</span><span class="sxs-lookup"><span data-stu-id="34577-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="34577-174">Si está de acuerdo con los resultados de su modelo, seleccione **Publicar** para que esté disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="34577-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="34577-p114">Después de publicar el modelo, seleccione **Usar modelo**. Esto crea un flujo de PowerAutomate que puede ejecutarse en la biblioteca de documentos de SharePoint y extrae los campos que se han identificado en el modelo, luego seleccione **Crear flujo**.</span><span class="sxs-lookup"><span data-stu-id="34577-p114">After the model is published, select **Use model**. This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="34577-177">Cuando finalice, verá el mensaje **Su flujo se ha creado correctamente**.</span><span class="sxs-lookup"><span data-stu-id="34577-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="34577-178">Paso 6: usar el modelo</span><span class="sxs-lookup"><span data-stu-id="34577-178">Step 6: Use your model</span></span>

<span data-ttu-id="34577-179">Después de publicar el modelo y crear el flujo de PowerAutomate, puede usar el modelo en la biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="34577-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="34577-180">Después de publicar el modelo, seleccione **Ir a SharePoint** para ir a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="34577-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="34577-181">En la vista modelo de la biblioteca de documentos, tenga en cuenta que los campos que seleccionó se muestran como columnas.</span><span class="sxs-lookup"><span data-stu-id="34577-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Modelo de la biblioteca de documentos aplicado](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="34577-183">Observe que el vínculo de información junto a **Documentos** indica que se aplica un modelo de procesamiento de formularios a esta biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="34577-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Botón información](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="34577-p115">Cargar archivos a su biblioteca de documentos. Los archivos que el modelo identifica como su tipo de contenido muestran los archivos en la vista y muestra en las columnas los datos extraídos.</span><span class="sxs-lookup"><span data-stu-id="34577-p115">Upload files to your document library. Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Hecho](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="34577-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="34577-188">See Also</span></span>
  
[<span data-ttu-id="34577-189">Documentación de Power Automate</span><span class="sxs-lookup"><span data-stu-id="34577-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="34577-190">Aprendizaje: mejorar el rendimiento empresarial con AI Builder</span><span class="sxs-lookup"><span data-stu-id="34577-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
