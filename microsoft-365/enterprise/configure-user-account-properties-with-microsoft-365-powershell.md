---
title: Configurar Microsoft 365 de cuenta de usuario con PowerShell
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
description: Use PowerShell para Microsoft 365 para configurar las propiedades de cuentas de usuario individuales o varias en el Microsoft 365 inquilino.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911089"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="e4d0c-103">Configurar Microsoft 365 de cuenta de usuario con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4d0c-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="e4d0c-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e4d0c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e4d0c-105">Puede usar el Centro Microsoft 365 administración para configurar las propiedades de las cuentas de usuario de su Microsoft 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="e4d0c-106">En PowerShell, también puede hacerlo, además de otras cosas que no puede hacer en el Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e4d0c-107">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="e4d0c-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e4d0c-108">Para configurar las propiedades de las cuentas de usuario en el módulo Azure Active Directory PowerShell para Graph, use el cmdlet [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) y especifique las propiedades que se deben establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="e4d0c-109">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="e4d0c-110">Cambiar las propiedades de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="e4d0c-110">Change properties for a specific user account</span></span>

<span data-ttu-id="e4d0c-111">La cuenta se identifica con el *parámetro -ObjectID* y se establecen o cambian propiedades específicas mediante parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="e4d0c-112">Esta es una lista de los parámetros más comunes:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="e4d0c-113">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="e4d0c-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="e4d0c-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="e4d0c-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="e4d0c-117">-Surname " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="e4d0c-118">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="e4d0c-119">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="e4d0c-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="e4d0c-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="e4d0c-122">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="e4d0c-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="e4d0c-124">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="e4d0c-125">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="e4d0c-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="e4d0c-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="e4d0c-128">Este es el código de región o país de dos letras ISO 3166-1 alfa-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="e4d0c-129">Para obtener parámetros adicionales, [vea Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="e4d0c-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="e4d0c-130">Para poder asignar licencias a una cuenta de usuario, debe asignar una ubicación de uso.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="e4d0c-131">Para mostrar el nombre principal de usuario de las cuentas de usuario, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="e4d0c-132">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4d0c-133">Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-134">Ordena la lista de nombres de entidad de seguridad de usuario alfabéticamente (**Ordenar UserPrincipalName**) y envíala al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-135">Mostrar solo la propiedad Nombre de entidad de seguridad de usuario para cada cuenta (**Seleccionar UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="e4d0c-136">Mostrarlos de una pantalla a la vez (**Más**).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="e4d0c-137">Para mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellido), ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="e4d0c-138">Rellene la *variable $userName* y quite los \< and > caracteres:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e4d0c-139">En este ejemplo se muestra el nombre principal de usuario de la cuenta de usuario que tiene el nombre para mostrar *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e4d0c-140">Al usar una *variable $upn,* puede realizar cambios en cuentas individuales en función de su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="e4d0c-141">Este es un ejemplo que establece la ubicación de uso de *Belinda Newman* en Francia.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="e4d0c-142">Pero especifica su nombre para mostrar en lugar de su nombre principal de usuario:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="e4d0c-143">Cambiar las propiedades de todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e4d0c-143">Change properties for all user accounts</span></span>

<span data-ttu-id="e4d0c-144">Para cambiar las propiedades de todos los usuarios, puede usar una combinación de los cmdlets **Get-AzureADUser** y **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="e4d0c-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="e4d0c-145">En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios a *Francia:*</span><span class="sxs-lookup"><span data-stu-id="e4d0c-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="e4d0c-146">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4d0c-147">Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-148">Establezca la ubicación del usuario en Francia (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="e4d0c-149">Cambiar las propiedades de un conjunto específico de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e4d0c-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="e4d0c-150">Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar una combinación de los cmdlets **Get-AzureADUser**, **Where** y **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="e4d0c-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="e4d0c-151">En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios del departamento de contabilidad a *Francia:*</span><span class="sxs-lookup"><span data-stu-id="e4d0c-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="e4d0c-152">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4d0c-153">Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="e4d0c-154">Busque todas las cuentas de usuario que tienen su *propiedad Department* establecida en "Accounting" (**Where {$_. Department -eq "Accounting"}**) y envíe la información resultante al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-155">Establezca la ubicación del usuario en Francia (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e4d0c-156">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4d0c-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e4d0c-157">Para configurar las propiedades de las cuentas de usuario con el módulo Microsoft Azure Active Directory para Windows PowerShell, use el cmdlet **Set-MsolUser** y especifique las propiedades que se deben establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="e4d0c-158">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="e4d0c-159">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="e4d0c-160">Ejecute estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="e4d0c-161">Cambiar las propiedades de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="e4d0c-161">Change properties for a specific user account</span></span>

<span data-ttu-id="e4d0c-162">Para configurar las propiedades de una cuenta de usuario específica, use el cmdlet [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) y especifique las propiedades que se deben establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="e4d0c-163">La cuenta se identifica con el *parámetro -UserPrincipalName* y se establecen o cambian propiedades específicas mediante parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="e4d0c-164">Esta es una lista de los parámetros más comunes.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="e4d0c-165">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="e4d0c-166">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="e4d0c-167">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="e4d0c-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="e4d0c-169">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="e4d0c-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="e4d0c-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="e4d0c-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="e4d0c-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="e4d0c-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="e4d0c-175">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="e4d0c-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="e4d0c-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="e4d0c-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="e4d0c-179">-Title " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="e4d0c-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="e4d0c-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="e4d0c-181">Este es el código de región o país de dos letras ISO 3166-1 alfa-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="e4d0c-182">Para obtener parámetros adicionales, [vea Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="e4d0c-183">Para ver los nombres principales de usuario de todos los usuarios, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="e4d0c-184">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4d0c-185">Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-186">Ordena la lista de nombres de entidad de seguridad de usuario alfabéticamente (**Ordenar UserPrincipalName**) y envíala al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-187">Mostrar solo la propiedad Nombre de entidad de seguridad de usuario para cada cuenta (**Seleccionar UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="e4d0c-188">Mostrarlos de una pantalla a la vez (**Más**).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="e4d0c-189">Para mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellido), ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="e4d0c-190">Rellene la *variable $userName* y quite los \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e4d0c-191">En este ejemplo se muestra el nombre principal de usuario del usuario denominado Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e4d0c-192">Al usar una *variable $upn,* puede realizar cambios en cuentas individuales en función de su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="e4d0c-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="e4d0c-193">Este es un ejemplo que establece la ubicación de uso de *Belinda Newman* en *Francia,* pero especifica su nombre para mostrar en lugar de su nombre principal de usuario:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="e4d0c-194">Cambiar las propiedades de todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e4d0c-194">Change properties for all user accounts</span></span>

<span data-ttu-id="e4d0c-195">Para cambiar las propiedades de todos los usuarios, use una combinación de los cmdlets **Get-MsolUser** y **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="e4d0c-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="e4d0c-196">En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios a *Francia:*</span><span class="sxs-lookup"><span data-stu-id="e4d0c-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="e4d0c-197">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4d0c-198">Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-199">Establezca la ubicación del usuario en Francia (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="e4d0c-200">Cambiar las propiedades de un conjunto específico de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e4d0c-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="e4d0c-201">Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar una combinación de los cmdlets **Get-MsolUser**, **Where** y **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="e4d0c-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="e4d0c-202">En el siguiente ejemplo se cambia la ubicación de uso de todos los usuarios del departamento de contabilidad a *Francia:*</span><span class="sxs-lookup"><span data-stu-id="e4d0c-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="e4d0c-203">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="e4d0c-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4d0c-204">Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-205">Busque todas las cuentas de usuario que tengan su *propiedad Department* establecida en "Accounting" (**Where {$_. Department -eq "Accounting"}**) y envía la información resultante al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="e4d0c-206">Establezca la ubicación del usuario en Francia (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="e4d0c-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4d0c-207">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4d0c-207">See also</span></span>

[<span data-ttu-id="e4d0c-208">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4d0c-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e4d0c-209">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4d0c-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e4d0c-210">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e4d0c-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)