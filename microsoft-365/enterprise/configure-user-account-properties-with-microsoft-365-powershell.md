---
title: Configurar las propiedades de la cuenta de usuario 365 de Microsoft con PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 'Resumen: Use PowerShell para Microsoft 365 para configurar las propiedades de una o varias cuentas de usuario en su inquilino de Microsoft 365.'
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693588"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="a5f8e-103">Configurar las propiedades de la cuenta de usuario 365 de Microsoft con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5f8e-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="a5f8e-104">*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a5f8e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a5f8e-105">Aunque puede usar el centro de administración de Microsoft 365 para configurar las propiedades de las cuentas de usuario de su inquilino de Microsoft 365, también puede usar PowerShell y hacer algunas cosas que el centro de administración de Microsoft 365 no puede.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a5f8e-106">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="a5f8e-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a5f8e-107">Para configurar las propiedades de las cuentas de usuario con el módulo Azure Active Directory PowerShell para Graph, use el cmdlet [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) y especifique las propiedades que se deben establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="a5f8e-108">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="a5f8e-109">Cambiar las propiedades de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="a5f8e-109">Change properties for a specific user account</span></span>

<span data-ttu-id="a5f8e-110">La cuenta se identifica con el parámetro **-objectId** y se establecen o cambian las propiedades específicas con parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-110">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="a5f8e-111">A continuación se muestra una lista de los parámetros más comunes.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-111">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="a5f8e-112">-Departamento " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="a5f8e-113">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="a5f8e-114">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="a5f8e-115">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="a5f8e-116">-2º apellido " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="a5f8e-117">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="a5f8e-118">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="a5f8e-119">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="a5f8e-120">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="a5f8e-121">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="a5f8e-122">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="a5f8e-123">-CódigoPostal " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="a5f8e-124">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="a5f8e-125">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="a5f8e-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="a5f8e-127">Este es el código de país o región de dos letras ISO 3166-1 (a2).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="a5f8e-128">Consulte [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) para obtener más parámetros.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) for additional parameters.</span></span>


<span data-ttu-id="a5f8e-129">Para mostrar el nombre principal de usuario de las cuentas de usuario, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-129">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="a5f8e-130">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-130">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="a5f8e-131">Obtener toda la información de las cuentas de usuario (**Get-AzureADUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-131">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-132">Ordenar la lista de nombres principales de usuario alfabéticamente (**ordenar UserPrincipalName**) y enviarlo al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-132">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-133">Mostrar solo la propiedad de nombre principal de usuario para cada cuenta (**Seleccione UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-133">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="a5f8e-134">Mostrar una pantalla a la vez (**más**).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-134">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="a5f8e-135">En este comando se enumeran todas las cuentas.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-135">This command will list all of your accounts.</span></span> <span data-ttu-id="a5f8e-136">Si desea mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellido), rellene la variable **$username** a continuación (quitando los \< and > caracteres) y, a continuación, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-136">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="a5f8e-137">En este ejemplo se muestra el nombre principal de usuario de la cuenta de usuario con el nombre para mostrar de los alféizares de Caleb.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-137">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="a5f8e-138">Mediante el uso de una variable **$UPN** , puede realizar cambios en las cuentas individuales en función de su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-138">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="a5f8e-139">Este es un ejemplo de configuración de la ubicación de uso de Belinda Newman en Francia, pero especificando su nombre para mostrar en lugar de su nombre principal de usuario:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-139">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="a5f8e-140">Cambiar las propiedades de todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="a5f8e-140">Change properties for all user accounts</span></span>

<span data-ttu-id="a5f8e-141">Para cambiar las propiedades de todos los usuarios, puede usar la combinación de los cmdlets **Get-AzureADUser** y **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="a5f8e-141">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="a5f8e-142">En el siguiente ejemplo se cambia a Francia la ubicación de uso de todos los usuarios:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-142">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="a5f8e-143">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-143">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="a5f8e-144">Obtener toda la información de las cuentas de usuario (**Get-AzureADUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-144">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-145">Establezca la ubicación del usuario en Francia (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-145">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="a5f8e-146">Cambiar las propiedades de un conjunto específico de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="a5f8e-146">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="a5f8e-147">Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar la combinación de los cmdlets **Get-AzureADUser**, **Where**y **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="a5f8e-147">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="a5f8e-148">En el siguiente ejemplo se cambia a Francia la ubicación de uso de todos los usuarios del departamento de contabilidad:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-148">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="a5f8e-149">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-149">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="a5f8e-150">Obtener toda la información de las cuentas de usuario (**Get-AzureADUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-150">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-151">Busque todas las cuentas de usuario que tengan su propiedad Department establecida en "Accounting" (**donde {$ _. Department-EQ "Accounting"}**) y enviar la información resultante al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-151">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-152">Establezca la ubicación del usuario en Francia (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-152">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a5f8e-153">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5f8e-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a5f8e-154">Para configurar las propiedades de las cuentas de usuario con el módulo Microsoft Azure Active Directory para Windows PowerShell, use el cmdlet **set-MsolUser** y especifique las propiedades que se van a establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-154">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="a5f8e-155">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-155">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="a5f8e-156">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-156">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="a5f8e-157">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-157">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="a5f8e-158">Cambiar las propiedades de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="a5f8e-158">Change properties for a specific user account</span></span>

<span data-ttu-id="a5f8e-159">Para configurar las propiedades de una cuenta de usuario específica, use el cmdlet [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) y especifique las propiedades que se van a establecer o cambiar.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-159">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="a5f8e-160">La cuenta se identifica con el parámetro **-UserPrincipalName** y se establecen o cambian las propiedades específicas con parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-160">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="a5f8e-161">A continuación se muestra una lista con los parámetros más comunes.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-161">Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="a5f8e-162">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-162">-City "\<city name>"</span></span>
    
- <span data-ttu-id="a5f8e-163">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-163">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="a5f8e-164">-Departamento " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-164">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="a5f8e-165">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-165">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="a5f8e-166">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-166">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="a5f8e-167">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-167">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="a5f8e-168">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-168">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="a5f8e-169">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-169">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="a5f8e-170">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-170">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="a5f8e-171">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-171">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="a5f8e-172">-CódigoPostal " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-172">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="a5f8e-173">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-173">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="a5f8e-174">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-174">-State "\<state name>"</span></span>
    
- <span data-ttu-id="a5f8e-175">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-175">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="a5f8e-176">-Title " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-176">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="a5f8e-177">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="a5f8e-177">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="a5f8e-178">Este es el código de país o región de dos letras ISO 3166-1 (a2).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-178">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="a5f8e-179">Consulte [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) para obtener más parámetros.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-179">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="a5f8e-180">Para ver los nombres principales de usuario de todos los usuarios, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-180">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="a5f8e-181">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="a5f8e-182">Obtener toda la información de las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-182">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-183">Ordenar la lista de nombres principales de usuario alfabéticamente (**ordenar UserPrincipalName**) y enviarlo al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-183">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-184">Mostrar solo la propiedad de nombre principal de usuario para cada cuenta (**Seleccione UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-184">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="a5f8e-185">Mostrar una pantalla a la vez (**más**).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-185">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="a5f8e-186">En este comando se enumeran todas las cuentas.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-186">This command will list all of your accounts.</span></span> <span data-ttu-id="a5f8e-187">Si desea mostrar el nombre principal de usuario de una cuenta en función de su nombre para mostrar (nombre y apellido), rellene la variable **$username** a continuación (quitando los \< and > caracteres) y, a continuación, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-187">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="a5f8e-188">En este ejemplo se muestra el nombre principal de usuario del usuario denominado Caleb alféizares.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-188">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="a5f8e-189">Mediante el uso de una variable **$UPN** , puede realizar cambios en las cuentas individuales en función de su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-189">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="a5f8e-190">Este es un ejemplo de configuración de la ubicación de uso de Belinda Newman en Francia, pero especificando su nombre para mostrar en lugar de su nombre principal de usuario:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-190">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="a5f8e-191">Cambiar las propiedades de todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="a5f8e-191">Change properties for all user accounts</span></span>

<span data-ttu-id="a5f8e-p110">Para cambiar las propiedades de todos los usuarios, puede combinar los cmdlets **Get-MsolUser** y **Set-MsolUser**. En el siguiente ejemplo se cambia a Francia la ubicación de uso de todos los usuarios:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-p110">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="a5f8e-194">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-194">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="a5f8e-195">Obtener toda la información de las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-195">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-196">Establezca la ubicación del usuario en Francia (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-196">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="a5f8e-197">Cambiar las propiedades de un conjunto específico de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="a5f8e-197">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="a5f8e-198">Para cambiar las propiedades de un conjunto específico de cuentas de usuario, puede usar la combinación de los cmdlets **Get-msoluser**, **Where**y **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="a5f8e-198">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="a5f8e-199">En el siguiente ejemplo se cambia a Francia la ubicación de uso de todos los usuarios del departamento de contabilidad:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-199">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="a5f8e-200">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="a5f8e-200">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="a5f8e-201">Obtener toda la información de las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-201">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-202">Busque todas las cuentas de usuario que tengan su propiedad Department establecida en "Accounting" (**donde {$ _. Department-EQ "Accounting"}**) y enviar la información resultante al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-202">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="a5f8e-203">Establezca la ubicación del usuario en Francia (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="a5f8e-203">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    

## <a name="see-also"></a><span data-ttu-id="a5f8e-204">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a5f8e-204">See also</span></span>

[<span data-ttu-id="a5f8e-205">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5f8e-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a5f8e-206">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5f8e-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a5f8e-207">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5f8e-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
