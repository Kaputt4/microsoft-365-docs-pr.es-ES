---
title: Configurar Microsoft 365 de cuenta de usuario con PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Use PowerShell para Microsoft 365 para configurar las propiedades de cuentas de usuario individuales o varias en el Microsoft 365 inquilino.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911089"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Configurar Microsoft 365 de cuenta de usuario con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede usar el Centro Microsoft 365 administración para configurar las propiedades de las cuentas de usuario de su Microsoft 365 inquilino. En PowerShell, también puede hacerlo, además de otras cosas que no puede hacer en el Centro de administración.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

Para configurar las propiedades de las cuentas de usuario en el módulo Azure Active Directory PowerShell para Graph, use el cmdlet [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) y especifique las propiedades que se deben establecer o cambiar.

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Cambiar las propiedades de una cuenta de usuario específica

La cuenta se identifica con el *parámetro -ObjectID* y se establecen o cambian propiedades específicas mediante parámetros adicionales. Esta es una lista de los parámetros más comunes:
  
- -Department " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -GivenName " \<user first name> "
    
- -Surname " \<user last name> "
    
- -Mobile " \<mobile phone number> "
    
- -JobTitle " \<job title> "
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress " \<street address> "
    
- -City " \<city name> "
    
- -State " \<state name> "
    
- -PostalCode " \<postal code> "
    
- -Country " \<country name> "
    
- -TelephoneNumber " \<office phone number> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Este es el código de región o país de dos letras ISO 3166-1 alfa-2 (A2).
    
Para obtener parámetros adicionales, [vea Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .

>[!Note]
>Para poder asignar licencias a una cuenta de usuario, debe asignar una ubicación de uso.
>

Para mostrar el nombre principal de usuario de las cuentas de usuario, ejecute el siguiente comando.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al comando siguiente ( **|** ).
    
1. Ordena la lista de nombres de entidad de seguridad de usuario alfabéticamente (**Ordenar UserPrincipalName**) y envíala al comando siguiente ( **|** ).
    
1. Mostrar solo la propiedad Nombre de entidad de seguridad de usuario para cada cuenta (**Seleccionar UserPrincipalName**).

1. Mostrarlos de una pantalla a la vez (**Más**).
    
Para mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellido), ejecute los siguientes comandos. Rellene la *variable $userName* y quite los \< and > caracteres:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

En este ejemplo se muestra el nombre principal de usuario de la cuenta de usuario que tiene el nombre para mostrar *Caleb Sills*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Al usar una *variable $upn,* puede realizar cambios en cuentas individuales en función de su nombre para mostrar. Este es un ejemplo que establece la ubicación de uso de *Belinda Newman* en Francia. Pero especifica su nombre para mostrar en lugar de su nombre principal de usuario:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Cambiar las propiedades de todas las cuentas de usuario

Para cambiar las propiedades de todos los usuarios, puede usar una combinación de los cmdlets **Get-AzureADUser** y **Set-AzureADUser.** En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios a *Francia:*
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al comando siguiente ( **|** ).
    
1. Establezca la ubicación del usuario en Francia (**Set-AzureADUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Cambiar las propiedades de un conjunto específico de cuentas de usuario

Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar una combinación de los cmdlets **Get-AzureADUser**, **Where** y **Set-AzureADUser.** En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios del departamento de contabilidad a *Francia:*
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al comando siguiente ( **|** ).
    
1.  Busque todas las cuentas de usuario que tienen su *propiedad Department* establecida en "Accounting" (**Where {$_. Department -eq "Accounting"}**) y envíe la información resultante al comando siguiente ( **|** ).
    
1. Establezca la ubicación del usuario en Francia (**Set-AzureADUser -UsageLocation "FR"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

Para configurar las propiedades de las cuentas de usuario con el módulo Microsoft Azure Active Directory para Windows PowerShell, use el cmdlet **Set-MsolUser** y especifique las propiedades que se deben establecer o cambiar.

En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre. Ejecute estos cmdlets desde Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Cambiar las propiedades de una cuenta de usuario específica

Para configurar las propiedades de una cuenta de usuario específica, use el cmdlet [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) y especifique las propiedades que se deben establecer o cambiar. 

La cuenta se identifica con el *parámetro -UserPrincipalName* y se establecen o cambian propiedades específicas mediante parámetros adicionales. Esta es una lista de los parámetros más comunes.
  
- -City " \<city name> "
    
- -Country " \<country name> "
    
- -Department " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -Fax " \<fax number> "
    
- -FirstName " \<user first name> "
    
- -LastName " \<user last name> "
    
- -MobilePhone " \<mobile phone number> "
    
- -Office " \<office location> "
    
- -PhoneNumber " \<office phone number> "
    
- -PostalCode " \<postal code> "
    
- -PreferredLanguage " \<language> "
    
- -State " \<state name> "
    
- -StreetAddress " \<street address> "
    
- -Title " \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Este es el código de región o país de dos letras ISO 3166-1 alfa-2 (A2).
    
Para obtener parámetros adicionales, [vea Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).

Para ver los nombres principales de usuario de todos los usuarios, ejecute el siguiente comando:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).
    
1. Ordena la lista de nombres de entidad de seguridad de usuario alfabéticamente (**Ordenar UserPrincipalName**) y envíala al comando siguiente ( **|** ).
    
1. Mostrar solo la propiedad Nombre de entidad de seguridad de usuario para cada cuenta (**Seleccionar UserPrincipalName**).
    
1. Mostrarlos de una pantalla a la vez (**Más**).
    
Para mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellido), ejecute los siguientes comandos. Rellene la *variable $userName* y quite los \< and > caracteres.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

En este ejemplo se muestra el nombre principal de usuario del usuario denominado Caleb Sills:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Al usar una *variable $upn,* puede realizar cambios en cuentas individuales en función de su nombre para mostrar. Este es un ejemplo que establece la ubicación de uso de *Belinda Newman* en *Francia,* pero especifica su nombre para mostrar en lugar de su nombre principal de usuario:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Cambiar las propiedades de todas las cuentas de usuario

Para cambiar las propiedades de todos los usuarios, use una combinación de los cmdlets **Get-MsolUser** y **Set-MsolUser.** En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios a *Francia:*
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).
    
1. Establezca la ubicación del usuario en Francia (**Set-MsolUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Cambiar las propiedades de un conjunto específico de cuentas de usuario

Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar una combinación de los cmdlets **Get-MsolUser**, **Where** y **Set-MsolUser.** En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios del departamento de contabilidad a *Francia:*
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).
    
1. Busque todas las cuentas de usuario que tengan su *propiedad Department* establecida en "Accounting" (**Where {$_. Department -eq "Accounting"}**) y envía la información resultante al comando siguiente ( **|** ).
    
1. Establezca la ubicación del usuario en Francia (**Set-MsolUser -UsageLocation "FR"**).

## <a name="see-also"></a>Consulte también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)