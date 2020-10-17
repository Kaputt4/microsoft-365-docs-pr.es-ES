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
ms.openlocfilehash: 36b16b491aa97e7329e440e2c1fb01b8a221a2b6
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477058"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="8119a-103">Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8119a-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="8119a-104">Cuando usa PowerShell para administrar Microsoft 365, es posible tener varias sesiones de Windows PowerShell abiertas al mismo tiempo en diferentes ventanas de Windows PowerShell, que corresponden al manejo de cuentas de usuario, SharePoint Online, Exchange Online, Skype Empresarial Online, Microsoft Teams y el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8119a-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="8119a-105">Esto no es ideal para la administración de Microsoft 365 porque no podemos intercambiar datos entre esas ventanas para la administración entre servicios.</span><span class="sxs-lookup"><span data-stu-id="8119a-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="8119a-106">Este tema describe cómo usar una única instancia de Windows PowerShell desde la que puede administrar cuentas de Microsoft 365, Skype Empresarial Online, Exchange Online, SharePoint Online, Microsoft Teams y el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8119a-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="8119a-107">Actualmente, este artículo solo contiene los comandos para conectarse a la nube mundial (+GCC).</span><span class="sxs-lookup"><span data-stu-id="8119a-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="8119a-108">Las notas brindan vínculos a artículos que explican cómo conectarse a otras nubes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8119a-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="8119a-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8119a-109">Before you begin</span></span>

<span data-ttu-id="8119a-110">Antes de poder administrar todo Microsoft 365 desde una sola instancia de Windows PowerShell, tenga en cuenta los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8119a-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="8119a-111">La cuenta profesional o educativa de Microsoft 365 que use para estos procedimientos tiene que ser un miembro del rol de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8119a-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="8119a-112">Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="8119a-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="8119a-113">Este es un requisito de PowerShell para Microsoft 365, no necesariamente para todos los demás servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8119a-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="8119a-114">Puede usar las siguientes versiones de Windows de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="8119a-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="8119a-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8119a-115">Windows 10</span></span>
    
  - <span data-ttu-id="8119a-116">Windows 8.1 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="8119a-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="8119a-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8119a-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="8119a-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8119a-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="8119a-119">Windows Server 2012 R2 o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8119a-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="8119a-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="8119a-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="8119a-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="8119a-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="8119a-122">\* Es necesario instalar Microsoft .NET Framework 4.5.*x* y, luego, Windows Management Framework 3.0 o Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="8119a-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="8119a-123">Para más información, consulte [Instalación de .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) y [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="8119a-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="8119a-124">Debe usar una versión de 64 bits de Windows para cumplir los requisitos del módulo Skype Empresarial Online y uno de los módulos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8119a-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="8119a-125">Debe instalar los módulos necesarios para Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype Empresarial Online y Teams:</span><span class="sxs-lookup"><span data-stu-id="8119a-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="8119a-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="8119a-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="8119a-127">Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8119a-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="8119a-128">Módulo Windows PowerShell para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8119a-128">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="8119a-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="8119a-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="8119a-130">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="8119a-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="8119a-131">Windows PowerShell necesita configurarse para ejecutar scripts firmados en Skype Empresarial Online y en el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8119a-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="8119a-132">Para ello, ejecute el siguiente comando en una sesión de Windows PowerShell con privilegios elevados (es decir, una ventana de Windows PowerShell que se abre seleccionando **Ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="8119a-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="8119a-133">Exchange Online y Centro de seguridad &amp; cumplimiento con el módulo de Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="8119a-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="8119a-134">En este artículo, se usa el módulo de Exchange Online PowerShell V2 para conectarse a Exchange Online y al Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8119a-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="8119a-135">Sin embargo, en este momento no puede conectarse al mismo tiempo a Exchange Online y al Centro de seguridad &amp; cumplimiento **en la misma ventana de PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8119a-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="8119a-136">Por lo tanto, al configurar una ventana de PowerShell para varios servicios de Microsoft 365, debe elegir una conexión o bien con Exchange Online *o* con el Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8119a-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="8119a-137">Pasos de conexión al usar solo una contraseña</span><span class="sxs-lookup"><span data-stu-id="8119a-137">Connection steps when using just a password</span></span>

<span data-ttu-id="8119a-138">Estos son los pasos para conectarse a todos los servicios en una única ventana de PowerShell cuando se usa solo una contraseña para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="8119a-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="8119a-139">Abra Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8119a-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="8119a-140">Ejecute este comando y escriba las credenciales de su cuenta profesional o educativa de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8119a-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="8119a-141">Ejecute este comando para conectarse a Azure AD con el módulo Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="8119a-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="8119a-142">Si usa el Módulo Microsoft Azure Active Directory para Windows PowerShell, también puede ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="8119a-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="8119a-143">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="8119a-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="8119a-144">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8119a-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="8119a-145">Ejecute estos comandos para conectarse a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8119a-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="8119a-146">Especifique el nombre de la organización para su dominio.</span><span class="sxs-lookup"><span data-stu-id="8119a-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="8119a-147">Por ejemplo, para "litwareinc.onmicrosoft.com", el valor del nombre de la organización es "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="8119a-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="8119a-148">Ejecute estos comandos para conectarse a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="8119a-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="8119a-149">La primera vez que se conecte, verá una advertencia sobre el aumento del valor `WSMan NetworkDelayms` que debe omitir.</span><span class="sxs-lookup"><span data-stu-id="8119a-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   > [!Note]
   > <span data-ttu-id="8119a-150">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="8119a-150">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="8119a-151">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8119a-151">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector..</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="8119a-152">Ejecute este comando para conectarse a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8119a-152">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="8119a-153">Para conectarse a Exchange Online para las nubes de Microsoft 365 que no sean mundiales, consulte [Conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8119a-153">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="8119a-154">Como alternativa, puede ejecutar estos comandos para conectarse al Centro de seguridad &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8119a-154">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="8119a-155">Para conectarse al Centro de seguridad &amp; cumplimiento para nubes de Microsoft 365 que no sean mundiales, vea [Conectarse al Centro de seguridad y cumplimiento de PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="8119a-155">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="8119a-156">Ejecute estos comandos para conectarse a Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8119a-156">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="8119a-157">Para conectarse a nubes de Microsoft Teams que no sean mundiales, consulte [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="8119a-157">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="8119a-158">Módulo de Azure Active Directory PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="8119a-158">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="8119a-159">Estos son los comandos para todos los servicios *excepto el Centro de seguridad &amp; cumplimiento* en un único bloque al usar el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="8119a-159">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="8119a-160">Especifique el nombre del host de su dominio y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="8119a-160">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="8119a-161">Estos son los comandos para todos los servicios *excepto Exchange Online* en un único bloque al usar el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="8119a-161">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="8119a-162">Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="8119a-162">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="8119a-163">Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8119a-163">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="8119a-164">Estos son los comandos para todos los servicios *excepto el Centro de seguridad &amp; cumplimiento* en un único bloque al usar el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8119a-164">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="8119a-165">Especifique el nombre del host de su dominio y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="8119a-165">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="8119a-166">Estos son los comandos para todos los servicios *excepto Exchange Online* en un único bloque al usar el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8119a-166">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="8119a-167">Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="8119a-167">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="8119a-168">Pasos de conexión al usar autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="8119a-168">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="8119a-169">Módulo de Azure Active Directory PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="8119a-169">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="8119a-170">Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto el Centro de seguridad &amp; cumplimiento* con autenticación multifactor mediante el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="8119a-170">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="8119a-171">Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto Exchange Online* con autenticación multifactor mediante el módulo de Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="8119a-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="8119a-172">Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8119a-172">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="8119a-173">Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto el Centro de seguridad &amp; cumplimiento* con autenticación multifactor mediante el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8119a-173">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="8119a-174">Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto Exchange Online* mediante autenticación multifactor con el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8119a-174">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="8119a-175">Cerrar la ventana de PowerShell</span><span class="sxs-lookup"><span data-stu-id="8119a-175">Close the PowerShell window</span></span>

<span data-ttu-id="8119a-176">Cuando esté listo para cerrar la ventana de Windows PowerShell, ejecute este comando para quitar las sesiones activas de Skype Empresarial Online, SharePoint Online y Teams:</span><span class="sxs-lookup"><span data-stu-id="8119a-176">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="8119a-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8119a-177">See also</span></span>

- [<span data-ttu-id="8119a-178">Conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8119a-178">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="8119a-179">Administrar SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8119a-179">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8119a-180">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8119a-180">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
