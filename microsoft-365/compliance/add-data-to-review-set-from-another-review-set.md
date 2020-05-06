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
description: Obtenga información sobre cómo seleccionar documentos de un conjunto de revisión y trabajar con ellos de forma individual en otro conjunto en un caso de exhibición avanzada de documentos electrónicos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 636e76b1740cfa07254e4c56165cfafa8f1fad5a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034684"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="2d39c-103">Agregar datos a un conjunto de revisión desde otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="2d39c-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="2d39c-104">En algunos casos, puede ser necesario seleccionar documentos de un conjunto de revisión y trabajar con ellos de forma individual en otro conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2d39c-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="2d39c-105">Esto es especialmente útil si ha seleccionado contenido en un conjunto de revisión y desea ejecutar análisis en el subconjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="2d39c-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="2d39c-106">Siga el flujo de trabajo de este artículo para agregar contenido de un conjunto de revisión a otro.</span><span class="sxs-lookup"><span data-stu-id="2d39c-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2d39c-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2d39c-107">Before you begin</span></span>

<span data-ttu-id="2d39c-108">Antes de empezar, deberá crear un nuevo conjunto de revisión para agregar los datos a.</span><span class="sxs-lookup"><span data-stu-id="2d39c-108">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="2d39c-109">Se puede Agregar un nuevo conjunto de revisiones en la ficha **Review sets** del caso.</span><span class="sxs-lookup"><span data-stu-id="2d39c-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="2d39c-110">Para obtener más información, vea [Create a Review Set](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="2d39c-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="2d39c-111">Paso 1: identificar el contenido que se va a agregar a otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="2d39c-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="2d39c-112">Puede agregar contenido de un conjunto de revisión a otro seleccionando documentos específicos en el conjunto de revisión de origen o seleccionando todos los elementos devueltos por el conjunto de revisión consulta.</span><span class="sxs-lookup"><span data-stu-id="2d39c-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="2d39c-113">Si está agregando elementos seleccionados, seleccione los elementos, seleccione **acción**y, a continuación, seleccione **Agregar a otro conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="2d39c-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Agregar a otro conjunto de revisión](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="2d39c-115">Paso 2: especificar opciones para agregar a otro conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="2d39c-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="2d39c-116">En la página **Agregar a otro** control flotante opciones de definición de revisión, elija el conjunto de revisiones al que desea agregar los elementos.</span><span class="sxs-lookup"><span data-stu-id="2d39c-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="2d39c-117">Elija si desea agregar **todos los resultados de búsqueda** o los **elementos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="2d39c-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="2d39c-118">**Información adicional** proporciona opciones para incluir todos los metadatos de los elementos y si desea incluir las etiquetas (activando la casilla de verificación **etiquetas** ) en el conjunto de revisión de origen cuando se agregan los documentos al nuevo conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2d39c-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Agregar a otro conjunto de revisión](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="2d39c-120">Después de hacer clic en **Aceptar**, se crea un nuevo trabajo (denominado **Agregar datos a otro conjunto de revisión**) para agregar el contenido a otro conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2d39c-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="2d39c-121">Puede ir a la pestaña **trabajos** y supervisar el progreso de este trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d39c-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="2d39c-122">Para obtener más información, consulte [Manage Jobs](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="2d39c-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
