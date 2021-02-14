---
title: Etiquetar documentos en un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: El etiquetado de documentos en un conjunto de revisión ayuda a quitar contenido innecesario e identificar el contenido relevante en un caso de eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285286"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="60d89-103">Etiquetar documentos en un conjunto de revisión en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="60d89-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="60d89-104">Organizar el contenido de un conjunto de revisión es importante para completar varios flujos de trabajo en el proceso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="60d89-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="60d89-105">Incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60d89-105">This includes:</span></span>

- <span data-ttu-id="60d89-106">Selección de contenido innecesario</span><span class="sxs-lookup"><span data-stu-id="60d89-106">Culling unnecessary content</span></span>

- <span data-ttu-id="60d89-107">Identificación de contenido relevante</span><span class="sxs-lookup"><span data-stu-id="60d89-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="60d89-108">Identificación del contenido que debe revisar un experto o un abogado</span><span class="sxs-lookup"><span data-stu-id="60d89-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="60d89-109">Cuando expertos, abogados u otros usuarios revisan el contenido de un conjunto de revisión, sus opiniones relacionadas con el contenido se pueden capturar mediante etiquetas.</span><span class="sxs-lookup"><span data-stu-id="60d89-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="60d89-110">Por ejemplo, si la intención es eliminar contenido innecesario, un usuario puede etiquetar documentos con una etiqueta como "no responde".</span><span class="sxs-lookup"><span data-stu-id="60d89-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="60d89-111">Después de revisar y etiquetar el contenido, se puede crear una búsqueda de conjunto de revisión para excluir cualquier contenido etiquetado como "no dinámico", lo que elimina este contenido de los siguientes pasos del flujo de trabajo de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="60d89-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="60d89-112">El panel de etiquetas se puede personalizar en cada caso para que las etiquetas admitan el flujo de trabajo de revisión previsto.</span><span class="sxs-lookup"><span data-stu-id="60d89-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="60d89-113">Tipos de etiquetas</span><span class="sxs-lookup"><span data-stu-id="60d89-113">Tag types</span></span>

<span data-ttu-id="60d89-114">EDiscovery avanzado proporciona dos tipos de etiquetas:</span><span class="sxs-lookup"><span data-stu-id="60d89-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="60d89-115">**Etiquetas de opción** única: restringe a los usuarios a seleccionar una sola etiqueta dentro de un grupo.</span><span class="sxs-lookup"><span data-stu-id="60d89-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="60d89-116">Esto puede ser útil para garantizar que los usuarios no seleccionen etiquetas conflictivas, como "responsive" y "non-responsive".</span><span class="sxs-lookup"><span data-stu-id="60d89-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="60d89-117">Aparecerán como botones de radio.</span><span class="sxs-lookup"><span data-stu-id="60d89-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="60d89-118">**Etiquetas de opción múltiple:** permitir a los usuarios seleccionar varias etiquetas dentro de un grupo.</span><span class="sxs-lookup"><span data-stu-id="60d89-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="60d89-119">Aparecerán como casillas.</span><span class="sxs-lookup"><span data-stu-id="60d89-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="60d89-120">Estructura de etiquetas</span><span class="sxs-lookup"><span data-stu-id="60d89-120">Tag structure</span></span>

<span data-ttu-id="60d89-121">Además de los tipos de etiquetas, la estructura de cómo se organizan las etiquetas en el panel de etiquetas se puede usar para que el etiquetado de documentos sea más intuitivo.</span><span class="sxs-lookup"><span data-stu-id="60d89-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="60d89-122">Las etiquetas se agrupan por secciones.</span><span class="sxs-lookup"><span data-stu-id="60d89-122">Tags are grouped by sections.</span></span> <span data-ttu-id="60d89-123">La búsqueda del conjunto de revisión admite la capacidad de buscar por etiqueta y por sección de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="60d89-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="60d89-124">Esto significa que puede crear una búsqueda de conjunto de revisión para recuperar documentos etiquetados con cualquier etiqueta de una sección.</span><span class="sxs-lookup"><span data-stu-id="60d89-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Secciones de etiquetas en el panel de etiquetas](../media/Tagtypes.png)

<span data-ttu-id="60d89-126">Las etiquetas se pueden organizar anidando dentro de una sección.</span><span class="sxs-lookup"><span data-stu-id="60d89-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="60d89-127">Por ejemplo, si la intención es identificar y etiquetar contenido con privilegios, el anidamiento puede usarse para dejar claro que un usuario puede etiquetar un documento como "Privileged" y seleccionar el tipo de privilegio comprobando la etiqueta anidada adecuada.</span><span class="sxs-lookup"><span data-stu-id="60d89-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Etiquetas anidadas dentro de una sección de etiquetas](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="60d89-129">Aplicar etiquetas</span><span class="sxs-lookup"><span data-stu-id="60d89-129">Applying tags</span></span>

<span data-ttu-id="60d89-130">Hay varias formas de aplicar una etiqueta al contenido.</span><span class="sxs-lookup"><span data-stu-id="60d89-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="60d89-131">Etiquetado de un solo documento</span><span class="sxs-lookup"><span data-stu-id="60d89-131">Tagging a single document</span></span>

<span data-ttu-id="60d89-132">Al ver un documento en un conjunto de revisión, puede mostrar las etiquetas que puede usar una revisión haciendo clic en **el panel de etiquetado.**</span><span class="sxs-lookup"><span data-stu-id="60d89-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Haga clic en Panel de etiquetas para mostrar el panel de etiquetas](../media/Singledoctag.png)

<span data-ttu-id="60d89-134">Esto le permitirá aplicar etiquetas al documento que se muestra en el visor.</span><span class="sxs-lookup"><span data-stu-id="60d89-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="60d89-135">Etiquetado masivo</span><span class="sxs-lookup"><span data-stu-id="60d89-135">Bulk tagging</span></span>

<span data-ttu-id="60d89-136">El etiquetado masivo se puede realizar seleccionando varios archivos en la cuadrícula de resultados y, a continuación, usando las etiquetas del **panel** de etiquetado de forma similar a etiquetar documentos individuales.</span><span class="sxs-lookup"><span data-stu-id="60d89-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="60d89-137">El des etiquetado masivo se puede realizar seleccionando etiquetas dos veces; El primer clic aplicará la etiqueta y la segunda se asegurará de que la etiqueta esté desactivada para todos los archivos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="60d89-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Captura de pantalla de una descripción de teléfono móvil generada automáticamente](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="60d89-139">Al etiquetar en masa, el panel de etiquetado mostrará un recuento de archivos etiquetados para cada etiqueta del panel.</span><span class="sxs-lookup"><span data-stu-id="60d89-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="60d89-140">Etiquetado en otros paneles de revisión</span><span class="sxs-lookup"><span data-stu-id="60d89-140">Tagging in other review panels</span></span>

<span data-ttu-id="60d89-141">Al revisar documentos, puede usar los demás paneles de revisión para revisar otras características de los documentos en la cuadrícula de resultados.</span><span class="sxs-lookup"><span data-stu-id="60d89-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="60d89-142">Esto incluye revisar otros documentos relacionados, subprocesos de correo electrónico, casi duplicados y duplicados hash.</span><span class="sxs-lookup"><span data-stu-id="60d89-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="60d89-143">Por ejemplo, al revisar documentos relacionados (mediante  el panel de revisión de la familia de documentos), puede reducir significativamente el tiempo de revisión mediante el etiquetado masivo de documentos relacionados.</span><span class="sxs-lookup"><span data-stu-id="60d89-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="60d89-144">Por ejemplo, si un mensaje de correo electrónico tiene varios datos adjuntos y desea asegurarse de que toda la familia se etiqueta de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="60d89-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="60d89-145">Por ejemplo, aquí se muestra cómo mostrar el panel de etiquetado al usar el **panel** **de revisión** de la familia de documentos:</span><span class="sxs-lookup"><span data-stu-id="60d89-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="60d89-146">Con el panel de revisión abierto para un documento seleccionado  (por ejemplo,  mostrando la lista de contenido relacionado en el panel de revisión de familia de documentos, haga clic en Etiquetar documentos bajo el panel de revisión de familia de documentos.</span><span class="sxs-lookup"><span data-stu-id="60d89-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="60d89-147">El panel de etiquetado se muestra como una ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="60d89-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="60d89-148">Elija una o más etiquetas para aplicar el documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="60d89-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="60d89-149">Para etiquetar todos los documentos, seleccione todos los documentos en el **panel** Familia de documentos, haga clic en Etiquetar documentos y, a continuación, elija las etiquetas que se aplicarán a toda la familia de documentos.</span><span class="sxs-lookup"><span data-stu-id="60d89-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Captura de pantalla de una publicación de redes sociales Generada automáticamente](../media/Relatedtag.png)
