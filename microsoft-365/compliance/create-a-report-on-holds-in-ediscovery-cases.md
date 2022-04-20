---
title: Uso de un script para crear un informe de suspensión de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo generar un informe que contenga información sobre todas las retenciones asociadas a casos de exhibición de documentos electrónicos.
ms.openlocfilehash: b0460b725359e2953c0a27b517a362327ae504f5
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64946471"
---
# <a name="use-a-script-to-create-a-report-on-holds-in-ediscovery-cases"></a>Uso de un script para crear un informe sobre retenciones en casos de exhibición de documentos electrónicos

El script de este artículo permite a los administradores de exhibición de documentos electrónicos y administradores de exhibición de documentos electrónicos generar un informe que contiene información sobre todas las retenciones asociadas a los casos de Core y eDiscovery (Premium) en el portal de cumplimiento de Microsoft Purview. El informe contiene información como el nombre del caso al que está asociada una retención, las ubicaciones de contenido que se colocan en suspensión y si la suspensión está basada en consultas. Si hay casos que no tienen retenciones, el script creará un informe adicional con una lista de casos sin retenciones.

Consulte la sección [Más información](#more-information) para obtener una descripción detallada de la información incluida en el informe.

## <a name="admin-requirements-and-script-information"></a>Requisitos de administración e información de script

- Para generar un informe sobre todos los casos de exhibición de documentos electrónicos de su organización, debe ser administrador de exhibición de documentos electrónicos en su organización. Si es administrador de eDiscovery, el informe solo incluirá información sobre los casos a los que puede acceder. Para obtener más información sobre los permisos de exhibición de documentos electrónicos, consulte [Asignación de permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

- El script de este artículo tiene un control mínimo de errores. El propósito principal es crear rápidamente un informe sobre las retenciones asociadas a los casos de eDiscovery en su organización.

- Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.

## <a name="step-1-connect-to-security--compliance-center-powershell"></a>Paso 1: Conectarse al PowerShell del Centro de seguridad y cumplimiento

El siguiente paso es conectarse al PowerShell del Centro de seguridad y cumplimiento de la organización. Para obtener instrucciones paso a paso, vea [Conectarse al PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Paso 2: Ejecutar el script para informar sobre las retenciones asociadas a casos de eDiscovery

Después de conectarse a PowerShell del Centro de cumplimiento de seguridad &, el siguiente paso es crear y ejecutar el script que recopila información sobre los casos de eDiscovery en su organización.

1. Guarde el texto siguiente en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de .ps1; por ejemplo, CaseHoldsReport.ps1.

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a folder path to save the report to a .csv file (filename is created automatically)'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casetype,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case type" -Value $casetype
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case type","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of eDiscovery (Standard) cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casetype $cc.casetype -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casetype $cc.casetype -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of eDiscovery (Premium) cases and holds..."
   " "
   $edc =Get-ComplianceCase -CaseType Advanced -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus -casetype $cc.casetype $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casetype $cc.casetype -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. En la sesión de Windows PowerShell que se abrió en el paso 1, vaya a la carpeta donde guardó el script.

3. Ejecute el script; por ejemplo:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   El script solicitará una carpeta de destino en la que guardar el informe.

4. Escriba el nombre de la ruta de acceso completa de la carpeta en la que desea guardar el informe y, a continuación, presione **Entrar**.

   > [!TIP]
   > Para guardar el informe en la misma carpeta en la que se encuentra el script, escriba un punto (".") cuando se le pida una carpeta de destino. Para guardar el informe en una subcarpeta de la carpeta donde se encuentra el script, solo tiene que escribir el nombre de la subcarpeta.

   El script comienza a recopilar información sobre todos los casos de eDiscovery de la organización. No acceda al archivo de informe mientras se ejecuta el script. Una vez completado el script, se muestra un mensaje de confirmación en la sesión de Windows PowerShell. Después de mostrar este mensaje, puede acceder al informe en la carpeta que especificó en el paso 4. El nombre de archivo del informe es `CaseHoldsReport<DateTimeStamp>.csv`.

   Además, el script también crea un informe con una lista de casos que no tienen retenciones. El nombre de archivo de este informe es `CaseswithNoHolds<DateTimeStamp>.csv`.

   Este es un ejemplo de ejecución del script de CaseHoldsReport.ps1.

   ![Salida después de ejecutar el script de CaseHoldsReport.ps1.](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>Más información

El caso contiene el informe que se crea al ejecutar el script en este artículo y contiene la siguiente información sobre cada retención. Como se explicó anteriormente, debe ser administrador de exhibición de documentos electrónicos para devolver información de todas las retenciones de su organización. Para obtener más información sobre las retenciones de casos, vea [casos de eDiscovery](./get-started-core-ediscovery.md).

- El nombre de la suspensión y el nombre del caso de exhibición de documentos electrónicos al que está asociada la suspensión.

- Si la suspensión está asociada a un caso core o eDiscovery (Premium).

- Si el caso de eDiscovery está activo o cerrado.

- Si la suspensión está habilitada o deshabilitada.

- Los miembros del caso de eDiscovery al que está asociada la suspensión. Los miembros del caso pueden ver o administrar un caso, en función de los permisos de exhibición de documentos electrónicos que se les hayan asignado.

- Hora y fecha en que se creó el caso.

- Si se cierra un caso, la persona que lo cerró y la hora y la fecha en que se cerró.

- Los buzones de Exchange y las ubicaciones de sitios de SharePoint que están en espera.

- Si la suspensión está basada en consultas, la sintaxis de la consulta.

- La hora y la fecha en que se creó la suspensión y la persona que la creó.

- La hora y la fecha en que se cambió la suspensión por última vez y la persona que la cambió.
