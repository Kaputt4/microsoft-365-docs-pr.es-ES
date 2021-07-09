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
ms.openlocfilehash: 0b118a97df765321704a995905de797e06a60108
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339423"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Investigar, solucionar y resolver problemas comunes de exhibición de documentos electrónicos

En este tema se tratan los pasos básicos de solución de problemas que puede seguir para identificar y resolver los problemas que puede encontrar durante una búsqueda de exhibición de documentos electrónicos o en otra parte del proceso de exhibición de documentos electrónicos. Resolver algunos de estos escenarios requiere ayuda del soporte técnico de Microsoft. La información sobre cuándo ponerse en contacto con el Soporte técnico de Microsoft se incluye en los pasos de resolución.

## <a name="errorissue-ambiguous-location"></a>Error/problema: Ubicación ambigua

Si intenta agregar la ubicación del buzón del usuario para buscar y hay objetos duplicados o en conflicto con el mismo userID en el directorio Exchange Online Protection (EOP), recibirá este error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Solución

Compruebe si hay usuarios duplicados o una lista de distribución con el mismo identificador de usuario.

1. Conectar [a PowerShell & Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

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

### <a name="resolution"></a>Solución

Si recibe este error, se recomienda comprobar las ubicaciones que han fallado en la búsqueda y, a continuación, volver a ejecutar la búsqueda solo en las ubicaciones con errores.

1. Conectar [a PowerShell & Centro de](/powershell/exchange/connect-to-scc-powershell) seguridad y, a continuación, ejecute el siguiente comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. En el resultado de PowerShell, vea las ubicaciones con errores en el campo errores o desde los detalles de estado del error desde el resultado de la búsqueda.

3. Reintente la búsqueda de exhibición de documentos electrónicos solo en las ubicaciones con errores.

4. Si sigue recibiendo estos errores, consulte [Reintentar](/Office365/SecurityCompliance/retry-failed-content-search) ubicaciones con errores para obtener más pasos de solución de problemas.

## <a name="errorissue-file-not-found"></a>Error o problema: no se encontró el archivo

Al ejecutar una búsqueda de exhibición de documentos electrónicos que incluye SharePoint online y una unidad para empresas, puede recibir el error aunque el archivo se encuentra `File Not Found` en el sitio. Este error estará en las advertencias de exportación y errors.csv o omitirá items.csv. Esto puede ocurrir si el archivo no se puede encontrar en el sitio o si el índice está desa actualizado. Este es el texto de un error real (con énfasis agregado).

> 28.06.2019 10:02:19_FailedToExportItem_Failed descargar contenido. Información de diagnóstico adicional : Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: No se pudo descargar del contenido 6ea52149-91cd-4965-b5bb-82ca6a3ec9be de tipo Document. Identificador de correlación: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***Archivo no encontrado***. en Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) en Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- fin del seguimiento de la pila de excepciones ---

### <a name="resolution"></a>Solución

1. Compruebe la ubicación identificada en la búsqueda para asegurarse de que la ubicación del archivo es correcta y se agrega en las ubicaciones de búsqueda.

2. Use los procedimientos de solicitar manualmente el rastreo y [la re indexación](/sharepoint/crawl-site-content) de un sitio, una biblioteca o una lista para volver a indizar el sitio.

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a>Error o problema: este archivo no se exportó porque ya no existe. El archivo se incluyó en el recuento de resultados de búsqueda estimados porque aún aparece en el índice. El archivo finalmente se quitará del índice y no provocará un error en el futuro.

Es posible que vea ese error al ejecutar una búsqueda de exhibición de documentos electrónicos que incluye SharePoint online y ubicaciones de One Drive For Business. La exhibición de documentos electrónicos se basa en el índice de SPO para identificar las ubicaciones de archivos. Si el archivo se eliminó pero el índice de SPO aún no se actualizó, puede producirse este error.

### <a name="resolution"></a>Solución 
Abra la ubicación del SPO y compruebe que este archivo no está allí.
La solución sugerida es volver a indizar manualmente el sitio o esperar a que el sitio vuelva a indexarse mediante el proceso en segundo plano automático.


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artifact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a>Error o problema: este resultado de búsqueda no se descargó, ya que es una carpeta u otro artefacto que no se puede descargar por sí mismo, se descargarán los elementos dentro de la carpeta o biblioteca.

Es posible que vea ese error al ejecutar una búsqueda de exhibición de documentos electrónicos que incluye SharePoint online y ubicaciones de One Drive For Business. Significa que ibamos a intentar exportar el elemento notificado en el índice, pero resultó ser una carpeta por lo que no lo exportamos. Como se mencionó en el error, no exportamos elementos de carpeta, pero exportamos su contenido.


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Error o problema: se produce un error en la búsqueda porque no se encuentra el destinatario

Se produce un error en una búsqueda de exhibición de documentos electrónicos con el error `recipient not found` . Este error puede producirse si no se puede encontrar el objeto de usuario en Exchange Online Protection (EOP) porque el objeto no se ha sincronizado.

### <a name="resolution"></a>Solución

1. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando para comprobar si el usuario está sincronizado con Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Debe haber un objeto de usuario de correo para la pregunta de usuario. Si no se devuelve nada, investigue el objeto de usuario. Póngase en contacto con el soporte técnico de Microsoft si el objeto no se puede sincronizar.

## <a name="errorissue-exporting-search-results-is-slow"></a>Error o problema: Exportar resultados de búsqueda es lento

Al exportar resultados de búsqueda desde la exhibición de documentos electrónicos principal o la búsqueda de contenido en el Centro de cumplimiento de Microsoft 365, la descarga tarda más de lo esperado.  Puede comprobar la cantidad de datos que se descargarán y, posiblemente, aumentar la velocidad de exportación.

### <a name="resolution"></a>Solución

1. Conectar [a PowerShell & Centro de](/powershell/exchange/connect-to-scc-powershell) seguridad y, a continuación, ejecute el siguiente comando:

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

## <a name="errorissue-export-process-not-progressing-or-is-stuck"></a>Error o problema: el proceso de exportación no progresa o está atascado

Al exportar resultados de búsqueda desde la exhibición de documentos electrónicos principal o la búsqueda de contenido en el Centro de cumplimiento de Microsoft 365, el proceso de exportación no avanza o parece que está atascado.

### <a name="resolution"></a>Solución

1. Si es necesario, vuelva a ejecutar la búsqueda. Si la búsqueda se ejecutó por última vez hace más de 7 días, debe volver a ejecutar la búsqueda.

2. Reinicie la exportación.

## <a name="errorissue-internal-server-error-500-occurred"></a>Error o problema: "Error interno del servidor (500) producido"

Al ejecutar una búsqueda de exhibición de documentos electrónicos, si la búsqueda falla continuamente con un error similar al "Error interno del servidor (500) ocurrido", es posible que necesite volver a ejecutar la búsqueda solo en ubicaciones de buzones específicas.

![Captura de pantalla de error interno del servidor 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Solución

1. Divide la búsqueda en búsquedas más pequeñas y vuelve a ejecutarla.  Intente usar un intervalo de fechas más pequeño o limite el número de ubicaciones que se buscan.

2. Conectar [a PowerShell & Centro de](/powershell/exchange/connect-to-scc-powershell) seguridad y, a continuación, ejecute el siguiente comando:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Examine el resultado en busca de resultados y errores.

4. Examine el archivo trace.log. Se encuentra en la misma carpeta a la que exportó los resultados de búsqueda.

5. Ponerse en contacto con el soporte técnico de Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Error o problema: las retenciones no se sincronizan

Error de distribución de la directiva de retención de casos de eDiscovery. El error dice:

> "Recursos: tarda más de lo esperado en implementar la directiva. Podría tardar 2 horas adicionales en actualizar el estado de implementación final, así que vuelva a comprobarlo en un par de horas".

### <a name="resolution"></a>Solución

1. Conectar a [PowerShell del Centro de & seguridad](/powershell/exchange/connect-to-scc-powershell) y, a continuación, ejecute el siguiente comando para una retención de casos de exhibición de documentos electrónicos:

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

Al descargar resultados de búsqueda mediante la herramienta de exportación de exhibición de documentos electrónicos, es posible que reciba el siguiente error: se trata de un error transitorio, que normalmente se produce en la `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage ubicación.

### <a name="resolution"></a>Solución

Para resolver este problema, [reintente la descarga de los resultados](export-search-results.md#step-2-download-the-search-results)de la búsqueda, que reiniciará la herramienta de exportación de exhibición de documentos electrónicos.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Error o problema: la exportación descargada no muestra resultados

Después de una exportación correcta, la descarga completada a través de la herramienta de exportación muestra cero archivos en los resultados.

### <a name="resolution"></a>Solución

Este es un problema del lado cliente. Para corregirlo, siga estos pasos:

1. Intente usar otro cliente o máquina para descargar.

2. Quite las búsquedas antiguas que ya no son necesarias con el cmdlet [Remove-ComplianceSearch.](/powershell/module/exchange/remove-compliancesearch)

3. Asegúrese de descargar en una unidad local.

4. Asegúrese de que el escáner de virus no se está ejecutando.

5. Asegúrese de que ninguna otra exportación se descarga en la misma carpeta o en cualquier carpeta primaria.

6. Si los pasos anteriores no funcionan, deshabilite la compresión y la desduplicación.

7. Si esto funciona, el problema se debe a un escáner de virus local o a un problema de disco.
