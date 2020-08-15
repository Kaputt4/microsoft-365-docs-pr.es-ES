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
ms.openlocfilehash: 2930d147e2ae3277b0af4d2aa81a602c73128439
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686553"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="835f4-103">Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="835f4-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="835f4-104">*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*</span><span class="sxs-lookup"><span data-stu-id="835f4-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="835f4-105">Muchas organizaciones utilizan la sincronización de hash de Azure AD Connect y contraseña para sincronizar el conjunto de cuentas de su bosque de cuentas en su Active Directory Domain Services (AD DS) local para el conjunto de cuentas en el inquilino de Azure AD de sus suscripciones a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="835f4-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> <span data-ttu-id="835f4-106">En este artículo se describe cómo puede añadir la sincronización hash de contraseñas al entorno de pruebas de Microsoft 365, dando como resultado la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="835f4-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="835f4-108">Existen dos fases para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="835f4-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="835f4-109">Crear el entorno de pruebas empresarial simulado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="835f4-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="835f4-110">Instalar y configurar Azure AD Connect en APP1.</span><span class="sxs-lookup"><span data-stu-id="835f4-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="835f4-111">Vaya a [Microsoft 365 for Enterprise test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para obtener un mapa visual de todos los artículos de la pila de la guía de entorno de pruebas 365 para empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="835f4-111">Go to [Microsoft 365 for enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="835f4-112">Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="835f4-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="835f4-p102">Siga las instrucciones de la [configuración básica empresarial simulada para Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Esta la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="835f4-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![La configuración básica empresarial simulada](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="835f4-116">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="835f4-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="835f4-117">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="835f4-117">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="835f4-118">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="835f4-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="835f4-119">DC1 es un controlador de dominio para el dominio de AD DS testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="835f4-119">DC1 is a domain controller for the testlab.\<your public domain name></span></span> <span data-ttu-id="835f4-120">.</span><span class="sxs-lookup"><span data-stu-id="835f4-120">AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="835f4-121">Fase 2: crear y registrar el dominio de laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="835f4-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="835f4-122">En esta fase agregará un dominio DNS público y a su suscripción.</span><span class="sxs-lookup"><span data-stu-id="835f4-122">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="835f4-123">En primer lugar, trabaje con proveedor de registro DNS público para crear un nuevo nombre de dominio DNS público en función de su nombre de dominio actual y agréguelo a su suscripción.</span><span class="sxs-lookup"><span data-stu-id="835f4-123">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.</span></span> <span data-ttu-id="835f4-124">Le recomendamos usar el nombre **testlab.**\<your public domain>.</span><span class="sxs-lookup"><span data-stu-id="835f4-124">We recommend using the name **testlab.**\<your public domain>.</span></span> <span data-ttu-id="835f4-125">Por ejemplo, si el nombre de dominio público es <span>\*\*\*\* contoso</span>. com, agregue el nombre de dominio público **<span>testlab</span>. contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="835f4-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="835f4-126">Después, agregue el dominio **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="835f4-126">Next, you add the **testlab.**\<your public domain></span></span> <span data-ttu-id="835f4-127">dominio a su suscripción de prueba de Microsoft 365 o de pago mediante el proceso de registro de dominio.</span><span class="sxs-lookup"><span data-stu-id="835f4-127">domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="835f4-128">Esto consiste en añadir más registros DNS al dominio **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="835f4-128">This consists of adding additional DNS records to the **testlab.**\<your public domain></span></span> <span data-ttu-id="835f4-129">.</span><span class="sxs-lookup"><span data-stu-id="835f4-129">domain.</span></span> <span data-ttu-id="835f4-130">Para obtener más información, consulte [Agregar un dominio a Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="835f4-130">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span> 

<span data-ttu-id="835f4-131">Este es el resultado de la configuración.</span><span class="sxs-lookup"><span data-stu-id="835f4-131">Here is your resulting configuration.</span></span>
  
![El registro del nombre de dominio del laboratorio de pruebas](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="835f4-133">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="835f4-133">This configuration consists of:</span></span>

- <span data-ttu-id="835f4-134">Una suscripción de prueba de Microsoft 365 E5 o de pago con el dominio DNS testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="835f4-134">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.\<your public domain name></span></span> <span data-ttu-id="835f4-135">registrado.</span><span class="sxs-lookup"><span data-stu-id="835f4-135">registered.</span></span>
- <span data-ttu-id="835f4-136">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="835f4-136">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="835f4-137">Observe el estado de testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="835f4-137">Notice how the testlab.\<your public domain name></span></span> <span data-ttu-id="835f4-138">ahora:</span><span class="sxs-lookup"><span data-stu-id="835f4-138">is now:</span></span>

- <span data-ttu-id="835f4-139">Compatible con los registros DNS públicos.</span><span class="sxs-lookup"><span data-stu-id="835f4-139">Supported by public DNS records.</span></span>
- <span data-ttu-id="835f4-140">Registrado en las suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="835f4-140">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="835f4-141">El dominio de AD DS de la intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="835f4-141">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="835f4-142">Fase 3: instalar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="835f4-142">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="835f4-143">En esta fase, instalará y configurará la herramienta Azure AD Connect en APP1 y, después, comprobará que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="835f4-143">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="835f4-144">Primero, instale y configure Azure AD Connect en APP1.</span><span class="sxs-lookup"><span data-stu-id="835f4-144">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="835f4-145">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y conéctese a APP1 con la cuenta TESTLAB\\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="835f4-145">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="835f4-146">Desde el escritorio de APP1, abra un símbolo del sistema de Windows PowerShell con el nivel de administrador y ejecute estos comandos para deshabilitar la seguridad mejorada de Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="835f4-146">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="835f4-147">En la barra de tareas, haga clic en **Internet Explorer** y vaya a [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="835f4-147">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="835f4-148">En la página de Microsoft Azure Active Directory Connect, haga clic en **Descargar** y, después, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="835f4-148">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="835f4-149">En la página **Bienvenido a Azure AD Connect**, haga clic en **Acepto** y, después, en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="835f4-149">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="835f4-150">En la página **Configuración rápida**, haga clic en **Usar configuración rápida**.</span><span class="sxs-lookup"><span data-stu-id="835f4-150">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="835f4-151">En la página **Conectar a Azure AD**, escriba el nombre de la cuenta de administrador global en **Nombre de usuario**, escriba la contraseña en **Contraseña** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="835f4-151">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="835f4-152">En la página **Conectarse a AD DS**, escriba **TESTLAB\\Usuario1** en **Nombre de usuario**, escriba la contraseña en **Contraseña** y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="835f4-152">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="835f4-153">En la página **Listo para configurar**, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="835f4-153">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="835f4-154">En la página **Configuración completada** de página, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="835f4-154">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="835f4-155">En Internet Explorer, vaya al Centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="835f4-155">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="835f4-156">En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="835f4-156">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="835f4-157">Observe la cuenta llamada **Usuario1**.</span><span class="sxs-lookup"><span data-stu-id="835f4-157">Note the account named **User1**.</span></span> <span data-ttu-id="835f4-158">Esta cuenta pertenece al dominio de AD DS de TESTLAB y es una prueba de que la sincronización de directorios funcionó correctamente.</span><span class="sxs-lookup"><span data-stu-id="835f4-158">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="835f4-159">Haga clic en la cuenta **Usuario1** y después, haga clic en **Licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="835f4-159">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="835f4-160">En **Licencias de producto**, seleccione su ubicación (si es necesario), deshabilite la licencia de **Office 365 E5** y habilite la licencia de **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="835f4-160">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="835f4-161">Haga clic en **Guardar** en la parte inferior de la página y después haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="835f4-161">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="835f4-162">A continuación, probará la capacidad de iniciar sesión en su suscripción con el nombre de usuario<strong>user1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="835f4-162">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="835f4-163">de la cuenta User1.</span><span class="sxs-lookup"><span data-stu-id="835f4-163">user name of the User1 account.</span></span>

1. <span data-ttu-id="835f4-164">Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="835f4-164">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="835f4-165">Cuando se le pida el nombre de usuario y la contraseña, especifique <strong>user1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="835f4-165">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="835f4-166">y la contraseña de User1.</span><span class="sxs-lookup"><span data-stu-id="835f4-166">and the User1 password.</span></span> <span data-ttu-id="835f4-167">Debería poder iniciar sesión como User1.</span><span class="sxs-lookup"><span data-stu-id="835f4-167">You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="835f4-168">Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global.</span><span class="sxs-lookup"><span data-stu-id="835f4-168">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="835f4-169">Por lo tanto, no verá el icono de **administrador** como opción.</span><span class="sxs-lookup"><span data-stu-id="835f4-169">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="835f4-170">Este es el resultado de la configuración.</span><span class="sxs-lookup"><span data-stu-id="835f4-170">Here is your resulting configuration.</span></span>

![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="835f4-172">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="835f4-172">This configuration consists of:</span></span> 
  
- <span data-ttu-id="835f4-173">Suscripciones de prueba o de pago de Office 365 E5 o Microsoft 365 E5 con el dominio DNS TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="835f4-173">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="835f4-174">registrado.</span><span class="sxs-lookup"><span data-stu-id="835f4-174">registered.</span></span>
- <span data-ttu-id="835f4-175">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="835f4-175">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="835f4-176">Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="835f4-176">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>
- <span data-ttu-id="835f4-177">La cuenta User1 en el dominio AD DS de TESTLAB se ha sincronizado con la cuenta empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="835f4-177">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="835f4-178">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="835f4-178">Next step</span></span>

<span data-ttu-id="835f4-179">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="835f4-179">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="835f4-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="835f4-180">See also</span></span>

[<span data-ttu-id="835f4-181">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="835f4-181">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="835f4-182">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="835f4-182">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="835f4-183">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="835f4-183">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


