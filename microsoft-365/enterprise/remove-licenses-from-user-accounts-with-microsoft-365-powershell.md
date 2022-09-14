---
title: Eliminación de licencias de Microsoft 365 de cuentas de usuario con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: Explica cómo usar PowerShell para quitar licencias de Microsoft 365 que se asignaron anteriormente a los usuarios.
ms.openlocfilehash: e726136fb2661d4855b3dcc828537b7be6e35c6c
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670727"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>Eliminación de licencias de Microsoft 365 de cuentas de usuario con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

>[!Note]
>[Obtenga información sobre cómo quitar licencias de cuentas de usuario](../admin/manage/remove-licenses-from-users.md) con el Centro de administración de Microsoft 365. Para obtener una lista de recursos adicionales, consulte [Administración de usuarios y grupos](/admin).
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Uso del SDK de PowerShell de Microsoft Graph

En primer lugar, [conéctese a su inquilino de Microsoft 365](/graph/powershell/get-started#authentication).

La asignación y eliminación de licencias para un usuario requiere el ámbito de permisos User.ReadWrite.All o uno de los demás permisos enumerados en la [página de referencia "Asignar licencia" Graph API](/graph/api/user-assignlicense).

El ámbito de permisos Organization.Read.All es necesario para leer las licencias disponibles en el inquilino.

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

Para ver la información del plan de licencias en su organización, consulte los temas siguientes:

- [Visualización de licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)

- [Visualización de los detalles de la licencia de cuenta y del servicio con PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)

### <a name="removing-licenses-from-user-accounts"></a>Eliminación de licencias de cuentas de usuario

Para quitar licencias de una cuenta de usuario existente, utilice la sintaxis siguiente:
  
```powershell
Set-MgUserLicense -UserId "<Account>" -RemoveLicenses @("<AccountSkuId1>") -AddLicenses @{}
```

En este ejemplo se quita el plan de licencias de **SPE_E5** (Microsoft 365 E5) del usuario **BelindaN@litwareinc.com**:

```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
Set-MgUserLicense -UserId "belindan@litwareinc.com" -RemoveLicenses @($e5Sku.SkuId) -AddLicenses @{}
```

Para quitar todas las licencias de un grupo de usuarios con licencia existentes, use la sintaxis siguiente:

```powershell
$licensedUsers = Get-MgUser -Filter 'assignedLicenses/$count ne 0' `
    -ConsistencyLevel eventual -CountVariable licensedUserCount -All `
    -Select UserPrincipalName,DisplayName,AssignedLicenses

foreach($user in $licensedUsers)
{
    $licencesToRemove = $user.AssignedLicenses | Select -ExpandProperty SkuId
    $user = Set-MgUserLicense -UserId $user.UserPrincipalName -RemoveLicenses $licencesToRemove -AddLicenses @{} 
}
```

Otra forma de liberar una licencia consiste en eliminar la cuenta de usuario. Para obtener más información, consulte [Eliminación y restauración de cuentas de usuario con PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

>El cmdlet Set-AzureADUserLicense está programado para retirarse. Migre los scripts al cmdlet de Set-MgUserLicense del SDK de Microsoft Graph, como se describió anteriormente. Para obtener más información, consulte [Migración de aplicaciones para acceder a las API de administración de licencias desde Microsoft Graph](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366).
>

En primer lugar, [conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

A continuación, enumere los planes de licencia del inquilino con este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

A continuación, obtenga el nombre de inicio de sesión de la cuenta para la que desea quitar una licencia, también conocida como nombre principal de usuario (UPN).

Por último, especifique los nombres de inicio de sesión de usuario y plan de licencia, quite los caracteres "<" y ">" y ejecute estos comandos.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

Para quitar todas las licencias de una cuenta de usuario específica, especifique el nombre de inicio de sesión de usuario, quite los caracteres "<" y ">" y ejecute estos comandos.

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

>[!Note]
>Los cmdlets Set-MsolUserLicense y New-MsolUser (-LicenseAssignment) están programados para retirarse. Migre los scripts al cmdlet de Set-MgUserLicense del SDK de Microsoft Graph, como se describió anteriormente. Para obtener más información, consulte [Migración de aplicaciones para acceder a las API de administración de licencias desde Microsoft Graph](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366).
>

En primer lugar, [conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
   
Para ver la información del plan de licencias (**AccountSkuID**) de su organización, vea los temas siguientes:
    
  - [Visualización de licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [Visualización de los detalles de la licencia de cuenta y del servicio con PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Si usa el cmdlet **Get-MsolUser** sin usar el parámetro _All_, solo se devuelven las 500 primeras cuentas.
    
### <a name="removing-licenses-from-user-accounts"></a>Eliminación de licencias de cuentas de usuario

Para quitar licencias de una cuenta de usuario existente, utilice la sintaxis siguiente:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

En este ejemplo se quita la licencia **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) de la cuenta de usuario BelindaN@litwareinc.com.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>No se puede usar el cmdlet para anular la `Set-MsolUserLicense` asignación de usuarios de licencias *canceladas* . Debe hacerlo individualmente para cada cuenta de usuario de la Centro de administración de Microsoft 365.
>

Para quitar todas las licencias de un grupo de usuarios con licencia existentes, use cualquiera de los métodos siguientes:
  
- **Filtrar las cuentas en función de un atributo de cuenta existente** Para ello, use la sintaxis siguiente:
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

En este ejemplo se quitan todas las licencias de todas las cuentas de usuario del departamento de ventas de la Estados Unidos.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **Uso de una lista de cuentas específicas para una licencia específica** Para ello, siga estos pasos:
    
1. Cree y guarde un archivo de texto que contenga una cuenta en cada línea de esta manera:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. Utilice la sintaxis siguiente:
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
En este ejemplo se quita la licencia **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) de las cuentas de usuario definidas en el archivo de texto C:\My Documents\Accounts.txt.
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

Para quitar todas las licencias de todas las cuentas de usuario existentes, use la sintaxis siguiente:
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

Otra forma de liberar una licencia consiste en eliminar la cuenta de usuario. Para obtener más información, consulte [Eliminación y restauración de cuentas de usuario con PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).
  
## <a name="see-also"></a>Vea también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
