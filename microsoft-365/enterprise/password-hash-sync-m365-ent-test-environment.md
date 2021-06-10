---
title: Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Resumen: configure y muestre la sincronización de hash de contraseñas e inicie sesión en su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921509"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="d3bea-103">Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d3bea-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="d3bea-104">*Esta Guía del laboratorio de pruebas se puede usar tanto Microsoft 365 entornos de prueba empresariales como Office 365 Enterprise de prueba.*</span><span class="sxs-lookup"><span data-stu-id="d3bea-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d3bea-105">Muchas organizaciones utilizan la sincronización de hash de Azure AD Connect y contraseña para sincronizar el conjunto de cuentas de su bosque de cuentas en su Active Directory Domain Services (AD DS) local para el conjunto de cuentas en el inquilino de Azure AD de sus suscripciones a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3bea-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="d3bea-106">En este artículo se describe cómo agregar la sincronización de hash de contraseña a su Microsoft 365 de prueba, lo que da como resultado esta configuración:</span><span class="sxs-lookup"><span data-stu-id="d3bea-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="d3bea-108">La configuración de este entorno de prueba implica tres fases:</span><span class="sxs-lookup"><span data-stu-id="d3bea-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="d3bea-109">Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3bea-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="d3bea-110">Fase 2: crear y registrar el dominio de laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="d3bea-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="d3bea-111">Fase 3: instalar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="d3bea-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="d3bea-112">Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="d3bea-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="d3bea-113">Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3bea-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="d3bea-114">Siga las instrucciones de [configuración base de empresa simulada para Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d3bea-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="d3bea-115">La configuración resultante tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="d3bea-115">Your resulting configuration looks like this:</span></span>
  
![La configuración básica empresarial simulada](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="d3bea-117">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="d3bea-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="d3bea-118">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d3bea-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="d3bea-119">Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="d3bea-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="d3bea-120">DC1 es un controlador de dominio para el testlab.<*nombre de* dominio público> dominio de AD DS.</span><span class="sxs-lookup"><span data-stu-id="d3bea-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="d3bea-121">Fase 2: crear y registrar el dominio de laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="d3bea-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="d3bea-122">En esta fase, agregue un dominio DNS público y, a continuación, agrégrelo a la suscripción.</span><span class="sxs-lookup"><span data-stu-id="d3bea-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="d3bea-123">En primer lugar, trabaje con el proveedor de registro DNS público para crear un nuevo nombre de dominio DNS público basado en el nombre de dominio actual y, a continuación, agrégrelo a la suscripción.</span><span class="sxs-lookup"><span data-stu-id="d3bea-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="d3bea-124">Se recomienda usar el nombre \**testlab.<*dominio público\* >\*\*.</span><span class="sxs-lookup"><span data-stu-id="d3bea-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="d3bea-125">Por ejemplo, si el nombre de dominio público es **<span>contoso</span>.com**, agregue el nombre de dominio público: **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="d3bea-126">A continuación, agregue **el testlab.<*dominio\* >*\* público a su Microsoft 365 de prueba o de pago mediante el proceso de registro de dominio.</span><span class="sxs-lookup"><span data-stu-id="d3bea-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="d3bea-127">Esto consiste en agregar registros DNS adicionales al **testlab.<*dominio público.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="d3bea-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="d3bea-128">Para obtener más información, [vea Agregar un dominio a Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="d3bea-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="d3bea-129">La configuración resultante tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="d3bea-129">Your resulting configuration looks like this:</span></span>
  
![El registro del nombre de dominio del laboratorio de pruebas](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="d3bea-131">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="d3bea-131">This configuration consists of:</span></span>

- <span data-ttu-id="d3bea-132">Una Microsoft 365 E5 de prueba o de pago con el dominio DNS testlab.<*su nombre de* dominio público> registrado.</span><span class="sxs-lookup"><span data-stu-id="d3bea-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="d3bea-133">Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="d3bea-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="d3bea-134">Observe cómo el testlab.<*el nombre de* dominio> es ahora:</span><span class="sxs-lookup"><span data-stu-id="d3bea-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="d3bea-135">Compatible con los registros DNS públicos.</span><span class="sxs-lookup"><span data-stu-id="d3bea-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="d3bea-136">Registrado en las suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3bea-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="d3bea-137">El dominio de AD DS de la intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="d3bea-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="d3bea-138">Fase 3: instalar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="d3bea-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="d3bea-139">En esta fase, instale y configure la herramienta de Conectar azure AD en APP1 y, a continuación, compruebe que funciona.</span><span class="sxs-lookup"><span data-stu-id="d3bea-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="d3bea-140">En primer lugar, instale y configure Azure AD Conectar app1.</span><span class="sxs-lookup"><span data-stu-id="d3bea-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="d3bea-141">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y conéctese a APP1 con la cuenta TESTLAB\\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="d3bea-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="d3bea-142">Desde el escritorio de APP1, abra un símbolo del sistema de Windows PowerShell con el nivel de administrador y ejecute estos comandos para deshabilitar la seguridad mejorada de Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="d3bea-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="d3bea-143">En la barra de tareas, **seleccione Internet Explorer** y vaya a [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="d3bea-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="d3bea-144">En la Microsoft Azure Active Directory Conectar, seleccione **Descargar** y, a continuación, **seleccione Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="d3bea-145">En la **página Bienvenido a Azure AD Conectar,** seleccione **Acepto** y, a continuación, **seleccione Continuar**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="d3bea-146">En la **página Configuración** express, seleccione Usar **configuración express**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="d3bea-147">En la **Conectar a Azure AD,** escriba el nombre de la cuenta de administrador global en Nombre de **usuario,** escriba su contraseña en **Contraseña** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="d3bea-148">En la **Conectar a AD DS,** escriba **TESTLAB \\ User1** en **Username,** escriba su contraseña en **Password** y, a continuación, **seleccione Next**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="d3bea-149">En la **página Listo para configurar,** seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="d3bea-150">En la **página Configuración completada,** seleccione **Salir**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="d3bea-151">En Internet Explorer, vaya al Centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="d3bea-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="d3bea-152">En el panel de navegación izquierdo, seleccione **Usuarios > usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="d3bea-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="d3bea-153">Observe la cuenta llamada **Usuario1**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-153">Note the account named **User1**.</span></span> <span data-ttu-id="d3bea-154">Esta cuenta pertenece al dominio de AD DS de TESTLAB y es una prueba de que la sincronización de directorios funcionó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3bea-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="d3bea-155">Selecciona la **cuenta User1** y, a continuación, **selecciona Licencias y aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="d3bea-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="d3bea-156">En **Licencias de productos,** seleccione su ubicación (si es necesario), deshabilite la Office 365 **de E5** y, a continuación, **habilite la Microsoft 365 E5** licencia.</span><span class="sxs-lookup"><span data-stu-id="d3bea-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="d3bea-157">Seleccione **Guardar** en la parte inferior de la página y, a continuación, **seleccione Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d3bea-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="d3bea-158">A continuación, pruebe la capacidad de iniciar sesión en la suscripción con **el  > user1@testlab.<** nombre de usuario de nombre de dominio de la cuenta User1:</span><span class="sxs-lookup"><span data-stu-id="d3bea-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="d3bea-159">Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="d3bea-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="d3bea-160">Cuando se le pida un nombre de usuario y una contraseña, **especifique user1@testlab.<*nombre\* >*\* de dominio y la contraseña user1.</span><span class="sxs-lookup"><span data-stu-id="d3bea-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="d3bea-161">Debería poder iniciar sesión como User1.</span><span class="sxs-lookup"><span data-stu-id="d3bea-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="d3bea-162">Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global.</span><span class="sxs-lookup"><span data-stu-id="d3bea-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="d3bea-163">Por lo tanto, no verá el icono de **administrador** como opción.</span><span class="sxs-lookup"><span data-stu-id="d3bea-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="d3bea-164">La configuración resultante tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="d3bea-164">Your resulting configuration looks like this:</span></span>

![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="d3bea-166">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="d3bea-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="d3bea-167">Microsoft 365 E5 o Office 365 suscripciones de prueba o de pago de E5 con el dominio DNS TESTLAB.<*el nombre* de dominio> registrado.</span><span class="sxs-lookup"><span data-stu-id="d3bea-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="d3bea-168">Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="d3bea-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="d3bea-169">Azure AD Conectar se ejecuta en APP1 para sincronizar periódicamente el dominio de TESTLAB AD DS con el inquilino de Azure AD de la Microsoft 365 suscripción.</span><span class="sxs-lookup"><span data-stu-id="d3bea-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="d3bea-170">La cuenta User1 en el dominio AD DS de TESTLAB se ha sincronizado con la cuenta empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d3bea-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="d3bea-171">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d3bea-171">Next step</span></span>

<span data-ttu-id="d3bea-172">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="d3bea-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3bea-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3bea-173">See also</span></span>

[<span data-ttu-id="d3bea-174">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d3bea-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d3bea-175">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3bea-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d3bea-176">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3bea-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)