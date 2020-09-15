---
title: Consultar los datos de un conjunto de revisión
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
description: Obtenga información sobre cómo crear y ejecutar una consulta en un conjunto de revisiones para organizar los datos para una revisión más eficiente en un caso de exhibición avanzada de documentos electrónicos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 508e8e9fdb4a558a998a33aa561dc3755edcc40d
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816723"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="f9bbf-103">Consultar los datos de un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="f9bbf-103">Query the data in a review set</span></span>

<span data-ttu-id="f9bbf-104">En la mayoría de los casos, será útil poder profundizar más en los datos de un conjunto de revisión y organizar los datos para facilitar una revisión más eficiente.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="f9bbf-105">Usar consultas en un conjunto de revisiones le ayudará a centrarse en un subconjunto de documentos que cumplan los criterios de la revisión.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="f9bbf-106">Crear y ejecutar una consulta en un conjunto de revisiones</span><span class="sxs-lookup"><span data-stu-id="f9bbf-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="f9bbf-107">Para crear y ejecutar una consulta en los documentos de un conjunto de revisión, seleccione **nueva consulta** en el conjunto de revisiones.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="f9bbf-108">Después de asignar un nombre a la consulta y definir las condiciones, seleccione **Guardar** para guardar y ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="f9bbf-109">Para ejecutar una consulta que se ha guardado previamente, seleccione una consulta guardada.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-109">To run a query that has been previously saved, select a saved query.</span></span>

![Revisar establecer consultas](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="f9bbf-111">Creación de una consulta de conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="f9bbf-111">Building a review set query</span></span>

<span data-ttu-id="f9bbf-112">Puede crear una consulta mediante una combinación de tarjetas de condición y lenguaje de consulta en la tarjeta de condición de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-112">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="f9bbf-113">También puede agrupar las tarjetas de condición como un bloque (denominado *grupo de condición*) para crear una consulta más compleja.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-113">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="f9bbf-114">Para obtener una lista y una descripción de las propiedades de metadatos que puede buscar, consulte [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="f9bbf-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="f9bbf-115">Tarjetas de condición</span><span class="sxs-lookup"><span data-stu-id="f9bbf-115">Condition cards</span></span>

<span data-ttu-id="f9bbf-116">Cada campo de búsqueda de un conjunto de revisión tiene una tarjeta de condición correspondiente que puede usar para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-116">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="f9bbf-117">Hay varios tipos de tarjetas de condición:</span><span class="sxs-lookup"><span data-stu-id="f9bbf-117">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="f9bbf-118">FREETEXT: se usa una tarjeta de condición FREETEXT para los campos de texto, como el asunto.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-118">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="f9bbf-119">Puede enumerar varios términos de búsqueda separándolos con una coma.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="f9bbf-120">Fecha: se usa una tarjeta de condición de fecha para los campos de fecha como última fecha de modificación.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-120">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="f9bbf-121">Opciones de búsqueda: una tarjeta de condición de opciones de búsqueda proporcionará una lista de valores posibles para el campo en particular en su conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-121">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="f9bbf-122">Se usa para los campos, como Sender, donde hay un número finito de valores posibles en su conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="f9bbf-123">Palabra clave: una tarjeta de condición de palabra clave es una instancia específica de la tarjeta de condición FREETEXT que puede usar para buscar términos o usar el lenguaje de consulta de tipo KQL en.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-123">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="f9bbf-124">Consulte a continuación para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="f9bbf-125">Lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="f9bbf-125">Query language</span></span>

<span data-ttu-id="f9bbf-126">Además de las tarjetas de condición, puede usar un lenguaje de consulta similar a tipo KQL en la tarjeta Keywords para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-126">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="f9bbf-127">El lenguaje de consulta para las consultas set de revisión admite operadores booleanos estándar, como **and**, **or**, **Not**y **Near**.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="f9bbf-128">También admite caracteres comodín de un solo carácter (?) y un comodín de varios caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="f9bbf-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="f9bbf-129">Filtros</span><span class="sxs-lookup"><span data-stu-id="f9bbf-129">Filters</span></span>

<span data-ttu-id="f9bbf-130">Además de las consultas que puede guardar, puede usar la revisión Set filters para aplicar rápidamente condiciones adicionales a una consulta de conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="f9bbf-131">El uso de filtros ayuda a restringir aún más los resultados mostrados por una consulta de conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Revisar definir filtros](../media/AeDReviewSetFilters.png)

<span data-ttu-id="f9bbf-133">Los filtros difieren de las consultas de dos maneras significativas:</span><span class="sxs-lookup"><span data-stu-id="f9bbf-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="f9bbf-134">Los filtros son transitorios.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-134">Filters are transient.</span></span> <span data-ttu-id="f9bbf-135">No se conservan más allá de la sesión existente.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="f9bbf-136">Es decir, no se puede guardar un filtro.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="f9bbf-137">Las consultas se guardan en el conjunto de revisión y acceden a ellas cada vez que se abre el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="f9bbf-138">Los filtros siempre son aditivos.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-138">Filters are always additive.</span></span> <span data-ttu-id="f9bbf-139">Se aplican filtros además de la consulta del conjunto de revisiones actual.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="f9bbf-140">Si se aplica una consulta diferente, se reemplazarán los resultados devueltos por la consulta actual.</span><span class="sxs-lookup"><span data-stu-id="f9bbf-140">Applying a different query will replace the results returned by the current query.</span></span>
