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
ms.openlocfilehash: a867ed2e55c73fe4bbd890273d78cf57f4bfbd2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926550"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Investigar, solucionar y resolver problemas comunes de exhibición de documentos electrónicos

En este tema se tratan los pasos básicos de solución de problemas que puede seguir para identificar y resolver los problemas que puede encontrar durante una búsqueda de exhibición de documentos electrónicos o en otra parte del proceso de exhibición de documentos electrónicos. Resolver algunos de estos escenarios requiere ayuda del soporte técnico de Microsoft. La información sobre cuándo ponerse en contacto con el Soporte técnico de Microsoft se incluye en los pasos de resolución.

## <a name="errorissue-ambiguous-location"></a>Error/problema: Ubicación ambigua

Si intenta agregar la ubicación del buzón del usuario para buscar y hay objetos duplicados o en conflicto con el mismo userID en el directorio de Exchange Online Protection (EOP), recibirá este error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Resolución

Compruebe si hay usuarios duplicados o una lista de distribución con el mismo identificador de usuario.

1. Conectarse [a PowerShell & Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

2. Ejecute el siguiente comando para recuperar todas las instancias del nombre de usuario:

    ```powershell
    Get-Recipient <username>
    ```

   El resultado de "useralias@contoso.com" sería similar al siguiente:

   > 
   > |Nombre|RecipientType|
   > |---|---|
   > |Alias, Usuario|MailUser|
   > |Alias, Usuario|Usuario|

3. Si se devuelven varios usuarios, busque y corrija el objeto en conflicto.

## <a name="errorissue-search-fails-on-specific-locations"></a>Error o problema: error de búsqueda en ubicaciones específicas

Una exhibición de documentos electrónicos o una búsqueda de contenido pueden producir el siguiente error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Error en la captura de pantalla de error de ubicación específica de la búsqueda](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Resolución

Si recibe este error, se recomienda comprobar las ubicaciones que han fallado en la búsqueda y, a continuación, volver a ejecutar la búsqueda solo en las ubicaciones con errores.

1. Conéctese [a PowerShell & centro](/powershell/exchange/connect-to-scc-powershell) de seguridad y, a continuación, ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. En el resultado de PowerShell, vea las ubicaciones con errores en el campo errores o desde los detalles de estado del error desde el resultado de la búsqueda.

3. Reintente la búsqueda de exhibición de documentos electrónicos solo en las ubicaciones con errores.

4. Si sigue recibiendo estos errores, consulte [Reintentar](/Office365/SecurityCompliance/retry-failed-content-search) ubicaciones con errores para obtener más pasos de solución de problemas.

## <a name="errorissue-file-not-found"></a>Error o problema: no se encontró el archivo

Al ejecutar una búsqueda de exhibición de documentos electrónicos que incluye ubicaciones de SharePoint Online y One Drive For Business, puede recibir el error aunque el archivo se encuentra `File Not Found` en el sitio. Este error estará en las advertencias de exportación y errors.csv o omitirá items.csv. Esto puede ocurrir si el archivo no se puede encontrar en el sitio o si el índice está desa actualizado. Este es el texto de un error real (con énfasis agregado).

> 28.06.2019 10:02:19_FailedToExportItem_Failed descargar contenido. Información de diagnóstico adicional : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: No se pudo descargar del contenido 6ea52149-91cd-4965-b5bb-82ca6a3ec9be de tipo Document. Identificador de correlación: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***Archivo no encontrado***. en Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) en Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- Fin del seguimiento de la pila de excepciones ---

### <a name="resolution"></a>Resolución

1. Compruebe la ubicación identificada en la búsqueda para asegurarse de que la ubicación del archivo es correcta y se ha agregado en las ubicaciones de búsqueda.

2. Use los procedimientos de solicitar manualmente el rastreo y [la re indexación](/sharepoint/crawl-site-content) de un sitio, una biblioteca o una lista para volver a indizar el sitio.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Error o problema: se produce un error en la búsqueda porque no se encuentra el destinatario

Se produce un error en una búsqueda de exhibición de documentos electrónicos con el error `recipient not found` . Este error puede producirse si el objeto de usuario no se encuentra en Exchange Online Protection (EOP) porque el objeto no se ha sincronizado.

### <a name="resolution"></a>Resolución

1. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando para comprobar si el usuario está sincronizado con Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Debe haber un objeto de usuario de correo para la pregunta de usuario. Si no se devuelve nada, investigue el objeto de usuario. Póngase en contacto con el soporte técnico de Microsoft si el objeto no se puede sincronizar.

## <a name="errorissue-exporting-search-results-is-slow"></a>Error o problema: Exportar resultados de búsqueda es lento

Al exportar los resultados de búsqueda desde la exhibición de documentos electrónicos o la búsqueda de contenido en el Centro de seguridad y cumplimiento, la descarga tarda más de lo esperado.  Puede comprobar la cantidad de datos que se descargarán y, posiblemente, aumentar la velocidad de exportación.

### <a name="resolution"></a>Resolución

1. Conéctese [a PowerShell & centro](/powershell/exchange/connect-to-scc-powershell) de seguridad y, a continuación, ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Busque la cantidad de datos que se descargarán en los parámetros SearchResults y SearchStatistics.

3. Ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. En el campo de resultados, busque los datos exportados y vea los errores encontrados.

5. Compruebe si hay errores en el archivo trace.log ubicado en el directorio al que exportó el contenido.

6. Si aún tiene problemas, considere la posibilidad de dividir las búsquedas que devuelven un gran conjunto de resultados en búsquedas más pequeñas. Por ejemplo, puede usar intervalos de fechas en las consultas de búsqueda para devolver un conjunto más pequeño de resultados que se pueden descargar más rápido.

## <a name="errorissue-internal-server-error-500-occurred"></a>Error o problema: "Error interno del servidor (500) producido"

Al ejecutar una búsqueda de exhibición de documentos electrónicos, si la búsqueda falla continuamente con un error similar al "Error interno del servidor (500) ocurrido", es posible que necesite volver a ejecutar la búsqueda solo en ubicaciones de buzones específicas.

![Captura de pantalla de error interno del servidor 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Resolución

1. Divide la búsqueda en búsquedas más pequeñas y vuelve a ejecutarla.  Intente usar un intervalo de fechas más pequeño o limite el número de ubicaciones que se buscan.

2. Conéctese [a PowerShell & centro](/powershell/exchange/connect-to-scc-powershell) de seguridad y, a continuación, ejecute el siguiente comando:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Examine el resultado en busca de resultados y errores.

4. Examine el archivo trace.log. Se encuentra en la misma carpeta a la que exportó los resultados de búsqueda.

5. Ponerse en contacto con el soporte técnico de Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Error o problema: las retenciones no se sincronizan

Error de distribución de la directiva de retención de casos de eDiscovery. El error dice:

> "Recursos: tarda más de lo esperado en implementar la directiva. Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a comprobarlo en un par de horas".

### <a name="resolution"></a>Resolución

1. Conéctese [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) de seguridad y cumplimiento y, a continuación, ejecute el siguiente comando para una retención de casos de exhibición de documentos electrónicos:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Para una directiva de retención, ejecute el siguiente comando:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Examine el valor del parámetro DistributionDetail en busca de errores como los siguientes:

   > Error: Recursos: tarda más de lo esperado en implementar la directiva. Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a comprobarlo en un par de horas".

3. Intente ejecutar el parámetro RetryDistribution en la directiva en cuestión:

   Para las retenciones de casos de exhibición de documentos electrónicos:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Para directivas de retención:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Ponerse en contacto con el soporte técnico de Microsoft.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Error: "No se cumple la condición especificada mediante encabezados condicionales HTTP"

Al descargar resultados de búsqueda con la herramienta de exportación de exhibición de documentos electrónicos, es posible que reciba el siguiente error: se trata de un error transitorio, que normalmente se produce en la ubicación de `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage.

### <a name="resolution"></a>Resolución

Para resolver este problema, [reintente la descarga de los resultados](export-search-results.md#step-2-download-the-search-results)de la búsqueda, que reiniciará la herramienta de exportación de exhibición de documentos electrónicos.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Error o problema: la exportación descargada no muestra resultados

Después de una exportación correcta, la descarga completada a través de la herramienta de exportación muestra cero archivos en los resultados.

### <a name="resolution"></a>Resolución

Este es un problema del lado cliente y, para corregirlo, intente los pasos siguientes:

1. Intente usar otro cliente o máquina para descargar.

2. Asegúrese de descargar en una unidad local.

3. Asegúrese de que el escáner de virus no se está ejecutando.

4. Asegúrese de que ninguna otra exportación se descarga en la misma carpeta o en cualquier carpeta primaria.

5. Si los pasos anteriores no funcionaron, deshabilite la compresión y la desduplicación.

6. Si esto funciona, el problema se debe a un escáner de virus local o a un problema de disco.