---
title: Aplicar un modelo de comprensión mediante documentos a una biblioteca de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Aprenda a aplicar un modelo publicado a una biblioteca de documentos de SharePoint
ms.openlocfilehash: 8b7d6cf21f422ba54933c2d3ac29b4b34171059e
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322158"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="c96fa-103">Aplicar un modelo de comprensión mediante documentos en la sintaxis de Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="c96fa-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="c96fa-104">Después de publicar el modelo de comprensión mediante documentos, puede aplicarlo a una o más bibliotecas de documentos de SharePoint en su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c96fa-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="c96fa-105">Solo puede aplicar el modelo a las bibliotecas de documentos a las que tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="c96fa-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="c96fa-106">Aplique el modelo a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="c96fa-106">Apply your model to a document library.</span></span>

<span data-ttu-id="c96fa-107">Para aplicar el modelo a una biblioteca de documentos de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="c96fa-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="c96fa-108">En la página principal del modelo, en el cuadro **Aplicar modelo a las bibliotecas**, seleccione **Publicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="c96fa-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="c96fa-109">También puede seleccionar **+Agregar biblioteca** en la sección **Bibliotecas con este modelo**.</span><span class="sxs-lookup"><span data-stu-id="c96fa-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Agregar un modelo a la biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="c96fa-111">Después, puede seleccionar el sitio de SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="c96fa-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="c96fa-112">Si el sitio no aparece en la lista, use el cuadro de búsqueda para encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="c96fa-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Seleccionar un sitio](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="c96fa-114">Debe tener permisos de *Administración de lista* o de *Edición* en la biblioteca de documentos a la que va a aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="c96fa-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="c96fa-115">Después de seleccionar el sitio, seleccione la biblioteca de documentos a la que quiere aplicar el modelo.</span><span class="sxs-lookup"><span data-stu-id="c96fa-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="c96fa-116">En el ejemplo, seleccione la biblioteca de documentos *Documentos* en el sitio de *Seguimiento de casos de Contoso*.</span><span class="sxs-lookup"><span data-stu-id="c96fa-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Seleccionar biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="c96fa-118">Como el modelo está asociado a un tipo de contenido, cuando lo aplique a la biblioteca, se agregará el tipo de contenido y su vista con las etiquetas que extrajo mostrándolo como columnas.</span><span class="sxs-lookup"><span data-stu-id="c96fa-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="c96fa-119">De forma predeterminada, esta vista es la vista predeterminada de la biblioteca, pero si lo prefiere, puede elegir que no sea la vista predeterminada seleccionando **Configuración avanzada** y anulando la selección **Establecer esta vista nueva como predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="c96fa-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Vista de biblioteca](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="c96fa-121">Seleccione **Agregar** para aplicar el modelo a la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c96fa-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="c96fa-122">En la página principal del modelo, en la sección **Bibliotecas con este modelo**, debe ver la dirección URL del sitio de SharePoint que se muestra.</span><span class="sxs-lookup"><span data-stu-id="c96fa-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Biblioteca seleccionada](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="c96fa-124">Vaya a la biblioteca de documentos y asegúrese de estar en la vista de biblioteca de documentos del modelo.</span><span class="sxs-lookup"><span data-stu-id="c96fa-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="c96fa-125">Tenga en cuenta que si selecciona el botón de información junto al nombre de la biblioteca de documentos, se mostrará un mensaje que indica que su modelo se ha aplicado a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="c96fa-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Vista de información](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="c96fa-127">Después de aplicar el modelo a la biblioteca de documentos, puede iniciar la carga de documentos en el sitio y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="c96fa-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="c96fa-128">El modelo identifica los archivos con el tipo de contenido asociado al modelo y los enumera en la vista.</span><span class="sxs-lookup"><span data-stu-id="c96fa-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="c96fa-129">Si su modelo tiene algún extractor, la vista muestra columnas para los datos que se extraen de cada archivo.</span><span class="sxs-lookup"><span data-stu-id="c96fa-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="c96fa-130">Aplicar el modelo a los archivos que ya se encuentren en la biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="c96fa-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="c96fa-131">Si bien un modelo aplicado procesa todos los archivos cargados en la biblioteca de documentos después de su aplicación, también puede hacer lo siguiente para ejecutar el modelo en archivos que ya existen en la biblioteca de documentos antes de que se aplique el modelo:</span><span class="sxs-lookup"><span data-stu-id="c96fa-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="c96fa-132">En la biblioteca de documentos, seleccione los archivos que quiere que sean procesados por su modelo.</span><span class="sxs-lookup"><span data-stu-id="c96fa-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="c96fa-133">Después de seleccionar los archivos, en la cinta de la biblioteca de documentos se mostrará **Clasificar y extraer**.</span><span class="sxs-lookup"><span data-stu-id="c96fa-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="c96fa-134">Seleccione **Clasificar y extraer**.</span><span class="sxs-lookup"><span data-stu-id="c96fa-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="c96fa-135">Los archivos que seleccionó se agregarán a la cola para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c96fa-135">The files you selected will be added to the queue to be processed.</span></span>

      ![Clasificar y extraer](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="c96fa-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c96fa-137">See Also</span></span>
[<span data-ttu-id="c96fa-138">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="c96fa-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="c96fa-139">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="c96fa-139">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c96fa-140">Información general de la comprensión mediante documentos </span><span class="sxs-lookup"><span data-stu-id="c96fa-140">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="c96fa-141">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="c96fa-141">Create a form processing model</span></span>](create-a-form-processing-model.md)  
