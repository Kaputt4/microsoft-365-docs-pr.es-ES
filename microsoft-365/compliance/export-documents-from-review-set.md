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
description: Obtenga información sobre cómo seleccionar y exportar contenido de un conjunto de revisiones para presentaciones o revisiones externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 855f1b8fef7a1df6ed86f058b71e5027851b5f0d
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399186"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="7a380-103">Exportar documentos desde un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="7a380-103">Export documents from a review set</span></span>

<span data-ttu-id="7a380-104">La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga.</span><span class="sxs-lookup"><span data-stu-id="7a380-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="7a380-105">La herramienta de exportación proporciona una página de configuración con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="7a380-105">The Export tool provides a configuration page with the following settings:</span></span>

![Opciones para exportar elementos de un conjunto de revisión](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="7a380-107">Opciones de exportación</span><span class="sxs-lookup"><span data-stu-id="7a380-107">Export options</span></span>

- <span data-ttu-id="7a380-108">Nombre de exportación: nombre del trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="7a380-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="7a380-109">Descripción: campo de texto libre para agregar una descripción.</span><span class="sxs-lookup"><span data-stu-id="7a380-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="7a380-110">Exportar estos documentos:</span><span class="sxs-lookup"><span data-stu-id="7a380-110">Export these documents:</span></span>

  - <span data-ttu-id="7a380-111">Solo documentos seleccionados: exporta solo los documentos que están seleccionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="7a380-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="7a380-112">Todos los documentos del conjunto de revisiones: exporta todos los documentos en el conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="7a380-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="7a380-113">Metadatos</span><span class="sxs-lookup"><span data-stu-id="7a380-113">Metadata</span></span>
  
  - <span data-ttu-id="7a380-114">Cargar archivo: este archivo contiene metadatos para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="7a380-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="7a380-115">consulte [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) para obtener más información sobre los campos que se incluyen.</span><span class="sxs-lookup"><span data-stu-id="7a380-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="7a380-116">Normalmente, las herramientas de eDiscovery de terceros pueden recopilar este archivo.</span><span class="sxs-lookup"><span data-stu-id="7a380-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="7a380-117">Etiquetas: cuando se selecciona, la información de etiquetado se incluirá en el archivo de carga.</span><span class="sxs-lookup"><span data-stu-id="7a380-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="7a380-118">Contenido</span><span class="sxs-lookup"><span data-stu-id="7a380-118">Content</span></span>
  
  - <span data-ttu-id="7a380-119">Archivos nativos: Marque esta casilla para incluir los archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="7a380-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="7a380-120">Opciones de conversación</span><span class="sxs-lookup"><span data-stu-id="7a380-120">Conversation options</span></span>
    
    - <span data-ttu-id="7a380-121">Archivos de conversación: exportar mensajes de chat reconstruidos.</span><span class="sxs-lookup"><span data-stu-id="7a380-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="7a380-122">Este formato presenta las conversaciones en un formulario similar al que ven los usuarios en la aplicación nativa.</span><span class="sxs-lookup"><span data-stu-id="7a380-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="7a380-123">Mensajes de chat individuales: exporte los archivos de conversación originales tal y como están almacenados en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7a380-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="7a380-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="7a380-124">Options</span></span>

  - <span data-ttu-id="7a380-125">Archivos de texto: incluye versiones de texto extraídos de archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="7a380-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="7a380-126">Reemplazar originales censurados con PDF convertidos: si se generan archivos PDF creados durante la revisión, estos archivos están disponibles para la exportación.</span><span class="sxs-lookup"><span data-stu-id="7a380-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="7a380-127">Puede elegir exportar solo los archivos nativos que se han censurado (no seleccionando esta opción) o puede seleccionar esta opción para exportar los archivos PDF que contienen las redacciones reales.</span><span class="sxs-lookup"><span data-stu-id="7a380-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="7a380-128">Opciones de salida (el contenido exportado está disponible para su descarga directa a través de un explorador Web o se puede enviar a una cuenta de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="7a380-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="7a380-129">Las dos primeras opciones permiten la descarga directa).</span><span class="sxs-lookup"><span data-stu-id="7a380-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="7a380-130">Archivos separados y PST (el correo electrónico se agrega a los PST cuando sea posible): los archivos se exportan en un formato similar a la estructura de directorios original que ven los usuarios en sus aplicaciones nativas.</span><span class="sxs-lookup"><span data-stu-id="7a380-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="7a380-131">Para obtener más información, consulte la sección [archivos sueltos y la estructura de exportación de PST](#loose-files-and-pst-export-structure) .</span><span class="sxs-lookup"><span data-stu-id="7a380-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="7a380-132">Estructura de directorios condensados: los archivos se exportan e incluyen en la descarga.</span><span class="sxs-lookup"><span data-stu-id="7a380-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="7a380-133">Estructura de directorios condensada exportada a su cuenta de almacenamiento de Azure: los archivos se exportan al accouunt de almacenamiento de Azure de su organización.</span><span class="sxs-lookup"><span data-stu-id="7a380-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="7a380-134">Archivos sueltos y estructura de exportación de PST</span><span class="sxs-lookup"><span data-stu-id="7a380-134">Loose files and PST export structure</span></span>

<span data-ttu-id="7a380-135">Si selecciona esta opción de exportación, el contenido exportado se organiza en la estructura siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a380-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="7a380-136">Carpeta raíz: esta carpeta en la ExportName.zip con nombre</span><span class="sxs-lookup"><span data-stu-id="7a380-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="7a380-137">Archivo de metadatos de Export_load_file.csv.</span><span class="sxs-lookup"><span data-stu-id="7a380-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="7a380-138">Summary.csv: un archivo de resumen que también contiene estadísticas de exportación.</span><span class="sxs-lookup"><span data-stu-id="7a380-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="7a380-139">Exchange: esta carpeta contiene todo el contenido de Exchange en formato de archivo nativo.</span><span class="sxs-lookup"><span data-stu-id="7a380-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="7a380-140">Los archivos nativos se reemplazan con documentos PDF censurados si ha seleccionado la opción **reemplazar archivos nativos censurados con archivos PDF convertidos** .</span><span class="sxs-lookup"><span data-stu-id="7a380-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="7a380-141">SharePoint = esta carpeta contiene todo el contenido nativo de SharePoint en un formato de archivo nativo.</span><span class="sxs-lookup"><span data-stu-id="7a380-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="7a380-142">Los archivos nativos se reemplazan con documentos PDF censurados si ha seleccionado la opción **reemplazar archivos nativos censurados con archivos PDF convertidos** .</span><span class="sxs-lookup"><span data-stu-id="7a380-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="7a380-143">Estructura de directorios condensada</span><span class="sxs-lookup"><span data-stu-id="7a380-143">Condensed directory structure</span></span>

- <span data-ttu-id="7a380-144">Carpeta raíz: esta carpeta se denomina ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="7a380-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="7a380-145">Archivo de metadatos de Export_load_file.csv.</span><span class="sxs-lookup"><span data-stu-id="7a380-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="7a380-146">Summary.txt: un archivo de resumen que también contiene estadísticas de exportación.</span><span class="sxs-lookup"><span data-stu-id="7a380-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="7a380-147">Input_or_native_files: esta carpeta contiene todos los archivos nativos que se exportaron.</span><span class="sxs-lookup"><span data-stu-id="7a380-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="7a380-148">Si exporta archivos PDF censurados, no se colocan en archivos PST.</span><span class="sxs-lookup"><span data-stu-id="7a380-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="7a380-149">En su lugar, se agregan a una carpeta separada.</span><span class="sxs-lookup"><span data-stu-id="7a380-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="7a380-150">Error_files: esta carpeta contiene los siguientes archivos de error, si se incluyen en la exportación:</span><span class="sxs-lookup"><span data-stu-id="7a380-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="7a380-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="7a380-151">ExtractionError.</span></span> <span data-ttu-id="7a380-152">Un archivo CSV que contiene los metadatos disponibles de los archivos que no se han extraído correctamente de los archivos principales.</span><span class="sxs-lookup"><span data-stu-id="7a380-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="7a380-153">ProcessingError: este archivo contiene una lista de documentos con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7a380-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="7a380-154">Este contenido es de nivel de elemento, lo que significa que si un archivo adjunto produjo un error de procesamiento, el mensaje de correo electrónico que contiene los datos adjuntos se incluye en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="7a380-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="7a380-155">Extracted_text_files: esta carpeta contiene todos los archivos de texto extraídos que se generaron en el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7a380-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="7a380-156">Los trabajos de exportación se conservan durante la vigencia del caso y se pueden descargar siempre y cuando no se elimine el caso.</span><span class="sxs-lookup"><span data-stu-id="7a380-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
