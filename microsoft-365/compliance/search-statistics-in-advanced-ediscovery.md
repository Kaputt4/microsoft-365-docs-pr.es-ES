---
title: Estadísticas de búsqueda en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Valide los resultados de la búsqueda consultando las estadísticas que se generan después de ejecutar una búsqueda de colección en eDiscovery avanzado.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750781"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="4bfa9-103">Estadísticas de búsqueda en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="4bfa9-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="4bfa9-104">Una forma de validar los resultados de la búsqueda es ver las estadísticas de los resultados para asegurarse de que se alineen con sus expectativas.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="4bfa9-105">Cuando se completa una búsqueda, se muestran estadísticas de alto nivel en el control desplegable de detalles de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="4bfa9-106">Número y volumen de elementos recuperados por la búsqueda</span><span class="sxs-lookup"><span data-stu-id="4bfa9-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="4bfa9-107">Número y volumen de elementos parcialmente indizados o sin indexar que se encontraron en las ubicaciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4bfa9-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="4bfa9-108">Número de buzones y ubicaciones en los que se ha buscado.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="4bfa9-109">Para ver estadísticas más detalladas, haga clic en "Estadísticas" en el menú desplegable de detalles de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="4bfa9-110">Vista de resumen</span><span class="sxs-lookup"><span data-stu-id="4bfa9-110">Summary view</span></span>

<span data-ttu-id="4bfa9-111">En la vista Resumen, puede ver los resultados de la búsqueda desglosados por tipo de ubicación (por ejemplo, Exchange).</span><span class="sxs-lookup"><span data-stu-id="4bfa9-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="4bfa9-112">Para cada tipo de ubicación, puede ver:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-112">For each location type, you can see:</span></span>

- <span data-ttu-id="4bfa9-113">Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4bfa9-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="4bfa9-114">Número de elementos de estas ubicaciones que coincidieron con las condiciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4bfa9-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="4bfa9-115">Volumen total de elementos que coincidieron con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="4bfa9-116">Vista de ubicaciones superiores</span><span class="sxs-lookup"><span data-stu-id="4bfa9-116">Top locations view</span></span>

<span data-ttu-id="4bfa9-117">En la vista De ubicaciones principales, verá las ubicaciones individuales con más coincidencias.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="4bfa9-118">Para cada ubicación, verá:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-118">For each location, you will see:</span></span>

- <span data-ttu-id="4bfa9-119">Nombre de ubicación (por ejemplo, dirección URL de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="4bfa9-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="4bfa9-120">Tipo de ubicación</span><span class="sxs-lookup"><span data-stu-id="4bfa9-120">Location type</span></span>

- <span data-ttu-id="4bfa9-121">Número de elementos que coincidieron con las condiciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4bfa9-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="4bfa9-122">Volumen total de elementos que coincidieron con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="4bfa9-123">Vista Consultas</span><span class="sxs-lookup"><span data-stu-id="4bfa9-123">Queries view</span></span>

<span data-ttu-id="4bfa9-124">Si ha usado (c:s) filas de palabras clave o palabras clave en la consulta, puede ver el desglose de la consulta en la vista Consultas por tipo de ubicación.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="4bfa9-125">Para cada tipo de ubicación, verá:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-125">For each location type, you will see:</span></span>

- <span data-ttu-id="4bfa9-126">Parte: esta columna tendrá la palabra "Principal" o "Palabra clave".</span><span class="sxs-lookup"><span data-stu-id="4bfa9-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="4bfa9-127">"Principal" significa que la fila presenta estadísticas en toda la consulta, mientras que "Palabra clave" significa uno de los componentes de consulta.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="4bfa9-128">Consulta: componente de consulta real al que hace referencia la fila.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="4bfa9-129">Si Part es "Primary", esta será la consulta completa; Si Part era "Palabra clave", verá uno de los componentes de consulta aquí.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="4bfa9-130">Al buscar en todos los buzones de contenido (sin especificar palabras clave), la consulta real es (tamaño >= 0) para que se devuelvan todos los elementos</span><span class="sxs-lookup"><span data-stu-id="4bfa9-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="4bfa9-131">Al buscar sitios de SharePoint Online y OneDrive para la Empresa, se agregan los dos componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="4bfa9-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="4bfa9-132">NOT IsExternalContent:1: excluye cualquier contenido de una organización de SharePoint local</span><span class="sxs-lookup"><span data-stu-id="4bfa9-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="4bfa9-133">NOT isOneNotePage: 1: excluye todos los archivos de OneNote porque serían duplicados de cualquier documento que coincida con la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="4bfa9-134">Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="4bfa9-135">Número de elementos de estas ubicaciones que coincidieron con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="4bfa9-136">Volumen total de elementos que coincidieron con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4bfa9-136">Total volume of items that matched the search conditions.</span></span>
