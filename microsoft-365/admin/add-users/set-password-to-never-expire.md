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
ms.openlocfilehash: 1c44f5c4d5966d70b5fed0b1b99e69b2938c6ddd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245667"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="30797-103">Establecer la contraseña de un usuario individual que nunca caduque</span><span class="sxs-lookup"><span data-stu-id="30797-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="30797-104">Cambiar la directiva de expiración de las contraseñas de la organización</span><span class="sxs-lookup"><span data-stu-id="30797-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="30797-105">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">seguridad & privacidad</a> .</span><span class="sxs-lookup"><span data-stu-id="30797-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="30797-106">Junto a **Directiva de contraseñas** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="30797-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="30797-107">Si las contraseñas se configuran para que no expiren nunca, establezca el botón de alternancia en **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="30797-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="30797-108">Obtendrá la opción de especificar el número de días que deben transcurrir hasta la expiración de las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="30797-108">You'll get the option to specify the number of days until passwords expire.</span></span> 


## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="30797-109">Establecer la Directiva de expiración de contraseña para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="30797-109">Set the password expiration policy for individual users</span></span> 

<span data-ttu-id="30797-110">Un administrador global de un servicio de nube de Microsoft puede usar el módulo Microsoft Azure AD para Windows PowerShell para establecer contraseñas que no expirarán para determinados usuarios.</span><span class="sxs-lookup"><span data-stu-id="30797-110">A global admin for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set passwords not to expire for specific users.</span></span> <span data-ttu-id="30797-111">También puede usar los cmdlets de Windows PowerShell para quitar la configuración Never-Expires o para ver las contraseñas de usuario que están configuradas para que no expiren nunca.</span><span class="sxs-lookup"><span data-stu-id="30797-111">You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span> 

<span data-ttu-id="30797-112">Esta guía se aplica a otros proveedores, como Intune y Office 365, que también dependen de Azure AD para los servicios de identidad y directorio.</span><span class="sxs-lookup"><span data-stu-id="30797-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="30797-113">La expiración de la contraseña es la única parte de la Directiva que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="30797-113">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="30797-114">Solo se pueden configurar para que no expiren las contraseñas de las cuentas de usuario que no se sincronizan mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="30797-114">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="30797-115">Para obtener más información acerca de la sincronización de directorios, consulte [conectar ad con Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="30797-115">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>


### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="30797-116">Cómo comprobar la Directiva de expiración de una contraseña</span><span class="sxs-lookup"><span data-stu-id="30797-116">How to check the expiration policy for a password</span></span>

* <span data-ttu-id="30797-117">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="30797-117">Run one of the following commands:</span></span>

   * <span data-ttu-id="30797-118">Para ver si la contraseña de un solo usuario está configurada para que no expire nunca, ejecute el siguiente cmdlet mediante el UPN (por ejemplo, *user@contoso.onmicrosoft.com*) o el identificador de usuario del usuario que desea comprobar:</span><span class="sxs-lookup"><span data-stu-id="30797-118">To see if a single user’s password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
<span data-ttu-id="30797-119">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="30797-119">Example:</span></span>
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * <span data-ttu-id="30797-120">Para ver la configuración de la **contraseña nunca caduca** para todos los usuarios, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="30797-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span> 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* <span data-ttu-id="30797-121">Para obtener un informe de todos los usuarios con PasswordNeverExpires en HTML en el escritorio del usuario actual con el nombre **ReportPasswordNeverExpires. html**</span><span class="sxs-lookup"><span data-stu-id="30797-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* <span data-ttu-id="30797-122">Para obtener un informe de todos los usuarios con PasswordNeverExpires en CSV en el escritorio del usuario actual con el nombre **ReportPasswordNeverExpires. csv**</span><span class="sxs-lookup"><span data-stu-id="30797-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### <a name="set-a-password-to-expire"></a><span data-ttu-id="30797-123">Establecer una contraseña de expiración</span><span class="sxs-lookup"><span data-stu-id="30797-123">Set a password to expire</span></span>

<span data-ttu-id="30797-124">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="30797-124">Run one of the following commands:</span></span>

   * <span data-ttu-id="30797-125">Para establecer la contraseña de un usuario para que expire la contraseña, ejecute el siguiente cmdlet mediante el UPN o el identificador de usuario del usuario:</span><span class="sxs-lookup"><span data-stu-id="30797-125">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

```
 Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None

```
   * <span data-ttu-id="30797-126">Para establecer las contraseñas de todos los usuarios de la organización para que expiren, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="30797-126">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

```
 Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None

```
### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="30797-127">Establecer una contraseña para que nunca expire</span><span class="sxs-lookup"><span data-stu-id="30797-127">Set a password to never expire</span></span>

<span data-ttu-id="30797-128">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="30797-128">Run one of the following commands:</span></span>

   * <span data-ttu-id="30797-129">Para establecer la contraseña de un usuario para que nunca expire, ejecute el siguiente cmdlet usando el UPN o el identificador de usuario del usuario:</span><span class="sxs-lookup"><span data-stu-id="30797-129">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span> 

```
Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration

```
   * <span data-ttu-id="30797-130">Para configurar las contraseñas de todos los usuarios de una organización para que no expiren nunca, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="30797-130">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span> 

```
Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration

```
   > [!WARNING]
   > <span data-ttu-id="30797-131">Las contraseñas se `-PasswordPolicies DisablePasswordExpiration` establecen para que sigan siendo `pwdLastSet` obsoletas en función del atributo.</span><span class="sxs-lookup"><span data-stu-id="30797-131">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="30797-132">Si establece las contraseñas de usuario para que nunca expiren y, a continuación, 90 + días para, las contraseñas expirarán.</span><span class="sxs-lookup"><span data-stu-id="30797-132">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="30797-133">Según el `pwdLastSet` atributo, si cambia la expiración a `-PasswordPolicies None`, todas las contraseñas que tienen un `pwdLastSet` antigüedad de más de 90 días requieren que el usuario los cambie la próxima vez que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="30797-133">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="30797-134">Este cambio puede afectar a un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="30797-134">This change can affect a large number of users.</span></span> 
