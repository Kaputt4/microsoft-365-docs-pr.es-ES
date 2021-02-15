---
title: Ver cuentas de usuario de Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Obtenga información sobre cómo ver, enumerar o mostrar sus cuentas de usuario de Microsoft 365 de diferentes maneras con PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754077"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Ver cuentas de usuario de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede usar el Centro de administración de Microsoft 365 para ver las cuentas de su inquilino de Microsoft 365. PowerShell para Microsoft 365 lo habilita, pero también proporciona funcionalidad adicional.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
### <a name="view-all-accounts"></a>Ver todas las cuentas

Para mostrar la lista completa de cuentas de usuario, ejecute este comando:
  
```powershell
Get-AzureADUser
```

Debería obtener información similar a esta:
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>Ver una cuenta específica

Para mostrar una cuenta de usuario específica, ejecute el siguiente comando. Rellene el nombre de la cuenta de inicio de sesión de la cuenta de usuario, que también se conoce como nombre principal de usuario (UPN). Quite los caracteres "<" y ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Aquí le mostramos un ejemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Ver valores de propiedad adicionales para una cuenta específica

De forma predeterminada, el cmdlet **Get-AzureADUser** solo muestra las propiedades *ObjectID*, *DisplayName* y *UserPrincipalName* de las cuentas.

Para ser más selectivo sobre las propiedades que se mostrarán, use el cmdlet **Select** en combinación con el cmdlet **Get-AzureADUser.** Para combinar los dos cmdlets, use el carácter de "canalización" ("|"), que indica a Azure Active Directory PowerShell para Graph que tome los resultados de un comando y lo envíe al siguiente comando. Este es un comando de ejemplo que muestra *DisplayName*, *Department* y *UsageLocation* para cada cuenta de usuario:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al siguiente comando ( **|** ).
    
1.  Mostrar solo el nombre de la cuenta de usuario, el departamento y la ubicación de uso (**Select DisplayName, Department, UsageLocation**).
  
Para ver todas las propiedades de una cuenta de usuario específica, use el cmdlet **Select** y el carácter comodín (*). Aquí le mostramos un ejemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Como otro ejemplo, ejecute el siguiente comando para comprobar el estado habilitado de una cuenta de usuario específica:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Ver el estado de sincronización de la cuenta

Las cuentas de usuario tienen dos orígenes: 

- Windows Server Active Directory (AD), que son cuentas que se sincronizan de AD local a la nube.

- Cuentas de Azure Active Directory (Azure AD) AD, que se crean directamente en la nube.


El siguiente comando indica a PowerShell que obtenga todos los usuarios que tengan el atributo *DirSyncEnabled* establecido en *True*. Puedes usarlo para buscar cuentas que se sincronizan desde AD local.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

El siguiente comando indica a PowerShell que obtenga todos los usuarios que tengan el atributo *DirSyncEnabled* establecido en *False*. Puedes usarlo para buscar cuentas solo de nube.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Ver cuentas basadas en una propiedad común

Para ser más selectivo con respecto a la lista de cuentas que se va a mostrar, puede usar el cmdlet **Where** en combinación con el cmdlet **Get-AzureADUser.** Para combinar los dos cmdlets, use el carácter de "canalización" ("|"), que indica a Azure Active Directory PowerShell para Graph que tome los resultados de un comando y lo envíe al siguiente comando. Este es un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Este comando indica a Azure Active Directory PowerShell para Graph que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al siguiente comando ( **|** ).
    
1. Busque todas las cuentas de usuario que tengan una ubicación de uso no especificada (**Where {$ \_ . UsageLocation -eq $Null}**). Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas para las que la propiedad de la cuenta de usuario UsageLocation (**$ \_ . UsageLocation**) no se especifica (**-eq $Null**).
    
La **propiedad UsageLocation** es solo una de las muchas propiedades asociadas a una cuenta de usuario. Para mostrar todas las propiedades de una cuenta de usuario específica, use el cmdlet **Select** y el carácter comodín (*). Aquí le mostramos un ejemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Por ejemplo, **City** es el nombre de una propiedad de la cuenta de usuario. Puede usar el siguiente comando para enumerar todas las cuentas de usuarios que viven en Londres:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  La sintaxis del cmdlet **Where** en estos ejemplos es **Where {$ \_ .** [nombre de propiedad de cuenta de usuario] [operador de comparación] [value] **}**.> [operador de comparación] es **-eq** para es igual a, **-ne** para no es igual a, **-lt** para menor que, **-gt** para mayor que y otros.  [value] suele ser una cadena (una secuencia de letras, números y otros caracteres), un valor numérico o $Null **para** no especificado. Para obtener más información, vea [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="view-all-accounts"></a>Ver todas las cuentas

Para mostrar la lista completa de cuentas de usuario, ejecute este comando:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre. Ejecute estos cmdlets desde Windows PowerShell.
>

Debería obtener información similar a esta:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

El cmdlet **Get-MsolUser** también tiene un conjunto de parámetros para filtrar el conjunto de cuentas de usuario que se muestran. Por ejemplo, para la lista de usuarios sin licencia (usuarios que se han agregado a Microsoft 365 pero que aún no tienen licencia para usar ninguno de los servicios), ejecute este comando:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Debería obtener información similar a esta:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Para obtener información acerca de los parámetros adicionales para filtrar el conjunto de cuentas de usuario que se muestran, vea [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Ver una cuenta específica

Para mostrar una cuenta de usuario específica, ejecute el siguiente comando. Rellene el nombre de inicio de sesión de la cuenta de usuario, que también se conoce como nombre principal de usuario (UPN). Quite los caracteres "<" y ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Ver cuentas basadas en una propiedad común

Para ser más selectivo con respecto a la lista de cuentas que se va a mostrar, puede usar el cmdlet **Where** en combinación con el cmdlet **Get-MsolUser.** Para combinar los dos cmdlets, use el carácter de "canalización" ("|"), que indica a PowerShell que tome los resultados de un comando y lo envíe al comando siguiente. Este es un ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al siguiente comando ( **|** ).
    
1. Busque todas las cuentas de usuario que tengan una ubicación de uso no especificada (**Donde {$ \_ . UsageLocation -eq $Null}**). Dentro de las llaves, el comando indica a PowerShell que busque solo el conjunto de cuentas para las que la propiedad de la cuenta de usuario UsageLocation (**$ \_ . UsageLocation**) no se especifica (**-eq $Null**).
    
Debería obtener información similar a esta:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

La *propiedad UsageLocation* es solo una de las muchas propiedades asociadas a una cuenta de usuario. Para ver todas las propiedades de las cuentas de usuario, use el cmdlet **Select** y el carácter comodín (*) para mostrarlas todas para una cuenta de usuario específica. Aquí le mostramos un ejemplo:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Por ejemplo, *City* es el nombre de una propiedad de la cuenta de usuario. Puede usar el siguiente comando para enumerar todas las cuentas de usuario de los usuarios que viven en Londres:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  La sintaxis del cmdlet **Where** en estos ejemplos es **Where {$ \_ .** [nombre de propiedad de cuenta de usuario] [operador de comparación] [value] **}**.  [operador de comparación] es **-eq** para igual a, **-ne** para no es igual a, **-lt** para menor que, **-gt** para mayor que y otros.  [value] suele ser una cadena (una secuencia de letras, números y otros caracteres), un valor numérico o $Null **para** no especificado. Para obtener más información, vea [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  
Para comprobar el estado bloqueado de una cuenta de usuario, use el siguiente comando:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Ver valores de propiedad adicionales para cuentas

De forma predeterminada, el cmdlet **Get-MsolUser** muestra estas tres propiedades de cuentas de usuario:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Si necesita propiedades adicionales, como el departamento donde trabaja el usuario y el país o región donde usan los servicios de Microsoft 365, puede ejecutar **Get-MsolUser** en combinación con el cmdlet **Select** para especificar la lista de propiedades de la cuenta de usuario. Aquí le mostramos un ejemplo:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información acerca de las cuentas de usuario (**Get-MsolUser**) y envíela al siguiente comando ( **|** ).
    
1. Mostrar solo el nombre de la cuenta de usuario, el departamento y la ubicación de uso (**Select DisplayName, Department, UsageLocation**).
    
Debería obtener información similar a esta:
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

El cmdlet **Select** le permite elegir qué propiedades mostrar. Para mostrar todas las propiedades de una cuenta de usuario específica, use el carácter comodín (*). Aquí le mostramos un ejemplo:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Para ser más selectivo con respecto a la lista de cuentas que se va a mostrar, también puede usar el cmdlet **Where.** Este es un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Este comando indica a PowerShell que:
  
1. Obtenga toda la información acerca de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).
    
1. Busque todas las cuentas de usuario que tengan una ubicación de uso no especificada (**Donde {$ \_ . UsageLocation -eq $Null}**) y envíe la información resultante al comando siguiente ( **|** ). Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas para las que la propiedad de la cuenta de usuario UsageLocation (**$ \_ . UsageLocation**) no se especifica (**-eq $Null**).
    
1. Mostrar solo el nombre de la cuenta de usuario, el departamento y la ubicación de uso (**Select DisplayName, Department, UsageLocation**).
    
Debería obtener información similar a esta:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Si usa la sincronización de directorios para crear y administrar los usuarios de Microsoft 365, puede mostrar la cuenta local desde la que se ha proyectado un usuario de Microsoft 365. En el siguiente ejemplo se supone que:

- Azure AD Connect está configurado para usar el delimitador de origen predeterminado de ObjectGUID. (Para obtener más información acerca de cómo configurar un delimitador de origen, [vea Azure AD Connect: conceptos de diseño).](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)
- Se ha instalado el módulo de Servicios de dominio de Active Directory para PowerShell (vea [herramientas RSAT).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Vea también

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
