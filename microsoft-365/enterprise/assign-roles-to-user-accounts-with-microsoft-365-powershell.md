---
title: Asignar roles a cuentas de usuario de Microsoft 365 con PowerShell
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: En este artículo, obtenga información sobre cómo usar PowerShell para Microsoft 365 de forma rápida y sencilla para asignar roles de administrador a cuentas de usuario.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754203"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Asignar roles de administrador a cuentas de usuario de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede asignar fácilmente roles a cuentas de usuario mediante PowerShell para Microsoft 365.

>[!Note]
>Obtenga información sobre  [cómo asignar roles de administrador a](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) cuentas de usuario con el Centro de administración de Microsoft 365.
>
>Para obtener una lista de recursos adicionales, vea [Administrar usuarios y grupos.](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer lugar, use una cuenta de administrador global [para conectarse a su inquilino de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
A continuación, identifique el nombre de inicio de sesión de la cuenta de usuario que desea agregar a un rol (ejemplo: fredsm \@ contoso.com). Esto también se conoce como el nombre principal de usuario (UPN).

A continuación, determine el nombre del rol. Vea [los permisos de rol de administrador en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

>[!Note]
>Preste atención a las notas de este artículo. Algunos nombres de roles son diferentes para PowerShell de Azure Active Directory (Azure AD). Por ejemplo, el rol de administrador de *SharePoint* en el Centro de administración de Microsoft 365 es administrador de servicio de *SharePoint* en Azure AD PowerShell.
>

A continuación, rellene los nombres de inicio de sesión y roles y ejecute estos comandos:
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Este es un ejemplo de un conjunto de comandos completado que asigna el rol de administrador de servicio de SharePoint a *la cuenta de contoso.com belindan: \@*
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Para mostrar la lista de nombres de usuario para un rol de administrador específico, use estos comandos.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer lugar, use una cuenta de administrador global [para conectarse a su inquilino de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
### <a name="for-a-single-role-change"></a>Para un único cambio de rol

La forma más común de especificar la cuenta de usuario es mediante su nombre para mostrar o su nombre de correo electrónico, que también se conoce como nombre de inicio de sesión o nombre principal de usuario (UPN).

#### <a name="display-names-of-user-accounts"></a>Mostrar nombres de cuentas de usuario

Si está acostumbrado a trabajar con los nombres para mostrar de las cuentas de usuario, determine la siguiente información:
  
- La cuenta de usuario que desea configurar
    
    Para especificar la cuenta de usuario, debe determinar su nombre para mostrar. Para obtener una lista completa de cuentas, use este comando:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Este comando muestra el nombre para mostrar de las cuentas de usuario, ordenado por el nombre para mostrar, una pantalla cada vez. Puede filtrar la lista a un conjunto más pequeño mediante el cmdlet **Where.** Vea el ejemplo siguiente.

   >[!Note]
   >PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre. Ejecute estos cmdlets desde Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Este comando enumera solo las cuentas de usuario para las que el nombre para mostrar comienza por "John".
    
- El rol que desea asignar
    
    Para mostrar la lista de roles de administrador disponibles que puede asignar a cuentas de usuario, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Después de determinar el nombre para mostrar de la cuenta y el nombre del rol, use estos comandos para asignar el rol a la cuenta:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Pegue los comandos en el Bloc de notas. Para las *$dispName* y *$roleName* variables, reemplace el texto de descripción por sus valores. Quite los \< and > caracteres pero mantenga las comillas. Pegue las líneas modificadas en el Módulo microsoft Azure Active Directory para Windows PowerShell para ejecutarlas. Como alternativa, puede usar el Windows PowerShell de script integrado (ISE).
  
Este es un ejemplo de un conjunto de comandos completado:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Nombres de inicio de sesión de cuentas de usuario

Si está acostumbrado a trabajar con los nombres de inicio de sesión o LOS UPN de las cuentas de usuario, determine la siguiente información:
  
- UPN de la cuenta de usuario
    
    Si no conoce el UPN, use este comando:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Este comando muestra el UPN de las cuentas de usuario, ordenado por UPN, una pantalla cada vez. Puede usar el cmdlet **Where** para filtrar la lista. Aquí le mostramos un ejemplo:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Este comando enumera solo las cuentas de usuario para las que el nombre para mostrar comienza por "John".
    
- El rol que desea asignar
    
    Para mostrar la lista de roles disponibles que puede asignar a cuentas de usuario, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Una vez que tenga el UPN de la cuenta y el nombre del rol, use estos comandos para asignar el rol a la cuenta:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Copie los comandos y péguelos en el Bloc de notas. Para las **$upnName** y **$roleName** variables. Reemplace el texto de descripción por sus valores. Quite los \< and > caracteres pero mantenga las comillas. Pegue las líneas modificadas en el Módulo Microsoft Azure Active Directory Windows PowerShell para ejecutarlas. Como alternativa, puede usar la Windows PowerShell ISE.
  
Este es un ejemplo de un conjunto de comandos completado:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Varios cambios de roles

Para varios cambios de roles, determine la siguiente información:
  
- Qué cuentas de usuario desea configurar. Puedes usar los métodos de la sección anterior para recopilar el conjunto de nombres para mostrar o UPN.
    
- Qué roles desea asignar a cada cuenta de usuario. Para mostrar la lista de roles disponibles que puede asignar a cuentas de usuario, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

A continuación, cree un archivo de texto de valores separados por comas (CSV) que tenga el nombre para mostrar o los campos UPN y nombre de rol. Puede hacerlo fácilmente en Microsoft Excel.

Este es un ejemplo de nombres para mostrar:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

A continuación, rellene la ubicación del archivo CSV y ejecute los comandos resultantes en el símbolo del sistema de PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Este es un ejemplo de UPN:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

A continuación, rellene la ubicación del archivo CSV y ejecute los comandos resultantes en el símbolo del sistema de PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>Vea también

- [Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
