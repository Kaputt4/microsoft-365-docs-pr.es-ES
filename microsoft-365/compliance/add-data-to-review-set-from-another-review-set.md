---
title: Agregar datos de un conjunto de revisión a otro conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo seleccionar documentos de un conjunto de revisión y trabajar con ellos individualmente en otro conjunto en un Advanced eDiscovery caso.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285195"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="c1c81-103">Agregar datos a un conjunto de revisión desde otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="c1c81-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="c1c81-104">En algunos casos, puede que sea necesario seleccionar documentos de un conjunto de revisión y trabajar con ellos individualmente en otro conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="c1c81-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="c1c81-105">Esto es especialmente útil si ha seleccionado contenido en un conjunto de revisión y quiere ejecutar un análisis en el subconjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="c1c81-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="c1c81-106">Siga el flujo de trabajo de este artículo para agregar contenido de un conjunto de revisión a otro.</span><span class="sxs-lookup"><span data-stu-id="c1c81-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="c1c81-107">Crear un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="c1c81-107">Create a review set</span></span>

<span data-ttu-id="c1c81-108">Antes de empezar, deberá crear un conjunto de revisión para agregar los datos.</span><span class="sxs-lookup"><span data-stu-id="c1c81-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="c1c81-109">Se puede agregar un nuevo conjunto de revisión en la **pestaña Conjuntos de revisión** del caso.</span><span class="sxs-lookup"><span data-stu-id="c1c81-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="c1c81-110">Para obtener más información, vea [Create a review set](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="c1c81-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="c1c81-111">Paso 1: Identificar el contenido que se agregará a otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="c1c81-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="c1c81-112">Para agregar contenido de un conjunto de revisión a otro, seleccione documentos específicos en el conjunto de revisión de origen o seleccione todos los elementos devueltos por la consulta del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="c1c81-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="c1c81-113">Si va a agregar elementos seleccionados, seleccione los elementos, **seleccione Acción** y, a continuación, seleccione Agregar a otro conjunto **de revisión**.</span><span class="sxs-lookup"><span data-stu-id="c1c81-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Agregar a otro conjunto de revisión en el menú Acción](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="c1c81-115">Paso 2: Especificar opciones para agregar a otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="c1c81-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="c1c81-116">En la **página desplegable Agregar a otro** conjunto de revisión, elija el conjunto de revisión al que desea agregar los elementos.</span><span class="sxs-lookup"><span data-stu-id="c1c81-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="c1c81-117">Elija si desea agregar **Todos los resultados de búsqueda** o Elementos **seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="c1c81-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="c1c81-118">**La** información adicional proporciona opciones para incluir todos los metadatos de  los elementos y si se deben incluir las etiquetas (seleccionando la casilla Etiquetas) del conjunto de revisión de origen cuando se agregan los documentos al nuevo conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="c1c81-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Opciones para agregar datos a otro conjunto de revisión](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="c1c81-120">Después de hacer clic **en Aceptar,** se crea un nuevo trabajo (denominado **Agregar datos** a otro conjunto de revisión) para agregar el contenido a otro conjunto de opiniones.</span><span class="sxs-lookup"><span data-stu-id="c1c81-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="c1c81-121">Puede ir a la pestaña **Trabajos** y supervisar el progreso de este trabajo.</span><span class="sxs-lookup"><span data-stu-id="c1c81-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="c1c81-122">Para obtener más información, vea [Administrar trabajos](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="c1c81-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
