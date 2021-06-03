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
description: Etiquetar documentos en un conjunto de revisión ayuda a quitar contenido innecesario e identificar contenido relevante en un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736308"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="fc93a-103">Etiquetar documentos en un conjunto de revisión en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fc93a-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="fc93a-104">Organizar el contenido en un conjunto de revisión es importante para completar varios flujos de trabajo en el proceso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="fc93a-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="fc93a-105">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="fc93a-105">This includes:</span></span>

- <span data-ttu-id="fc93a-106">Selección de contenido innecesario</span><span class="sxs-lookup"><span data-stu-id="fc93a-106">Culling unnecessary content</span></span>

- <span data-ttu-id="fc93a-107">Identificación de contenido relevante</span><span class="sxs-lookup"><span data-stu-id="fc93a-107">Identifying relevant content</span></span>

- <span data-ttu-id="fc93a-108">Identificar el contenido que debe revisar un experto o un abogado</span><span class="sxs-lookup"><span data-stu-id="fc93a-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="fc93a-109">Cuando expertos, abogados u otros usuarios revisan el contenido de un conjunto de opiniones, sus opiniones relacionadas con el contenido se pueden capturar mediante etiquetas.</span><span class="sxs-lookup"><span data-stu-id="fc93a-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="fc93a-110">Por ejemplo, si el objetivo es crear contenido innecesario, un usuario puede etiquetar documentos con una etiqueta como "no responde".</span><span class="sxs-lookup"><span data-stu-id="fc93a-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="fc93a-111">Después de revisar y etiquetar el contenido, se puede crear una búsqueda de conjunto de revisión para excluir cualquier contenido etiquetado como "no responde".</span><span class="sxs-lookup"><span data-stu-id="fc93a-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="fc93a-112">Este proceso elimina el contenido que no responde de los siguientes pasos del flujo de trabajo de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="fc93a-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="fc93a-113">El panel de etiquetado de un conjunto de revisión se puede personalizar para cada caso de modo que las etiquetas admitan el flujo de trabajo de revisión previsto para el caso.</span><span class="sxs-lookup"><span data-stu-id="fc93a-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="fc93a-114">El ámbito de las etiquetas es Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="fc93a-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="fc93a-115">Esto significa que un caso solo puede tener un conjunto de etiquetas que los revisores pueden usar para etiquetar documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fc93a-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="fc93a-116">No puede configurar un conjunto diferente de etiquetas para su uso en distintos conjuntos de revisión en el mismo caso.</span><span class="sxs-lookup"><span data-stu-id="fc93a-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="fc93a-117">Tipos de etiquetas</span><span class="sxs-lookup"><span data-stu-id="fc93a-117">Tag types</span></span>

<span data-ttu-id="fc93a-118">Advanced eDiscovery proporciona dos tipos de etiquetas:</span><span class="sxs-lookup"><span data-stu-id="fc93a-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="fc93a-119">**Etiquetas de opción** única: restringe a los revisores a seleccionar una sola etiqueta dentro de un grupo.</span><span class="sxs-lookup"><span data-stu-id="fc93a-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="fc93a-120">Estos tipos de etiquetas pueden ser útiles para garantizar que los revisores no seleccionen etiquetas en conflicto como "responsive" y "non-responsive".</span><span class="sxs-lookup"><span data-stu-id="fc93a-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="fc93a-121">Las etiquetas de opción única aparecen como botones de radio.</span><span class="sxs-lookup"><span data-stu-id="fc93a-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="fc93a-122">**Etiquetas de opción múltiple:** permitir que las revisiones seleccionen varias etiquetas dentro de un grupo.</span><span class="sxs-lookup"><span data-stu-id="fc93a-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="fc93a-123">Estos tipos de etiquetas aparecen como casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="fc93a-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="fc93a-124">Estructura de etiquetas</span><span class="sxs-lookup"><span data-stu-id="fc93a-124">Tag structure</span></span>

<span data-ttu-id="fc93a-125">Además de los tipos de etiquetas, la estructura de cómo se organizan las etiquetas en el panel de etiquetas se puede usar para hacer que los documentos de etiquetado sean más intuitivos.</span><span class="sxs-lookup"><span data-stu-id="fc93a-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="fc93a-126">Las etiquetas se agrupan por secciones.</span><span class="sxs-lookup"><span data-stu-id="fc93a-126">Tags are grouped by sections.</span></span> <span data-ttu-id="fc93a-127">La búsqueda de conjunto de revisión admite la capacidad de buscar por etiqueta y por sección de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="fc93a-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="fc93a-128">Esto significa que puede crear una búsqueda de conjunto de revisión para recuperar documentos etiquetados con cualquier etiqueta de una sección.</span><span class="sxs-lookup"><span data-stu-id="fc93a-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Secciones de etiquetas en el panel de etiquetas](../media/TagTypes.png)

<span data-ttu-id="fc93a-130">Puede organizar aún más las etiquetas anidandolas dentro de una sección.</span><span class="sxs-lookup"><span data-stu-id="fc93a-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="fc93a-131">Por ejemplo, si el objetivo es identificar y etiquetar contenido con privilegios, se puede usar el anidamiento para dejar claro que un revisor puede etiquetar un documento como "Privileged" y seleccionar el tipo de privilegio comprobando la etiqueta anidada adecuada.</span><span class="sxs-lookup"><span data-stu-id="fc93a-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Etiquetas anidadas dentro de una sección de etiquetas](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="fc93a-133">Crear etiquetas</span><span class="sxs-lookup"><span data-stu-id="fc93a-133">Create tags</span></span>

<span data-ttu-id="fc93a-134">Antes de aplicar etiquetas a documentos en el conjunto de revisión, debe crear una estructura de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="fc93a-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="fc93a-135">Abra un conjunto de revisión y navegue a la barra de comandos y seleccione **Etiquetar por consulta**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="fc93a-136">En el panel de etiquetado, seleccione **Administrar opciones de etiquetas**</span><span class="sxs-lookup"><span data-stu-id="fc93a-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="fc93a-137">Seleccione **Agregar sección de etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="fc93a-138">Escriba un título de grupo de etiquetas y una descripción opcional y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="fc93a-139">Seleccione el menú desplegable de triple punto junto al título del grupo de etiquetas y haga clic en **Agregar** casilla de verificación o **en El botón de opción Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="fc93a-140">Escriba un nombre y una descripción para la casilla o el botón de opción.</span><span class="sxs-lookup"><span data-stu-id="fc93a-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="fc93a-141">Repita este proceso para crear nuevas secciones de etiquetas, opciones de etiquetas y casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="fc93a-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![Configurar la estructura de etiquetas](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="fc93a-143">Aplicación de etiquetas</span><span class="sxs-lookup"><span data-stu-id="fc93a-143">Applying tags</span></span>

<span data-ttu-id="fc93a-144">Con la estructura de etiquetas en su lugar, los revisores pueden aplicar etiquetas a los documentos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fc93a-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="fc93a-145">Hay dos formas diferentes de aplicar etiquetas:</span><span class="sxs-lookup"><span data-stu-id="fc93a-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="fc93a-146">Archivos de etiqueta</span><span class="sxs-lookup"><span data-stu-id="fc93a-146">Tag files</span></span>

- <span data-ttu-id="fc93a-147">Etiqueta por consulta</span><span class="sxs-lookup"><span data-stu-id="fc93a-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="fc93a-148">Archivos de etiqueta</span><span class="sxs-lookup"><span data-stu-id="fc93a-148">Tag files</span></span>

<span data-ttu-id="fc93a-149">Tanto si selecciona un solo elemento como varios elementos de un conjunto de revisión, puede aplicar etiquetas a su selección haciendo clic en **Etiquetar archivos** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="fc93a-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="fc93a-150">En el panel de etiquetado, puede seleccionar una etiqueta y se aplica automáticamente a los documentos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fc93a-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![Etiquetar archivos seleccionados](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="fc93a-152">Las etiquetas solo se aplicarán a los elementos seleccionados de la lista de elementos.</span><span class="sxs-lookup"><span data-stu-id="fc93a-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="fc93a-153">Etiqueta por consulta</span><span class="sxs-lookup"><span data-stu-id="fc93a-153">Tag by query</span></span>

<span data-ttu-id="fc93a-154">El etiquetado por consulta le permite aplicar etiquetas a todos los elementos mostrados por una consulta de filtro que se aplica actualmente en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fc93a-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="fc93a-155">Anule la selección de todos los elementos del conjunto de revisión y vaya a la barra de comandos y **seleccione Etiquetar por consulta**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="fc93a-156">En el panel de etiquetado, seleccione la etiqueta que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="fc93a-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="fc93a-157">En el **desplegable Selección de** etiquetas, hay tres opciones que determinan a qué elementos aplicar la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="fc93a-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="fc93a-158">**Elementos que coinciden con la consulta aplicada:** aplica etiquetas a elementos específicos que coinciden con las condiciones de consulta de filtro.</span><span class="sxs-lookup"><span data-stu-id="fc93a-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="fc93a-159">**Incluir elementos de familia asociados:** aplica etiquetas a elementos específicos que coinciden con las condiciones de consulta de filtro y sus elementos de familia asociados.</span><span class="sxs-lookup"><span data-stu-id="fc93a-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="fc93a-160">*Los elementos de* familia son elementos que comparten el mismo valor de metadatos de FamilyId.</span><span class="sxs-lookup"><span data-stu-id="fc93a-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="fc93a-161">**Incluir elementos de conversación asociados:** aplica etiquetas a los elementos que coinciden con las condiciones de consulta de filtro y sus elementos de conversación asociados.</span><span class="sxs-lookup"><span data-stu-id="fc93a-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="fc93a-162">*Los elementos de* conversación son elementos que comparten los mismos valores de metadatos de ConversationId.</span><span class="sxs-lookup"><span data-stu-id="fc93a-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![Selección de etiquetas](../media/TagByQuery2.png)

4. <span data-ttu-id="fc93a-164">Haga **clic en Iniciar trabajo de etiquetado** para desencadenar el trabajo de etiquetado.</span><span class="sxs-lookup"><span data-stu-id="fc93a-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="fc93a-165">Filtro de etiquetas</span><span class="sxs-lookup"><span data-stu-id="fc93a-165">Tag filter</span></span>

<span data-ttu-id="fc93a-166">Use el filtro de etiquetas en el conjunto de revisión para buscar o excluir rápidamente elementos de los resultados de la consulta en función de cómo se etiqueta un elemento.</span><span class="sxs-lookup"><span data-stu-id="fc93a-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="fc93a-167">Seleccione **Filtros** para expandir el panel de filtro.</span><span class="sxs-lookup"><span data-stu-id="fc93a-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="fc93a-168">Seleccione y expanda **Propiedades de elemento**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="fc93a-169">Desplácese hacia abajo para buscar el filtro denominado **Tag**, seleccione la casilla y, a continuación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="fc93a-170">Para incluir o excluir elementos con una etiqueta específica de una consulta, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fc93a-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="fc93a-171">**Incluir elementos:** seleccione el valor de la etiqueta y **seleccione Igual a cualquiera en** el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="fc93a-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="fc93a-172">O bien:</span><span class="sxs-lookup"><span data-stu-id="fc93a-172">Or</span></span>

   - <span data-ttu-id="fc93a-173">**Excluir elementos:** seleccione el valor de la etiqueta y **seleccione No es** igual a ninguno en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="fc93a-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![Elementos de exclusión de filtro de etiquetas](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="fc93a-175">Asegúrese de actualizar la página para asegurarse de que el filtro de etiquetas muestra los cambios más recientes en la estructura de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="fc93a-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
