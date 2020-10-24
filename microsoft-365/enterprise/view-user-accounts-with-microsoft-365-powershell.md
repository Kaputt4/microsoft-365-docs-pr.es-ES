---
title: Ver cuentas de usuario 365 de Microsoft con PowerShell
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
description: Obtenga información sobre cómo ver, enumerar o mostrar las cuentas de usuario de Microsoft 365 de diferentes formas con PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754077"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="17a35-103">Ver cuentas de usuario 365 de Microsoft con PowerShell</span><span class="sxs-lookup"><span data-stu-id="17a35-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="17a35-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="17a35-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="17a35-105">Puede usar el centro de administración de Microsoft 365 para ver las cuentas de su inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17a35-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="17a35-106">PowerShell para Microsoft 365 habilita esto, pero también proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="17a35-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="17a35-107">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="17a35-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="17a35-108">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="17a35-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="17a35-109">Ver todas las cuentas</span><span class="sxs-lookup"><span data-stu-id="17a35-109">View all accounts</span></span>

<span data-ttu-id="17a35-110">Para mostrar la lista completa de cuentas de usuario, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="17a35-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="17a35-111">Debe obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="17a35-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="17a35-112">Ver una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="17a35-112">View a specific account</span></span>

<span data-ttu-id="17a35-113">Para mostrar una cuenta de usuario específica, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="17a35-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="17a35-114">Rellene el nombre de la cuenta de inicio de sesión de la cuenta de usuario, que también se conoce como el nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="17a35-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="17a35-115">Quite los caracteres "<" y ">".</span><span class="sxs-lookup"><span data-stu-id="17a35-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="17a35-116">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a35-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="17a35-117">Ver valores de propiedades adicionales para una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="17a35-117">View additional property values for a specific account</span></span>

<span data-ttu-id="17a35-118">De forma predeterminada, el cmdlet **Get-AzureADUser** solo muestra las propiedades *objectId*, *displayName*y *UserPrincipalName* de las cuentas.</span><span class="sxs-lookup"><span data-stu-id="17a35-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="17a35-119">Para ser más selectivo sobre las propiedades que se van a mostrar, use el cmdlet **Select** junto con el cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="17a35-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="17a35-120">Para combinar los dos cmdlets, use el carácter "canalización" ("|"), que indica a Azure Active Directory PowerShell para que Graph tome los resultados de un comando y lo envíe al siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="17a35-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="17a35-121">Este es un comando de ejemplo que muestra *displayName*, *Department*y *UsageLocation* para cada cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="17a35-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="17a35-122">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="17a35-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="17a35-123">Obtener toda la información de las cuentas de usuario (**Get-AzureADUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="17a35-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="17a35-124">Mostrar solo el nombre de la cuenta de usuario, el Departamento y la ubicación de uso (**Seleccione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="17a35-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="17a35-125">Para ver todas las propiedades de una cuenta de usuario específica, use el cmdlet **Select** y el carácter comodín (\*).</span><span class="sxs-lookup"><span data-stu-id="17a35-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="17a35-126">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a35-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="17a35-127">Como otro ejemplo, ejecute el siguiente comando para comprobar el estado de habilitación de una cuenta de usuario específica:</span><span class="sxs-lookup"><span data-stu-id="17a35-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="17a35-128">Ver el estado de sincronización de cuentas</span><span class="sxs-lookup"><span data-stu-id="17a35-128">View account synchronization status</span></span>

<span data-ttu-id="17a35-129">Las cuentas de usuario tienen dos orígenes:</span><span class="sxs-lookup"><span data-stu-id="17a35-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="17a35-130">Windows Server Active Directory (AD), que son cuentas que se sincronizan desde AD local a la nube.</span><span class="sxs-lookup"><span data-stu-id="17a35-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="17a35-131">Cuentas AD de Azure Active Directory (Azure AD), que se crean directamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="17a35-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="17a35-132">El siguiente comando indica a PowerShell que debe obtener todos los usuarios que tienen el atributo *DirSyncEnabled* establecido en *true*.</span><span class="sxs-lookup"><span data-stu-id="17a35-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="17a35-133">Puede usarlo para buscar cuentas que se sincronizan desde AD local.</span><span class="sxs-lookup"><span data-stu-id="17a35-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="17a35-134">El siguiente comando indica a PowerShell que debe obtener todos los usuarios que tienen el atributo *DirSyncEnabled* establecido en *false*.</span><span class="sxs-lookup"><span data-stu-id="17a35-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="17a35-135">Puede usarlo para buscar cuentas solo de la nube.</span><span class="sxs-lookup"><span data-stu-id="17a35-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="17a35-136">Ver cuentas basadas en una propiedad común</span><span class="sxs-lookup"><span data-stu-id="17a35-136">View accounts based on a common property</span></span>

<span data-ttu-id="17a35-137">Para ser más selectivo acerca de la lista de cuentas para mostrar, puede usar el cmdlet **Where** en combinación con el cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="17a35-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="17a35-138">Para combinar los dos cmdlets, use el carácter "canalización" ("|"), que indica a Azure Active Directory PowerShell para que Graph tome los resultados de un comando y lo envíe al siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="17a35-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="17a35-139">Este es un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="17a35-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="17a35-140">Este comando le indica a Azure Active Directory PowerShell para que Graph:</span><span class="sxs-lookup"><span data-stu-id="17a35-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="17a35-141">Obtener toda la información de las cuentas de usuario (**Get-AzureADUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="17a35-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="17a35-142">Buscar todas las cuentas de usuario que tienen una ubicación de uso no especificada (**donde {$ \_ . UsageLocation-EQ $Null}**).</span><span class="sxs-lookup"><span data-stu-id="17a35-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="17a35-143">Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas para el que la propiedad de la cuenta de usuario UsageLocation (\*\* $ \_ . UsageLocation**) no está especificado (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="17a35-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="17a35-144">La propiedad **UsageLocation** es solo una de las muchas propiedades asociadas con una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="17a35-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="17a35-145">Para mostrar todas las propiedades de una cuenta de usuario específica, use el cmdlet **Select** y el carácter comodín (\*).</span><span class="sxs-lookup"><span data-stu-id="17a35-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="17a35-146">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a35-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="17a35-147">Por ejemplo, **City** es el nombre de una propiedad de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="17a35-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="17a35-148">Puede usar el siguiente comando para obtener una lista de todas las cuentas de usuarios que viven en Londres:</span><span class="sxs-lookup"><span data-stu-id="17a35-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="17a35-149">La sintaxis del cmdlet **Where** en estos ejemplos es **donde {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="17a35-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="17a35-150">[nombre de propiedad de cuenta de usuario] [operador de comparación] Value **}**. > [operador de comparación] is **-EQ** para igual a, **-ne** para no es igual a, **-lt** para menor que, **-gt** para mayor que, y otros.</span><span class="sxs-lookup"><span data-stu-id="17a35-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="17a35-151">[VALUE] suele ser una cadena (una secuencia de letras, números y otros caracteres), un valor numérico o **$null** para no especificado.</span><span class="sxs-lookup"><span data-stu-id="17a35-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="17a35-152">Para obtener más información, vea [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="17a35-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="17a35-153">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17a35-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="17a35-154">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="17a35-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="17a35-155">Ver todas las cuentas</span><span class="sxs-lookup"><span data-stu-id="17a35-155">View all accounts</span></span>

<span data-ttu-id="17a35-156">Para mostrar la lista completa de cuentas de usuario, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="17a35-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="17a35-157">PowerShell Core no es compatible con el módulo Microsoft Azure Active Directory para el módulo y los cmdlets de Windows PowerShell con *msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="17a35-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="17a35-158">Ejecute estos cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17a35-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="17a35-159">Debe obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="17a35-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="17a35-160">El cmdlet **Get-MsolUser** también tiene un conjunto de parámetros para filtrar el conjunto de cuentas de usuario que se muestran.</span><span class="sxs-lookup"><span data-stu-id="17a35-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="17a35-161">Por ejemplo, para la lista de usuarios sin licencia (usuarios que se han agregado a Microsoft 365 pero que todavía no han sido autorizados para usar ninguno de los servicios), ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="17a35-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="17a35-162">Debe obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="17a35-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="17a35-163">Para obtener información acerca de los parámetros adicionales para filtrar el conjunto de cuentas de usuario que se muestran, consulte [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="17a35-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="17a35-164">Ver una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="17a35-164">View a specific account</span></span>

<span data-ttu-id="17a35-165">Para mostrar una cuenta de usuario específica, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="17a35-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="17a35-166">Rellene el nombre de inicio de sesión de la cuenta de usuario, que también se conoce como el nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="17a35-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="17a35-167">Quite los caracteres "<" y ">".</span><span class="sxs-lookup"><span data-stu-id="17a35-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="17a35-168">Ver cuentas basadas en una propiedad común</span><span class="sxs-lookup"><span data-stu-id="17a35-168">View accounts based on a common property</span></span>

<span data-ttu-id="17a35-169">Para ser más selectivo acerca de la lista de cuentas para mostrar, puede usar el cmdlet **Where** en combinación con el cmdlet **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="17a35-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="17a35-170">Para combinar los dos cmdlets, use el carácter "canalización" ("|"), que indica a PowerShell que debe tomar los resultados de un comando y enviarlo al siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="17a35-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="17a35-171">Este es un ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="17a35-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="17a35-172">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="17a35-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="17a35-173">Obtener toda la información de las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="17a35-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="17a35-174">Buscar todas las cuentas de usuario que tienen una ubicación de uso no especificada (**donde {$ \_ . UsageLocation-EQ $Null}**).</span><span class="sxs-lookup"><span data-stu-id="17a35-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="17a35-175">Dentro de las llaves, el comando indica a PowerShell que busque solo el conjunto de cuentas para el que la propiedad de la cuenta de usuario UsageLocation (\*\* $ \_ . UsageLocation**) no está especificado (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="17a35-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="17a35-176">Debe obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="17a35-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="17a35-177">La propiedad *UsageLocation* es solo una de las muchas propiedades asociadas con una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="17a35-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="17a35-178">Para ver todas las propiedades de las cuentas de usuario, use el cmdlet **Select** y el carácter comodín (\*) para mostrarlos todos para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="17a35-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="17a35-179">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a35-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="17a35-180">Por ejemplo, *City* es el nombre de una propiedad de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="17a35-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="17a35-181">Puede usar el siguiente comando para obtener una lista de todas las cuentas de usuario de los usuarios que viven en Londres:</span><span class="sxs-lookup"><span data-stu-id="17a35-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="17a35-182">La sintaxis del cmdlet **Where** en estos ejemplos es **donde {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="17a35-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="17a35-183">[nombre de propiedad de cuenta de usuario] [operador de comparación] Value **}**.</span><span class="sxs-lookup"><span data-stu-id="17a35-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="17a35-184">[Comparison Operator] es **-EQ** para igual a, **-ne** para no es igual a, **-lt** para menor que, **-gt** para mayor que, y otros.</span><span class="sxs-lookup"><span data-stu-id="17a35-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="17a35-185">[VALUE] suele ser una cadena (una secuencia de letras, números y otros caracteres), un valor numérico o **$null** para no especificado.</span><span class="sxs-lookup"><span data-stu-id="17a35-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="17a35-186">Para obtener más información, vea [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="17a35-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="17a35-187">Para comprobar el estado de bloqueo de una cuenta de usuario, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="17a35-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="17a35-188">Ver los valores de propiedad adicionales de las cuentas</span><span class="sxs-lookup"><span data-stu-id="17a35-188">View additional property values for accounts</span></span>

<span data-ttu-id="17a35-189">De forma predeterminada, el cmdlet **Get-MsolUser** muestra estas tres propiedades de las cuentas de usuario:</span><span class="sxs-lookup"><span data-stu-id="17a35-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="17a35-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="17a35-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="17a35-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="17a35-191">DisplayName</span></span>
    
- <span data-ttu-id="17a35-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="17a35-192">isLicensed</span></span>
    
<span data-ttu-id="17a35-193">Si necesita más propiedades, como el Departamento en el que trabaja el usuario y el país o región donde usan los servicios de Microsoft 365, puede ejecutar **Get-MsolUser** en combinación con el cmdlet **Select** para especificar la lista de propiedades de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="17a35-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="17a35-194">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a35-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="17a35-195">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="17a35-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="17a35-196">Obtener toda la información sobre las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="17a35-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="17a35-197">Mostrar solo el nombre de la cuenta de usuario, el Departamento y la ubicación de uso (**Seleccione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="17a35-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="17a35-198">Debe obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="17a35-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="17a35-199">El cmdlet **Select** permite elegir las propiedades que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="17a35-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="17a35-200">Para mostrar todas las propiedades de una cuenta de usuario específica, use el carácter comodín (\*).</span><span class="sxs-lookup"><span data-stu-id="17a35-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="17a35-201">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a35-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="17a35-202">Para ser más selectivo acerca de la lista de cuentas para mostrar, también puede usar el cmdlet **Where** .</span><span class="sxs-lookup"><span data-stu-id="17a35-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="17a35-203">Este es un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="17a35-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="17a35-204">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="17a35-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="17a35-205">Obtener toda la información sobre las cuentas de usuario (**Get-MsolUser**) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="17a35-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="17a35-206">Buscar todas las cuentas de usuario que tienen una ubicación de uso no especificada (**donde {$ \_ . UsageLocation-EQ $Null}**) y envía la información resultante al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="17a35-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="17a35-207">Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas para el que la propiedad de la cuenta de usuario UsageLocation (\*\* $ \_ . UsageLocation**) no está especificado (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="17a35-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="17a35-208">Mostrar solo el nombre de la cuenta de usuario, el Departamento y la ubicación de uso (**Seleccione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="17a35-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="17a35-209">Debe obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="17a35-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="17a35-210">Si está usando la sincronización de directorios para crear y administrar los usuarios de Microsoft 365, puede mostrar la cuenta local desde la que se ha proyectado a un usuario de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17a35-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="17a35-211">En el ejemplo siguiente se supone que:</span><span class="sxs-lookup"><span data-stu-id="17a35-211">The following example assumes that:</span></span>

- <span data-ttu-id="17a35-212">Azure AD Connect está configurado para usar el delimitador de origen predeterminado de ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="17a35-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="17a35-213">(Para obtener más información acerca de la configuración de un delimitador de origen, consulte [Azure ad Connect: Design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span><span class="sxs-lookup"><span data-stu-id="17a35-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="17a35-214">Se ha instalado el módulo de servicios de dominio de Active Directory para PowerShell (consulte [herramientas de RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="17a35-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="17a35-215">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="17a35-215">See also</span></span>

[<span data-ttu-id="17a35-216">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="17a35-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="17a35-217">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="17a35-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="17a35-218">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="17a35-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
