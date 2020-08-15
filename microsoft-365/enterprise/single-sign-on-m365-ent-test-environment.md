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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure y pruebe el inicio de sesión único de conexión directa de Azure AD para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 3ba229a62f66cad715f604bab91cd12032da7be8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685777"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e45b3-103">Inicio de sesión único de conexión directa de Azure AD para un entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e45b3-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e45b3-104">*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e45b3-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e45b3-p101">El inicio de sesión único de conexión directa (SSO) de Azure AD inicia sesión automáticamente a los usuarios cuando se encuentran en sus equipos PC o dispositivos conectados a la red de la organización. El SSO de conexión directa de Azure AD proporciona a los usuarios un acceso sencillo a aplicaciones basadas en la nube, sin necesitar componentes locales adicionales.</span><span class="sxs-lookup"><span data-stu-id="e45b3-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="e45b3-107">En este artículo, se describe cómo configurar el entorno de prueba de Microsoft 365 para SSO de conexión directa de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e45b3-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="e45b3-108">Hay dos fases de configuración:</span><span class="sxs-lookup"><span data-stu-id="e45b3-108">There are two phases to setting this up:</span></span>

1.    <span data-ttu-id="e45b3-109">Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="e45b3-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="e45b3-110">Configurar Azure AD Connect en APP1 para SSO de conexión directa de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e45b3-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Guías del entorno de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e45b3-112">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="e45b3-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e45b3-113">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e45b3-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e45b3-p102">Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="e45b3-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="e45b3-117">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="e45b3-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="e45b3-118">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e45b3-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="e45b3-119">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="e45b3-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="e45b3-120">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 periódicamente.</span><span class="sxs-lookup"><span data-stu-id="e45b3-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="e45b3-121">Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="e45b3-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="e45b3-122">En esta fase, configurará Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD y, después, comprobará que funcione.</span><span class="sxs-lookup"><span data-stu-id="e45b3-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="e45b3-123">Configurar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="e45b3-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="e45b3-124">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="e45b3-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="e45b3-125">Desde el escritorio de APP1, ejecute Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="e45b3-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="e45b3-126">En la página de **Bienvenida**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="e45b3-127">En la página **Tareas adicionales**, haga clic en **Cambiar inicio de sesión de usuario** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="e45b3-128">En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="e45b3-129">En la página **Inicio de sesión de usuario**, seleccione **Habilitar inicio de sesión único** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="e45b3-130">En la página **Habilitar inicio de sesión único**, haga clic en **Escribir credenciales**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="e45b3-p103">En el cuadro de diálogo **Seguridad de Windows**, escriba **usuario1** y la contraseña de la cuenta usuario1 y, después, haga clic en **Aceptar**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="e45b3-133">En la página **Listo para configurar**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="e45b3-134">En la página **Configuración completada**, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="e45b3-p104">Desde Azure Portal, en el panel izquierdo, haga clic en **Azure Active Directory > Azure AD Connect**. Asegúrese de que la característica **Inicio de sesión único de conexión directa** esté **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="e45b3-137">A continuación, pruebe la capacidad de iniciar sesión en su suscripción con el <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="e45b3-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="e45b3-138">de la cuenta User1.</span><span class="sxs-lookup"><span data-stu-id="e45b3-138">user name of the User1 account.</span></span>

1. <span data-ttu-id="e45b3-139">En Internet Explorer, en APP1, haga clic en el icono de configuración y, después, seleccione **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-139">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="e45b3-140">En **Opciones de Internet**, haga clic en la pestaña **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-140">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="e45b3-141">Haga clic en **Intranet local** y, después, seleccione **Sitios**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-141">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="e45b3-142">En **Intranet local**, haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-142">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="e45b3-143">En **Agregar este sitio web a la zona de**, escriba **https<span>://</span>autologon.microsoftazuread-sso.com**, haga clic en **Agregar > Cerrar > Aceptar > Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-143">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="e45b3-144">Cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="e45b3-144">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="e45b3-145">Cuando se le pida que inicie sesión, especifique <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="e45b3-145">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="e45b3-146">nombre y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e45b3-146">name, and then click **Next**.</span></span> <span data-ttu-id="e45b3-147">Debería iniciar sesión correctamente como User1 sin que se le pide una contraseña.</span><span class="sxs-lookup"><span data-stu-id="e45b3-147">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="e45b3-148">Esto demuestra que el SSO de inicio de sesión directa de Azure AD está funcionando.</span><span class="sxs-lookup"><span data-stu-id="e45b3-148">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="e45b3-149">Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e45b3-149">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="e45b3-150">Por lo tanto, no verá el icono de **administrador** como opción.</span><span class="sxs-lookup"><span data-stu-id="e45b3-150">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="e45b3-151">Esta es la configuración resultante:</span><span class="sxs-lookup"><span data-stu-id="e45b3-151">Here is your resulting configuration:</span></span>

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="e45b3-153">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="e45b3-153">This configuration consists of:</span></span>

- <span data-ttu-id="e45b3-154">Una suscripción de prueba de Microsoft 365 E5 o de pago con el dominio DNS testlab.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="e45b3-154">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="e45b3-155">registrado.</span><span class="sxs-lookup"><span data-stu-id="e45b3-155">registered.</span></span>
- <span data-ttu-id="e45b3-156">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="e45b3-156">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="e45b3-157">Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 con el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="e45b3-157">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="e45b3-158">El SSO de conexión directa de Azure AD está habilitado para que los equipos en la intranet ficticia puedan iniciar sesión en recursos de nube de Microsoft 365 sin especificar una contraseña de cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e45b3-158">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="e45b3-159">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e45b3-159">Next step</span></span>

<span data-ttu-id="e45b3-160">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="e45b3-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e45b3-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="e45b3-161">See also</span></span>

[<span data-ttu-id="e45b3-162">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e45b3-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e45b3-163">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e45b3-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e45b3-164">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e45b3-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


