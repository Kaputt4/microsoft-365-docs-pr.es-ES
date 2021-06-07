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
ms.openlocfilehash: 70d6aa1373daf2322319d21e385fc1498af3351e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782806"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="3f3f6-103">Conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f3f6-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="3f3f6-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3f3f6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3f3f6-105">PowerShell para Microsoft 365 le permite administrar la configuración de Microsoft 365 desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="3f3f6-106">Para conectarse a PowerShell, solo tiene que instalar el software necesario y después conectarse a su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="3f3f6-107">Hay dos versiones del módulo de PowerShell que puede usar para conectarse a Microsoft 365 y administrar cuentas de usuario, grupos y licencias:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="3f3f6-108">Azure Active Directory PowerShell para Graph, cuyos cmdlets incluyen *AzureAD* en su nombre</span><span class="sxs-lookup"><span data-stu-id="3f3f6-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="3f3f6-109">Módulo Microsoft Azure Active Directory para Windows PowerShell, cuyos cmdlets incluyen *Msol* en su nombre</span><span class="sxs-lookup"><span data-stu-id="3f3f6-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="3f3f6-110">Actualmente, el Módulo Azure Active Directory PowerShell para Graph no reemplaza completamente la funcionalidad del Módulo Microsoft Azure AD para Windows PowerShell para la administración de usuarios, grupos y licencias.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="3f3f6-111">En algunos casos, deberá usar ambas versiones.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="3f3f6-112">Puede instalar ambas versiones de forma segura en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3f3f6-113">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="3f3f6-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="3f3f6-114">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="3f3f6-114">**Operating system**</span></span>

<span data-ttu-id="3f3f6-p103">Use una versión de 64 bits de Windows. La compatibilidad con la versión de 32 bits de Módulo Microsoft Azure Active Directory para Windows PowerShell se descontinuó en 2014.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="3f3f6-117">Puede usar las siguientes versiones de Windows:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="3f3f6-118">Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="3f3f6-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="3f3f6-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="3f3f6-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="3f3f6-120">Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2 SP1, descargue e instale [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="3f3f6-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3f3f6-121">**PowerShell**</span></span>

- <span data-ttu-id="3f3f6-122">Para el Módulo Azure Active Directory PowerShell para Graph, debe usar la versión 5.1 o posterior de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="3f3f6-p104">Para el Módulo Microsoft Azure Active Directory para Windows PowerShell, debe usar la versión 5.1 o posterior de PowerShell, hasta la versión 6 de PowerShell. No puede usar la versión 7 de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="3f3f6-125">Estos procedimientos están diseñados para los usuarios que sean miembros de un rol de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="3f3f6-126">Para obtener más información, vea [Asignar roles de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-126">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3f3f6-127">Conéctese al módulo de PowerShell de Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="3f3f6-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3f3f6-128">Los comandos del módulo PowerShell Azure Active Directory para Graph incluyen *AzureAD* en su nombre de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="3f3f6-129">Puede instalar el módulo [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2) o [Azure PowerShell](/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-129">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="3f3f6-130">Para los procedimientos que necesitan los nuevos cmdlets del Módulo Azure Active Directory PowerShell para Graph, siga estos pasos para instalar el módulo y conectarse a su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="3f3f6-131">Para información sobre la compatibilidad con diferentes versiones de Windows, vea [Módulo Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2) .</span><span class="sxs-lookup"><span data-stu-id="3f3f6-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="3f3f6-132">Paso 1: Instalar el software necesario</span><span class="sxs-lookup"><span data-stu-id="3f3f6-132">Step 1: Install the required software</span></span>

<span data-ttu-id="3f3f6-133">Estos pasos son necesarios solo una vez en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="3f3f6-134">Pero es probable que tenga que actualizar el software periódicamente.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="3f3f6-135">Abra una ventana de símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="3f3f6-136">Ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="3f3f6-137">De forma predeterminada, la Galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-137">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="3f3f6-138">La primera vez que use PSGallery, verá el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-138">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="3f3f6-139">Responda **Sí** o **Sí a todo** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-139">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="3f3f6-140">Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f3f6-140">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="3f3f6-p109">Para conectarse a Azure AD para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor (MFA), ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell (no tiene que ser elevado).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="3f3f6-143">Nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="3f3f6-143">Office 365 cloud</span></span> | <span data-ttu-id="3f3f6-144">Comando</span><span class="sxs-lookup"><span data-stu-id="3f3f6-144">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="3f3f6-145">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="3f3f6-145">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="3f3f6-146">Office 365 ofrecido por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="3f3f6-146">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="3f3f6-147">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="3f3f6-147">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="3f3f6-148">Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="3f3f6-148">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="3f3f6-149">En el cuadro de diálogo **Inicie sesión en su cuenta**, escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-149">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="3f3f6-150">Si está usando la autenticación multifactor, siga las instrucciones para proporcionar información de autenticación adicional, como un código de comprobación.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-150">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="3f3f6-151">Después de conectarse, puede usar los cmdlets para el [Módulo Azure Active Directory PowerShell para Graph](/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-151">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3f3f6-152">Conectar con el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f3f6-152">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="3f3f6-153">Los cmdlets del Módulo Microsoft Azure Active Directory para Windows PowerShell tienen *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-153">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="3f3f6-154">La versión 7 de PowerShell no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlets que llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-154">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="3f3f6-155">Para la versión 7 de PowerShell y versiones posteriores, debe usar el Módulo Azure Active Directory Powershell para Graph o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-155">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="3f3f6-156">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet sque llevan *Msol* en su nombre.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-156">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="3f3f6-157">Ejecute estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-157">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="3f3f6-158">Paso 1: Instalar el software necesario</span><span class="sxs-lookup"><span data-stu-id="3f3f6-158">Step 1: Install the required software</span></span>

<span data-ttu-id="3f3f6-159">Estos pasos son necesarios solo una vez en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-159">These steps are required only one time on your computer.</span></span> <span data-ttu-id="3f3f6-160">Pero es probable que tenga que actualizar el software periódicamente.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-160">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="3f3f6-161">Si no ejecuta Windows 10, instale la versión de 64 bits del asistente para inicio de sesión de Microsoft Online Services: [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-161">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="3f3f6-162">Siga estos pasos para instalar el Módulo Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-162">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="3f3f6-163">Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-163">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="3f3f6-164">Ejecute el comando **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-164">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="3f3f6-165">Si se le pide que instale el proveedor de NuGet, escriba **Y** y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-165">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="3f3f6-166">Si se le pide que instale el módulo desde PSGallery, escriba **Y** y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-166">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="3f3f6-167">Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f3f6-167">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="3f3f6-p113">Para conectarse a Azure AD para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor, ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell (no tiene que ser elevado).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="3f3f6-170">Nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="3f3f6-170">Office 365 cloud</span></span> | <span data-ttu-id="3f3f6-171">Comando</span><span class="sxs-lookup"><span data-stu-id="3f3f6-171">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="3f3f6-172">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="3f3f6-172">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="3f3f6-173">Office 365 ofrecido por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="3f3f6-173">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="3f3f6-174">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="3f3f6-174">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="3f3f6-175">Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="3f3f6-175">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="3f3f6-176">En el cuadro de diálogo **Inicie sesión en su cuenta**, escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-176">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="3f3f6-177">Si está usando la autenticación multifactor, siga las instrucciones para proporcionar información de autenticación adicional, como un código de comprobación.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-177">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="3f3f6-178">¿Cómo sabrá que funcionó?</span><span class="sxs-lookup"><span data-stu-id="3f3f6-178">How do you know it worked?</span></span>

<span data-ttu-id="3f3f6-179">Si no recibe un mensaje de error, se ha conectado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-179">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="3f3f6-180">Para realizar una prueba rápida, ejecute un cmdlet de Microsoft 365, como  **Get-MsolUser** y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-180">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="3f3f6-181">Si recibe un mensaje de error, compruebe los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-181">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="3f3f6-182">**Un problema habitual es una contraseña incorrecta**.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-182">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="3f3f6-183">Vuelva a ejecutar el [Paso 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) y preste atención al nombre de usuario y la contraseña que escriba.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-183">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="3f3f6-184">**El Módulo Microsoft Azure Active Directory para Windows PowerShell necesita que Microsoft .NET Framework 3.5.* x* esté habilitado en el equipo**. Es probable que el equipo tenga instalada una versión más reciente (por ejemplo, 4 o 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-184">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="3f3f6-185">Pero la compatibilidad con versiones anteriores de .NET Framework se puede habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-185">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="3f3f6-186">Para más información, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-186">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="3f3f6-187">Para Windows Server 2012 o Windows Server 2012 R2, vea [Habilitar .NET Framework 3.5 con el Asistente para agregar roles y características](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-187">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="3f3f6-188">Para Windows 7 o Windows Server 2008 R2, vea [No puede abrir el Módulo de Azure Active Directory para Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-188">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="3f3f6-189">Para Windows 10, Windows 8.1 y Windows 8, vea [Instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="3f3f6-189">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="3f3f6-190">**Puede que su versión de Módulo de Microsoft Azure Active Directory para Windows PowerShell esté obsoleta.**</span><span class="sxs-lookup"><span data-stu-id="3f3f6-190">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="3f3f6-191">Para comprobarlo, ejecute el siguiente comando en PowerShell para Microsoft 365 o el Módulo de Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-191">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="3f3f6-192">Si el número de versión devuelto es menor que *1.0.8070.2*, desinstale el Módulo Microsoft Azure Active Directory para Windows PowerShell e instale de nuevo siguiendo el [Paso 1](#step-1-install-the-required-software) descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3f3f6-192">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="3f3f6-193">**Si recibe un mensaje de error de conexión**, consulte el [Error "Connect-MsolService: se produjo una excepción de tipo"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="3f3f6-193">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="3f3f6-194">**Si recibe un mensaje de error "Obtener elemento: no se encontró la ruta de acceso"**, utilice este comando:</span><span class="sxs-lookup"><span data-stu-id="3f3f6-194">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="3f3f6-195">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f3f6-195">See also</span></span>

- [<span data-ttu-id="3f3f6-196">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f3f6-196">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3f3f6-197">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f3f6-197">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3f3f6-198">Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f3f6-198">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
