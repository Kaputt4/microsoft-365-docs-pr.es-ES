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
description: Obtenga información sobre los pasos básicos de solución de problemas que puede seguir para resolver problemas comunes en la exhibición de documentos electrónicos de Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1fbda23b730956db42d8e7a92218fb9837868b8
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988144"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="c8e90-103">Investigar, solucionar problemas y resolver problemas comunes de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="c8e90-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="c8e90-104">En este tema se tratan los pasos básicos de solución de problemas que puede realizar para identificar y resolver problemas que pueden surgir durante una búsqueda de exhibición de documentos electrónicos o en otro lugar del proceso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="c8e90-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="c8e90-105">La resolución de algunos de estos escenarios requiere ayuda del soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8e90-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="c8e90-106">La información sobre cuándo ponerse en contacto con el Soporte técnico de Microsoft se incluye en los pasos de resolución.</span><span class="sxs-lookup"><span data-stu-id="c8e90-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="c8e90-107">Error/problema: ubicación ambigua</span><span class="sxs-lookup"><span data-stu-id="c8e90-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="c8e90-108">Si intenta agregar la ubicación del buzón del usuario para buscar y hay objetos duplicados o en conflicto con el mismo userID en el directorio de Exchange Online Protection (EOP), recibirá este error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="c8e90-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="c8e90-109">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-109">Resolution</span></span>

<span data-ttu-id="c8e90-110">Compruebe si hay usuarios duplicados o una lista de distribución con el mismo identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="c8e90-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="c8e90-111">Conéctese [a PowerShell del Centro & seguridad y cumplimiento.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="c8e90-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c8e90-112">Ejecute el siguiente comando para recuperar todas las instancias del nombre de usuario:</span><span class="sxs-lookup"><span data-stu-id="c8e90-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="c8e90-113">El resultado de "useralias@contoso.com" sería similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8e90-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="c8e90-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="c8e90-114">Name</span></span>|<span data-ttu-id="c8e90-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="c8e90-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="c8e90-116">Alias, Usuario</span><span class="sxs-lookup"><span data-stu-id="c8e90-116">Alias, User</span></span>|<span data-ttu-id="c8e90-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="c8e90-117">MailUser</span></span>|
   > |<span data-ttu-id="c8e90-118">Alias, Usuario</span><span class="sxs-lookup"><span data-stu-id="c8e90-118">Alias, User</span></span>|<span data-ttu-id="c8e90-119">User</span><span class="sxs-lookup"><span data-stu-id="c8e90-119">User</span></span>|

3. <span data-ttu-id="c8e90-120">Si se devuelven varios usuarios, busque y corrija el objeto en conflicto.</span><span class="sxs-lookup"><span data-stu-id="c8e90-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="c8e90-121">Error o problema: error de búsqueda en ubicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="c8e90-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="c8e90-122">Una exhibición de documentos electrónicos o una búsqueda de contenido pueden producir el siguiente error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="c8e90-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Captura de pantalla de error de ubicación específica de búsqueda](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="c8e90-124">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-124">Resolution</span></span>

<span data-ttu-id="c8e90-125">Si recibe este error, le recomendamos que compruebe las ubicaciones en las que se produjo un error en la búsqueda y, a continuación, vuelva a ejecutar la búsqueda solo en las ubicaciones con errores.</span><span class="sxs-lookup"><span data-stu-id="c8e90-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="c8e90-126">Conéctese [a PowerShell & Centro de seguridad y](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) cumplimiento y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c8e90-126">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="c8e90-127">En el resultado de PowerShell, vea las ubicaciones con errores en el campo de errores o desde los detalles de estado del error de la salida de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c8e90-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="c8e90-128">Vuelva a intentar la búsqueda de exhibición de documentos electrónicos solo en las ubicaciones con errores.</span><span class="sxs-lookup"><span data-stu-id="c8e90-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="c8e90-129">Si sigue recibiendo estos errores, consulte [Reintentar](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) ubicaciones con errores para obtener más pasos de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="c8e90-129">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="c8e90-130">Error/problema: no se encontró el archivo</span><span class="sxs-lookup"><span data-stu-id="c8e90-130">Error/issue: File not found</span></span>

<span data-ttu-id="c8e90-131">Al ejecutar una búsqueda de exhibición de documentos electrónicos que incluya ubicaciones de SharePoint Online y One Drive para empresas, es posible que reciba el error aunque el archivo se encuentra `File Not Found` en el sitio.</span><span class="sxs-lookup"><span data-stu-id="c8e90-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="c8e90-132">Este error se producirá en las advertencias de exportación errors.csv o omitido items.csv.</span><span class="sxs-lookup"><span data-stu-id="c8e90-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="c8e90-133">Esto puede ocurrir si el archivo no se encuentra en el sitio o si el índice está des actualizado.</span><span class="sxs-lookup"><span data-stu-id="c8e90-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="c8e90-134">Este es el texto de un error real (con énfasis agregado).</span><span class="sxs-lookup"><span data-stu-id="c8e90-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="c8e90-135">28.06.2019 10:02:19_FailedToExportItem_Failed descargar contenido.</span><span class="sxs-lookup"><span data-stu-id="c8e90-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="c8e90-136">Información de diagnóstico adicional: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: No se pudo descargar desde el contenido 6ea52149-91cd-4965-b5bb-82ca6a3ec9be de tipo Document.</span><span class="sxs-lookup"><span data-stu-id="c8e90-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="c8e90-137">Identificador de correlación: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="c8e90-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="c8e90-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***Archivo no encontrado.***</span><span class="sxs-lookup"><span data-stu-id="c8e90-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="c8e90-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="c8e90-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="c8e90-140">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-140">Resolution</span></span>

1. <span data-ttu-id="c8e90-141">Compruebe la ubicación identificada en la búsqueda para asegurarse de que la ubicación del archivo es correcta y se agrega en las ubicaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c8e90-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="c8e90-142">Use los procedimientos de solicitar manualmente el rastreo y [la nueva indización](https://docs.microsoft.com/sharepoint/crawl-site-content) de un sitio, una biblioteca o una lista para volver a indexar el sitio.</span><span class="sxs-lookup"><span data-stu-id="c8e90-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="c8e90-143">Error o problema: se produce un error en la búsqueda porque no se encuentra el destinatario</span><span class="sxs-lookup"><span data-stu-id="c8e90-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="c8e90-144">Se produce un error en una búsqueda de exhibición de documentos electrónicos con el error `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="c8e90-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="c8e90-145">Este error puede producirse si no se encuentra el objeto de usuario en Exchange Online Protection (EOP) porque el objeto no se ha sincronizado.</span><span class="sxs-lookup"><span data-stu-id="c8e90-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="c8e90-146">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-146">Resolution</span></span>

1. <span data-ttu-id="c8e90-147">Conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8e90-147">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c8e90-148">Ejecute el siguiente comando para comprobar si el usuario está sincronizado con Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="c8e90-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="c8e90-149">Debe haber un objeto de usuario de correo para la pregunta del usuario.</span><span class="sxs-lookup"><span data-stu-id="c8e90-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="c8e90-150">Si no se devuelve nada, investigue el objeto de usuario.</span><span class="sxs-lookup"><span data-stu-id="c8e90-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="c8e90-151">Póngase en contacto con el soporte técnico de Microsoft si no se puede sincronizar el objeto.</span><span class="sxs-lookup"><span data-stu-id="c8e90-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="c8e90-152">Error o problema: exportar los resultados de la búsqueda es lento</span><span class="sxs-lookup"><span data-stu-id="c8e90-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="c8e90-153">Al exportar los resultados de la búsqueda desde la exhibición de documentos electrónicos o la búsqueda de contenido en el Centro de seguridad y cumplimiento, la descarga tarda más de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="c8e90-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="c8e90-154">Puedes comprobar la cantidad de datos que se descargarán y, posiblemente, aumentar la velocidad de exportación.</span><span class="sxs-lookup"><span data-stu-id="c8e90-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="c8e90-155">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-155">Resolution</span></span>

1. <span data-ttu-id="c8e90-156">Conéctese [a PowerShell & Centro de seguridad y](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) cumplimiento y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c8e90-156">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="c8e90-157">Busque la cantidad de datos que se descargarán en los parámetros SearchResults y SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="c8e90-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="c8e90-158">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c8e90-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="c8e90-159">En el campo de resultados, busque los datos que se han exportado y vea los errores encontrados.</span><span class="sxs-lookup"><span data-stu-id="c8e90-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="c8e90-160">Compruebe si hay errores en el archivo trace.log ubicado en el directorio al que exportó el contenido.</span><span class="sxs-lookup"><span data-stu-id="c8e90-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="c8e90-161">Si aún tiene problemas, considere dividir las búsquedas que devuelven un gran conjunto de resultados en búsquedas más pequeñas.</span><span class="sxs-lookup"><span data-stu-id="c8e90-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="c8e90-162">Por ejemplo, puede usar intervalos de fechas en consultas de búsqueda para devolver un conjunto más pequeño de resultados que se pueden descargar más rápido.</span><span class="sxs-lookup"><span data-stu-id="c8e90-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="c8e90-163">Error/problema: "Error interno del servidor (500) "</span><span class="sxs-lookup"><span data-stu-id="c8e90-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="c8e90-164">Al ejecutar una búsqueda de exhibición de documentos electrónicos, si la búsqueda falla continuamente con un error similar a "Error interno del servidor (500)", puede que necesite volver a ejecutar la búsqueda solo en ubicaciones de buzones específicas.</span><span class="sxs-lookup"><span data-stu-id="c8e90-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Captura de pantalla del error interno del servidor 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="c8e90-166">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-166">Resolution</span></span>

1. <span data-ttu-id="c8e90-167">Divide la búsqueda en búsquedas más pequeñas y vuelve a ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="c8e90-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="c8e90-168">Intente usar un intervalo de fechas más pequeño o limite el número de ubicaciones en las que se busca.</span><span class="sxs-lookup"><span data-stu-id="c8e90-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="c8e90-169">Conéctese [a PowerShell & Centro de seguridad y](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) cumplimiento y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c8e90-169">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="c8e90-170">Examine el resultado en busca de resultados y errores.</span><span class="sxs-lookup"><span data-stu-id="c8e90-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="c8e90-171">Examine el archivo trace.log.</span><span class="sxs-lookup"><span data-stu-id="c8e90-171">Examine the trace.log file.</span></span> <span data-ttu-id="c8e90-172">Se encuentra en la misma carpeta a la que exportó los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c8e90-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="c8e90-173">Ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8e90-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="c8e90-174">Error o problema: las retenciones no se sincronizan</span><span class="sxs-lookup"><span data-stu-id="c8e90-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="c8e90-175">Error de distribución de la directiva de retención de casos de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c8e90-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="c8e90-176">El error dice:</span><span class="sxs-lookup"><span data-stu-id="c8e90-176">The error reads:</span></span>

> <span data-ttu-id="c8e90-177">"Recursos: la implementación de la directiva tarda más de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="c8e90-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="c8e90-178">Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a consultarlo en un par de horas".</span><span class="sxs-lookup"><span data-stu-id="c8e90-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="c8e90-179">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-179">Resolution</span></span>

1. <span data-ttu-id="c8e90-180">Conéctese [a PowerShell & Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) de seguridad y cumplimiento y, a continuación, ejecute el siguiente comando para una retención de casos de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="c8e90-180">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="c8e90-181">Para una directiva de retención, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c8e90-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="c8e90-182">Examine el valor del parámetro DistributionDetail para ver si hay errores como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c8e90-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="c8e90-183">Error: Recursos: la implementación de la directiva tarda más de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="c8e90-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="c8e90-184">Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a consultarlo en un par de horas".</span><span class="sxs-lookup"><span data-stu-id="c8e90-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="c8e90-185">Intente ejecutar el parámetro RetryDistribution en la directiva en cuestión:</span><span class="sxs-lookup"><span data-stu-id="c8e90-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="c8e90-186">Para las retenciones de casos de eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="c8e90-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="c8e90-187">Para las directivas de retención:</span><span class="sxs-lookup"><span data-stu-id="c8e90-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="c8e90-188">Ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8e90-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="c8e90-189">Error: "No se cumple la condición especificada mediante encabezados condicionales HTTP"</span><span class="sxs-lookup"><span data-stu-id="c8e90-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="c8e90-190">Al descargar los resultados de búsqueda con la herramienta de exportación de exhibición de documentos electrónicos, es posible que reciba el siguiente error: este es un error transitorio, que normalmente se produce en la ubicación de `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c8e90-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="c8e90-191">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-191">Resolution</span></span>

<span data-ttu-id="c8e90-192">Para resolver este problema, vuelva a intentar [descargar los resultados](export-search-results.md#step-2-download-the-search-results)de la búsqueda, lo que reiniciará la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="c8e90-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="c8e90-193">Error/problema: la exportación descargada no muestra resultados</span><span class="sxs-lookup"><span data-stu-id="c8e90-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="c8e90-194">Después de una exportación correcta, la descarga completada a través de la herramienta de exportación muestra cero archivos en los resultados.</span><span class="sxs-lookup"><span data-stu-id="c8e90-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="c8e90-195">Solución</span><span class="sxs-lookup"><span data-stu-id="c8e90-195">Resolution</span></span>

<span data-ttu-id="c8e90-196">Este es un problema del lado cliente y, para corregirlo, intente los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="c8e90-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="c8e90-197">Intenta usar otro cliente o máquina para descargar.</span><span class="sxs-lookup"><span data-stu-id="c8e90-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="c8e90-198">Asegúrese de descargar en una unidad local.</span><span class="sxs-lookup"><span data-stu-id="c8e90-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="c8e90-199">Asegúrese de que el antivirus no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c8e90-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="c8e90-200">Asegúrese de que no se está descargando ninguna otra exportación en la misma carpeta o en cualquier carpeta principal.</span><span class="sxs-lookup"><span data-stu-id="c8e90-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="c8e90-201">Si los pasos anteriores no funcionaron, deshabilite la compresión y la desduplicación.</span><span class="sxs-lookup"><span data-stu-id="c8e90-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="c8e90-202">Si esto funciona, el problema se debe a un antivirus local o a un problema de disco.</span><span class="sxs-lookup"><span data-stu-id="c8e90-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
