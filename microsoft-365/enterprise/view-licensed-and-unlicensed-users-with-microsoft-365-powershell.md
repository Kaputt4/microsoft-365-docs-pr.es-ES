---
title: Ver los usuarios con licencia y sin licencia de Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: En este artículo se explica cómo usar PowerShell para ver cuentas de usuario de Microsoft 365 con licencia y sin licencia.
ms.openlocfilehash: 8a99ba2a80f1d814ec5268c4f8f479837eb54dc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693802"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="4e987-103">Ver los usuarios con licencia y sin licencia de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e987-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="4e987-104">*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4e987-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4e987-105">Las cuentas de usuario de la organización de Microsoft 365 pueden tener algunas, todas o ninguna de las licencias disponibles asignadas desde los planes de licencias que están disponibles en la organización.</span><span class="sxs-lookup"><span data-stu-id="4e987-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="4e987-106">Puede usar PowerShell para Microsoft 365 para encontrar rápidamente a los usuarios con licencia y sin licencia de la organización.</span><span class="sxs-lookup"><span data-stu-id="4e987-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4e987-107">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="4e987-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4e987-108">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="4e987-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="4e987-109">Para ver la lista de todas las cuentas de usuario de la organización a las que no se ha asignado ninguno de los planes de licencias (usuarios sin licencia), ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4e987-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="4e987-110">Para ver la lista de todas las cuentas de usuario de la organización a las que se han asignado los planes de licencias (usuarios con licencia), ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4e987-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="4e987-111">Para obtener una lista de todos los usuarios de la suscripción, use el `Get-AzureAdUser -All $true` comando.</span><span class="sxs-lookup"><span data-stu-id="4e987-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4e987-112">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e987-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4e987-113">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4e987-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="4e987-114">Para ver la lista de todas las cuentas de usuario y su estado de licencias en la organización, ejecute el siguiente comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e987-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="4e987-115">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="4e987-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="4e987-116">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e987-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="4e987-117">Para ver la lista de todas las cuentas de usuario sin licencia de su organización, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e987-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="4e987-118">Para ver la lista de todas las cuentas de usuario con licencia de su organización, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e987-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="4e987-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4e987-119">See also</span></span>

[<span data-ttu-id="4e987-120">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e987-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4e987-121">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e987-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4e987-122">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e987-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
