---
title: Crear cuentas de usuario de Microsoft 365 con PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Cómo usar PowerShell para crear cuentas de usuario individuales o múltiples de Microsoft 365.
ms.openlocfilehash: d96de72ca3e7c4a439665c3ebf751a8fe25ce572
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754215"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="e9079-103">Crear cuentas de usuario de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9079-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="e9079-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e9079-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e9079-105">Puede usar PowerShell para Microsoft 365 para crear cuentas de usuario de forma eficaz, incluidas varias cuentas.</span><span class="sxs-lookup"><span data-stu-id="e9079-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="e9079-106">Al crear cuentas de usuario en PowerShell, siempre se requieren ciertas propiedades de cuenta.</span><span class="sxs-lookup"><span data-stu-id="e9079-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="e9079-107">Otras propiedades no son necesarias, pero son importantes.</span><span class="sxs-lookup"><span data-stu-id="e9079-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="e9079-108">Vea la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="e9079-108">See the following table.</span></span>
  
|<span data-ttu-id="e9079-109">**Nombre de propiedad**</span><span class="sxs-lookup"><span data-stu-id="e9079-109">**Property name**</span></span>|<span data-ttu-id="e9079-110">**Obligatorio**</span><span class="sxs-lookup"><span data-stu-id="e9079-110">**Required?**</span></span>|<span data-ttu-id="e9079-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e9079-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9079-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="e9079-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="e9079-113">Sí</span><span class="sxs-lookup"><span data-stu-id="e9079-113">Yes</span></span>  <br/> |<span data-ttu-id="e9079-114">Este es el nombre para mostrar que se usa en los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9079-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="e9079-115">Por ejemplo, *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="e9079-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="e9079-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="e9079-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="e9079-117">Sí</span><span class="sxs-lookup"><span data-stu-id="e9079-117">Yes</span></span>  <br/> |<span data-ttu-id="e9079-118">Este es el nombre de cuenta que se usa para iniciar sesión en los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9079-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="e9079-119">Por ejemplo, *CalebS \@ contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="e9079-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="e9079-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="e9079-120">**FirstName**</span></span> <br/> |<span data-ttu-id="e9079-121">No</span><span class="sxs-lookup"><span data-stu-id="e9079-121">No</span></span>  <br/> ||
|<span data-ttu-id="e9079-122">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="e9079-122">**LastName**</span></span> <br/> |<span data-ttu-id="e9079-123">No</span><span class="sxs-lookup"><span data-stu-id="e9079-123">No</span></span>  <br/> ||
|<span data-ttu-id="e9079-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="e9079-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="e9079-125">No</span><span class="sxs-lookup"><span data-stu-id="e9079-125">No</span></span>  <br/> |<span data-ttu-id="e9079-126">Este es el plan de licencias (también conocido como el plan de licencia o SKU) desde el que se asigna una licencia disponible a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e9079-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="e9079-127">La licencia define los servicios de Microsoft 365 que están disponibles para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e9079-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="e9079-128">No es necesario asignar una licencia a un usuario al crear la cuenta, pero la cuenta debe tener una licencia para acceder a los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9079-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="e9079-129">Dispone de 30 días para conceder una licencia a la cuenta de usuario después de crearla.</span><span class="sxs-lookup"><span data-stu-id="e9079-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="e9079-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="e9079-130">**Password**</span></span> <br/> |<span data-ttu-id="e9079-131">No</span><span class="sxs-lookup"><span data-stu-id="e9079-131">No</span></span>  <br/> | <span data-ttu-id="e9079-132">Si no especifica una contraseña, se asignará una contraseña aleatoria a la cuenta de usuario y la contraseña será visible en los resultados del comando.</span><span class="sxs-lookup"><span data-stu-id="e9079-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="e9079-133">Si especifica una contraseña, debe tener de 8 a 16 caracteres de texto ASCII de los siguientes tipos: letras minúsculas, letras mayúsculas, números y símbolos.</span><span class="sxs-lookup"><span data-stu-id="e9079-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="e9079-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="e9079-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="e9079-135">No</span><span class="sxs-lookup"><span data-stu-id="e9079-135">No</span></span>  <br/> |<span data-ttu-id="e9079-136">Se trata de un código de país válido ISO 3166-1 alpha-2.</span><span class="sxs-lookup"><span data-stu-id="e9079-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="e9079-137">Por ejemplo, *EE. UU.* para Estados Unidos y *FR* para Francia.</span><span class="sxs-lookup"><span data-stu-id="e9079-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="e9079-138">Es importante proporcionar este valor, ya que algunos servicios de Microsoft 365 no están disponibles en determinados países.</span><span class="sxs-lookup"><span data-stu-id="e9079-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="e9079-139">No puede asignar una licencia a una cuenta de usuario a menos que la cuenta tenga este valor configurado.</span><span class="sxs-lookup"><span data-stu-id="e9079-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="e9079-140">Para obtener más información, consulte [Sobre las restricciones de licencia](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="e9079-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="e9079-141">[Obtenga información sobre cómo crear cuentas de usuario](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) mediante el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9079-141">[Learn how to create user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="e9079-142">Para obtener una lista de recursos adicionales, vea [Administrar usuarios y grupos.](https://docs.microsoft.com/microsoft-365/admin/add-users/)</span><span class="sxs-lookup"><span data-stu-id="e9079-142">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e9079-143">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="e9079-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e9079-144">En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="e9079-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="e9079-145">Después de conectarse, use la siguiente sintaxis para crear una cuenta individual:</span><span class="sxs-lookup"><span data-stu-id="e9079-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="e9079-146">En este ejemplo se crea una cuenta para el usuario estadounidense *Caleb Sills:*</span><span class="sxs-lookup"><span data-stu-id="e9079-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e9079-147">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9079-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e9079-148">En primer [lugar, conéctese a su espacio empresarial de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e9079-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="e9079-149">Cree una cuenta de usuario individual</span><span class="sxs-lookup"><span data-stu-id="e9079-149">Create an individual user account</span></span>

<span data-ttu-id="e9079-150">Para crear una cuenta individual, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9079-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="e9079-151">PowerShell Core no admite el Módulo Microsoft Azure Active Directory para Windows PowerShell módulo y cmdlets que tienen *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e9079-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="e9079-152">Ejecute estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9079-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="e9079-153">Para obtener una lista de los nombres de planes de licencias disponibles, use este comando:</span><span class="sxs-lookup"><span data-stu-id="e9079-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="e9079-154">En este ejemplo se crea una cuenta para el usuario estadounidense *Caleb Sills* y se asigna una licencia desde el plan de licencias `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="e9079-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="e9079-155">Crear varias cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e9079-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="e9079-p108">Cree un archivo de valores separados por comas (CSV) que contenga la información necesaria de la cuenta de usuario. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e9079-p108">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="e9079-158">Los nombres de columna y su orden en la primera fila del archivo CSV son arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="e9079-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="e9079-159">Pero asegúrese de que el orden de los datos del resto del archivo coincide con el orden de los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="e9079-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="e9079-160">Y use los nombres de columna para los valores de parámetro en el comando de PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9079-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="e9079-161">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9079-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="e9079-162">En este ejemplo se crean cuentas de usuario a partir del archivo *C:\My Documents\NewAccounts.csv* y se registra el resultado en un archivo denominado *C:\My Documents\NewAccountResults.csv*.</span><span class="sxs-lookup"><span data-stu-id="e9079-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="e9079-163">Revise el archivo de salida para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="e9079-163">Review the output file to see the results.</span></span> <span data-ttu-id="e9079-164">No especificamos contraseñas, por lo que las contraseñas aleatorias generadas por Microsoft 365 son visibles en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e9079-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e9079-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9079-165">See also</span></span>

[<span data-ttu-id="e9079-166">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9079-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e9079-167">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9079-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e9079-168">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9079-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
