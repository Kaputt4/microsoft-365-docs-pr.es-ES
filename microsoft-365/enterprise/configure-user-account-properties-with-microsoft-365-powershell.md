---
title: Configurar las propiedades de la cuenta de usuario de Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Use PowerShell para Microsoft 365 para configurar las propiedades de cuentas de usuario individuales o múltiples en su inquilino de Microsoft 365.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754333"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="27409-103">Configurar las propiedades de la cuenta de usuario de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="27409-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="27409-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="27409-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="27409-105">Puede usar el Centro de administración de Microsoft 365 para configurar las propiedades de las cuentas de usuario de su inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27409-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="27409-106">En PowerShell, también puede hacer esto, además de otras cosas que no puede hacer en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="27409-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="27409-107">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="27409-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="27409-108">Para configurar las propiedades de las cuentas de usuario en el módulo Azure Active Directory PowerShell para Graph, use el cmdlet [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) y especifique las propiedades que se deben establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="27409-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="27409-109">En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="27409-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="27409-110">Cambiar las propiedades de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="27409-110">Change properties for a specific user account</span></span>

<span data-ttu-id="27409-111">La cuenta se identifica con el *parámetro -ObjectID* y se establecen o cambian propiedades específicas mediante parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="27409-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="27409-112">Esta es una lista de los parámetros más comunes:</span><span class="sxs-lookup"><span data-stu-id="27409-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="27409-113">-Department \<department name> "</span><span class="sxs-lookup"><span data-stu-id="27409-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="27409-114">-DisplayName \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="27409-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="27409-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="27409-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="27409-116">-GivenName \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="27409-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="27409-117">-Surname \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="27409-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="27409-118">-Mobile \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="27409-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="27409-119">-JobTitle \<job title> "</span><span class="sxs-lookup"><span data-stu-id="27409-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="27409-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="27409-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="27409-121">-StreetAddress \<street address> "</span><span class="sxs-lookup"><span data-stu-id="27409-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="27409-122">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="27409-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="27409-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="27409-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="27409-124">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="27409-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="27409-125">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="27409-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="27409-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="27409-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="27409-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="27409-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="27409-128">Este es el código de país o región de dos letras ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="27409-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="27409-129">Para obtener parámetros adicionales, [vea Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="27409-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="27409-130">Para poder asignar licencias a una cuenta de usuario, debe asignar una ubicación de uso.</span><span class="sxs-lookup"><span data-stu-id="27409-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="27409-131">Para mostrar el nombre principal de usuario de las cuentas de usuario, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="27409-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="27409-132">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="27409-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="27409-133">Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-134">Ordene la lista de nombres principales de usuario alfabéticamente (**Ordenar UserPrincipalName**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-135">Muestra solo la propiedad Nombre principal de usuario para cada cuenta (**Seleccionar UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="27409-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="27409-136">Mostrarlos de una pantalla a la vez (**Más**).</span><span class="sxs-lookup"><span data-stu-id="27409-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="27409-137">Para mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellidos), ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="27409-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="27409-138">Rellene la *variable $userName* y quite los \< and > caracteres:</span><span class="sxs-lookup"><span data-stu-id="27409-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="27409-139">En este ejemplo se muestra el nombre principal de usuario de la cuenta de usuario que tiene el nombre para mostrar *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="27409-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="27409-140">Mediante el uso de *$upn* variable, puede realizar cambios en cuentas individuales en función de su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="27409-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="27409-141">Este es un ejemplo que establece la ubicación de uso de *Belinda Newman* en Francia.</span><span class="sxs-lookup"><span data-stu-id="27409-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="27409-142">Pero especifica su nombre para mostrar en lugar de su nombre principal de usuario:</span><span class="sxs-lookup"><span data-stu-id="27409-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="27409-143">Cambiar las propiedades de todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="27409-143">Change properties for all user accounts</span></span>

<span data-ttu-id="27409-144">Para cambiar las propiedades de todos los usuarios, puede usar una combinación de los cmdlets **Get-AzureADUser** y **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="27409-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="27409-145">En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios a *Francia:*</span><span class="sxs-lookup"><span data-stu-id="27409-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="27409-146">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="27409-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="27409-147">Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-148">Establezca la ubicación del usuario en Francia (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="27409-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="27409-149">Cambiar las propiedades de un conjunto específico de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="27409-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="27409-150">Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar una combinación de los cmdlets **Get-AzureADUser**, **Where** y **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="27409-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="27409-151">En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios del departamento de contabilidad a *Francia:*</span><span class="sxs-lookup"><span data-stu-id="27409-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="27409-152">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="27409-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="27409-153">Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="27409-154">Busque todas las cuentas de usuario que tengan su *propiedad Department* establecida en "Accounting"**(Donde {$_. Department -eq "Accounting"}**) y envíe la información resultante al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-155">Establezca la ubicación del usuario en Francia (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="27409-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="27409-156">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="27409-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="27409-157">Para configurar las propiedades de las cuentas de usuario con el módulo Microsoft Azure Active Directory para Windows PowerShell, use el cmdlet **Set-MsolUser** y especifique las propiedades que se establecerán o cambiarán.</span><span class="sxs-lookup"><span data-stu-id="27409-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="27409-158">En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="27409-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="27409-159">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="27409-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="27409-160">Ejecute estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27409-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="27409-161">Cambiar las propiedades de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="27409-161">Change properties for a specific user account</span></span>

<span data-ttu-id="27409-162">Para configurar las propiedades de una cuenta de usuario específica, use el cmdlet [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) y especifique las propiedades que se establecerán o cambiarán.</span><span class="sxs-lookup"><span data-stu-id="27409-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="27409-163">Identifique la cuenta con el *parámetro -UserPrincipalName* y establezca o cambie propiedades específicas mediante parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="27409-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="27409-164">Esta es una lista de los parámetros más comunes.</span><span class="sxs-lookup"><span data-stu-id="27409-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="27409-165">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="27409-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="27409-166">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="27409-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="27409-167">-Department \<department name> "</span><span class="sxs-lookup"><span data-stu-id="27409-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="27409-168">-DisplayName \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="27409-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="27409-169">-Fax \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="27409-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="27409-170">-FirstName \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="27409-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="27409-171">-LastName \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="27409-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="27409-172">-MobilePhone \<mobile phone number> " "</span><span class="sxs-lookup"><span data-stu-id="27409-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="27409-173">-Office \<office location> "</span><span class="sxs-lookup"><span data-stu-id="27409-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="27409-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="27409-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="27409-175">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="27409-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="27409-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="27409-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="27409-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="27409-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="27409-178">-StreetAddress \<street address> "</span><span class="sxs-lookup"><span data-stu-id="27409-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="27409-179">-Title \<title name> " "</span><span class="sxs-lookup"><span data-stu-id="27409-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="27409-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="27409-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="27409-181">Este es el código de país o región de dos letras ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="27409-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="27409-182">Para obtener más parámetros, [vea Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="27409-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="27409-183">Para ver los nombres principales de usuario de todos los usuarios, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="27409-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="27409-184">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="27409-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="27409-185">Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-186">Ordene la lista de nombres principales de usuario alfabéticamente (**Ordenar UserPrincipalName**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-187">Muestra solo la propiedad Nombre principal de usuario para cada cuenta (**Seleccionar UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="27409-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="27409-188">Mostrarlos de una pantalla a la vez (**Más**).</span><span class="sxs-lookup"><span data-stu-id="27409-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="27409-189">Para mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellidos), ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="27409-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="27409-190">Rellene la variable *$userName* y quite los \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="27409-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="27409-191">En este ejemplo se muestra el nombre principal de usuario para el usuario llamado Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="27409-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="27409-192">Mediante el uso de *$upn* variable, puede realizar cambios en cuentas individuales en función de su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="27409-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="27409-193">Este es un ejemplo que establece la ubicación de uso de *Belinda Newman* en *Francia,* pero especifica su nombre para mostrar en lugar de su nombre principal de usuario:</span><span class="sxs-lookup"><span data-stu-id="27409-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="27409-194">Cambiar las propiedades de todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="27409-194">Change properties for all user accounts</span></span>

<span data-ttu-id="27409-195">Para cambiar las propiedades de todos los usuarios, use una combinación de los cmdlets **Get-MsolUser** y **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="27409-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="27409-196">En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios a *Francia:*</span><span class="sxs-lookup"><span data-stu-id="27409-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="27409-197">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="27409-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="27409-198">Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-199">Establezca la ubicación del usuario en Francia (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="27409-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="27409-200">Cambiar las propiedades de un conjunto específico de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="27409-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="27409-201">Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar una combinación de los cmdlets **Get-MsolUser**, **Where** y **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="27409-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="27409-202">En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios del departamento de contabilidad a *Francia:*</span><span class="sxs-lookup"><span data-stu-id="27409-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="27409-203">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="27409-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="27409-204">Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-205">Busque todas las cuentas de usuario que tengan su *propiedad Department* establecida en "Accounting"**(Donde {$_. Department -eq "Accounting"}**) y envíe la información resultante al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="27409-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="27409-206">Establezca la ubicación del usuario en Francia (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="27409-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="27409-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="27409-207">See also</span></span>

[<span data-ttu-id="27409-208">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="27409-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="27409-209">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="27409-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="27409-210">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27409-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
