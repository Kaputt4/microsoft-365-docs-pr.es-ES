---
title: Aplicar un modelo de comprensión mediante documentos a una biblioteca de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
description: Aprenda a aplicar un modelo publicado a una biblioteca de documentos de SharePoint
ms.openlocfilehash: cda9de43d0139c52f950527eb75d050602005fd2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843299"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="19522-103">Aplicar un modelo de comprensión mediante documentos en la sintaxis de Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="19522-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="19522-104">Después de publicar el modelo de comprensión mediante documentos, puede aplicarlo a una o más bibliotecas de documentos de SharePoint en su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19522-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="19522-105">Solo puede aplicar el modelo a las bibliotecas de documentos a las que tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="19522-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="19522-106">Aplique el modelo a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="19522-106">Apply your model to a document library.</span></span>

<span data-ttu-id="19522-107">Para aplicar el modelo a una biblioteca de documentos de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="19522-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="19522-108">En la página principal del modelo, en el cuadro **Aplicar modelo a las bibliotecas**, seleccione **Publicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="19522-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="19522-109">También puede seleccionar **+Agregar biblioteca** en la sección **Bibliotecas con este modelo**.</span><span class="sxs-lookup"><span data-stu-id="19522-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Agregar un modelo a la biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="19522-111">Después, puede seleccionar el sitio de SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="19522-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="19522-112">Si el sitio no aparece en la lista, use el cuadro de búsqueda para encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="19522-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Seleccionar un sitio](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="19522-114">Debe tener permisos de *Administración de lista* o de *Edición* en la biblioteca de documentos a la que va a aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="19522-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="19522-115">Después de seleccionar el sitio, seleccione la biblioteca de documentos a la que quiere aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="19522-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="19522-116">En el ejemplo, seleccione la biblioteca de documentos *Documentos* en el sitio de *Seguimiento de casos de Contoso*.</span><span class="sxs-lookup"><span data-stu-id="19522-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Seleccionar biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="19522-118">Como el modelo está asociado a un tipo de contenido, cuando lo aplique a la biblioteca, se agregará el tipo de contenido y su vista con las etiquetas que extrajo mostrándolo como columnas.</span><span class="sxs-lookup"><span data-stu-id="19522-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="19522-119">De forma predeterminada, esta vista es la vista predeterminada de la biblioteca, pero si lo prefiere, puede elegir que no sea la vista predeterminada seleccionando **Configuración avanzada** y anulando la selección **Establecer esta vista nueva como predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="19522-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Vista de biblioteca](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="19522-121">Seleccione **Agregar** para aplicar el modelo a la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="19522-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="19522-122">En la página principal del modelo, en la sección **Bibliotecas con este modelo**, debe ver la dirección URL del sitio de SharePoint que se muestra.</span><span class="sxs-lookup"><span data-stu-id="19522-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Biblioteca seleccionada](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="19522-124">Vaya a la biblioteca de documentos y asegúrese de estar en la vista de biblioteca de documentos del modelo.</span><span class="sxs-lookup"><span data-stu-id="19522-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="19522-125">Tenga en cuenta que, si selecciona el botón de información situado junto al nombre de la biblioteca de documentos, se mostrará un mensaje que indica que la biblioteca de documentos tiene aplicado un modelo.</span><span class="sxs-lookup"><span data-stu-id="19522-125">Notice that if you select the information button next to the document library name, a message notes that the document library has a model applied to it.</span></span>

    ![Vista de información](../media/content-understanding/info-du.png)</br> 

    <span data-ttu-id="19522-127">Puede seleccionar la opción **Ver modelos activos** para consultar detalles sobre los modelos que se aplican a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="19522-127">You can the select **View active models** to see details about any models that are applied to the document library.</span></span>

8. <span data-ttu-id="19522-128">Puede seleccionar la opción **Modelos activos** para ver los modelos que se aplican a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="19522-128">In the **Active models** pane, you can see the models that are applied to the document library.</span></span> <span data-ttu-id="19522-129">Seleccione un modelo para ver más detalles sobre él, como una descripción, quién lo publicó y si el modelo aplica una etiqueta de retención a los archivos que clasifica.</span><span class="sxs-lookup"><span data-stu-id="19522-129">Select a model to see more details about it, such as a description of the model, who published the model, and if the model applies a retention label to the files it classifies.</span></span>

    ![Panel Modelos activos](../media/content-understanding/active-models.png)</br> 

<span data-ttu-id="19522-131">Después de aplicar el modelo a la biblioteca de documentos, puede iniciar la carga de documentos en el sitio y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="19522-131">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="19522-132">El modelo identifica los archivos con el tipo de contenido asociado al modelo y los enumera en la vista.</span><span class="sxs-lookup"><span data-stu-id="19522-132">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="19522-133">Si su modelo tiene algún extractor, la vista muestra columnas para los datos que se extraen de cada archivo.</span><span class="sxs-lookup"><span data-stu-id="19522-133">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="19522-134">Aplicar el modelo a los archivos que ya se encuentren en la biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="19522-134">Apply the model to files already in the document library</span></span>

<span data-ttu-id="19522-135">Si bien un modelo aplicado procesa todos los archivos cargados en la biblioteca de documentos después de su aplicación, también puede hacer lo siguiente para ejecutar el modelo en archivos que ya existen en la biblioteca de documentos antes de que se aplique el modelo:</span><span class="sxs-lookup"><span data-stu-id="19522-135">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="19522-136">En la biblioteca de documentos, seleccione los archivos que quiere que sean procesados por su modelo.</span><span class="sxs-lookup"><span data-stu-id="19522-136">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="19522-137">Después de seleccionar los archivos, en la cinta de la biblioteca de documentos se mostrará **Clasificar y extraer**.</span><span class="sxs-lookup"><span data-stu-id="19522-137">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="19522-138">Seleccione **Clasificar y extraer**.</span><span class="sxs-lookup"><span data-stu-id="19522-138">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="19522-139">Los archivos que seleccionó se agregarán a la cola para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="19522-139">The files you selected will be added to the queue to be processed.</span></span>

      ![Clasificar y extraer](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> <span data-ttu-id="19522-141">Puede copiar archivos individuales a una biblioteca y aplicarlos a un modelo, pero no carpetas.</span><span class="sxs-lookup"><span data-stu-id="19522-141">You can copy individual files to a library and apply them to a model, but not folders.</span></span>

### <a name="the-classification-date-field"></a><span data-ttu-id="19522-142">Campo Fecha de clasificación</span><span class="sxs-lookup"><span data-stu-id="19522-142">The Classification Date field</span></span>

<span data-ttu-id="19522-143">Cuando se aplica un modelo de procesamiento de formularios o información de documentos de SharePoint Syntex a una biblioteca de documentos, en el esquema de la biblioteca se incluye un campo <b>Fecha de clasificación</b>.</span><span class="sxs-lookup"><span data-stu-id="19522-143">When a SharePoint Syntex document understanding or form processing model is applied to a document library, a <b> Classification date </b> field is included in the library schema.</span></span> <span data-ttu-id="19522-144">De forma predeterminada, este campo está vacío, pero cuando un modelo procesa y clasifica documentos, este campo se actualiza con una marca de fecha y hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="19522-144">By default this field is empty, but when documents are processed and classified by a model, this field is updated with a date-time stamp of completion.</span></span> 

   ![Columna Fecha de clasificación](../media/content-understanding/class-date-column.png)</br> 

<span data-ttu-id="19522-146">El desencadenador [<b>Cuando un modelo de comprensión de contenidos clasifica un archivo</b>](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) usa el campo Fecha de clasificación para ejecutar un flujo de Power Automate después de que un modelo de comprensión de contenidos de Syntex haya terminado de procesar un archivo y haya actualizado el campo "Fecha de clasificación".</span><span class="sxs-lookup"><span data-stu-id="19522-146">The Classification date field is used by the [<b>When a file is classified by a content understanding model</b> trigger](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) to run a Power Automate flow after a Syntex content understanding model has finished processing a file and updated the "Classification date" field.</span></span>

   ![Desencadenador de flujo](../media/content-understanding/trigger.png)</br>

<span data-ttu-id="19522-148">El desencadenador <b>Cuando un modelo de comprensión de contenidos clasifica un archivo</b> se puede usar después para iniciar otro flujo de trabajo con la información extraída del archivo.</span><span class="sxs-lookup"><span data-stu-id="19522-148">The <b>When a file is classified by a content understanding model</b> trigger can then be used to start another workflow using any  extracted information from the file.</span></span>



## <a name="see-also"></a><span data-ttu-id="19522-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="19522-149">See Also</span></span>
[<span data-ttu-id="19522-150">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="19522-150">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="19522-151">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="19522-151">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="19522-152">Información general de la comprensión mediante documentos </span><span class="sxs-lookup"><span data-stu-id="19522-152">Document Understanding overview</span></span>](document-understanding-overview.md)
