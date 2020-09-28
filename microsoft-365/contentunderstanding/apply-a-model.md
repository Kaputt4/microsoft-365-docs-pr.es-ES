---
title: Aplicación de un documento con información sobre un modelo a una biblioteca de documentos
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
description: Obtenga información sobre cómo aplicar un modelo publicado a una biblioteca de documentos de SharePoint
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295495"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="9fea1-103">Aplicar un documento que comprenda el modelo en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="9fea1-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="9fea1-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="9fea1-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="9fea1-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="9fea1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="9fea1-106">Después de publicar el documento con información sobre el modelo, puede aplicarlo a una biblioteca de documentos de SharePoint en su inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9fea1-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="9fea1-107">Solo puede aplicar el modelo a las bibliotecas de documentos a las que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="9fea1-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="9fea1-108">Aplique el modelo a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="9fea1-108">Apply your model to a document library.</span></span>

<span data-ttu-id="9fea1-109">Para aplicar el modelo a una biblioteca de documentos de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="9fea1-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="9fea1-110">En la Página principal del modelo, en el mosaico **aplicar modelo a bibliotecas** , seleccione **publicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="9fea1-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="9fea1-111">O bien, puede seleccionar  **+ Agregar biblioteca** en la sección **bibliotecas con este modelo** .</span><span class="sxs-lookup"><span data-stu-id="9fea1-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Agregar un modelo a la biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="9fea1-113">Seleccione el sitio de SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="9fea1-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="9fea1-114">Si el sitio no aparece en la lista, use el cuadro de búsqueda para buscarlo.</span><span class="sxs-lookup"><span data-stu-id="9fea1-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Seleccionar un sitio](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="9fea1-116">Debe tener permisos de *Administración de listas* o derechos de *edición* en la biblioteca de documentos a la que va a aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="9fea1-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="9fea1-117">Después de seleccionar el sitio, seleccione la biblioteca de documentos a la que desea aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="9fea1-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="9fea1-118">En el ejemplo, seleccione la biblioteca de documentos *documentos* en el sitio de *seguimiento de casos de Contoso* .</span><span class="sxs-lookup"><span data-stu-id="9fea1-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Selección de una biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="9fea1-120">Como el modelo está asociado a un tipo de contenido, cuando se aplica a la biblioteca, crea una vista para el tipo de contenido con las etiquetas que extrajo muestra como columnas.</span><span class="sxs-lookup"><span data-stu-id="9fea1-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="9fea1-121">Esta vista es la vista predeterminada de la biblioteca de forma predeterminada, pero, opcionalmente, puede optar por no tenerla como la vista predeterminada seleccionando la **Configuración avanzada** y anular la selección de **establecer esta nueva vista como predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="9fea1-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Vista de biblioteca](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="9fea1-123">Seleccione **Agregar** para aplicar el modelo a la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9fea1-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="9fea1-124">En la Página principal del modelo, en la sección **bibliotecas con este modelo** , debería ver la dirección URL del sitio de SharePoint que se muestra.</span><span class="sxs-lookup"><span data-stu-id="9fea1-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Biblioteca seleccionada](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="9fea1-126">Vaya a la biblioteca de documentos y asegúrese de que se encuentra en la vista de la biblioteca de documentos del modelo.</span><span class="sxs-lookup"><span data-stu-id="9fea1-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="9fea1-127">Tenga en cuenta que si selecciona el botón información junto al nombre de la biblioteca de documentos, aparecerá un mensaje en el que se indica que el modelo se ha aplicado a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="9fea1-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Vista de información](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="9fea1-129">Después de aplicar el modelo a la biblioteca de documentos, puede empezar a cargar los documentos en el sitio y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="9fea1-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="9fea1-130">El modelo identifica los archivos con tipo de contenido asociado al modelo y los enumera en la vista.</span><span class="sxs-lookup"><span data-stu-id="9fea1-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="9fea1-131">Si el modelo tiene algún extractor, la vista muestra las columnas de los datos que se extraen de cada archivo.</span><span class="sxs-lookup"><span data-stu-id="9fea1-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="9fea1-132">Aplicar el modelo a los archivos que ya se encuentran en la biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="9fea1-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="9fea1-133">Mientras que un modelo aplicado procesa todos los archivos cargados en la biblioteca de documentos después de su aplicación, también puede hacer lo siguiente para ejecutar el modelo en archivos que ya existen en la biblioteca de documentos antes del modelo que se aplica:</span><span class="sxs-lookup"><span data-stu-id="9fea1-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="9fea1-134">En la biblioteca de documentos, seleccione los archivos que desea que procese el modelo.</span><span class="sxs-lookup"><span data-stu-id="9fea1-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="9fea1-135">Después de seleccionar los archivos, la **clasificación y la extracción** aparecerán en la cinta de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="9fea1-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="9fea1-136">Seleccione **clasificar y extraer**.</span><span class="sxs-lookup"><span data-stu-id="9fea1-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="9fea1-137">Los archivos seleccionados se agregarán a la cola para ser procesados.</span><span class="sxs-lookup"><span data-stu-id="9fea1-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Clasificar y extraer](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="9fea1-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9fea1-139">See Also</span></span>
[<span data-ttu-id="9fea1-140">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="9fea1-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="9fea1-141">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="9fea1-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="9fea1-142">Información general sobre el documento</span><span class="sxs-lookup"><span data-stu-id="9fea1-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="9fea1-143">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="9fea1-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
