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
description: En este artículo, obtenga información sobre cómo usar PowerShell para Microsoft 365 de forma rápida y sencilla para asignar roles de administrador a las cuentas de usuario.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754203"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Asignar roles de administrador a las cuentas de usuario de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede asignar roles fácilmente a las cuentas de usuario con PowerShell para Microsoft 365.

>[!Note]
>Obtenga información sobre cómo  [asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) a las cuentas de usuario con el centro de administración de Microsoft 365.
>
>Para obtener una lista de recursos adicionales, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer lugar, use una cuenta de administrador global para [conectarse a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
A continuación, identifique el nombre de inicio de sesión de la cuenta de usuario que desea agregar a un rol (ejemplo: fredsm \@ contoso.com). Esto también se conoce como el nombre principal de usuario (UPN).

A continuación, determine el nombre de la función. Consulte [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Preste atención a las notas de este artículo. Algunos nombres de rol son diferentes para Azure Active Directory (Azure AD) PowerShell. Por ejemplo, el rol de *Administrador de SharePoint* en el centro de administración de Microsoft 365 es el administrador de *servicios de SharePoint* en Azure ad PowerShell.
>

Después, rellene los nombres de inicio de sesión y de rol y ejecute estos comandos:
  
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

A continuación, se muestra un ejemplo de un conjunto de comandos completado que asigna el rol de administrador de servicios de SharePoint a la cuenta * \@ contoso.com de Laura* :
  
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

En primer lugar, use una cuenta de administrador global para [conectarse a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
### <a name="for-a-single-role-change"></a>Para un cambio de función único

Las formas más comunes de especificar la cuenta de usuario es mediante el uso de su nombre para mostrar o su nombre de correo electrónico, que también se conoce como el nombre de inicio de sesión o el nombre principal del usuario (UPN).

#### <a name="display-names-of-user-accounts"></a>Mostrar los nombres de las cuentas de usuario

Si se usa para trabajar con los nombres para mostrar de las cuentas de usuario, determine la siguiente información:
  
- La cuenta de usuario que desea configurar
    
    Para especificar la cuenta de usuario, debe determinar su nombre para mostrar. Para obtener una lista completa de las cuentas, use este comando:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Este comando muestra el nombre para mostrar de las cuentas de usuario, ordenados por nombre para mostrar, de una en una pantalla cada vez. Puede filtrar la lista para un conjunto más pequeño con el cmdlet **Where** . Vea el ejemplo siguiente.

   >[!Note]
   >PowerShell Core no es compatible con el módulo Microsoft Azure Active Directory para el módulo y los cmdlets de Windows PowerShell con *msol* en su nombre. Ejecute estos cmdlets de Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Este comando muestra sólo las cuentas de usuario para las que el nombre para mostrar empieza por "John".
    
- El rol que desea asignar
    
    Para mostrar la lista de roles de administrador disponibles que puede asignar a las cuentas de usuario, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Después de determinar el nombre para mostrar de la cuenta y el nombre de la función, use estos comandos para asignar el rol a la cuenta:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Pegue los comandos en el Bloc de notas. Para las variables *$dispName* y *$roleName* , reemplace el texto de la descripción con sus valores. Quite los \< and > caracteres pero mantenga las comillas. Pegue las líneas modificadas en la ventana Módulo Microsoft Azure Active Directory para Windows PowerShell para ejecutarlas. Como alternativa, puede usar el entorno de script integrado (ISE) de Windows PowerShell.
  
A continuación, se muestra un ejemplo de un conjunto de comandos completado:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Nombres de inicio de sesión de cuentas de usuario

Si se usa para trabajar con los nombres de inicio de sesión o UPN de las cuentas de usuario, determine la siguiente información:
  
- El UPN de la cuenta de usuario
    
    Si no conoce el UPN, use este comando:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Este comando enumera el UPN de las cuentas de usuario, ordenados por UPN, de una en una pantalla a la vez. Puede usar el cmdlet **Where** para filtrar la lista. Aquí le mostramos un ejemplo:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Este comando muestra sólo las cuentas de usuario para las que el nombre para mostrar empieza por "John".
    
- El rol que desea asignar
    
    Para mostrar la lista de los roles disponibles que puede asignar a las cuentas de usuario, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Una vez que tenga el UPN de la cuenta y el nombre del rol, use estos comandos para asignar el rol a la cuenta:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Copie los comandos y péguelos en el Bloc de notas. Para las variables **$upnName** y **$roleName** . Reemplace el texto de la descripción con sus valores. Quite los \< and > caracteres pero mantenga las comillas. Pegue las líneas modificadas en la ventana módulo de Microsoft Azure Active Directory para Windows PowerShell para ejecutarlas. Como alternativa, puede usar Windows PowerShell ISE.
  
A continuación, se muestra un ejemplo de un conjunto de comandos completado:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Varios cambios de funciones

Para varios cambios de funciones, determine la siguiente información:
  
- Qué cuentas de usuario desea configurar. Puede usar los métodos de la sección anterior para recopilar el conjunto de nombres para mostrar o UPN.
    
- Qué roles desea asignar a cada cuenta de usuario. Para mostrar la lista de los roles disponibles que puede asignar a las cuentas de usuario, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

A continuación, cree un archivo de texto de valores separados por comas (CSV) que tenga los campos nombre para mostrar o nombre de rol y UPN. Puede hacerlo fácilmente en Microsoft Excel.

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

Este es un ejemplo para los UPN:
  
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

## <a name="see-also"></a>Recursos adicionales

- [Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
