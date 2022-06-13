---
title: Actualizar el archivo de tabla de origen de información confidencial de coincidencia exacta de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Actualice el archivo de tabla de origen de información confidencial.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a846f22b866b4b8adf75c44e55fde4b9d56b8ac4
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66008853"
---
# <a name="refresh-your-exact-data-match-sensitive-information-source-table-file"></a>Actualizar el archivo de tabla de origen de información confidencial de coincidencia exacta de datos 

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Puede actualizar la base de datos de información confidencial hasta 5 veces en cada período de 24 horas. Tendrá que volver a establecer y cargar la tabla de origen de información confidencial.

1. Vuelva a exportar los datos confidenciales a una aplicación, como Microsoft Excel, y guarde el archivo en formato delimitado .csv, formato .tsv o canalización (|). Mantenga el mismo nombre de archivo y ubicación que usó cuando anteriormente ha cargado y ha cargado el archivo con hash. Consulte [Exportación de datos de origen para obtener información confidencial exacta basada en coincidencias de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type) para obtener más información sobre cómo exportar los datos confidenciales y obtenerlos en el formato correcto.

      > [!NOTE]
      > Si no hay cambios en la estructura (nombres de campo) del archivo de tabla de origen de información confidencial, no tendrá que realizar ningún cambio en el archivo de esquema de base de datos al actualizar los datos. Pero si necesita realizar cambios, asegúrese de editar el esquema de la base de datos y su paquete de reglas consecuentemente. Vea [Administrar el esquema de coincidencia de datos exacto](sit-use-exact-data-manage-schema.md#manage-your-exact-data-match-schema) para ver los pasos para editar o quitar un esquema. Consulte [Creación de un paquete de reglas o tipo de información confidencial de coincidencia de datos exactos](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) para ver los pasos para editar o quitar el paquete sit/rule de EDM.

2. Use los procedimientos de [Hash y cargue la tabla de origen de información confidencial para que los datos exactos coincidan con los tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) para cargar el archivo de origen de la tabla de información confidencial.

3. Puede usar [el Programador de tareas](/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar el [hash y cargar la tabla de origen de información confidencial para obtener datos exactos que coincidan con el procedimiento de tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) . Puede programar tareas con varios métodos:

   |Método|Qué hacer|
   |---|---|
   |PowerShell|Consulte la documentación [TareasProgramadas](/powershell/module/scheduledtasks/) y [script de PowerShell de ejemplo](#example-powershell-script-for-task-scheduler) de este artículo|
   |API del Programador de tareas|Consulte la documentación del [Programador de tareas](/windows/desktop/TaskSchd/using-the-task-scheduler)|
   |Interfaz de usuario de Windows|En Windows, haga clic en **Inicio** y escriba Programador de tareas. A continuación, en la lista de resultados, haga clic en **Programador de tareas** y **Ejecutar como administrador**.|

## <a name="example-powershell-script-for-task-scheduler"></a>Script de PowerShell de ejemplo para el Programador de tareas

Esta sección incluye un script de PowerShell de ejemplo que puede usar para programar las tareas de creación de hash para los datos y cargar los datos con hash:

### <a name="schedule-hashing-and-upload-in-a-combined-step"></a>Programación de hash y carga en un paso combinado

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

### <a name="schedule-hashing-and-upload-as-separate-steps"></a>Programación de hash y carga como pasos independientes

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
