---
title: Visualización de usuarios de Microsoft 365 con licencia y sin licencia con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/21/2020
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: En este artículo se explica cómo usar PowerShell para ver las cuentas de usuario de Microsoft 365 con licencia y sin licencia.
ms.openlocfilehash: cd33a9ef5eaadd9c8ccf03dfb9c2f0c283016ebe
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68194497"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>Visualización de usuarios de Microsoft 365 con licencia y sin licencia con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Las cuentas de usuario de la organización de Microsoft 365 pueden tener algunas, todas o ninguna de las licencias disponibles asignadas desde los planes de licencias que están disponibles en su organización. Puede usar PowerShell para Microsoft 365 para encontrar rápidamente los usuarios con licencia y sin licencia de su organización.

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Uso del SDK de PowerShell de Microsoft Graph

En primer lugar, [conéctese a su inquilino de Microsoft 365](/graph/powershell/get-started#authentication).

La lectura de propiedades de usuario, incluidos los detalles de la licencia, requiere el ámbito de permiso User.Read.All o uno de los demás permisos enumerados en la [página de referencia "Obtener un usuario" Graph API](/graph/api/user-get).

El ámbito de permisos Organization.Read.All es necesario para leer las licencias disponibles en el inquilino.

```powershell
Connect-Graph -Scopes User.Read.All, Organization.Read.All
```

Para ver los detalles de licencia de una cuenta de usuario específica, ejecute el siguiente comando:
  
```powershell
Get-MgUserLicenseDetail -UserId "<user sign-in name (UPN)>"
```

Por ejemplo:

```powershell
Get-MgUserLicenseDetail -UserId "belindan@litwareinc.com"
```

Para ver la lista de todas las cuentas de usuario de la organización a las que NO se ha asignado ninguno de los planes de licencia (usuarios sin licencia), ejecute el siguiente comando:
  
```powershell
Get-MgUser -Filter 'assignedLicenses/$count eq 0' -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All

Write-Host "Found $unlicensedUserCount unlicensed users."
```

Para ver la lista de todas las cuentas de usuario miembro (excepto los invitados) de la organización a las que NO se les ha asignado ninguno de los planes de licencia (usuarios sin licencia), ejecute el siguiente comando:
  
```powershell
Get-MgUser -Filter "assignedLicenses/`$count eq 0 and userType eq 'Member'" -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All

Write-Host "Found $unlicensedUserCount unlicensed users (excluding guests)."
```

Para ver la lista de todas las cuentas de usuario de la organización a las que se ha asignado cualquiera de los planes de licencia (usuarios con licencia), ejecute el siguiente comando:
  
```powershell
Get-MgUser -Filter 'assignedLicenses/$count ne 0' -ConsistencyLevel eventual -CountVariable licensedUserCount -All -Select UserPrincipalName,DisplayName,AssignedLicenses | Format-Table -Property UserPrincipalName,DisplayName,AssignedLicenses

Write-Host "Found $licensedUserCount licensed users."
```

Para ver la lista de todas las cuentas de usuario de la organización que tienen asignada una licencia E5, ejecute el siguiente comando:

```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'

Get-MgUser -Filter "assignedLicenses/any(x:x/skuId eq $($e5sku.SkuId) )" -ConsistencyLevel eventual -CountVariable e5licensedUserCount -All

Write-Host "Found $e5licensedUserCount E5 licensed users."
```

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer lugar, [conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
Para ver la lista de todas las cuentas de usuario de la organización a las que NO se ha asignado ninguno de los planes de licencia (usuarios sin licencia), ejecute el siguiente comando:
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

Para ver la lista de todas las cuentas de usuario de la organización a las que se ha asignado cualquiera de los planes de licencia (usuarios con licencia), ejecute el siguiente comando:
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>Para enumerar todos los usuarios de la suscripción, use el `Get-AzureAdUser -All $true` comando .
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer lugar, [conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Para ver la lista de todas las cuentas de usuario y su estado de licencia en su organización, ejecute el siguiente comando en PowerShell:
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

Para ver la lista de todas las cuentas de usuario sin licencia de su organización, ejecute el comando siguiente:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Para ver la lista de todas las cuentas de usuario con licencia de su organización, ejecute el comando siguiente:
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>Vea también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
