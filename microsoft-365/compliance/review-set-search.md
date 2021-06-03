---
title: Consultar el contenido de un conjunto de revisión
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
description: Obtenga información sobre cómo crear y ejecutar una consulta en un conjunto de revisión para organizar el contenido para una revisión más eficaz en un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736458"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="92fea-103">Consultar y filtrar contenido en un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="92fea-103">Query and filter content in a review set</span></span>

<span data-ttu-id="92fea-104">En la mayoría de los casos, será útil profundizar en el contenido de un conjunto de revisión y organizarlo para facilitar una revisión más eficaz.</span><span class="sxs-lookup"><span data-stu-id="92fea-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="92fea-105">El uso de filtros y consultas en un conjunto de revisión le ayuda a centrarse en un subconjunto de documentos que cumplan los criterios de la revisión.</span><span class="sxs-lookup"><span data-stu-id="92fea-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="92fea-106">Filtros predeterminados</span><span class="sxs-lookup"><span data-stu-id="92fea-106">Default filters</span></span>

<span data-ttu-id="92fea-107">En un conjunto de revisión, hay cinco filtros predeterminados que se cargan previamente en el conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="92fea-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="92fea-108">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="92fea-108">Keywords</span></span>
- <span data-ttu-id="92fea-109">Fecha</span><span class="sxs-lookup"><span data-stu-id="92fea-109">Date</span></span>
- <span data-ttu-id="92fea-110">Sender/Author</span><span class="sxs-lookup"><span data-stu-id="92fea-110">Sender/Author</span></span>
- <span data-ttu-id="92fea-111">Asunto/Título</span><span class="sxs-lookup"><span data-stu-id="92fea-111">Subject/Title</span></span>
- <span data-ttu-id="92fea-112">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="92fea-112">Tags</span></span>

![Tipos de filtro predeterminados](../media/DefaultFilterTypes.png)

<span data-ttu-id="92fea-114">Haga clic en cada filtro para expandirlo y asignar un valor.</span><span class="sxs-lookup"><span data-stu-id="92fea-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="92fea-115">Haga clic fuera del filtro para aplicar automáticamente el filtro al conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="92fea-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="92fea-116">La siguiente captura de pantalla muestra el filtro Fecha configurado para mostrar documentos dentro de un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="92fea-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![Filtro predeterminado expandido](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="92fea-118">Agregar o quitar filtros</span><span class="sxs-lookup"><span data-stu-id="92fea-118">Add or remove filters</span></span>

<span data-ttu-id="92fea-119">Para agregar o quitar los filtros que se  muestran para el conjunto de revisión, seleccione Filtros para abrir el panel de filtro, que se muestra en una página desplegable.</span><span class="sxs-lookup"><span data-stu-id="92fea-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![Panel de filtro](../media/FilterPanel.png)

<span data-ttu-id="92fea-121">Los filtros disponibles se organizan en cuatro secciones:</span><span class="sxs-lookup"><span data-stu-id="92fea-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="92fea-122">**Búsqueda:** filtros que proporcionan distintas capacidades de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="92fea-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="92fea-123">**Analytics & codificación predictiva:** filtra las propiedades generadas y agregadas a los documentos al ejecutar el trabajo analítico de correo electrónico de **&** o al usar modelos de codificación predictiva.</span><span class="sxs-lookup"><span data-stu-id="92fea-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="92fea-124">**Identificadores:** filtra todas las propiedades de identificador de los documentos.</span><span class="sxs-lookup"><span data-stu-id="92fea-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="92fea-125">**Propiedades del elemento:** filtra las propiedades del documento.</span><span class="sxs-lookup"><span data-stu-id="92fea-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="92fea-126">Expanda cada sección y seleccione o anule la selección de filtros para agregarlos o quitarlos en el conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="92fea-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="92fea-127">Al agregar un filtro, se muestra en el conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="92fea-127">When you add a filter, it's displayed in the filter set.</span></span> 

![Lista de secciones y propiedades de filtro en el panel de filtros](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="92fea-129">Al expandir una sección en el panel de filtros, observará que los tipos de filtro predeterminados están seleccionados.</span><span class="sxs-lookup"><span data-stu-id="92fea-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="92fea-130">Puede mantener estos seleccionados o anular la selección y quitarlos del conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="92fea-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="92fea-131">Tipos de filtro</span><span class="sxs-lookup"><span data-stu-id="92fea-131">Filter types</span></span>

<span data-ttu-id="92fea-132">Cada campo que se puede buscar en un conjunto de revisión tiene un filtro correspondiente que puede usar para los elementos de filtro en función de un campo específico.</span><span class="sxs-lookup"><span data-stu-id="92fea-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="92fea-133">Hay varios tipos de filtros:</span><span class="sxs-lookup"><span data-stu-id="92fea-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="92fea-134">**Freetext:** se aplica un filtro de texto libre a campos de texto como "Subject".</span><span class="sxs-lookup"><span data-stu-id="92fea-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="92fea-135">Puede enumerar varios términos de búsqueda separlos con una coma.</span><span class="sxs-lookup"><span data-stu-id="92fea-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="92fea-136">**Fecha:** se usa un filtro de fecha para campos de fecha como "Fecha de última modificación".</span><span class="sxs-lookup"><span data-stu-id="92fea-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="92fea-137">**Opciones de** búsqueda: un filtro de opciones de búsqueda proporciona una lista de valores posibles (cada valor se muestra con una casilla que puede seleccionar) para campos concretos de la revisión.</span><span class="sxs-lookup"><span data-stu-id="92fea-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="92fea-138">Este filtro se usa para campos, como "Sender", donde hay un número finito de valores posibles en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="92fea-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="92fea-139">**Palabra** clave: una condición de palabra clave es una instancia específica de condición de texto libre que puede usar para buscar términos.</span><span class="sxs-lookup"><span data-stu-id="92fea-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="92fea-140">También puede usar el lenguaje de consulta de tipo KQL en este tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="92fea-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="92fea-141">Para obtener más información, vea las secciones Lenguaje de consulta y Generador de consultas avanzado en este tema.</span><span class="sxs-lookup"><span data-stu-id="92fea-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="92fea-142">Incluir y excluir relaciones de filtro</span><span class="sxs-lookup"><span data-stu-id="92fea-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="92fea-143">Tiene la opción de cambiar la relación de incluir y excluir para un filtro determinado.</span><span class="sxs-lookup"><span data-stu-id="92fea-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="92fea-144">Por ejemplo, en el filtro Etiqueta, puede excluir elementos **etiquetados** con una etiqueta determinada seleccionando Igual a ninguno en el filtro desplegable.</span><span class="sxs-lookup"><span data-stu-id="92fea-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![Excluir filtro de etiquetas](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="92fea-146">Guardar filtros como consultas</span><span class="sxs-lookup"><span data-stu-id="92fea-146">Save filters as queries</span></span>

<span data-ttu-id="92fea-147">Una vez que esté satisfecho con los filtros, puede guardar la combinación de filtros como una consulta de filtro.</span><span class="sxs-lookup"><span data-stu-id="92fea-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="92fea-148">Esto le permite aplicar el filtro en las sesiones de revisión futuras.</span><span class="sxs-lookup"><span data-stu-id="92fea-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="92fea-149">Para guardar un filtro, seleccione **Guardar la consulta** y así mismo.</span><span class="sxs-lookup"><span data-stu-id="92fea-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="92fea-150">Usted u otros revisores pueden ejecutar consultas de filtro guardadas previamente seleccionando el menú desplegable Consultas **de** filtro guardadas y seleccionando una consulta de filtro para aplicar a los documentos establecidos de revisión.</span><span class="sxs-lookup"><span data-stu-id="92fea-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![Guardar una consulta de filtro](../media/SaveFilterQuery.png)

<span data-ttu-id="92fea-152">Para eliminar una consulta de filtro, abra el panel de filtro y seleccione el icono de papelera junto a la consulta.</span><span class="sxs-lookup"><span data-stu-id="92fea-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![Eliminar una consulta de filtro](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="92fea-154">Lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="92fea-154">Query language</span></span>

<span data-ttu-id="92fea-155">Además de usar filtros, también puede usar un lenguaje de consulta de tipo KQL en el filtro Palabras clave para crear la consulta de búsqueda del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="92fea-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="92fea-156">El lenguaje de consulta para consultas de conjunto de revisión admite operadores booleanos estándar, como **AND**, **OR**, **NOT** y **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="92fea-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="92fea-157">También admite un comodín de un solo carácter (?) y un comodín de varios caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="92fea-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="92fea-158">Generador de consultas avanzada</span><span class="sxs-lookup"><span data-stu-id="92fea-158">Advanced query builder</span></span>

<span data-ttu-id="92fea-159">También puede crear consultas más avanzadas para buscar documentos en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="92fea-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="92fea-160">Abra el panel de filtro, seleccione **Filtros** y expanda la **sección** Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="92fea-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![Agregar un filtro KQL](../media/AddKQLFilter.png)

2. <span data-ttu-id="92fea-162">Seleccione el filtro **KQL y** haga clic **en Abrir generador de consultas**.</span><span class="sxs-lookup"><span data-stu-id="92fea-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="92fea-163">En este panel, puede crear consultas KQL complejas mediante el generador de consultas.</span><span class="sxs-lookup"><span data-stu-id="92fea-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="92fea-164">Puede agregar condiciones o agregar grupos de condiciones que estén hechos de varias condiciones que estén conectadas lógicamente mediante relaciones **AND** **o OR.**</span><span class="sxs-lookup"><span data-stu-id="92fea-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![Usar el generador de consultas para configurar consultas de filtro complejas](../media/ComplexQuery.png)
