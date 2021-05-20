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
description: Inicia sesión en tu cuenta de administrador de Microsoft 365 para establecer algunas contraseñas de usuario individuales para que nunca caduquen mediante Windows PowerShell.
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571930"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Establecer la contraseña de un usuario individual para que nunca expire

En este artículo se explica cómo establecer una contraseña para que un usuario individual no caduque. Debe completar estos pasos con PowerShell.

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](../../business-video/admin-center-overview.md). 

Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para realizar estos pasos.

Un administrador global de un servicio en la nube de Microsoft puede usar el [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) establecer contraseñas que no caducarán para usuarios específicos. También puede usar cmdlets [de AzureAD](/powershell/module/Azuread) para quitar la configuración que nunca caduca o para ver qué contraseñas de usuario están configuradas para que nunca caduquen.

Esta guía se aplica a otros proveedores, como Intune y Microsoft 365, que también dependen de Azure AD para servicios de identidad y directorio. La expiración de la contraseña es la única parte de la directiva que se puede cambiar.

> [!NOTE]
> Solo se pueden configurar contraseñas para cuentas de usuario que no estén sincronizadas mediante la sincronización de directorios para que no caduquen. Para obtener más información acerca de la sincronización de directorios, consulte [Conectar AD con Azure AD](/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Cómo comprobar la política de caducidad de una contraseña

Para obtener más información acerca del comando Get-AzureADUser en el módulo AzureAD, consulte el artículo de referencia [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Ejecute uno de los siguientes comandos:

- Para ver si la contraseña de un solo usuario está configurada para que nunca caduque, ejecute el siguiente cmdlet mediante UPN (por ejemplo, *user@contoso.onmicrosoft.com)* o el identificador de usuario del usuario que desea comprobar:

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

- Para ver la **configuración Contraseña nunca caduca** para todos los usuarios, ejecute el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Para obtener un informe de todos los usuarios con PasswordNeverExpires en Html en el escritorio del usuario actual con nombre  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Para obtener un informe de todos los usuarios con PasswordNeverExpires en CSV en el escritorio del usuario actual con nombre **ReportPasswordNeverExpires.csv**

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

- Para establecer que las contraseñas de todos los usuarios de una organización nunca caducan, ejecute el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Las cuentas de usuario configuradas con el `-PasswordPolicies DisablePasswordExpiration` parámetro siguen siendo la antigüedad en función del `pwdLastSet` atributo. En función del `pwdLastSet` atributo, si cambia la expiración a `-PasswordPolicies None` , todas las contraseñas que tienen un pwdLastSet anterior a 90 días requieren que el usuario las cambie la próxima vez que inicie sesión. Este cambio puede afectar a un gran número de usuarios.

### <a name="set-a-password-to-expire"></a>Establezca una contraseña para que caduque

Ejecute uno de los siguientes comandos:

- Para establecer la contraseña de un usuario para que caduque la contraseña, ejecute el siguiente cmdlet mediante upn o el identificador de usuario del usuario:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Para establecer las contraseñas de todos los usuarios de la organización para que caduquen, use el siguiente cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Contenido relacionado

[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)

[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)