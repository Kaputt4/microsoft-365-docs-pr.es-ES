---
title: Buscar estadísticas en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
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
description: Para validar los resultados de la búsqueda, vea las estadísticas que se generan después de ejecutar una búsqueda de colección en la exhibición avanzada de documentos electrónicos.
ms.openlocfilehash: ef5653a76d94272ba5f608149648f1421198929a
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286086"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="1ed34-103">Estadísticas de búsqueda en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="1ed34-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="1ed34-104">Una forma de validar los resultados de la búsqueda es ver las estadísticas de los resultados para asegurarse de que se ajustan a sus expectativas.</span><span class="sxs-lookup"><span data-stu-id="1ed34-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="1ed34-105">Una vez finalizada la búsqueda, se muestran las estadísticas de alto nivel en el control flotante de detalles de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="1ed34-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="1ed34-106">Número y volumen de los elementos recuperados por la búsqueda</span><span class="sxs-lookup"><span data-stu-id="1ed34-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="1ed34-107">Número y volumen de los elementos sin indexar o parcialmente indizados que se encontraron en las ubicaciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1ed34-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="1ed34-108">Número de buzones y ubicaciones que se han buscado.</span><span class="sxs-lookup"><span data-stu-id="1ed34-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="1ed34-109">Para ver estadísticas más detalladas, haga clic en "estadísticas" en el control flotante de detalles de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1ed34-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="1ed34-110">Vista de Resumen</span><span class="sxs-lookup"><span data-stu-id="1ed34-110">Summary view</span></span>

<span data-ttu-id="1ed34-111">En la vista de Resumen, puede ver los resultados de la búsqueda desglosados por tipo de ubicación (por ejemplo, Exchange).</span><span class="sxs-lookup"><span data-stu-id="1ed34-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="1ed34-112">Para cada tipo de ubicación, puede ver:</span><span class="sxs-lookup"><span data-stu-id="1ed34-112">For each location type, you can see:</span></span>

- <span data-ttu-id="1ed34-113">Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1ed34-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="1ed34-114">Número de elementos de estas ubicaciones que coinciden con las condiciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1ed34-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="1ed34-115">Volumen total de elementos que coinciden con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1ed34-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="1ed34-116">Vista de ubicaciones superiores</span><span class="sxs-lookup"><span data-stu-id="1ed34-116">Top locations view</span></span>

<span data-ttu-id="1ed34-117">En la vista de ubicaciones superiores, verá las ubicaciones individuales con más coincidencias.</span><span class="sxs-lookup"><span data-stu-id="1ed34-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="1ed34-118">Para cada ubicación, verá:</span><span class="sxs-lookup"><span data-stu-id="1ed34-118">For each location, you will see:</span></span>

- <span data-ttu-id="1ed34-119">Nombre de la ubicación (por ejemplo, dirección URL de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="1ed34-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="1ed34-120">Tipo de ubicación</span><span class="sxs-lookup"><span data-stu-id="1ed34-120">Location type</span></span>

- <span data-ttu-id="1ed34-121">Número de elementos que coinciden con las condiciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1ed34-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="1ed34-122">Volumen total de elementos que coinciden con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1ed34-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="1ed34-123">Vista de consultas</span><span class="sxs-lookup"><span data-stu-id="1ed34-123">Queries view</span></span>

<span data-ttu-id="1ed34-124">Si ha usado (c:s) palabra clave o filas de palabra clave en la consulta, puede ver el desglose de la consulta en la vista consultas por tipo de ubicación.</span><span class="sxs-lookup"><span data-stu-id="1ed34-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="1ed34-125">Para cada tipo de ubicación, verá:</span><span class="sxs-lookup"><span data-stu-id="1ed34-125">For each location type, you will see:</span></span>

- <span data-ttu-id="1ed34-126">Parte: esta columna tendrá la palabra "principal" o "palabra clave".</span><span class="sxs-lookup"><span data-stu-id="1ed34-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="1ed34-127">"Principal" significa que la fila presenta estadísticas sobre toda la consulta, mientras que "palabra clave" se refiere a uno de los componentes de consulta.</span><span class="sxs-lookup"><span data-stu-id="1ed34-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="1ed34-128">Consulta: el componente de consulta real al que hace referencia la fila.</span><span class="sxs-lookup"><span data-stu-id="1ed34-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="1ed34-129">Si la parte es "principal", será toda la consulta; Si la parte es "keyword", verá uno de los componentes de consulta aquí.</span><span class="sxs-lookup"><span data-stu-id="1ed34-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="1ed34-130">Cuando busca en todo el contenido de los buzones (sin especificar ninguna palabra clave), la consulta real es (Size >= 0) para que se devuelvan todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="1ed34-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="1ed34-131">Al buscar sitios de SharePoint Online y OneDrive para la empresa, se agregan los dos componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ed34-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="1ed34-132">NO IsExternalContent: 1-excluye el contenido de una organización de SharePoint local</span><span class="sxs-lookup"><span data-stu-id="1ed34-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="1ed34-133">NO isOneNotePage: 1: excluye todos los archivos de OneNote porque serían duplicados de cualquier documento que coincida con la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1ed34-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="1ed34-134">Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1ed34-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="1ed34-135">Número de elementos de estas ubicaciones que coinciden con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1ed34-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="1ed34-136">Volumen total de elementos que coinciden con las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1ed34-136">Total volume of items that matched the search conditions.</span></span>
