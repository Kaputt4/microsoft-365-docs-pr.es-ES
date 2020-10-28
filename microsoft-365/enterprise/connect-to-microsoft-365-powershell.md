---
title: Conectarse a Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Conéctese a su espacio empresarial de Microsoft 365 mediante PowerShell para Microsoft 365 de forma que pueda realizar tareas desde el Centro de administración desde la línea de comandos.
ms.openlocfilehash: d8263fd14d5eae58d3686f18056945a60158b421
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754309"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="c3143-103">Conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3143-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="c3143-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c3143-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c3143-105">PowerShell para Microsoft 365 le permite administrar la configuración de Microsoft 365 desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c3143-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="c3143-106">Para conectarse a PowerShell, solo tiene que instalar el software necesario y después conectarse a su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3143-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="c3143-107">Hay dos versiones del módulo de PowerShell que puede usar para conectarse a Microsoft 365 y administrar cuentas de usuario, grupos y licencias:</span><span class="sxs-lookup"><span data-stu-id="c3143-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="c3143-108">Azure Active Directory PowerShell para Graph, cuyos cmdlets incluyen *AzureAD* en su nombre</span><span class="sxs-lookup"><span data-stu-id="c3143-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="c3143-109">Módulo Microsoft Azure Active Directory para Windows PowerShell, cuyos cmdlets incluyen *Sol* en su nombre</span><span class="sxs-lookup"><span data-stu-id="c3143-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Sol* in their name</span></span>

<span data-ttu-id="c3143-110">Actualmente, el Módulo Azure Active Directory para Graph no reemplaza completamente la funcionalidad del Módulo Microsoft Azure AD para Windows PowerShell para la administración de usuarios, grupos y licencias.</span><span class="sxs-lookup"><span data-stu-id="c3143-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="c3143-111">En algunos casos, deberá usar ambas versiones.</span><span class="sxs-lookup"><span data-stu-id="c3143-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="c3143-112">Puede instalar ambas versiones de forma segura en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="c3143-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3143-113">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="c3143-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="c3143-114">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="c3143-114">**Operating system**</span></span>

<span data-ttu-id="c3143-115">Debe usar una versión de 64 bits de Windows.</span><span class="sxs-lookup"><span data-stu-id="c3143-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="c3143-116">El soporte para la versión de 32 bits de Módulo Microsoft Azure AD para Windows PowerShell finalizó en 2014.</span><span class="sxs-lookup"><span data-stu-id="c3143-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="c3143-117">Puede usar las siguientes versiones de Windows:</span><span class="sxs-lookup"><span data-stu-id="c3143-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="c3143-118">Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="c3143-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="c3143-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="c3143-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="c3143-120">Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2 SP1, descargue e instale [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="c3143-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="c3143-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c3143-121">**PowerShell**</span></span>

- <span data-ttu-id="c3143-122">Para el Módulo Azure Active Directory PowerShell para Graph, debe usar la versión 5.1 o posterior de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3143-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="c3143-123">Para el Módulo Microsoft Azure Active Directory para Windows PowerShell, debe usar la versión 5.1 o posterior de PowerShell, hasta la versión 6.</span><span class="sxs-lookup"><span data-stu-id="c3143-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="c3143-124">No puede usar la versión 7 de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3143-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="c3143-125">Estos procedimientos están diseñados para los usuarios que sean miembros de un rol de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3143-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="c3143-126">Para obtener más información, vea [Asignar roles de administrador](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="c3143-126">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c3143-127">Conéctese al módulo de PowerShell de Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="c3143-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c3143-128">Los comandos del módulo PowerShell Azure Active Directory para Graph incluyen *AzureAD* en su nombre de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3143-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="c3143-129">Puede instalar el módulo [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) o [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="c3143-129">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="c3143-130">Para los procedimientos que necesitan los nuevos cmdlets del Módulo Azure Active Directory PowerShell para Graph, siga estos pasos para instalar el módulo y conectarse a su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3143-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="c3143-131">Para información sobre la compatibilidad con diferentes versiones de Windows, vea [Módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span><span class="sxs-lookup"><span data-stu-id="c3143-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="c3143-132">Paso 1: Instalar el software necesario</span><span class="sxs-lookup"><span data-stu-id="c3143-132">Step 1: Install the required software</span></span>

<span data-ttu-id="c3143-133">Estos pasos son necesarios solo una vez en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c3143-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="c3143-134">Pero es probable que tenga que actualizar el software periódicamente.</span><span class="sxs-lookup"><span data-stu-id="c3143-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="c3143-135">Abra una ventana de símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="c3143-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="c3143-136">Ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="c3143-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="c3143-137">Si se le pregunta si quiere instalar un módulo desde un repositorio que no es de confianza, escriba **Y** y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="c3143-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="c3143-138">Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3143-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="c3143-139">Para conectarse a Azure Active Directory (Azure AD) para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor, ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3143-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="c3143-140">(no tiene que ser con privilegios elevados).</span><span class="sxs-lookup"><span data-stu-id="c3143-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="c3143-141">Nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="c3143-141">Office 365 cloud</span></span> | <span data-ttu-id="c3143-142">Comando</span><span class="sxs-lookup"><span data-stu-id="c3143-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="c3143-143">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="c3143-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="c3143-144">Office 365 ofrecido por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="c3143-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="c3143-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c3143-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="c3143-146">Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="c3143-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="c3143-147">En el cuadro de diálogo **Inicie sesión en su cuenta** , escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y seleccione **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="c3143-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK** .</span></span>

<span data-ttu-id="c3143-148">Si está usando la autenticación multifactor, siga las instrucciones para proporcionar información de autenticación adicional, como un código de comprobación.</span><span class="sxs-lookup"><span data-stu-id="c3143-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="c3143-149">Después de conectarse, puede usar los cmdlets para el [Módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="c3143-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c3143-150">Conectar con el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3143-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="c3143-151">Los cmdlets del Módulo Microsoft Azure Active Directory para Windows PowerShell tienen *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="c3143-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="c3143-152">La versión 7 de PowerShell no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlets que llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="c3143-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c3143-153">Para la versión 7 de PowerShell y versiones posteriores, debe usar el Módulo Azure Active Directory Powershell para Graph o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3143-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="c3143-154">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="c3143-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c3143-155">Ejecute estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3143-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="c3143-156">Paso 1: Instalar el software necesario</span><span class="sxs-lookup"><span data-stu-id="c3143-156">Step 1: Install the required software</span></span>

<span data-ttu-id="c3143-157">Estos pasos son necesarios solo una vez en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c3143-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="c3143-158">Pero es probable que tenga que actualizar el software periódicamente.</span><span class="sxs-lookup"><span data-stu-id="c3143-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="c3143-159">Si no ejecuta Windows 10, instale la versión de 64 bits del asistente para inicio de sesión de Microsoft Online Services: [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="c3143-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="c3143-160">Siga estos pasos para instalar el Módulo Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3143-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="c3143-161">Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="c3143-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="c3143-162">Ejecute el comando **Install-Module MSOnline** .</span><span class="sxs-lookup"><span data-stu-id="c3143-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="c3143-163">Si se le pide que instale el proveedor de NuGet, escriba **Y** y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="c3143-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="c3143-164">Si se le pide que instale el módulo desde PSGallery, escriba **Y** y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="c3143-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="c3143-165">Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3143-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="c3143-166">Para conectarse a Azure AD para su suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor, ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3143-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="c3143-167">(no tiene que ser con privilegios elevados).</span><span class="sxs-lookup"><span data-stu-id="c3143-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="c3143-168">Nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="c3143-168">Office 365 cloud</span></span> | <span data-ttu-id="c3143-169">Comando</span><span class="sxs-lookup"><span data-stu-id="c3143-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="c3143-170">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="c3143-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="c3143-171">Office 365 ofrecido por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="c3143-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="c3143-172">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c3143-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="c3143-173">Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="c3143-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="c3143-174">En el cuadro de diálogo **Inicie sesión en su cuenta** , escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y seleccione **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="c3143-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK** .</span></span>

<span data-ttu-id="c3143-175">Si está usando la autenticación multifactor, siga las instrucciones para proporcionar información de autenticación adicional, como un código de comprobación.</span><span class="sxs-lookup"><span data-stu-id="c3143-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="c3143-176">¿Cómo sabrá que funcionó?</span><span class="sxs-lookup"><span data-stu-id="c3143-176">How do you know it worked?</span></span>

<span data-ttu-id="c3143-177">Si no recibe un mensaje de error, se ha conectado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3143-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="c3143-178">Para realizar una prueba rápida, ejecute un cmdlet de Microsoft 365, como  **Get-MsolUser** y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="c3143-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser** , and see the results.</span></span>
  
<span data-ttu-id="c3143-179">Si recibe un mensaje de error, compruebe los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="c3143-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="c3143-180">**Un problema habitual es una contraseña incorrecta** .</span><span class="sxs-lookup"><span data-stu-id="c3143-180">**A common problem is an incorrect password** .</span></span> <span data-ttu-id="c3143-181">Vuelva a ejecutar el [Paso 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) y preste atención al nombre de usuario y la contraseña que escriba.</span><span class="sxs-lookup"><span data-stu-id="c3143-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="c3143-182">**El Módulo Microsoft Azure Active Directory para Windows PowerShell necesita que Microsoft .NET Framework 3.5.* x* esté habilitado en el equipo**. Es probable que el equipo tenga instalada una versión más reciente (por ejemplo, 4 o 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="c3143-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="c3143-183">Pero la compatibilidad con versiones anteriores de .NET Framework se puede habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="c3143-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="c3143-184">Para más información, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="c3143-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="c3143-185">Para Windows Server 2012 o Windows Server 2012 R2, vea [Habilitar .NET Framework 3.5 con el Asistente para agregar roles y características](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span><span class="sxs-lookup"><span data-stu-id="c3143-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span></span>
    
  - <span data-ttu-id="c3143-186">Para Windows 7 o Windows Server 2008 R2, vea [No puede abrir el Módulo de Azure Active Directory para Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span><span class="sxs-lookup"><span data-stu-id="c3143-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span></span>

  - <span data-ttu-id="c3143-187">Para Windows 10, Windows 8.1 y Windows 8, vea [Instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="c3143-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="c3143-188">**Puede que su versión de Módulo de Microsoft Azure Active Directory para Windows PowerShell esté obsoleta.**</span><span class="sxs-lookup"><span data-stu-id="c3143-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="c3143-189">Para comprobarlo, ejecute el siguiente comando en PowerShell para Microsoft 365 o el Módulo de Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3143-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="c3143-190">Si el número de versión devuelto es menor que *1.0.8070.2* , desinstale el Módulo Microsoft Azure Active Directory para Windows PowerShell e instale de nuevo siguiendo el [Paso 1](#step-1-install-the-required-software) descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c3143-190">If the version number returned is lower than *1.0.8070.2* , uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="c3143-191">**Si recibe un mensaje de error de conexión** , consulte el [Error "Connect-MsolService: se produjo una excepción de tipo"](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="c3143-191">**If you get a connection error message** , see ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="c3143-192">**Si recibe un mensaje de error "Obtener elemento: no se encontró la ruta de acceso"** , utilice este comando:</span><span class="sxs-lookup"><span data-stu-id="c3143-192">**If you get a "Get-Item: Cannot find path" error message** , run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="c3143-193">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3143-193">See also</span></span>

- [<span data-ttu-id="c3143-194">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3143-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c3143-195">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3143-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c3143-196">Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3143-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
