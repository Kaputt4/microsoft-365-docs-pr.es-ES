---
title: Establecer la contraseña de un usuario individual que nunca caduque
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Obtenga información sobre cómo establecer contraseñas de usuario individuales para que no expiren nunca, mediante Windows PowerShell.
ms.openlocfilehash: 275fedf7bf4e52320b769689516ad39a31c63ea1
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105740"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Establecer la contraseña de un usuario individual que nunca caduque

## <a name="set-the-password-expiration-policy-for-your-organization"></a>Cambiar la directiva de expiración de las contraseñas de la organización

1. En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">seguridad & privacidad</a> .
2. Junto a **Directiva de contraseñas** , seleccione **Editar**. 
3. Si las contraseñas se configuran para que no expiren nunca, establezca el botón de alternancia en **desactivado**. Obtendrá la opción de especificar el número de días que deben transcurrir hasta la expiración de las contraseñas.

## <a name="set-the-password-expiration-policy-for-individual-users"></a>Establecer la Directiva de expiración de contraseña para usuarios individuales

Un administrador global de un servicio de nube de Microsoft puede usar el módulo Microsoft Azure AD para Windows PowerShell para establecer contraseñas que no expirarán para determinados usuarios. También puede usar los cmdlets de Windows PowerShell para quitar la configuración Never-Expires o para ver las contraseñas de usuario que están configuradas para que no expiren nunca.

Esta guía se aplica a otros proveedores, como Intune y Office 365, que también dependen de Azure AD para los servicios de identidad y directorio. La expiración de la contraseña es la única parte de la Directiva que se puede cambiar.

> [!NOTE]
> Solo se pueden configurar para que no expiren las contraseñas de las cuentas de usuario que no se sincronizan mediante la sincronización de directorios. Para obtener más información acerca de la sincronización de directorios, consulte [conectar ad con Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>Cómo comprobar la Directiva de expiración de una contraseña
Ejecute uno de los siguientes comandos:

- Para ver si la contraseña de un solo usuario está configurada para que no expire nunca, ejecute el siguiente cmdlet mediante el UPN (por ejemplo, *user@contoso.onmicrosoft.com*) o el identificador de usuario del usuario que desea comprobar:

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    Ejemplo:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- Para ver la configuración de la **contraseña nunca caduca** para todos los usuarios, ejecute el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Para obtener un informe de todos los usuarios con PasswordNeverExpires en HTML en el escritorio del usuario actual con el nombre **ReportPasswordNeverExpires. html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Para obtener un informe de todos los usuarios con PasswordNeverExpires en CSV en el escritorio del usuario actual con el nombre **ReportPasswordNeverExpires. csv**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a>Establecer una contraseña de expiración

Ejecute uno de los siguientes comandos:

- Para establecer la contraseña de un usuario para que expire la contraseña, ejecute el siguiente cmdlet mediante el UPN o el identificador de usuario del usuario:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Para establecer las contraseñas de todos los usuarios de la organización para que expiren, use el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a>Establecer una contraseña para que nunca expire

Ejecute uno de los siguientes comandos:

- Para establecer la contraseña de un usuario para que nunca expire, ejecute el siguiente cmdlet usando el UPN o el identificador de usuario del usuario:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- Para configurar las contraseñas de todos los usuarios de una organización para que no expiren nunca, ejecute el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Las contraseñas se `-PasswordPolicies DisablePasswordExpiration` establecen para que sigan siendo `pwdLastSet` obsoletas en función del atributo. Si establece las contraseñas de usuario para que nunca expiren y, a continuación, 90 + días para, las contraseñas expirarán. Según el `pwdLastSet` atributo, si cambia la expiración a `-PasswordPolicies None`, todas las contraseñas que tienen un `pwdLastSet` antigüedad de más de 90 días requieren que el usuario los cambie la próxima vez que inicie sesión. Este cambio puede afectar a un gran número de usuarios.