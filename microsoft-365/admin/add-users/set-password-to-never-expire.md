---
title: Establecer la contraseña de un usuario individual para que nunca expire
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Inicie sesión en su cuenta Microsoft 365 administrador para establecer algunas contraseñas de usuario individuales para que nunca expiren mediante Windows PowerShell.
ms.openlocfilehash: c9f0c245aca0e028183c42f6a257068d74aa563d
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326728"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Establecer la contraseña de un usuario individual para que nunca expire

En este artículo se explica cómo establecer una contraseña para que un usuario individual no expire. Debe completar estos pasos con PowerShell.

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](../../business-video/admin-center-overview.md).

Debe ser administrador global o administrador [de contraseñas](about-admin-roles.md) para realizar estos pasos.

Un administrador global de un servicio en la nube de Microsoft puede usar el Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2) para Graph para establecer las contraseñas para que no expiren para usuarios específicos. También puede usar cmdlets [de AzureAD](/powershell/module/Azuread) para quitar la configuración que no expira nunca o para ver qué contraseñas de usuario están configuradas para que nunca expiren.

Esta guía se aplica a otros proveedores, como Intune y Microsoft 365, que también dependen de Azure AD para los servicios de directorio y identidad. La expiración de contraseña es la única parte de la directiva que se puede cambiar.


## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Cómo comprobar la directiva de expiración de una contraseña

Para obtener más información acerca del Get-AzureADUser en el módulo AzureAD, vea el artículo de referencia [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser).

Ejecute uno de los siguientes comandos:

- Para ver si la contraseña de un único usuario está establecida para que nunca expire, ejecute el siguiente cmdlet mediante el UPN (por ejemplo, *user@contoso.onmicrosoft.com*) o el identificador de usuario del usuario que desea comprobar:

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

- Para ver la **configuración Contraseña nunca expira** para todos los usuarios, ejecute el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Para obtener un informe de todos los usuarios con PasswordNeverExpires en Html en el escritorio del usuario actual con el nombre  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- Para obtener un informe de todos los usuarios con PasswordNeverExpires en CSV en el escritorio del usuario actual con el nombre **ReportPasswordNeverExpires.csv**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- Para establecer las contraseñas de todos los usuarios de una organización para que nunca expiren, ejecute el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Cuentas de usuario configuradas con `-PasswordPolicies DisablePasswordExpiration` el parámetro todavía antigüedad en función del `pwdLastSet` atributo. Según el atributo, si cambia la expiración a , todas las contraseñas con `pwdLastSet` un pwdLastSet de más de 90 días requieren que el usuario las cambie la próxima vez que inicie `-PasswordPolicies None` sesión. Este cambio puede afectar a un gran número de usuarios.

### <a name="set-a-password-to-expire"></a>Establecer una contraseña para expirar

Ejecute uno de los siguientes comandos:

- Para establecer la contraseña de un usuario para que la contraseña expire, ejecute el siguiente cmdlet mediante el UPN o el identificador de usuario del usuario:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Para establecer las contraseñas de todos los usuarios de la organización para que expiren, use el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Contenido relacionado

[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)\
[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)\
[Establecer la directiva de expiración de contraseña para su organización](../manage/set-password-expiration-policy.md) (artículo)
