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
description: Aprenda a crear y ejecutar una consulta en un conjunto de revisión para organizar los datos para una revisión más eficaz en un caso de eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816573"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="46326-103">Consultar los datos de un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="46326-103">Query the data in a review set</span></span>

<span data-ttu-id="46326-104">En la mayoría de los casos, será útil profundizar en los datos de un conjunto de revisión y organizar esos datos para facilitar una revisión más eficaz.</span><span class="sxs-lookup"><span data-stu-id="46326-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="46326-105">El uso de consultas en un conjunto de revisión le ayuda a centrarse en un subconjunto de documentos que cumplen los criterios de la revisión.</span><span class="sxs-lookup"><span data-stu-id="46326-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="46326-106">Creación y ejecución de una consulta en un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="46326-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="46326-107">Para crear y ejecutar una consulta en los documentos de un conjunto de revisión, seleccione **Nueva consulta** en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="46326-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="46326-108">Después de nombrar la consulta y definir las condiciones, seleccione **Guardar** para guardar y ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="46326-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="46326-109">Para ejecutar una consulta que se haya guardado anteriormente, seleccione una consulta guardada.</span><span class="sxs-lookup"><span data-stu-id="46326-109">To run a query that has been previously saved, select a saved query.</span></span>

![Consultas de conjunto de revisión](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="46326-111">Creación de una consulta de conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="46326-111">Building a review set query</span></span>

<span data-ttu-id="46326-112">Puede crear una consulta mediante una combinación de palabras clave, propiedades y condiciones en la condición De palabras clave.</span><span class="sxs-lookup"><span data-stu-id="46326-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="46326-113">También puede agrupar condiciones como un bloque (denominado grupo *de condiciones)* para crear una consulta más compleja.</span><span class="sxs-lookup"><span data-stu-id="46326-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="46326-114">Para obtener una lista y una descripción de las propiedades de metadatos que puede buscar, vea Campos de metadatos del documento [en eDiscovery avanzado.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="46326-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="46326-115">Condiciones</span><span class="sxs-lookup"><span data-stu-id="46326-115">Conditions</span></span>

<span data-ttu-id="46326-116">Cada campo que permite búsquedas en un conjunto de revisión tiene una condición correspondiente que puede usar para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="46326-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="46326-117">Existen varios tipos de condiciones:</span><span class="sxs-lookup"><span data-stu-id="46326-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="46326-118">Texto libre: se usa una condición de texto libre para campos de texto como el asunto.</span><span class="sxs-lookup"><span data-stu-id="46326-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="46326-119">Puede enumerar varios términos de búsqueda si los separa con una coma.</span><span class="sxs-lookup"><span data-stu-id="46326-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="46326-120">Fecha: se usa una condición de fecha para campos de fecha como la fecha de la última modificación.</span><span class="sxs-lookup"><span data-stu-id="46326-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="46326-121">Opciones de búsqueda: una condición de opciones de búsqueda proporcionará una lista de posibles valores para el campo concreto del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="46326-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="46326-122">Esto se usa para campos, como el remitente, donde hay un número finito de valores posibles en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="46326-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="46326-123">Palabra clave: una condición de palabra clave es una instancia específica de la condición de texto libre que puede usar para buscar términos o usar lenguaje de consulta de tipo KQL en.</span><span class="sxs-lookup"><span data-stu-id="46326-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="46326-124">Consulta a continuación para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="46326-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="46326-125">Lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="46326-125">Query language</span></span>

<span data-ttu-id="46326-126">Además de las condiciones, puede usar un lenguaje de consulta de tipo KQL en la condición de palabras clave para crear la consulta.</span><span class="sxs-lookup"><span data-stu-id="46326-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="46326-127">El lenguaje de consulta para consultas de conjunto de revisión admite operadores booleanos estándar, como **AND**, **OR**, **NOT** y **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="46326-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="46326-128">También admite un carácter comodín de un solo carácter (?) y un carácter comodín de varios caracteres (\*).</span><span class="sxs-lookup"><span data-stu-id="46326-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="46326-129">Filtros</span><span class="sxs-lookup"><span data-stu-id="46326-129">Filters</span></span>

<span data-ttu-id="46326-130">Además de las consultas que puede guardar, puede usar filtros de conjunto de revisión para aplicar rápidamente condiciones adicionales a una consulta de conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="46326-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="46326-131">El uso de filtros ayuda a refinar aún más los resultados mostrados por una consulta de conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="46326-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Revisar filtros de conjunto](../media/AeDReviewSetFilters.png)

<span data-ttu-id="46326-133">Los filtros difieren de las consultas de dos maneras significativas:</span><span class="sxs-lookup"><span data-stu-id="46326-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="46326-134">Los filtros son transitorios.</span><span class="sxs-lookup"><span data-stu-id="46326-134">Filters are transient.</span></span> <span data-ttu-id="46326-135">No se conservan más allá de la sesión existente.</span><span class="sxs-lookup"><span data-stu-id="46326-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="46326-136">En otras palabras, no puede guardar un filtro.</span><span class="sxs-lookup"><span data-stu-id="46326-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="46326-137">Las consultas se guardan en el conjunto de revisión y acceden a ellas siempre que abran el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="46326-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="46326-138">Los filtros siempre son aditivas.</span><span class="sxs-lookup"><span data-stu-id="46326-138">Filters are always additive.</span></span> <span data-ttu-id="46326-139">Los filtros se aplican además de la consulta del conjunto de revisión actual.</span><span class="sxs-lookup"><span data-stu-id="46326-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="46326-140">La aplicación de una consulta diferente reemplazará los resultados devueltos por la consulta actual.</span><span class="sxs-lookup"><span data-stu-id="46326-140">Applying a different query will replace the results returned by the current query.</span></span>
