---
title: Establecer la contraseña de un usuario individual que nunca caduque
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Obtenga información sobre cómo establecer contraseñas de usuario individuales para que no expiren nunca, mediante Windows PowerShell.
ms.openlocfilehash: e778ad8a020a6767934d51f8bc227bfc39b13a9b
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580921"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="08285-103">Establecer la contraseña de un usuario individual que nunca caduque</span><span class="sxs-lookup"><span data-stu-id="08285-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="08285-104">En este artículo se explica cómo establecer una contraseña para que un usuario individual no expire.</span><span class="sxs-lookup"><span data-stu-id="08285-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="08285-105">Debe completar estos pasos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08285-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="08285-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="08285-106">Before you begin</span></span>

<span data-ttu-id="08285-107">Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro.</span><span class="sxs-lookup"><span data-stu-id="08285-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="08285-108">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08285-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="08285-109">[¿Qué es una cuenta de administrador?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="08285-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="08285-110">Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para poder realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="08285-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="08285-111">Un administrador global de un servicio de nube de Microsoft puede usar [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) para establecer que las contraseñas no expiren para determinados usuarios.</span><span class="sxs-lookup"><span data-stu-id="08285-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="08285-112">También puede usar cmdlets de [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) para quitar la configuración nunca expirada o para ver las contraseñas de usuario que están configuradas para que no expiren nunca.</span><span class="sxs-lookup"><span data-stu-id="08285-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="08285-113">Esta guía se aplica a otros proveedores, como Intune y Microsoft 365, que también dependen de Azure AD para los servicios de identidad y directorio.</span><span class="sxs-lookup"><span data-stu-id="08285-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="08285-114">La expiración de la contraseña es la única parte de la Directiva que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="08285-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="08285-115">Solo se pueden configurar para que no expiren las contraseñas de las cuentas de usuario que no se sincronizan mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="08285-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="08285-116">Para obtener más información acerca de la sincronización de directorios, consulte [conectar ad con Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="08285-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="08285-117">Cómo comprobar la Directiva de expiración de una contraseña</span><span class="sxs-lookup"><span data-stu-id="08285-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="08285-118">Para obtener más información acerca del comando Get-AzureADUser en el módulo AzureAD, vea el artículo de referencia [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="08285-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="08285-119">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="08285-119">Run one of the following commands:</span></span>

- <span data-ttu-id="08285-120">Para ver si la contraseña de un solo usuario está configurada para que no expire nunca, ejecute el siguiente cmdlet mediante el UPN (por ejemplo, *user@contoso.onmicrosoft.com*) o el identificador de usuario del usuario que desea comprobar:</span><span class="sxs-lookup"><span data-stu-id="08285-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="08285-121">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="08285-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="08285-122">Para ver la configuración de la **contraseña nunca caduca** para todos los usuarios, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="08285-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="08285-123">Para obtener un informe de todos los usuarios con PasswordNeverExpires en HTML en el escritorio del usuario actual con el nombre  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="08285-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="08285-124">Para obtener un informe de todos los usuarios con PasswordNeverExpires en CSV en el escritorio del usuario actual con el nombre **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="08285-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="08285-125">Para configurar las contraseñas de todos los usuarios de una organización para que no expiren nunca, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="08285-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="08285-126">Establecer una contraseña de expiración</span><span class="sxs-lookup"><span data-stu-id="08285-126">Set a password to expire</span></span>

<span data-ttu-id="08285-127">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="08285-127">Run one of the following commands:</span></span>

- <span data-ttu-id="08285-128">Para establecer la contraseña de un usuario para que expire la contraseña, ejecute el siguiente cmdlet mediante el UPN o el identificador de usuario del usuario:</span><span class="sxs-lookup"><span data-stu-id="08285-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="08285-129">Para establecer las contraseñas de todos los usuarios de la organización para que expiren, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="08285-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="08285-130">Cuentas de usuario configuradas con el `-PasswordPolicies DisablePasswordExpiration` parámetro vigencia aún en función del atributo de la `pwdLastSet` cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="08285-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="08285-131">Por ejemplo, si establece contraseñas de usuario para que nunca expiren y, a continuación, 90 o más días, las contraseñas seguirán expirando.</span><span class="sxs-lookup"><span data-stu-id="08285-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="08285-132">Según el `pwdLastSet` atributo de la cuenta de usuario, para las cuentas de usuario configuradas con el `-PasswordPolicies None` parámetro, todas las contraseñas con una `pwdLastSet` antigüedad superior a 90 días requieren que el usuario las cambie la próxima vez que inicie sesión. Este cambio puede afectar a un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="08285-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="08285-133">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="08285-133">Related content</span></span>

[<span data-ttu-id="08285-134">Permitir que los usuarios puedan restablecer sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="08285-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="08285-135">Restablecer contraseñas</span><span class="sxs-lookup"><span data-stu-id="08285-135">Reset passwords</span></span>](../add-users/reset-passwords.md)