---
title: Duplicar un modelo en Microsoft SharePoint Syntex
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
description: Obtenga información sobre cómo y por qué duplicar un modelo en Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446082"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="305fa-103">Duplicar un modelo en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="305fa-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="305fa-104">Duplicar un modelo de compresión mediante documentos puede ahorrarle tiempo y esfuerzo si necesita crear un modelo nuevo y saber si un modelo existente es muy similar a lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="305fa-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="305fa-105">Por ejemplo, un modelo existente denominado "Contratos" clasifica los mismos archivos con los que tiene que trabajar.</span><span class="sxs-lookup"><span data-stu-id="305fa-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="305fa-106">El nuevo modelo extraerá algunos de los datos existentes, pero necesitará ser actualizado para poder extraer datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="305fa-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="305fa-107">En lugar de crear y entrenar un modelo desde cero, puede usar la característica de modelo duplicado para hacer una copia del modelo Contratos, que también copiará todos los elementos de aprendizaje asociados, como los archivos de ejemplo y los extractores de entidades.</span><span class="sxs-lookup"><span data-stu-id="305fa-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="305fa-108">Cuando duplique el modelo, después de cambiarle el nombre (por ejemplo, a "Renovaciones de contrato"), podrá realizar actualizaciones en él.</span><span class="sxs-lookup"><span data-stu-id="305fa-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="305fa-109">Por ejemplo, puede quitar algunos de los campos extraídos existentes que no necesite y, después, entrenar el modelo para extraer uno nuevo (por ejemplo, "Fecha de renovación").</span><span class="sxs-lookup"><span data-stu-id="305fa-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="305fa-110">Duplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="305fa-110">Duplicate a model</span></span>

<span data-ttu-id="305fa-111">Siga estos pasos para duplicar un modelo de comprensión mediante documentos.</span><span class="sxs-lookup"><span data-stu-id="305fa-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="305fa-112">Desde el centro de contenido, seleccione **Modelos** para ver la lista de modelos.</span><span class="sxs-lookup"><span data-stu-id="305fa-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="305fa-113">En la página **Modelos**, seleccione el modelo que quiere duplicar.</span><span class="sxs-lookup"><span data-stu-id="305fa-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="305fa-114">Mediante la cinta de opciones o el botón **Mostrar acciones** (junto al nombre del modelo), seleccione **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="305fa-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![Captura de pantalla de la página Modelos que muestra un modelo seleccionado con las opciones de Duplicar resaltadas.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="305fa-116">En el panel **Duplicar modelo**:</span><span class="sxs-lookup"><span data-stu-id="305fa-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="305fa-117">a.</span><span class="sxs-lookup"><span data-stu-id="305fa-117">a.</span></span> <span data-ttu-id="305fa-118">En **Nombre**, escriba el nuevo nombre del modelo que quiere duplicar.</span><span class="sxs-lookup"><span data-stu-id="305fa-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![Captura de pantalla que muestra el panel Duplicar modelo.](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="305fa-120">b.</span><span class="sxs-lookup"><span data-stu-id="305fa-120">b.</span></span> <span data-ttu-id="305fa-121">En **Descripción**, agregue una descripción del modelo nuevo.</span><span class="sxs-lookup"><span data-stu-id="305fa-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="305fa-122">c.</span><span class="sxs-lookup"><span data-stu-id="305fa-122">c.</span></span> <span data-ttu-id="305fa-123">(Opcional) En **Configuración avanzada**, seleccione si quiere asociar un [tipo de contenido](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) existente.</span><span class="sxs-lookup"><span data-stu-id="305fa-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="305fa-124">Seleccione **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="305fa-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="305fa-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="305fa-125">See Also</span></span>
[<span data-ttu-id="305fa-126">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="305fa-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="305fa-127">Cambiar el nombre de un modelo</span><span class="sxs-lookup"><span data-stu-id="305fa-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="305fa-128">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="305fa-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="305fa-129">Información general sobre la comprensión de los documentos</span><span class="sxs-lookup"><span data-stu-id="305fa-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="305fa-130">Tipos de explicación</span><span class="sxs-lookup"><span data-stu-id="305fa-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="305fa-131">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="305fa-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="305fa-132">Modo de accesibilidad de SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="305fa-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)