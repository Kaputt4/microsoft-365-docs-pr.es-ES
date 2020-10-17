---
title: Configurar las propiedades de la cuenta de usuario 365 de Microsoft con PowerShell
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
description: 'Resumen: Use PowerShell para Microsoft 365 para configurar las propiedades de una o varias cuentas de usuario en su inquilino de Microsoft 365.'
ms.openlocfilehash: ae797d67b47c637dc95176b92fad8090f8a7ab37
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580933"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="4f6ad-103">Configurar las propiedades de la cuenta de usuario 365 de Microsoft con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f6ad-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="4f6ad-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4f6ad-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4f6ad-105">Aunque puede usar el centro de administración de Microsoft 365 para configurar las propiedades de las cuentas de usuario de su inquilino de Microsoft 365, también puede usar PowerShell y hacer algunas cosas que el centro de administración de Microsoft 365 no puede.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4f6ad-106">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="4f6ad-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4f6ad-107">Para configurar las propiedades de las cuentas de usuario con el módulo Azure Active Directory PowerShell para Graph, use el cmdlet [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) y especifique las propiedades que se deben establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="4f6ad-108">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="4f6ad-109">Cambiar las propiedades de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="4f6ad-109">Change properties for a specific user account</span></span>

<span data-ttu-id="4f6ad-110">La cuenta se identifica con el parámetro **-objectId** y se establecen o cambian las propiedades específicas con parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-110">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="4f6ad-111">A continuación se muestra una lista de los parámetros más comunes.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-111">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="4f6ad-112">-Departamento " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="4f6ad-113">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="4f6ad-114">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="4f6ad-115">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="4f6ad-116">-2º apellido " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="4f6ad-117">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="4f6ad-118">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="4f6ad-119">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="4f6ad-120">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="4f6ad-121">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="4f6ad-122">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="4f6ad-123">-CódigoPostal " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="4f6ad-124">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="4f6ad-125">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="4f6ad-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="4f6ad-127">Este es el código de país o región de dos letras ISO 3166-1 (a2).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="4f6ad-128">Consulte [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) para obtener más parámetros.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) for additional parameters.</span></span>

>[!Note]
><span data-ttu-id="4f6ad-129">Antes de poder asignar licencias a una cuenta de usuario, debe asignar una ubicación de uso.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-129">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="4f6ad-130">Para mostrar el nombre principal de usuario de las cuentas de usuario, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-130">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="4f6ad-131">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-131">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4f6ad-132">Obtener toda la información de las cuentas de usuario (**Get-AzureADUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-132">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-133">Ordenar la lista de nombres principales de usuario alfabéticamente (**ordenar UserPrincipalName**) y enviarlo al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-133">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-134">Mostrar solo la propiedad de nombre principal de usuario para cada cuenta (**Seleccione UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-134">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="4f6ad-135">Mostrar una pantalla a la vez (**más**).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-135">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="4f6ad-136">En este comando se enumeran todas las cuentas.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-136">This command will list all of your accounts.</span></span> <span data-ttu-id="4f6ad-137">Si desea mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellido), rellene la variable **$username** a continuación (quitando los \< and > caracteres) y, a continuación, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-137">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4f6ad-138">En este ejemplo se muestra el nombre principal de usuario de la cuenta de usuario con el nombre para mostrar de los alféizares de Caleb.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-138">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4f6ad-139">Mediante el uso de una variable **$UPN** , puede realizar cambios en las cuentas individuales en función de su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-139">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="4f6ad-140">Este es un ejemplo de configuración de la ubicación de uso de Belinda Newman en Francia, pero especificando su nombre para mostrar en lugar de su nombre principal de usuario:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-140">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="4f6ad-141">Cambiar las propiedades de todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="4f6ad-141">Change properties for all user accounts</span></span>

<span data-ttu-id="4f6ad-142">Para cambiar las propiedades de todos los usuarios, puede usar la combinación de los cmdlets **Get-AzureADUser** y **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="4f6ad-142">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="4f6ad-143">En el siguiente ejemplo se cambia a Francia la ubicación de uso de todos los usuarios:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-143">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="4f6ad-144">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-144">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4f6ad-145">Obtener toda la información de las cuentas de usuario (**Get-AzureADUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-145">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-146">Establezca la ubicación del usuario en Francia (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-146">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="4f6ad-147">Cambiar las propiedades de un conjunto específico de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="4f6ad-147">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="4f6ad-148">Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar la combinación de los cmdlets **Get-AzureADUser**, **Where**y **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="4f6ad-148">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="4f6ad-149">En el siguiente ejemplo se cambia a Francia la ubicación de uso de todos los usuarios del departamento de contabilidad:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-149">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="4f6ad-150">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-150">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4f6ad-151">Obtener toda la información de las cuentas de usuario (**Get-AzureADUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-151">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-152">Busque todas las cuentas de usuario que tengan su propiedad Department establecida en "Accounting" (**donde {$ _. Department-EQ "Accounting"}**) y enviar la información resultante al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-152">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-153">Establezca la ubicación del usuario en Francia (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-153">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4f6ad-154">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f6ad-154">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4f6ad-155">Para configurar las propiedades de las cuentas de usuario con el módulo Microsoft Azure Active Directory para Windows PowerShell, use el cmdlet **set-MsolUser** y especifique las propiedades que se van a establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-155">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="4f6ad-156">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-156">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="4f6ad-157">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-157">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="4f6ad-158">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-158">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="4f6ad-159">Cambiar las propiedades de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="4f6ad-159">Change properties for a specific user account</span></span>

<span data-ttu-id="4f6ad-160">Para configurar las propiedades de una cuenta de usuario específica, use el cmdlet [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) y especifique las propiedades que se van a establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-160">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="4f6ad-161">La cuenta se identifica con el parámetro **-UserPrincipalName** y se establecen o cambian las propiedades específicas con parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-161">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="4f6ad-162">A continuación se muestra una lista con los parámetros más comunes.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-162">Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="4f6ad-163">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-163">-City "\<city name>"</span></span>
    
- <span data-ttu-id="4f6ad-164">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-164">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="4f6ad-165">-Departamento " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-165">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="4f6ad-166">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-166">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="4f6ad-167">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-167">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="4f6ad-168">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-168">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="4f6ad-169">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-169">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="4f6ad-170">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-170">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="4f6ad-171">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-171">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="4f6ad-172">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-172">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="4f6ad-173">-CódigoPostal " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-173">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="4f6ad-174">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-174">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="4f6ad-175">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-175">-State "\<state name>"</span></span>
    
- <span data-ttu-id="4f6ad-176">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-176">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="4f6ad-177">-Title " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-177">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="4f6ad-178">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="4f6ad-178">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="4f6ad-179">Este es el código de país o región de dos letras ISO 3166-1 (a2).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-179">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="4f6ad-180">Consulte [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) para obtener más parámetros.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-180">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="4f6ad-181">Para ver los nombres principales de usuario de todos los usuarios, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-181">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="4f6ad-182">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-182">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4f6ad-183">Obtener toda la información de las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-183">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-184">Ordenar la lista de nombres principales de usuario alfabéticamente (**ordenar UserPrincipalName**) y enviarlo al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-184">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-185">Mostrar solo la propiedad de nombre principal de usuario para cada cuenta (**Seleccione UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-185">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="4f6ad-186">Mostrar una pantalla a la vez (**más**).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-186">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="4f6ad-187">En este comando se enumeran todas las cuentas.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-187">This command will list all of your accounts.</span></span> <span data-ttu-id="4f6ad-188">Si desea mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellido), rellene la variable **$username** a continuación (quitando los \< and > caracteres) y, a continuación, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-188">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4f6ad-189">En este ejemplo se muestra el nombre principal de usuario del usuario denominado Caleb alféizares.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-189">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4f6ad-190">Mediante el uso de una variable **$UPN** , puede realizar cambios en las cuentas individuales en función de su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="4f6ad-190">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="4f6ad-191">Este es un ejemplo de configuración de la ubicación de uso de Belinda Newman en Francia, pero especificando su nombre para mostrar en lugar de su nombre principal de usuario:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-191">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="4f6ad-192">Cambiar las propiedades de todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="4f6ad-192">Change properties for all user accounts</span></span>

<span data-ttu-id="4f6ad-p110">Para cambiar las propiedades de todos los usuarios, puede combinar los cmdlets **Get-MsolUser** y **Set-MsolUser**. En el siguiente ejemplo se cambia a Francia la ubicación de uso de todos los usuarios:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-p110">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="4f6ad-195">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-195">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4f6ad-196">Obtener toda la información de las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-196">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-197">Establezca la ubicación del usuario en Francia (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-197">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="4f6ad-198">Cambiar las propiedades de un conjunto específico de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="4f6ad-198">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="4f6ad-199">Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar la combinación de los cmdlets **Get-msoluser**, **Where**y **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="4f6ad-199">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="4f6ad-200">En el siguiente ejemplo se cambia a Francia la ubicación de uso de todos los usuarios del departamento de contabilidad:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-200">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="4f6ad-201">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="4f6ad-201">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4f6ad-202">Obtener toda la información de las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-202">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-203">Busque todas las cuentas de usuario que tengan su propiedad Department establecida en "Accounting" (**donde {$ _. Department-EQ "Accounting"}**) y enviar la información resultante al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-203">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="4f6ad-204">Establezca la ubicación del usuario en Francia (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="4f6ad-204">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>


## <a name="see-also"></a><span data-ttu-id="4f6ad-205">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f6ad-205">See also</span></span>

[<span data-ttu-id="4f6ad-206">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f6ad-206">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4f6ad-207">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f6ad-207">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4f6ad-208">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f6ad-208">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
