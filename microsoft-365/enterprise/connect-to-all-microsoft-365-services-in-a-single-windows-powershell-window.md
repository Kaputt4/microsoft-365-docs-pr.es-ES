---
title: Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Resumen: Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell.'
ms.openlocfilehash: cd030018dabff628af18d173cf542a3d375b27d0
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515117"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="c3f8c-103">Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3f8c-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="c3f8c-104">Cuando usa PowerShell para administrar Microsoft 365, puede tener varias sesiones de PowerShell abiertas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="c3f8c-105">Es posible que tenga distintas ventanas de PowerShell para administrar cuentas de usuario, SharePoint Online, Exchange Online, Skype empresarial online, Microsoft Teams y el centro de cumplimiento de &amp; seguridad.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="c3f8c-106">Este escenario no es óptimo para la administración de Microsoft 365, porque no se pueden intercambiar datos entre esas ventanas para la administración entre servicios.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="c3f8c-107">Este artículo describe cómo usar una única instancia de PowerShell desde la que puede administrar cuentas de Microsoft 365, Skype empresarial online, Exchange Online, SharePoint Online, Microsoft Teams y el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="c3f8c-108">Actualmente, este artículo solo contiene los comandos para conectarse a la nube mundial (+GCC).</span><span class="sxs-lookup"><span data-stu-id="c3f8c-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="c3f8c-109">Las notas brindan vínculos a artículos sobre cómo conectarse a otras nubes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c3f8c-110">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c3f8c-110">Before you begin</span></span>

<span data-ttu-id="c3f8c-111">Antes de poder administrar todo Microsoft 365 desde una sola instancia de Windows PowerShell, tenga en cuenta los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="c3f8c-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="c3f8c-112">La cuenta profesional o educativa de Microsoft 365 que use debe ser un miembro del rol de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="c3f8c-113">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="c3f8c-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="c3f8c-114">Este es un requisito de PowerShell para Microsoft 365, pero no necesariamente para todos los demás servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="c3f8c-115">Puede usar las siguientes versiones de Windows de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="c3f8c-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="c3f8c-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3f8c-116">Windows 10</span></span>
    
  - <span data-ttu-id="c3f8c-117">Windows 8.1 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="c3f8c-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="c3f8c-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c3f8c-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="c3f8c-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c3f8c-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="c3f8c-120">Windows Server 2012 R2 o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c3f8c-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="c3f8c-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="c3f8c-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="c3f8c-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="c3f8c-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="c3f8c-123">\* Debe instalar Microsoft .NET Framework 4.5.*x* y, después, Windows Management Framework 3.0 o 4.0.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="c3f8c-124">Para obtener más información, vea [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="c3f8c-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="c3f8c-125">Debe usar una versión de 64 bits de Windows para cumplir los requisitos del módulo Skype Empresarial Online y uno de los módulos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="c3f8c-126">Debe instalar los módulos necesarios para Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype Empresarial Online y Teams:</span><span class="sxs-lookup"><span data-stu-id="c3f8c-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="c3f8c-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="c3f8c-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="c3f8c-128">Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c3f8c-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="c3f8c-129">Módulo Windows PowerShell para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c3f8c-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="c3f8c-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="c3f8c-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="c3f8c-131">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="c3f8c-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="c3f8c-132">PowerShell debe configurarse para ejecutar scripts firmados en Skype empresarial Online y en el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="c3f8c-133">Ejecutar el siguiente comando en una sesión de PowerShell con privilegios elevados (una sesión de PowerShell que se abre seleccionando **Ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="c3f8c-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="c3f8c-134">Pasos de conexión al usar solo una contraseña</span><span class="sxs-lookup"><span data-stu-id="c3f8c-134">Connection steps when using just a password</span></span>

<span data-ttu-id="c3f8c-135">Siga estos pasos para conectarse a todos los servicios en una única ventana de PowerShell cuando use solo una contraseña para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="c3f8c-136">Abra Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="c3f8c-137">Ejecute este comando y escriba las credenciales de su cuenta profesional o educativa de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="c3f8c-138">Ejecute este comando para conectarse a Azure AD usando Azure Active Directory PowerShell para el módulo de Graph.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="c3f8c-139">O si usa Microsoft Azure Active Directory para el módulo de Windows PowerShell, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="c3f8c-140">PowerShell Core no es compatible con Microsoft Azure Active Directory para el módulo de Windows PowerShell ni los cmdlet que llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c3f8c-141">Debe ejecutar estos cmdlets desde PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="c3f8c-142">Ejecute estos comandos para conectarse a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="c3f8c-143">Especifique el nombre de la organización para su dominio.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="c3f8c-144">Por ejemplo, para "litwareinc\.onmicrosoft.com", el valor del nombre de la organización es "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="c3f8c-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="c3f8c-145">Ejecute estos comandos para conectarse a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-145">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="c3f8c-146">Se mostrará una advertencia sobre cómo aumentar el valor `WSMan NetworkDelayms` la primera vez que se conecte.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-146">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="c3f8c-147">Omítalo.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-147">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="c3f8c-148">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-148">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="c3f8c-149">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-149">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

6. <span data-ttu-id="c3f8c-150">Ejecute estos comandos para conectarse a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-150">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="c3f8c-151">Para conectarse a Exchange Online para las nubes de Microsoft 365 que no sean mundiales, consulte [Conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3f8c-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="c3f8c-152">Ejecute estos comandos para conectarse al Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-152">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="c3f8c-153">Para conectarse al Centro de seguridad &amp; cumplimiento para nubes de Microsoft 365 que no sean mundiales, vea [Conectarse al Centro de seguridad y cumplimiento de PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3f8c-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="c3f8c-154">Ejecute estos comandos para conectarse a Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="c3f8c-155">Para conectarse a nubes de Microsoft Teams que no sean *mundiales*, consulte [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="c3f8c-155">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>
  



### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c3f8c-156">Azure Active Directory PowerShell para el módulo de Graph</span><span class="sxs-lookup"><span data-stu-id="c3f8c-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c3f8c-157">Estos son los comandos para todos los servicios en un único bloque al usar Azure Active Directory PowerShell para el módulo de Graph.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-157">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="c3f8c-158">Especifica el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-158">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="c3f8c-159">Microsoft Azure Active Directory para el módulo de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3f8c-159">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="c3f8c-160">Estos son los comandos para todos los servicios en un único bloque al usar el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-160">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="c3f8c-161">Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-161">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="c3f8c-162">Pasos de conexión al usar autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="c3f8c-162">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c3f8c-163">Módulo de Azure Active Directory PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="c3f8c-163">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c3f8c-164">Estos son todos los comandos en un único bloque para conectarse a varios servicios de Microsoft 365 al usar la autenticación multifactor mediante el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-164">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="c3f8c-165">Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3f8c-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="c3f8c-166">Estos son todos los comandos en un único bloque para conectarse a varios servicios de Microsoft 365 al usar la autenticación multifactor con el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3f8c-166">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="c3f8c-167">Cerrar la ventana de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3f8c-167">Close the PowerShell window</span></span>

<span data-ttu-id="c3f8c-168">Para cerrar la ventana de PowerShell, ejecute este comando para quitar las sesiones activas de Skype empresarial online, SharePoint Online y Teams:</span><span class="sxs-lookup"><span data-stu-id="c3f8c-168">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="c3f8c-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3f8c-169">See also</span></span>

- [<span data-ttu-id="c3f8c-170">Conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3f8c-170">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="c3f8c-171">Administrar SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3f8c-171">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c3f8c-172">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3f8c-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
