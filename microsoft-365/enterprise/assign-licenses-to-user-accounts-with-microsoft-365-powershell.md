---
title: Asignar Microsoft 365 a cuentas de usuario con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: En este artículo, obtenga información sobre cómo usar PowerShell para asignar una licencia Microsoft 365 a usuarios sin licencia.
ms.openlocfilehash: 5ce0a8a5cab4acf5db2e72f56526228a8f78b7809677026267bd6caceff77004
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53904892"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Asignar Microsoft 365 a cuentas de usuario con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Los usuarios no pueden usar ningún servicio Microsoft 365 hasta que se haya asignado a su cuenta una licencia de un plan de licencias. Puede usar PowerShell para asignar rápidamente licencias a cuentas sin licencia. 

Primero se debe asignar una ubicación a las cuentas de usuario. Especificar una ubicación es una parte necesaria para crear una nueva cuenta de usuario en el [Centro de administración de Microsoft 365](../admin/add-users/add-users.md). 

De forma predeterminada, las cuentas sincronizadas desde los Servicios de dominio de Active Directory locales no tienen una ubicación especificada. Puede configurar una ubicación para estas cuentas desde:

- Centro de administración de Microsoft 365
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - [Azure Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Usuarios de **Active Directory**> cuenta de usuario > información de contacto de perfil  >     >    >  **país o región**).

>[!Note]
>[Obtenga información sobre cómo asignar licencias a cuentas de usuario](../admin/manage/assign-licenses-to-users.md) con el Centro de administración de Microsoft 365. Para obtener una lista de recursos adicionales, vea [Administrar usuarios y grupos.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  

A continuación, enumera los planes de licencia de tu inquilino con este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

A continuación, obtenga el nombre de inicio de sesión de la cuenta a la que desea agregar una licencia, también conocida como nombre principal de usuario (UPN).

A continuación, asegúrese de que la cuenta de usuario tenga asignada una ubicación de uso.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Si no hay ninguna ubicación de uso asignada, puede asignar uno con estos comandos:

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

Tenga en cuenta que empezaremos a desuso de este módulo cuando la funcionalidad de este módulo esté disponible en la versión [Azure Active Directory PowerShell para Graph](/powershell/azuread/v2/azureactivedirectory) módulo. Se recomienda a los clientes que creen nuevos scripts de PowerShell que usen el módulo más reciente en lugar de este módulo.

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Ejecute el comando para ver los planes de licencias disponibles y el número de licencias disponibles `Get-MsolAccountSku` en cada plan de la organización. El número de licencias disponibles en cada plan es **ActiveUnits** - **WarningUnits** - **ConsumedUnits**. Para obtener más información acerca de los planes de licencias, licencias y servicios, vea [Ver licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

Para buscar las cuentas sin licencia en la organización, ejecute este comando.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Solo puede asignar licencias a cuentas de usuario que tengan la propiedad **UsageLocation** establecida en un código de país iso 3166-1 alfa-2 válido. Por ejemplo, US para Estados Unidos y FR para Francia. Algunos Microsoft 365 servicios no están disponibles en determinados países. Para obtener más información, consulte [Sobre las restricciones de licencia](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Para buscar cuentas que no tienen un valor **UsageLocation,** ejecute este comando.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Para establecer el **valor UsageLocation** en una cuenta, ejecute este comando.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Por ejemplo:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Si usa el cmdlet **Get-MsolUser** sin usar el parámetro **All**, solo se devuelven las 500 primeras cuentas.

### <a name="assigning-licenses-to-user-accounts"></a>Asignar licencias a cuentas de usuario
    
Para asignar una licencia a un usuario, use el siguiente comando en PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

En este ejemplo se asigna una licencia del plan de licencias **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) al usuario sin **\@ licencia belindan litwareinc.com**:
  
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

En este ejemplo se asignan esas mismas licencias a usuarios sin licencia en el departamento de ventas de Estados Unidos:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Mover un usuario a una suscripción diferente (plan de licencia) con el Azure Active Directory PowerShell para Graph módulo

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
A continuación, obtenga el nombre de inicio de sesión de la cuenta de usuario para la que desea cambiar de suscripción, también conocido como el nombre principal de usuario (UPN).

A continuación, enumera las suscripciones (planes de licencia) de tu inquilino con este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

A continuación, enumera las suscripciones que la cuenta de usuario tiene actualmente con estos comandos.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identifique la suscripción que el usuario tiene actualmente (la suscripción FROM) y la suscripción a la que se mueve el usuario (la suscripción a TO).

Por último, especifique los nombres de suscripción TO y FROM (números de parte SKU) y ejecute estos comandos.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
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

## <a name="see-also"></a>Consulte también

[Administrar cuentas de usuario, licencias y grupos con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
