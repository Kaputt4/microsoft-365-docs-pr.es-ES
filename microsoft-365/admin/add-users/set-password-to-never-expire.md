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
ms.openlocfilehash: 12c717d8d625b0135f185b1af131db00e9762c73
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635563"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="12acd-103">Establecer la contraseña de un usuario individual para que nunca expire</span><span class="sxs-lookup"><span data-stu-id="12acd-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="12acd-104">En este artículo se explica cómo establecer una contraseña para que un usuario individual no expire.</span><span class="sxs-lookup"><span data-stu-id="12acd-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="12acd-105">Debe completar estos pasos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12acd-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="12acd-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="12acd-106">Before you begin</span></span>

<span data-ttu-id="12acd-107">Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro.</span><span class="sxs-lookup"><span data-stu-id="12acd-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="12acd-108">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12acd-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="12acd-109">[¿Qué es una cuenta de administrador?](../../business-video/admin-center-overview.md).</span><span class="sxs-lookup"><span data-stu-id="12acd-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="12acd-110">Debe ser administrador global o administrador [de contraseñas](about-admin-roles.md) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="12acd-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="12acd-111">Un administrador global de un servicio en la nube de Microsoft puede usar el Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) para Graph para establecer las contraseñas para que no expiren para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="12acd-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="12acd-112">También puede usar cmdlets [de AzureAD](/powershell/module/Azuread) para quitar la configuración que no expira nunca o para ver qué contraseñas de usuario están configuradas para que nunca expiren.</span><span class="sxs-lookup"><span data-stu-id="12acd-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="12acd-113">Esta guía se aplica a otros proveedores, como Intune y Microsoft 365, que también dependen de Azure AD para los servicios de directorio y identidad.</span><span class="sxs-lookup"><span data-stu-id="12acd-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="12acd-114">La expiración de contraseña es la única parte de la directiva que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="12acd-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="12acd-115">Solo se pueden configurar las contraseñas de cuentas de usuario que no estén sincronizadas mediante la sincronización de directorios para que no expiren.</span><span class="sxs-lookup"><span data-stu-id="12acd-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="12acd-116">Para obtener más información acerca de la sincronización de directorios, [vea Conectar AD con Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="12acd-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="12acd-117">Cómo comprobar la directiva de expiración de una contraseña</span><span class="sxs-lookup"><span data-stu-id="12acd-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="12acd-118">Para obtener más información acerca del Get-AzureADUser en el módulo AzureAD, vea el artículo de referencia [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="12acd-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="12acd-119">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="12acd-119">Run one of the following commands:</span></span>

- <span data-ttu-id="12acd-120">Para ver si la contraseña de un único usuario está establecida para que nunca expire, ejecute el siguiente cmdlet mediante el UPN (por ejemplo, *user@contoso.onmicrosoft.com*) o el identificador de usuario del usuario que desea comprobar:</span><span class="sxs-lookup"><span data-stu-id="12acd-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="12acd-121">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="12acd-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="12acd-122">Para ver la **configuración Contraseña nunca expira** para todos los usuarios, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="12acd-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="12acd-123">Para obtener un informe de todos los usuarios con PasswordNeverExpires en Html en el escritorio del usuario actual con el nombre  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="12acd-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="12acd-124">Para obtener un informe de todos los usuarios con PasswordNeverExpires en CSV en el escritorio del usuario actual con el nombre **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="12acd-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="12acd-125">Para establecer las contraseñas de todos los usuarios de una organización para que nunca expiren, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="12acd-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="12acd-126">Cuentas de usuario configuradas con `-PasswordPolicies DisablePasswordExpiration` el parámetro todavía antigüedad en función del `pwdLastSet` atributo.</span><span class="sxs-lookup"><span data-stu-id="12acd-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="12acd-127">Según el atributo, si cambia la expiración a , todas las contraseñas con `pwdLastSet` un pwdLastSet de más de 90 días requieren que el usuario las cambie la próxima vez que inicie `-PasswordPolicies None` sesión.</span><span class="sxs-lookup"><span data-stu-id="12acd-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="12acd-128">Este cambio puede afectar a un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="12acd-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="12acd-129">Establecer una contraseña para expirar</span><span class="sxs-lookup"><span data-stu-id="12acd-129">Set a password to expire</span></span>

<span data-ttu-id="12acd-130">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="12acd-130">Run one of the following commands:</span></span>

- <span data-ttu-id="12acd-131">Para establecer la contraseña de un usuario para que la contraseña expire, ejecute el siguiente cmdlet mediante el UPN o el identificador de usuario del usuario:</span><span class="sxs-lookup"><span data-stu-id="12acd-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="12acd-132">Para establecer las contraseñas de todos los usuarios de la organización para que expiren, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="12acd-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="12acd-133">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="12acd-133">Related content</span></span>

<span data-ttu-id="12acd-134">[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="12acd-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="12acd-135">[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="12acd-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="12acd-136">[Establecer la directiva de expiración de contraseña para su organización](../manage/set-password-expiration-policy.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="12acd-136">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>