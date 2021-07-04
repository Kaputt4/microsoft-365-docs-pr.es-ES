---
title: Ver Microsoft 365 de usuario con PowerShell
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Obtenga información sobre cómo ver, enumerar o mostrar sus Microsoft 365 de usuario de diferentes maneras con PowerShell.
ms.openlocfilehash: 77219fb89430ed257ef2a68a7b24bf9ebac715b2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290176"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="900f0-103">Ver Microsoft 365 de usuario con PowerShell</span><span class="sxs-lookup"><span data-stu-id="900f0-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="900f0-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="900f0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="900f0-105">Puede usar el Centro de administración de Microsoft 365 para ver las cuentas de su Microsoft 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="900f0-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="900f0-106">PowerShell para Microsoft 365 habilita esto, pero también proporciona funciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="900f0-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="900f0-107">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="900f0-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="900f0-108">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="900f0-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="900f0-109">Ver todas las cuentas</span><span class="sxs-lookup"><span data-stu-id="900f0-109">View all accounts</span></span>

<span data-ttu-id="900f0-110">Para mostrar la lista completa de cuentas de usuario, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="900f0-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="900f0-111">Debe obtener información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="900f0-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="900f0-112">Ver una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="900f0-112">View a specific account</span></span>

<span data-ttu-id="900f0-113">Para mostrar una cuenta de usuario específica, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="900f0-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="900f0-114">Rellene el nombre de cuenta de inicio de sesión de la cuenta de usuario, que también se conoce como nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="900f0-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="900f0-115">Quite los caracteres "<" y ">".</span><span class="sxs-lookup"><span data-stu-id="900f0-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="900f0-116">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="900f0-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="900f0-117">Ver valores de propiedad adicionales para una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="900f0-117">View additional property values for a specific account</span></span>

<span data-ttu-id="900f0-118">De forma predeterminada, el cmdlet **Get-AzureADUser** solo muestra las propiedades *ObjectID,* *DisplayName* y *UserPrincipalName* de las cuentas.</span><span class="sxs-lookup"><span data-stu-id="900f0-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="900f0-119">Para ser más selectivo acerca de las propiedades que se mostrarán, use el cmdlet **Select** en combinación con el cmdlet **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="900f0-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="900f0-120">Para combinar los dos cmdlets, use el carácter "canalización" ("|"), que indica a Azure Active Directory PowerShell para Graph que tome los resultados de un comando y envíelo al siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="900f0-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="900f0-121">Este es un comando de ejemplo que muestra *DisplayName,* *Department* y *UsageLocation* para cada cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="900f0-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="900f0-122">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="900f0-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="900f0-123">Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="900f0-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="900f0-124">Mostrar solo el nombre de cuenta de usuario, el departamento y la ubicación de uso (**Seleccione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="900f0-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="900f0-125">Para ver todas las propiedades de una cuenta de usuario específica, use el cmdlet **Select** y el carácter comodín (\*).</span><span class="sxs-lookup"><span data-stu-id="900f0-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="900f0-126">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="900f0-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="900f0-127">Como otro ejemplo, ejecute el siguiente comando para comprobar el estado habilitado de una cuenta de usuario específica:</span><span class="sxs-lookup"><span data-stu-id="900f0-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="900f0-128">Ver estado de sincronización de cuentas</span><span class="sxs-lookup"><span data-stu-id="900f0-128">View account synchronization status</span></span>

<span data-ttu-id="900f0-129">Las cuentas de usuario tienen dos orígenes:</span><span class="sxs-lookup"><span data-stu-id="900f0-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="900f0-130">Windows Server Active Directory (AD), que son cuentas que se sincronizan desde AD local a la nube.</span><span class="sxs-lookup"><span data-stu-id="900f0-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="900f0-131">Azure Active Directory (Azure AD) cuentas de AD, que se crean directamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="900f0-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="900f0-132">El siguiente comando indica a PowerShell que obtenga todos los usuarios que tengan el atributo *DirSyncEnabled* establecido en *True*.</span><span class="sxs-lookup"><span data-stu-id="900f0-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="900f0-133">Puedes usarlo para buscar cuentas que se sincronicen desde AD local.</span><span class="sxs-lookup"><span data-stu-id="900f0-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="900f0-134">El siguiente comando indica a PowerShell que obtenga todos los usuarios que tengan el atributo *DirSyncEnabled* establecido en *False*.</span><span class="sxs-lookup"><span data-stu-id="900f0-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="900f0-135">Puede usarlo para buscar cuentas solo en la nube.</span><span class="sxs-lookup"><span data-stu-id="900f0-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="900f0-136">Ver cuentas basadas en una propiedad común</span><span class="sxs-lookup"><span data-stu-id="900f0-136">View accounts based on a common property</span></span>

<span data-ttu-id="900f0-137">Para ser más selectivo acerca de la lista de cuentas que se va a mostrar, puede usar el cmdlet **Where** en combinación con el cmdlet **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="900f0-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="900f0-138">Para combinar los dos cmdlets, use el carácter "canalización" ("|"), que indica a Azure Active Directory PowerShell para Graph que tome los resultados de un comando y envíelo al siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="900f0-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="900f0-139">Este es un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="900f0-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="900f0-140">Este comando indica Azure Active Directory PowerShell para Graph a:</span><span class="sxs-lookup"><span data-stu-id="900f0-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="900f0-141">Obtenga toda la información de las cuentas de usuario (**Get-AzureADUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="900f0-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="900f0-142">Busque todas las cuentas de usuario que tienen una ubicación de uso no especificada (**Donde {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="900f0-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="900f0-143">Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas para las que la propiedad de cuenta de usuario UsageLocation (**$ \_ . UsageLocation**) no se especifica (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="900f0-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="900f0-144">La **propiedad UsageLocation** es solo una de las muchas propiedades asociadas a una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="900f0-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="900f0-145">Para mostrar todas las propiedades de una cuenta de usuario específica, use el cmdlet **Select** y el carácter comodín (\*).</span><span class="sxs-lookup"><span data-stu-id="900f0-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="900f0-146">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="900f0-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="900f0-147">Por ejemplo, **City** es el nombre de una propiedad de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="900f0-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="900f0-148">Puede usar el siguiente comando para enumerar todas las cuentas de usuarios que viven en Londres:</span><span class="sxs-lookup"><span data-stu-id="900f0-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="900f0-149">La sintaxis del cmdlet **Where** en estos ejemplos es **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="900f0-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="900f0-150">[nombre de propiedad de cuenta de usuario] [operador de comparación] [value] **}**.> [operador de comparación] es **-eq** para igual, **-ne** para no es igual, **-lt** para menor que, **-gt** para mayor que y otros.</span><span class="sxs-lookup"><span data-stu-id="900f0-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="900f0-151">[value] suele ser una cadena (una secuencia de letras, números y otros caracteres), un valor numérico o $Null **para** unspecified.</span><span class="sxs-lookup"><span data-stu-id="900f0-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="900f0-152">Para obtener más información, vea [Where](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="900f0-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="900f0-153">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="900f0-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="900f0-154">En primer [lugar, conéctese a su Microsoft 365 inquilino](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="900f0-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="900f0-155">Ver todas las cuentas</span><span class="sxs-lookup"><span data-stu-id="900f0-155">View all accounts</span></span>

<span data-ttu-id="900f0-156">Para mostrar la lista completa de cuentas de usuario, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="900f0-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="900f0-157">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="900f0-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="900f0-158">Ejecute estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900f0-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="900f0-159">Debe obtener información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="900f0-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="900f0-160">El cmdlet **Get-MsolUser** también tiene un conjunto de parámetros para filtrar el conjunto de cuentas de usuario que se muestran.</span><span class="sxs-lookup"><span data-stu-id="900f0-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="900f0-161">Por ejemplo, para la lista de usuarios sin licencia (usuarios que se han agregado a Microsoft 365 pero aún no tienen licencia para usar ninguno de los servicios), ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="900f0-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="900f0-162">Debe obtener información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="900f0-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="900f0-163">Para obtener información sobre parámetros adicionales para filtrar el conjunto de cuentas de usuario que se muestran, vea [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="900f0-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="900f0-164">Ver una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="900f0-164">View a specific account</span></span>

<span data-ttu-id="900f0-165">Para mostrar una cuenta de usuario específica, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="900f0-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="900f0-166">Rellene el nombre de inicio de sesión de la cuenta de usuario, que también se conoce como nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="900f0-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="900f0-167">Quite los caracteres "<" y ">".</span><span class="sxs-lookup"><span data-stu-id="900f0-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="900f0-168">Ver cuentas basadas en una propiedad común</span><span class="sxs-lookup"><span data-stu-id="900f0-168">View accounts based on a common property</span></span>

<span data-ttu-id="900f0-169">Para ser más selectivo acerca de la lista de cuentas que se va a mostrar, puede usar el cmdlet **Where** en combinación con el cmdlet **Get-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="900f0-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="900f0-170">Para combinar los dos cmdlets, use el carácter "pipe" ("|"), que indica a PowerShell que tome los resultados de un comando y envíelo al comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="900f0-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="900f0-171">Este es un ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="900f0-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="900f0-172">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="900f0-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="900f0-173">Obtenga toda la información de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="900f0-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="900f0-174">Buscar todas las cuentas de usuario que tengan una ubicación de uso no especificada (**Donde {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="900f0-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="900f0-175">Dentro de las llaves, el comando indica a PowerShell que busque solo el conjunto de cuentas para las que la propiedad de cuenta de usuario UsageLocation (**$ \_ . UsageLocation**) no se especifica (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="900f0-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="900f0-176">Debe obtener información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="900f0-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="900f0-177">La *propiedad UsageLocation* es solo una de las muchas propiedades asociadas a una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="900f0-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="900f0-178">Para ver todas las propiedades de las cuentas de usuario, use el cmdlet **Select** y el carácter comodín (\*) para mostrarlas todas para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="900f0-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="900f0-179">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="900f0-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="900f0-180">Por ejemplo, *City* es el nombre de una propiedad de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="900f0-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="900f0-181">Puede usar el siguiente comando para enumerar todas las cuentas de usuario de los usuarios que viven en Londres:</span><span class="sxs-lookup"><span data-stu-id="900f0-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="900f0-182">La sintaxis del cmdlet **Where** en estos ejemplos es **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="900f0-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="900f0-183">[nombre de propiedad de cuenta de usuario] [operador de comparación] [value] **}**.</span><span class="sxs-lookup"><span data-stu-id="900f0-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="900f0-184">[operador de comparación] es **-eq** para igual, **-ne** para no es igual, **-lt** para menor que, **-gt** para mayor que y otros.</span><span class="sxs-lookup"><span data-stu-id="900f0-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="900f0-185">[value] suele ser una cadena (una secuencia de letras, números y otros caracteres), un valor numérico o $Null **para** unspecified.</span><span class="sxs-lookup"><span data-stu-id="900f0-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="900f0-186">Para obtener más información, vea [Where](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="900f0-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>
  
<span data-ttu-id="900f0-187">Para comprobar el estado bloqueado de una cuenta de usuario, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="900f0-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="900f0-188">Ver valores de propiedad adicionales para cuentas</span><span class="sxs-lookup"><span data-stu-id="900f0-188">View additional property values for accounts</span></span>

<span data-ttu-id="900f0-189">De forma predeterminada, el cmdlet **Get-MsolUser** muestra estas tres propiedades de cuentas de usuario:</span><span class="sxs-lookup"><span data-stu-id="900f0-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="900f0-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="900f0-190">UserPrincipalName</span></span>

- <span data-ttu-id="900f0-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="900f0-191">DisplayName</span></span>

- <span data-ttu-id="900f0-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="900f0-192">isLicensed</span></span>

<span data-ttu-id="900f0-193">Si necesita propiedades adicionales, como el departamento donde trabaja el usuario y el país o región donde usan servicios de Microsoft 365, puede ejecutar **Get-MsolUser** en combinación con el cmdlet **Select** para especificar la lista de propiedades de cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="900f0-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="900f0-194">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="900f0-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="900f0-195">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="900f0-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="900f0-196">Obtenga toda la información acerca de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="900f0-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="900f0-197">Mostrar solo el nombre de cuenta de usuario, el departamento y la ubicación de uso (**Seleccione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="900f0-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="900f0-198">Debe obtener información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="900f0-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="900f0-199">El cmdlet **Select** le permite elegir qué propiedades mostrar.</span><span class="sxs-lookup"><span data-stu-id="900f0-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="900f0-200">Para mostrar todas las propiedades de una cuenta de usuario específica, use el carácter comodín (\*).</span><span class="sxs-lookup"><span data-stu-id="900f0-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="900f0-201">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="900f0-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="900f0-202">Para ser más selectivo acerca de la lista de cuentas que se va a mostrar, también puede usar el cmdlet **Where.**</span><span class="sxs-lookup"><span data-stu-id="900f0-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="900f0-203">Este es un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="900f0-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="900f0-204">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="900f0-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="900f0-205">Obtenga toda la información acerca de las cuentas de usuario (**Get-MsolUser**) y envíela al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="900f0-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="900f0-206">Buscar todas las cuentas de usuario que tengan una ubicación de uso no especificada (**Donde {$ \_ . UsageLocation -eq $Null}**) y envíe la información resultante al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="900f0-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="900f0-207">Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas para las que la propiedad de cuenta de usuario UsageLocation (**$ \_ . UsageLocation**) no se especifica (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="900f0-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="900f0-208">Mostrar solo el nombre de cuenta de usuario, el departamento y la ubicación de uso (**Seleccione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="900f0-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="900f0-209">Debe obtener información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="900f0-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="900f0-210">Si usa la sincronización de directorios para crear y administrar los usuarios de Microsoft 365, puede mostrar la cuenta local desde la que se ha proyectado Microsoft 365 usuario.</span><span class="sxs-lookup"><span data-stu-id="900f0-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="900f0-211">En el ejemplo siguiente se supone que:</span><span class="sxs-lookup"><span data-stu-id="900f0-211">The following example assumes that:</span></span>

- <span data-ttu-id="900f0-212">Azure AD Conectar está configurado para usar el delimitador de origen predeterminado de ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="900f0-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="900f0-213">(Para obtener más información acerca de cómo configurar un delimitador de origen, [vea Azure AD Conectar: Conceptos de diseño](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span><span class="sxs-lookup"><span data-stu-id="900f0-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="900f0-214">Se ha instalado el módulo servicios de dominio de Active Directory para PowerShell (vea [HERRAMIENTAS RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="900f0-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="900f0-215">Vea también</span><span class="sxs-lookup"><span data-stu-id="900f0-215">See also</span></span>

[<span data-ttu-id="900f0-216">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="900f0-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="900f0-217">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="900f0-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="900f0-218">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="900f0-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)