---
title: Solución de problemas comunes de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Investigue, solucione problemas y resuelva problemas comunes en la exhibición de documentos electrónicos de Office 365.
siblings_only: true
ms.openlocfilehash: 3ff22ae11a21aef3909e58e03c8fefcf21db6435
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074826"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="c491a-103">Investigar, solucionar problemas y resolver problemas comunes de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c491a-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="c491a-104">En este tema se describen los pasos básicos de solución de problemas que puede realizar para identificar y resolver los problemas que se encuentren durante una búsqueda de exhibición de documentos electrónicos o en cualquier otro lugar del proceso de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c491a-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="c491a-105">Para resolver algunos de estos escenarios se necesita ayuda del soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c491a-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="c491a-106">La información sobre cuándo ponerse en contacto con el soporte técnico de Microsoft se incluye en los pasos de resolución.</span><span class="sxs-lookup"><span data-stu-id="c491a-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="c491a-107">Error/problema: ubicación ambigua</span><span class="sxs-lookup"><span data-stu-id="c491a-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="c491a-108">Si intenta agregar la ubicación del buzón de correo del usuario a la búsqueda y hay objetos duplicados o en conflicto con el mismo userID en el directorio de Exchange Online Protection (EOP), recibirá este error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span><span class="sxs-lookup"><span data-stu-id="c491a-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span> 

### <a name="resolution"></a><span data-ttu-id="c491a-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="c491a-109">Resolution</span></span>

<span data-ttu-id="c491a-110">Compruebe si hay usuarios duplicados o una lista de distribución con el mismo identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="c491a-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="c491a-111">Conéctese a [Office 365 Security & el centro de cumplimiento de PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c491a-111">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c491a-112">Ejecute el siguiente comando para recuperar todas las instancias del nombre de usuario:</span><span class="sxs-lookup"><span data-stu-id="c491a-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="c491a-113">La salida de ' useralias@contoso.com ' sería similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c491a-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="c491a-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="c491a-114">Name</span></span>  |<span data-ttu-id="c491a-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="c491a-115">RecipientType</span></span>  |
   > |---------|---------|
   > |<span data-ttu-id="c491a-116">Alias, usuario</span><span class="sxs-lookup"><span data-stu-id="c491a-116">Alias, User</span></span>     |<span data-ttu-id="c491a-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="c491a-117">MailUser</span></span>         |
   > |<span data-ttu-id="c491a-118">Alias, usuario</span><span class="sxs-lookup"><span data-stu-id="c491a-118">Alias, User</span></span>     |<span data-ttu-id="c491a-119">Usuario</span><span class="sxs-lookup"><span data-stu-id="c491a-119">User</span></span>         |

3. <span data-ttu-id="c491a-120">Si se devuelven varios usuarios, busque y corrija el objeto conflictivo.</span><span class="sxs-lookup"><span data-stu-id="c491a-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="c491a-121">Error/problema: la búsqueda produce un error en ubicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="c491a-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="c491a-122">Una exhibición de documentos electrónicos o búsqueda de contenido puede producir el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="c491a-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="c491a-123">Esta búsqueda se completó con errores (#).</span><span class="sxs-lookup"><span data-stu-id="c491a-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="c491a-124">¿Desea volver a intentar la búsqueda en las ubicaciones con errores?</span><span class="sxs-lookup"><span data-stu-id="c491a-124">Would you like to retry the search on the failed locations?</span></span>

![Captura de pantalla del error de la ubicación específica de búsqueda con errores](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="c491a-126">Resolución</span><span class="sxs-lookup"><span data-stu-id="c491a-126">Resolution</span></span>

<span data-ttu-id="c491a-127">Si recibe este error, se recomienda comprobar las ubicaciones en las que se produjo un error en la búsqueda y, a continuación, volver a ejecutar la búsqueda solo en las ubicaciones con error.</span><span class="sxs-lookup"><span data-stu-id="c491a-127">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="c491a-128">Conéctese al [centro de seguridad & cumplimiento de Office 365 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c491a-128">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. <span data-ttu-id="c491a-129">Desde el resultado de PowerShell, vea las ubicaciones fallidas en el campo errores o los detalles de estado en el error de la salida de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c491a-129">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="c491a-130">Vuelva a intentar la búsqueda de exhibición de documentos electrónicos solo en las ubicaciones fallidas.</span><span class="sxs-lookup"><span data-stu-id="c491a-130">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="c491a-131">Si sigue recibiendo estos errores, consulte [Reintentar ubicaciones erróneas](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) para más pasos de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="c491a-131">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="c491a-132">Error/problema: no se encontró el archivo</span><span class="sxs-lookup"><span data-stu-id="c491a-132">Error/issue: File not found</span></span>

<span data-ttu-id="c491a-133">Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos que incluye SharePoint Online y una unidad para las ubicaciones de `File Not Found` la empresa, puede recibir el error, aunque el archivo se encuentra en el sitio.</span><span class="sxs-lookup"><span data-stu-id="c491a-133">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="c491a-134">Este error se producirá en la advertencia de exportación y errores. csv o en los elementos omitidos. csv.</span><span class="sxs-lookup"><span data-stu-id="c491a-134">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="c491a-135">Esto puede ocurrir si no se encuentra el archivo en el sitio o si el índice no está actualizado.</span><span class="sxs-lookup"><span data-stu-id="c491a-135">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="c491a-136">Este es el texto de un error real (con énfasis agregado).</span><span class="sxs-lookup"><span data-stu-id="c491a-136">Here's the text of an actual error (with emphasis added).</span></span>
  
> <span data-ttu-id="c491a-137">28.06.2019 10:02:19_FailedToExportItem_Failed descargar contenido.</span><span class="sxs-lookup"><span data-stu-id="c491a-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="c491a-138">Información de diagnóstico adicional: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: no se pudo descargar del contenido 6ea52149-91cd-4965-b5bb-82ca6a3ec9be de tipo Document.</span><span class="sxs-lookup"><span data-stu-id="c491a-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="c491a-139">Identificador de correlación: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="c491a-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="c491a-140">ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: ***no se encuentra el archivo***.</span><span class="sxs-lookup"><span data-stu-id="c491a-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="c491a-141">en Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) en Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---final del seguimiento de pila de la excepción interna---</span><span class="sxs-lookup"><span data-stu-id="c491a-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="c491a-142">Resolución</span><span class="sxs-lookup"><span data-stu-id="c491a-142">Resolution</span></span>

1. <span data-ttu-id="c491a-143">Compruebe la ubicación identificada en la búsqueda para asegurarse de que la ubicación del archivo es correcta y se ha agregado en las ubicaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c491a-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="c491a-144">Use los procedimientos de [solicitar manualmente el rastreo y la reindexación de un sitio, una biblioteca o una lista para volver](https://docs.microsoft.com/sharepoint/crawl-site-content) a indizar el sitio.</span><span class="sxs-lookup"><span data-stu-id="c491a-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="c491a-145">Error/problema: la búsqueda produce un error porque no se encuentra el destinatario</span><span class="sxs-lookup"><span data-stu-id="c491a-145">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="c491a-146">Una búsqueda de exhibición de documentos electrónicos `recipient not found`da error con el.</span><span class="sxs-lookup"><span data-stu-id="c491a-146">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="c491a-147">Este error puede producirse si no se encuentra el objeto de usuario en Exchange Online Protection (EOP) porque el objeto no se ha sincronizado.</span><span class="sxs-lookup"><span data-stu-id="c491a-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="c491a-148">Resolución</span><span class="sxs-lookup"><span data-stu-id="c491a-148">Resolution</span></span>

1. <span data-ttu-id="c491a-149">Conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c491a-149">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c491a-150">Ejecute el siguiente comando para comprobar si el usuario se ha sincronizado con Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="c491a-150">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. <span data-ttu-id="c491a-151">Debe haber un objeto de usuario de correo para la pregunta del usuario.</span><span class="sxs-lookup"><span data-stu-id="c491a-151">There should be a mail user object for the user question.</span></span> <span data-ttu-id="c491a-152">Si no se devuelve nada, investigue el objeto de usuario.</span><span class="sxs-lookup"><span data-stu-id="c491a-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="c491a-153">Póngase en contacto con el soporte técnico de Microsoft si el objeto no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="c491a-153">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="c491a-154">Error/problema: exportar resultados de la búsqueda es lento</span><span class="sxs-lookup"><span data-stu-id="c491a-154">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="c491a-155">Al exportar resultados de búsqueda de eDiscovery o búsqueda de contenido en el centro de seguridad y cumplimiento, la descarga tarda más de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="c491a-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="c491a-156">Puede comprobar la cantidad de datos que se van a descargar y, posiblemente, aumentar la velocidad de exportación.</span><span class="sxs-lookup"><span data-stu-id="c491a-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="c491a-157">Resolución</span><span class="sxs-lookup"><span data-stu-id="c491a-157">Resolution</span></span>

1.  <span data-ttu-id="c491a-158">Pruebe a usar los pasos que se indican en el artículo [aumentar la velocidad de descarga](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="c491a-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>

2.  <span data-ttu-id="c491a-159">Si sigue teniendo problemas, conéctese a [PowerShell del centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c491a-159">If you still have issues, connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. <span data-ttu-id="c491a-160">Busque la cantidad de datos que se van a descargar en los parámetros SearchResults y SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="c491a-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

5. <span data-ttu-id="c491a-161">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c491a-161">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. <span data-ttu-id="c491a-162">En el campo resultados, busque los datos que se han exportado y vea los errores encontrados.</span><span class="sxs-lookup"><span data-stu-id="c491a-162">In the results field, find the data that has been exported and view any errors encountered.</span></span>

7. <span data-ttu-id="c491a-163">Consulte el archivo trace. log que se encuentra en el directorio al que exportó el contenido para ver si hay errores.</span><span class="sxs-lookup"><span data-stu-id="c491a-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="c491a-164">Error/problema: "se ha producido un error interno del servidor (500)"</span><span class="sxs-lookup"><span data-stu-id="c491a-164">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="c491a-165">Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos, si se produce un error en la búsqueda con un error similar a "error interno del servidor (500)", es posible que tenga que volver a ejecutar la búsqueda solo en ubicaciones de buzón específicas.</span><span class="sxs-lookup"><span data-stu-id="c491a-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Captura de pantalla del error interno del servidor 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="c491a-167">Resolución</span><span class="sxs-lookup"><span data-stu-id="c491a-167">Resolution</span></span>

1. <span data-ttu-id="c491a-168">Divida la búsqueda en búsquedas más pequeñas y vuelva a ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c491a-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="c491a-169">Intente usar un intervalo de fechas menor o limitar el número de ubicaciones en las que se busca.</span><span class="sxs-lookup"><span data-stu-id="c491a-169">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="c491a-170">Conéctese al [centro de seguridad & cumplimiento de Office 365 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c491a-170">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
    Get-ComplianceSearch <searchname> | FL
    ```

3. <span data-ttu-id="c491a-171">Examine el resultado para obtener resultados y errores.</span><span class="sxs-lookup"><span data-stu-id="c491a-171">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="c491a-172">Examine el archivo trace. log.</span><span class="sxs-lookup"><span data-stu-id="c491a-172">Examine the trace.log file.</span></span> <span data-ttu-id="c491a-173">Se encuentra en la misma carpeta en la que exportó los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c491a-173">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="c491a-174">Ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c491a-174">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="c491a-175">Error/problema: no se sincronizan las suspensiones</span><span class="sxs-lookup"><span data-stu-id="c491a-175">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="c491a-176">error de distribución de sincronización de la Directiva de suspensión de casos de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c491a-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="c491a-177">El error reza:</span><span class="sxs-lookup"><span data-stu-id="c491a-177">The error reads:</span></span>

> <span data-ttu-id="c491a-178">"Recursos: se está tardando más de lo esperado en implementar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="c491a-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="c491a-179">La actualización del estado de implementación final puede tardar unas 2 horas más, por lo que debe volver a comprobarlo en un par de horas.</span><span class="sxs-lookup"><span data-stu-id="c491a-179">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="c491a-180">Resolución</span><span class="sxs-lookup"><span data-stu-id="c491a-180">Resolution</span></span>

1.  <span data-ttu-id="c491a-181">Conéctese al [centro de seguridad & cumplimiento de Office 365 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) y ejecute el siguiente comando para una suspensión de caso de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="c491a-181">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

    ```powershell
    Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
    ```

    <span data-ttu-id="c491a-182">Para una directiva de retención, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c491a-182">For a retention policy, run the following command:</span></span>

    ```powershell
    Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
    ```

2. <span data-ttu-id="c491a-183">Examine el valor del parámetro DistributionDetail para buscar errores como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c491a-183">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>
 
   > <span data-ttu-id="c491a-184">Error: recursos: se está tardando más de lo esperado en implementar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="c491a-184">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="c491a-185">La actualización del estado de implementación final puede tardar unas 2 horas más, por lo que debe volver a comprobarlo en un par de horas.</span><span class="sxs-lookup"><span data-stu-id="c491a-185">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.”</span></span> 
   
3. <span data-ttu-id="c491a-186">Intente ejecutar el parámetro RetryDistribution en la Directiva en cuestión:</span><span class="sxs-lookup"><span data-stu-id="c491a-186">Try running the RetryDistribution parameter on the policy in question:</span></span>
   
    
    <span data-ttu-id="c491a-187">Para suspensiones de casos de eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="c491a-187">For eDiscovery case holds:</span></span>

    ```powershell
    Set-CaseHoldPolicy <policyname> -RetryDistribution
    ```

    <span data-ttu-id="c491a-188">Para directivas de retención:</span><span class="sxs-lookup"><span data-stu-id="c491a-188">For retention policies:</span></span>

    ```powershell
    Set-RetentionCompliancePolicy <policyname> -RetryDistribution
    ``` 

4. <span data-ttu-id="c491a-189">Ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c491a-189">Contact Microsoft Support.</span></span>

## <a name="see-also"></a><span data-ttu-id="c491a-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="c491a-190">See Also</span></span>

- [<span data-ttu-id="c491a-191">Sugerencias para evitar errores de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="c491a-191">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
