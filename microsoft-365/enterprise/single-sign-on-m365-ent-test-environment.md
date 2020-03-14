---
title: Inicio de sesión único de conexión directa de Azure AD para un entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure y pruebe el inicio de sesión único de conexión directa de Azure AD para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: d2b17acb2b57e379fe204e3ea4402b3f00ef7d6c
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633168"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="1213a-103">Inicio de sesión único de conexión directa de Azure AD para un entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1213a-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="1213a-104">*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1213a-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1213a-p101">El inicio de sesión único de conexión directa (SSO) de Azure AD inicia sesión automáticamente a los usuarios cuando se encuentran en sus equipos PC o dispositivos conectados a la red de la organización. El SSO de conexión directa de Azure AD proporciona a los usuarios un acceso sencillo a aplicaciones basadas en la nube, sin necesitar componentes locales adicionales.</span><span class="sxs-lookup"><span data-stu-id="1213a-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="1213a-107">En este artículo, se describe cómo configurar el entorno de prueba de Microsoft 365 para SSO de conexión directa de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1213a-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="1213a-108">Hay dos fases de configuración:</span><span class="sxs-lookup"><span data-stu-id="1213a-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="1213a-109">Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="1213a-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="1213a-110">Configurar Azure AD Connect en APP1 para SSO de conexión directa de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1213a-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Guías del entorno de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="1213a-112">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1213a-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="1213a-113">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1213a-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="1213a-p102">Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="1213a-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="1213a-117">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="1213a-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="1213a-118">Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="1213a-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="1213a-119">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="1213a-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="1213a-120">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 u Office 365 periódicamente.</span><span class="sxs-lookup"><span data-stu-id="1213a-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="1213a-121">Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="1213a-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="1213a-122">En esta fase, configurará Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD y, después, comprobará que funcione.</span><span class="sxs-lookup"><span data-stu-id="1213a-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="1213a-123">Configurar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="1213a-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="1213a-124">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="1213a-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="1213a-125">Desde el escritorio de APP1, ejecute Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1213a-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="1213a-126">En la página de **Bienvenida**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="1213a-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="1213a-127">En la página **Tareas adicionales**, haga clic en **Cambiar inicio de sesión de usuario** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1213a-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="1213a-128">En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1213a-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="1213a-129">En la página **Inicio de sesión de usuario**, seleccione **Habilitar inicio de sesión único** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1213a-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="1213a-130">En la página **Habilitar inicio de sesión único**, haga clic en **Escribir credenciales**.</span><span class="sxs-lookup"><span data-stu-id="1213a-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="1213a-p103">En el cuadro de diálogo **Seguridad de Windows**, escriba **usuario1** y la contraseña de la cuenta usuario1 y, después, haga clic en **Aceptar**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1213a-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="1213a-133">En la página **Listo para configurar**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="1213a-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="1213a-134">En la página **Configuración completada**, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="1213a-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="1213a-p104">Desde Azure Portal, en el panel izquierdo, haga clic en **Azure Active Directory > Azure AD Connect**. Asegúrese de que la característica **Inicio de sesión único de conexión directa** esté **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="1213a-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="1213a-137">Después, compruebe si puede iniciar sesión en su suscripción con el <strong>user1@testlab.</strong>\<su nombre de usuario de dominio público> de la cuenta Usuario1.</span><span class="sxs-lookup"><span data-stu-id="1213a-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="1213a-138">En Internet Explorer, en APP1, haga clic en el icono de configuración y, después, seleccione **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="1213a-138">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="1213a-139">En **Opciones de Internet**, haga clic en la pestaña **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="1213a-139">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="1213a-140">Haga clic en **Intranet local** y, después, seleccione **Sitios**.</span><span class="sxs-lookup"><span data-stu-id="1213a-140">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="1213a-141">En **Intranet local**, haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="1213a-141">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="1213a-142">En **Agregar este sitio web a la zona de**, escriba **https<span>://</span>autologon.microsoftazuread-sso.com**, haga clic en **Agregar > Cerrar > Aceptar > Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1213a-142">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="1213a-143">Cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="1213a-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="1213a-144">Cuando se le solicite iniciar sesión, especifique <strong>user1@testlab.</strong> \<su dominio público> nombre y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1213a-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="1213a-145">Debería iniciar sesión correctamente como User1 sin que se le pide una contraseña.</span><span class="sxs-lookup"><span data-stu-id="1213a-145">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="1213a-146">Esto demuestra que el SSO de inicio de sesión directa de Azure AD está funcionando.</span><span class="sxs-lookup"><span data-stu-id="1213a-146">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="1213a-147">Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1213a-147">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="1213a-148">Por lo tanto, no verá el icono de **administrador** como opción.</span><span class="sxs-lookup"><span data-stu-id="1213a-148">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="1213a-149">Esta es la configuración resultante:</span><span class="sxs-lookup"><span data-stu-id="1213a-149">Here is your resulting configuration:</span></span>

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="1213a-151">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="1213a-151">This configuration consists of:</span></span>

- <span data-ttu-id="1213a-152">Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5 con el dominio DNS TESTLAB.\<su nombre de dominio > registrado.</span><span class="sxs-lookup"><span data-stu-id="1213a-152">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="1213a-153">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="1213a-153">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="1213a-154">Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft Office 365 u Office 365 con el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="1213a-154">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 or Office 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="1213a-155">El SSO de conexión directa de Azure AD está habilitado para que los equipos en la intranet ficticia puedan iniciar sesión en recursos de nube de Microsoft 365 sin especificar una contraseña de cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="1213a-155">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="1213a-156">Vea el paso [Simplificar el inicio de sesión de usuario](identity-secure-your-passwords.md#identity-sso) en la fase Identidad para obtener información y vínculos sobre cómo configurar el SSO de conexión directa de Azure AD en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="1213a-156">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="1213a-157">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="1213a-157">Next step</span></span>

<span data-ttu-id="1213a-158">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="1213a-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1213a-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="1213a-159">See also</span></span>

[<span data-ttu-id="1213a-160">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1213a-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1213a-161">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1213a-161">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1213a-162">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1213a-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


