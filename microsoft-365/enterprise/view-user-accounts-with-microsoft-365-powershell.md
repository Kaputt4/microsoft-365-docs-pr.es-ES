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
ms.openlocfilehash: 4dba05ce440ec0d395fda58a12df3e9f751bb469
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357903"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="0da3c-103">Ver cuentas de usuario 365 de Microsoft con PowerShell</span><span class="sxs-lookup"><span data-stu-id="0da3c-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="0da3c-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0da3c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0da3c-105">Aunque puede usar el centro de administración de Microsoft 365 para ver las cuentas de su inquilino de Microsoft 365, también puede usar PowerShell para Microsoft 365 y hacer algunas cosas que el centro de administración no puede.</span><span class="sxs-lookup"><span data-stu-id="0da3c-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="0da3c-106">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="0da3c-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="0da3c-107">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="0da3c-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="0da3c-108">Ver todas las cuentas</span><span class="sxs-lookup"><span data-stu-id="0da3c-108">View all accounts</span></span>

<span data-ttu-id="0da3c-109">Para mostrar la lista completa de cuentas de usuario, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="0da3c-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="0da3c-110">Verá información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="0da3c-110">You should see information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="0da3c-111">Ver una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="0da3c-111">View a specific account</span></span>

<span data-ttu-id="0da3c-112">Para mostrar una cuenta de usuario específica, rellene el nombre de la cuenta de inicio de sesión de la cuenta de usuario, también conocido como nombre principal de usuario (UPN), quite los caracteres "<" y ">" y ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="0da3c-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="0da3c-113">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0da3c-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="0da3c-114">Ver valores de propiedades adicionales para una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="0da3c-114">View additional property values for a specific account</span></span>

<span data-ttu-id="0da3c-115">De forma predeterminada, el cmdlet **Get-AzureADUser** solo muestra las propiedades objectId, DisplayName y UserPrincipalName de las cuentas.</span><span class="sxs-lookup"><span data-stu-id="0da3c-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="0da3c-116">Para ser más selectivo acerca de la lista de propiedades que se mostrarán, puede usar el cmdlet **Select** junto con el cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="0da3c-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="0da3c-117">Para combinar los dos cmdlets, usamos el carácter "canalización" "|", que indica a Azure Active Directory PowerShell para que Graph tome los resultados de un comando y lo envíe al siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="0da3c-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="0da3c-118">Este es un comando de ejemplo que muestra DisplayName, Department y UsageLocation para cada cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="0da3c-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="0da3c-119">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="0da3c-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="0da3c-120">Obtener toda la información de las cuentas de usuario ( **Get-AzureADUser** ) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="0da3c-121">Mostrar solo el nombre de la cuenta de usuario, el Departamento y la ubicación de uso ( **Seleccione DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="0da3c-122">Para ver todas las propiedades de las cuentas de usuario, use el cmdlet **Select** y el carácter comodín (\*) para mostrarlos todos para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="0da3c-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="0da3c-123">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0da3c-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="0da3c-124">Como otro ejemplo, puede comprobar el estado habilitado de una cuenta de usuario específica con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0da3c-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="0da3c-125">Ver el estado de sincronización de cuentas</span><span class="sxs-lookup"><span data-stu-id="0da3c-125">View account synchronization status</span></span>

<span data-ttu-id="0da3c-126">Las cuentas de usuario tienen dos orígenes; Windows Server Active Directory (AD), que son cuentas que se sincronizan desde un AD local a la nube y Azure AD, que son cuentas creadas directamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="0da3c-126">User accounts have two sources; Windows Server Active Directory (AD) which are accounts that sync from on-premises AD to the cloud and Azure AD which are accounts directly created in the cloud.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```
<span data-ttu-id="0da3c-127">Este comando indica a PowerShell que debe obtener todos los usuarios que tienen el atributo **DirSyncEnabled** establecido en true.</span><span class="sxs-lookup"><span data-stu-id="0da3c-127">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to True.</span></span> <span data-ttu-id="0da3c-128">Se puede usar para extraer cuentas que se sincronizan desde un anuncio local.</span><span class="sxs-lookup"><span data-stu-id="0da3c-128">It can be used to pull up accounts synchronizing from on-premise AD.</span></span>


```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```
<span data-ttu-id="0da3c-129">Este comando indica a PowerShell que debe obtener todos los usuarios que tienen el atributo **DirSyncEnabled** establecido en false.</span><span class="sxs-lookup"><span data-stu-id="0da3c-129">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to False.</span></span> <span data-ttu-id="0da3c-130">Puede usarse para extraer cuentas solo en la nube.</span><span class="sxs-lookup"><span data-stu-id="0da3c-130">It can be used to pull up cloud-only accounts.</span></span>

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="0da3c-131">Ver algunas cuentas basadas en una propiedad común</span><span class="sxs-lookup"><span data-stu-id="0da3c-131">View some accounts based on a common property</span></span>

<span data-ttu-id="0da3c-132">Para ser más selectivo acerca de la lista de cuentas para mostrar, puede usar el cmdlet **Where** en combinación con el cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="0da3c-132">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="0da3c-133">Para combinar los dos cmdlets, usamos el carácter "canalización" "|", que indica a Azure Active Directory PowerShell para que Graph tome los resultados de un comando y lo envíe al siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="0da3c-133">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="0da3c-134">A continuación se incluye un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="0da3c-134">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="0da3c-135">Este comando le indica a Azure Active Directory PowerShell para que Graph:</span><span class="sxs-lookup"><span data-stu-id="0da3c-135">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="0da3c-136">Obtener toda la información de las cuentas de usuario ( **Get-AzureADUser** ) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-136">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="0da3c-137">Buscar todas las cuentas de usuario que tienen una ubicación de uso no especificada ( **donde {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-137">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="0da3c-138">Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas en el que la propiedad de la cuenta de usuario UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) no está especificado ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-138">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="0da3c-139">La propiedad **UsageLocation** es solo una de las muchas propiedades asociadas con una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0da3c-139">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="0da3c-140">Para ver todas las propiedades de las cuentas de usuario, use el cmdlet **Select** y el carácter comodín (\*) para mostrarlos todos para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="0da3c-140">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="0da3c-141">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0da3c-141">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="0da3c-p108">Por ejemplo, en esta lista, **City** es el nombre de una propiedad de la cuenta de usuario. Esto significa que puede usar el comando siguiente para enumerar todas las cuentas de los usuarios que viven en Londres:</span><span class="sxs-lookup"><span data-stu-id="0da3c-p108">For example, from this list, **City** is the name of a user account property. This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="0da3c-144">La sintaxis del cmdlet **Where** que se muestra en estos ejemplos es **donde {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="0da3c-144">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="0da3c-145">[nombre de propiedad de cuenta de usuario] [operador de comparación] Value **}**. > [operador de comparación] is **-EQ** para igual a, **-ne** para no es igual a, **-lt** para menor que, **-gt** para mayor que, y otros.</span><span class="sxs-lookup"><span data-stu-id="0da3c-145">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="0da3c-146">[VALUE] suele ser una cadena (una secuencia de letras, números y otros caracteres), un valor numérico o **$null** para> sin especificar vea [dónde](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0da3c-146">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="0da3c-147">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0da3c-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="0da3c-148">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0da3c-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="0da3c-149">Ver todas las cuentas</span><span class="sxs-lookup"><span data-stu-id="0da3c-149">View all accounts</span></span>

<span data-ttu-id="0da3c-150">Para mostrar la lista completa de cuentas de usuario, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="0da3c-150">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="0da3c-151">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="0da3c-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="0da3c-152">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0da3c-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="0da3c-153">Verá información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="0da3c-153">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="0da3c-154">El cmdlet **Get-MsolUser** también tiene un conjunto de parámetros para filtrar el conjunto de cuentas de usuario que se muestran.</span><span class="sxs-lookup"><span data-stu-id="0da3c-154">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="0da3c-155">Por ejemplo, para la lista de usuarios sin licencia (usuarios que se han agregado a Microsoft 365 pero que todavía no han sido autorizados para usar ninguno de los servicios), ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="0da3c-155">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="0da3c-156">Verá información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="0da3c-156">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="0da3c-157">Para obtener más información acerca de los parámetros adicionales para filtrar la visualización del conjunto de cuentas de usuario que se muestra, consulte [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="0da3c-157">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="0da3c-158">Ver una cuenta específica</span><span class="sxs-lookup"><span data-stu-id="0da3c-158">View a specific account</span></span>

<span data-ttu-id="0da3c-159">Para mostrar una cuenta de usuario específica, escriba el nombre de inicio de sesión de la cuenta de usuario de la cuenta de usuario, también conocido como nombre principal de usuario (UPN), quite los caracteres "<" y ">" y ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="0da3c-159">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="0da3c-160">Ver algunas cuentas basadas en una propiedad común</span><span class="sxs-lookup"><span data-stu-id="0da3c-160">View some accounts based on a common property</span></span>

<span data-ttu-id="0da3c-161">Para ser más selectivo acerca de la lista de cuentas para mostrar, puede usar el cmdlet **Where** en combinación con el cmdlet **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="0da3c-161">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="0da3c-162">Para combinar los dos cmdlets, usamos el carácter "canal" "|", que indica a PowerShell que debe tomar los resultados de un comando y enviarlo al comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="0da3c-162">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="0da3c-163">A continuación se incluye un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="0da3c-163">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="0da3c-164">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="0da3c-164">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="0da3c-165">Obtener toda la información de las cuentas de usuario ( **Get-MsolUser** ) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-165">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="0da3c-166">Buscar todas las cuentas de usuario que tienen una ubicación de uso no especificada ( **donde {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-166">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="0da3c-167">Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas en el que la propiedad de la cuenta de usuario UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) no está especificado ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-167">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="0da3c-168">Verá información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="0da3c-168">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="0da3c-169">La propiedad **UsageLocation** es solo una de las muchas propiedades asociadas con una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0da3c-169">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="0da3c-170">Para ver todas las propiedades de las cuentas de usuario, use el cmdlet **Select** y el carácter comodín (\*) para mostrarlos todos para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="0da3c-170">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="0da3c-171">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0da3c-171">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="0da3c-p115">Por ejemplo, en esta lista, **City** es el nombre de una propiedad de la cuenta de usuario. Esto significa que puede usar el comando siguiente para enumerar todas las cuentas de los usuarios que viven en Londres:</span><span class="sxs-lookup"><span data-stu-id="0da3c-p115">For example, from this list, **City** is the name of a user account property. This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="0da3c-174">La sintaxis del cmdlet **Where** que se muestra en estos ejemplos es **donde {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="0da3c-174">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="0da3c-175">[nombre de propiedad de cuenta de usuario] [operador de comparación] Value **}**.</span><span class="sxs-lookup"><span data-stu-id="0da3c-175">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="0da3c-176">[Comparison Operator] es **-EQ** para igual a, **-ne** para no es igual a, **-lt** para menor que, **-gt** para mayor que, y otros.</span><span class="sxs-lookup"><span data-stu-id="0da3c-176">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="0da3c-177">[VALUE] suele ser una cadena (una secuencia de letras, números y otros caracteres), un valor numérico o **$null** para no especificado.</span><span class="sxs-lookup"><span data-stu-id="0da3c-177">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="0da3c-178">Vea [dónde](https://technet.microsoft.com/library/hh849715.aspx) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0da3c-178">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="0da3c-179">Puede comprobar el estado de bloqueo de una cuenta de usuario con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0da3c-179">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="0da3c-180">Ver los valores de propiedad adicionales de las cuentas</span><span class="sxs-lookup"><span data-stu-id="0da3c-180">View additional property values for accounts</span></span>

<span data-ttu-id="0da3c-181">De forma predeterminada, el cmdlet **Get-MsolUser** muestra tres propiedades de las cuentas de usuario:</span><span class="sxs-lookup"><span data-stu-id="0da3c-181">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="0da3c-182">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="0da3c-182">UserPrincipalName</span></span>
    
- <span data-ttu-id="0da3c-183">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0da3c-183">DisplayName</span></span>
    
- <span data-ttu-id="0da3c-184">isLicensed</span><span class="sxs-lookup"><span data-stu-id="0da3c-184">isLicensed</span></span>
    
<span data-ttu-id="0da3c-185">Si necesita más propiedades, como el Departamento en el que trabaja el usuario y el país o la región donde el usuario usa los servicios de Microsoft 365, puede ejecutar **Get-MsolUser** en combinación con el cmdlet **Select** para especificar la lista de propiedades de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0da3c-185">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="0da3c-186">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0da3c-186">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="0da3c-187">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="0da3c-187">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="0da3c-188">Obtener toda la información de las cuentas de usuario ( **Get-MsolUser** ) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-188">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="0da3c-189">Mostrar solo el nombre de la cuenta de usuario, el Departamento y la ubicación de uso ( **Seleccione DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-189">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="0da3c-190">Verá información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="0da3c-190">You should see information similar to this:</span></span>
  
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

<span data-ttu-id="0da3c-191">El cmdlet **Select** permite seleccionar y elegir las propiedades que desea que muestre un comando.</span><span class="sxs-lookup"><span data-stu-id="0da3c-191">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="0da3c-192">Para ver todas las propiedades de las cuentas de usuario, use el carácter comodín (\*) para mostrarlas todas para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="0da3c-192">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="0da3c-193">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0da3c-193">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="0da3c-194">Para ser más selectivo acerca de la lista de cuentas para mostrar, también puede usar el cmdlet **Where** .</span><span class="sxs-lookup"><span data-stu-id="0da3c-194">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="0da3c-195">A continuación se incluye un comando de ejemplo que muestra solo las cuentas de usuario que tienen una ubicación de uso no especificada:</span><span class="sxs-lookup"><span data-stu-id="0da3c-195">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="0da3c-196">Este comando indica a PowerShell que:</span><span class="sxs-lookup"><span data-stu-id="0da3c-196">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="0da3c-197">Obtener toda la información de las cuentas de usuario ( **Get-MsolUser** ) y enviarla al comando siguiente ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-197">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="0da3c-198">Buscar todas las cuentas de usuario que tienen una ubicación de uso no especificada ( **donde {$ \_ . UsageLocation-EQ $Null}** ) y envía la información resultante al siguiente comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-198">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="0da3c-199">Dentro de las llaves, el comando indica a PowerShell que solo busque el conjunto de cuentas en el que la propiedad de la cuenta de usuario UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) no está especificado ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-199">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="0da3c-200">Mostrar solo el nombre de la cuenta de usuario, el Departamento y la ubicación de uso ( **Seleccione DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="0da3c-200">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="0da3c-201">Verá información similar a esta:</span><span class="sxs-lookup"><span data-stu-id="0da3c-201">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="0da3c-202">Si usa la sincronización de directorios para crear y administrar los usuarios de Microsoft 365, puede mostrar la cuenta local de la que se ha proyectado un usuario de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0da3c-202">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="0da3c-203">El siguiente ejemplo presupone que Azure AD Connect se ha configurado para usar el delimitador de origen predeterminado de ObjectGUID (para obtener más información sobre la configuración de un delimitador de origen, consulte [Azure ad Connect: Design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) y se supone que se ha instalado el módulo de servicios de dominio de Active Directory para PowerShell (consulte [las herramientas de RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span><span class="sxs-lookup"><span data-stu-id="0da3c-203">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="0da3c-204">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0da3c-204">See also</span></span>

[<span data-ttu-id="0da3c-205">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="0da3c-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0da3c-206">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="0da3c-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0da3c-207">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0da3c-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
