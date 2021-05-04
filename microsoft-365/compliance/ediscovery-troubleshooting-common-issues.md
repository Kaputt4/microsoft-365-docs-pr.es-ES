---
title: Solución de problemas comunes de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre los pasos básicos de solución de problemas que puede seguir para resolver problemas comunes en Office 365 exhibición de documentos electrónicos.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3d3d0830ac677ea812a0d09793de8214245d6b2a
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060995"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="1adfe-103">Investigar, solucionar y resolver problemas comunes de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="1adfe-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="1adfe-104">En este tema se tratan los pasos básicos de solución de problemas que puede seguir para identificar y resolver los problemas que puede encontrar durante una búsqueda de exhibición de documentos electrónicos o en otra parte del proceso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="1adfe-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="1adfe-105">Resolver algunos de estos escenarios requiere ayuda del soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1adfe-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="1adfe-106">La información sobre cuándo ponerse en contacto con el Soporte técnico de Microsoft se incluye en los pasos de resolución.</span><span class="sxs-lookup"><span data-stu-id="1adfe-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="1adfe-107">Error/problema: Ubicación ambigua</span><span class="sxs-lookup"><span data-stu-id="1adfe-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="1adfe-108">Si intenta agregar la ubicación del buzón del usuario para buscar y hay objetos duplicados o en conflicto con el mismo userID en el directorio Exchange Online Protection (EOP), recibirá este error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="1adfe-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="1adfe-109">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-109">Resolution</span></span>

<span data-ttu-id="1adfe-110">Compruebe si hay usuarios duplicados o una lista de distribución con el mismo identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="1adfe-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="1adfe-111">Conectar [a PowerShell & Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="1adfe-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="1adfe-112">Ejecute el siguiente comando para recuperar todas las instancias del nombre de usuario:</span><span class="sxs-lookup"><span data-stu-id="1adfe-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="1adfe-113">El resultado de "useralias@contoso.com" sería similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="1adfe-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="1adfe-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="1adfe-114">Name</span></span>|<span data-ttu-id="1adfe-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="1adfe-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="1adfe-116">Alias, Usuario</span><span class="sxs-lookup"><span data-stu-id="1adfe-116">Alias, User</span></span>|<span data-ttu-id="1adfe-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="1adfe-117">MailUser</span></span>|
   > |<span data-ttu-id="1adfe-118">Alias, Usuario</span><span class="sxs-lookup"><span data-stu-id="1adfe-118">Alias, User</span></span>|<span data-ttu-id="1adfe-119">User</span><span class="sxs-lookup"><span data-stu-id="1adfe-119">User</span></span>|

3. <span data-ttu-id="1adfe-120">Si se devuelven varios usuarios, busque y corrija el objeto en conflicto.</span><span class="sxs-lookup"><span data-stu-id="1adfe-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="1adfe-121">Error o problema: error de búsqueda en ubicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="1adfe-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="1adfe-122">Una exhibición de documentos electrónicos o una búsqueda de contenido pueden producir el siguiente error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="1adfe-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Error en la captura de pantalla de error de ubicación específica de la búsqueda](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="1adfe-124">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-124">Resolution</span></span>

<span data-ttu-id="1adfe-125">Si recibe este error, se recomienda comprobar las ubicaciones que han fallado en la búsqueda y, a continuación, volver a ejecutar la búsqueda solo en las ubicaciones con errores.</span><span class="sxs-lookup"><span data-stu-id="1adfe-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="1adfe-126">Conectar [a PowerShell & Centro de](/powershell/exchange/connect-to-scc-powershell) seguridad y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1adfe-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="1adfe-127">En el resultado de PowerShell, vea las ubicaciones con errores en el campo errores o desde los detalles de estado del error desde el resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1adfe-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="1adfe-128">Reintente la búsqueda de exhibición de documentos electrónicos solo en las ubicaciones con errores.</span><span class="sxs-lookup"><span data-stu-id="1adfe-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="1adfe-129">Si sigue recibiendo estos errores, consulte [Reintentar](/Office365/SecurityCompliance/retry-failed-content-search) ubicaciones con errores para obtener más pasos de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="1adfe-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="1adfe-130">Error o problema: no se encontró el archivo</span><span class="sxs-lookup"><span data-stu-id="1adfe-130">Error/issue: File not found</span></span>

<span data-ttu-id="1adfe-131">Al ejecutar una búsqueda de exhibición de documentos electrónicos que incluye SharePoint online y una unidad para empresas, puede recibir el error aunque el archivo se encuentra `File Not Found` en el sitio.</span><span class="sxs-lookup"><span data-stu-id="1adfe-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="1adfe-132">Este error estará en las advertencias de exportación y errors.csv o omitirá items.csv.</span><span class="sxs-lookup"><span data-stu-id="1adfe-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="1adfe-133">Esto puede ocurrir si el archivo no se puede encontrar en el sitio o si el índice está desa actualizado.</span><span class="sxs-lookup"><span data-stu-id="1adfe-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="1adfe-134">Este es el texto de un error real (con énfasis agregado).</span><span class="sxs-lookup"><span data-stu-id="1adfe-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="1adfe-135">28.06.2019 10:02:19_FailedToExportItem_Failed descargar contenido.</span><span class="sxs-lookup"><span data-stu-id="1adfe-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="1adfe-136">Información de diagnóstico adicional : Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: No se pudo descargar del contenido 6ea52149-91cd-4965-b5bb-82ca6a3ec9be de tipo Document.</span><span class="sxs-lookup"><span data-stu-id="1adfe-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="1adfe-137">Identificador de correlación: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="1adfe-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="1adfe-138">ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***Archivo no encontrado***.</span><span class="sxs-lookup"><span data-stu-id="1adfe-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="1adfe-139">en Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) en Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- fin del seguimiento de la pila de excepciones ---</span><span class="sxs-lookup"><span data-stu-id="1adfe-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="1adfe-140">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-140">Resolution</span></span>

1. <span data-ttu-id="1adfe-141">Compruebe la ubicación identificada en la búsqueda para asegurarse de que la ubicación del archivo es correcta y se agrega en las ubicaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1adfe-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="1adfe-142">Use los procedimientos de solicitar manualmente el rastreo y [la re indexación](/sharepoint/crawl-site-content) de un sitio, una biblioteca o una lista para volver a indizar el sitio.</span><span class="sxs-lookup"><span data-stu-id="1adfe-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="1adfe-143">Error o problema: se produce un error en la búsqueda porque no se encuentra el destinatario</span><span class="sxs-lookup"><span data-stu-id="1adfe-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="1adfe-144">Se produce un error en una búsqueda de exhibición de documentos electrónicos con el error `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="1adfe-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="1adfe-145">Este error puede producirse si no se puede encontrar el objeto de usuario en Exchange Online Protection (EOP) porque el objeto no se ha sincronizado.</span><span class="sxs-lookup"><span data-stu-id="1adfe-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="1adfe-146">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-146">Resolution</span></span>

1. <span data-ttu-id="1adfe-147">Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1adfe-147">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="1adfe-148">Ejecute el siguiente comando para comprobar si el usuario está sincronizado con Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="1adfe-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="1adfe-149">Debe haber un objeto de usuario de correo para la pregunta de usuario.</span><span class="sxs-lookup"><span data-stu-id="1adfe-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="1adfe-150">Si no se devuelve nada, investigue el objeto de usuario.</span><span class="sxs-lookup"><span data-stu-id="1adfe-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="1adfe-151">Póngase en contacto con el soporte técnico de Microsoft si el objeto no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="1adfe-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="1adfe-152">Error o problema: Exportar resultados de búsqueda es lento</span><span class="sxs-lookup"><span data-stu-id="1adfe-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="1adfe-153">Al exportar los resultados de búsqueda desde la exhibición de documentos electrónicos o la búsqueda de contenido en el Centro de seguridad y cumplimiento, la descarga tarda más de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="1adfe-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="1adfe-154">Puede comprobar la cantidad de datos que se descargarán y, posiblemente, aumentar la velocidad de exportación.</span><span class="sxs-lookup"><span data-stu-id="1adfe-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="1adfe-155">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-155">Resolution</span></span>

1. <span data-ttu-id="1adfe-156">Conectar [a PowerShell & Centro de](/powershell/exchange/connect-to-scc-powershell) seguridad y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1adfe-156">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="1adfe-157">Busque la cantidad de datos que se descargarán en los parámetros SearchResults y SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="1adfe-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="1adfe-158">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1adfe-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="1adfe-159">En el campo de resultados, busque los datos exportados y vea los errores encontrados.</span><span class="sxs-lookup"><span data-stu-id="1adfe-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="1adfe-160">Compruebe si hay errores en el archivo trace.log ubicado en el directorio al que exportó el contenido.</span><span class="sxs-lookup"><span data-stu-id="1adfe-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="1adfe-161">Si aún tiene problemas, considere la posibilidad de dividir las búsquedas que devuelven un gran conjunto de resultados en búsquedas más pequeñas.</span><span class="sxs-lookup"><span data-stu-id="1adfe-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="1adfe-162">Por ejemplo, puede usar intervalos de fechas en las consultas de búsqueda para devolver un conjunto más pequeño de resultados que se pueden descargar más rápido.</span><span class="sxs-lookup"><span data-stu-id="1adfe-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="1adfe-163">Error o problema: "Error interno del servidor (500) producido"</span><span class="sxs-lookup"><span data-stu-id="1adfe-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="1adfe-164">Al ejecutar una búsqueda de exhibición de documentos electrónicos, si la búsqueda falla continuamente con un error similar al "Error interno del servidor (500) ocurrido", es posible que necesite volver a ejecutar la búsqueda solo en ubicaciones de buzones específicas.</span><span class="sxs-lookup"><span data-stu-id="1adfe-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Captura de pantalla de error interno del servidor 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="1adfe-166">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-166">Resolution</span></span>

1. <span data-ttu-id="1adfe-167">Divide la búsqueda en búsquedas más pequeñas y vuelve a ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="1adfe-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="1adfe-168">Intente usar un intervalo de fechas más pequeño o limite el número de ubicaciones que se buscan.</span><span class="sxs-lookup"><span data-stu-id="1adfe-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="1adfe-169">Conectar [a PowerShell & Centro de](/powershell/exchange/connect-to-scc-powershell) seguridad y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1adfe-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="1adfe-170">Examine el resultado en busca de resultados y errores.</span><span class="sxs-lookup"><span data-stu-id="1adfe-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="1adfe-171">Examine el archivo trace.log.</span><span class="sxs-lookup"><span data-stu-id="1adfe-171">Examine the trace.log file.</span></span> <span data-ttu-id="1adfe-172">Se encuentra en la misma carpeta a la que exportó los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1adfe-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="1adfe-173">Ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1adfe-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="1adfe-174">Error o problema: las retenciones no se sincronizan</span><span class="sxs-lookup"><span data-stu-id="1adfe-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="1adfe-175">Error de distribución de la directiva de retención de casos de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1adfe-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="1adfe-176">El error dice:</span><span class="sxs-lookup"><span data-stu-id="1adfe-176">The error reads:</span></span>

> <span data-ttu-id="1adfe-177">"Recursos: tarda más de lo esperado en implementar la directiva.</span><span class="sxs-lookup"><span data-stu-id="1adfe-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="1adfe-178">Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a comprobarlo en un par de horas".</span><span class="sxs-lookup"><span data-stu-id="1adfe-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="1adfe-179">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-179">Resolution</span></span>

1. <span data-ttu-id="1adfe-180">Conectar a [PowerShell del Centro de & seguridad](/powershell/exchange/connect-to-scc-powershell) y, a continuación, ejecute el siguiente comando para una retención de casos de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="1adfe-180">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="1adfe-181">Para una directiva de retención, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1adfe-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="1adfe-182">Examine el valor del parámetro DistributionDetail en busca de errores como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1adfe-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="1adfe-183">Error: Recursos: tarda más de lo esperado en implementar la directiva.</span><span class="sxs-lookup"><span data-stu-id="1adfe-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="1adfe-184">Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a comprobarlo en un par de horas".</span><span class="sxs-lookup"><span data-stu-id="1adfe-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="1adfe-185">Intente ejecutar el parámetro RetryDistribution en la directiva en cuestión:</span><span class="sxs-lookup"><span data-stu-id="1adfe-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="1adfe-186">Para las retenciones de casos de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="1adfe-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="1adfe-187">Para directivas de retención:</span><span class="sxs-lookup"><span data-stu-id="1adfe-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="1adfe-188">Ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1adfe-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="1adfe-189">Error: "No se cumple la condición especificada mediante encabezados condicionales HTTP"</span><span class="sxs-lookup"><span data-stu-id="1adfe-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="1adfe-190">Al descargar resultados de búsqueda mediante la herramienta de exportación de exhibición de documentos electrónicos, es posible que reciba el siguiente error: se trata de un error transitorio, que normalmente se produce en la `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage ubicación.</span><span class="sxs-lookup"><span data-stu-id="1adfe-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="1adfe-191">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-191">Resolution</span></span>

<span data-ttu-id="1adfe-192">Para resolver este problema, [reintente la descarga de los resultados](export-search-results.md#step-2-download-the-search-results)de la búsqueda, que reiniciará la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="1adfe-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="1adfe-193">Error o problema: la exportación descargada no muestra resultados</span><span class="sxs-lookup"><span data-stu-id="1adfe-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="1adfe-194">Después de una exportación correcta, la descarga completada a través de la herramienta de exportación muestra cero archivos en los resultados.</span><span class="sxs-lookup"><span data-stu-id="1adfe-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="1adfe-195">Solución</span><span class="sxs-lookup"><span data-stu-id="1adfe-195">Resolution</span></span>

<span data-ttu-id="1adfe-196">Este es un problema del lado cliente y, para corregirlo, intente los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1adfe-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="1adfe-197">Intente usar otro cliente o máquina para descargar.</span><span class="sxs-lookup"><span data-stu-id="1adfe-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="1adfe-198">Quite las búsquedas antiguas que ya no son necesarias con el cmdlet [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch].</span><span class="sxs-lookup"><span data-stu-id="1adfe-198">Remove old searches that are no longer needed using [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch] cmdlet.</span></span>

3. <span data-ttu-id="1adfe-199">Asegúrese de descargar en una unidad local.</span><span class="sxs-lookup"><span data-stu-id="1adfe-199">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="1adfe-200">Asegúrese de que el escáner de virus no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="1adfe-200">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="1adfe-201">Asegúrese de que ninguna otra exportación se descarga en la misma carpeta o en cualquier carpeta primaria.</span><span class="sxs-lookup"><span data-stu-id="1adfe-201">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="1adfe-202">Si los pasos anteriores no funcionaron, deshabilite la compresión y la desduplicación.</span><span class="sxs-lookup"><span data-stu-id="1adfe-202">If the previous steps did not work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="1adfe-203">Si esto funciona, el problema se debe a un escáner de virus local o a un problema de disco.</span><span class="sxs-lookup"><span data-stu-id="1adfe-203">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
