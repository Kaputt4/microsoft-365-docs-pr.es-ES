---
title: Usar un script de PowerShell para buscar en el registro de auditoría
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Usar un script de PowerShell que ejecute el cmdlet Search-UnifiedAuditLog en Exchange Online para buscar en el registro de auditoUsar un script de PowerShell que ejecute el cmdlet Search-UnifiedAuditLog en Exchange Online para buscar en el registro de auditoría+ Este script está optimizado para devolver un gran conjunto (hasta 50 000) de registros de auditoría. El script exporta dichos registros a un archivo CSV que puede visualizar o transformar mediante Power Query en Excel.
ms.openlocfilehash: 8abea51bb1e7e1fa7bd513bea78708b06da62def
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341013"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>Usar un script de PowerShell para buscar en el registro de auditoría

Hoy en día, la seguridad, el cumplimiento y la auditoría son la prioridad número 1 de los administradores de TI. Microsoft 365 cuenta con varias capacidades integradas para ayudar a las organizaciones a administrar la seguridad, el cumplimiento y la auditoría. En particular, un registro unificado de auditoría puede ayudarle a investigar incidentes de seguridad y problemas relacionados con el cumplimiento. Puede recuperar los registros de auditoría mediante los siguientes métodos:

- [API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference)

- La [herramienta de búsqueda en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md) en el Centro de cumplimiento de Microsoft 365

- El cmdlet [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) en Exchange Online PowerShell

Si necesita recuperar registros de auditoría con regularidad, debería considerar una solución que utilice la API de Actividad de administración de Office 365, ya que puede ofrecer a grandes organizaciones la escalabilidad y el rendimiento necesarios para recuperar millones de registros de auditoría de manera continua. Utilizar la herramienta de búsqueda en el registro de auditoría en el Centro de cumplimiento de Microsoft 365 es una manera rápida de encontrar registros de auditoría para operaciones específicas que puedan tener lugar en un intervalo de tiempo más corto. Utilizar intervalos de tiempo mayores en la herramienta de búsqueda en el registro de auditoría, especialmente en el caso de grandes organizaciones, puede entregar un número de registros demasiado elevado como para poderlos administrar o exportar con facilidad.

Cuando se den situaciones en las que necesite recuperar datos de auditoría de forma manual para una investigación o incidente en concreto, sobre todo en el caso de intervalos de fechas mayores en grandes organizaciones, puede que usar el cmdlet **Search-UnifiedAuditLog** sea la mejor opción. Este artículo incluye un script de PowerShell que utiliza el cmdlet para recuperar hasta 50 000 registros de auditoría y, a continuación, exportarlos al archivo CSV al que puede dar formato mediante Power Query en Excel para ayudarle con la revisión. Asimismo, utilizar el script de este artículo minimiza la posibilidad de que se agote el tiempo de espera de búsquedas en grandes registros de auditoría en el servicio.

## <a name="before-you-run-the-script"></a>Antes de ejecutar el script:

- El registro de auditoría debe estar habilitado para su organización para poder utilizar correctamente el script para entregar registros de auditoría. El registro de auditoría está activado de forma predeterminada para organizaciones de Microsoft 365 y Office 365 Enterprise. Para comprobar que la búsqueda de registros de auditoría está activada en su organización, puede ejecutar el comando siguiente en PowerShell de Exchange Online:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  El valor de `True` para la propiedad **UnifiedAuditLogIngestionEnabled** indica que la búsqueda de registros de auditoría está activada.

- Usted debe tener asignado el rol de Registros de auditoría o Registros de auditoría de solo lectura en Exchange Online para ejecutar correctamente el script. De forma predeterminada, estos roles se asignan a los grupos de roles de Administración de la organización y Administración de cumplimiento en la página depermisosdel centro de administración de Exchange. Para más información, consulte la sección «Requisitos para buscar en el registro de auditoría» en [Buscar en el registro de auditoría en el Centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).

- Puede que el script tarde mucho tiempo en completarse. El tiempo que tarde en ejecutarse dependerá del intervalo de fechas y el tamaño del intervalo que establezca en la configuración del script para recuperar registros de auditoría. Los intervalos grandes de fecha y los intervalos menores resultarán en un tiempo de ejecución mayor. Consulte la tabla en el Paso 2 para más información sobre los intervalos de fechas.

- El script de ejemplo que se proporciona en este artículo no es compatible con ningún servicio o programa de soporte técnico estándar de Microsoft. El script de ejemplo se proporciona tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento del script de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega del script no serán en ningún caso responsables de cualquier daño (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso del script de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.

## <a name="step-1-connect-to-exchange-online-powershell"></a>Paso 1: Conectar con Exchange Online PowerShell

El primer paso es conectar al PowerShell de Exchange Online. Puede conectarse con la autenticación moderna o con la autenticación multifactor (MFA). Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>Paso 2: modificar y ejecutar el script para recuperar registros de auditoría

Una vez que se haya conectado a Exchange Online PowerShell, el siguiente paso será crear, modificar y ejecutar el script para recuperar los datos de auditoría. Las primeras siete líneas del script de búsqueda en el registro de auditoría contienen las siguientes variables que puede modificar para configurar la búsqueda. Consulte la tabla del paso 2 para obtener una descripción de dichas variables.

1. Guarde el siguiente texto en un script de Windows PowerShell mediante un sufijo de nombre de archivo de .ps1. Por ejemplo, SearchAuditLog.ps1.

   ```powershell
   #Modify the values for the following variables to configure the audit log search.
   $logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
   $outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
   [DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
   [DateTime]$end = [DateTime]::UtcNow
   $record = "AzureActiveDirectory"
   $resultSize = 5000
   $intervalMinutes = 60
   
   #Start script
   [DateTime]$currentStart = $start
   [DateTime]$currentEnd = $start
   
   Function Write-LogFile ([String]$Message)
   {
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
       $final | Out-File $logFile -Append
   }
   
   Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
   Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"
   
   $totalCount = 0
   while ($true)
   {
       $currentEnd = $currentStart.AddMinutes($intervalMinutes)
       if ($currentEnd -gt $end)
       {
           $currentEnd = $end
       }
   
       if ($currentStart -eq $currentEnd)
       {
           break
       }
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
       Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       $currentCount = 0
   
       $sw = [Diagnostics.StopWatch]::StartNew()
       do
       {
           $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize
   
           if (($results | Measure-Object).Count -ne 0)
           {
               $results | export-csv -Path $outputFile -Append -NoTypeInformation
   
               $currentTotal = $results[0].ResultCount
               $totalCount += $results.Count
               $currentCount += $results.Count
               Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"
   
               if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
               {
                   $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                   Write-LogFile $message
                   Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                   ""
                   break
               }
           }
       }
       while (($results | Measure-Object).Count -ne 0)
   
       $currentStart = $currentEnd
   }
   
   Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
   Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green
   ```

2. Modifique las variables que se enumeran en la siguiente tabla para configurar los criterios de búsqueda. El script incluye valores de ejemplo de estas variables, pero debería cambiarlos (a menos que se indique lo contrario) para adaptarlos a sus requisitos específicos.

   <br>

   ****

   |Variable|Valor de ejemplo|Descripción|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|Especifica el nombre y la ubicación del archivo de registro que contiene información sobre el progreso de la búsqueda en el registro de auditoría realizada por el script. El script escribe marcas de tiempo en UTC en el archivo de registro.|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|Especifica el nombre y la ubicación del archivo CSV que contiene los registros de auditoría devueltos por el script.|
   |`[DateTime]$start` y `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|Especifica el intervalo de fechas para la búsqueda en el registro de auditoría. El script entregará registros de actividades de auditoría que tuvieron lugar entre del intervalo de fechas especificado. Por ejemplo, para entregar actividades realizadas en enero de 2021, puede utilizar una fecha de inicio de `"2021-01-01"` y una fecha de finalización de `"2021-01-31"` (asegúrese de escribir los valores entre comillas dobles) El valor de muestra del script entrega registros de actividades realizadas en las últimas 24 horas. Si no incluye una marca de tiempo en el valor, la marca de tiempo predeterminada es 12:00 AM (medianoche) en la fecha especificada.|
   |`$record`|"AzureActiveDirectory"|Especifica el tipo de registro de las actividades de auditoría (también llamadas *operaciones*) para buscar. Esta propiedad indica el servicio o la característica en la que se desencadenó una actividad. Para obtener una lista de los tipos de registro que puede usar para esta variable, consulte [Tipos de registro de auditoría](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype). Puede utilizar el nombre de tipo de registro o valor ENUM. <br/><br/>**Sugerencia:** Para obtener registros de auditoría para todos los tipos de registro, utilice el valor `$null` (sin usar comillas dobles).|
   |`$resultSize`|5000|Especifica el número de resultados entregados cada vez que el cmdlet **Search-UnifiedAuditLog** es llamado por el script (llamado *conjunto de resultados*). 5 000 es el valor máximo que admite el cmdlet. Deje este valor sin modificar.|
   |`$intervalMinutes`|60|Para ayudar a superar el límite de 5000 registros obtenidos, esta variable toma el intervalo de datos que especificó y lo divide en intervalos de tiempo menores. Ahora, cada intervalo, y no el intervalo de fechas completo, está sujeto al límite del comando de 5000 resultados de registro. El valor predeterminado de 5000 registros por intervalo de 60 minutos dentro del intervalo de fechas debería bastar para la mayoría de las organizaciones. Sin embargo, si el script devuelve un error que dice `maximum results limitation reached`, reduzca el intervalo de tiempo (por ejemplo, a 30 minutos o incluso a 15 minutos) y vuelva a ejecutar el script.|
   ||||

   La mayoría de las variables enumeradas en la tabla anterior se corresponden con parámetros para el cmdlet **Search-UnifiedAuditLog**. Para obtener más información acerca de estos parámetros, consulte [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).

3. En su equipo local, abra Windows PowerShell y vaya a la carpeta en la que guardó el script modificado.

4. Ejecute el script en Exchange Online PowerShell, por ejemplo:

   ```powershell
   .\SearchAuditLog.ps1
   ```

El script muestra mensajes de progreso durante la ejecución. Una vez que el script haya terminado de ejecutarse, creará el archivo de registro y el archivo CSV que contiene los registros de auditoría y los guarda en las carpetas definidas por las variables `$logFile` y `$outputFile`.

> [!IMPORTANT]
> Existe un límite de 50 000 registros de auditoría como máximo que se devuelven cada vez que ejecuta este script. Si ejecuta este script y devuelve 50 000 resultados, es probable que no se incluyeran los registros de auditoría de las actividades que tuvieron lugar dentro del intervalo de fechas. Si esto sucede, se recomienda que divida el intervalo de fechas en intervalos menores y que vuelva ejecutar el script para cada intervalo de fecha. Por ejemplo, si un intervalo de fechas de 90 días devuelve 50 000 resultados, puede volver a ejecutar el script dos veces; una vez para los primeros 45 días del intervalo de fechas y una segunda vez para los siguientes 45 días.

## <a name="step-3-format-and-view-the-audit-records"></a>Paso 3: Dar formato y visualizar los registros de auditoría

Una vez que haya ejecutado el script y exportado los registros de auditoría a un archivo CSV, puede que quiera dar formato al archivo CSV para que resulte más fácil revisar y analizar los registros de auditoría. Una manera de hacer esto es utilizar la característica transformar de Power Query JSON en Excel para dividir cada propiedad en el objeto JSON en la columna **AuditData** en su propia columna. Para obtener instrucciones paso a paso, consulte «Paso 2: Dar formato al registro de auditoría exportado mediante el Editor de Power Query» en [Exportar, configurar y ver los archivos de registros de auditoría](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor). 
