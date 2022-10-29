---
title: Uso de PowerShell para administrar la conexión de Shifts a UKG Dimensions
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo usar PowerShell para administrar la conexión shifts a las dimensiones de UKG.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 9d3375f41e4fda4cdc4e4be6352e197512729024
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785559"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-ukg-dimensions"></a>Uso de PowerShell para administrar la conexión de Shifts a UKG Dimensions

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Información general

El [conector Turnos de Microsoft Teams para ukg dimensiones](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions) permite integrar la aplicación Shifts en Microsoft Teams con UKG Dimensions. Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en las dimensiones de UKG desde los turnos.

Puede usar el [Asistente para conectores Shifts](shifts-connector-wizard-ukg.md) en el Centro de administración de Microsoft 365 o [PowerShell](shifts-connector-ukg-powershell-setup.md) para configurar una conexión. Una vez configurada una conexión, puede administrarla mediante [los cmdlets de PowerShell del conector Shifts](#shifts-connector-cmdlets).

En este artículo, se describe cómo hacer lo siguiente:

- [Comprobación del estado de la configuración de la conexión](#check-connection-setup-status)
- [Visualización de un informe de errores para una conexión](#view-an-error-report-for-a-connection)
- [Resolución de errores de conexión](#resolve-connection-errors)
- [Cambiar la configuración de conexión](#change-connection-settings)
- [Desajustar un equipo de una conexión y asignarlo a otra conexión](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Deshabilitar la sincronización para una conexión](#disable-sync-for-a-connection)

En este artículo se supone que ya ha configurado una conexión a UKG Dimensions, ya sea mediante el asistente o PowerShell.

> [!NOTE]
> También puede administrar la conexión en el Centro de administración de Microsoft 365. Por ejemplo, puede comprobar el estado de mantenimiento y acceder al asistente para cambiar la configuración de conexión. Para obtener más información, consulte [Uso de la Centro de administración de Microsoft 365 para administrar la conexión shifts a las dimensiones de UKG](shifts-connector-ukg-admin-center-manage.md).

## <a name="before-you-begin"></a>Antes de empezar

[!INCLUDE [shifts-connector-admin-role](includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configurar el entorno

> [!NOTE]
> Asegúrese de seguir estos pasos para configurar el entorno antes de ejecutar cualquiera de los comandos o scripts de este artículo.

[!INCLUDE [shifts-connector-set-up-environment](includes/shifts-connector-set-up-environment.md)]

7. Conectarse a Teams

    ```powershell
    Connect-MicrosoftTeams
    ```

    Cuando se le solicite, inicie sesión con sus credenciales de administrador. Ahora está configurado para ejecutar los scripts de este artículo y los cmdlets del conector Turnos.

## <a name="check-connection-setup-status"></a>Comprobar el estado de la configuración de la conexión

[!INCLUDE [shifts-connector-check-setup-status](includes/shifts-connector-check-setup-status.md)]

## <a name="view-an-error-report-for-a-connection"></a>Visualizar un informe de errores para una conexión

[!INCLUDE [shifts-connector-view-error-report](includes/shifts-connector-view-error-report.md)]

> [!NOTE]
> Para obtener una lista completa de mensajes de error, consulte [Lista de mensajes de error](#list-of-error-messages) más adelante en este artículo.

## <a name="resolve-connection-errors"></a>Resolver errores de conexión

### <a name="user-mapping-errors"></a>Errores de asignación de usuarios

Pueden producirse errores de asignación de usuarios si uno o varios usuarios de una instancia de WFM no son miembros del equipo asignado en Teams. Para resolver este problema, asegúrese de que los usuarios del equipo asignado coincidan con los usuarios de la instancia de WFM.

Para ver los detalles de los usuarios sin asignar, [configure el entorno](#set-up-your-environment) (si aún no lo ha hecho) y, a continuación, ejecute el siguiente script.

```powershell
#View sync errors script
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.7.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>Errores de autorización de la cuenta

[!INCLUDE [shifts-connector-account-authorization-errors](includes/shifts-connector-account-authorization-errors.md)]

## <a name="change-connection-settings"></a>Cambiar la configuración de conexión

[!INCLUDE [shifts-connector-change-connection-settings](includes/shifts-connector-change-connection-settings.md)]

[Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho) y, a continuación, ejecute el siguiente script.

```powershell
#Update connector instance and mapping script
Write-Host "Update Connector instance and mapping"
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

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance | where {$_.ConnectorId -match $UkgId}
write $InstanceList

#Prompt for the WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$apiUrl = $Instance.ConnectorSpecificSettingApiUrl
$ssoUrl = $Instance.ConnectorSpecificSettingSsoUrl
$clientId = $Instance.ConnectorSpecificSettingClientId
$syncFreq = Read-Host -Prompt 'Input new sync frequency'
$AppKey = Read-Host -Prompt 'Input your app key' -AsSecureString
$plainKey =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($AppKey))
$ClientSecret = Read-Host -Prompt 'Input your client secret' -AsSecureString
$plainSecret =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($ClientSecret))

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
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance `
    -ConnectorInstanceId $InstanceId `
    -ConnectorId $UkgId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $updatedConnectorScenario `
    -EnabledWfiScenario $updatedWfiScenario `
    -Name $UpdatedInstanceName `
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
        }) `
    -IfMatch $Etag
if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de expiración

[!INCLUDE [shifts-connector-disable-shifts-requests](includes/shifts-connector-disable-shifts-requests.md)]

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Desajustar un equipo de una conexión y asignarlo a otra conexión

[!INCLUDE [shifts-connector-unmap-a-team](includes/shifts-connector-unmap-a-team.md)]

## <a name="disable-sync-for-a-connection"></a>Deshabilitar la sincronización para una conexión

Use este script para deshabilitar la sincronización de una conexión. Tenga en cuenta que este script no quita ni elimina una conexión. Desactiva la sincronización para que no se sincronice ningún dato entre Shifts y el sistema de WFM para la conexión que especifique.

[Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho) y, a continuación, ejecute el siguiente script.

```powershell
#Disable sync script
Write-Host "Disable sync"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.7.0
} catch {
    throw
}

#List connection instances available
$UkgId = "95BF2848-2DDA-4425-B0EE-D62AEED4C0A0"
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance | where {$_.ConnectorId -match $UkgId}
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $apiUrl = $Instance.ConnectorSpecificSettingApiUrl
    $ssoUrl = $Instance.ConnectorSpecificSettingSsoUrl
    $clientId = $Instance.ConnectorSpecificSettingClientId
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$UkgId = "95BF2848-2DDA-4425-B0EE-D62AEED4C0A0"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))
$AppKey = Read-Host -Prompt 'Input your app key' -AsSecureString
$plainKey =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($AppKey))
$ClientSecret = Read-Host -Prompt 'Input your client secret' -AsSecureString
$plainSecret =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($ClientSecret))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance `
    -ConnectorInstanceId $InstanceId `
    -ConnectorId $UkgId `
    -ConnectorAdminEmail $ConnectorAdminEmail `
    -DesignatedActorId $DesignatedActorId `
    -EnabledConnectorScenario @() `
    -EnabledWfiScenario @() `
    -Name $UpdatedInstanceName `
    -SyncFrequencyInMin 10 `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
            LoginUserName = $WfmUserName
            LoginPwd = $plainPwd
        }) `
    -IfMatch $Etag

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="list-of-error-messages"></a>Lista de mensajes de error

Esta es la lista de mensajes de error que puede encontrar e información para ayudarle a resolverlos.

|Tipo de error |Detalles del error |Solución |
|---------|---------|---------|
|No se puede autenticar el sistema de administración de la fuerza de trabajo.|Las credenciales de la cuenta del sistema de administración del personal que ha proporcionado no son válidas o esta cuenta no tiene los permisos necesarios.|Actualice las credenciales de la cuenta de servicio de WFM en la configuración de conexión. Para ello, siga uno de estos procedimientos:<ul><li>En el Centro de administración de Microsoft 365, elija **Editar** en la página Administración de conectores o en la página de detalles de conexión para ir al Asistente para conectores de turnos.</li><li>Use el cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) o [Update-CsTeamsShiftsConnectionInstance](/powershell/module/teams/update-csteamsshiftsconnectioninstance) .</li><li>Use [este script de PowerShell](#change-connection-settings).</li></ul>|
|No se puede autenticar Graph. |Error de autenticación. Asegúrese de que ha escrito credenciales válidas para el actor designado y que tiene los permisos necesarios.|Asegúrese de que la cuenta del sistema de Microsoft 365 (también conocida como actor designado) se agrega como propietario del equipo.<br> O bien, actualice las credenciales de la cuenta del sistema de Microsoft 365 en la configuración de conexión.|
|Algunos usuarios no se han asignado correctamente|Error en la asignación de algunos usuarios: \<X\> usuarios de AAD correctos, \<X\> con errores y \<X\> usuarios del sistema de administración de fuerza de trabajo con errores.|Use el cmdlet [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult) o [este script de PowerShell](#user-mapping-errors) para identificar a los usuarios para los que se produjo un error en la asignación. Asegúrese de que los usuarios del equipo asignado coincidan con los usuarios de la instancia de WFM.|
|No se puede asignar un equipo o equipos en este lote. |Este perfil de actor designado no tiene privilegios de propiedad de equipo. |Asegúrese de que la cuenta del sistema de Microsoft 365 (también conocida como actor designado) se agrega como propietario del equipo.<br>Si ha cambiado la cuenta del sistema de Microsoft 365, agregue esa cuenta como propietario del equipo y actualice la configuración de conexión para usarla.|
|    |Este equipo ya está asignado a una instancia de conector existente. |Quite la asignación del equipo de la conexión existente mediante el cmdlet [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) . O bien, cree una nueva conexión para volver a asignar el equipo.|
|    |Esta zona horaria no es válida. La zona horaria pasada no usa el formato de base de datos tz.|Asegúrese de que la zona horaria es correcta y, a continuación, vuelva a asignar el equipo.|
|    |No podemos encontrar esta instancia del conector.|Asigne el equipo a una conexión existente.|
|    |No se encontró este equipo de AAD.|Asegúrese de que el equipo existe o cree un nuevo equipo.|

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
- [Uso del asistente del conector Shifts para conectar shifts a ukg dimensiones](shifts-connector-wizard-ukg.md)
- [Uso de PowerShell para conectar turnos a dimensiones de UKG](shifts-connector-ukg-powershell-setup.md)
- [Use la Centro de administración de Microsoft 365 para administrar la conexión de Shifts a UKG Dimensions.](shifts-connector-ukg-admin-center-manage.md)
- [Administrar la aplicación Turnos para su organización en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Descripción de PowerShell para Teams](/microsoftteams/teams-powershell-overview)
