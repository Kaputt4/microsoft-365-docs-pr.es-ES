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
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Investigar, solucionar problemas y resolver problemas comunes de exhibición de documentos electrónicos

En este tema se tratan los pasos básicos de solución de problemas que puede realizar para identificar y resolver problemas que pueden surgir durante una búsqueda de exhibición de documentos electrónicos o en otro lugar del proceso de exhibición de documentos electrónicos. La resolución de algunos de estos escenarios requiere ayuda del soporte técnico de Microsoft. La información sobre cuándo ponerse en contacto con el Soporte técnico de Microsoft se incluye en los pasos de resolución.

## <a name="errorissue-ambiguous-location"></a>Error/problema: ubicación ambigua

Si intenta agregar la ubicación del buzón del usuario para buscar y hay objetos duplicados o en conflicto con el mismo userID en el directorio de Exchange Online Protection (EOP), recibirá este error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Solución

Compruebe si hay usuarios duplicados o una lista de distribución con el mismo identificador de usuario.

1. Conéctese [a PowerShell del Centro & seguridad y cumplimiento.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Ejecute el siguiente comando para recuperar todas las instancias del nombre de usuario:

    ```powershell
    Get-Recipient <username>
    ```

   El resultado de "useralias@contoso.com" sería similar al siguiente:

   > 
   > |Nombre|RecipientType|
   > |---|---|
   > |Alias, Usuario|MailUser|
   > |Alias, Usuario|User|

3. Si se devuelven varios usuarios, busque y corrija el objeto en conflicto.

## <a name="errorissue-search-fails-on-specific-locations"></a>Error o problema: error de búsqueda en ubicaciones específicas

Una exhibición de documentos electrónicos o una búsqueda de contenido pueden producir el siguiente error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Captura de pantalla de error de ubicación específica de búsqueda](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Solución

Si recibe este error, le recomendamos que compruebe las ubicaciones en las que se produjo un error en la búsqueda y, a continuación, vuelva a ejecutar la búsqueda solo en las ubicaciones con errores.

1. Conéctese [a PowerShell & Centro de seguridad y](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) cumplimiento y, a continuación, ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. En el resultado de PowerShell, vea las ubicaciones con errores en el campo de errores o desde los detalles de estado del error de la salida de búsqueda.

3. Vuelva a intentar la búsqueda de exhibición de documentos electrónicos solo en las ubicaciones con errores.

4. Si sigue recibiendo estos errores, consulte [Reintentar](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) ubicaciones con errores para obtener más pasos de solución de problemas.

## <a name="errorissue-file-not-found"></a>Error/problema: no se encontró el archivo

Al ejecutar una búsqueda de exhibición de documentos electrónicos que incluya ubicaciones de SharePoint Online y One Drive para empresas, es posible que reciba el error aunque el archivo se encuentra `File Not Found` en el sitio. Este error se producirá en las advertencias de exportación errors.csv o omitido items.csv. Esto puede ocurrir si el archivo no se encuentra en el sitio o si el índice está des actualizado. Este es el texto de un error real (con énfasis agregado).

> 28.06.2019 10:02:19_FailedToExportItem_Failed descargar contenido. Información de diagnóstico adicional: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: No se pudo descargar desde el contenido 6ea52149-91cd-4965-b5bb-82ca6a3ec9be de tipo Document. Identificador de correlación: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***Archivo no encontrado.*** at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---

### <a name="resolution"></a>Solución

1. Compruebe la ubicación identificada en la búsqueda para asegurarse de que la ubicación del archivo es correcta y se agrega en las ubicaciones de búsqueda.

2. Use los procedimientos de solicitar manualmente el rastreo y [la nueva indización](https://docs.microsoft.com/sharepoint/crawl-site-content) de un sitio, una biblioteca o una lista para volver a indexar el sitio.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Error o problema: se produce un error en la búsqueda porque no se encuentra el destinatario

Se produce un error en una búsqueda de exhibición de documentos electrónicos con el error `recipient not found` . Este error puede producirse si no se encuentra el objeto de usuario en Exchange Online Protection (EOP) porque el objeto no se ha sincronizado.

### <a name="resolution"></a>Solución

1. Conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando para comprobar si el usuario está sincronizado con Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Debe haber un objeto de usuario de correo para la pregunta del usuario. Si no se devuelve nada, investigue el objeto de usuario. Póngase en contacto con el soporte técnico de Microsoft si no se puede sincronizar el objeto.

## <a name="errorissue-exporting-search-results-is-slow"></a>Error o problema: exportar los resultados de la búsqueda es lento

Al exportar los resultados de la búsqueda desde la exhibición de documentos electrónicos o la búsqueda de contenido en el Centro de seguridad y cumplimiento, la descarga tarda más de lo esperado.  Puedes comprobar la cantidad de datos que se descargarán y, posiblemente, aumentar la velocidad de exportación.

### <a name="resolution"></a>Solución

1. Conéctese [a PowerShell & Centro de seguridad y](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) cumplimiento y, a continuación, ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Busque la cantidad de datos que se descargarán en los parámetros SearchResults y SearchStatistics.

3. Ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. En el campo de resultados, busque los datos que se han exportado y vea los errores encontrados.

5. Compruebe si hay errores en el archivo trace.log ubicado en el directorio al que exportó el contenido.

6. Si aún tiene problemas, considere dividir las búsquedas que devuelven un gran conjunto de resultados en búsquedas más pequeñas. Por ejemplo, puede usar intervalos de fechas en consultas de búsqueda para devolver un conjunto más pequeño de resultados que se pueden descargar más rápido.

## <a name="errorissue-internal-server-error-500-occurred"></a>Error/problema: "Error interno del servidor (500) "

Al ejecutar una búsqueda de exhibición de documentos electrónicos, si la búsqueda falla continuamente con un error similar a "Error interno del servidor (500)", puede que necesite volver a ejecutar la búsqueda solo en ubicaciones de buzones específicas.

![Captura de pantalla del error interno del servidor 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Solución

1. Divide la búsqueda en búsquedas más pequeñas y vuelve a ejecutarla.  Intente usar un intervalo de fechas más pequeño o limite el número de ubicaciones en las que se busca.

2. Conéctese [a PowerShell & Centro de seguridad y](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) cumplimiento y, a continuación, ejecute el siguiente comando:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Examine el resultado en busca de resultados y errores.

4. Examine el archivo trace.log. Se encuentra en la misma carpeta a la que exportó los resultados de la búsqueda.

5. Ponerse en contacto con el soporte técnico de Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Error o problema: las retenciones no se sincronizan

Error de distribución de la directiva de retención de casos de eDiscovery. El error dice:

> "Recursos: la implementación de la directiva tarda más de lo esperado. Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a consultarlo en un par de horas".

### <a name="resolution"></a>Solución

1. Conéctese [a PowerShell & Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) de seguridad y cumplimiento y, a continuación, ejecute el siguiente comando para una retención de casos de exhibición de documentos electrónicos:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Para una directiva de retención, ejecute el siguiente comando:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Examine el valor del parámetro DistributionDetail para ver si hay errores como los siguientes:

   > Error: Recursos: la implementación de la directiva tarda más de lo esperado. Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a consultarlo en un par de horas".

3. Intente ejecutar el parámetro RetryDistribution en la directiva en cuestión:

   Para las retenciones de casos de eDiscovery:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Para las directivas de retención:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Ponerse en contacto con el soporte técnico de Microsoft.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Error: "No se cumple la condición especificada mediante encabezados condicionales HTTP"

Al descargar los resultados de búsqueda con la herramienta de exportación de exhibición de documentos electrónicos, es posible que reciba el siguiente error: este es un error transitorio, que normalmente se produce en la ubicación de `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage.

### <a name="resolution"></a>Solución

Para resolver este problema, vuelva a intentar [descargar los resultados](export-search-results.md#step-2-download-the-search-results)de la búsqueda, lo que reiniciará la herramienta de exportación de exhibición de documentos electrónicos.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Error/problema: la exportación descargada no muestra resultados

Después de una exportación correcta, la descarga completada a través de la herramienta de exportación muestra cero archivos en los resultados.

### <a name="resolution"></a>Solución

Este es un problema del lado cliente y, para corregirlo, intente los siguientes pasos:

1. Intenta usar otro cliente o máquina para descargar.

2. Asegúrese de descargar en una unidad local.

3. Asegúrese de que el antivirus no se está ejecutando.

4. Asegúrese de que no se está descargando ninguna otra exportación en la misma carpeta o en cualquier carpeta principal.

5. Si los pasos anteriores no funcionaron, deshabilite la compresión y la desduplicación.

6. Si esto funciona, el problema se debe a un antivirus local o a un problema de disco.
