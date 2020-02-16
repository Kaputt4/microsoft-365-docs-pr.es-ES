---
title: Exportar documentos desde un conjunto de revisión
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
description: ''
ms.openlocfilehash: 9a732258e787de3407731f0fdfc98ed07653df71
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074366"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="3bce8-102">Exportar documentos desde un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="3bce8-102">Export documents from a review set</span></span>

<span data-ttu-id="3bce8-103">Puede exportar el contenido para la presentación o la revisión externa a partir de un conjunto de revisión por uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="3bce8-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="3bce8-104">Descargar documentos</span><span class="sxs-lookup"><span data-stu-id="3bce8-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="3bce8-105">Exportar documentos</span><span class="sxs-lookup"><span data-stu-id="3bce8-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="3bce8-106">Descargar documentos de un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="3bce8-106">Download documents from a review set</span></span>

<span data-ttu-id="3bce8-107">La descarga ofrece una forma sencilla de descargar contenido de un conjunto de revisión en formato nativo.</span><span class="sxs-lookup"><span data-stu-id="3bce8-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="3bce8-108">Aprovecha las características de transferencia de datos del explorador para que aparezca un mensaje del explorador una vez que la descarga esté lista.</span><span class="sxs-lookup"><span data-stu-id="3bce8-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="3bce8-109">Los archivos descargados con este método se comprimen en un archivo contenedor y serán archivos de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="3bce8-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="3bce8-110">Esto significa que, si selecciona un archivo adjunto, recibirá automáticamente el correo electrónico con los datos adjuntos incluidos.</span><span class="sxs-lookup"><span data-stu-id="3bce8-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="3bce8-111">De forma similar, si selecciona una hoja de cálculo de Excel que estaba incrustada en un documento de Word, recibirá el documento de Word con la hoja de cálculo de Excel incrustada.</span><span class="sxs-lookup"><span data-stu-id="3bce8-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="3bce8-112">Los elementos descargados conservarán la fecha de la última modificación, que se puede ver como una propiedad de archivo.</span><span class="sxs-lookup"><span data-stu-id="3bce8-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="3bce8-113">Para descargar contenido de un conjunto de revisión, seleccione los archivos que desea descargar y, a continuación, seleccione "Descargar" en el menú acciones.</span><span class="sxs-lookup"><span data-stu-id="3bce8-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Una captura de pantalla de una descripción de equipo generada automáticamente](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="3bce8-115">Exportar documentos desde un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="3bce8-115">Export documents from a review set</span></span>

<span data-ttu-id="3bce8-116">La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga.</span><span class="sxs-lookup"><span data-stu-id="3bce8-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="3bce8-117">Proporciona una página de configuración con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="3bce8-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="3bce8-118">Archivo de metadatos</span><span class="sxs-lookup"><span data-stu-id="3bce8-118">Metadata file</span></span>

<span data-ttu-id="3bce8-119">Esto puede considerarse el "Cargar archivo" que contiene metadatos asociados con los archivos que se exportan.</span><span class="sxs-lookup"><span data-stu-id="3bce8-119">This can be considered your "load file" that contains metadata associated with the files you export.</span></span> <span data-ttu-id="3bce8-120">Para obtener una lista de los campos exportados disponibles en el archivo de metadatos, consulte [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="3bce8-120">For a list of exported fields available in the metadata file, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="3bce8-121">Por lo general, este archivo puede ser recopilado por herramientas de terceros.</span><span class="sxs-lookup"><span data-stu-id="3bce8-121">This file can typically be ingested by third-party tools.</span></span>

### <a name="tag-data"></a><span data-ttu-id="3bce8-122">Datos de etiqueta</span><span class="sxs-lookup"><span data-stu-id="3bce8-122">Tag data</span></span>

<span data-ttu-id="3bce8-123">Este contenido se agregaría como campos en el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3bce8-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="3bce8-124">Contiene toda la información de etiqueta aplicada en los conjuntos de revisión.</span><span class="sxs-lookup"><span data-stu-id="3bce8-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="3bce8-125">Archivos de texto</span><span class="sxs-lookup"><span data-stu-id="3bce8-125">Text files</span></span>

<span data-ttu-id="3bce8-126">Los archivos de texto se pueden generar para cada archivo exportado de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="3bce8-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="3bce8-127">A menudo, los asociados de servicios necesitan estos archivos como parte de la recopilación de datos en herramientas de terceros.</span><span class="sxs-lookup"><span data-stu-id="3bce8-127">Often times these files are required by service partners as part of ingesting data into third-party tools.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="3bce8-128">Archivos censurados</span><span class="sxs-lookup"><span data-stu-id="3bce8-128">Redacted files</span></span>

<span data-ttu-id="3bce8-129">Si se generan archivos PDF censurados durante la revisión, estos archivos están disponibles durante la exportación.</span><span class="sxs-lookup"><span data-stu-id="3bce8-129">If redacted PDF files are generated during review, these files are available during export.</span></span> <span data-ttu-id="3bce8-130">Puede decidir si desea exportar solo los archivos nativos o reemplazar los archivos nativos que requerían censura con los archivos PDF que contienen las redacciones reales.</span><span class="sxs-lookup"><span data-stu-id="3bce8-130">You can decide whether to export native files only or to replace the native files that required redaction with the PDF files that contain the actual redactions.</span></span>

### <a name="export-location"></a><span data-ttu-id="3bce8-131">Ubicación de exportación</span><span class="sxs-lookup"><span data-stu-id="3bce8-131">Export location</span></span>

<span data-ttu-id="3bce8-132">El contenido exportado se entrega en un BLOB de Azure o el BLOB de un cliente de Microsoft se puede usar si los detalles se proporcionan en la exportación.</span><span class="sxs-lookup"><span data-stu-id="3bce8-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="3bce8-133">Exportar estructura</span><span class="sxs-lookup"><span data-stu-id="3bce8-133">Export structure</span></span>

<span data-ttu-id="3bce8-134">Cuando se exporta contenido desde un conjunto de revisión, el contenido se organiza en la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bce8-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="3bce8-135">Carpeta raíz: identificador de descarga</span><span class="sxs-lookup"><span data-stu-id="3bce8-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="3bce8-136">Exportar\_archivo\_de carga. csv = archivo de metadatos</span><span class="sxs-lookup"><span data-stu-id="3bce8-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="3bce8-137">Summary. txt = un archivo de resumen con las estadísticas de exportación</span><span class="sxs-lookup"><span data-stu-id="3bce8-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="3bce8-138">Archivos\_nativos\_o de entrada = contiene todos los archivos nativos</span><span class="sxs-lookup"><span data-stu-id="3bce8-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="3bce8-139">Archivos\_de errores = contiene los archivos de error incluidos en la exportación</span><span class="sxs-lookup"><span data-stu-id="3bce8-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="3bce8-140">ExtractionError: un CSV que contiene los metadatos disponibles de los archivos que no se han extraído correctamente de los archivos principales</span><span class="sxs-lookup"><span data-stu-id="3bce8-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="3bce8-141">ProcessingError: contenido con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3bce8-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="3bce8-142">Este contenido es el significado del nivel de elemento si los datos adjuntos experimentan un error de procesamiento, el correo electrónico que contiene los datos adjuntos se incluirá en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="3bce8-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="3bce8-143">Archivos\_de\_texto extraídos = contiene todos los archivos de texto extraídos generados en el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3bce8-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>
