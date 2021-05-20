---
title: Asignar Microsoft 365 a cuentas de usuario con PowerShell
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
description: En este artículo, obtenga información sobre cómo usar PowerShell para asignar una licencia Microsoft 365 a usuarios sin licencia.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572626"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="176c9-103">Asignar Microsoft 365 a cuentas de usuario con PowerShell</span><span class="sxs-lookup"><span data-stu-id="176c9-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="176c9-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="176c9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="176c9-105">Los usuarios no pueden usar ningún servicio Microsoft 365 hasta que se haya asignado a su cuenta una licencia de un plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="176c9-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="176c9-106">Puede usar PowerShell para asignar rápidamente licencias a cuentas sin licencia.</span><span class="sxs-lookup"><span data-stu-id="176c9-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="176c9-107">Primero se debe asignar una ubicación a las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="176c9-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="176c9-108">Especificar una ubicación es una parte necesaria para crear una nueva cuenta de usuario en el [centro Microsoft 365 administración.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="176c9-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="176c9-109">De forma predeterminada, las cuentas sincronizadas desde los Servicios de dominio de Active Directory locales no tienen una ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="176c9-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="176c9-110">Puede configurar una ubicación para estas cuentas desde:</span><span class="sxs-lookup"><span data-stu-id="176c9-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="176c9-111">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="176c9-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="176c9-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="176c9-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="176c9-113">[Azure Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Usuarios de **Active Directory**> cuenta de usuario > información de contacto de perfil  >     >    >  **país o región**).</span><span class="sxs-lookup"><span data-stu-id="176c9-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="176c9-114">[Obtenga información sobre cómo asignar licencias a cuentas de usuario](../admin/manage/assign-licenses-to-users.md) con el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="176c9-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="176c9-115">Para obtener una lista de recursos adicionales, vea [Administrar usuarios y grupos.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="176c9-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="176c9-116">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="176c9-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="176c9-117">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="176c9-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="176c9-118">A continuación, enumera los planes de licencia de tu inquilino con este comando.</span><span class="sxs-lookup"><span data-stu-id="176c9-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="176c9-119">A continuación, obtenga el nombre de inicio de sesión de la cuenta a la que desea agregar una licencia, también conocida como nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="176c9-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="176c9-120">A continuación, asegúrese de que la cuenta de usuario tenga asignada una ubicación de uso.</span><span class="sxs-lookup"><span data-stu-id="176c9-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="176c9-121">Si no hay ninguna ubicación de uso asignada, puede asignar uno con estos comandos:</span><span class="sxs-lookup"><span data-stu-id="176c9-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="176c9-122">Por último, especifique el nombre de inicio de sesión de usuario y el nombre del plan de licencia y ejecute estos comandos.</span><span class="sxs-lookup"><span data-stu-id="176c9-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="176c9-123">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="176c9-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="176c9-124">Tenga en cuenta que empezaremos a desuso de este módulo cuando la funcionalidad de este módulo esté disponible en la versión [Azure Active Directory PowerShell para Graph](/powershell/azuread/v2/azureactivedirectory) módulo.</span><span class="sxs-lookup"><span data-stu-id="176c9-124">Please note that we will begin to deprecate this module when the functionality of this module is available in the newer [Azure Active Directory PowerShell for Graph](/powershell/azuread/v2/azureactivedirectory) module.</span></span> <span data-ttu-id="176c9-125">Se recomienda a los clientes que creen nuevos scripts de PowerShell que usen el módulo más reciente en lugar de este módulo.</span><span class="sxs-lookup"><span data-stu-id="176c9-125">We advise customers who are creating new PowerShell scripts to use the newer module instead of this module.</span></span>

<span data-ttu-id="176c9-126">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="176c9-126">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="176c9-127">Ejecute el comando para ver los planes de licencias disponibles y el número de licencias disponibles `Get-MsolAccountSku` en cada plan de la organización.</span><span class="sxs-lookup"><span data-stu-id="176c9-127">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="176c9-128">El número de licencias disponibles en cada plan es **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="176c9-128">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="176c9-129">Para obtener más información acerca de los planes de licencias, licencias y servicios, vea [Ver licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="176c9-129">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="176c9-130">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="176c9-130">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="176c9-131">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="176c9-131">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="176c9-132">Para buscar las cuentas sin licencia en la organización, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="176c9-132">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="176c9-133">Solo puede asignar licencias a cuentas de usuario que tengan la propiedad **UsageLocation** establecida en un código de país iso 3166-1 alfa-2 válido.</span><span class="sxs-lookup"><span data-stu-id="176c9-133">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="176c9-134">Por ejemplo, US para Estados Unidos y FR para Francia.</span><span class="sxs-lookup"><span data-stu-id="176c9-134">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="176c9-135">Algunos Microsoft 365 servicios no están disponibles en determinados países.</span><span class="sxs-lookup"><span data-stu-id="176c9-135">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="176c9-136">Para obtener más información, consulte [Sobre las restricciones de licencia](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="176c9-136">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="176c9-137">Para buscar cuentas que no tienen un valor **UsageLocation,** ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="176c9-137">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="176c9-138">Para establecer el **valor UsageLocation** en una cuenta, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="176c9-138">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="176c9-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="176c9-139">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="176c9-140">Si usa el cmdlet **Get-MsolUser** sin usar el parámetro **All**, solo se devuelven las 500 primeras cuentas.</span><span class="sxs-lookup"><span data-stu-id="176c9-140">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="176c9-141">Asignar licencias a cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="176c9-141">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="176c9-142">Para asignar una licencia a un usuario, use el siguiente comando en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="176c9-142">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="176c9-143">En este ejemplo se asigna una licencia del plan de licencias **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) al usuario sin **\@ licencia belindan litwareinc.com**:</span><span class="sxs-lookup"><span data-stu-id="176c9-143">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="176c9-144">Para asignar una licencia a todos los usuarios sin licencia, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="176c9-144">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="176c9-145">No se pueden asignar varias licencias a un usuario desde el mismo plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="176c9-145">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="176c9-146">Si no dispone de licencias suficientes, las licencias se asignan a los usuarios en el orden en que los devuelve el cmdlet **Get-MsolUser** hasta que se agoten las licencias disponibles.</span><span class="sxs-lookup"><span data-stu-id="176c9-146">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="176c9-147">En este ejemplo se asignan licencias del plan de licencias **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) a todos los usuarios sin licencia:</span><span class="sxs-lookup"><span data-stu-id="176c9-147">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="176c9-148">En este ejemplo se asignan esas mismas licencias a usuarios sin licencia en el departamento de ventas de Estados Unidos:</span><span class="sxs-lookup"><span data-stu-id="176c9-148">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="176c9-149">Mover un usuario a una suscripción diferente (plan de licencia) con el Azure Active Directory PowerShell para Graph módulo</span><span class="sxs-lookup"><span data-stu-id="176c9-149">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="176c9-150">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="176c9-150">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="176c9-151">A continuación, obtenga el nombre de inicio de sesión de la cuenta de usuario para la que desea cambiar de suscripción, también conocido como el nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="176c9-151">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="176c9-152">A continuación, enumera las suscripciones (planes de licencia) de tu inquilino con este comando.</span><span class="sxs-lookup"><span data-stu-id="176c9-152">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="176c9-153">A continuación, enumera las suscripciones que la cuenta de usuario tiene actualmente con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="176c9-153">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="176c9-154">Identifique la suscripción que el usuario tiene actualmente (la suscripción FROM) y la suscripción a la que se mueve el usuario (la suscripción a TO).</span><span class="sxs-lookup"><span data-stu-id="176c9-154">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="176c9-155">Por último, especifique los nombres de suscripción TO y FROM (números de parte SKU) y ejecute estos comandos.</span><span class="sxs-lookup"><span data-stu-id="176c9-155">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="176c9-156">Puede comprobar el cambio en la suscripción de la cuenta de usuario con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="176c9-156">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="176c9-157">Consulta también</span><span class="sxs-lookup"><span data-stu-id="176c9-157">See also</span></span>

[<span data-ttu-id="176c9-158">Administrar cuentas de usuario, licencias y grupos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="176c9-158">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="176c9-159">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="176c9-159">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="176c9-160">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="176c9-160">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
