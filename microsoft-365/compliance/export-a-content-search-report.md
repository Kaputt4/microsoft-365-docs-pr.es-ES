---
title: Exportar un informe de búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: En lugar de exportar los resultados reales de una búsqueda de contenido en el Centro de seguridad & cumplimiento en Office 365, puede exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de la búsqueda y un documento con información detallada sobre cada elemento que se exportaría.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311578"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="0ec63-104">Exportar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="0ec63-104">Export a Content search report</span></span>

<span data-ttu-id="0ec63-105">En lugar de exportar el conjunto completo de resultados de búsqueda desde una búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 (o desde una búsqueda asociada a un caso de exhibición de documentos electrónicos principal), puede exportar los mismos informes que se generan al exportar los resultados de búsqueda reales.</span><span class="sxs-lookup"><span data-stu-id="0ec63-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="0ec63-106">Al exportar un informe, los archivos de informe se descargan en una carpeta del equipo local que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="0ec63-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="0ec63-107">Por ejemplo, si la búsqueda de contenido se denomina  *ContosoCase0815*, el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="0ec63-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="0ec63-108">Para obtener una lista de los documentos que se incluyen en el informe, vea [What's included in the report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="0ec63-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="0ec63-109">Antes de exportar un informe de búsqueda</span><span class="sxs-lookup"><span data-stu-id="0ec63-109">Before you export a search report</span></span>

- <span data-ttu-id="0ec63-110">Para exportar un informe de búsqueda, debe tener asignado el rol de administración Búsqueda de cumplimiento en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0ec63-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="0ec63-111">Este rol se asigna de forma predeterminada a los grupos de roles integrados eDiscovery Manager y Organization Management.</span><span class="sxs-lookup"><span data-stu-id="0ec63-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="0ec63-112">Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0ec63-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="0ec63-113">Al exportar un informe, los datos se almacenan temporalmente en una ubicación Azure Storage en la nube de Microsoft antes de que se descarguen en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="0ec63-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="0ec63-114">Asegúrese de que su organización puede conectarse al punto de conexión de Azure, que **\* es .blob.core.windows.net** (el comodín representa un identificador único para la exportación).</span><span class="sxs-lookup"><span data-stu-id="0ec63-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="0ec63-115">Los datos de resultados de búsqueda se eliminan de la Azure Storage dos semanas después de su creación.</span><span class="sxs-lookup"><span data-stu-id="0ec63-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="0ec63-116">El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:</span><span class="sxs-lookup"><span data-stu-id="0ec63-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="0ec63-117">Versión más reciente de Windows (32 bits o 64 bits)</span><span class="sxs-lookup"><span data-stu-id="0ec63-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="0ec63-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="0ec63-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="0ec63-119">Debe usar uno de los siguientes exploradores compatibles para ejecutar la herramienta de exportación de exhibición de documentos<sup>electrónicos 1</sup>:</span><span class="sxs-lookup"><span data-stu-id="0ec63-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="0ec63-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ec63-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="0ec63-121">O</span><span class="sxs-lookup"><span data-stu-id="0ec63-121">OR</span></span>

  - <span data-ttu-id="0ec63-122">Microsoft Internet Explorer 10 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0ec63-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="0ec63-123"><sup>1</sup> Microsoft no fabrica extensiones de terceros ni complementos para ClickOnce aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0ec63-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="0ec63-124">No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con extensiones o complementos de terceros.</span><span class="sxs-lookup"><span data-stu-id="0ec63-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="0ec63-125"><sup>2</sup> Como resultado de los cambios recientes en Microsoft Edge, ClickOnce soporte técnico ya no está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0ec63-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="0ec63-126">Para obtener instrucciones sobre cómo ClickOnce compatibilidad en Edge, vea [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="0ec63-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="0ec63-127">Si el tamaño total estimado de los resultados devueltos por la búsqueda supera los 2 TB, se produce un error al exportar los informes.</span><span class="sxs-lookup"><span data-stu-id="0ec63-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="0ec63-128">Para exportar correctamente los informes, intente restringir el ámbito y volver a ejecutar la búsqueda para que el tamaño estimado de los resultados sea inferior a 2 TB.</span><span class="sxs-lookup"><span data-stu-id="0ec63-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="0ec63-129">Si los resultados de una búsqueda tienen más de 7 días y envía un trabajo de informe de exportación, se muestra un mensaje de error que le pedirá que vuelva a ejecutar la búsqueda para actualizar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0ec63-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="0ec63-130">Si esto sucede, cancele la exportación, vuelva a ejecutar la búsqueda y vuelva a iniciar la exportación.</span><span class="sxs-lookup"><span data-stu-id="0ec63-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="0ec63-131">La exportación de informes de búsqueda cuenta con el número máximo de exportaciones que se ejecutan al mismo tiempo y el número máximo de exportaciones que puede ejecutar un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="0ec63-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="0ec63-132">Para obtener más información acerca de los límites de exportación, vea [Export Content search results](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="0ec63-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="0ec63-133">Paso 1: Generar el informe para exportar</span><span class="sxs-lookup"><span data-stu-id="0ec63-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="0ec63-134">El primer paso es preparar el informe para su descarga en el equipo que exporta.</span><span class="sxs-lookup"><span data-stu-id="0ec63-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="0ec63-135">Al exportar el informe, los documentos del informe se cargan en un área Azure Storage en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ec63-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="0ec63-136">En el Microsoft 365 de cumplimiento, seleccione la búsqueda de contenido desde la que desea exportar el informe.</span><span class="sxs-lookup"><span data-stu-id="0ec63-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="0ec63-137">En el **menú** Acciones de la parte inferior de la página desplegable de búsqueda, haga clic **en Exportar informe**.</span><span class="sxs-lookup"><span data-stu-id="0ec63-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![Opción Exportar informe en el menú Acciones](../media/ActionMenuExportReport.png)

   <span data-ttu-id="0ec63-139">Se **muestra la página** desplegable Exportar informe.</span><span class="sxs-lookup"><span data-stu-id="0ec63-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="0ec63-140">Las opciones de informe de exportación disponibles para exportar información sobre la búsqueda dependen de si los resultados de la búsqueda se encuentran en buzones o sitios o en una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="0ec63-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="0ec63-141">En **Opciones de salida,** elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0ec63-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![Exportar opciones de salida](../media/ExportOutputOptions.png)

    - <span data-ttu-id="0ec63-143">Todos los elementos, excepto los que tienen formato no reconocido, se cifran o no se **indizan por otras razones.**</span><span class="sxs-lookup"><span data-stu-id="0ec63-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="0ec63-144">Esta opción solo exporta información sobre elementos indizados.</span><span class="sxs-lookup"><span data-stu-id="0ec63-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="0ec63-145">**Todos los elementos, incluidos** los que tienen formato no reconocido, se cifran o no se indizan por otros motivos.</span><span class="sxs-lookup"><span data-stu-id="0ec63-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="0ec63-146">Esta opción exporta información sobre elementos indexados y no indexados.</span><span class="sxs-lookup"><span data-stu-id="0ec63-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="0ec63-147">Solo los elementos que tienen un formato no reconocido, se cifran **o no se indizan por otras razones**.</span><span class="sxs-lookup"><span data-stu-id="0ec63-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="0ec63-148">Esta opción solo exporta información sobre elementos no indexados.</span><span class="sxs-lookup"><span data-stu-id="0ec63-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="0ec63-149">Configure la **opción Habilitar desduplicación para Exchange contenido.**</span><span class="sxs-lookup"><span data-stu-id="0ec63-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="0ec63-150">Si selecciona esta opción, el recuento de mensajes duplicados (antes de la desduplicación y después de la desduplicación) se incluye en el informe de resumen de exportación.</span><span class="sxs-lookup"><span data-stu-id="0ec63-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="0ec63-151">Además, solo se incluirá una copia de un mensaje en el manifest.xml archivo.</span><span class="sxs-lookup"><span data-stu-id="0ec63-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="0ec63-152">Pero el informe de resultados de exportación contendrá una fila para cada copia de un mensaje duplicado de modo que pueda identificar los buzones que contienen una copia del mensaje duplicado.</span><span class="sxs-lookup"><span data-stu-id="0ec63-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="0ec63-153">Para obtener más información acerca de los informes exportados, vea [What's included in the report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="0ec63-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="0ec63-154">Si no selecciona esta opción, los informes de exportación contendrán información sobre todos los mensajes devueltos por la búsqueda, incluidos los duplicados.</span><span class="sxs-lookup"><span data-stu-id="0ec63-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="0ec63-155">Para obtener más información sobre la desduplicación y cómo se identifican los elementos duplicados, vea [Desduplicación en](de-duplication-in-ediscovery-search-results.md)los resultados de búsqueda de exhibición de documentos electrónicos .</span><span class="sxs-lookup"><span data-stu-id="0ec63-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="0ec63-156">Haga clic **en Generar informe**.</span><span class="sxs-lookup"><span data-stu-id="0ec63-156">Click **Generate report**.</span></span>

   <span data-ttu-id="0ec63-157">Los informes de búsqueda están preparados para su descarga, lo que significa que los documentos del informe se cargan en una Azure Storage en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ec63-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="0ec63-158">Esto podría llevar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="0ec63-158">This may take several minutes.</span></span>

<span data-ttu-id="0ec63-159">Consulte la siguiente sección para obtener instrucciones para descargar los informes de búsqueda exportados.</span><span class="sxs-lookup"><span data-stu-id="0ec63-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="0ec63-160">Paso 2: Descargar el informe</span><span class="sxs-lookup"><span data-stu-id="0ec63-160">Step 2: Download the report</span></span>

<span data-ttu-id="0ec63-161">El siguiente paso es descargar el informe del área Azure Storage en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="0ec63-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="0ec63-162">En la **página Búsqueda de contenido** del Centro de Microsoft 365 cumplimiento, seleccione la **pestaña** Exportar</span><span class="sxs-lookup"><span data-stu-id="0ec63-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="0ec63-163">Es posible que tenga que hacer clic **en Actualizar** para actualizar la lista de trabajos de exportación para que muestre el trabajo de exportación que creó.</span><span class="sxs-lookup"><span data-stu-id="0ec63-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="0ec63-164">Los trabajos de informe de exportación tienen el mismo nombre que la búsqueda correspondiente **con _ReportsOnly** anexado al nombre de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0ec63-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="0ec63-165">Seleccione el trabajo de exportación que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0ec63-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="0ec63-166">En la **página Exportar control** desplegable del informe en Exportar **clave**, haga clic en Copiar en **el Portapapeles.**</span><span class="sxs-lookup"><span data-stu-id="0ec63-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="0ec63-167">Esta clave se usa en el paso 6 para descargar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0ec63-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="0ec63-168">Dado que cualquier persona puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, usar esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave del mismo manera que protegería las contraseñas u otra información relacionada con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0ec63-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="0ec63-169">En la parte superior de la página desplegable, haga clic **en Descargar resultados**.</span><span class="sxs-lookup"><span data-stu-id="0ec63-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="0ec63-170">Si se le pide que instale la herramienta de exportación **de exhibición** de documentos electrónicos, haga clic **en Instalar**.</span><span class="sxs-lookup"><span data-stu-id="0ec63-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="0ec63-171">En la **herramienta de exportación de exhibición de** documentos electrónicos , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ec63-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![Herramienta de exportación de eDiscovery](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="0ec63-173">Pegue la clave de exportación que copió en el paso 3 en el cuadro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0ec63-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="0ec63-174">Haga **clic en** Examinar para especificar la ubicación en la que desea descargar los archivos de informe de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0ec63-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="0ec63-175">Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0ec63-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="0ec63-176">La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar.</span><span class="sxs-lookup"><span data-stu-id="0ec63-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="0ec63-177">Cuando el proceso de exportación se completa, puede acceder a los archivos en la ubicación donde se descargaron.</span><span class="sxs-lookup"><span data-stu-id="0ec63-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="0ec63-178">Lo que se incluye en el informe</span><span class="sxs-lookup"><span data-stu-id="0ec63-178">What's included in the report</span></span>

<span data-ttu-id="0ec63-179">Al generar y exportar un informe sobre los resultados de una búsqueda de contenido, se descargan los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="0ec63-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="0ec63-180">**Resumen de exportación:** Un Excel que contiene un resumen de la exportación.</span><span class="sxs-lookup"><span data-stu-id="0ec63-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="0ec63-181">Esto incluye información como el número de orígenes de contenido que se buscaron, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se exportarían y el tamaño estimado y real de los elementos que se exportarían.</span><span class="sxs-lookup"><span data-stu-id="0ec63-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="0ec63-182">Si incluye elementos no indexados al exportar el informe, el número de elementos sin indexar se incluye en el número total de resultados de búsqueda estimados y en el número total de resultados de búsqueda descargados (si desea exportar los resultados de búsqueda) que aparecen en el informe de resumen de exportación.</span><span class="sxs-lookup"><span data-stu-id="0ec63-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="0ec63-183">En otras palabras, el número total de elementos que se descargarían es igual al número total de resultados estimados y al número total de elementos no indexados.</span><span class="sxs-lookup"><span data-stu-id="0ec63-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="0ec63-184">**Manifiesto:** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0ec63-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="0ec63-185">Si ha habilitado la opción de desduplicación, el mensaje duplicado no se incluye en el archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="0ec63-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="0ec63-186">**Resultados:** Un Excel que contiene una fila con información sobre cada elemento indizado que se exportaría con los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0ec63-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="0ec63-187">Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos:</span><span class="sxs-lookup"><span data-stu-id="0ec63-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="0ec63-188">La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).</span><span class="sxs-lookup"><span data-stu-id="0ec63-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="0ec63-189">La fecha en que se envió o se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0ec63-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="0ec63-190">La línea Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0ec63-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="0ec63-191">El remitente y los destinatarios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0ec63-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="0ec63-192">Para los documentos de SharePoint y OneDrive para la Empresa, el registro de resultados contiene información sobre cada documento, incluidos:</span><span class="sxs-lookup"><span data-stu-id="0ec63-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="0ec63-193">La dirección URL del documento.</span><span class="sxs-lookup"><span data-stu-id="0ec63-193">The URL for the document.</span></span>

  - <span data-ttu-id="0ec63-194">La dirección URL de la colección de sitio donde se ubica el documento.</span><span class="sxs-lookup"><span data-stu-id="0ec63-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="0ec63-195">La fecha en la que el documento se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="0ec63-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="0ec63-196">El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).</span><span class="sxs-lookup"><span data-stu-id="0ec63-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="0ec63-197">El número de filas del informe **de** resultados debe ser igual al número total de resultados de búsqueda menos el número total de elementos enumerados en el informe **Elementos sin** indizar.</span><span class="sxs-lookup"><span data-stu-id="0ec63-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="0ec63-198">**Trace.log:** un registro de seguimiento que contiene información de registro detallada sobre el proceso de exportación y puede ayudar a descubrir problemas durante la exportación.</span><span class="sxs-lookup"><span data-stu-id="0ec63-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="0ec63-199">Si abre un vale con el Soporte técnico de Microsoft sobre un problema relacionado con la exportación de informes de búsqueda, es posible que se le pida que proporcione este registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0ec63-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="0ec63-200">**Elementos sin indizar:** Un Excel que contiene información sobre los elementos no indexados incluidos en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0ec63-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="0ec63-201">Si no incluye elementos sin indizar al generar el informe de resultados de búsqueda, este informe se seguirá descargando, pero estará vacío.</span><span class="sxs-lookup"><span data-stu-id="0ec63-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
