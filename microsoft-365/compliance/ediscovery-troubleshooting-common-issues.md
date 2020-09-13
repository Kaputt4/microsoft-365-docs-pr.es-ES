---
title: Solución de problemas comunes de eDiscovery
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
description: Obtenga información sobre los pasos básicos de solución de problemas que puede realizar para resolver problemas comunes en la exhibición de documentos electrónicos de Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c9d917306c1a4ffd0dd1e11e1dd87c135e94f05
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545958"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Investigar, solucionar problemas y resolver problemas comunes de eDiscovery

En este tema se describen los pasos básicos de solución de problemas que puede realizar para identificar y resolver los problemas que se encuentren durante una búsqueda de exhibición de documentos electrónicos o en cualquier otro lugar del proceso de eDiscovery. Para resolver algunos de estos escenarios se necesita ayuda del soporte técnico de Microsoft. La información sobre cuándo ponerse en contacto con el soporte técnico de Microsoft se incluye en los pasos de resolución.

## <a name="errorissue-ambiguous-location"></a>Error/problema: ubicación ambigua

Si intenta agregar la ubicación del buzón de correo del usuario a la búsqueda y hay objetos duplicados o en conflicto con el mismo userID en el directorio de Exchange Online Protection (EOP), recibirá este error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Solución

Compruebe si hay usuarios duplicados o una lista de distribución con el mismo identificador de usuario.

1. Conéctese al [centro de seguridad & PowerShell del centro de cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Ejecute el siguiente comando para recuperar todas las instancias del nombre de usuario:

    ```powershell
    Get-Recipient <username>
    ```

   La salida de ' useralias@contoso.com ' sería similar a la siguiente:

   > 
   > |Nombre|RecipientType|
   > |---|---|
   > |Alias, usuario|MailUser|
   > |Alias, usuario|Usuario|

3. Si se devuelven varios usuarios, busque y corrija el objeto conflictivo.

## <a name="errorissue-search-fails-on-specific-locations"></a>Error/problema: la búsqueda produce un error en ubicaciones específicas

Una exhibición de documentos electrónicos o búsqueda de contenido puede producir el siguiente error:
>Esta búsqueda se completó con errores (#).  ¿Desea volver a intentar la búsqueda en las ubicaciones con errores?

![Captura de pantalla del error de la ubicación específica de búsqueda con errores](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Solución

Si recibe este error, se recomienda comprobar las ubicaciones en las que se produjo un error en la búsqueda y, a continuación, volver a ejecutar la búsqueda solo en las ubicaciones con error.

1. Conéctese a [PowerShell del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) y, a continuación, ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Desde el resultado de PowerShell, vea las ubicaciones fallidas en el campo errores o los detalles de estado en el error de la salida de la búsqueda.

3. Vuelva a intentar la búsqueda de exhibición de documentos electrónicos solo en las ubicaciones fallidas.

4. Si sigue recibiendo estos errores, consulte [Reintentar ubicaciones erróneas](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) para más pasos de solución de problemas.

## <a name="errorissue-file-not-found"></a>Error/problema: no se encontró el archivo

Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos que incluye SharePoint Online y una unidad para las ubicaciones de la empresa, puede recibir el error, `File Not Found` aunque el archivo se encuentra en el sitio. Este error se producirá en las advertencias de exportación y errors.csv u omitido items.csv. Esto puede ocurrir si no se encuentra el archivo en el sitio o si el índice no está actualizado. Este es el texto de un error real (con énfasis agregado).

> 28.06.2019 10:02:19_FailedToExportItem_Failed descargar contenido. Información de diagnóstico adicional: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: no se pudo descargar del contenido 6ea52149-91cd-4965-b5bb-82ca6a3ec9be de tipo Document. Identificador de correlación: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: ***no se encuentra el archivo***. en Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) en Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---final del seguimiento de pila de la excepción interna---

### <a name="resolution"></a>Solución

1. Compruebe la ubicación identificada en la búsqueda para asegurarse de que la ubicación del archivo es correcta y se ha agregado en las ubicaciones de búsqueda.

2. Use los procedimientos de [solicitar manualmente el rastreo y la reindexación de un sitio, una biblioteca o una lista para volver](https://docs.microsoft.com/sharepoint/crawl-site-content) a indizar el sitio.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Error/problema: la búsqueda produce un error porque no se encuentra el destinatario

Una búsqueda de exhibición de documentos electrónicos da error con el `recipient not found` . Este error puede producirse si no se encuentra el objeto de usuario en Exchange Online Protection (EOP) porque el objeto no se ha sincronizado.

### <a name="resolution"></a>Solución

1. Conéctese a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando para comprobar si el usuario se ha sincronizado con Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Debe haber un objeto de usuario de correo para la pregunta del usuario. Si no se devuelve nada, investigue el objeto de usuario. Póngase en contacto con el soporte técnico de Microsoft si el objeto no se puede sincronizar.

## <a name="errorissue-exporting-search-results-is-slow"></a>Error/problema: exportar resultados de la búsqueda es lento

Al exportar resultados de búsqueda de eDiscovery o búsqueda de contenido en el centro de seguridad y cumplimiento, la descarga tarda más de lo esperado.  Puede comprobar la cantidad de datos que se van a descargar y, posiblemente, aumentar la velocidad de exportación.

### <a name="resolution"></a>Solución

1. Pruebe a usar los pasos que se indican en el artículo [aumentar la velocidad de descarga](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).

2. Si sigue teniendo problemas, conéctese a [PowerShell del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) y, a continuación, ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

3. Busque la cantidad de datos que se van a descargar en los parámetros SearchResults y SearchStatistics.

4. Ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

5. En el campo resultados, busque los datos que se han exportado y vea los errores encontrados.

6. Consulte el archivo trace. log que se encuentra en el directorio al que exportó el contenido para ver si hay errores.

## <a name="errorissue-internal-server-error-500-occurred"></a>Error/problema: "se ha producido un error interno del servidor (500)"

Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos, si se produce un error en la búsqueda con un error similar a "error interno del servidor (500)", es posible que tenga que volver a ejecutar la búsqueda solo en ubicaciones de buzón específicas.

![Captura de pantalla del error interno del servidor 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Solución

1. Divida la búsqueda en búsquedas más pequeñas y vuelva a ejecutar la búsqueda.  Intente usar un intervalo de fechas menor o limitar el número de ubicaciones en las que se busca.

2. Conéctese a [PowerShell del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) y, a continuación, ejecute el siguiente comando:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Examine el resultado para obtener resultados y errores.

4. Examine el archivo trace. log. Se encuentra en la misma carpeta en la que exportó los resultados de la búsqueda.

5. Ponerse en contacto con el soporte técnico de Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Error/problema: no se sincronizan las suspensiones

error de distribución de sincronización de la Directiva de suspensión de casos de eDiscovery. El error reza:

> "Recursos: se está tardando más de lo esperado en implementar la Directiva. La actualización del estado de implementación final puede tardar unas 2 horas más, por lo que debe volver a comprobarlo en un par de horas.

### <a name="resolution"></a>Solución

1. Conéctese a [PowerShell del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) y, a continuación, ejecute el siguiente comando para una suspensión de caso de exhibición de documentos electrónicos:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Para una directiva de retención, ejecute el siguiente comando:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Examine el valor del parámetro DistributionDetail para buscar errores como los siguientes:

   > Error: recursos: se está tardando más de lo esperado en implementar la Directiva. La actualización del estado de implementación final puede tardar unas 2 horas más, por lo que debe volver a comprobarlo en un par de horas.

3. Intente ejecutar el parámetro RetryDistribution en la Directiva en cuestión:

   Para suspensiones de casos de eDiscovery:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Para directivas de retención:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Ponerse en contacto con el soporte técnico de Microsoft.

## <a name="see-also"></a>Vea también

- [Sugerencias para evitar errores de ubicación de contenido](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
