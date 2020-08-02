---
title: Aplicación de un documento que comprende el modelo a una biblioteca de documentos (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo aplicar un modelo publicado a una biblioteca de documentos de SharePoint.
ms.openlocfilehash: 7e5f3f02c2679769515b27026918a15c901c896e
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537613"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="43450-103">Aplicación de un modelo de comprensión de documentos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="43450-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="43450-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="43450-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="43450-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="43450-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="43450-106">Después de publicar el documento con información sobre el modelo, puede aplicarlo a una biblioteca de documentos de SharePoint en su inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43450-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="43450-107">Solo podrá aplicar el modelo a las bibliotecas de documentos a las que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="43450-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="43450-108">Aplique el modelo a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="43450-108">Apply your model to a document library.</span></span>

<span data-ttu-id="43450-109">Para aplicar el modelo a una biblioteca de documentos de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="43450-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="43450-110">En la Página principal del modelo, en el mosaico **aplicar modelo a bibliotecas** , seleccione **publicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="43450-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="43450-111">O bien, puede seleccionar **+ Agregar biblioteca** en la sección **bibliotecas con este modelo** .</span><span class="sxs-lookup"><span data-stu-id="43450-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Agregar un modelo a la biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="43450-113">A continuación, puede seleccionar el sitio de SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="43450-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="43450-114">Si el sitio no aparece en la lista, use el cuadro de búsqueda para buscarlo.</span><span class="sxs-lookup"><span data-stu-id="43450-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Seleccionar un sitio](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="43450-116">Debe tener permisos de *Administración de listas* o derechos de *edición* en la biblioteca de documentos a la que va a aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="43450-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="43450-117">Después de seleccionar el sitio, debe seleccionar la biblioteca de documentos a la que desea aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="43450-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="43450-118">En el ejemplo, se selecciona la biblioteca de documentos *documentos* del sitio de *seguimiento de casos de Contoso* .</span><span class="sxs-lookup"><span data-stu-id="43450-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Selección de una biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="43450-120">Como el modelo está asociado a un tipo de contenido, cuando se aplica a la biblioteca, se creará una vista para el tipo de contenido con las etiquetas que se extrajo Mostrar como columnas.</span><span class="sxs-lookup"><span data-stu-id="43450-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="43450-121">De forma predeterminada, esta vista será la vista predeterminada de la biblioteca, pero, opcionalmente, puede optar por no tenerla como la vista predeterminada seleccionando **Configuración avanzada** y deseleccionando **establecer esta nueva vista como predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="43450-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Vista de biblioteca](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="43450-123">Seleccione **Agregar** para aplicar el modelo a la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="43450-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="43450-124">En la Página principal del modelo, en la sección **bibliotecas con este modelo** , verá la dirección URL del sitio de SharePoint que se muestra.</span><span class="sxs-lookup"><span data-stu-id="43450-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![Vista de biblioteca](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="43450-126">Vaya a la biblioteca de documentos y asegúrese de que se encuentra en la vista de la biblioteca de documentos del modelo.</span><span class="sxs-lookup"><span data-stu-id="43450-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="43450-127">Observará que si selecciona el botón información junto al nombre de la biblioteca de documentos, un mensaje le indicará que el modelo se ha aplicado a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="43450-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![Vista de biblioteca](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="43450-129">Después de aplicar el modelo a la biblioteca de documentos, puede empezar a cargar los documentos en el sitio y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="43450-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="43450-130">El modelo identificará los archivos con el tipo de contenido asociado al modelo y los mostrará en la vista.</span><span class="sxs-lookup"><span data-stu-id="43450-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="43450-131">Si el modelo tiene algún extractor, la vista mostrará columnas para los datos que va a extraer de cada archivo.</span><span class="sxs-lookup"><span data-stu-id="43450-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="43450-132">Aplicar el modelo a los archivos que ya se encuentran en la biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="43450-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="43450-133">Mientras que un modelo aplicado procesará todos los archivos cargados en la biblioteca de documentos después de su aplicación, también puede hacer lo siguiente para ejecutar el modelo en archivos que ya existían en la biblioteca de documentos antes del modelo que se aplica:</span><span class="sxs-lookup"><span data-stu-id="43450-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="43450-134">En la biblioteca de documentos, seleccione los archivos que desea que procese el modelo.</span><span class="sxs-lookup"><span data-stu-id="43450-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="43450-135">Después de seleccionar los archivos, la **clasificación y la extracción** aparecerán en la cinta de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="43450-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="43450-136">Seleccione **clasificar y extraer**.</span><span class="sxs-lookup"><span data-stu-id="43450-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="43450-137">Los archivos seleccionados se agregarán a la cola para ser procesados.</span><span class="sxs-lookup"><span data-stu-id="43450-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Clasificar y extraer](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="43450-139">Consulta también</span><span class="sxs-lookup"><span data-stu-id="43450-139">See Also</span></span>
[<span data-ttu-id="43450-140">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="43450-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="43450-141">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="43450-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="43450-142">Información general sobre el documento</span><span class="sxs-lookup"><span data-stu-id="43450-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="43450-143">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="43450-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




