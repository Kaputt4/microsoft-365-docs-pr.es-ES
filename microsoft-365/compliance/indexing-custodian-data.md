---
title: Clasificación avanzada de los datos de administración
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
description: Cuando se agrega un custodio a un caso Advanced eDiscovery, cualquier contenido que se consideró parcialmente indizado se vuelve a procesar para que sea totalmente posible realizar búsquedas.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911214"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="2ad4d-103">Clasificación avanzada de los datos de administración</span><span class="sxs-lookup"><span data-stu-id="2ad4d-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="2ad4d-104">Cuando se agrega un custodio a un caso Advanced eDiscovery, cualquier contenido que se consideró parcialmente indizado se vuelve a procesar para que sea totalmente posible realizar búsquedas.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="2ad4d-105">Este proceso se denomina *Indización avanzada*.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="2ad4d-106">El contenido se puede indizar parcialmente por varios motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="2ad4d-107">Para obtener más información sobre el procesamiento de soporte técnico y elementos parcialmente indizados, vea:</span><span class="sxs-lookup"><span data-stu-id="2ad4d-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="2ad4d-108">Tipos de archivo admitidos en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2ad4d-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="2ad4d-109">Elementos parcialmente indizados en la búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="2ad4d-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="2ad4d-110">Formatos de archivo indizados por la búsqueda de Exchange</span><span class="sxs-lookup"><span data-stu-id="2ad4d-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="2ad4d-111">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="2ad4d-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="2ad4d-112">Visualización de resultados de indización avanzada</span><span class="sxs-lookup"><span data-stu-id="2ad4d-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="2ad4d-113">Una vez completado el proceso de indización avanzada, puede comprender la eficacia del reprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="2ad4d-114">En la vista Resultados  de indización avanzada de la ficha Procesamiento de un caso, el gráfico enumera el número de elementos agregados al *índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="2ad4d-115">El índice híbrido es donde Advanced eDiscovery almacena el contenido reprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="2ad4d-116">Esta vista también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="2ad4d-117">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="2ad4d-117">For more information, see:</span></span>

- [<span data-ttu-id="2ad4d-118">Corrección de errores al procesar los datos</span><span class="sxs-lookup"><span data-stu-id="2ad4d-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="2ad4d-119">Corrección de errores de un único elemento</span><span class="sxs-lookup"><span data-stu-id="2ad4d-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="2ad4d-120">Actualización del índice avanzado para custodios</span><span class="sxs-lookup"><span data-stu-id="2ad4d-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="2ad4d-121">Cuando se agrega un custodio a un Advanced eDiscovery caso, todos los elementos parcialmente indizados se reprocesamienton.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="2ad4d-122">Sin embargo, a medida que pasa el tiempo, se pueden agregar elementos más indizados parcialmente al buzón de un usuario o a OneDrive cuenta.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="2ad4d-123">Si es necesario, puede actualizar el índice para un custodio específico.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="2ad4d-124">Para obtener más información, vea [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="2ad4d-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="2ad4d-125">También puede actualizar el índice de todos los custodios en un caso haciendo clic en el **índice Actualizar** de la **ficha** Procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="2ad4d-126">La actualización de índices de custodia es un proceso de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="2ad4d-127">Se recomienda no actualizar índices más de una vez al día en un caso.</span><span class="sxs-lookup"><span data-stu-id="2ad4d-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>