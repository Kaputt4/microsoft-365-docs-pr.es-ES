---
title: Administrar grupos de seguridad con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Obtenga información sobre cómo usar PowerShell para administrar grupos de seguridad.
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909507"
---
# <a name="manage-security-groups-with-powershell"></a>Administrar grupos de seguridad con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede usar PowerShell para Microsoft 365 como alternativa al Centro de administración de Microsoft 365 para administrar grupos de seguridad. 

En este artículo se describe la descripción, la creación, el cambio de configuración y la eliminación de grupos de seguridad. 

Cuando un bloque de comandos de este artículo requiera que especifique valores de variables, siga estos pasos.

1. Copie el bloque de comandos en el Portapapeles y péguelo en Bloc de notas o en el entorno de script integrado (ISE) de PowerShell.
2. Rellene los valores de variable y quite los caracteres "<" y ">".
3. Ejecute los comandos en la ventana de PowerShell o el ISE de PowerShell.

Consulte [Mantener la pertenencia a grupos de seguridad](maintain-group-membership-with-microsoft-365-powershell.md) para administrar la pertenencia a grupos con PowerShell.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="list-your-groups"></a>Enumerar los grupos

Use este comando para enumerar todos los grupos.

```powershell
Get-AzureADGroup
```
Use estos comandos para mostrar la configuración de un grupo específico por su nombre para mostrar.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Creación de un grupo nuevo

Use este comando para crear un nuevo grupo de seguridad.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>Cambiar la configuración de un grupo

Muestra la configuración del grupo con estos comandos.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

A continuación, use [el artículo Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) para determinar cómo cambiar una configuración.

### <a name="remove-a-security-group"></a>Quitar un grupo de seguridad

Use estos comandos para quitar un grupo de seguridad.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>Administrar los propietarios de un grupo de seguridad

Use estos comandos para mostrar los propietarios actuales de un grupo de seguridad.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Use estos comandos para agregar una cuenta de usuario por su nombre principal de usuario **(UPN)** a los propietarios actuales de un grupo de seguridad.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Use estos comandos para agregar una cuenta de usuario por su nombre **para** mostrar a los propietarios actuales de un grupo de seguridad.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Use estos comandos para quitar una cuenta de usuario por su **UPN** a los propietarios actuales de un grupo de seguridad.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Use estos comandos para quitar una cuenta de usuario por su nombre **para** mostrar a los propietarios actuales de un grupo de seguridad.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="list-your-groups"></a>Enumerar los grupos

Use este comando para enumerar todos los grupos.

```powershell
Get-MsolGroup
```
Use estos comandos para mostrar la configuración de un grupo específico por su nombre para mostrar.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Creación de un grupo nuevo

Use este comando para crear un nuevo grupo de seguridad.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>Cambiar la configuración de un grupo

Muestra la configuración del grupo con estos comandos.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

A continuación, use [el artículo Set-MsolGroup](/powershell/module/msonline/set-msolgroup) para determinar cómo cambiar una configuración.

### <a name="remove-a-security-group"></a>Quitar un grupo de seguridad

Use estos comandos para quitar un grupo de seguridad.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>Consulte también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)