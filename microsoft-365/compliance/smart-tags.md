---
title: Configurar etiquetas inteligentes en la exhibición avanzada de documentos electrónicos
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
description: Las etiquetas inteligentes le permiten aplicar las funciones de aprendizaje automático al revisar el contenido en un caso de exhibición avanzada de documentos electrónicos. Use los grupos de etiquetas inteligentes para mostrar los resultados de los modelos de detección de aprendizaje automático, como el modelo de privilegios de clientes de abogados.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081087"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="c9e08-104">Configurar etiquetas inteligentes en la exhibición avanzada de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="c9e08-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="c9e08-105">Las capacidades de machine learning (ML) en eDiscovery avanzado pueden ayudarle a que el proceso de toma de decisiones sea más eficaz al revisar los documentos de casos en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="c9e08-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="c9e08-106">Las etiquetas inteligentes son una forma de llevar las capacidades de los ML a donde se registran las decisiones: al etiquetar documentos durante la revisión.</span><span class="sxs-lookup"><span data-stu-id="c9e08-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="c9e08-107">Al crear un grupo de etiquetas inteligentes, las decisiones que son el resultado del modelo de los ML que ha asociado al grupo de etiquetas inteligentes se muestran en línea con las etiquetas del grupo de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="c9e08-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="c9e08-108">Esto ayuda a ver la información de resultados de los ML en línea cuando se están revisando documentos específicos.</span><span class="sxs-lookup"><span data-stu-id="c9e08-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="c9e08-109">Cómo configurar un grupo de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="c9e08-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="c9e08-110">En un conjunto de revisiones, haga clic en **administrar conjunto de revisiones** y, a continuación, en **administrar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="c9e08-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="c9e08-111">Haga clic en **Agregar grupo de etiquetas** y, a continuación, seleccione **Agregar grupo de etiquetas inteligentes**.</span><span class="sxs-lookup"><span data-stu-id="c9e08-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="c9e08-112">Seleccione el modelo de ML que desea asociar al grupo de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="c9e08-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="c9e08-113">Se crea un grupo de etiquetas y *n* etiquetas secundarias, donde *N* es el número de posibles salidas del modelo.</span><span class="sxs-lookup"><span data-stu-id="c9e08-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="c9e08-114">Por ejemplo, el [modelo de detección de privilegios de clientes de abogados](attorney-privilege-detection.md) tiene dos posibles resultados:</span><span class="sxs-lookup"><span data-stu-id="c9e08-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="c9e08-115">**Positivo** : Use para etiquetar documentos que contengan contenido privilegiado con el cliente de abogados.</span><span class="sxs-lookup"><span data-stu-id="c9e08-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="c9e08-116">**Negativo** : se usa para etiquetar documentos que no contienen contenido privilegiado de clientes.</span><span class="sxs-lookup"><span data-stu-id="c9e08-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="c9e08-117">Si selecciona este modelo, se crea un grupo de etiquetas con dos etiquetas secundarias (una etiqueta secundaria llamada **positivo** y la otra llamada **negativo**) para el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="c9e08-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="c9e08-118">En este ejemplo, cada etiqueta secundaria corresponde a uno de los resultados posibles del modelo de detección de privilegios de cliente de abogado.</span><span class="sxs-lookup"><span data-stu-id="c9e08-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="c9e08-119">Si lo desea, puede cambiar el nombre del grupo de etiquetas y de las etiquetas secundarias.</span><span class="sxs-lookup"><span data-stu-id="c9e08-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="c9e08-120">Por ejemplo, podría cambiar el nombre de la etiqueta **positiva** a **privileged** y la etiqueta **negativa** a **no privileged**.</span><span class="sxs-lookup"><span data-stu-id="c9e08-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="c9e08-121">Cómo usar las etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="c9e08-121">How to use smart tags</span></span>

<span data-ttu-id="c9e08-122">Al revisar un documento, se muestran los resultados del modelo junto a la etiqueta secundaria correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c9e08-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="c9e08-123">Por ejemplo, si tiene un grupo de etiquetas inteligentes para la detección de privilegios de clientes y revisa un documento que puede tener privilegios, se mostrará el motivo de dicha conclusión junto a la etiqueta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c9e08-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="c9e08-124">Es importante tener en cuenta que la etiqueta no se aplica automáticamente al documento.</span><span class="sxs-lookup"><span data-stu-id="c9e08-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="c9e08-125">El revisor toma la decisión sobre cómo etiquetar el documento.</span><span class="sxs-lookup"><span data-stu-id="c9e08-125">The reviewer makes the decision about how to tag the document.</span></span>
