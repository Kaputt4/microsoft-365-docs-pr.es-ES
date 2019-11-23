---
title: Consultar los datos de un conjunto de revisión
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
description: ''
ms.openlocfilehash: b37ff9bf96ff641750acc9ac47ef9c27b566651c
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202351"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="8a1d2-102">Consultar los datos de un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="8a1d2-102">Query the data in a review set</span></span>

<span data-ttu-id="8a1d2-103">En la mayoría de los casos, será útil poder profundizar más en los datos de un conjunto de revisión y organizar los datos para facilitar una revisión más eficiente.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-103">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="8a1d2-104">Usar consultas en un conjunto de revisiones le ayudará a centrarse en un subconjunto de documentos que cumplan los criterios de la revisión.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-104">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="8a1d2-105">Crear y ejecutar una consulta en un conjunto de revisiones</span><span class="sxs-lookup"><span data-stu-id="8a1d2-105">Creating and running a query in a review set</span></span>

<span data-ttu-id="8a1d2-106">Para crear y ejecutar una consulta en los documentos de un conjunto de revisiones, haga clic en **nueva consulta** en el conjunto de revisiones.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-106">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="8a1d2-107">Después de asignar un nombre a la consulta y definir las condiciones, haga clic en **Guardar** para guardar y ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-107">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="8a1d2-108">Para ejecutar una consulta que se ha guardado previamente, haga clic en una consulta guardada.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-108">To run a query that has been previously saved, click a saved query.</span></span> 

![Revisar establecer consultas](media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="8a1d2-110">Creación de una consulta de conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="8a1d2-110">Building a review set query</span></span>

<span data-ttu-id="8a1d2-111">Puede crear una consulta mediante una combinación de tarjetas de condición y lenguaje de consulta en la tarjeta de condición de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-111">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="8a1d2-112">También puede agrupar las tarjetas de condición como un bloque (denominado *grupo de condición*) para crear una consulta más compleja.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-112">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="8a1d2-113">Para obtener una lista y una descripción de las propiedades de metadatos que puede buscar, consulte [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="8a1d2-113">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="8a1d2-114">Tarjetas de condición</span><span class="sxs-lookup"><span data-stu-id="8a1d2-114">Condition cards</span></span>

<span data-ttu-id="8a1d2-115">Cada campo de búsqueda de un conjunto de revisión tiene una tarjeta de condición correspondiente que puede usar para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-115">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="8a1d2-116">Hay varios tipos de tarjetas de condición:</span><span class="sxs-lookup"><span data-stu-id="8a1d2-116">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="8a1d2-117">FREETEXT: se usa una tarjeta de condición FREETEXT para los campos de texto, como el asunto.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-117">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="8a1d2-118">Puede enumerar varios términos de búsqueda separándolos con una coma.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-118">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="8a1d2-119">Fecha: se usa una tarjeta de condición de fecha para los campos de fecha como última fecha de modificación.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-119">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="8a1d2-120">Opciones de búsqueda: una tarjeta de condición de opciones de búsqueda proporcionará una lista de valores posibles para el campo en particular en su conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-120">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="8a1d2-121">Se usa para los campos, como Sender, donde hay un número finito de valores posibles en su conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-121">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="8a1d2-122">Palabra clave: una tarjeta de condición de palabra clave es una instancia específica de la tarjeta de condición FREETEXT que puede usar para buscar términos o usar el lenguaje de consulta de tipo KQL en.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-122">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="8a1d2-123">Consulte a continuación para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-123">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="8a1d2-124">Lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="8a1d2-124">Query language</span></span>

<span data-ttu-id="8a1d2-125">Además de las tarjetas de condición, puede usar un lenguaje de consulta similar a tipo KQL en la tarjeta Keywords para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-125">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="8a1d2-126">El lenguaje de consulta para las consultas set de revisión admite operadores booleanos estándar, como **and**, **or**, **Not**y **Near**.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-126">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="8a1d2-127">También admite caracteres comodín de un solo carácter (?) y un comodín de varios caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="8a1d2-127">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="8a1d2-128">Uso de filtros</span><span class="sxs-lookup"><span data-stu-id="8a1d2-128">Using filters</span></span>

<span data-ttu-id="8a1d2-129">Además de las consultas que puede guardar, puede usar la revisión Set filters para aplicar rápidamente condiciones adicionales a una consulta de conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-129">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="8a1d2-130">Esto le ayuda a restringir aún más los resultados mostrados por una consulta de conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-130">This helps you further refine the results displayed by a review set query.</span></span>

![Revisar definir filtros](media/AeDReviewSetFilters.png)

<span data-ttu-id="8a1d2-132">Los filtros difieren de las consultas de dos maneras significativas:</span><span class="sxs-lookup"><span data-stu-id="8a1d2-132">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="8a1d2-133">Los filtros son transitorios.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-133">Filters are transient.</span></span> <span data-ttu-id="8a1d2-134">No se conservan más allá de la sesión existente.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-134">They don't persist beyond the existing session.</span></span> <span data-ttu-id="8a1d2-135">Es decir, no se puede guardar un filtro.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-135">In other words, you can't save a filter.</span></span> <span data-ttu-id="8a1d2-136">Las consultas se guardan en el conjunto de revisión y acceden a ellas cada vez que se abre el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-136">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="8a1d2-137">Los filtros siempre son aditivos.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-137">Filters are always additive.</span></span> <span data-ttu-id="8a1d2-138">Se aplican filtros además de la consulta del conjunto de revisiones actual.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-138">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="8a1d2-139">Si se aplica una consulta diferente, se reemplazarán los resultados devueltos por la consulta actual.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-139">Applying a different query will replace the results returned by the current query.</span></span>
