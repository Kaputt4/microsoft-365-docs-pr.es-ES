---
title: Eliminar Microsoft 365 de usuario con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Obtenga información sobre cómo usar diferentes módulos en PowerShell para eliminar Microsoft 365 cuentas de usuario.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919145"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Eliminar Microsoft 365 de usuario con PowerShell

Puede usar PowerShell para Microsoft 365 para eliminar y restaurar cuentas de usuario.

>[!Note]
>Obtenga información sobre [cómo restaurar una cuenta de usuario](../admin/add-users/restore-user.md) mediante el centro Microsoft 365 administración.
>
>Para obtener una lista de recursos adicionales, vea [Administrar usuarios y grupos.](../admin/add-users/index.yml)
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Después de conectarse, use la siguiente sintaxis para quitar una cuenta de usuario individual:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

En este ejemplo se quita la cuenta de *usuario fabricec \@ litwareinc.com*.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> El *parámetro -ObjectID* del cmdlet **Remove-AzureADUser** acepta el nombre de inicio de sesión de la cuenta, también conocido como nombre principal de usuario o el identificador de objeto de la cuenta.
  
Para mostrar el nombre de cuenta según el nombre de usuario, use los comandos siguientes:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

En este ejemplo se muestra el nombre de cuenta del usuario *Caleb Sills*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Para eliminar una cuenta según el nombre para mostrar del usuario, use los comandos siguientes:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

Al eliminar una cuenta de usuario a través del módulo Microsoft Azure Active Directory para Windows PowerShell, la cuenta no se elimina permanentemente. Puede restaurar la cuenta de usuario eliminada durante los siguientes 30 días.

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Para eliminar una cuenta de usuario, utilice la siguiente sintaxis:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre. Ejecute estos cmdlets desde Windows PowerShell.
>

En este ejemplo se elimina la cuenta de *usuario BelindaN@litwareinc.com*.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Para restaurar una cuenta de usuario eliminada dentro del periodo de gracia de 30 días, utilice la sintaxis siguiente:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

En este ejemplo se restaura la cuenta *eliminada BelindaN \@ litwareinc.com*.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Para ver la lista de usuarios eliminados que pueden restaurarse, ejecute el siguiente comando:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Si otra cuenta usa el nombre principal de usuario original de la cuenta de usuario, use el parámetro _NewUserPrincipalName_ en vez de _UserPrincipalName_ para especificar un nombre principal de usuario al restaurar la cuenta de usuario.


## <a name="see-also"></a>Vea también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)