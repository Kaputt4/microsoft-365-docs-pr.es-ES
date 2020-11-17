---
title: Aplicar una etiqueta de retención a un modelo de comprensión mediante documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Este artículo muestra cómo aplicar una etiqueta de retención a un modelo de comprensión mediante documentos
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087480"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="46265-103">Aplicar una etiqueta de retención a un modelo de comprensión mediante documentos</span><span class="sxs-lookup"><span data-stu-id="46265-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="46265-104">Puede aplicar fácilmente una [etiqueta de retención](https://docs.microsoft.com/microsoft-365/compliance/retention) a un modelo de comprensión mediante documentos en Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="46265-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="46265-105">Las etiquetas de retención le permiten aplicar la configuración de retención a los documentos que identifican sus modelos de comprensión mediante documentos.</span><span class="sxs-lookup"><span data-stu-id="46265-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="46265-106">Por ejemplo, si desea que el modelo no solo identifique cualquier documento de *Notificación de seguros* cargados en la biblioteca de documentos, sino que también pueda aplicar una etiqueta de retención de *negocios* para que estos documentos no se puedan eliminar de la biblioteca de documentos durante el período de tiempo especificado (por ejemplo, los próximos cinco meses).</span><span class="sxs-lookup"><span data-stu-id="46265-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="46265-107">Puede aplicar una etiqueta de retención preexistente al modelo de comprensión mediante documentos en la página principal del modelo.</span><span class="sxs-lookup"><span data-stu-id="46265-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="46265-108">Para que las etiquetas de retención estén disponibles para aplicarlas a su modelo de comprensión mediante documentos, deben [crearse y publicarse en el Centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="46265-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="46265-109">Aplicar una etiqueta de retención a un modelo de comprensión mediante documentos</span><span class="sxs-lookup"><span data-stu-id="46265-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="46265-110">En la página principal del modelo, seleccione **Configuración del modelo**.</span><span class="sxs-lookup"><span data-stu-id="46265-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="46265-111">En **Configuración del modelo**, en la sección **Seguridad y cumplimiento**, seleccione el menú **Etiqueta de retención** para ver una lista de las etiquetas de retención disponibles para que se apliquen al modelo.</span><span class="sxs-lookup"><span data-stu-id="46265-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="46265-112">![Menú Etiqueta de retención](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="46265-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="46265-113">Seleccione la etiqueta de retención que desea aplicar al modelo y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="46265-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="46265-114">Después de aplicar la etiqueta de retención al modelo, podrá aplicarla a:</span><span class="sxs-lookup"><span data-stu-id="46265-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="46265-115">una nueva biblioteca de documentos y</span><span class="sxs-lookup"><span data-stu-id="46265-115">New document library</span></span>
- <span data-ttu-id="46265-116">una biblioteca de documentos en la que ya se aplica el modelo.</span><span class="sxs-lookup"><span data-stu-id="46265-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="46265-117">Aplicar la etiqueta de retención a la biblioteca de documentos en la que ya se aplica el modelo</span><span class="sxs-lookup"><span data-stu-id="46265-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="46265-118">Si ya se ha aplicado el modelo de comprensión mediante documentos a una biblioteca de documentos, puede hacer lo siguiente para sincronizar la actualización de la etiqueta de retención y aplicarla en la biblioteca de documentos:</span><span class="sxs-lookup"><span data-stu-id="46265-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="46265-119">En la Página principal del modelo, en la sección **Bibliotecas con este modelo**, seleccione la biblioteca de documentos a la que quiera aplicar la actualización de la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="46265-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="46265-120">Seleccione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="46265-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="46265-121">![Modelo de sincronización](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="46265-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="46265-122">Después de aplicar la actualización y sincronizarla con el modelo, puede confirmar que se ha aplicado haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="46265-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="46265-123">En el centro de contenido, en la sección **Bibliotecas con este modelo**, haga clic en la biblioteca a la que se ha aplicado el modelo actualizado.</span><span class="sxs-lookup"><span data-stu-id="46265-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="46265-124">En la vista de la biblioteca de documentos, seleccione el icono de información para ver las propiedades del modelo.</span><span class="sxs-lookup"><span data-stu-id="46265-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="46265-125">En la lista **Modelos activos**, seleccione el modelo actualizado.</span><span class="sxs-lookup"><span data-stu-id="46265-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="46265-126">En la sección **Etiqueta de retención** verá el nombre de la etiqueta de retención aplicada.</span><span class="sxs-lookup"><span data-stu-id="46265-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="46265-127">En la página de vista del modelo de la biblioteca de documentos, se mostrará una nueva columna de la **Etiqueta de retención**.</span><span class="sxs-lookup"><span data-stu-id="46265-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="46265-128">A medida que el modelo clasifica los archivos que identifica como pertenecientes al tipo de contenido y los muestra en la vista de biblioteca, en la columna Etiqueta de retención también se muestra el nombre de la etiqueta de retención que se ha aplicado a través del modelo.</span><span class="sxs-lookup"><span data-stu-id="46265-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="46265-129">Por ejemplo, todos los documentos de *Avisos de seguros* que su modelo identifique también tendrán la etiqueta de retención *Negocios* aplicada para que no se eliminen de la biblioteca de documentos durante cinco meses.</span><span class="sxs-lookup"><span data-stu-id="46265-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="46265-130">Si se intenta eliminar el archivo de la biblioteca de documentos, se mostrará un error que indica que no está permitido debido a la etiqueta de retención aplicada.</span><span class="sxs-lookup"><span data-stu-id="46265-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="46265-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46265-131">See Also</span></span>
[<span data-ttu-id="46265-132">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="46265-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="46265-133">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="46265-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="46265-134">Información general de la comprensión mediante documentos </span><span class="sxs-lookup"><span data-stu-id="46265-134">Document Understanding overview</span></span>](document-understanding-overview.md)


