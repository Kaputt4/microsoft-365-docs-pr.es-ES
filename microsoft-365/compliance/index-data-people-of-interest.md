---
title: Indización avanzada de datos para una investigación
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
description: Obtenga información sobre cómo usar la indización avanzada para asegurarse de que su búsqueda captura todos los datos que desea investigar.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b0bb1a757ac70466fb43f2385485ce6da1dc741
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285966"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="fbb49-103">Indización avanzada de datos para una investigación</span><span class="sxs-lookup"><span data-stu-id="fbb49-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="fbb49-104">El contenido del sistema activo se puede indizar parcialmente por una serie de motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.</span><span class="sxs-lookup"><span data-stu-id="fbb49-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="fbb49-105">Cuando se trata de un derrame de datos de riesgo alto, desea asegurarse de que la búsqueda capturó todos los datos que desea investigar.</span><span class="sxs-lookup"><span data-stu-id="fbb49-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="fbb49-106">Cuando se agrega a una persona de interés a una investigación de datos, todo el contenido que se considere indizado parcialmente se reprocesa para que se pueda buscar por completo.</span><span class="sxs-lookup"><span data-stu-id="fbb49-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span> <span data-ttu-id="fbb49-107">Este proceso se denomina *indización avanzada*.</span><span class="sxs-lookup"><span data-stu-id="fbb49-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="fbb49-108">Para obtener más información acerca de la compatibilidad de procesamiento y los elementos indizados parcialmente, consulte:</span><span class="sxs-lookup"><span data-stu-id="fbb49-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="fbb49-109">Tipos de archivo admitidos en investigaciones de datos</span><span class="sxs-lookup"><span data-stu-id="fbb49-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="fbb49-110">Elementos parcialmente indizados en la búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="fbb49-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="fbb49-111">Formatos de archivo indizados por la búsqueda de Exchange</span><span class="sxs-lookup"><span data-stu-id="fbb49-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="fbb49-112">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="fbb49-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="fbb49-113">Ver resultados de indización avanzada</span><span class="sxs-lookup"><span data-stu-id="fbb49-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="fbb49-114">Una vez completado el proceso de indización avanzado, puede comprender la efectividad del reprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="fbb49-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="fbb49-115">En la vista de indización de personas de interés, el gráfico muestra todos los elementos agregados al *Índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="fbb49-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="fbb49-116">El índice híbrido es donde las investigaciones de datos (versión preliminar) almacenan el contenido reprocesado.</span><span class="sxs-lookup"><span data-stu-id="fbb49-116">The hybrid index is where Data Investigations (preview) stores the reprocessed content.</span></span>

<span data-ttu-id="fbb49-117">El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="fbb49-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="fbb49-118">Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="fbb49-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="fbb49-119">Actualización de índices avanzados para personas de interés</span><span class="sxs-lookup"><span data-stu-id="fbb49-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="fbb49-120">Cuando se agrega a una persona de interés a una investigación de datos, se reprocesan todos los elementos parcialmente indizados.</span><span class="sxs-lookup"><span data-stu-id="fbb49-120">When a person of interest is added to a data investigation, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="fbb49-121">Sin embargo, a medida que pasa el tiempo, se pueden agregar más elementos indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fbb49-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="fbb49-122">Cuando sea necesario, puede actualizar los índices.</span><span class="sxs-lookup"><span data-stu-id="fbb49-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="fbb49-123">La actualización de personas de índices de interés es un proceso de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="fbb49-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="fbb49-124">Se recomienda no actualizar índices más de una vez al día en una investigación.</span><span class="sxs-lookup"><span data-stu-id="fbb49-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
