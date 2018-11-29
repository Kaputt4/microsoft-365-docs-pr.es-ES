---
title: Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure y muestre la sincronización de hash de contraseñas e inicie sesión en su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 3cee2b69ce34647627cb2b72f9e0f59a6fba17e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871733"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="d904c-103">Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d904c-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="d904c-p101">Muchas organizaciones usan Azure AD Connect y la sincronización de hash de contraseñas para sincronizar el conjunto de cuentas de su bosque de Windows Server Active Directory (AD) local con el conjunto de cuentas del inquilino de Azure AD de las suscripciones de Office 365 y EMS E5. En este artículo se describe cómo agregar la sincronización de hash de contraseñas al entorno de pruebas de Microsoft 365, lo que da como resultado la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="d904c-p101">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Windows Server Active Directory (AD) forest to the set of accounts in the Azure AD tenant of their Office 365 and EMS E5 subscriptions. This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="d904c-107">Existen dos fases para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="d904c-107">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="d904c-108">Crear el entorno de pruebas empresarial simulado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d904c-108">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="d904c-109">Instalar y configurar Azure AD Connect en APP1.</span><span class="sxs-lookup"><span data-stu-id="d904c-109">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="d904c-110">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía del entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d904c-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="d904c-111">Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d904c-111">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="d904c-p102">Siga las instrucciones de la [configuración básica empresarial simulada para Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Esta la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="d904c-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![La configuración básica empresarial simulada](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="d904c-115">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="d904c-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="d904c-116">Suscripciones de prueba o permanentes de Office 365 E5 y EMS E5.</span><span class="sxs-lookup"><span data-stu-id="d904c-116">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="d904c-p103">Una intranet de organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENT1 en una red virtual de Azure. DC1 es un controlador de dominio para el testlab.\<su nombre de dominio público>dominio de Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="d904c-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network. DC1 is a domain controller for the testlab.\<your public domain name> Windows Server AD domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="d904c-119">Fase 2: crear y registrar el dominio de laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="d904c-119">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="d904c-120">En esta fase agregará un dominio DNS público y a su suscripción.</span><span class="sxs-lookup"><span data-stu-id="d904c-120">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="d904c-p104">Primero, trabaje con su proveedor de registro de DNS para crear un nombre de dominio DNS público en función de su nombre de dominio actual y agregarlo a su suscripción a Office 365. Se recomienda usar el nombre **testlab.**\<su dominio público>. Por ejemplo, si su nombre de dominio público es <span>**contoso</span>.com**, agregue el nombre de dominio público **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="d904c-p104">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your Office 365 subscription. We recommend using the name **testlab.**\<your public domain>. For example, if your public domain name is <span>**contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="d904c-p105">Después, agregue el **testlab.**\<el dominio público> dominio a su suscripción de prueba o permanente a Office 365 mediante el proceso de registro de dominio. Esto consiste en agregar más registros DNS al **testlab.**\<el dominio público> dominio. Para obtener más información, vea [Agregar usuarios y dominios a Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="d904c-p105">Next, you add the **testlab.**\<your public domain> domain to your Office 365 trial or permanent subscription by going through the domain registration process. This consists of adding additional DNS records to the **testlab.**\<your public domain> domain. For more information, see [Add users and domain to Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span> 

<span data-ttu-id="d904c-127">Esta la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="d904c-127">Here is your resulting configuration.</span></span>
  
![El registro del nombre de dominio del laboratorio de pruebas](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="d904c-129">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="d904c-129">This configuration consists of:</span></span>

- <span data-ttu-id="d904c-130">Suscripción de prueba o permanente a Office 365 E5 y EMS E5 con el dominio DNS testlab.\<su nombre de dominio público> registrado.</span><span class="sxs-lookup"><span data-stu-id="d904c-130">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="d904c-131">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="d904c-131">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="d904c-132">Observe cómo está ahora el testlab.\<su nombre de dominio público>:</span><span class="sxs-lookup"><span data-stu-id="d904c-132">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="d904c-133">Compatible con los registros DNS públicos.</span><span class="sxs-lookup"><span data-stu-id="d904c-133">Supported by public DNS records.</span></span>
- <span data-ttu-id="d904c-134">Registrado en las suscripciones a Office 365 y EMS.</span><span class="sxs-lookup"><span data-stu-id="d904c-134">Registered in your Office 365 and EMS subscriptions.</span></span>
- <span data-ttu-id="d904c-135">El dominio de Windows Server AD de la intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="d904c-135">The Windows Server AD domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="d904c-136">Fase 3: instalar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="d904c-136">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="d904c-137">En esta fase, instalará y configurará la herramienta Azure AD Connect en APP1 y, después, comprobará que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="d904c-137">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="d904c-138">Primero, instale y configure Azure AD Connect en APP1.</span><span class="sxs-lookup"><span data-stu-id="d904c-138">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="d904c-139">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y conéctese a APP1 con la cuenta TESTLAB\\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="d904c-139">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="d904c-140">Desde el escritorio de APP1, abra un símbolo del sistema de Windows PowerShell con el nivel de administrador y ejecute estos comandos:</span><span class="sxs-lookup"><span data-stu-id="d904c-140">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="d904c-141">En la barra de tareas, haga clic en **Internet Explorer** y vaya a [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="d904c-141">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="d904c-142">En la página de Microsoft Azure Active Directory Connect, haga clic en **Descargar** y, después, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d904c-142">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="d904c-143">En la página **Bienvenido a Azure AD Connect**, haga clic en **Acepto** y, después, en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="d904c-143">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="d904c-144">En la página **Configuración rápida**, haga clic en **Usar configuración rápida**.</span><span class="sxs-lookup"><span data-stu-id="d904c-144">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="d904c-145">En la página **Conectar a Azure AD**, escriba el nombre de la cuenta de administrador global de Office 365 en **Nombre de usuario**, escriba la contraseña en **Contraseña** y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d904c-145">On the **Connect to Azure AD** page, type your Office 365 global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d904c-146">En la página **Conectarse a AD DS**, escriba **TESTLAB\\Usuario1** en **Nombre de usuario**, escriba la contraseña en **Contraseña** y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d904c-146">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="d904c-147">En la página **Listo para configurar**, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d904c-147">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="d904c-148">En la página **Configuración completada**, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="d904c-148">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="d904c-149">En Internet Explorer, vaya al portal de Office 365 ([https://portal.office.com](https://portal.office.com)).</span><span class="sxs-lookup"><span data-stu-id="d904c-149">In Internet Explorer, go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)).</span></span>
    
12. <span data-ttu-id="d904c-150">En la página principal del portal, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="d904c-150">From the main portal page, click **Admin**.</span></span>
    
13. <span data-ttu-id="d904c-151">En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="d904c-151">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="d904c-p106">Observe la cuenta llamada **Usuario1**. Esta cuenta pertenece al dominio TESTLAB de Windows Server AD y es una prueba de que la sincronización de directorios funcionó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d904c-p106">Note the account named **User1**. This account is from the TESTLAB Windows Server AD domain and is proof that directory synchronization has worked.</span></span>
    
14. <span data-ttu-id="d904c-p107">Haga clic en la cuenta **Usuario1**. Para licencias de productos, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d904c-p107">Click the **User1** account. For product licenses, click **Edit**.</span></span>
    
15. <span data-ttu-id="d904c-p108">En **Licencias de productos**, seleccione su país y después haga clic en el control **Desactivado** de **Office 365 Enterprise E5** (para cambiarlo a **Activado**). Haga lo mismo para la licencia de **Enterprise Mobility + Security E5**.</span><span class="sxs-lookup"><span data-stu-id="d904c-p108">In **Product licenses**, select your scountry, and then click the **Off** control for **Office 365 Enterprise E5** (switching it to **On**). Do the same for the **Enterprise Mobility + Security E5** license.</span></span> 

16. <span data-ttu-id="d904c-158">Haga clic en **Guardar** en la parte inferior de la página y después haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d904c-158">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="d904c-159">Después, compruebe si puede iniciar sesión en su suscripción de Office 365 con el nombre de usuario <strong>user1@testlab.</strong>\< su nombre de dominio > nombre de usuario de la cuenta Usuario1.</span><span class="sxs-lookup"><span data-stu-id="d904c-159">Next, you test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="d904c-160">Desde APP1, cierre sesión en Office 365 y vuelva a iniciar sesión, esta vez especificando una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="d904c-160">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="d904c-p109">Cuando se le pida un nombre de usuario y una contraseña, especifique <strong>user1@testlab.</strong>\<su nombre de dominio > y la contraseña de Usuario1. Debería iniciar sesión correctamente como Usuario1.</span><span class="sxs-lookup"><span data-stu-id="d904c-p109">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password. You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="d904c-p110">Tenga en cuenta que, aunque Usuario1 tiene permisos de administrador de dominio para el dominio de Windows Server AD de TESTLAB, no es un administrador global de Office 365. Por lo tanto, el icono de \*\*Administrador \*\* no aparecerá entre las opciones.</span><span class="sxs-lookup"><span data-stu-id="d904c-p110">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="d904c-165">Esta la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="d904c-165">Here is your resulting configuration.</span></span>

![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="d904c-167">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="d904c-167">This configuration consists of:</span></span> 
  
- <span data-ttu-id="d904c-168">Suscripción de prueba o permanente a Office 365 E5 y EMS E5 con el dominio DNS TESTLAB./\<su nombre de dominio> registrado.</span><span class="sxs-lookup"><span data-stu-id="d904c-168">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="d904c-p111">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Azure Connect de AD se ejecuta en APP1 para sincronizar el dominio de Windows Server AD de TESTLAB con el inquilino de Azure AD de las suscripciones de Office 365 y EMS E5 periódicamente.</span><span class="sxs-lookup"><span data-stu-id="d904c-p111">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>
- <span data-ttu-id="d904c-171">La cuenta User1 en el dominio de Windows Server AD de TESTLAB se ha sincronizado con el inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d904c-171">The User1 account in the TESTLAB  Windows Server AD domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="d904c-172">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="d904c-172">Next step</span></span>

<span data-ttu-id="d904c-173">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="d904c-173">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d904c-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="d904c-174">See also</span></span>

[<span data-ttu-id="d904c-175">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d904c-175">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d904c-176">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d904c-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d904c-177">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d904c-177">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


