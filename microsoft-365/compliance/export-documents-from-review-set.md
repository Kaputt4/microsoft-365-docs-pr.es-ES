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
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423651"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="54a1e-103">Exportar documentos desde un conjunto de revisión en exhibición de documentos electrónicos avanzada</span><span class="sxs-lookup"><span data-stu-id="54a1e-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="54a1e-104">La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga.</span><span class="sxs-lookup"><span data-stu-id="54a1e-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="54a1e-105">La herramienta Exportar proporciona una página de configuración con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="54a1e-105">The Export tool provides a configuration page with the following settings:</span></span>

![Opciones para exportar elementos de un conjunto de revisión](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="54a1e-107">Opciones de exportación</span><span class="sxs-lookup"><span data-stu-id="54a1e-107">Export options</span></span>

- <span data-ttu-id="54a1e-108">Nombre de exportación: nombre del trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="54a1e-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="54a1e-109">Descripción: campo de texto libre para agregar una descripción.</span><span class="sxs-lookup"><span data-stu-id="54a1e-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="54a1e-110">Exporte estos documentos:</span><span class="sxs-lookup"><span data-stu-id="54a1e-110">Export these documents:</span></span>

  - <span data-ttu-id="54a1e-111">Solo documentos seleccionados: exporta solo los documentos seleccionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="54a1e-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="54a1e-112">Todos los documentos del conjunto de revisión: exporta todos los documentos del conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="54a1e-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="54a1e-113">Metadata</span><span class="sxs-lookup"><span data-stu-id="54a1e-113">Metadata</span></span>
  
  - <span data-ttu-id="54a1e-114">Cargar archivo: este archivo contiene metadatos para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="54a1e-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="54a1e-115">Para obtener más información acerca de los campos que se incluyen, vea [Campos de metadatos de documento en Exhibición de documentos electrónicos avanzada.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="54a1e-115">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="54a1e-116">Este archivo normalmente puede ser ingerido por herramientas de exhibición de documentos electrónicos de terceros.</span><span class="sxs-lookup"><span data-stu-id="54a1e-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="54a1e-117">Etiquetas: cuando se selecciona, la información de etiquetado se incluirá en el archivo de carga.</span><span class="sxs-lookup"><span data-stu-id="54a1e-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="54a1e-118">Contenido</span><span class="sxs-lookup"><span data-stu-id="54a1e-118">Content</span></span>
  
  - <span data-ttu-id="54a1e-119">Archivos nativos: active esta casilla para incluir los archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="54a1e-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="54a1e-120">Opciones de conversación</span><span class="sxs-lookup"><span data-stu-id="54a1e-120">Conversation options</span></span>
    
    - <span data-ttu-id="54a1e-121">Archivos de conversación: exportar mensajes de chat reconstruidos.</span><span class="sxs-lookup"><span data-stu-id="54a1e-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="54a1e-122">Este formato presenta conversaciones en un formulario que se asemeja a lo que los usuarios ven en la aplicación nativa.</span><span class="sxs-lookup"><span data-stu-id="54a1e-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="54a1e-123">Mensajes de chat individuales: exporte los archivos de conversación originales a medida que se almacenan en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54a1e-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="54a1e-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="54a1e-124">Options</span></span>

  - <span data-ttu-id="54a1e-125">Archivos de texto: incluye versiones de texto extraídas de archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="54a1e-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="54a1e-126">Reemplazar los nativos redactados por archivos PDF convertidos: si los archivos PDF redactados se generan durante la revisión, estos archivos están disponibles para la exportación.</span><span class="sxs-lookup"><span data-stu-id="54a1e-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="54a1e-127">Puede elegir exportar solo los archivos nativos que se han redactado (no seleccionando esta opción) o puede seleccionar esta opción para exportar los archivos PDF que contienen las redacciones reales.</span><span class="sxs-lookup"><span data-stu-id="54a1e-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="54a1e-128">Opciones de salida (El contenido exportado está disponible para su descarga directamente a través de un explorador web o se puede enviar a una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="54a1e-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="54a1e-129">Las dos primeras opciones habilitan la descarga directa).</span><span class="sxs-lookup"><span data-stu-id="54a1e-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="54a1e-130">Archivos sueltos y PST (el correo electrónico se agrega a los PST cuando es posible): los archivos se exportan en un formato similar a la estructura de directorio original que ven los usuarios en sus aplicaciones nativas.</span><span class="sxs-lookup"><span data-stu-id="54a1e-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="54a1e-131">Para obtener más información, vea [la sección Archivos sueltos y estructura de exportación de PST.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="54a1e-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="54a1e-132">Estructura de directorio condensada: los archivos se exportan e incluyen en la descarga.</span><span class="sxs-lookup"><span data-stu-id="54a1e-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="54a1e-133">Estructura de directorio condensada exportada a su cuenta de Azure Storage: los archivos se exportan a la cuenta de Azure Storage de su organización.</span><span class="sxs-lookup"><span data-stu-id="54a1e-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage account.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="54a1e-134">Archivos sueltos y estructura de exportación de PST</span><span class="sxs-lookup"><span data-stu-id="54a1e-134">Loose files and PST export structure</span></span>

<span data-ttu-id="54a1e-135">Si selecciona esta opción de exportación, el contenido exportado se organiza en la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="54a1e-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="54a1e-136">Carpeta raíz: esta carpeta en el nombre ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="54a1e-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="54a1e-137">Export_load_file.csv: archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="54a1e-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="54a1e-138">Summary.csv: un archivo de resumen que también contiene estadísticas de exportación.</span><span class="sxs-lookup"><span data-stu-id="54a1e-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="54a1e-139">Exchange: esta carpeta contiene todo el contenido de Exchange en formato de archivo nativo.</span><span class="sxs-lookup"><span data-stu-id="54a1e-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="54a1e-140">Los archivos nativos se reemplazan por archivos PDF redactados si ha seleccionado la opción Reemplazar **nativos** redactados con ARCHIVOS PDF convertidos.</span><span class="sxs-lookup"><span data-stu-id="54a1e-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="54a1e-141">SharePoint = Esta carpeta contiene todo el contenido nativo de SharePoint en un formato de archivo nativo.</span><span class="sxs-lookup"><span data-stu-id="54a1e-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="54a1e-142">Los archivos nativos se reemplazan por archivos PDF redactados si ha seleccionado la opción Reemplazar **nativos** redactados con ARCHIVOS PDF convertidos.</span><span class="sxs-lookup"><span data-stu-id="54a1e-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="54a1e-143">Estructura de directorio condensada</span><span class="sxs-lookup"><span data-stu-id="54a1e-143">Condensed directory structure</span></span>

- <span data-ttu-id="54a1e-144">Carpeta raíz: esta carpeta se denomina ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="54a1e-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="54a1e-145">Export_load_file.csv: archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="54a1e-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="54a1e-146">Summary.txt: un archivo de resumen que también contiene estadísticas de exportación.</span><span class="sxs-lookup"><span data-stu-id="54a1e-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="54a1e-147">Input_or_native_files: esta carpeta contiene todos los archivos nativos que se exportaron.</span><span class="sxs-lookup"><span data-stu-id="54a1e-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="54a1e-148">Si exporta archivos PDF redactados, no se colocarán en archivos PST.</span><span class="sxs-lookup"><span data-stu-id="54a1e-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="54a1e-149">En su lugar, se agregan a una carpeta separada.</span><span class="sxs-lookup"><span data-stu-id="54a1e-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="54a1e-150">Error_files: esta carpeta contiene los siguientes archivos de error, si se incluyen en la exportación:</span><span class="sxs-lookup"><span data-stu-id="54a1e-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="54a1e-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="54a1e-151">ExtractionError.</span></span> <span data-ttu-id="54a1e-152">Un archivo CSV que contiene los metadatos disponibles de archivos que no se extrajeron correctamente de los archivos primarios.</span><span class="sxs-lookup"><span data-stu-id="54a1e-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="54a1e-153">ProcessingError: este archivo contiene una lista de documentos con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="54a1e-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="54a1e-154">Este contenido es de nivel de elemento, lo que significa que si un archivo adjunto produjo un error de procesamiento, el mensaje de correo electrónico que contiene los datos adjuntos se incluye en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="54a1e-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="54a1e-155">Extracted_text_files: esta carpeta contiene todos los archivos de texto extraídos que se generaron durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="54a1e-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="54a1e-156">Los trabajos de exportación se conservan durante la duración del caso.</span><span class="sxs-lookup"><span data-stu-id="54a1e-156">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="54a1e-157">Sin embargo, debe descargar el contenido de un trabajo de exportación en un plazo de 30 días después de que se complete el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="54a1e-157">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>
