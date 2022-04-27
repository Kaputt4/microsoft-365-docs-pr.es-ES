---
title: Asignación de licencias de Microsoft 365 a cuentas de usuario con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: En este artículo, aprenderá a usar PowerShell para asignar una licencia de Microsoft 365 a usuarios sin licencia.
ms.openlocfilehash: 7f01ac335941c2f7b0ba425f5aff963056ce0da8
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091443"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Asignación de licencias de Microsoft 365 a cuentas de usuario con PowerShell

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Los usuarios no pueden usar ningún Microsoft 365 servicios hasta que su cuenta tenga asignada una licencia de un plan de licencias. Puede usar PowerShell para asignar rápidamente licencias a cuentas sin licencia. 

Primero se debe asignar una ubicación a las cuentas de usuario. Especificar una ubicación es una parte necesaria de la creación de una nueva cuenta de usuario en el [Centro de administración de Microsoft 365](../admin/add-users/add-users.md). 

Las cuentas sincronizadas desde el Active Directory local Domain Services no tienen una ubicación especificada de forma predeterminada. Puede configurar una ubicación para estas cuentas desde:

- Centro de administración de Microsoft 365
- [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
- La [Azure Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active** **DirectoryUsers** >  > cuenta de usuario > **profileContact** >  **infoCountry** >  **o región**).

>[!Note]
>[Obtenga información sobre cómo asignar licencias a cuentas de usuario](../admin/manage/assign-licenses-to-users.md) con el Centro de administración de Microsoft 365. Para obtener una lista de recursos adicionales, consulte [Administración de usuarios y grupos](/admin).
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Uso del SDK de PowerShell de Microsoft Graph

En primer lugar, [conéctese al inquilino de Microsoft 365](/graph/powershell/get-started#authentication).

La asignación y eliminación de licencias para un usuario requiere el ámbito de permisos User.ReadWrite.All o uno de los demás permisos enumerados en la [página de referencia "Asignar licencia" Graph API](/graph/api/user-assignlicense).

El ámbito de permisos Organization.Read.All es necesario para leer las licencias disponibles en el inquilino.

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

Ejecute el `Get-MgSubscribedSku` comando para ver los planes de licencias disponibles y el número de licencias disponibles en cada plan de la organización. El número de licencias disponibles en cada plan es **ActiveUnits** - **WarningUnits** - **ConsumedUnits**. Para obtener más información sobre los planes de licencias, las licencias y los servicios, consulte [Visualización de licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

Para buscar las cuentas sin licencia en su organización, ejecute este comando.

```powershell
Get-MgUser -Filter 'assignedLicenses/$count eq 0' -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All
```

Solo puede asignar licencias a cuentas de usuario que tengan la propiedad **UsageLocation** establecida en un código de país iso 3166-1 alfa-2 válido. Por ejemplo, US para Estados Unidos y FR para Francia. Algunos servicios de Microsoft 365 no están disponibles en determinados países. Para obtener más información, consulte [Sobre las restricciones de licencia](https://go.microsoft.com/fwlink/p/?LinkId=691730).

Para buscar cuentas que no tienen un valor **UsageLocation** , ejecute este comando.

```powershell
Get-MgUser -Select Id,DisplayName,Mail,UserPrincipalName,UsageLocation,UserType | where { $_.UsageLocation -eq $null -and $_.UserType -eq 'Member' }
```

Para establecer el valor **UsageLocation** en una cuenta, ejecute este comando.

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"

Update-MgUser -UserId $userUPN -UsageLocation $userLoc
```

Por ejemplo:

```powershell
Update-MgUser -UserId "belindan@litwareinc.com" -UsageLocation US
```

Si usa el cmdlet **Get-MgUser** sin usar el parámetro **-All** , solo se devuelven las primeras 100 cuentas.

### <a name="assigning-licenses-to-user-accounts"></a>Asignación de licencias a cuentas de usuario

Para asignar una licencia a un usuario, use el siguiente comando en PowerShell.
  
```powershell
Set-MgUserLicense -UserId $userUPN -AddLicenses @{SkuId = "<SkuId>"} -RemoveLicenses @()
```

En este ejemplo se asigna una licencia del plan de licencias de **SPE_E5** (Microsoft 365 E5) al usuario sin licencia **belindan\@ litwareinc.com**:
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{SkuId = $e5Sku.SkuId} -RemoveLicenses @()
```

En este ejemplo se asignan **SPE_E5** (Microsoft 365 E5) y **EMSPREMIUM** (ENTERPRISE MOBILITY + SECURITY E5) al usuario **belindan\@ litwareinc.com**:
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$e5EmsSku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'EMSPREMIUM'
$addLicenses = @(
    @{SkuId = $e5Sku.SkuId},
    @{SkuId = $e5EmsSku.SkuId}
)

Set-MgUserLicense -UserId "belinda@litwareinc.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

En este ejemplo se asignan **SPE_E5** (Microsoft 365 E5) con los servicios **MICROSOFTBOOKINGS** (Microsoft Bookings) y **LOCKBOX_ENTERPRISE** (Caja de seguridad del cliente) desactivados:
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$disabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("LOCKBOX_ENTERPRISE", "MICROSOFTBOOKINGS") | `
    Select -ExpandProperty ServicePlanId

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)

Set-MgUserLicense -UserId "belinda@litwareinc.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

En este ejemplo se actualiza un usuario con **SPE_E5** (Microsoft 365 E5) y se desactivan los planes de servicio Sway y Forms al tiempo que se dejan los planes deshabilitados existentes del usuario en su estado actual:
  
```powershell
$userLicense = Get-MgUserLicenseDetail -UserId "belinda@fdoau.onmicrosoft.com"
$userDisabledPlans = $userLicense.ServicePlans | `
    Where ProvisioningStatus -eq "Disabled" | `
    Select -ExpandProperty ServicePlanId

$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$newDisabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("SWAY", "FORMS_PLAN_E5") | `
    Select -ExpandProperty ServicePlanId

$disabledPlans = ($userDisabledPlans + $newDisabledPlans) | Select -Unique

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)

Set-MgUserLicense -UserId "belinda@litwareinc.onmicrosoft.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

### <a name="assign-licenses-to-a-user-by-copying-the-license-assignment-from-another-user"></a>Asignar licencias a un usuario copiando la asignación de licencias de otro usuario

En este ejemplo se asigna **jamesp\@ litwareinc.com** con el mismo plan de licencias que se ha aplicado a **belindan\@ litwareinc.com**:

```powershell
$mgUser = Get-MgUser -UserId "belindan@litwareinc.com"
Set-MgUserLicense -UserId "jamesp@litwareinc.com" -AddLicenses $mgUser.AssignedLicenses -RemoveLicenses @()
```

### <a name="move-a-user-to-a-different-subscription-license-plan"></a>Traslado de un usuario a otra suscripción (plan de licencia)

En este ejemplo se actualiza un usuario del plan de licencias de **SPE_E3** (Microsoft 365 E3) al plan de licencias **de SPE_E5** (Microsoft 365 E5):

```powershell
$e3Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E3'
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'

# Unassign E3
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{} -RemoveLicenses @($e3Sku.SkuId)
# Assign E5
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{SkuId = $e5Sku.SkuId} -RemoveLicenses @()
```

Puede comprobar el cambio en la suscripción de la cuenta de usuario con este comando.

```powershell
Get-MgUserLicenseDetail -UserId "belindan@litwareinc.com"
```

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

>[!Note]
>El cmdlet Set-AzureADUserLicense está programado para retirarse. Migre los scripts al cmdlet Set-MgUserLicense del SDK de Microsoft Graph, tal como se describió anteriormente. Para obtener más información, consulte [Migración de aplicaciones para acceder a las API de administración de licencias desde Microsoft Graph](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366).
>

En primer lugar, [conéctese al inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  

A continuación, enumere los planes de licencia del inquilino con este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

A continuación, obtenga el nombre de inicio de sesión de la cuenta a la que desea agregar una licencia, también conocida como nombre principal de usuario (UPN).

A continuación, asegúrese de que la cuenta de usuario tiene asignada una ubicación de uso.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Si no hay ninguna ubicación de uso asignada, puede asignar una con estos comandos:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Por último, especifique el nombre de inicio de sesión de usuario y el nombre del plan de licencia y ejecute estos comandos.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

>[!Note]
>Los cmdlets Set-MsolUserLicense y New-MsolUser (-LicenseAssignment) están programados para retirarse. Migre los scripts al cmdlet Set-MgUserLicense del SDK de Microsoft Graph, tal como se describió anteriormente. Para obtener más información, consulte [Migración de aplicaciones para acceder a las API de administración de licencias desde Microsoft Graph](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366).
>

En primer lugar, [conéctese al inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Ejecute el `Get-MsolAccountSku` comando para ver los planes de licencias disponibles y el número de licencias disponibles en cada plan de la organización. El número de licencias disponibles en cada plan es **ActiveUnits** - **WarningUnits** - **ConsumedUnits**. Para obtener más información sobre los planes de licencias, las licencias y los servicios, consulte [Visualización de licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

Para buscar las cuentas sin licencia en su organización, ejecute este comando.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Solo puede asignar licencias a cuentas de usuario que tengan la propiedad **UsageLocation** establecida en un código de país iso 3166-1 alfa-2 válido. Por ejemplo, US para Estados Unidos y FR para Francia. Algunos servicios de Microsoft 365 no están disponibles en determinados países. Para obtener más información, consulte [Sobre las restricciones de licencia](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Para buscar cuentas que no tienen un valor **UsageLocation** , ejecute este comando.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Para establecer el valor **UsageLocation** en una cuenta, ejecute este comando.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Por ejemplo:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Si usa el cmdlet **Get-MsolUser** sin usar el parámetro **All**, solo se devuelven las 500 primeras cuentas.

### <a name="assigning-licenses-to-user-accounts"></a>Asignación de licencias a cuentas de usuario
    
Para asignar una licencia a un usuario, use el siguiente comando en PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

En este ejemplo se asigna una licencia del plan de **licencias litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) al usuario sin licencia **belindan\@ litwareinc.com**:
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Para asignar una licencia a todos los usuarios sin licencia, ejecute este comando.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>No se pueden asignar varias licencias a un usuario desde el mismo plan de licencias. Si no dispone de licencias suficientes, las licencias se asignan a los usuarios en el orden en que los devuelve el cmdlet **Get-MsolUser** hasta que se agoten las licencias disponibles.
>

En este ejemplo se asignan licencias del plan de licencias **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) a todos los usuarios sin licencia:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

En este ejemplo se asignan esas mismas licencias a usuarios sin licencia en el departamento de ventas de la Estados Unidos:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Traslado de un usuario a otra suscripción (plan de licencia) con el módulo Azure Active Directory PowerShell para Graph

En primer lugar, [conéctese al inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
A continuación, obtenga el nombre de inicio de sesión de la cuenta de usuario para la que desea cambiar las suscripciones, también conocida como nombre principal de usuario (UPN).

A continuación, enumere las suscripciones (planes de licencia) del inquilino con este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

A continuación, enumere las suscripciones que la cuenta de usuario tiene actualmente con estos comandos.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identifique la suscripción que el usuario tiene actualmente (la suscripción FROM) y la suscripción a la que el usuario se está moviendo (la suscripción A).

Por último, especifique los nombres de suscripción TO y FROM (números de parte de SKU) y ejecute estos comandos.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

Puede comprobar el cambio en la suscripción de la cuenta de usuario con estos comandos.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Vea también

[Administrar cuentas de usuario, licencias y grupos con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
