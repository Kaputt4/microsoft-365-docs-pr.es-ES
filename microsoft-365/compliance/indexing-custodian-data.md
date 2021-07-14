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
ms.openlocfilehash: f510b7e9c0fa2c5c181709c96907610066a4b1cf
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430518"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="a16a0-103">Clasificación avanzada de los datos de administración</span><span class="sxs-lookup"><span data-stu-id="a16a0-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="a16a0-104">Cuando se agrega un custodio Advanced eDiscovery un caso de Advanced eDiscovery, se vuelve a indizar todo el contenido que se consideró parcialmente indizado o con errores de indización para hacerlo totalmente compatible con búsquedas.</span><span class="sxs-lookup"><span data-stu-id="a16a0-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="a16a0-105">Este proceso de reindexación se denomina *Indexación avanzada*.</span><span class="sxs-lookup"><span data-stu-id="a16a0-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="a16a0-106">Hay varias razones por las que el contenido está parcialmente indizado o tiene errores de indización.</span><span class="sxs-lookup"><span data-stu-id="a16a0-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="a16a0-107">Esto incluye archivos de imagen o la presencia de imágenes en un archivo, tipos de archivo no admitidos o límites de indización de tamaño de archivo.</span><span class="sxs-lookup"><span data-stu-id="a16a0-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="a16a0-108">Para SharePoint, la indización avanzada solo se ejecuta en elementos que se marcan como parcialmente indizados o que tienen errores de indización.</span><span class="sxs-lookup"><span data-stu-id="a16a0-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="a16a0-109">En Exchange, los mensajes de correo electrónico que tienen datos adjuntos de imagen no se marcan como parcialmente indizados o con errores de indización.</span><span class="sxs-lookup"><span data-stu-id="a16a0-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="a16a0-110">Esto significa que esos archivos no se volverán a indizar mediante el proceso de indización avanzada.</span><span class="sxs-lookup"><span data-stu-id="a16a0-110">This means that those files will not be reindexed by Advanced indexing process.</span></span>

<span data-ttu-id="a16a0-111">Para obtener más información sobre el procesamiento de soporte técnico y elementos parcialmente indizados, vea:</span><span class="sxs-lookup"><span data-stu-id="a16a0-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="a16a0-112">Tipos de archivo admitidos en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a16a0-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="a16a0-113">Elementos parcialmente indizados en la búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="a16a0-113">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="a16a0-114">Formatos de archivo indizados por la búsqueda de Exchange</span><span class="sxs-lookup"><span data-stu-id="a16a0-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="a16a0-115">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="a16a0-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="a16a0-116">Visualización de resultados de indización avanzada</span><span class="sxs-lookup"><span data-stu-id="a16a0-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="a16a0-117">Una vez completado el proceso de indización avanzada, puede comprender la eficacia del reprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="a16a0-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="a16a0-118">En la vista Resultados  de indización avanzada de la ficha Procesamiento de un caso, el gráfico enumera el número de elementos agregados al *índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="a16a0-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="a16a0-119">El índice híbrido es donde Advanced eDiscovery almacena el contenido reprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="a16a0-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="a16a0-120">Esta vista también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="a16a0-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="a16a0-121">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="a16a0-121">For more information, see:</span></span>

- [<span data-ttu-id="a16a0-122">Corrección de errores al procesar los datos</span><span class="sxs-lookup"><span data-stu-id="a16a0-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="a16a0-123">Corrección de errores de un único elemento</span><span class="sxs-lookup"><span data-stu-id="a16a0-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="a16a0-124">Actualización del índice avanzado para custodios</span><span class="sxs-lookup"><span data-stu-id="a16a0-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="a16a0-125">Cuando se agrega un custodio a un Advanced eDiscovery caso, todos los elementos parcialmente indizados se reprocesamienton.</span><span class="sxs-lookup"><span data-stu-id="a16a0-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="a16a0-126">Sin embargo, a medida que pasa el tiempo, se pueden agregar elementos más indizados parcialmente al buzón de un usuario o a OneDrive cuenta.</span><span class="sxs-lookup"><span data-stu-id="a16a0-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="a16a0-127">Si es necesario, puede actualizar el índice para un custodio específico.</span><span class="sxs-lookup"><span data-stu-id="a16a0-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="a16a0-128">Para obtener más información, vea [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="a16a0-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="a16a0-129">También puede actualizar el índice de todos los custodios en un caso haciendo clic en el **índice Actualizar** de la **ficha** Procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a16a0-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="a16a0-130">La actualización de índices de custodia es un proceso de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="a16a0-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="a16a0-131">Se recomienda no actualizar índices más de una vez al día en un caso.</span><span class="sxs-lookup"><span data-stu-id="a16a0-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
