---
title: Cambiar el nombre de un extractor en Microsoft SharePoint Syntex
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
description: Obtenga información sobre cómo y por qué cambiar el nombre de un extractor en Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446055"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="4a0c2-103">Cambiar el nombre de un extractor en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4a0c2-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="4a0c2-104">En algún momento, puede que tenga que cambiar el nombre de un extractor para referirse a un campo de datos extraído por un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="4a0c2-105">Por ejemplo, su organización decide realizar cambios en sus documentos de contrato y se refiere a los "consumidores" como "clientes" en sus documentos.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="4a0c2-106">Si estaba extrayendo un campo "Consumidor" en su modelo, puede cambiarle el nombre a "Cliente".</span><span class="sxs-lookup"><span data-stu-id="4a0c2-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="4a0c2-107">Al sincronizar el modelo actualizado con la biblioteca de documentos de SharePoint, verá una nueva columna de "Cliente" en la vista de biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="4a0c2-108">La vista conservará la columna "Consumidor" para la actividad anterior, pero actualizará la nueva columna "Cliente" para todos los documentos nuevos que procese su modelo.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="4a0c2-109">Asegúrese de sincronizar el modelo actualizado con las bibliotecas de documentos donde lo había aplicado anteriormente para que se muestre el nuevo nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="4a0c2-110">Cambiar el nombre de un extractor</span><span class="sxs-lookup"><span data-stu-id="4a0c2-110">Rename an extractor</span></span>

<span data-ttu-id="4a0c2-111">Siga estos pasos para cambiar el nombre de un extractor de entidades.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="4a0c2-112">Desde el centro de contenido, seleccione **Modelos** para ver la lista de modelos.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="4a0c2-113">En la página **Modelos**, en la columna **Nombre**, seleccione el modelo para el que quiere cambiar el nombre de un extractor.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="4a0c2-114">En **Extractores de entidades**, seleccione el nombre del extractor al que quiere cambiar el nombre y, después, **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![Captura de pantalla de la sección de Extractores de entidades que muestra un extractor seleccionado con la opción Cambiar nombre resaltada.](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="4a0c2-116">En el panel **Cambiar nombre al extractor de entidades**:</span><span class="sxs-lookup"><span data-stu-id="4a0c2-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="4a0c2-117">a.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-117">a.</span></span> <span data-ttu-id="4a0c2-118">En **Nuevo nombre**, escriba el nuevo nombre del extractor.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![Captura de pantalla en la que se muestra el panel del Extractor de entidades.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="4a0c2-120">b.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-120">b.</span></span> <span data-ttu-id="4a0c2-121">(Opcional) En **Configuración avanzada**, seleccione si quiere asociar una columna de sitio existente.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="4a0c2-122">Seleccione **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="4a0c2-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a0c2-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a0c2-123">See Also</span></span>
[<span data-ttu-id="4a0c2-124">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="4a0c2-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="4a0c2-125">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="4a0c2-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="4a0c2-126">Cambiar el nombre de un modelo</span><span class="sxs-lookup"><span data-stu-id="4a0c2-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="4a0c2-127">Tipos de explicación</span><span class="sxs-lookup"><span data-stu-id="4a0c2-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="4a0c2-128">Aprovechar la taxonomía del almacén de términos al crear un extractor</span><span class="sxs-lookup"><span data-stu-id="4a0c2-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="4a0c2-129">Información general sobre la comprensión mediante documentos</span><span class="sxs-lookup"><span data-stu-id="4a0c2-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="4a0c2-130">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="4a0c2-130">Apply a model</span></span>](apply-a-model.md) 
