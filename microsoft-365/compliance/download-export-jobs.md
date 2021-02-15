---
title: Descargar trabajos de exportación para un caso de eDiscovery avanzado
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Instale y use el Explorador de Azure Storage para descargar documentos exportados desde un conjunto de revisión en eDiscovery avanzado.
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751297"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="74fb3-103">Descargar trabajos de exportación en un caso de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="74fb3-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="74fb3-104">Al exportar documentos de un conjunto de revisión en un caso de eDiscovery avanzado, los documentos se cargan en una ubicación de Azure Storage proporcionada por Microsoft o en una ubicación de Azure Storage administrada por su organización.</span><span class="sxs-lookup"><span data-stu-id="74fb3-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="74fb3-105">El tipo de ubicación de Azure Storage usada depende de la opción seleccionada cuando se exportaron los documentos.</span><span class="sxs-lookup"><span data-stu-id="74fb3-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="74fb3-106">En este artículo se proporcionan instrucciones sobre cómo usar microsoft Azure Storage Explorer para conectarse a una ubicación de Azure Storage para examinar y descargar los documentos exportados.</span><span class="sxs-lookup"><span data-stu-id="74fb3-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="74fb3-107">Para obtener más información acerca de Azure Storage Explorer, vea [Inicio rápido: Usar Azure Storage Explorer.](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="74fb3-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="74fb3-108">Paso 1: Instalar el Explorador de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="74fb3-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="74fb3-109">El primer paso es descargar e instalar el Explorador de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="74fb3-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="74fb3-110">Para obtener instrucciones, vea [la herramienta Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span><span class="sxs-lookup"><span data-stu-id="74fb3-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="74fb3-111">Use esta herramienta para conectarse a los documentos exportados y descargarlos en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="74fb3-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="74fb3-112">Paso 2: Obtener la dirección URL de SAS del trabajo de exportación</span><span class="sxs-lookup"><span data-stu-id="74fb3-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="74fb3-113">El siguiente paso es obtener la dirección URL de firma de acceso compartido (SAS) que se genera al crear el trabajo de exportación para exportar documentos [de un conjunto de revisión.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="74fb3-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="74fb3-114">Puede copiar la dirección URL de SAS de los documentos que se cargan en una ubicación de Azure Storage proporcionada por Microsoft o en una ubicación de Azure Storage administrada por su organización.</span><span class="sxs-lookup"><span data-stu-id="74fb3-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="74fb3-115">En cualquier caso, se usa la dirección URL de SAS para conectarse a la ubicación de Azure Storage en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="74fb3-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="74fb3-116">En la **página eDiscovery avanzado,** vaya al caso y, a continuación, haga clic en la **pestaña** Exportaciones.</span><span class="sxs-lookup"><span data-stu-id="74fb3-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="74fb3-117">En la **pestaña Exportaciones,** haga clic en el trabajo de exportación que desea descargar.</span><span class="sxs-lookup"><span data-stu-id="74fb3-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="74fb3-118">En la página desplegable, en **Ubicaciones,** copie la dirección URL de SAS que se muestra.</span><span class="sxs-lookup"><span data-stu-id="74fb3-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="74fb3-119">Si es necesario, puede guardarlo en un archivo para que pueda acceder a él en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="74fb3-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![Copiar la dirección URL de SAS mostrada en Ubicaciones](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="74fb3-121">Paso 3: Conectarse a la ubicación de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="74fb3-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="74fb3-122">El último paso es usar el Explorador de Azure Storage y la dirección URL de SAS para conectarse a la ubicación de Azure Storage y descargar los documentos que exportó a un equipo local.</span><span class="sxs-lookup"><span data-stu-id="74fb3-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="74fb3-123">Abra el Explorador de Azure Storage que instaló en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="74fb3-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="74fb3-124">Haga clic en **el icono Agregar** cuenta.</span><span class="sxs-lookup"><span data-stu-id="74fb3-124">Click the **Add account** icon.</span></span> <span data-ttu-id="74fb3-125">Como alternativa, puede hacer clic con el botón secundario en **Cuentas de almacenamiento.**</span><span class="sxs-lookup"><span data-stu-id="74fb3-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![Haga clic en el icono Agregar cuenta](../media/AzureStorageConnect.png)

3. <span data-ttu-id="74fb3-127">En la **página Conectarse** a Azure Storage, haga clic en Usar un URI de firma de acceso compartido **(SAS)** y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="74fb3-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![Haga clic en Usar un URI de firma de acceso compartido (SAS) y, a continuación, haga clic en Siguiente](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="74fb3-129">En la página Adjuntar con URI de **SAS,** haga clic en el cuadro uri y, a continuación, pegue la dirección URL de SAS que obtuvo en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="74fb3-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![Pegar la dirección URL de SAS en el cuadro uri](../media/AzureStorageConnect3.png)

    <span data-ttu-id="74fb3-131">Observe que una parte de la dirección URL de SAS se muestra en el **cuadro Nombre para** mostrar.</span><span class="sxs-lookup"><span data-stu-id="74fb3-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="74fb3-132">Se usará como el nombre para mostrar del contenedor  que se crea en las cuentas de almacenamiento después de conectarse a la ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74fb3-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="74fb3-133">Este nombre consta del identificador del caso de eDiscovery avanzado y un identificador único.</span><span class="sxs-lookup"><span data-stu-id="74fb3-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="74fb3-134">Puede conservar el nombre para mostrar predeterminado o cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="74fb3-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="74fb3-135">Si lo cambia, el nombre para mostrar debe ser único.</span><span class="sxs-lookup"><span data-stu-id="74fb3-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="74fb3-136">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="74fb3-136">Click **Next**.</span></span>

    <span data-ttu-id="74fb3-137">Se **muestra la página Resumen** de conexión.</span><span class="sxs-lookup"><span data-stu-id="74fb3-137">The **Connection summary** page is displayed.</span></span>

    ![Haga clic en Conectar en la página Resumen de conexión para conectarse a la ubicación de Azure Storage](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="74fb3-139">En la **página Resumen de conexión,** revise la información de conexión y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="74fb3-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="74fb3-140">Se **abre el nodo Contenedores** de blobs (en Cuentas **de**  >  **almacenamiento (contenedores adjuntos).** \></span><span class="sxs-lookup"><span data-stu-id="74fb3-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Exportar trabajos en el nodo contenedores blobs](../media/AzureStorageConnect5.png)

    <span data-ttu-id="74fb3-142">Contiene un contenedor con el nombre para mostrar del paso 4.</span><span class="sxs-lookup"><span data-stu-id="74fb3-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="74fb3-143">Este contenedor contiene una carpeta para cada trabajo de exportación que haya creado.</span><span class="sxs-lookup"><span data-stu-id="74fb3-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="74fb3-144">Estas carpetas se denominan con un identificador que corresponde al identificador del trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="74fb3-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="74fb3-145">Puede encontrar estos IDs de exportación (y  el nombre de la exportación) en Información de soporte técnico en la página desplegable para cada uno de los datos de preparación para el trabajo de exportación que aparecen en la pestaña **Trabajos.** </span><span class="sxs-lookup"><span data-stu-id="74fb3-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="74fb3-146">Haga doble clic en la carpeta de trabajo de exportación para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="74fb3-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="74fb3-147">Se muestra una lista de carpetas e informes de exportación.</span><span class="sxs-lookup"><span data-stu-id="74fb3-147">A list of folders and export reports is displayed.</span></span>
   
    ![La carpeta de exportación contiene archivos exportados e informes de exportación](../media/AzureStorageConnect6.png)

   <span data-ttu-id="74fb3-149">La carpeta de trabajo de exportación contiene los siguientes elementos.</span><span class="sxs-lookup"><span data-stu-id="74fb3-149">The export job folder contains the following items.</span></span> <span data-ttu-id="74fb3-150">Los elementos reales de la carpeta de exportación están determinados por las opciones de exportación configuradas cuando se creó el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="74fb3-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="74fb3-151">Para obtener más información, vea [Exportar documentos de un conjunto de revisión.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="74fb3-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="74fb3-152">Export_load_file.csv: este archivo CSV es un informe de exportación de detalles que contiene información sobre cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="74fb3-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="74fb3-153">El archivo consta de una columna para cada propiedad de metadatos de un documento.</span><span class="sxs-lookup"><span data-stu-id="74fb3-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="74fb3-154">Para obtener una lista y una descripción de los metadatos que se incluyen en este informe, vea la columna **Nombre** de campo exportado en la tabla de los campos de metadatos del documento en [eDiscovery avanzado.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="74fb3-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="74fb3-155">Summary.txt: archivo de texto que contiene un resumen de la exportación, incluidas las estadísticas de exportación.</span><span class="sxs-lookup"><span data-stu-id="74fb3-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="74fb3-156">Extracted_text_files: esta carpeta contiene una versión de archivo de texto de cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="74fb3-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="74fb3-157">NativeFiles: esta carpeta contiene una versión de archivo nativa de cada documento exportado.</span><span class="sxs-lookup"><span data-stu-id="74fb3-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="74fb3-158">Error_files: esta carpeta incluye los siguientes elementos cuando el trabajo de exportación contiene archivos de error:</span><span class="sxs-lookup"><span data-stu-id="74fb3-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="74fb3-159">ExtractionError.csv: este archivo CSV contiene los metadatos disponibles para los archivos que no se extrajeron correctamente de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="74fb3-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="74fb3-160">ProcessingError: esta carpeta contiene documentos con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="74fb3-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="74fb3-161">Este contenido se encuentra en un nivel de elemento, lo que significa que si un archivo adjunto tiene un error de procesamiento, el documento que contiene los datos adjuntos también se incluirá en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="74fb3-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="74fb3-162">Para exportar todo el contenido de la exportación, seleccione la carpeta de exportación y, a continuación, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="74fb3-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="74fb3-163">Especifique la ubicación donde desea descargar los archivos exportados y, a continuación, haga clic en Seleccionar carpeta.</span><span class="sxs-lookup"><span data-stu-id="74fb3-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="74fb3-164">El Explorador de Azure Storage inicia el proceso de exportación.</span><span class="sxs-lookup"><span data-stu-id="74fb3-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="74fb3-165">El estado de la descarga de los elementos exportados se muestra en el **panel** Actividades.</span><span class="sxs-lookup"><span data-stu-id="74fb3-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="74fb3-166">Se muestra un mensaje cuando finaliza la descarga.</span><span class="sxs-lookup"><span data-stu-id="74fb3-166">A message is displayed when the download is finished.</span></span>

    ![Se muestra un mensaje cuando finaliza la descarga](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="74fb3-168">En lugar de descargar todo el trabajo de exportación, puede seleccionar elementos específicos para descargar.</span><span class="sxs-lookup"><span data-stu-id="74fb3-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="74fb3-169">Y en lugar de descargar elementos, puede hacer doble clic en un elemento para verlo.</span><span class="sxs-lookup"><span data-stu-id="74fb3-169">And instead of downloading items, you can double-click an item to view it.</span></span>
