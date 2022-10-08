---
title: Bloquear cuentas de usuario de Microsoft 365 con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Cómo usar PowerShell para bloquear y desbloquear el acceso a las cuentas de Microsoft 365.
ms.openlocfilehash: ab212909aa0fa664bee42ac7d5ca74b4b29f7994
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68163456"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Bloquear cuentas de usuario de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Al bloquear el acceso a una cuenta de Microsoft 365, impide que nadie use la cuenta para iniciar sesión y acceder a los servicios y datos de su organización de Microsoft 365. Puede usar PowerShell para bloquear el acceso a cuentas de usuario individuales o varias.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer lugar, [conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="block-access-to-individual-user-accounts"></a>Bloquear el acceso a cuentas de usuario individuales

Use la sintaxis siguiente para bloquear una cuenta de usuario individual:

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> El parámetro *-ObjectID* del cmdlet **Set-AzureAD** acepta el nombre de inicio de sesión de la cuenta, también conocido como nombre principal de usuario, o el identificador de objeto de la cuenta.

En este ejemplo se bloquea el acceso a la cuenta *de usuario fabricec@litwareinc.com*.

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

En este ejemplo se muestra el UPN de la cuenta de usuario del usuario  *Caleb Sills*.

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
Get-AzureADUser  -ObjectID <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Bloquear varias cuentas de usuario

Para bloquear el acceso a varias cuentas de usuario, cree un archivo de texto que contenga un nombre de inicio de sesión de cuenta en cada línea como este:

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

En los comandos siguientes, el archivo de texto de ejemplo es *C:\My Documents\Accounts.txt*. Reemplace este nombre de archivo por la ruta de acceso y el nombre de archivo del archivo de texto.

Para bloquear el acceso a las cuentas enumeradas en el archivo de texto, ejecute el siguiente comando:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

Para desbloquear las cuentas que aparecen en el archivo de texto, ejecute el siguiente comando:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer lugar, [conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="block-individual-user-accounts"></a>Bloquear cuentas de usuario individuales

Use la sintaxis siguiente para bloquear el acceso a una cuenta de usuario individual:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core no admite el módulo Microsoft Azure Active Directory para Windows PowerShell módulo y cmdlets que tengan *Msol* en su nombre. Debe ejecutar estos cmdlets desde Windows PowerShell.

En este ejemplo se bloquea el acceso a la cuenta de usuario *fabricec\@litwareinc.com*.

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

### <a name="block-access-for-multiple-user-accounts"></a>Bloquear el acceso para varias cuentas de usuario

En primer lugar, cree un archivo de texto que contenga una cuenta en cada línea como esta:

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

En los comandos siguientes, el archivo de texto de ejemplo es *C:\My Documents\Accounts.txt*. Reemplace este nombre de archivo por la ruta de acceso y el nombre de archivo del archivo de texto.

Para bloquear el acceso a las cuentas que aparecen en el archivo de texto, ejecute el siguiente comando:

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Para desbloquear las cuentas enumeradas en el archivo de texto, ejecute el siguiente comando:

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Vea también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
