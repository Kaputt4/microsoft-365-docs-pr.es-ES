---
title: Recopilar datos para un caso en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: esclee
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
ms.openlocfilehash: 9d8a88ddfc6bcb30f8678f39ad2bc4fbaf717ecc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034354"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="39b07-103">Recopilar datos para un caso en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="39b07-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="39b07-104">Una vez que haya identificado los custodios y los orígenes de datos que sean de interés para su caso, es el momento de identificar el conjunto de documentos en los que profundizar.</span><span class="sxs-lookup"><span data-stu-id="39b07-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="39b07-105">Puede usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos para identificar los documentos relevantes de ubicaciones de apoyo y no Private en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39b07-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="39b07-106">Después de ejecutar una búsqueda, puede ver las estadísticas de los elementos recuperados, como las ubicaciones en las que la mayoría de los elementos coinciden con la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39b07-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="39b07-107">También puede obtener una vista previa de un subconjunto de los resultados.</span><span class="sxs-lookup"><span data-stu-id="39b07-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="39b07-108">Cuando haya identificado el conjunto de documentos que desea examinar con más detalle, puede Agregar los resultados de la búsqueda a un conjunto de revisión para recopilar y procesar.</span><span class="sxs-lookup"><span data-stu-id="39b07-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="39b07-109">Crear una búsqueda</span><span class="sxs-lookup"><span data-stu-id="39b07-109">Create a search</span></span>

<span data-ttu-id="39b07-110">Si selecciona **nueva búsqueda** en la ficha **búsquedas** , se iniciará un asistente que le guiará en la creación de una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39b07-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="39b07-111">Para obtener información detallada sobre cómo crear una búsqueda, vea [crear una búsqueda para recopilar datos](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="39b07-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="39b07-112">Una vez creada la búsqueda, se muestra una página de control flotante con los detalles.</span><span class="sxs-lookup"><span data-stu-id="39b07-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="39b07-113">Los botones **Statistics** y **Preview** no están inicialmente disponibles porque la búsqueda todavía no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="39b07-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="39b07-114">Puede realizar un seguimiento del progreso de la búsqueda en la ficha **búsquedas** .</span><span class="sxs-lookup"><span data-stu-id="39b07-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="39b07-115">Ver los resultados de la búsqueda y las estadísticas</span><span class="sxs-lookup"><span data-stu-id="39b07-115">View search results and statistics</span></span>

<span data-ttu-id="39b07-116">Hay dos componentes de una búsqueda de contenido: Statistics (Estimations) y Preview.</span><span class="sxs-lookup"><span data-stu-id="39b07-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="39b07-117">Cuando se completen todos estos componentes, verá que el estado que se muestra en las columnas correspondientes de la ficha **búsquedas** cambia de **enviado** a **en curso** a **completado**.</span><span class="sxs-lookup"><span data-stu-id="39b07-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="39b07-118">Una vez completada la estimación de la búsqueda, seleccione la búsqueda para mostrar la página de flotante, que mostrará algunas estadísticas de alto nivel sobre los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39b07-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="39b07-119">En este momento, el botón **estadísticas** estará activo.</span><span class="sxs-lookup"><span data-stu-id="39b07-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="39b07-120">Puede seleccionarlo para ver las estadísticas de búsqueda, como:</span><span class="sxs-lookup"><span data-stu-id="39b07-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="39b07-121">Resumen</span><span class="sxs-lookup"><span data-stu-id="39b07-121">Summary</span></span>
- <span data-ttu-id="39b07-122">Principales ubicaciones</span><span class="sxs-lookup"><span data-stu-id="39b07-122">Top locations</span></span>
- <span data-ttu-id="39b07-123">Queries</span><span class="sxs-lookup"><span data-stu-id="39b07-123">Queries</span></span>

<span data-ttu-id="39b07-124">Para obtener más información acerca de las estadísticas de búsqueda, vea [estadísticas de búsqueda](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="39b07-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="39b07-125">Una vez completada la vista previa, el botón **vista previa** estará activo.</span><span class="sxs-lookup"><span data-stu-id="39b07-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="39b07-126">Selecciónelo para obtener una vista previa de un subconjunto muestreado de los resultados.</span><span class="sxs-lookup"><span data-stu-id="39b07-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="39b07-127">Agregar los resultados de búsqueda a un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="39b07-127">Add search results to a review set</span></span>

<span data-ttu-id="39b07-128">Cuando esté listo para recopilar y procesar todos los resultados de una búsqueda, puede hacerlo si lo agrega a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="39b07-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="39b07-129">Para obtener más información, consulte [Agregar datos a un conjunto de revisión](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="39b07-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="39b07-130">Agregar datos que no son de Microsoft 365 a un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="39b07-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="39b07-131">Como parte del proceso de recopilación de un caso, también puede agregar datos que no sean de Office 365 a un conjunto de revisión y revisar y analizar junto con los datos de Office 365 que recopiló mediante la herramienta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39b07-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="39b07-132">Al agregar un servicio no de Office 365, debe asociarlo a un custodio específico en el caso.</span><span class="sxs-lookup"><span data-stu-id="39b07-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="39b07-133">Para obtener más información, vea [cargar datos que no son de Microsoft 365 en un conjunto de revisión](load-non-Office-365-data-into-a-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="39b07-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
