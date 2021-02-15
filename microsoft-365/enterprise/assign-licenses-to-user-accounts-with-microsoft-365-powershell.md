---
title: Asignar licencias de Microsoft 365 a cuentas de usuario con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: En este artículo, obtenga información sobre cómo usar PowerShell para asignar una licencia de Microsoft 365 a usuarios sin licencia.
ms.openlocfilehash: 8c3165b99477afa14e6d2b0da927b5f64c416ef1
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580945"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="60d5d-103">Asignar licencias de Microsoft 365 a cuentas de usuario con PowerShell</span><span class="sxs-lookup"><span data-stu-id="60d5d-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="60d5d-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="60d5d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="60d5d-105">Los usuarios no pueden usar ningún servicio de Microsoft 365 hasta que su cuenta tenga asignada una licencia de un plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="60d5d-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="60d5d-106">Puede usar PowerShell para asignar rápidamente licencias a cuentas sin licencia.</span><span class="sxs-lookup"><span data-stu-id="60d5d-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="60d5d-107">Primero se debe asignar una ubicación a las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="60d5d-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="60d5d-108">La especificación de una ubicación es una parte necesaria de la creación de una nueva cuenta de usuario en el [Centro de administración de Microsoft 365.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="60d5d-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="60d5d-109">De forma predeterminada, las cuentas sincronizadas desde los Servicios de dominio de Active Directory locales no tienen una ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="60d5d-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="60d5d-110">Puede configurar una ubicación para estas cuentas desde:</span><span class="sxs-lookup"><span data-stu-id="60d5d-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="60d5d-111">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60d5d-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="60d5d-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="60d5d-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="60d5d-113">[Azure Portal](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Usuarios de **Active Directory**> cuenta de usuario > información de contacto de perfil  >   país o   >    >  **región**).</span><span class="sxs-lookup"><span data-stu-id="60d5d-113">The [Azure portal](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="60d5d-114">[Obtenga información sobre cómo asignar licencias a cuentas de usuario](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) con el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60d5d-114">[Learn how to assign licenses to user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="60d5d-115">Para obtener una lista de recursos adicionales, vea [Administrar usuarios y grupos.](https://docs.microsoft.com/microsoft-365/admin/add-users/)</span><span class="sxs-lookup"><span data-stu-id="60d5d-115">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="60d5d-116">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="60d5d-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="60d5d-117">En primer [lugar, conéctese a su inquilino de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="60d5d-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="60d5d-118">A continuación, haga una lista de los planes de licencia de su espacio empresarial con este comando.</span><span class="sxs-lookup"><span data-stu-id="60d5d-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="60d5d-119">A continuación, obtenga el nombre de inicio de sesión de la cuenta a la que desea agregar una licencia, también conocida como el nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="60d5d-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="60d5d-120">A continuación, asegúrese de que la cuenta de usuario tenga asignada una ubicación de uso.</span><span class="sxs-lookup"><span data-stu-id="60d5d-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="60d5d-121">Si no hay ninguna ubicación de uso asignada, puede asignar una con estos comandos:</span><span class="sxs-lookup"><span data-stu-id="60d5d-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="60d5d-122">Por último, especifique el nombre de inicio de sesión del usuario y el nombre del plan de licencia y ejecute estos comandos.</span><span class="sxs-lookup"><span data-stu-id="60d5d-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="60d5d-123">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60d5d-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="60d5d-124">En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="60d5d-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="60d5d-125">Ejecute el comando para ver los planes de licencias disponibles y el número de licencias disponibles `Get-MsolAccountSku` en cada plan de la organización.</span><span class="sxs-lookup"><span data-stu-id="60d5d-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="60d5d-126">El número de licencias disponibles en cada plan es **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="60d5d-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="60d5d-127">Para obtener más información acerca de los planes de licencias, licencias y servicios, vea [Ver licencias y servicios con PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="60d5d-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="60d5d-128">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="60d5d-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="60d5d-129">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60d5d-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="60d5d-130">Para buscar las cuentas sin licencia en la organización, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="60d5d-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="60d5d-131">Solo puede asignar licencias a cuentas de usuario que tengan la propiedad **UsageLocation** establecida en un código de país ISO 3166-1 alpha-2 válido.</span><span class="sxs-lookup"><span data-stu-id="60d5d-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="60d5d-132">Por ejemplo, US para Estados Unidos y FR para Francia.</span><span class="sxs-lookup"><span data-stu-id="60d5d-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="60d5d-133">Algunos servicios de Microsoft 365 no están disponibles en determinados países.</span><span class="sxs-lookup"><span data-stu-id="60d5d-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="60d5d-134">Para obtener más información, consulte [Sobre las restricciones de licencia](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="60d5d-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="60d5d-135">Para buscar cuentas que no tengan un valor **UsageLocation,** ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="60d5d-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="60d5d-136">Para establecer el **valor UsageLocation** en una cuenta, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="60d5d-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="60d5d-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60d5d-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="60d5d-138">Si usa el cmdlet **Get-MsolUser** sin usar el parámetro **All**, solo se devuelven las 500 primeras cuentas.</span><span class="sxs-lookup"><span data-stu-id="60d5d-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="60d5d-139">Asignar licencias a cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="60d5d-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="60d5d-140">Para asignar una licencia a un usuario, use el siguiente comando en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60d5d-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="60d5d-141">En este ejemplo se asigna una licencia del plan de licencias **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) al usuario sin **licencia belindan \@ litwareinc.com:**</span><span class="sxs-lookup"><span data-stu-id="60d5d-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="60d5d-142">Para asignar una licencia a todos los usuarios sin licencia, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="60d5d-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="60d5d-143">No se pueden asignar varias licencias a un usuario desde el mismo plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="60d5d-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="60d5d-144">Si no dispone de licencias suficientes, las licencias se asignan a los usuarios en el orden en que los devuelve el cmdlet **Get-MsolUser** hasta que se agoten las licencias disponibles.</span><span class="sxs-lookup"><span data-stu-id="60d5d-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="60d5d-145">En este ejemplo se asignan licencias del plan de licencias **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) a todos los usuarios sin licencia:</span><span class="sxs-lookup"><span data-stu-id="60d5d-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="60d5d-146">En este ejemplo se asignan esas mismas licencias a usuarios sin licencia en el departamento de ventas de Estados Unidos:</span><span class="sxs-lookup"><span data-stu-id="60d5d-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="60d5d-147">Mover un usuario a una suscripción diferente (plan de licencia) con el módulo de PowerShell de Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="60d5d-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="60d5d-148">En primer [lugar, conéctese a su inquilino de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="60d5d-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="60d5d-149">A continuación, obtenga el nombre de inicio de sesión de la cuenta de usuario para la que desea cambiar de suscripción, también conocido como el nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="60d5d-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="60d5d-150">A continuación, enumera las suscripciones (planes de licencia) de tu espacio empresarial con este comando.</span><span class="sxs-lookup"><span data-stu-id="60d5d-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="60d5d-151">A continuación, enumera las suscripciones que la cuenta de usuario tiene actualmente con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="60d5d-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="60d5d-152">Identifica la suscripción que el usuario tiene actualmente (la suscripción FROM) y la suscripción a la que se mueve el usuario (la suscripción PARA).</span><span class="sxs-lookup"><span data-stu-id="60d5d-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="60d5d-153">Por último, especifica los nombres de suscripción TO y FROM (números de partes de SKU) y ejecuta estos comandos.</span><span class="sxs-lookup"><span data-stu-id="60d5d-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="60d5d-154">Puede comprobar el cambio en la suscripción de la cuenta de usuario con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="60d5d-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="60d5d-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="60d5d-155">See also</span></span>

[<span data-ttu-id="60d5d-156">Administrar cuentas de usuario, licencias y grupos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="60d5d-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="60d5d-157">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="60d5d-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="60d5d-158">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60d5d-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
