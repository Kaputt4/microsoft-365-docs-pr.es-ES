---
title: Aplicar una etiqueta de retención a un modelo
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
description: Este artículo muestra cómo aplicar una etiqueta de retención a un modelo en SharePoint Syntex
ms.openlocfilehash: 00a8d255b3274af3cd96527e0dcd2ae2644226ac
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861616"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="5824f-103">Puede aplicar fácilmente una etiqueta de retención a un modelo en SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="5824f-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="5824f-104">Puede aplicar fácilmente una [etiqueta de retención](../compliance/retention.md) a un modelo en Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="5824f-104">You can easily apply a [retention label](../compliance/retention.md) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="5824f-105">Puede hacerlo tanto para modelos de comprensión de documentos como para modelos de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="5824f-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="5824f-106">Las etiquetas de retención le permiten aplicar la configuración de retención a los documentos que identifican sus modelos.</span><span class="sxs-lookup"><span data-stu-id="5824f-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="5824f-107">Por ejemplo, si desea que el modelo no solo identifique cualquier documento de *Notificación de seguros* cargados en la biblioteca de documentos, sino que también pueda aplicar una etiqueta de retención de *negocios* para que estos documentos no se puedan eliminar de la biblioteca de documentos durante el período de tiempo especificado (por ejemplo, los próximos cinco meses).</span><span class="sxs-lookup"><span data-stu-id="5824f-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="5824f-108">Puede aplicar una etiqueta de retención preexistente al modelo en la página principal del modelo.</span><span class="sxs-lookup"><span data-stu-id="5824f-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="5824f-109">Para que las etiquetas de retención estén disponibles para aplicarlas a su modelo de comprensión mediante documentos, deben [crearse y publicarse en el Centro de cumplimiento de Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="5824f-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="5824f-110">Aplicar una etiqueta de retención a un modelo de comprensión mediante documentos</span><span class="sxs-lookup"><span data-stu-id="5824f-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="5824f-111">En la página principal del modelo, seleccione **Configuración del modelo**.</span><span class="sxs-lookup"><span data-stu-id="5824f-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="5824f-112">En **Configuración del modelo**, en la sección **Seguridad y cumplimiento**, seleccione el menú **Etiqueta de retención** para ver una lista de las etiquetas de retención disponibles para que se apliquen al modelo.</span><span class="sxs-lookup"><span data-stu-id="5824f-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="5824f-113">![Menú Etiqueta de retención](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="5824f-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="5824f-114">Seleccione la etiqueta de retención que desea aplicar al modelo y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5824f-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="5824f-115">Después de aplicar la etiqueta de retención al modelo, podrá aplicarla a:</span><span class="sxs-lookup"><span data-stu-id="5824f-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="5824f-116">una nueva biblioteca de documentos y</span><span class="sxs-lookup"><span data-stu-id="5824f-116">New document library</span></span>
- <span data-ttu-id="5824f-117">una biblioteca de documentos en la que ya se aplica el modelo.</span><span class="sxs-lookup"><span data-stu-id="5824f-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="5824f-118">Aplicar la etiqueta de retención a la biblioteca de documentos en la que ya se aplica el modelo</span><span class="sxs-lookup"><span data-stu-id="5824f-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="5824f-119">Si ya se ha aplicado el modelo de comprensión mediante documentos a una biblioteca de documentos, puede hacer lo siguiente para sincronizar la actualización de la etiqueta de retención y aplicarla en la biblioteca de documentos:</span><span class="sxs-lookup"><span data-stu-id="5824f-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="5824f-120">En la Página principal del modelo, en la sección **Bibliotecas con este modelo**, seleccione la biblioteca de documentos a la que quiera aplicar la actualización de la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="5824f-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="5824f-121">Seleccione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="5824f-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="5824f-122">![Modelo de sincronización](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="5824f-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="5824f-123">Después de aplicar la actualización y sincronizarla con el modelo, puede confirmar que se ha aplicado haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5824f-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="5824f-124">En el centro de contenido, en la sección **Bibliotecas con este modelo**, haga clic en la biblioteca a la que se ha aplicado el modelo actualizado.</span><span class="sxs-lookup"><span data-stu-id="5824f-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="5824f-125">En la vista de la biblioteca de documentos, seleccione el icono de información para ver las propiedades del modelo.</span><span class="sxs-lookup"><span data-stu-id="5824f-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="5824f-126">En la lista **Modelos activos**, seleccione el modelo actualizado.</span><span class="sxs-lookup"><span data-stu-id="5824f-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="5824f-127">En la sección **Etiqueta de retención** verá el nombre de la etiqueta de retención aplicada.</span><span class="sxs-lookup"><span data-stu-id="5824f-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="5824f-128">En la página de vista del modelo de la biblioteca de documentos, se mostrará una nueva columna de la **Etiqueta de retención**.</span><span class="sxs-lookup"><span data-stu-id="5824f-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="5824f-129">A medida que el modelo clasifica los archivos que identifica como pertenecientes al tipo de contenido y los muestra en la vista de biblioteca, en la columna Etiqueta de retención también se muestra el nombre de la etiqueta de retención que se ha aplicado a través del modelo.</span><span class="sxs-lookup"><span data-stu-id="5824f-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="5824f-130">Por ejemplo, todos los documentos de *Avisos de seguros* que su modelo identifique también tendrán la etiqueta de retención *Negocios* aplicada para que no se eliminen de la biblioteca de documentos durante cinco meses.</span><span class="sxs-lookup"><span data-stu-id="5824f-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="5824f-131">Si se intenta eliminar el archivo de la biblioteca de documentos, se mostrará un error que indica que no está permitido debido a la etiqueta de retención aplicada.</span><span class="sxs-lookup"><span data-stu-id="5824f-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="5824f-132">Agregar una etiqueta de retención a un modelo de comprensión mediante documentos</span><span class="sxs-lookup"><span data-stu-id="5824f-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="5824f-133">Para que las etiquetas de retención estén disponibles para aplicarlas a su modelo de procesamiento de formularios, deben [crearse y publicarse en el Centro de cumplimiento de Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="5824f-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="5824f-134">Puede aplicar una etiqueta de retención a un modelo de procesamiento de formularios cuando cree el modelo, o bien aplicarlo a un modelo ya existente.</span><span class="sxs-lookup"><span data-stu-id="5824f-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="5824f-135">Agregar una etiqueta de retención a un modelo de comprensión mediante documentos cuando se crea el modelo</span><span class="sxs-lookup"><span data-stu-id="5824f-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="5824f-136">Cuando cree un [nuevo modelo de procesamiento de formularios](./create-a-form-processing-model.md), seleccione la <b>Configuración avanzada.</b></span><span class="sxs-lookup"><span data-stu-id="5824f-136">When you are [creating a new form processing model](./create-a-form-processing-model.md), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="5824f-137">En <b>Configuración avanzada</b>, en la sección <b>Etiqueta de retención</b>, seleccione el menú y, después, seleccione la etiqueta de retención que quiere aplicar al modelo.</b></span><span class="sxs-lookup"><span data-stu-id="5824f-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![Agregar a un nuevo modelo de procesamiento de formularios](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="5824f-139">Cuando haya completado la configuración del modelo restante, seleccione <b>Crear</b> para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="5824f-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="5824f-140">Agregar una etiqueta de retención a un modelo de comprensión mediante documentos existente</span><span class="sxs-lookup"><span data-stu-id="5824f-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="5824f-141">Hay dos maneras de agregar una etiqueta de retención a un modelo de comprensión mediante documentos existente:</span><span class="sxs-lookup"><span data-stu-id="5824f-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="5824f-142">A través del menú Automatizar de la biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="5824f-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="5824f-143">A través de la configuración del Modelo activo en la biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="5824f-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="5824f-144">Agregar una etiqueta de retención a un modelo de comprensión mediante documentos existente con el menú Automatizar</span><span class="sxs-lookup"><span data-stu-id="5824f-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="5824f-145">Puede agregar una etiqueta de retención a un modelo de procesamiento de formularios existente del que sea propietario mediante el menú Automatizar de la biblioteca de documentos en la que se aplica el modelo.</span><span class="sxs-lookup"><span data-stu-id="5824f-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="5824f-146">En la biblioteca de documentos a la que se aplica el modelo de procesamiento de formularios, seleccione el menú <b>Automatizar</b>, luego <b>AI Builder</b> y finalmente <b>Ver detalles del modelo de procesamiento de formularios</b>.</span><span class="sxs-lookup"><span data-stu-id="5824f-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![Menú Automatizar](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="5824f-148">En los detalles del modelo, en <b>Etiqueta de retención</b>, seleccione la etiqueta de retención que quiera aplicar.</span><span class="sxs-lookup"><span data-stu-id="5824f-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="5824f-149">Después, seleccione <b>Guardar</b>.</span><span class="sxs-lookup"><span data-stu-id="5824f-149">Then select <b>Save</b>.</span></span>

     ![Agregar a un modelo de procesamiento de formularios ya existente](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="5824f-151">Agregar una etiqueta de retención a un modelo de procesamiento de formularios existente en la configuración del modelo activo</span><span class="sxs-lookup"><span data-stu-id="5824f-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="5824f-152">Puede agregar una etiqueta de retención a un modelo de procesamiento de formulario existente del que sea propietario en la configuración del Modelo activo de la biblioteca de documentos en la que se aplica el modelo.</span><span class="sxs-lookup"><span data-stu-id="5824f-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="5824f-153">En la biblioteca de documentos de SharePoint en la que se aplica el modelo, seleccione el icono <b>Ver modelos activos</b> y, después, seleccione <b>Ver modelos activos</b>.</b></span><span class="sxs-lookup"><span data-stu-id="5824f-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![Ver modelos activos](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="5824f-155">En <b>Modelos activos</b>, seleccione el modelo de procesamiento de formularios al que quiere aplicar la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="5824f-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![Detalles del modelo](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="5824f-157">En los detalles del modelo, en <b>Etiqueta de retención</b>, seleccione la etiqueta de retención que quiera aplicar.</span><span class="sxs-lookup"><span data-stu-id="5824f-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="5824f-158">Después, seleccione <b>Guardar</b>.</span><span class="sxs-lookup"><span data-stu-id="5824f-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="5824f-159">Debe ser el propietario del modelo del panel de configuración del modelo para poder editarlo.</span><span class="sxs-lookup"><span data-stu-id="5824f-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="5824f-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5824f-160">See Also</span></span>
[<span data-ttu-id="5824f-161">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="5824f-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="5824f-162">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="5824f-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="5824f-163">Información general de la comprensión mediante documentos </span><span class="sxs-lookup"><span data-stu-id="5824f-163">Document Understanding overview</span></span>](document-understanding-overview.md)
