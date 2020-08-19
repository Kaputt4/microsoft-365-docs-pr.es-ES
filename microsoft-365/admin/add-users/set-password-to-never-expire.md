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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Obtenga información sobre cómo establecer contraseñas de usuario individuales para que no expiren nunca, mediante Windows PowerShell.
ms.openlocfilehash: f85eb2d3aaf5b19779ea8f293e2cbdc28c1535aa
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804213"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="e7258-103">Establecer la contraseña de un usuario individual que nunca caduque</span><span class="sxs-lookup"><span data-stu-id="e7258-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="e7258-104">Cambiar la directiva de expiración de las contraseñas de la organización</span><span class="sxs-lookup"><span data-stu-id="e7258-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="e7258-105">En el centro de administración, vaya a la página de configuración de **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> .</span><span class="sxs-lookup"><span data-stu-id="e7258-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="e7258-106">En la parte superior de la página Configuración, seleccione **seguridad & privacidad**.</span><span class="sxs-lookup"><span data-stu-id="e7258-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="e7258-107">Establecer la **directiva de expiración de contraseña**</span><span class="sxs-lookup"><span data-stu-id="e7258-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="e7258-108">Si las contraseñas están configuradas para que no expiren nunca, haga clic en la casilla junto a **Establecer contraseñas de usuario para que expiren después de un número de días**.</span><span class="sxs-lookup"><span data-stu-id="e7258-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="e7258-109">Obtendrá la opción de especificar el número de días que deben transcurrir hasta la expiración de las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="e7258-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="e7258-110">Establecer la Directiva de expiración de contraseña para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="e7258-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="e7258-111">Un administrador global de un servicio de nube de Microsoft puede usar [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) para establecer que las contraseñas no expiren para determinados usuarios.</span><span class="sxs-lookup"><span data-stu-id="e7258-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="e7258-112">También puede usar cmdlets de [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) para quitar la configuración nunca expirada o para ver las contraseñas de usuario que están configuradas para que no expiren nunca.</span><span class="sxs-lookup"><span data-stu-id="e7258-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="e7258-113">Esta guía se aplica a otros proveedores, como Intune y Microsoft 365, que también dependen de Azure AD para los servicios de identidad y directorio.</span><span class="sxs-lookup"><span data-stu-id="e7258-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="e7258-114">La expiración de la contraseña es la única parte de la Directiva que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="e7258-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="e7258-115">Para obtener más información acerca de Azure AD PowerShell para Graph, consulte [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="e7258-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="e7258-116">Solo se pueden configurar para que no expiren las contraseñas de las cuentas de usuario que no se sincronizan mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="e7258-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="e7258-117">Para obtener más información acerca de la sincronización de directorios, consulte [conectar ad con Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="e7258-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="e7258-118">Cómo comprobar la Directiva de expiración de una contraseña</span><span class="sxs-lookup"><span data-stu-id="e7258-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="e7258-119">Para obtener más información sobre el comando Get-AzureADUser en el módulo AzureAD, vea el artículo de referencia [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="e7258-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="e7258-120">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e7258-120">Run one of the following commands:</span></span>

- <span data-ttu-id="e7258-121">Para ver si la contraseña de un solo usuario está configurada para que no expire nunca, ejecute el siguiente cmdlet mediante el UPN (por ejemplo, *user@contoso.onmicrosoft.com*) o el identificador de usuario del usuario que desea comprobar:</span><span class="sxs-lookup"><span data-stu-id="e7258-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="e7258-122">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7258-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="e7258-123">Para ver la configuración de la **contraseña nunca caduca** para todos los usuarios, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e7258-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="e7258-124">Para obtener un informe de todos los usuarios con PasswordNeverExpires en HTML en el escritorio del usuario actual con el nombre  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="e7258-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="e7258-125">Para obtener un informe de todos los usuarios con PasswordNeverExpires en CSV en el escritorio del usuario actual con el nombre **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="e7258-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="e7258-126">Establecer una contraseña de expiración</span><span class="sxs-lookup"><span data-stu-id="e7258-126">Set a password to expire</span></span>

<span data-ttu-id="e7258-127">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e7258-127">Run one of the following commands:</span></span>

- <span data-ttu-id="e7258-128">Para establecer la contraseña de un usuario para que expire la contraseña, ejecute el siguiente cmdlet mediante el UPN o el identificador de usuario del usuario:</span><span class="sxs-lookup"><span data-stu-id="e7258-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="e7258-129">Para establecer las contraseñas de todos los usuarios de la organización para que expiren, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e7258-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="e7258-130">Establecer una contraseña para que nunca expire</span><span class="sxs-lookup"><span data-stu-id="e7258-130">Set a password to never expire</span></span>

<span data-ttu-id="e7258-131">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e7258-131">Run one of the following commands:</span></span>

- <span data-ttu-id="e7258-132">Para establecer la contraseña de un usuario para que nunca expire, ejecute el siguiente cmdlet usando el UPN o el identificador de usuario del usuario:</span><span class="sxs-lookup"><span data-stu-id="e7258-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="e7258-133">Para configurar las contraseñas de todos los usuarios de una organización para que no expiren nunca, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e7258-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="e7258-134">Cuentas de usuario configuradas con el `-PasswordPolicies DisablePasswordExpiration` parámetro vigencia aún en función del atributo de la `pwdLastSet` cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e7258-134">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="e7258-135">Por ejemplo, si establece contraseñas de usuario para que nunca expiren y, a continuación, 90 o más días, las contraseñas seguirán expirando.</span><span class="sxs-lookup"><span data-stu-id="e7258-135">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="e7258-136">Según el `pwdLastSet` atributo de la cuenta de usuario, para las cuentas de usuario configuradas con el `-PasswordPolicies None` parámetro, todas las contraseñas con una `pwdLastSet` antigüedad superior a 90 días requieren que el usuario las cambie la próxima vez que inicie sesión. Este cambio puede afectar a un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="e7258-136">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>
