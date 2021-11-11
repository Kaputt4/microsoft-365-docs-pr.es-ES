---
title: Actualizar el archivo de tabla de origen de información confidencial
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Actualice el archivo de tabla de origen de información confidencial.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fd083b798785f0dbfca8603f8b7bc28fece6004e
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914852"
---
# <a name="refresh-your-sensitive-information-source-table-file"></a>Actualizar el archivo de tabla de origen de información confidencial 

Puede actualizar la base de datos de información confidencial dos veces cada 24 horas. Tendrás que volver ahajar y cargar la tabla de origen de información confidencial.

1. Vuelva a exportar los datos confidenciales a una aplicación, como Microsoft Excel, y guarde el archivo en .csv, formato .tsv o canal (|) delimitado. Mantenga el mismo nombre de archivo y la misma ubicación que usó cuando ha hashado y cargado previamente el archivo. Vea Export [source data for exact data match based sensitive information type](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type) para obtener información detallada sobre cómo exportar los datos confidenciales y obtenerlos en el formato correcto.

      > [!NOTE]
      > Si no hay cambios en la estructura (nombres de campo) del archivo de tabla de origen de información confidencial, no tendrá que realizar cambios en el archivo de esquema de base de datos al actualizar los datos. Pero si necesita realizar cambios, asegúrese de editar el esquema de la base de datos y su paquete de reglas consecuentemente. Consulta Administrar [el esquema exacto de coincidencia de datos](sit-use-exact-data-manage-schema.md#manage-your-exact-data-match-schema) para ver los pasos para editar o quitar un esquema. Consulta Crear datos [exactos que coincidan con](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) el tipo de información confidencial/paquete de regla para los pasos para editar o quitar el paquete de reglas/SIT de EDM.

2. Use los procedimientos de [Hash y cargue](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) la tabla de origen de información confidencial para obtener datos exactos que coincidan con los tipos de información confidencial para cargar el archivo de origen de la tabla de información confidencial.

2. Puede usar el [Programador de tareas para](/windows/desktop/TaskSchd/task-scheduler-start-page) automatizar el hash y cargar la tabla de origen de información confidencial para el procedimiento de tipos de información confidencial de coincidencia de [datos](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) exactos. Puede programar tareas con varios métodos:

   |Método|Qué hacer|
   |---|---|
   |Windows PowerShell|Consulte la documentación [TareasProgramadas](/powershell/module/scheduledtasks/) y [script de PowerShell de ejemplo](#example-powershell-script-for-task-scheduler) de este artículo|
   |API del Programador de tareas|Consulte la documentación del [Programador de tareas](/windows/desktop/TaskSchd/using-the-task-scheduler)|
   |Interfaz de usuario de Windows|En Windows, haga clic en **Inicio** y escriba Programador de tareas. A continuación, en la lista de resultados, haga clic en **Programador de tareas** y **Ejecutar como administrador**.|

### <a name="example-powershell-script-for-task-scheduler"></a>Script de PowerShell de ejemplo para el Programador de tareas 

Esta sección incluye un script de PowerShell de ejemplo que puede usar para programar las tareas de creación de hash para los datos y cargar los datos con hash:

#### <a name="schedule-hashing-and-upload-in-a-combined-step"></a>Programar hash y cargar en un paso combinado

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="schedule-hashing-and-upload-as-separate-steps"></a>Programar hash y cargar como pasos independientes

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```
