---
title: Uso de PowerShell para conectar turnos a dimensiones de UKG
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo usar PowerShell para integrar Shifts con UKG Dimensions.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 0a69dd9b92fb0f71f3dbeb2841dcef62e2bd81bb
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68786373"
---
# <a name="use-powershell-to-connect-shifts-to-ukg-dimensions"></a>Uso de PowerShell para conectar turnos a dimensiones de UKG

## <a name="overview"></a>Información general

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Use el [conector Turnos de Microsoft Teams para las dimensiones de UKG](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions) para integrar la aplicación Shifts en Microsoft Teams con ukg dimensiones. Una vez configurada una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en las dimensiones de UKG desde los turnos.

En este artículo, le guiaremos a través de cómo usar PowerShell para configurar y configurar el conector para integrar Shifts con UKG Dimensions.

Para configurar la conexión, ejecute un script de PowerShell. El script configura el conector, aplica la configuración de sincronización, crea la conexión y asigna instancias de UKG Dimensions a los equipos. La configuración de sincronización determina las características habilitadas en Turnos y la información de programación sincronizada entre las dimensiones de UKG y los turnos. Las asignaciones definen la relación de sincronización entre las instancias de UKG Dimensions y los equipos de Teams. Puede asignar a los equipos existentes y a los nuevos equipos.

Proporcionamos dos scripts. Puede usar cualquiera de los scripts, dependiendo de si desea asignar a los equipos existentes o crear nuevos equipos a los que asignar.

Puede configurar varias conexiones, cada una con una configuración de sincronización diferente. Por ejemplo, si su organización tiene varias ubicaciones con requisitos de programación diferentes, cree una conexión con una configuración de sincronización única para cada ubicación. Tenga en cuenta que una instancia de UKG Dimensions solo se puede asignar a un equipo en un momento dado. Si una instancia ya está asignada a un equipo, no se puede asignar a otro equipo.

Con UKG Dimensions como sistema de registro, los trabajadores de primera línea pueden administrar de forma eficaz sus programaciones y disponibilidad en turnos en sus dispositivos. Los administradores de primera línea pueden seguir usando las dimensiones de UKG para configurar programaciones.

> [!NOTE]
> También puede usar el [asistente para conectores Shifts](shifts-connector-wizard-ukg.md) en el Centro de administración de Microsoft 365 para conectar turnos a dimensiones ukg.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="prerequisites"></a>Requisitos previos

[!INCLUDE [shifts-connector-ukg-prerequisites](includes/shifts-connector-ukg-prerequisites.md)]

### <a name="admin-role-to-manage-the-connector-using-powershell"></a>Rol de administrador para administrar el conector mediante PowerShell

[!INCLUDE [shifts-connector-admin-role](includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configurar el entorno

[!INCLUDE [shifts-connector-set-up-environment](includes/shifts-connector-set-up-environment.md)]

## <a name="connect-to-teams"></a>Conectarse a Teams

Ejecute lo siguiente para conectarse a Teams.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador. Ahora está configurado para ejecutar los scripts de este artículo y los cmdlets del conector Turnos.

## <a name="identify-the-teams-you-want-to-map"></a>Identificar los equipos que desea asignar

> [!NOTE]
> Complete este paso si va a asignar instancias de UKG Dimensions a los equipos existentes. Si va a crear nuevos equipos a los que asignará estas instancias, puede omitir este paso.

En Azure Portal, vaya a la página [Todos los grupos](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) para obtener una lista de los TeamIds de los equipos de su organización.

Tome nota de los identificadores de equipo de los equipos que desea asignar. El script le pedirá que escriba esta información.

> [!NOTE]
> Si uno o varios equipos tienen una programación existente, el script quitará las programaciones de esos equipos. De lo contrario, verá turnos duplicados.

## <a name="run-the-script"></a>Ejecutar el script

Ejecute el script:

- Para configurar una conexión y crear nuevos equipos para asignar, [ejecute este script](#set-up-a-connection-and-create-new-teams-to-map).
- Para configurar una conexión y asignarla a los equipos existentes, [ejecute este script](#set-up-a-connection-and-map-to-existing-teams).

El script realiza las siguientes acciones. Se le pedirá que escriba los detalles de instalación y configuración.

1. Prueba y comprueba la conexión a las dimensiones de UKG mediante las credenciales de la cuenta de servicio de UKG Dimensions y las direcciones URL de servicio que especifique.
1. Configure el conector Turnos.
1. Aplique la configuración de sincronización. Esta configuración incluye la frecuencia de sincronización (en minutos) y los datos de programación que se sincronizan entre las dimensiones de UKG y los turnos. Los datos de programación se definen en los parámetros siguientes:

    - El parámetro **enabledConnectorScenarios** define los datos que se sincronizan entre las dimensiones de UKG y los desplazamientos. Las opciones son `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff` `TimeOffRequest`.
    - El parámetro **enabledWfiScenarios** define los datos que se sincronizan de Shifts a UKG Dimensions. Las opciones son `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    Para obtener más información, consulte [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance). Para ver la lista de opciones de sincronización admitidas para cada parámetro, ejecute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector).

    > [!IMPORTANT]
    > El script habilita la sincronización para todas estas opciones. Si desea cambiar la configuración de sincronización, puede hacerlo después de configurar la conexión. Para más información, consulte [Uso de PowerShell para administrar la conexión shifts a las dimensiones de UKG](shifts-connector-ukg-powershell-manage.md).

1. Crea la conexión.
1. Asigna instancias de UKG Dimensions a los equipos. Las asignaciones se basan en los identificadores de instancia de UKG Dimensions y TeamIds que escriba o en los nuevos equipos que cree, en función del script que ejecute. Si un equipo tiene una programación existente, el script quita los datos de programación del intervalo de fecha y hora que especifique.

Un mensaje de operación correcta en la pantalla indica que la conexión se ha configurado correctamente.

## <a name="manage-your-connection"></a>Administrar la conexión

Una vez configurada una conexión, puede administrar y realizar cambios en ella en el Centro de administración de Microsoft 365 o mediante PowerShell.

### <a name="use-the-microsoft-365-admin-center"></a>Use el Centro de administración de Microsoft 365

La página Administración de conectores muestra cada conexión que ha configurado, junto con información como el estado de mantenimiento y los detalles del intervalo de sincronización. También puede acceder al asistente para realizar cambios en cualquiera de las conexiones. Por ejemplo, puede actualizar la configuración de sincronización y las asignaciones de equipo.

Para obtener más información, consulte [Uso de la Centro de administración de Microsoft 365 para administrar la conexión shifts a las dimensiones de UKG](shifts-connector-ukg-admin-center-manage.md).

### <a name="use-powershell"></a>Usar PowerShell

Puede usar PowerShell para ver un informe de errores, cambiar la configuración de conexión, deshabilitar la sincronización, etc. Para obtener instrucciones paso a paso, consulte [Uso de PowerShell para administrar la conexión de Shifts a las dimensiones de UKG](shifts-connector-ukg-powershell-manage.md).

## <a name="scripts"></a>Scripts

### <a name="set-up-a-connection-and-create-new-teams-to-map"></a>Configurar una conexión y crear nuevos equipos para asignar

```powershell
#Map WFM instances to teams script
Write-Host "Map WFM sites to teams"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.7.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$UkgId = "95BF2848-2DDA-4425-B0EE-D62AEED4C0A0"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$Ukg = $connectors | where {$_.Id -match $UkgId}
$enabledConnectorScenario = $Ukg.SupportedScenario
$wfiSupportedScenario = $Ukg.wfiSupportedScenario

#Prompt for entering of WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$apiUrl = Read-Host -Prompt 'Input connector api url'
$ssoUrl = Read-Host -Prompt 'Input connector sso url'
$clientId = Read-Host -Prompt 'Input connector client id'
$AppKey = Read-Host -Prompt 'Input your app key' -AsSecureString
$plainKey =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($AppKey))
$ClientSecret = Read-Host -Prompt 'Input your client secret' -AsSecureString
$plainSecret =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($ClientSecret))

$testResult = Test-CsTeamsShiftsConnectionValidate `
    -Name $InstanceName `
    -ConnectorId $UkgId `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
            LoginUserName = $WfmUserName
            LoginPwd = $plainPwd
        })
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create a connection instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency"

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$InstanceResponse = New-CsTeamsShiftsConnectionInstance `
    -ConnectorId $UkgId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $enabledConnectorScenario `
    -EnabledWfiScenario $wfiSupportedScenario `
    -Name $InstanceName `
    -SyncFrequencyInMin $syncFreq `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
            LoginUserName = $WfmUserName
            LoginPwd = $plainPwd
        })
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of instances
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if (($WfmTeamIds -ne $NULL) -and ($WfmTeamIds.Count -gt 0)){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

#Create a new Teams team with owner set to system account and name set to the site name
Write-Host "Creating a Teams team"
$teamsTeamName = Read-Host -Prompt "Input the Teams team name"
$Team = New-Team -DisplayName $teamsTeamName -Visibility "Public" -Owner $teamsUserId
Write-Host "Success"
$TeamsTeamId=$Team.GroupId

#Add users to the Team for Shifts
Write-Host "Adding users to Teams team"
$currentUser = Read-Host -Prompt "Input the current user's user name or ID"
Add-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
$failedWfmUsers=@()
foreach ($user in $WFMUsers) {
    try {
    $userEmail = $user.Name + "@" +$domain
    Add-TeamUser -GroupId $TeamsTeamId -User $userEmail
    } catch {
        $failedWfmUsers+=$user
    }
}
if($failedWfmUsers.Count -gt 0){
    Write-Host "There are WFM users not existed in Teams tenant:"
    write $failedWfmUsers
}

#Enable scheduling in the group
$RequestBody = @{
    Enabled = $true
    TimeZone = "America/Los_Angeles"
}
$teamUpdateUrl="https://graph.microsoft.com/v1.0/teams/"+$TeamsTeamId+"/schedule"
$Schedule = Invoke-MgGraphRequest -Uri $teamUpdateUrl -Method PUT -Body $RequestBody

#Create a mapping of the new team to the instance
Write-Host "Create a mapping of the new team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"

$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Remove-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
Disconnect-MgGraph
```

### <a name="set-up-a-connection-and-map-to-existing-teams"></a>Configurar una conexión y asignarla a los equipos existentes

```powershell
#Map WFM instances to existing teams script
Write-Host "Map WFM sites to existing teams"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.7.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$UkgId = "95BF2848-2DDA-4425-B0EE-D62AEED4C0A0"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$ukg = $connectors | where {$_.Id -match $UkgId}
$enabledConnectorScenario = $ukg.SupportedScenario
$wfiSupportedScenario = $ukg.wfiSupportedScenario

#Prompt for entering of WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$apiUrl = Read-Host -Prompt 'Input connector api url'
$ssoUrl = Read-Host -Prompt 'Input connector sso url'
$clientId = Read-Host -Prompt 'Input connector client id'
$AppKey = Read-Host -Prompt 'Input your app key' -AsSecureString
$plainKey =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($AppKey))
$ClientSecret = Read-Host -Prompt 'Input your client secret' -AsSecureString
$plainSecret =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($ClientSecret))

$testResult = Test-CsTeamsShiftsConnectionValidate `
    -Name $InstanceName `
    -ConnectorId $UkgId `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
            LoginUserName = $WfmUserName
            LoginPwd = $plainPwd
        })
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create a connection instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency. Value should be equal to or more than 10."

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}

$InstanceResponse = New-CsTeamsShiftsConnectionInstance `
    -ConnectorId $UkgId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $enabledConnectorScenario `
    -EnabledWfiScenario $wfiSupportedScenario `
    -Name $InstanceName `
    -SyncFrequencyInMin $syncFreq `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
            LoginUserName = $WfmUserName
            LoginPwd = $plainPwd
        })
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if (($WfmTeamIds -ne $NULL) -and ($WfmTeamIds.Count -gt 0)){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

$TeamsTeamId = Read-Host -Prompt "Input the ID of the Teams team to be mapped"
#Clear schedule of the Teams team
Write-Host "Clear schedule of the existing team"
$startTime = Read-Host -Prompt "Input the start time of clear schedule"
$endTime = Read-Host -Prompt "Input the end time of clear schedule"

$entityTypeString = Read-Host -Prompt 'Input the entity types of clear schedule'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$entityType = $entityTypeString -Split {$Delimiters -contains $_}
$entityType = $entityType.Trim()
$entityType = $entityType.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
Remove-CsTeamsShiftsScheduleRecord -TeamId $TeamsTeamId -DateRangeStartDate $startTime -DateRangeEndDate $endTime -ClearSchedulingGroup:$True -EntityType $entityType -DesignatedActorId $teamsUserId

#Create a mapping of the existing team to the instance
Write-Host "Create a mapping of the existing team to the site"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"


$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Disconnect-MgGraph
```

## <a name="shifts-connector-cmdlets"></a>Cmdlets del conector Turnos

Para obtener ayuda con los cmdlets del conector Turnos, incluidos los cmdlets usados en los scripts, busque **CsTeamsShiftsConnection** en la [referencia de cmdlets de PowerShell de Teams](/powershell/teams/intro). Estos son los vínculos a algunos cmdlets que se usan habitualmente.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Update-CsTeamsShiftsConnectionInstance](/powershell/module/teams/update-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Uso de PowerShell para administrar la conexión de Shifts a UKG Dimensions](shifts-connector-ukg-powershell-manage.md)
- [Use la Centro de administración de Microsoft 365 para administrar la conexión de Shifts a UKG Dimensions.](shifts-connector-ukg-admin-center-manage.md)
- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Información general de PowerShell para Teams](/microsoftteams/teams-powershell-overview)
- [Referencia del cmdlet de PowerShell para Teams](/powershell/teams/intro)
