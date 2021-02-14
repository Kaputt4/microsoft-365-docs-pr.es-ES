---
title: Configurar etiquetas inteligentes en eDiscovery avanzado
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
ROBOTS: NOINDEX, NOFOLLOW
description: Las etiquetas inteligentes le permiten aplicar las capacidades de aprendizaje automático al revisar el contenido en un caso de eDiscovery avanzado. Use grupos de etiquetas inteligentes para mostrar los resultados de modelos de detección de aprendizaje automático, como el modelo de privilegios abogado-cliente.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081087"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="8a628-104">Configurar etiquetas inteligentes en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="8a628-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="8a628-105">Las capacidades de aprendizaje automático (ML) en eDiscovery avanzado pueden ayudarle a hacer que el proceso de decisión sea más eficaz al revisar documentos de casos en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="8a628-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="8a628-106">Las etiquetas inteligentes son una forma de llevar las capacidades de ML al lugar donde se registran las decisiones: al etiquetar documentos durante la revisión.</span><span class="sxs-lookup"><span data-stu-id="8a628-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="8a628-107">Cuando crea un grupo de etiquetas inteligentes, las decisiones que son el resultado del modelo de ML que ha asociado con el grupo de etiquetas inteligentes se muestran en línea con las etiquetas del grupo de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="8a628-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="8a628-108">Esto ayuda a ver la información de resultados de ML en línea al revisar documentos específicos.</span><span class="sxs-lookup"><span data-stu-id="8a628-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="8a628-109">Cómo configurar un grupo de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="8a628-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="8a628-110">En un conjunto de revisión, haga **clic en Administrar conjunto de revisión** y, a continuación, haga clic en Administrar **etiquetas.**</span><span class="sxs-lookup"><span data-stu-id="8a628-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="8a628-111">Haga **clic en Agregar grupo de** etiquetas **y, a continuación, seleccione Agregar grupo de etiquetas inteligentes.**</span><span class="sxs-lookup"><span data-stu-id="8a628-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="8a628-112">Seleccione el modelo de ML que desea asociar al grupo de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="8a628-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="8a628-113">Esto crea un grupo de etiquetas y *N* etiquetas secundarias, donde *N* es el número de salidas posibles del modelo.</span><span class="sxs-lookup"><span data-stu-id="8a628-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="8a628-114">Por ejemplo, el modelo de detección de privilegios [abogado-cliente](attorney-privilege-detection.md) tiene dos salidas posibles:</span><span class="sxs-lookup"><span data-stu-id="8a628-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="8a628-115">**Positivo:** se usa para etiquetar documentos que contienen contenido con privilegios de abogado-cliente.</span><span class="sxs-lookup"><span data-stu-id="8a628-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="8a628-116">**Negativo:** se usa para etiquetar documentos que no contienen contenido con privilegios de abogado-cliente.</span><span class="sxs-lookup"><span data-stu-id="8a628-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="8a628-117">Si selecciona este modelo, se crea un grupo de etiquetas con dos etiquetas secundarias (una etiqueta secundaria denominada **Positive** y la otra denominada **Negative)** para el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="8a628-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="8a628-118">En este ejemplo, cada etiqueta secundaria corresponde a uno de los posibles resultados del modelo de detección de privilegios abogado-cliente.</span><span class="sxs-lookup"><span data-stu-id="8a628-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="8a628-119">Opcionalmente, puede cambiar el nombre del grupo de etiquetas y las etiquetas secundarias.</span><span class="sxs-lookup"><span data-stu-id="8a628-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="8a628-120">Por ejemplo, puede cambiar el nombre de la **etiqueta Positive** a **Privileged** y **negative** a **Not privileged**.</span><span class="sxs-lookup"><span data-stu-id="8a628-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="8a628-121">Cómo usar etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="8a628-121">How to use smart tags</span></span>

<span data-ttu-id="8a628-122">Al revisar un documento, los resultados del modelo se muestran junto a la etiqueta secundaria adecuada.</span><span class="sxs-lookup"><span data-stu-id="8a628-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="8a628-123">Por ejemplo, si tiene un grupo de etiquetas inteligentes para la detección de privilegios abogado-cliente y revisa un documento que puede tener privilegios, el motivo de esa conclusión se muestra junto a la etiqueta adecuada.</span><span class="sxs-lookup"><span data-stu-id="8a628-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="8a628-124">Es importante tener en cuenta que la etiqueta no se aplica automáticamente al documento.</span><span class="sxs-lookup"><span data-stu-id="8a628-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="8a628-125">El revisor toma la decisión sobre cómo etiquetar el documento.</span><span class="sxs-lookup"><span data-stu-id="8a628-125">The reviewer makes the decision about how to tag the document.</span></span>
