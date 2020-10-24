---
title: Asignar roles a cuentas de usuario de Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: En este artículo, obtenga información sobre cómo usar PowerShell para Microsoft 365 de forma rápida y sencilla para asignar roles de administrador a las cuentas de usuario.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754203"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="92fe4-103">Asignar roles de administrador a las cuentas de usuario de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="92fe4-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="92fe4-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="92fe4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="92fe4-105">Puede asignar roles fácilmente a las cuentas de usuario con PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="92fe4-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="92fe4-106">Obtenga información sobre cómo  [asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) a las cuentas de usuario con el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="92fe4-106">Learn how to  [assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="92fe4-107">Para obtener una lista de recursos adicionales, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="92fe4-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="92fe4-108">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="92fe4-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="92fe4-109">En primer lugar, use una cuenta de administrador global para [conectarse a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="92fe4-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="92fe4-110">A continuación, identifique el nombre de inicio de sesión de la cuenta de usuario que desea agregar a un rol (ejemplo: fredsm \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="92fe4-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="92fe4-111">Esto también se conoce como el nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="92fe4-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="92fe4-112">A continuación, determine el nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="92fe4-112">Next, determine the name of the role.</span></span> <span data-ttu-id="92fe4-113">Consulte [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="92fe4-113">See [administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="92fe4-114">Preste atención a las notas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="92fe4-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="92fe4-115">Algunos nombres de rol son diferentes para Azure Active Directory (Azure AD) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92fe4-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="92fe4-116">Por ejemplo, el rol de *Administrador de SharePoint* en el centro de administración de Microsoft 365 es el administrador de *servicios de SharePoint* en Azure ad PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92fe4-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="92fe4-117">Después, rellene los nombres de inicio de sesión y de rol y ejecute estos comandos:</span><span class="sxs-lookup"><span data-stu-id="92fe4-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="92fe4-118">A continuación, se muestra un ejemplo de un conjunto de comandos completado que asigna el rol de administrador de servicios de SharePoint a la cuenta \* \@ contoso.com de Laura\* :</span><span class="sxs-lookup"><span data-stu-id="92fe4-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="92fe4-119">Para mostrar la lista de nombres de usuario para un rol de administrador específico, use estos comandos.</span><span class="sxs-lookup"><span data-stu-id="92fe4-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="92fe4-120">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92fe4-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="92fe4-121">En primer lugar, use una cuenta de administrador global para [conectarse a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="92fe4-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="92fe4-122">Para un cambio de función único</span><span class="sxs-lookup"><span data-stu-id="92fe4-122">For a single role change</span></span>

<span data-ttu-id="92fe4-123">Las formas más comunes de especificar la cuenta de usuario es mediante el uso de su nombre para mostrar o su nombre de correo electrónico, que también se conoce como el nombre de inicio de sesión o el nombre principal del usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="92fe4-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="92fe4-124">Mostrar los nombres de las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="92fe4-124">Display names of user accounts</span></span>

<span data-ttu-id="92fe4-125">Si se usa para trabajar con los nombres para mostrar de las cuentas de usuario, determine la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="92fe4-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="92fe4-126">La cuenta de usuario que desea configurar</span><span class="sxs-lookup"><span data-stu-id="92fe4-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="92fe4-127">Para especificar la cuenta de usuario, debe determinar su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="92fe4-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="92fe4-128">Para obtener una lista completa de las cuentas, use este comando:</span><span class="sxs-lookup"><span data-stu-id="92fe4-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="92fe4-129">Este comando muestra el nombre para mostrar de las cuentas de usuario, ordenados por nombre para mostrar, de una en una pantalla cada vez.</span><span class="sxs-lookup"><span data-stu-id="92fe4-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="92fe4-130">Puede filtrar la lista para un conjunto más pequeño con el cmdlet **Where** .</span><span class="sxs-lookup"><span data-stu-id="92fe4-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="92fe4-131">Vea el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="92fe4-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="92fe4-132">PowerShell Core no es compatible con el módulo Microsoft Azure Active Directory para el módulo y los cmdlets de Windows PowerShell con *msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="92fe4-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="92fe4-133">Ejecute estos cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92fe4-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="92fe4-134">Este comando muestra sólo las cuentas de usuario para las que el nombre para mostrar empieza por "John".</span><span class="sxs-lookup"><span data-stu-id="92fe4-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="92fe4-135">El rol que desea asignar</span><span class="sxs-lookup"><span data-stu-id="92fe4-135">The role you want to assign</span></span>
    
    <span data-ttu-id="92fe4-136">Para mostrar la lista de roles de administrador disponibles que puede asignar a las cuentas de usuario, use este comando:</span><span class="sxs-lookup"><span data-stu-id="92fe4-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="92fe4-137">Después de determinar el nombre para mostrar de la cuenta y el nombre de la función, use estos comandos para asignar el rol a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="92fe4-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="92fe4-138">Pegue los comandos en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="92fe4-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="92fe4-139">Para las variables *$dispName* y *$roleName* , reemplace el texto de la descripción con sus valores.</span><span class="sxs-lookup"><span data-stu-id="92fe4-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="92fe4-140">Quite los \< and > caracteres pero mantenga las comillas.</span><span class="sxs-lookup"><span data-stu-id="92fe4-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="92fe4-141">Pegue las líneas modificadas en la ventana Módulo Microsoft Azure Active Directory para Windows PowerShell para ejecutarlas.</span><span class="sxs-lookup"><span data-stu-id="92fe4-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="92fe4-142">Como alternativa, puede usar el entorno de script integrado (ISE) de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92fe4-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="92fe4-143">A continuación, se muestra un ejemplo de un conjunto de comandos completado:</span><span class="sxs-lookup"><span data-stu-id="92fe4-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="92fe4-144">Nombres de inicio de sesión de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="92fe4-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="92fe4-145">Si se usa para trabajar con los nombres de inicio de sesión o UPN de las cuentas de usuario, determine la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="92fe4-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="92fe4-146">El UPN de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="92fe4-146">The user account's UPN</span></span>
    
    <span data-ttu-id="92fe4-147">Si no conoce el UPN, use este comando:</span><span class="sxs-lookup"><span data-stu-id="92fe4-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="92fe4-148">Este comando enumera el UPN de las cuentas de usuario, ordenados por UPN, de una en una pantalla a la vez.</span><span class="sxs-lookup"><span data-stu-id="92fe4-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="92fe4-149">Puede usar el cmdlet **Where** para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="92fe4-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="92fe4-150">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="92fe4-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="92fe4-151">Este comando muestra sólo las cuentas de usuario para las que el nombre para mostrar empieza por "John".</span><span class="sxs-lookup"><span data-stu-id="92fe4-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="92fe4-152">El rol que desea asignar</span><span class="sxs-lookup"><span data-stu-id="92fe4-152">The role you want to assign</span></span>
    
    <span data-ttu-id="92fe4-153">Para mostrar la lista de los roles disponibles que puede asignar a las cuentas de usuario, use este comando:</span><span class="sxs-lookup"><span data-stu-id="92fe4-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="92fe4-154">Una vez que tenga el UPN de la cuenta y el nombre del rol, use estos comandos para asignar el rol a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="92fe4-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="92fe4-155">Copie los comandos y péguelos en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="92fe4-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="92fe4-156">Para las variables **$upnName** y **$roleName** .</span><span class="sxs-lookup"><span data-stu-id="92fe4-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="92fe4-157">Reemplace el texto de la descripción con sus valores.</span><span class="sxs-lookup"><span data-stu-id="92fe4-157">Replace the description text with their values.</span></span> <span data-ttu-id="92fe4-158">Quite los \< and > caracteres pero mantenga las comillas.</span><span class="sxs-lookup"><span data-stu-id="92fe4-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="92fe4-159">Pegue las líneas modificadas en la ventana módulo de Microsoft Azure Active Directory para Windows PowerShell para ejecutarlas.</span><span class="sxs-lookup"><span data-stu-id="92fe4-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="92fe4-160">Como alternativa, puede usar Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="92fe4-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="92fe4-161">A continuación, se muestra un ejemplo de un conjunto de comandos completado:</span><span class="sxs-lookup"><span data-stu-id="92fe4-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="92fe4-162">Varios cambios de funciones</span><span class="sxs-lookup"><span data-stu-id="92fe4-162">Multiple role changes</span></span>

<span data-ttu-id="92fe4-163">Para varios cambios de funciones, determine la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="92fe4-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="92fe4-164">Qué cuentas de usuario desea configurar.</span><span class="sxs-lookup"><span data-stu-id="92fe4-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="92fe4-165">Puede usar los métodos de la sección anterior para recopilar el conjunto de nombres para mostrar o UPN.</span><span class="sxs-lookup"><span data-stu-id="92fe4-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="92fe4-166">Qué roles desea asignar a cada cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="92fe4-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="92fe4-167">Para mostrar la lista de los roles disponibles que puede asignar a las cuentas de usuario, use este comando:</span><span class="sxs-lookup"><span data-stu-id="92fe4-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="92fe4-168">A continuación, cree un archivo de texto de valores separados por comas (CSV) que tenga los campos nombre para mostrar o nombre de rol y UPN.</span><span class="sxs-lookup"><span data-stu-id="92fe4-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="92fe4-169">Puede hacerlo fácilmente en Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="92fe4-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="92fe4-170">Este es un ejemplo de nombres para mostrar:</span><span class="sxs-lookup"><span data-stu-id="92fe4-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="92fe4-171">A continuación, rellene la ubicación del archivo CSV y ejecute los comandos resultantes en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92fe4-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="92fe4-172">Este es un ejemplo para los UPN:</span><span class="sxs-lookup"><span data-stu-id="92fe4-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="92fe4-173">A continuación, rellene la ubicación del archivo CSV y ejecute los comandos resultantes en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92fe4-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="92fe4-174">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="92fe4-174">See also</span></span>

- [<span data-ttu-id="92fe4-175">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="92fe4-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="92fe4-176">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="92fe4-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="92fe4-177">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="92fe4-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
