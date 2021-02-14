---
title: Ver detalles de servicio y licencia de cuenta de Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: Explica cómo usar PowerShell para determinar los servicios de Microsoft 365 que se han asignado a los usuarios.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694217"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="d3dcb-103">Ver detalles de servicio y licencia de cuenta de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3dcb-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="d3dcb-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d3dcb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d3dcb-105">En Microsoft 365, las licencias de los planes de licencias (también denominados SKU o planes de Microsoft 365) dan a los usuarios acceso a los servicios de Microsoft 365 definidos para esos planes.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="d3dcb-106">Sin embargo, un usuario podría no tener acceso a todos los servicios disponibles en una licencia que está actualmente asignada a ellos.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="d3dcb-107">Puede usar PowerShell para Microsoft 365 para ver el estado de los servicios en las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="d3dcb-108">Para obtener más información acerca de los planes de licencias, licencias y servicios, vea [Ver licencias y servicios con PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d3dcb-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d3dcb-109">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="d3dcb-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="d3dcb-110">En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="d3dcb-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="d3dcb-111">A continuación, haga una lista de los planes de licencia de su espacio empresarial con este comando.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="d3dcb-112">Use estos comandos para enumerar los servicios que están disponibles en cada plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-112">Use these commands to list the services that are available in each licensing plan.</span></span>

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

<span data-ttu-id="d3dcb-113">Use estos comandos para enumerar las licencias asignadas a una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d3dcb-114">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3dcb-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d3dcb-115">En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="d3dcb-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="d3dcb-116">A continuación, ejecute este comando para enumerar los planes de licencias que están disponibles en su organización.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="d3dcb-117">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="d3dcb-118">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="d3dcb-119">A continuación, ejecute este comando para enumerar los servicios que están disponibles en cada plan de licencias y el orden en que aparecen (el número de índice).</span><span class="sxs-lookup"><span data-stu-id="d3dcb-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="d3dcb-120">Use este comando para enumerar las licencias asignadas a un usuario y el orden en que aparecen (el número de índice).</span><span class="sxs-lookup"><span data-stu-id="d3dcb-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="d3dcb-121">Para ver los servicios de una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="d3dcb-121">To view services for a user account</span></span>

<span data-ttu-id="d3dcb-122">Para ver todos los servicios de Microsoft 365 a los que tiene acceso un usuario, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d3dcb-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="d3dcb-123">En este ejemplo se muestran los servicios a los que el usuario BelindaN@litwareinc.com tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="d3dcb-124">Se muestran los servicios que están asociados a todas las licencias asignadas a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="d3dcb-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="d3dcb-125">En este ejemplo se muestran los servicios a los que tiene acceso la usuaria BelindaN@litwareinc.com a partir de la primera licencia asignada a su cuenta (el número de índice es 0).</span><span class="sxs-lookup"><span data-stu-id="d3dcb-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="d3dcb-126">Para ver todos los servicios de un usuario al que se han asignado varias *licencias,* use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3dcb-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a><span data-ttu-id="d3dcb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3dcb-127">See also</span></span>

[<span data-ttu-id="d3dcb-128">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3dcb-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d3dcb-129">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3dcb-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d3dcb-130">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d3dcb-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
