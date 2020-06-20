---
title: Exportar un informe de búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: En lugar de exportar los resultados reales de una búsqueda de contenido en el centro de seguridad & cumplimiento en Office 365, puede exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de la búsqueda y un documento con información detallada sobre cada elemento que se exportará.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25525a0670f31a7e962fb72f6d1559381e8b33cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817779"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="108cf-104">Exportar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="108cf-104">Export a Content Search report</span></span>

<span data-ttu-id="108cf-105">En lugar de exportar el conjunto completo de resultados de búsqueda de una búsqueda de contenido en el centro de seguridad & cumplimiento (y desde una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos), puede exportar los mismos informes que se generan al exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="108cf-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="108cf-106">Al exportar un informe, se descarga en una carpeta que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="108cf-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="108cf-107">Por ejemplo, si la búsqueda de contenido se denomina *ContosoCase0815*, el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="108cf-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="108cf-108">Para obtener una lista de los documentos que se incluyen en el informe, consulte [what's included in the Report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="108cf-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="108cf-109">Asignar roles y comprobar los requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="108cf-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="108cf-110">Para exportar un informe de búsqueda de contenido, debe tener asignado el rol de administración de búsqueda de cumplimiento en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="108cf-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="108cf-111">Este rol se asigna de forma predeterminada a los grupos de roles integrados eDiscovery Manager y administración de la organización.</span><span class="sxs-lookup"><span data-stu-id="108cf-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="108cf-112">Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="108cf-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="108cf-113">Al exportar un informe, los datos se almacenan temporalmente en un área de almacenamiento única de Azure en la nube de Microsoft antes de descargarlos en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="108cf-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="108cf-114">Asegúrese de que su organización puede conectarse al extremo en Azure, que es \*\* \* . BLOB.Core.Windows.net\*\* (el carácter comodín representa un identificador único para la exportación).</span><span class="sxs-lookup"><span data-stu-id="108cf-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="108cf-115">Los datos de los resultados de la búsqueda se eliminan del área de Azure Storage dos semanas después de su creación.</span><span class="sxs-lookup"><span data-stu-id="108cf-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="108cf-116">El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:</span><span class="sxs-lookup"><span data-stu-id="108cf-116">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="108cf-117">versiones de 32 o 64 bits de Windows 7 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="108cf-117">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="108cf-118">Microsoft .NET Framework 4,7</span><span class="sxs-lookup"><span data-stu-id="108cf-118">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="108cf-119">Debe usar uno de los siguientes exploradores compatibles para ejecutar la herramienta de exportación de exhibición de documentos electrónicos<sup>1</sup>:</span><span class="sxs-lookup"><span data-stu-id="108cf-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="108cf-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="108cf-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="108cf-121">O</span><span class="sxs-lookup"><span data-stu-id="108cf-121">OR</span></span>

  - <span data-ttu-id="108cf-122">Microsoft Internet Explorer 10 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="108cf-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="108cf-123"><sup>1</sup> Microsoft no fabrica extensiones de terceros ni complementos para aplicaciones ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="108cf-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="108cf-124">No se admite la exportación de resultados de búsqueda con un explorador no compatible con extensiones de terceros o complementos.</span><span class="sxs-lookup"><span data-stu-id="108cf-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="108cf-125"><sup>2</sup> como resultado de los últimos cambios realizados en Microsoft Edge, la compatibilidad con ClickOnce ya no está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="108cf-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="108cf-126">Para obtener instrucciones sobre cómo habilitar la compatibilidad con ClickOnce en Edge, consulte [use la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="108cf-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="108cf-127">Si el tamaño total estimado de los resultados devueltos por una búsqueda de contenido supera los 2 TB, se producirá un error al exportar el informe.</span><span class="sxs-lookup"><span data-stu-id="108cf-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="108cf-128">Para exportar correctamente el informe, intente restringir el ámbito y vuelva a ejecutar la búsqueda para que el tamaño estimado de los resultados sea inferior a 2 TB.</span><span class="sxs-lookup"><span data-stu-id="108cf-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="108cf-129">La exportación de informes de búsqueda de contenido cuenta con el número máximo de exportaciones que se ejecutan al mismo tiempo y el número máximo de exportaciones que puede ejecutar un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="108cf-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="108cf-130">Para obtener más información acerca de los límites de exportación, consulte [exportar resultados](export-search-results.md#export-limits)de la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="108cf-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="108cf-131">Generar y descargar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="108cf-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="108cf-132">Los pasos para generar y descargar un informe de búsqueda de contenido son similares a la exportación real de los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="108cf-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="108cf-133">Paso 1: generar el informe para la exportación</span><span class="sxs-lookup"><span data-stu-id="108cf-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="108cf-134">El primer paso consiste en preparar el informe para descargarlo en la exportación de su equipo.</span><span class="sxs-lookup"><span data-stu-id="108cf-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="108cf-135">Cuando se trata de un informe, los documentos del informe se cargan en un área de almacenamiento de Azure en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="108cf-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="108cf-136">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="108cf-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="108cf-137">Inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="108cf-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="108cf-138">En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en búsqueda de contenido de **búsqueda** \> **Content search**.</span><span class="sxs-lookup"><span data-stu-id="108cf-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="108cf-139">En la página **búsqueda de contenido** , seleccione una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="108cf-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="108cf-140">En el panel de detalles, en **exportar informe a un equipo**, haga clic en **generar informe**.</span><span class="sxs-lookup"><span data-stu-id="108cf-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="108cf-141">Si los resultados de una búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="108cf-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="108cf-142">Si esto ocurre, cancele la exportación, haga clic en **Actualizar resultados de búsqueda** en el panel de detalles de la búsqueda seleccionada y, a continuación, vuelva a iniciar la exportación del informe después de que se actualicen los resultados.</span><span class="sxs-lookup"><span data-stu-id="108cf-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="108cf-143">En la página **exportar un informe** , en **incluir estos elementos de la búsqueda**, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="108cf-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="108cf-144">Exportar solo los elementos indexados</span><span class="sxs-lookup"><span data-stu-id="108cf-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="108cf-145">Exportar los elementos indexados y sin indexar</span><span class="sxs-lookup"><span data-stu-id="108cf-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="108cf-146">Exportar solo los elementos sin indexar</span><span class="sxs-lookup"><span data-stu-id="108cf-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="108cf-147">Para obtener más información acerca de los elementos sin indexar, vea [elementos parcialmente indizados en la búsqueda de contenido](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="108cf-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="108cf-148">Elija incluir estadísticas de búsqueda para todas las versiones de los documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="108cf-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="108cf-149">Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen sitios de SharePoint o de OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="108cf-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="108cf-150">Haga clic en **generar informe**.</span><span class="sxs-lookup"><span data-stu-id="108cf-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="108cf-151">El informe de resultados de búsqueda está preparado para la descarga, lo que significa que los documentos del informe se cargarán en el área de almacenamiento de Azure en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="108cf-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="108cf-152">Cuando el informe está listo para la descarga, el vínculo de **descarga del informe** se muestra en **exportar informe a un equipo** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="108cf-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="108cf-153">También puede exportar un informe para una búsqueda de contenido que esté asociada a un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="108cf-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="108cf-154">**Para ello, vaya a eDiscovery** \> **eDiscovery**, seleccione un caso y haga clic en **Editar** ![ icono de edición ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="108cf-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="108cf-155">En la página **búsquedas** , seleccione una búsqueda y, a continuación, haga clic en **exportar** ![ los resultados de la búsqueda exportar ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **un informe**.</span><span class="sxs-lookup"><span data-stu-id="108cf-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="108cf-156">Paso 2: descargar el informe</span><span class="sxs-lookup"><span data-stu-id="108cf-156">Step 2: Download the report</span></span>

<span data-ttu-id="108cf-157">El siguiente paso es descargar el informe desde el área de almacenamiento de Azure a su equipo local.</span><span class="sxs-lookup"><span data-stu-id="108cf-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="108cf-158">En el panel de detalles de la búsqueda para la que generó el informe, en **exportar informe a un equipo**, haga clic en **Descargar Informe**.</span><span class="sxs-lookup"><span data-stu-id="108cf-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="108cf-159">Se muestra la página **Descargar Informe** , que contiene la siguiente información sobre el informe que se descarga en el equipo.</span><span class="sxs-lookup"><span data-stu-id="108cf-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="108cf-160">El número de elementos que se descargarán.</span><span class="sxs-lookup"><span data-stu-id="108cf-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="108cf-161">El tamaño total estimado de los elementos que se descargarán.</span><span class="sxs-lookup"><span data-stu-id="108cf-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="108cf-162">Si los elementos indexados o sin indexar se exportarán.</span><span class="sxs-lookup"><span data-stu-id="108cf-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="108cf-163">Los elementos sin indexar son elementos que tienen un formato reconocido, están cifrados o no se indizaron por otros motivos.</span><span class="sxs-lookup"><span data-stu-id="108cf-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="108cf-164">Si se descargarán las versiones de los documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="108cf-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="108cf-165">El estado del proceso de exportación del informe.</span><span class="sxs-lookup"><span data-stu-id="108cf-165">The status of the report export process.</span></span> <span data-ttu-id="108cf-166">Puede iniciar la descarga del informe incluso si no se ha completado la preparación del informe.</span><span class="sxs-lookup"><span data-stu-id="108cf-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="108cf-167">En **Clave de exportación**, haga clic en **Copiar al Portapapeles**.</span><span class="sxs-lookup"><span data-stu-id="108cf-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="108cf-168">Use esta clave en el paso 5 para descargar el informe.</span><span class="sxs-lookup"><span data-stu-id="108cf-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="108cf-169">Dado que cualquiera puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, usar esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave igual que lo haría con las contraseñas u otra información relacionada con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="108cf-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="108cf-170">Haga clic en **Descargar Informe**.</span><span class="sxs-lookup"><span data-stu-id="108cf-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="108cf-171">Si se le pide que instale la **herramienta de exportación de exhibición**de documentos electrónicos, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="108cf-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="108cf-172">En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="108cf-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="108cf-173">Haga clic en **examinar** para especificar la ubicación en la que desea descargar el informe.</span><span class="sxs-lookup"><span data-stu-id="108cf-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="108cf-174">Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo.</span><span class="sxs-lookup"><span data-stu-id="108cf-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="108cf-175">La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar.</span><span class="sxs-lookup"><span data-stu-id="108cf-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="108cf-176">Una vez finalizado el proceso de exportación, puede tener acceso a los archivos en la ubicación en la que se descargaron.</span><span class="sxs-lookup"><span data-stu-id="108cf-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="108cf-177">Puede descargar el informe para una búsqueda de contenido que esté asociada con un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="108cf-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="108cf-178">**Para ello, vaya a eDiscovery** \> **eDiscovery**, seleccione un caso y haga clic en **Editar** ![ icono de edición ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="108cf-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="108cf-179">En la página **exportaciones** , seleccione una exportación de informe y, a continuación, haga clic en **Descargar Informe** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="108cf-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="108cf-180">Contenido incluido en el informe</span><span class="sxs-lookup"><span data-stu-id="108cf-180">What's included in the report</span></span>

<span data-ttu-id="108cf-181">Cuando se genera y se exporta un informe sobre los resultados de una búsqueda de contenido, se descargan los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="108cf-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="108cf-182">**Resumen de exportación:** Un documento de Excel que contiene un resumen de la exportación.</span><span class="sxs-lookup"><span data-stu-id="108cf-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="108cf-183">Esto incluye información como el número de orígenes de contenido que se han buscado, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se exportarían y el tamaño estimado y real de los elementos que se exportaría.</span><span class="sxs-lookup"><span data-stu-id="108cf-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="108cf-184">Si incluye elementos sin indexar al exportar el informe, el número de elementos sin indexar se incluye en el número total de resultados de búsqueda estimados y en el número total de resultados de la búsqueda descargados (si se exportaron los resultados de la búsqueda) que aparecen en el informe de Resumen de exportación.</span><span class="sxs-lookup"><span data-stu-id="108cf-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="108cf-185">Es decir, el número total de elementos que se descargarán es igual al número total de resultados estimados y el número total de elementos sin indexar.</span><span class="sxs-lookup"><span data-stu-id="108cf-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="108cf-186">**Manifiesto:** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="108cf-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="108cf-187">**Resultados:** Un documento de Excel que contiene una fila con información acerca de cada elemento indizado que se exportará con los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="108cf-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="108cf-188">Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos:</span><span class="sxs-lookup"><span data-stu-id="108cf-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="108cf-189">La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).</span><span class="sxs-lookup"><span data-stu-id="108cf-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="108cf-190">La fecha en que se envió o se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="108cf-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="108cf-191">La línea Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="108cf-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="108cf-192">El remitente y los destinatarios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="108cf-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="108cf-193">Para los documentos de los sitios de SharePoint y OneDrive para la empresa, el registro de resultados contiene información sobre cada documento, incluidos:</span><span class="sxs-lookup"><span data-stu-id="108cf-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="108cf-194">La dirección URL del documento.</span><span class="sxs-lookup"><span data-stu-id="108cf-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="108cf-195">La dirección URL de la colección de sitio donde se ubica el documento.</span><span class="sxs-lookup"><span data-stu-id="108cf-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="108cf-196">La fecha en la que el documento se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="108cf-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="108cf-197">El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).</span><span class="sxs-lookup"><span data-stu-id="108cf-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="108cf-198">El número de filas en el informe de **resultados** debe ser igual al número total de resultados de búsqueda menos el número total de elementos que aparecen en el informe de **elementos sin indexar** .</span><span class="sxs-lookup"><span data-stu-id="108cf-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="108cf-199">**Elementos sin indexar:** Un documento de Excel que contiene información sobre los elementos sin indexar incluidos en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="108cf-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="108cf-200">Si no incluye elementos sin indexar al generar el informe de resultados de la búsqueda, este informe se descargará, pero estará vacío.</span><span class="sxs-lookup"><span data-stu-id="108cf-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
