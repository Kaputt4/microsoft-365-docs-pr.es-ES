---
title: Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
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
ms.openlocfilehash: 08d2f4c6ce67aa9fea196d56b2eb5f36a36d7943
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430051"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="6d724-103">Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d724-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="6d724-104">Cuando usa PowerShell para administrar Microsoft 365, es posible tener varias sesiones de Windows PowerShell abiertas al mismo tiempo en diferentes ventanas de Windows PowerShell, que corresponden al manejo de cuentas de usuario, SharePoint Online, Exchange Online, Skype Empresarial Online, Microsoft Teams y el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6d724-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="6d724-105">Esto no es ideal para la administración de Microsoft 365 porque no podemos intercambiar datos entre esas ventanas para la administración entre servicios.</span><span class="sxs-lookup"><span data-stu-id="6d724-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="6d724-106">Este tema describe cómo usar una única instancia de Windows PowerShell desde la que puede administrar cuentas de Microsoft 365, Skype Empresarial Online, Exchange Online, SharePoint Online, Microsoft Teams y el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6d724-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="6d724-107">Actualmente, este artículo solo contiene los comandos para conectarse a la nube mundial (+GCC).</span><span class="sxs-lookup"><span data-stu-id="6d724-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="6d724-108">Las notas brindan vínculos a artículos que explican cómo conectarse a otras nubes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d724-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="6d724-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="6d724-109">Before you begin</span></span>

<span data-ttu-id="6d724-110">Antes de poder administrar todo Microsoft 365 desde una sola instancia de Windows PowerShell, tenga en cuenta los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="6d724-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="6d724-111">La cuenta profesional o educativa de Microsoft 365 que use para estos procedimientos tiene que ser un miembro del rol de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d724-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="6d724-112">Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="6d724-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="6d724-113">Este es un requisito de PowerShell para Microsoft 365, no necesariamente para todos los demás servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d724-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="6d724-114">Puede usar las siguientes versiones de Windows de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="6d724-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="6d724-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6d724-115">Windows 10</span></span>
    
  - <span data-ttu-id="6d724-116">Windows 8.1 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="6d724-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="6d724-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="6d724-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="6d724-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6d724-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="6d724-119">Windows Server 2012 R2 o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6d724-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="6d724-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="6d724-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="6d724-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="6d724-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="6d724-122">\* Es necesario instalar Microsoft .NET Framework 4.5.*x* y, luego, Windows Management Framework 3.0 o Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="6d724-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="6d724-123">Para más información, consulte [Instalación de .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) y [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="6d724-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="6d724-124">Debe usar una versión de 64 bits de Windows para cumplir los requisitos del módulo Skype Empresarial Online y uno de los módulos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d724-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="6d724-125">Debe instalar los módulos necesarios para Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype Empresarial Online y Teams:</span><span class="sxs-lookup"><span data-stu-id="6d724-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="6d724-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="6d724-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="6d724-127">Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6d724-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="6d724-128">Módulo Windows PowerShell para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6d724-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="6d724-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="6d724-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="6d724-130">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="6d724-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="6d724-131">Windows PowerShell necesita configurarse para ejecutar scripts firmados en Skype Empresarial Online y en el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6d724-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="6d724-132">Para ello, ejecute el siguiente comando en una sesión de Windows PowerShell con privilegios elevados (es decir, una ventana de Windows PowerShell que se abre seleccionando **Ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="6d724-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="6d724-133">Exchange Online y Centro de seguridad &amp; cumplimiento con el módulo de Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="6d724-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="6d724-134">En este artículo, se usa el módulo de Exchange Online PowerShell V2 para conectarse a Exchange Online y al Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6d724-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="6d724-135">Sin embargo, en este momento no puede conectarse al mismo tiempo a Exchange Online y al Centro de seguridad &amp; cumplimiento **en la misma ventana de PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6d724-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="6d724-136">Por lo tanto, al configurar una ventana de PowerShell para varios servicios de Microsoft 365, debe elegir una conexión o bien con Exchange Online *o* con el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6d724-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="6d724-137">Pasos de conexión al usar solo una contraseña</span><span class="sxs-lookup"><span data-stu-id="6d724-137">Connection steps when using just a password</span></span>

<span data-ttu-id="6d724-138">Estos son los pasos para conectarse a todos los servicios en una única ventana de PowerShell cuando se usa solo una contraseña para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6d724-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="6d724-139">Abra Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d724-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="6d724-140">Ejecute este comando y escriba las credenciales de su cuenta profesional o educativa de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d724-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="6d724-141">Ejecute este comando para conectarse a Azure AD con el módulo Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="6d724-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="6d724-142">Si usa el Módulo Microsoft Azure Active Directory para Windows PowerShell, también puede ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="6d724-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="6d724-143">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="6d724-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="6d724-144">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d724-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="6d724-145">Ejecute estos comandos para conectarse a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6d724-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="6d724-146">Especifique el nombre de la organización para su dominio.</span><span class="sxs-lookup"><span data-stu-id="6d724-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="6d724-147">Por ejemplo, para "litwareinc.onmicrosoft.com", el valor del nombre de la organización es "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="6d724-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="6d724-148">Ejecute estos comandos para conectarse a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="6d724-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="6d724-149">La primera vez que se conecte, verá una advertencia sobre el aumento del valor `WSMan NetworkDelayms` que debe omitir.</span><span class="sxs-lookup"><span data-stu-id="6d724-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="6d724-150">Ejecute este comando para conectarse a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6d724-150">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="6d724-151">Para conectarse a Exchange Online para las nubes de Microsoft 365 que no sean mundiales, consulte [Conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6d724-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="6d724-152">Como alternativa, puede ejecutar estos comandos para conectarse al Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6d724-152">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="6d724-153">Para conectarse al Centro de seguridad &amp; cumplimiento para nubes de Microsoft 365 que no sean mundiales, vea [Conectarse al Centro de seguridad y cumplimiento de PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="6d724-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="6d724-154">Ejecute estos comandos para conectarse a Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d724-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="6d724-155">Para conectarse a nubes de Microsoft Teams que no sean mundiales, consulte [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="6d724-155">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6d724-156">Módulo de Azure Active Directory PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="6d724-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6d724-157">Estos son los comandos para todos los servicios *excepto el Centro de seguridad &amp; cumplimiento* en un único bloque al usar el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="6d724-157">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="6d724-158">Especifique el nombre del host de su dominio y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="6d724-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="6d724-159">Estos son los comandos para todos los servicios *excepto Exchange Online* en un único bloque al usar el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="6d724-159">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="6d724-160">Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="6d724-160">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="6d724-161">Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d724-161">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="6d724-162">Estos son los comandos para todos los servicios *excepto el Centro de seguridad &amp; cumplimiento* en un único bloque al usar el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d724-162">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="6d724-163">Especifique el nombre del host de su dominio y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="6d724-163">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="6d724-164">Estos son los comandos para todos los servicios *excepto Exchange Online* en un único bloque al usar el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d724-164">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="6d724-165">Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="6d724-165">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="6d724-166">Pasos de conexión al usar autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="6d724-166">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6d724-167">Módulo de Azure Active Directory PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="6d724-167">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6d724-168">Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto el Centro de seguridad &amp; cumplimiento* con autenticación multifactor mediante el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="6d724-168">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="6d724-169">Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto Exchange Online* con autenticación multifactor mediante el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="6d724-169">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="6d724-170">Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d724-170">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="6d724-171">Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto el Centro de seguridad &amp; cumplimiento* con autenticación multifactor mediante el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d724-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="6d724-172">Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto Exchange Online* mediante autenticación multifactor con el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d724-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="6d724-173">Cerrar la ventana de PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d724-173">Close the PowerShell window</span></span>

<span data-ttu-id="6d724-174">Cuando esté listo para cerrar la ventana de Windows PowerShell, ejecute este comando para quitar las sesiones activas de Skype Empresarial Online, SharePoint Online y Teams:</span><span class="sxs-lookup"><span data-stu-id="6d724-174">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="6d724-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d724-175">See also</span></span>

- [<span data-ttu-id="6d724-176">Conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d724-176">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="6d724-177">Administrar SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d724-177">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="6d724-178">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d724-178">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
