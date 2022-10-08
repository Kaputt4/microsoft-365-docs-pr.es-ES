---
title: Establecer la contraseña de un usuario individual para que nunca expire
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Inicie sesión en su cuenta de administrador de Microsoft 365 para establecer que algunas contraseñas de usuario individuales nunca expiren mediante PowerShell de Azure AD.
ms.openlocfilehash: 27a5e5955267eb1a012c6dcb7618582b5256dc11
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191593"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Establecer la contraseña de un usuario individual para que nunca expire

En este artículo se explica cómo establecer una contraseña para que un usuario individual no expire. Debe completar estos pasos mediante PowerShell.

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. Consulte [Información general de la Centro de administración de Microsoft 365](/microsoft-365/admin/admin-overview/admin-center-overview).

Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para realizar estos pasos.

Un administrador global de un servicio en la nube de Microsoft puede usar [PowerShell de Azure Active Directory para Graph para](/powershell/azure/active-directory/install-adv2) establecer que las contraseñas no expiren para usuarios específicos. También puede usar cmdlets de [AzureAD](/powershell/module/Azuread) para quitar la configuración de nunca expira o para ver qué contraseñas de usuario están establecidas para que nunca expiren.

Esta guía se aplica a otros proveedores, como Intune y Microsoft 365, que también dependen de Azure AD para los servicios de identidad y directorio. La expiración de contraseña es la única parte de la directiva que se puede cambiar.

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Comprobación de la directiva de expiración para obtener una contraseña

Para obtener más información sobre el comando Get-AzureADUser en el módulo AzureAD, consulte el artículo [de referencia Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser).

Ejecute uno de los siguientes comandos:

- Para ver si la contraseña de un solo usuario está establecida en nunca expirar, ejecute el siguiente cmdlet mediante el UPN (por ejemplo, *user@contoso.onmicrosoft.com*) o el identificador de usuario del usuario que desea comprobar:

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

- Para ver la configuración **Contraseña nunca expira** para todos los usuarios, ejecute el siguiente cmdlet:

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

- Para establecer que las contraseñas de todos los usuarios de una organización no expiren nunca, ejecute el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Cuentas de usuario configuradas con el `-PasswordPolicies DisablePasswordExpiration` parámetro still age en función del `pwdLastSet` atributo . En función del `pwdLastSet` atributo , si cambia la expiración a `-PasswordPolicies None`, todas las contraseñas que tienen un pwdLastSet anterior a 90 días requieren que el usuario las cambie la próxima vez que inicie sesión. Este cambio puede afectar a un gran número de usuarios.

### <a name="set-a-password-to-expire"></a>Establecer una contraseña para expirar

Ejecute uno de los siguientes comandos:

- Para establecer la contraseña de un usuario para que expire, ejecute el siguiente cmdlet mediante el UPN o el identificador de usuario del usuario:

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
[Establecer la directiva de expiración de contraseñas para su organización](../manage/set-password-expiration-policy.md) (artículo)
