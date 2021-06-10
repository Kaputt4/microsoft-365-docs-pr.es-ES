---
title: Eliminar Microsoft 365 de usuario con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Obtenga información sobre cómo usar diferentes módulos en PowerShell para eliminar Microsoft 365 cuentas de usuario.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919145"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="41ca5-103">Eliminar Microsoft 365 de usuario con PowerShell</span><span class="sxs-lookup"><span data-stu-id="41ca5-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="41ca5-104">Puede usar PowerShell para Microsoft 365 para eliminar y restaurar cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="41ca5-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="41ca5-105">Obtenga información sobre [cómo restaurar una cuenta de usuario](../admin/add-users/restore-user.md) mediante el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="41ca5-105">Learn how to [restore a user account](../admin/add-users/restore-user.md) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="41ca5-106">Para obtener una lista de recursos adicionales, vea [Administrar usuarios y grupos.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="41ca5-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="41ca5-107">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="41ca5-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="41ca5-108">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="41ca5-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="41ca5-109">Después de conectarse, use la siguiente sintaxis para quitar una cuenta de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="41ca5-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="41ca5-110">En este ejemplo se quita la cuenta de *usuario fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="41ca5-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="41ca5-111">El *parámetro -ObjectID* del cmdlet **Remove-AzureADUser** acepta el nombre de inicio de sesión de la cuenta, también conocido como nombre principal de usuario o el identificador de objeto de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="41ca5-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="41ca5-112">Para mostrar el nombre de cuenta según el nombre de usuario, use los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="41ca5-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="41ca5-113">En este ejemplo se muestra el nombre de cuenta del usuario *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="41ca5-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="41ca5-114">Para eliminar una cuenta según el nombre para mostrar del usuario, use los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="41ca5-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="41ca5-115">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41ca5-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="41ca5-116">Al eliminar una cuenta de usuario a través del módulo Microsoft Azure Active Directory para Windows PowerShell, la cuenta no se elimina permanentemente.</span><span class="sxs-lookup"><span data-stu-id="41ca5-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="41ca5-117">Puede restaurar la cuenta de usuario eliminada durante los siguientes 30 días.</span><span class="sxs-lookup"><span data-stu-id="41ca5-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="41ca5-118">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="41ca5-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="41ca5-119">Para eliminar una cuenta de usuario, utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="41ca5-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="41ca5-120">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="41ca5-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="41ca5-121">Ejecute estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41ca5-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="41ca5-122">En este ejemplo se elimina la cuenta de *usuario BelindaN@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="41ca5-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="41ca5-123">Para restaurar una cuenta de usuario eliminada dentro del periodo de gracia de 30 días, utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="41ca5-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="41ca5-124">En este ejemplo se restaura la cuenta *eliminada BelindaN \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="41ca5-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="41ca5-125">Para ver la lista de usuarios eliminados que pueden restaurarse, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="41ca5-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="41ca5-126">Si otra cuenta usa el nombre principal de usuario original de la cuenta de usuario, use el parámetro _NewUserPrincipalName_ en vez de _UserPrincipalName_ para especificar un nombre principal de usuario al restaurar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="41ca5-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="41ca5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="41ca5-127">See also</span></span>

[<span data-ttu-id="41ca5-128">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="41ca5-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="41ca5-129">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="41ca5-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="41ca5-130">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41ca5-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)