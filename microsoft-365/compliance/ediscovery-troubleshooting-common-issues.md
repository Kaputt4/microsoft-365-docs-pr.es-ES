---
title: Problemas comunes de eDiscovery de troublshooting
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
description: Investigue y resuelva los problemas comunes de la exhibición de documentos electrónicos de Office 365.
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207302"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="86a08-103">Investigar, solucionar problemas y resolver problemas comunes de la exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="86a08-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="86a08-104">En este tema se describen los pasos básicos de solución de problemas que puede realizar para identificar y resolver los problemas que se encuentren durante una búsqueda de exhibición de documentos electrónicos o en cualquier otro lugar del proceso de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="86a08-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="86a08-105">Para resolver algunos de estos escenarios se necesita ayuda de los servicios de soporte técnico (CSS).</span><span class="sxs-lookup"><span data-stu-id="86a08-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="86a08-106">La información sobre cuándo ponerse en contacto con CSS se incluye en los pasos de resolución.</span><span class="sxs-lookup"><span data-stu-id="86a08-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="86a08-107">Error/problema ubicación ambigua</span><span class="sxs-lookup"><span data-stu-id="86a08-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="86a08-108">Recibirá este error "la búsqueda de cumplimiento contiene la siguiente ubicación `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` no válida si intentó agregar la ubicación del buzón de correo del usuario a la búsqueda y hay objetos duplicados o en conflicto con el mismo identificador de usuario en la protección en línea de Exchange (EOP). Active.</span><span class="sxs-lookup"><span data-stu-id="86a08-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="86a08-109">Solución</span><span class="sxs-lookup"><span data-stu-id="86a08-109">Resolution</span></span>

<span data-ttu-id="86a08-110">Compruebe si hay usuarios duplicados o una lista de distribución con el mismo identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="86a08-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="86a08-111">Conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="86a08-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="86a08-112">Recuperar todas las instancias del nombre de usuario, escriba:</span><span class="sxs-lookup"><span data-stu-id="86a08-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="86a08-113">El resultado de ' useralias@contoso.com ' podría ser</span><span class="sxs-lookup"><span data-stu-id="86a08-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="86a08-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="86a08-114">Name</span></span>  |<span data-ttu-id="86a08-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="86a08-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="86a08-116">Alias, usuario</span><span class="sxs-lookup"><span data-stu-id="86a08-116">Alias, User</span></span>     |<span data-ttu-id="86a08-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="86a08-117">MailUser</span></span>         |
> |<span data-ttu-id="86a08-118">Alias, usuario</span><span class="sxs-lookup"><span data-stu-id="86a08-118">Alias, User</span></span>     |<span data-ttu-id="86a08-119">User</span><span class="sxs-lookup"><span data-stu-id="86a08-119">User</span></span>         |

3. <span data-ttu-id="86a08-120">Si se devuelven varios usuarios, busque y corrija el objeto conflictivo.</span><span class="sxs-lookup"><span data-stu-id="86a08-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="86a08-121">Error/problema de búsqueda de errores en ubicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="86a08-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="86a08-122">Una exhibición de documentos electrónicos o búsqueda de contenido puede producir el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="86a08-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="86a08-123">Esta búsqueda se completó con errores (#).</span><span class="sxs-lookup"><span data-stu-id="86a08-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="86a08-124">¿Desea volver a intentar la búsqueda en las ubicaciones con errores?</span><span class="sxs-lookup"><span data-stu-id="86a08-124">Would you like to retry the search on the failed locations?</span></span>

![captura de pantalla del error de búsqueda de ubicación específica errónea]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="86a08-126">Solución</span><span class="sxs-lookup"><span data-stu-id="86a08-126">Resolution</span></span>

<span data-ttu-id="86a08-127">Si recibe este error, le recomendamos que compruebe las ubicaciones en las que se produjo un error en la búsqueda y que, a continuación, vuelva a ejecutar la búsqueda solo en las ubicaciones con error.</span><span class="sxs-lookup"><span data-stu-id="86a08-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="86a08-128">Conéctese a [PowerShell de Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="86a08-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="86a08-129">Tipo:</span><span class="sxs-lookup"><span data-stu-id="86a08-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="86a08-130">Desde el resultado de PowerShell, vea las ubicaciones fallidas en el campo errores o los detalles de estado en el error de la salida de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="86a08-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="86a08-131">Vuelva a intentar la búsqueda de exhibición de documentos electrónicos solo en las ubicaciones fallidas.</span><span class="sxs-lookup"><span data-stu-id="86a08-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="86a08-132">Si sigue recibiendo estos errores, consulte [reintento de ubicaciones fallidas](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) para obtener pasos adicionales para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="86a08-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="86a08-133">No se encontró el archivo de error/problema</span><span class="sxs-lookup"><span data-stu-id="86a08-133">Error/issue file not found</span></span>

<span data-ttu-id="86a08-134">Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos que incluye SharePoint Online y una unidad para las ubicaciones de `File Not Found` la empresa, puede recibir el error, aunque el archivo se encuentra en el sitio.</span><span class="sxs-lookup"><span data-stu-id="86a08-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="86a08-135">Este error se producirá en la advertencia de exportación y errores. csv o en los elementos omitidos. csv esto puede ocurrir si el archivo no se encuentra en el sitio o si el índice está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="86a08-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="86a08-136">Este es el texto de un error real, con énfasis agregado.</span><span class="sxs-lookup"><span data-stu-id="86a08-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="86a08-137">28.06.2019 10:02:19_FailedToExportItem_Failed para descargar contenido.</span><span class="sxs-lookup"><span data-stu-id="86a08-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="86a08-138">Información de diagnóstico adicional: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: no se pudo descargar del contenido 6ea52149-91cd-4965-b5bb-82ca6a3ec9be de tipo Document.</span><span class="sxs-lookup"><span data-stu-id="86a08-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="86a08-139">Identificador de correlación: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="86a08-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="86a08-140">ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: ***no se encuentra el archivo***.</span><span class="sxs-lookup"><span data-stu-id="86a08-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="86a08-141">en Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) en Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---final del seguimiento de pila de la excepción interna---</span><span class="sxs-lookup"><span data-stu-id="86a08-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="86a08-142">Solución</span><span class="sxs-lookup"><span data-stu-id="86a08-142">Resolution</span></span>

1. <span data-ttu-id="86a08-143">Compruebe la ubicación identificada en la búsqueda para asegurarse de que la ubicación del archivo es correcta y se ha agregado en las ubicaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="86a08-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="86a08-144">Use los procedimientos que se [muestran en solicitar manualmente el rastreo y la reindexación de un sitio, una biblioteca o una lista](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) para volver a indizar el sitio.</span><span class="sxs-lookup"><span data-stu-id="86a08-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="86a08-145">Error/problema la búsqueda no se encuentra el destinatario</span><span class="sxs-lookup"><span data-stu-id="86a08-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="86a08-146">la búsqueda de exhibición de `recipient not found`documentos electrónicos produce errores.</span><span class="sxs-lookup"><span data-stu-id="86a08-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="86a08-147">Este error puede producirse si no se encuentra el objeto de usuario en Exchange Online Protection (EOP) porque el objeto no se ha sincronizado.</span><span class="sxs-lookup"><span data-stu-id="86a08-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="86a08-148">Solución</span><span class="sxs-lookup"><span data-stu-id="86a08-148">Resolution</span></span>

1. <span data-ttu-id="86a08-149">Conéctese a [PowerShell de Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="86a08-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="86a08-150">Compruebe si el objeto de usuario está sincronizado con Exchange Online Protection tipo:</span><span class="sxs-lookup"><span data-stu-id="86a08-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="86a08-151">Debe haber un objeto mailuser para la pregunta del usuario.</span><span class="sxs-lookup"><span data-stu-id="86a08-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="86a08-152">Si no se devuelve nada, investigue el objeto de usuario.</span><span class="sxs-lookup"><span data-stu-id="86a08-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="86a08-153">CSS de contacto si el objeto no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="86a08-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="86a08-154">Error/problema la exportación de resultados de búsqueda es lenta</span><span class="sxs-lookup"><span data-stu-id="86a08-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="86a08-155">Al exportar resultados de búsqueda de eDiscovery o búsqueda de contenido en el centro de seguridad y cumplimiento, la descarga tarda más de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="86a08-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="86a08-156">Puede comprobar la cantidad de datos que se van a descargar y, posiblemente, aumentar la velocidad de exportación.</span><span class="sxs-lookup"><span data-stu-id="86a08-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="86a08-157">Solución</span><span class="sxs-lookup"><span data-stu-id="86a08-157">Resolution</span></span>

1.  <span data-ttu-id="86a08-158">Pruebe a usar los pasos que se indican en el artículo [aumentar la velocidad de descarga](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="86a08-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="86a08-159">Si sigue teniendo problemas, conéctese a [PowerShell de Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) y escriba:</span><span class="sxs-lookup"><span data-stu-id="86a08-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="86a08-160">Busque la cantidad de datos que se van a descargar en los parámetros SearchResults y SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="86a08-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="86a08-161">Tipo:</span><span class="sxs-lookup"><span data-stu-id="86a08-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="86a08-162">En el campo resultados, busque los datos que se han exportado y vea los errores encontrados.</span><span class="sxs-lookup"><span data-stu-id="86a08-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="86a08-163">Consulte el archivo trace. log que se encuentra en el directorio al que exportó el contenido para ver si hay errores.</span><span class="sxs-lookup"><span data-stu-id="86a08-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="86a08-164">Error/problema "se ha producido un error interno del servidor (500)"</span><span class="sxs-lookup"><span data-stu-id="86a08-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="86a08-165">Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos, si se produce un error en la búsqueda con un error similar a "error interno del servidor (500)", es posible que necesite volver a ejecutar la búsqueda solo en ubicaciones de buzón específicas.</span><span class="sxs-lookup"><span data-stu-id="86a08-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![captura de pantalla del error interno del servidor 500](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="86a08-167">Solución</span><span class="sxs-lookup"><span data-stu-id="86a08-167">Resolution</span></span>

1. <span data-ttu-id="86a08-168">Divida la búsqueda en búsquedas más pequeñas y vuelva a ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="86a08-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="86a08-169">Intente usar un intervalo de fechas menor o limitar el número de ubicaciones en las que se busca.</span><span class="sxs-lookup"><span data-stu-id="86a08-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="86a08-170">Conéctese a [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="86a08-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="86a08-171">Examine el resultado para obtener resultados y errores.</span><span class="sxs-lookup"><span data-stu-id="86a08-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="86a08-172">Examine el archivo trace. log.</span><span class="sxs-lookup"><span data-stu-id="86a08-172">Examine the trace.log file.</span></span> <span data-ttu-id="86a08-173">Estará en la misma carpeta a la que envió la exportación.</span><span class="sxs-lookup"><span data-stu-id="86a08-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="86a08-174">Póngase en contacto con CSS de soporte.</span><span class="sxs-lookup"><span data-stu-id="86a08-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="86a08-175">No se sincronizan los errores/problemas en espera</span><span class="sxs-lookup"><span data-stu-id="86a08-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="86a08-176">error de distribución de sincronización de la Directiva de suspensión de casos de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="86a08-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="86a08-177">El error reza:</span><span class="sxs-lookup"><span data-stu-id="86a08-177">The error reads:</span></span>

> <span data-ttu-id="86a08-178">"Recursos: se está tardando más de lo esperado en implementar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="86a08-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="86a08-179">Es posible que tarde unas dos horas en actualizar el estado de implementación final, por lo que debe volver a comprobarlo en un par de horas.</span><span class="sxs-lookup"><span data-stu-id="86a08-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="86a08-180">Solución</span><span class="sxs-lookup"><span data-stu-id="86a08-180">Resolution</span></span>

1.  <span data-ttu-id="86a08-181">Conéctese a [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="86a08-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="86a08-182">Examine el valor del parámetro Distributiondetail para buscar errores como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="86a08-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="86a08-183">Si se produce un error, cree una escalación a PG para forzar una resincronización manual en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="86a08-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="86a08-184">CSS de contactos.</span><span class="sxs-lookup"><span data-stu-id="86a08-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="86a08-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="86a08-185">See Also</span></span>
- [<span data-ttu-id="86a08-186">Sugerencias para evitar errores de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="86a08-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)