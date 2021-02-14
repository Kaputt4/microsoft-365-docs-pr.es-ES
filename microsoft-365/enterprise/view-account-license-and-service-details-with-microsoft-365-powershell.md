---
title: Ver detalles de servicio y licencia de cuenta de Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: Explica cómo usar PowerShell para determinar los servicios de Microsoft 365 que se han asignado a los usuarios.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694217"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>Ver detalles de servicio y licencia de cuenta de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

En Microsoft 365, las licencias de los planes de licencias (también denominados SKU o planes de Microsoft 365) dan a los usuarios acceso a los servicios de Microsoft 365 definidos para esos planes. Sin embargo, un usuario podría no tener acceso a todos los servicios disponibles en una licencia que está actualmente asignada a ellos. Puede usar PowerShell para Microsoft 365 para ver el estado de los servicios en las cuentas de usuario. 

Para obtener más información acerca de los planes de licencias, licencias y servicios, vea [Ver licencias y servicios con PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
A continuación, haga una lista de los planes de licencia de su espacio empresarial con este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Use estos comandos para enumerar los servicios que están disponibles en cada plan de licencias.

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

Use estos comandos para enumerar las licencias asignadas a una cuenta de usuario.

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

A continuación, ejecute este comando para enumerar los planes de licencias que están disponibles en su organización. 

```powershell
Get-MsolAccountSku
```
>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

A continuación, ejecute este comando para enumerar los servicios que están disponibles en cada plan de licencias y el orden en que aparecen (el número de índice).

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
Use este comando para enumerar las licencias asignadas a un usuario y el orden en que aparecen (el número de índice).

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>Para ver los servicios de una cuenta de usuario

Para ver todos los servicios de Microsoft 365 a los que tiene acceso un usuario, use la siguiente sintaxis:
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

En este ejemplo se muestran los servicios a los que el usuario BelindaN@litwareinc.com tiene acceso. Se muestran los servicios que están asociados a todas las licencias asignadas a su cuenta.
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

En este ejemplo se muestran los servicios a los que tiene acceso la usuaria BelindaN@litwareinc.com a partir de la primera licencia asignada a su cuenta (el número de índice es 0).
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

Para ver todos los servicios de un usuario al que se han asignado varias *licencias,* use la sintaxis siguiente:

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a>Vea también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
