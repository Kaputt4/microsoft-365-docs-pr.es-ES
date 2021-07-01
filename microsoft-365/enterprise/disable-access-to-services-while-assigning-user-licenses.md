---
title: Deshabilitar el acceso a Microsoft 365 servicios al asignar licencias de usuario
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Obtenga información sobre cómo asignar licencias a cuentas de usuario y deshabilitar planes de servicio específicos al mismo tiempo con PowerShell para Microsoft 365.
ms.openlocfilehash: ca5becb8709eeab7b5c535747ac93d36fefa0da8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228908"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="d8cf4-103">Deshabilitar el acceso a Microsoft 365 servicios al asignar licencias de usuario</span><span class="sxs-lookup"><span data-stu-id="d8cf4-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="d8cf4-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d8cf4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d8cf4-105">Microsoft 365 suscripciones vienen con planes de servicio para servicios individuales.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="d8cf4-106">Microsoft 365 a menudo los administradores deben deshabilitar determinados planes al asignar licencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="d8cf4-107">Con las instrucciones de este artículo, puede asignar una licencia Microsoft 365 a la vez que deshabilita planes de servicio específicos mediante PowerShell para una cuenta de usuario individual o varias cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d8cf4-108">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="d8cf4-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="d8cf4-109">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="d8cf4-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>


<span data-ttu-id="d8cf4-110">A continuación, enumera los planes de licencia de tu inquilino con este comando.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="d8cf4-111">A continuación, obtenga el nombre de inicio de sesión de la cuenta a la que desea agregar una licencia, también conocida como nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="d8cf4-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="d8cf4-112">A continuación, compile una lista de servicios que se habilitarán.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="d8cf4-113">Para obtener una lista completa de los planes de licencia (también conocidos como nombres de producto), sus planes de servicio incluidos y sus nombres [descriptivos correspondientes,](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)vea Nombres de productos e identificadores de plan de servicio para licencias.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="d8cf4-114">Para el bloque de comandos siguiente, rellene el nombre principal de usuario de la cuenta de usuario, el número de parte sku y la lista de planes de servicio para habilitar y quitar el texto explicativo y los \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="d8cf4-115">A continuación, ejecute los comandos resultantes en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d8cf4-116">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8cf4-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d8cf4-117">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d8cf4-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="d8cf4-118">A continuación, ejecute este comando para ver las suscripciones actuales:</span><span class="sxs-lookup"><span data-stu-id="d8cf4-118">Next, run this command to see your current subscriptions:</span></span>

```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="d8cf4-119">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="d8cf4-120">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="d8cf4-121">En la presentación del  `Get-MsolAccountSku` comando:</span><span class="sxs-lookup"><span data-stu-id="d8cf4-121">In the display of the  `Get-MsolAccountSku` command:</span></span>

- <span data-ttu-id="d8cf4-122">**AccountSkuId** es una suscripción para su organización en \<OrganizationName> : \<Subscription> format.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="d8cf4-123">Es el valor que proporcionó al inscribirse en \<OrganizationName> Microsoft 365 y es único para su organización.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="d8cf4-124">El \<Subscription> valor es para una suscripción específica.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="d8cf4-125">Por ejemplo, para litwareinc:ENTERPRISEPACK, el nombre de la organización es litwareinc y el nombre de la suscripción es ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="d8cf4-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>

- <span data-ttu-id="d8cf4-126">**ActiveUnits es** el número de licencias que ha comprado para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>

- <span data-ttu-id="d8cf4-127">**WarningUnits** es el número de licencias de una suscripción que no ha renovado y que expirará después del período de gracia de 30 días.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>

- <span data-ttu-id="d8cf4-128">**ConsumedUnits es** el número de licencias que has asignado a los usuarios para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>

<span data-ttu-id="d8cf4-129">Tenga en cuenta accountSkuId para la Microsoft 365 que contiene los usuarios que desea licenciar.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="d8cf4-130">Además, asegúrese de que hay suficientes licencias para asignar (resta **ConsumedUnits** de **ActiveUnits**).</span><span class="sxs-lookup"><span data-stu-id="d8cf4-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits**).</span></span>

<span data-ttu-id="d8cf4-131">A continuación, ejecute este comando para ver los detalles sobre los Microsoft 365 de servicio que están disponibles en todas las suscripciones:</span><span class="sxs-lookup"><span data-stu-id="d8cf4-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="d8cf4-132">Desde la presentación de este comando, determine qué planes de servicio desea deshabilitar al asignar licencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>

<span data-ttu-id="d8cf4-133">Esta es una lista parcial de planes de servicio y sus correspondientes Microsoft 365 servicios.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="d8cf4-134">En la tabla siguiente se muestran los Microsoft 365 de servicio y sus nombres descriptivos para los servicios más comunes.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="d8cf4-135">Su lista de planes de servicio puede ser diferente.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-135">Your list of service plans might be different.</span></span>

|<span data-ttu-id="d8cf4-136">**Plan de servicio**</span><span class="sxs-lookup"><span data-stu-id="d8cf4-136">**Service plan**</span></span>|<span data-ttu-id="d8cf4-137">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d8cf4-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="d8cf4-138">Sway</span><span class="sxs-lookup"><span data-stu-id="d8cf4-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="d8cf4-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8cf4-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="d8cf4-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="d8cf4-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="d8cf4-141">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="d8cf4-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="d8cf4-142">Aplicaciones Microsoft 365 para empresas *(anteriormente denominado Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="d8cf4-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="d8cf4-143">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d8cf4-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="d8cf4-144">Oficina</span><span class="sxs-lookup"><span data-stu-id="d8cf4-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="d8cf4-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d8cf4-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="d8cf4-146">Plan 2 de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d8cf4-146">Exchange Online Plan 2</span></span>  <br/> |

<span data-ttu-id="d8cf4-147">Para obtener una lista completa de los planes de licencia (también conocidos como nombres de producto), sus planes de servicio incluidos y sus nombres [descriptivos correspondientes,](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)vea Nombres de productos e identificadores de plan de servicio para licencias.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="d8cf4-148">Ahora que tiene el AccountSkuId y los planes de servicio para deshabilitar, puede asignar licencias para un usuario individual o para varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>

### <a name="for-a-single-user"></a><span data-ttu-id="d8cf4-149">Para un solo usuario</span><span class="sxs-lookup"><span data-stu-id="d8cf4-149">For a single user</span></span>

<span data-ttu-id="d8cf4-150">Para un único usuario, rellene el nombre principal de usuario de la cuenta de usuario, accountSkuId y la lista de planes de servicio para deshabilitar y quitar el texto explicativo y los \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="d8cf4-151">A continuación, ejecute los comandos resultantes en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="d8cf4-152">Este es un bloque de comandos de ejemplo para la cuenta denominada belindan@contoso.com, para la licencia contoso:ENTERPRISEPACK, y los planes de servicio que se van a deshabilitar son RMS_S_ENTERPRISE, SWAY, INTUNE_O365 y YAMMER_ENTERPRISE:</span><span class="sxs-lookup"><span data-stu-id="d8cf4-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="d8cf4-153">Para varios usuarios</span><span class="sxs-lookup"><span data-stu-id="d8cf4-153">For multiple users</span></span>

<span data-ttu-id="d8cf4-154">Para realizar esta tarea de administración para varios usuarios, cree un archivo de texto de valores separados por comas (CSV) que contenga los campos UserPrincipalName y UsageLocation.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-154">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields.</span></span> <span data-ttu-id="d8cf4-155">A continuación le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d8cf4-155">Here is an example:</span></span>

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="d8cf4-156">A continuación, rellene la ubicación de los archivos CSV de entrada y salida, el id. de SKU de la cuenta y la lista de planes de servicio que desea deshabilitar y, a continuación, ejecute los comandos resultantes en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

<span data-ttu-id="d8cf4-157">Este bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d8cf4-157">This PowerShell command block:</span></span>

- <span data-ttu-id="d8cf4-158">Muestra el nombre principal de usuario de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-158">Displays the user principal name of each user.</span></span>

- <span data-ttu-id="d8cf4-159">Asigna licencias personalizadas a cada usuario.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-159">Assigns customized licenses to each user.</span></span>

- <span data-ttu-id="d8cf4-160">Crea un archivo CSV con todos los usuarios que se procesaron y muestra su estado de licencia.</span><span class="sxs-lookup"><span data-stu-id="d8cf4-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8cf4-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8cf4-161">See also</span></span>

[<span data-ttu-id="d8cf4-162">Deshabilitar el acceso a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8cf4-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)

[<span data-ttu-id="d8cf4-163">Deshabilitar el acceso a Sway con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8cf4-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)

[<span data-ttu-id="d8cf4-164">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8cf4-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="d8cf4-165">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8cf4-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)