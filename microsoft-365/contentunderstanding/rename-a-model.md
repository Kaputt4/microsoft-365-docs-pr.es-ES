---
title: Cambiar el nombre de un modelo en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenga información sobre cómo y por qué cambiar el nombre de un modelo en Microsoft SharePoint Syntex.
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446061"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="7079f-103">Cambiar el nombre de un modelo en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="7079f-103">Rename a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="7079f-104">En algún momento, puede que quiera cambiar el nombre de un modelo de comprensión mediante documentos.</span><span class="sxs-lookup"><span data-stu-id="7079f-104">At some point, you might want to rename a document understanding model.</span></span> <span data-ttu-id="7079f-105">Un ejemplo común es cuando crea un borrador inicial de un modelo, para el que posiblemente no haya pensado demasiado en el nombre final (por ejemplo, es posible que lo llamara "AlexInerbaModel1").</span><span class="sxs-lookup"><span data-stu-id="7079f-105">A common example is when you create an initial draft of a model, you might not have given a lot of thought as to the final name (for example, you might have named it “AlexWilburModel1”).</span></span> <span data-ttu-id="7079f-106">A medida que está más cerca de finalizar el modelo y ponerlo en uso, se da cuenta de que un nombre más apropiado sería "Renovaciones de contrato" y decide cambiarle el nombre.</span><span class="sxs-lookup"><span data-stu-id="7079f-106">As you come closer to finalizing the model and putting it to use, you realize that a more proper name would be “Contract Renewals,” and you want to rename it.</span></span>  

<span data-ttu-id="7079f-107">Otro ejemplo es cuando su organización toma la decisión de referirse a un proceso o tipo de documento con un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="7079f-107">Another example is when your organization makes a decision to refer to a process or document type by a different name.</span></span> <span data-ttu-id="7079f-108">Por ejemplo, después de crear el modelo y estar listo para aplicarlo, su organización podría pensar que todos los elementos con el nombre "Contratos" ahora se denominarán formalmente "Acuerdos".</span><span class="sxs-lookup"><span data-stu-id="7079f-108">For example, after you create your model and are ready to apply it, your organization might mandate that all “Contracts” will now formally be referred to as “Agreements.”</span></span> <span data-ttu-id="7079f-109">Si es necesario, puede elegir cambiar el nombre del modelo de "Renovaciones de contrato" a "Renovaciones de contrato".</span><span class="sxs-lookup"><span data-stu-id="7079f-109">If needed, you can choose to rename your model from “Contract Renewals” to “Agreement Renewals.”</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7079f-110">Solo puede cambiar el nombre de un modelo de comprensión mediante documentos si no se ha aplicado a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="7079f-110">You can only rename a document understanding model if it has not been applied to a document library.</span></span> 

<span data-ttu-id="7079f-111">Al cambiar el nombre de un modelo también se cambia el [tipo de contenido](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que está asociado al modelo.</span><span class="sxs-lookup"><span data-stu-id="7079f-111">Renaming a model also renames the [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that is associated with the model.</span></span>

## <a name="rename-a-model"></a><span data-ttu-id="7079f-112">Cambiar el nombre de un modelo</span><span class="sxs-lookup"><span data-stu-id="7079f-112">Rename a model</span></span>

<span data-ttu-id="7079f-113">Siga estos pasos para cambiar el nombre a un modelo de comprensión mediante documentos.</span><span class="sxs-lookup"><span data-stu-id="7079f-113">Follow these steps to rename a document understanding model.</span></span>

1. <span data-ttu-id="7079f-114">Desde el centro de contenido, seleccione **Modelos** para ver la lista de modelos.</span><span class="sxs-lookup"><span data-stu-id="7079f-114">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="7079f-115">En la página **Modelos**, seleccione el modelo al que quiere cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="7079f-115">On the **Models** page, select the model you want to rename.</span></span>

3. <span data-ttu-id="7079f-116">Mediante la cinta de opciones o el botón **Mostrar acciones** (junto al nombre del modelo), seleccione **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="7079f-116">By using either the ribbon or the **Show actions** button (next to the model name), select **Rename**.</span></span> </br>

    ![Captura de pantalla de la página Modelos que muestra un modelo seleccionado con las opciones de Cambiar nombre resaltadas.](../media/content-understanding/select-model-rename-both.png) </br>

4. <span data-ttu-id="7079f-118">En el panel **Cambiar nombre del modelo**:</span><span class="sxs-lookup"><span data-stu-id="7079f-118">On the **Rename model** panel:</span></span>

   <span data-ttu-id="7079f-119">a.</span><span class="sxs-lookup"><span data-stu-id="7079f-119">a.</span></span> <span data-ttu-id="7079f-120">En **Nuevo nombre**, escriba el nuevo nombre del modelo cuyo nombre quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="7079f-120">Under **New name**, enter the new name of the model that you want to rename.</span></span></br>

    ![Captura de pantalla que muestra el panel Cambiar nombre del modelo.](../media/content-understanding/rename-model-panel.png) </br>

   <span data-ttu-id="7079f-122">b.</span><span class="sxs-lookup"><span data-stu-id="7079f-122">b.</span></span> <span data-ttu-id="7079f-123">(Opcional) En **Configuración avanzada**, seleccione si quiere asociar un [tipo de contenido](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) existente.</span><span class="sxs-lookup"><span data-stu-id="7079f-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span> <span data-ttu-id="7079f-124">Si elige **Usar un tipo de contenido existente**, se cambiará el nombre del modelo para que coincida con el tipo de contenido seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7079f-124">If you choose **Use an existing content type**, the model will be renamed to match the selected content type.</span></span>

5. <span data-ttu-id="7079f-125">Seleccione **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="7079f-125">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7079f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7079f-126">See Also</span></span>
[<span data-ttu-id="7079f-127">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="7079f-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="7079f-128">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="7079f-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="7079f-129">Cambiar el nombre de un extractor</span><span class="sxs-lookup"><span data-stu-id="7079f-129">Rename an extractor</span></span>](rename-an-extractor.md)

[<span data-ttu-id="7079f-130">Información general sobre la comprensión de los documentos</span><span class="sxs-lookup"><span data-stu-id="7079f-130">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="7079f-131">Tipos de explicación</span><span class="sxs-lookup"><span data-stu-id="7079f-131">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="7079f-132">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="7079f-132">Apply a model</span></span>](apply-a-model.md) 
