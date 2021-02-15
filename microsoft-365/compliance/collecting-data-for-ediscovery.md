---
title: Recopilar datos para un caso en eDiscovery avanzado
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
description: Obtenga información sobre cómo identificar un conjunto de documentos para su revisión en una investigación mediante la herramienta de búsqueda en eDiscovery avanzado.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751277"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="d0243-103">Recopilar datos para un caso en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="d0243-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="d0243-104">Una vez que haya identificado administradores y orígenes de datos que son de interés para su caso, es el momento de identificar el conjunto de documentos en los que profundizar.</span><span class="sxs-lookup"><span data-stu-id="d0243-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="d0243-105">Puede usar la herramienta de búsqueda en eDiscovery avanzado para identificar documentos relevantes de ubicaciones de custodia y no custodia en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0243-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="d0243-106">Después de ejecutar una búsqueda, puede ver estadísticas de los elementos recuperados, como las ubicaciones con más elementos que coincidieron con la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d0243-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="d0243-107">También puede obtener una vista previa de un subconjunto de los resultados.</span><span class="sxs-lookup"><span data-stu-id="d0243-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="d0243-108">Cuando haya identificado el conjunto de documentos que desea examinar, puede agregar los resultados de la búsqueda a un conjunto de revisión para recopilar y procesar.</span><span class="sxs-lookup"><span data-stu-id="d0243-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="d0243-109">Crear una búsqueda</span><span class="sxs-lookup"><span data-stu-id="d0243-109">Create a search</span></span>

<span data-ttu-id="d0243-110">Si selecciona **Nueva búsqueda en** la pestaña **Búsquedas,** se iniciará un asistente que le guiará a través de la creación de una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d0243-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="d0243-111">Para obtener información detallada sobre cómo crear una búsqueda, vea [Crear una búsqueda para recopilar datos.](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="d0243-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="d0243-112">Después de crear una búsqueda, se muestra una página desplegable con detalles.</span><span class="sxs-lookup"><span data-stu-id="d0243-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="d0243-113">Los **botones Estadísticas** **y Vista** previa no están disponibles inicialmente porque la búsqueda aún no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="d0243-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="d0243-114">Puede realizar un seguimiento del progreso de la búsqueda en la **pestaña** Búsquedas.</span><span class="sxs-lookup"><span data-stu-id="d0243-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="d0243-115">Ver resultados de búsqueda y estadísticas</span><span class="sxs-lookup"><span data-stu-id="d0243-115">View search results and statistics</span></span>

<span data-ttu-id="d0243-116">Hay dos componentes de una búsqueda de contenido: estadísticas (estimaciones) y vista previa.</span><span class="sxs-lookup"><span data-stu-id="d0243-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="d0243-117">A medida que se complete cada uno de estos componentes,  verá que el estado que se muestra en las columnas correspondientes en la pestaña Búsquedas cambia de **Enviado** a En curso **a** **Completado.**</span><span class="sxs-lookup"><span data-stu-id="d0243-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="d0243-118">Una vez completada la estimación de búsqueda, seleccione la búsqueda para mostrar la página desplegable, que mostrará algunas estadísticas de alto nivel sobre los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d0243-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="d0243-119">En este punto, el **botón Estadísticas** estará activo.</span><span class="sxs-lookup"><span data-stu-id="d0243-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="d0243-120">Puede seleccionarla para ver estadísticas de búsqueda, como:</span><span class="sxs-lookup"><span data-stu-id="d0243-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="d0243-121">Resumen</span><span class="sxs-lookup"><span data-stu-id="d0243-121">Summary</span></span>
- <span data-ttu-id="d0243-122">Ubicaciones principales</span><span class="sxs-lookup"><span data-stu-id="d0243-122">Top locations</span></span>
- <span data-ttu-id="d0243-123">Consultas</span><span class="sxs-lookup"><span data-stu-id="d0243-123">Queries</span></span>

<span data-ttu-id="d0243-124">Para obtener más información acerca de las estadísticas de búsqueda, vea [Estadísticas de búsqueda.](search-statistics-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d0243-124">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

<span data-ttu-id="d0243-125">Una vez completada la vista previa, **el** botón Vista previa estará activo.</span><span class="sxs-lookup"><span data-stu-id="d0243-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="d0243-126">Selecciónelo para obtener una vista previa de un subconjunto de muestra de los resultados.</span><span class="sxs-lookup"><span data-stu-id="d0243-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="d0243-127">Agregar los resultados de búsqueda a un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="d0243-127">Add search results to a review set</span></span>

<span data-ttu-id="d0243-128">Cuando esté listo para recopilar y procesar todos los resultados de una búsqueda, puede hacerlo agregándole a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="d0243-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="d0243-129">Para obtener más información, [vea Agregar datos a un conjunto de revisión.](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="d0243-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="d0243-130">Agregar datos que no son de Microsoft 365 a un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="d0243-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="d0243-131">Como parte del proceso de recopilación de un caso, también puede agregar datos que no son de Office 365 a un conjunto de revisión y revisar y analizar junto con los datos de Office 365 que recopiló mediante la herramienta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d0243-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="d0243-132">Cuando agrega un usuario que no es de Office 365, tiene que asociarlo con un administrador específico en el caso.</span><span class="sxs-lookup"><span data-stu-id="d0243-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="d0243-133">Para obtener más información, vea Cargar datos que no son [de Microsoft 365 en un conjunto de revisión.](load-non-Office-365-data-into-a-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="d0243-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
