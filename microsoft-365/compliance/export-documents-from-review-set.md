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
description: Obtenga información sobre cómo seleccionar y exportar contenido de un conjunto de revisión avanzada de exhibición de documentos electrónicos para presentaciones o revisiones externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581024"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="2b642-103">Exportar documentos desde un conjunto de revisión en exhibición de documentos electrónicos avanzada</span><span class="sxs-lookup"><span data-stu-id="2b642-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="2b642-104">La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga al exportar el documento de un conjunto de revisión de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="2b642-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="2b642-105">Para exportar documentos de un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="2b642-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="2b642-106">En el Centro de cumplimiento de Microsoft 365,  abra el caso eDiscovery avanzado, seleccione la pestaña Conjuntos de revisión y, a continuación, seleccione el conjunto de opiniones que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="2b642-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="2b642-107">En el conjunto de revisión, haga clic **en Exportar**  >  **acción**.</span><span class="sxs-lookup"><span data-stu-id="2b642-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="2b642-108">La herramienta Exportar muestra la página desplegable con la configuración para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="2b642-109">Algunas opciones están seleccionadas de forma predeterminada, pero puede cambiar estas opciones.</span><span class="sxs-lookup"><span data-stu-id="2b642-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="2b642-110">Consulte la siguiente sección para obtener descripciones de las opciones de exportación que puede configurar.</span><span class="sxs-lookup"><span data-stu-id="2b642-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Opciones de configuración para exportar elementos de un conjunto de revisión](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="2b642-112">Después de configurar la exportación, haga clic **en Exportar** para iniciar el proceso de exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="2b642-113">Según la opción seleccionada  en la sección Opciones de salida, puede tener acceso a los archivos de exportación mediante descarga directa o en la cuenta de Azure Storage de su organización.</span><span class="sxs-lookup"><span data-stu-id="2b642-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="2b642-114">Los trabajos de exportación se conservan durante la duración del caso.</span><span class="sxs-lookup"><span data-stu-id="2b642-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="2b642-115">Sin embargo, debe descargar el contenido de un trabajo de exportación en un plazo de 30 días después de que se complete el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="2b642-116">Opciones de exportación</span><span class="sxs-lookup"><span data-stu-id="2b642-116">Export options</span></span>

<span data-ttu-id="2b642-117">Use las siguientes opciones para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="2b642-118">**Nombre de exportación:** nombre del trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="2b642-119">**Descripción:** campo de texto libre para agregar una descripción.</span><span class="sxs-lookup"><span data-stu-id="2b642-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="2b642-120">**Exportar estos documentos**</span><span class="sxs-lookup"><span data-stu-id="2b642-120">**Export these documents**</span></span>

  - <span data-ttu-id="2b642-121">**Solo documentos seleccionados:** esta opción exporta solo los documentos seleccionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="2b642-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="2b642-122">**Todos los documentos del conjunto de revisión:** esta opción exporta todos los documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2b642-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="2b642-123">**Metadatos**</span><span class="sxs-lookup"><span data-stu-id="2b642-123">**Metadata**</span></span>
  
  - <span data-ttu-id="2b642-124">**Cargar archivo:** este archivo contiene metadatos para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="2b642-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="2b642-125">Este archivo normalmente puede ser ingerido por herramientas de exhibición de documentos electrónicos de terceros.</span><span class="sxs-lookup"><span data-stu-id="2b642-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="2b642-126">Para obtener más información acerca de los campos que se incluyen, vea [Campos de metadatos de documento en Exhibición de documentos electrónicos avanzada.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="2b642-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="2b642-127">**Etiquetas:** cuando se selecciona, la información de etiquetado se incluye en el archivo de carga.</span><span class="sxs-lookup"><span data-stu-id="2b642-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="2b642-128">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="2b642-128">**Content**</span></span>
  
  - <span data-ttu-id="2b642-129">**Archivos nativos:** active esta casilla para incluir los archivos nativos de los documentos en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="2b642-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="2b642-130">Si elige exportar archivos nativos, tiene las siguientes opciones para exportar conversaciones de chat.</span><span class="sxs-lookup"><span data-stu-id="2b642-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="2b642-131">**Opciones de conversación**</span><span class="sxs-lookup"><span data-stu-id="2b642-131">**Conversation options**</span></span>

    - <span data-ttu-id="2b642-132">**Archivos de conversación:** esta opción exporta conversaciones de chat reconstruidas.</span><span class="sxs-lookup"><span data-stu-id="2b642-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="2b642-133">Este formato presenta conversaciones en un formulario que se asemeja a lo que los usuarios ven en la aplicación nativa.</span><span class="sxs-lookup"><span data-stu-id="2b642-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="2b642-134">**Mensajes de chat individuales:** esta opción exporta los archivos de conversación originales a medida que se almacenan en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b642-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="2b642-135">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="2b642-135">**Options**</span></span>

  - <span data-ttu-id="2b642-136">**Archivos de** texto: esta opción incluye las versiones de texto extraídas de los archivos nativos en la exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="2b642-137">**Reemplace los nativos redactados por archivos PDF convertidos:** si los archivos PDF redactados se generan durante la revisión, estos archivos están disponibles para la exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="2b642-138">Puede elegir exportar solo los archivos nativos que se han redactado (no seleccionando esta opción) o puede seleccionar esta opción para exportar los archivos PDF que contienen las redacciones reales.</span><span class="sxs-lookup"><span data-stu-id="2b642-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="2b642-139">**Opciones de** salida: el contenido exportado está disponible para su descarga directamente a través de un explorador web o se puede enviar a una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2b642-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="2b642-140">Las dos primeras opciones habilitan la descarga directa.</span><span class="sxs-lookup"><span data-stu-id="2b642-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="2b642-141">**Archivos sueltos y PST (el** correo electrónico se agrega a los PST cuando es posible): los archivos se exportan en un formato similar a la estructura de directorio original que ven los usuarios en sus aplicaciones nativas.</span><span class="sxs-lookup"><span data-stu-id="2b642-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="2b642-142">Para obtener más información, vea [la sección Archivos sueltos y estructura de exportación de PST.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="2b642-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="2b642-143">**Estructura de directorio condensada:** los archivos se exportan e incluyen en la descarga.</span><span class="sxs-lookup"><span data-stu-id="2b642-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="2b642-144">**Estructura de directorio condensada exportada a su** cuenta de Azure Storage: los archivos se exportan a la cuenta de Azure Storage de su organización.</span><span class="sxs-lookup"><span data-stu-id="2b642-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="2b642-145">Para esta opción, debe proporcionar la dirección URL del contenedor en su cuenta de Azure Storage para exportar los archivos.</span><span class="sxs-lookup"><span data-stu-id="2b642-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="2b642-146">También debe proporcionar el token de firma de acceso compartido (SAS) para su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2b642-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="2b642-147">Para obtener más información, vea [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2b642-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="2b642-148">En las secciones siguientes se describe la estructura de carpetas para archivos sueltos y opciones de estructura de directorios condensadas.</span><span class="sxs-lookup"><span data-stu-id="2b642-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="2b642-149">Archivos sueltos y estructura de exportación de PST</span><span class="sxs-lookup"><span data-stu-id="2b642-149">Loose files and PST export structure</span></span>

<span data-ttu-id="2b642-150">Si selecciona esta opción de exportación, el contenido exportado se organiza en la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="2b642-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="2b642-151">Carpeta raíz: esta carpeta en el nombre ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="2b642-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="2b642-152">Export_load_file.csv: el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2b642-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="2b642-153">Summary.csv: un archivo de resumen que también contiene estadísticas de exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="2b642-154">Exchange: esta carpeta contiene todo el contenido de Exchange en formato de archivo nativo.</span><span class="sxs-lookup"><span data-stu-id="2b642-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="2b642-155">Los archivos nativos se reemplazan por archivos PDF redactados si ha seleccionado la opción Reemplazar **nativos** redactados con ARCHIVOS PDF convertidos.</span><span class="sxs-lookup"><span data-stu-id="2b642-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="2b642-156">SharePoint: esta carpeta contiene todo el contenido nativo de SharePoint en un formato de archivo nativo.</span><span class="sxs-lookup"><span data-stu-id="2b642-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="2b642-157">Los archivos nativos se reemplazan por archivos PDF redactados si ha seleccionado la opción Reemplazar **nativos** redactados con ARCHIVOS PDF convertidos.</span><span class="sxs-lookup"><span data-stu-id="2b642-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="2b642-158">Estructura de directorio condensada</span><span class="sxs-lookup"><span data-stu-id="2b642-158">Condensed directory structure</span></span>

- <span data-ttu-id="2b642-159">Carpeta raíz: esta carpeta se denomina ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="2b642-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="2b642-160">Export_load_file.csv: el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2b642-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="2b642-161">Summary.txt: un archivo de resumen que también contiene estadísticas de exportación.</span><span class="sxs-lookup"><span data-stu-id="2b642-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="2b642-162">NativeFiles: esta carpeta contiene todos los archivos nativos que se exportaron.</span><span class="sxs-lookup"><span data-stu-id="2b642-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="2b642-163">Si exporta archivos PDF redactados, no se colocarán en archivos PST.</span><span class="sxs-lookup"><span data-stu-id="2b642-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="2b642-164">En su lugar, se agregan a una carpeta separada.</span><span class="sxs-lookup"><span data-stu-id="2b642-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="2b642-165">Error_files: esta carpeta contiene los siguientes archivos de error, si se incluyen en la exportación:</span><span class="sxs-lookup"><span data-stu-id="2b642-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="2b642-166">ExtractionError: un archivo CSV que contiene los metadatos disponibles de archivos que no se extrajeron correctamente de los archivos primarios.</span><span class="sxs-lookup"><span data-stu-id="2b642-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="2b642-167">ProcessingError: este archivo contiene una lista de documentos con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2b642-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="2b642-168">Este contenido es de nivel de elemento, lo que significa que si un archivo adjunto produjo un error de procesamiento, el mensaje de correo electrónico que contiene los datos adjuntos se incluye en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="2b642-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="2b642-169">Extracted_text_files: esta carpeta contiene todos los archivos de texto extraídos que se generaron durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2b642-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
