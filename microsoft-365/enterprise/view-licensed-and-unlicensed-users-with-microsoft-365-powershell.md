---
title: Ver usuarios con licencia y sin licencia Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: En este artículo se explica cómo usar PowerShell para ver cuentas de usuario con licencia Microsoft 365 licencia.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651389"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>Ver usuarios con licencia y sin licencia Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Las cuentas de usuario de Microsoft 365 organización pueden tener algunas, todas o ninguna de las licencias disponibles asignadas desde los planes de licencias que están disponibles en su organización. Puede usar PowerShell para Microsoft 365 encontrar rápidamente los usuarios con licencia y sin licencia en su organización.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
Para ver la lista de todas las cuentas de usuario de la organización a las que NO se ha asignado ninguno de los planes de licencias (usuarios sin licencia), ejecute el siguiente comando:
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

Para ver la lista de todas las cuentas de usuario de la organización a las que se ha asignado cualquiera de sus planes de licencias (usuarios con licencia), ejecute el siguiente comando:
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>Para enumerar todos los usuarios de la suscripción, use el `Get-AzureAdUser -All $true` comando.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Para ver la lista de todas las cuentas de usuario y su estado de licencias en la organización, ejecute el siguiente comando en PowerShell:
  
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

## <a name="see-also"></a>Consulte también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
