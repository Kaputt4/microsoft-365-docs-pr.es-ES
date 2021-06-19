---
title: Aplicar una etiqueta de confidencialidad a un modelo en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenga información sobre cómo aplicar una etiqueta de confidencialidad a un modelo en SharePoint Syntex.
ms.openlocfilehash: 2ddfd6ffe11e8e01e32b6e1b5ddf65763e4ae381
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022419"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="28f82-103">Aplicar una etiqueta de confidencialidad a un modelo en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="28f82-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="28f82-104">Puede aplicar fácilmente una [etiqueta de confidencialidad](../compliance/sensitivity-labels.md) a un modelo de comprensión mediante documentos en Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="28f82-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="28f82-105">Esta característica no está disponible todavía para los modelos de procesamiento de formularios.</span><span class="sxs-lookup"><span data-stu-id="28f82-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="28f82-106">Las etiquetas de confidencialidad le permiten aplicar directivas de cifrado, de uso compartido y de acceso condicional a los documentos que sus modelos identifiquen.</span><span class="sxs-lookup"><span data-stu-id="28f82-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="28f82-107">Ejemplo de uso: desea que el modelo no solo identifique los documentos financieros que contienen números de cuenta bancaria o de tarjeta de crédito que se cargan en la biblioteca de documentos, sino también que aplique una etiqueta de confidencialidad de *Cifrado* para restringir quién puede tener acceso a ese contenido y cómo se puede usar.</span><span class="sxs-lookup"><span data-stu-id="28f82-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span> <span data-ttu-id="28f82-108">Los modelos Syntex respetan [orden de las etiquetas](../compliance/apply-sensitivity-label-automatically.md?view=o365-worldwide#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label)reglas y tampoco sobrescriben una etiqueta existente aplicada manualmente por un usuario al archivo.</span><span class="sxs-lookup"><span data-stu-id="28f82-108">Syntex models honor [label order](../compliance/apply-sensitivity-label-automatically.md?view=o365-worldwide#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) rules and also do not overwrite an existing label that was manually applied by a user to the file.</span></span> 

<span data-ttu-id="28f82-109">Puede aplicar una etiqueta de confidencialidad preexistente al modelo en la página principal del modelo.</span><span class="sxs-lookup"><span data-stu-id="28f82-109">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="28f82-110">Para que esté disponible en la selección desde la configuración del modelo, la etiqueta ya debe haberse publicado.</span><span class="sxs-lookup"><span data-stu-id="28f82-110">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="28f82-111">Para que las etiquetas de confidencialidad estén disponibles para aplicarlas a su modelo de comprensión mediante documentos, deben [crearse y publicarse en el Centro de cumplimiento de Microsoft 365](../business-video/create-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="28f82-111">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="28f82-112">Agregar una etiqueta de confidencialidad a un modelo de comprensión mediante documentos</span><span class="sxs-lookup"><span data-stu-id="28f82-112">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="28f82-113">En la página principal del modelo, seleccione **Configuración del modelo**.</span><span class="sxs-lookup"><span data-stu-id="28f82-113">From the model home page, select **Model settings**.</span></span>

   ![Captura de pantalla de la página Modelos con la opción Configuración de modelo resaltada.](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="28f82-115">En el panel **Configuración del modelo**, sección **Cumplimiento**, seleccione el menú **Etiqueta de confidencialidad** para ver una lista de las etiquetas de confidencialidad disponibles para que se apliquen al modelo.</span><span class="sxs-lookup"><span data-stu-id="28f82-115">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![Captura de pantalla del panel Configuración del modelo que muestra el menú de etiqueta de confidencialidad.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="28f82-117">Seleccione la etiqueta de confidencialidad que desea aplicar al modelo y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28f82-117">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="28f82-118">Después de aplicar la etiqueta de confidencialidad al modelo, puede aplicarla a:</span><span class="sxs-lookup"><span data-stu-id="28f82-118">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="28f82-119">una nueva biblioteca de documentos y</span><span class="sxs-lookup"><span data-stu-id="28f82-119">New document library</span></span>
- <span data-ttu-id="28f82-120">una biblioteca de documentos en la que ya se aplica el modelo.</span><span class="sxs-lookup"><span data-stu-id="28f82-120">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="28f82-121">Aplicar la etiqueta de confidencialidad a la biblioteca de documentos en la que ya se aplica el modelo</span><span class="sxs-lookup"><span data-stu-id="28f82-121">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="28f82-122">Si ya se ha aplicado el modelo de comprensión mediante documentos a una biblioteca de documentos, puede hacer lo siguiente para sincronizar la actualización de la etiqueta de confidencialidad y aplicarla en la biblioteca de documentos:</span><span class="sxs-lookup"><span data-stu-id="28f82-122">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="28f82-123">En la Página principal del modelo, sección **Bibliotecas con este modelo**, seleccione la biblioteca de documentos a la que quiera aplicar la actualización de la etiqueta de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="28f82-123">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="28f82-124">Seleccione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="28f82-124">Select **Sync**.</span></span>

   ![Captura de pantalla que muestra la sección Bibliotecas en este modelo con Sincronización resaltada.](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="28f82-126">Después de aplicar la actualización y sincronizarla con el modelo, puede confirmar que se ha aplicado haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28f82-126">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="28f82-127">En el centro de contenido, sección **Bibliotecas con este modelo**, seleccione la biblioteca a la que se ha aplicado el modelo actualizado.</span><span class="sxs-lookup"><span data-stu-id="28f82-127">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="28f82-128">En la vista de la biblioteca de documentos, seleccione el icono de información para ver las propiedades del modelo.</span><span class="sxs-lookup"><span data-stu-id="28f82-128">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="28f82-129">En la lista **Modelos activos**, seleccione el modelo actualizado.</span><span class="sxs-lookup"><span data-stu-id="28f82-129">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="28f82-130">En la sección **etiqueta de confidencialidad**, verá el nombre de la etiqueta de confidencialidad aplicada.</span><span class="sxs-lookup"><span data-stu-id="28f82-130">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="28f82-131">En la página de vista del modelo de la biblioteca de documentos, se mostrará una nueva columna de la **Etiqueta de confidencialidad**.</span><span class="sxs-lookup"><span data-stu-id="28f82-131">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="28f82-132">A medida que el modelo clasifica los archivos que identifica como pertenecientes al tipo de contenido y los muestra en la vista de biblioteca, en la columna **Etiqueta de confidencialidad** también se muestra el nombre de la etiqueta de confidencialidad que se ha aplicado con el modelo.</span><span class="sxs-lookup"><span data-stu-id="28f82-132">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="28f82-133">Por ejemplo, en todos los documentos financieros que identifique el modelo también se aplicará la etiqueta de confidencialidad *Cifrado*, lo que evitará que los usuarios no autorizados tengan acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="28f82-133">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="28f82-134">Si una persona no autorizada intenta acceder al archivo desde la biblioteca de documentos, un error le informará de que no le está permitido debido a la etiqueta de confidencialidad aplicada.</span><span class="sxs-lookup"><span data-stu-id="28f82-134">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="28f82-135">Ver también</span><span class="sxs-lookup"><span data-stu-id="28f82-135">See also</span></span>

[<span data-ttu-id="28f82-136">Aplicar una etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="28f82-136">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="28f82-137">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="28f82-137">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="28f82-138">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="28f82-138">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="28f82-139">Información general de la comprensión mediante documentos </span><span class="sxs-lookup"><span data-stu-id="28f82-139">Document Understanding overview</span></span>](document-understanding-overview.md)
