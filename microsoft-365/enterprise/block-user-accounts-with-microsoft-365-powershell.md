---
title: Bloquear Microsoft 365 de usuario con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Cómo usar PowerShell para bloquear y desbloquear el acceso a Microsoft 365 cuentas.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754685"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="e8134-103">Bloquear Microsoft 365 de usuario con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8134-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="e8134-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e8134-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e8134-105">Cuando bloquea el acceso a una cuenta Microsoft 365, impide que cualquier usuario use la cuenta para iniciar sesión y obtener acceso a los servicios y datos de su Microsoft 365 organización.</span><span class="sxs-lookup"><span data-stu-id="e8134-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="e8134-106">Puede usar PowerShell para bloquear el acceso a cuentas individuales o de varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="e8134-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e8134-107">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="e8134-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e8134-108">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="e8134-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="e8134-109">Bloquear el acceso a cuentas de usuario individuales</span><span class="sxs-lookup"><span data-stu-id="e8134-109">Block access to individual user accounts</span></span>

<span data-ttu-id="e8134-110">Use la siguiente sintaxis para bloquear una cuenta de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="e8134-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="e8134-111">El *parámetro -ObjectID* del cmdlet **Set-AzureAD** acepta el nombre de inicio de sesión de la cuenta, también conocido como nombre principal de usuario, o el identificador de objeto de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e8134-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="e8134-112">En este ejemplo se bloquea el acceso a la cuenta de *usuario fabricec@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="e8134-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="e8134-113">Para desbloquear esta cuenta de usuario, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e8134-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="e8134-114">Para mostrar el UPN de la cuenta de usuario en función del nombre para mostrar del usuario, use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e8134-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="e8134-115">En este ejemplo se muestra el UPN de la cuenta de usuario para el  *usuario Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="e8134-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e8134-116">Para bloquear una cuenta en función del nombre para mostrar del usuario, use los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e8134-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="e8134-117">Para comprobar el estado bloqueado de una cuenta de usuario, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e8134-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="e8134-118">Bloquear varias cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e8134-118">Block multiple user accounts</span></span>

<span data-ttu-id="e8134-119">Para bloquear el acceso a varias cuentas de usuario, cree un archivo de texto que contenga un nombre de inicio de sesión de cuenta en cada línea como esta:</span><span class="sxs-lookup"><span data-stu-id="e8134-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="e8134-120">En los siguientes comandos, el archivo de texto de ejemplo es *C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="e8134-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="e8134-121">Reemplace este nombre de archivo por la ruta de acceso y el nombre del archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e8134-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="e8134-122">Para bloquear el acceso a las cuentas enumeradas en el archivo de texto, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e8134-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="e8134-123">Para desbloquear las cuentas que aparecen en el archivo de texto, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e8134-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e8134-124">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8134-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e8134-125">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e8134-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="e8134-126">Bloquear cuentas de usuario individuales</span><span class="sxs-lookup"><span data-stu-id="e8134-126">Block individual user accounts</span></span>

<span data-ttu-id="e8134-127">Use la siguiente sintaxis para bloquear el acceso a una cuenta de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="e8134-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="e8134-128">PowerShell Core no admite el módulo Microsoft Azure Active Directory para Windows PowerShell y cmdlets que tienen *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e8134-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="e8134-129">Debe ejecutar estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8134-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="e8134-130">En este ejemplo se bloquea el acceso a la cuenta de *usuario fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="e8134-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="e8134-131">Para desbloquear la cuenta de usuario, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e8134-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="e8134-132">Para comprobar el estado bloqueado de una cuenta de usuario, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e8134-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="e8134-133">Bloquear el acceso a varias cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e8134-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="e8134-134">En primer lugar, cree un archivo de texto que contenga una cuenta en cada línea como esta:</span><span class="sxs-lookup"><span data-stu-id="e8134-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="e8134-135">En los siguientes comandos, el archivo de texto de ejemplo es *C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="e8134-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="e8134-136">Reemplace este nombre de archivo por la ruta de acceso y el nombre del archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e8134-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="e8134-137">Para bloquear el acceso a las cuentas que aparecen en el archivo de texto, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e8134-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="e8134-138">Para desbloquear las cuentas enumeradas en el archivo de texto, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e8134-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="e8134-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8134-139">See also</span></span>

[<span data-ttu-id="e8134-140">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8134-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e8134-141">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8134-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e8134-142">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8134-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
