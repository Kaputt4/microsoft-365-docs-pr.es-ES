---
title: Bloquear Microsoft 365 de usuario con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Cómo usar PowerShell para bloquear y desbloquear el acceso a Microsoft 365 cuentas.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754685"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Bloquear Microsoft 365 de usuario con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Cuando bloquea el acceso a una cuenta Microsoft 365, impide que cualquier usuario use la cuenta para iniciar sesión y obtener acceso a los servicios y datos de su Microsoft 365 organización. Puede usar PowerShell para bloquear el acceso a cuentas individuales o de varios usuarios.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
### <a name="block-access-to-individual-user-accounts"></a>Bloquear el acceso a cuentas de usuario individuales

Use la siguiente sintaxis para bloquear una cuenta de usuario individual:
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> El *parámetro -ObjectID* del cmdlet **Set-AzureAD** acepta el nombre de inicio de sesión de la cuenta, también conocido como nombre principal de usuario, o el identificador de objeto de la cuenta.
  
En este ejemplo se bloquea el acceso a la cuenta de *usuario fabricec@litwareinc.com*.
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Para desbloquear esta cuenta de usuario, ejecute el siguiente comando:
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Para mostrar el UPN de la cuenta de usuario en función del nombre para mostrar del usuario, use los siguientes comandos:
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

En este ejemplo se muestra el UPN de la cuenta de usuario para el  *usuario Caleb Sills*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Para bloquear una cuenta en función del nombre para mostrar del usuario, use los siguientes comandos:
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Para comprobar el estado bloqueado de una cuenta de usuario, use el siguiente comando:
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Bloquear varias cuentas de usuario

Para bloquear el acceso a varias cuentas de usuario, cree un archivo de texto que contenga un nombre de inicio de sesión de cuenta en cada línea como esta:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

En los siguientes comandos, el archivo de texto de ejemplo es *C:\My Documents\Accounts.txt*. Reemplace este nombre de archivo por la ruta de acceso y el nombre del archivo de texto.
  
Para bloquear el acceso a las cuentas enumeradas en el archivo de texto, ejecute el siguiente comando:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

Para desbloquear las cuentas que aparecen en el archivo de texto, ejecute el siguiente comando:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
### <a name="block-individual-user-accounts"></a>Bloquear cuentas de usuario individuales

Use la siguiente sintaxis para bloquear el acceso a una cuenta de usuario individual:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core no admite el módulo Microsoft Azure Active Directory para Windows PowerShell y cmdlets que tienen *Msol* en su nombre. Debe ejecutar estos cmdlets desde Windows PowerShell.

En este ejemplo se bloquea el acceso a la cuenta de *usuario fabricec \@ litwareinc.com*.
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Para desbloquear la cuenta de usuario, ejecute el siguiente comando:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Para comprobar el estado bloqueado de una cuenta de usuario, ejecute el siguiente comando:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Bloquear el acceso a varias cuentas de usuario

En primer lugar, cree un archivo de texto que contenga una cuenta en cada línea como esta:
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

En los siguientes comandos, el archivo de texto de ejemplo es *C:\My Documents\Accounts.txt*. Reemplace este nombre de archivo por la ruta de acceso y el nombre del archivo de texto.
    
Para bloquear el acceso a las cuentas que aparecen en el archivo de texto, ejecute el siguiente comando:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Para desbloquear las cuentas enumeradas en el archivo de texto, ejecute el siguiente comando:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Consulte también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
