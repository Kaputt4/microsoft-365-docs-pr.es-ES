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
description: Obtenga información sobre cómo seleccionar y exportar contenido de un conjunto de Advanced eDiscovery para presentaciones o revisiones externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a174c147da6e424891508bad484f45f4a5d308b6
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461404"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="4d0a3-103">Exportar documentos de un conjunto de revisión en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4d0a3-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="4d0a3-104">La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga al exportar el documento de un conjunto de revisión en Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="4d0a3-105">Para exportar documentos de un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="4d0a3-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="4d0a3-106">En el Centro de cumplimiento de Microsoft 365, abra el Advanced eDiscovery, seleccione la  pestaña Conjuntos de revisión y, a continuación, seleccione el conjunto de revisión que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="4d0a3-107">En el conjunto de revisión, haga clic **en Exportar**  >  **acción**.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="4d0a3-108">La herramienta Exportar muestra la página desplegable con la configuración para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="4d0a3-109">Algunas opciones están seleccionadas de forma predeterminada, pero puede cambiar estas opciones.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="4d0a3-110">Consulte la siguiente sección para obtener descripciones de las opciones de exportación que puede configurar.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Opciones de configuración para exportar elementos de un conjunto de revisión](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="4d0a3-112">Después de configurar la exportación, haga clic **en Exportar** para iniciar el proceso de exportación.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="4d0a3-113">Según la opción seleccionada  en la sección Opciones de salida, puede tener acceso a los archivos de exportación mediante descarga directa o en la cuenta de Azure Storage organización.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="4d0a3-114">Los trabajos de exportación se conservan durante la duración del caso.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="4d0a3-115">Sin embargo, debe descargar el contenido de un trabajo de exportación en un plazo de 30 días después de que se complete el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="4d0a3-116">Opciones de exportación</span><span class="sxs-lookup"><span data-stu-id="4d0a3-116">Export options</span></span>

<span data-ttu-id="4d0a3-117">Use las siguientes opciones para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-117">Use the following options to configure the export.</span></span> <span data-ttu-id="4d0a3-118">No todas las opciones están permitidas para algunas opciones de salida, sobre todo, la exportación de archivos de texto y archivos PDF redactadas no se permite al exportar al formato PST.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-118">Not all options are allowed for some output options, most notably, export of text files and redacted PDFs are not allowed when exporting to the PST format.</span></span>

- <span data-ttu-id="4d0a3-119">**Nombre de exportación:** nombre del trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-119">**Export name**: Name of the export job.</span></span> <span data-ttu-id="4d0a3-120">Esto se usará para nombrar los archivos ZIP que se descargarán.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-120">This will be used to name the ZIP files that will be downloaded.</span></span>

- <span data-ttu-id="4d0a3-121">**Descripción:** campo de texto libre para agregar una descripción.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-121">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="4d0a3-122">**Exportar estos documentos**</span><span class="sxs-lookup"><span data-stu-id="4d0a3-122">**Export these documents**</span></span>

  - <span data-ttu-id="4d0a3-123">Solo documentos seleccionados: esta opción exporta solo los documentos seleccionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-123">Selected documents only: This option exports only the documents that are currently selected.</span></span> <span data-ttu-id="4d0a3-124">Esta opción solo está disponible cuando los elementos están seleccionados en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-124">This option is only available when items are selected in a review set.</span></span>
  
  - <span data-ttu-id="4d0a3-125">Todos los documentos filtrados: esta opción exporta los documentos en un filtro activo.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-125">All filtered documents: This option exports the documents in an active filter.</span></span> <span data-ttu-id="4d0a3-126">Esta opción solo está disponible cuando se aplica un filtro al conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-126">This option is only available when a filter is applied to the review set.</span></span>
  
  - <span data-ttu-id="4d0a3-127">Todos los documentos del conjunto de revisión: esta opción exporta todos los documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-127">All documents in the review set: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="4d0a3-128">**Opciones de** salida: el contenido exportado está disponible para su descarga directamente a través de un explorador web o se puede enviar a una cuenta Azure Storage usuario.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-128">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="4d0a3-129">Las dos primeras opciones habilitan la descarga directa.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-129">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="4d0a3-130">Solo informes: solo se crean el archivo de resumen y carga.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-130">Reports only: Only the summary and load file are created.</span></span>
  
  - <span data-ttu-id="4d0a3-131">Archivos sueltos y PST (el correo electrónico se agrega a los ARCHIVOS PST cuando es posible): los archivos se exportan en un formato similar a la estructura de directorio original que ven los usuarios en sus aplicaciones nativas.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-131">Loose files and PSTs (email is added to PSTs when possible): Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="4d0a3-132">Para obtener más información, vea [la sección Archivos sueltos y estructura de exportación de PST.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="4d0a3-132">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="4d0a3-133">Estructura de directorio condensada: los archivos se exportan e incluyen en la descarga.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-133">Condensed directory structure: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="4d0a3-134">Estructura de directorio condensada exportada a su Azure Storage: los archivos se exportan a la cuenta de Azure Storage organización.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-134">Condensed directory structure exported to your Azure Storage account: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="4d0a3-135">Para esta opción, debe proporcionar la dirección URL del contenedor en su cuenta de Azure Storage a la que exportar los archivos.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-135">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="4d0a3-136">También debe proporcionar el token de firma de acceso compartido (SAS) para su Azure Storage cuenta.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-136">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="4d0a3-137">Para obtener más información, vea [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4d0a3-137">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

- <span data-ttu-id="4d0a3-138">**Include**</span><span class="sxs-lookup"><span data-stu-id="4d0a3-138">**Include**</span></span>
  
  - <span data-ttu-id="4d0a3-139">Etiquetas: cuando se selecciona, la información de etiquetado se incluye en el archivo de carga.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-139">Tags: When selected, tagging information is included in the load file.</span></span>
  
  - <span data-ttu-id="4d0a3-140">Archivos de texto: esta opción incluye las versiones de texto extraídas de los archivos nativos en la exportación.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-140">Text files: This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="4d0a3-141">Reemplace los nativos redactados por archivos PDF convertidos: si los archivos PDF redactados se generan durante la revisión, estos archivos están disponibles para la exportación.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-141">Replace redacted natives with converted PDFs: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="4d0a3-142">Puede elegir exportar solo los archivos nativos que se han redactado (no seleccionando esta opción) o puede seleccionar esta opción para exportar los archivos PDF que contienen las redacciones reales.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-142">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

<span data-ttu-id="4d0a3-143">En las secciones siguientes se describe la estructura de carpetas para archivos sueltos y opciones de estructura de directorios condensadas.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-143">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span> <span data-ttu-id="4d0a3-144">Las exportaciones se particionan en archivos ZIP con un tamaño máximo de contenido sin comprimir de 75 GB.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-144">Exports are partitioned into ZIP files with a maximum size of uncompressed content of 75 GB.</span></span> <span data-ttu-id="4d0a3-145">Si el tamaño de exportación es inferior a 75 GB, la exportación constará de un archivo de resumen y un único archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-145">If the export size is less than 75 GB, the export will consist of a summary file and a single ZIP file.</span></span> <span data-ttu-id="4d0a3-146">Para las exportaciones de más de 75 GB de datos sin comprimir, se crearán varios archivos ZIP.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-146">For exports larger than 75 GB of uncompressed data, multiple ZIP files will be created.</span></span> <span data-ttu-id="4d0a3-147">Una vez descargados, los archivos ZIP se pueden descomprimir en una sola ubicación para volver a crear la exportación completa.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-147">Once downloaded, the ZIP files can be uncompressed into a single location to recreate the full export.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="4d0a3-148">Archivos sueltos y estructura de exportación de PST</span><span class="sxs-lookup"><span data-stu-id="4d0a3-148">Loose files and PST export structure</span></span>

<span data-ttu-id="4d0a3-149">Si selecciona esta opción de exportación, el contenido exportado se organiza en la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="4d0a3-149">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="4d0a3-150">Summary.csv: incluye un resumen del contenido exportado desde el conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="4d0a3-150">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="4d0a3-151">Carpeta raíz: esta carpeta en el nombre [Export Name] x de z.zip y se repetirá para cada partición de archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-151">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="4d0a3-152">Export_load_file_x de z.csv: el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-152">Export_load_file_x of z.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="4d0a3-153">Advertencias y errores x de z.csv: este archivo incluye información sobre los errores detectados al intentar exportar desde el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-153">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  
  - <span data-ttu-id="4d0a3-154">Exchange: esta carpeta contiene todo el contenido de Exchange almacenado en archivos PST.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-154">Exchange: This folder contains all content from Exchange stored in PST files.</span></span> <span data-ttu-id="4d0a3-155">Los archivos PDF redactados no se pueden incluir con esta opción.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-155">Redacted PDF files cannot be included with this option.</span></span> <span data-ttu-id="4d0a3-156">Si se selecciona un archivo adjunto en el conjunto de revisión, el correo electrónico primario se exportará con los datos adjuntos adjuntos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-156">If an attachment is selected in the review set, the parent email will be exported with the attachment attached.</span></span>
  
  - <span data-ttu-id="4d0a3-157">SharePoint: esta carpeta contiene todo el contenido nativo de SharePoint en un formato de archivo nativo.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-157">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="4d0a3-158">Los archivos PDF redactados no se pueden incluir con esta opción.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-158">Redacted PDF files cannot be included with this option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="4d0a3-159">Estructura de directorio condensada</span><span class="sxs-lookup"><span data-stu-id="4d0a3-159">Condensed directory structure</span></span>

- <span data-ttu-id="4d0a3-160">Summary.csv: incluye un resumen del contenido exportado desde el conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="4d0a3-160">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="4d0a3-161">Carpeta raíz: esta carpeta en el nombre [Export Name] x de z.zip y se repetirá para cada partición de archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-161">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="4d0a3-162">Export_load_file_x de z.csv: el archivo de metadatos y también incluye la ubicación de cada archivo almacenado en el archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-162">Export_load_file_x of z.csv: The metadata file and also includes the location of each file that is stored in the ZIP file.</span></span>
  
  - <span data-ttu-id="4d0a3-163">Advertencias y errores x de z.csv: este archivo incluye información sobre los errores detectados al intentar exportar desde el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-163">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>

  - <span data-ttu-id="4d0a3-164">NativeFiles: esta carpeta contiene todos los archivos nativos que se exportaron.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-164">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="4d0a3-165">Los archivos nativos se reemplazan por archivos PDF redactados si ha seleccionado la opción Reemplazar *nativos* redactados con ARCHIVOS PDF convertidos.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-165">Natives files are replaced with redacted PDFs if you selected the *Replace redacted natives with converted PDFs* option.</span></span>
  
  - <span data-ttu-id="4d0a3-166">Error_files: esta carpeta contiene archivos que tuvieron un error de extracción u otro procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-166">Error_files: This folder contains files that had either extraction or other processing error.</span></span> <span data-ttu-id="4d0a3-167">Los archivos se colocarán en carpetas independientes, ya sea ExtractionError o ProcessingError.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-167">The files will be placed into separate folders, either ExtractionError or ProcessingError.</span></span> <span data-ttu-id="4d0a3-168">Estos archivos se enumeran en el archivo de carga.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-168">These files are listed in the load file.</span></span>

  - <span data-ttu-id="4d0a3-169">Extracted_text_files: esta carpeta contiene todos los archivos de texto extraídos que se generaron durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a><span data-ttu-id="4d0a3-170">Estructura de directorio condensada exportada a Azure Storage cuenta</span><span class="sxs-lookup"><span data-stu-id="4d0a3-170">Condensed directory structure exported to your Azure Storage Account</span></span>

<span data-ttu-id="4d0a3-171">Esta opción usa la misma estructura general que la estructura de directorio condensada, pero el contenido no está comprimido y los datos se guardan en su Azure Storage cuenta.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-171">This option uses the same general structure as the *Condensed directory structure*, however the contents is not zipped and the data is saved to your Azure Storage account.</span></span> <span data-ttu-id="4d0a3-172">Esta opción se usa generalmente al trabajar con un proveedor de exhibición de documentos electrónicos de terceros.</span><span class="sxs-lookup"><span data-stu-id="4d0a3-172">This option is generally used when working with a third-party eDiscovery provider.</span></span> <span data-ttu-id="4d0a3-173">Para obtener más información sobre cómo usar esta opción, vea Exportar documentos en una revisión [establecida en una cuenta Azure Storage .](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="4d0a3-173">For details about how to use this option, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>
