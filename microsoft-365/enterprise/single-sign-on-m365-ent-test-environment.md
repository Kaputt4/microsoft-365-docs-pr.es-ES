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
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904869"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="772c1-103">Inicio de sesión único de conexión directa de Azure AD para un entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="772c1-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="772c1-104">*Esta guía del laboratorio de pruebas se puede usar para entornos de prueba de Microsoft 365 para empresas y office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="772c1-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="772c1-105">Azure AD Seamless Single Sign-On (SSO de conexión directa) inicia sesión automáticamente en los usuarios cuando están en sus equipos o dispositivos que están conectados a la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="772c1-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="772c1-106">Sso de conexión directa de Azure AD proporciona a los usuarios un fácil acceso a aplicaciones basadas en la nube sin necesidad de componentes locales adicionales.</span><span class="sxs-lookup"><span data-stu-id="772c1-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="772c1-107">En este artículo se describe cómo configurar el entorno de prueba de Microsoft 365 para SSO de conexión directa de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="772c1-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="772c1-108">La configuración de SSO de conexión directa de Azure AD implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="772c1-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="772c1-109">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="772c1-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="772c1-110">Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="772c1-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="772c1-112">Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para](../downloads/Microsoft365EnterpriseTLGStack.pdf)enterprise Test Lab Guide Stack .</span><span class="sxs-lookup"><span data-stu-id="772c1-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="772c1-113">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="772c1-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="772c1-114">Siga las instrucciones de [sincronización de hash de contraseña para Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="772c1-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="772c1-115">La configuración resultante tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="772c1-115">Your resulting configuration looks like this:</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="772c1-117">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="772c1-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="772c1-118">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="772c1-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="772c1-119">Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="772c1-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="772c1-120">Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio DE SERVICIOS de dominio de Active Directory (AD DS) de TESTLAB con el inquilino de Azure AD de su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="772c1-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="772c1-121">Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="772c1-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="772c1-122">En esta fase, configure Azure AD Connect en APP1 para SSO de conexión directa de Azure AD y compruebe que funciona.</span><span class="sxs-lookup"><span data-stu-id="772c1-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="772c1-123">Configurar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="772c1-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="772c1-124">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="772c1-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="772c1-125">Desde el escritorio de APP1, ejecute Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="772c1-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="772c1-126">En la **página de bienvenida,** seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="772c1-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="772c1-127">En la **página Tareas adicionales,** seleccione **Cambiar inicio de sesión de usuario** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="772c1-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="772c1-128">En la **página Conectarse a Azure AD,** escriba las credenciales de la cuenta de administrador global y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="772c1-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="772c1-129">En la **página Inicio de sesión de usuario,** seleccione Habilitar inicio de sesión **único** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="772c1-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="772c1-130">En la **página Habilitar inicio de sesión único,** seleccione Escribir **credenciales**.</span><span class="sxs-lookup"><span data-stu-id="772c1-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="772c1-131">En el cuadro de diálogo Seguridad de **Windows,** escriba **user1** y la contraseña de la cuenta de usuario1, seleccione **Aceptar** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="772c1-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="772c1-132">En la **página Listo para configurar,** seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="772c1-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="772c1-133">En la **página Configuración completada,** seleccione **Salir**.</span><span class="sxs-lookup"><span data-stu-id="772c1-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="772c1-134">En Azure Portal, en el panel izquierdo, seleccione **Azure Active Directory** Azure AD  >  **Connect**.</span><span class="sxs-lookup"><span data-stu-id="772c1-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="772c1-135">Compruebe que la **característica de inicio de sesión único sin** problemas aparece como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="772c1-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="772c1-136">A continuación, pruebe la capacidad de iniciar sesión en la suscripción con el <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="772c1-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="772c1-137">de la cuenta User1.</span><span class="sxs-lookup"><span data-stu-id="772c1-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="772c1-138">En Internet Explorer en APP1, seleccione el icono de configuración y, a continuación, seleccione **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="772c1-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="772c1-139">En **Opciones de Internet,** seleccione la **pestaña** Seguridad.</span><span class="sxs-lookup"><span data-stu-id="772c1-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="772c1-140">Seleccione **Intranet local** y, a continuación, **sitios**.</span><span class="sxs-lookup"><span data-stu-id="772c1-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="772c1-141">En **Intranet local,** seleccione **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="772c1-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="772c1-142">En **Agregar este sitio web a la zona**, escriba https **<span>://</span>autologon.microsoftazuread-sso.com**, seleccione Agregar   >  **cerrar**  >  **aceptar**  >  .</span><span class="sxs-lookup"><span data-stu-id="772c1-142">In **Add this website to the zone**, enter **https <span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="772c1-143">Cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="772c1-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="772c1-144">Cuando se le pida que inicie sesión, especifique <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="772c1-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="772c1-145">y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="772c1-145">name, and then select **Next**.</span></span> <span data-ttu-id="772c1-146">Debería iniciar sesión correctamente como User1 sin que se le pide una contraseña.</span><span class="sxs-lookup"><span data-stu-id="772c1-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="772c1-147">Esto demuestra que el SSO de inicio de sesión directa de Azure AD está funcionando.</span><span class="sxs-lookup"><span data-stu-id="772c1-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="772c1-148">Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="772c1-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="772c1-149">Por lo tanto, no verá el icono de **administrador** como opción.</span><span class="sxs-lookup"><span data-stu-id="772c1-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="772c1-150">Esta es la configuración resultante:</span><span class="sxs-lookup"><span data-stu-id="772c1-150">Here is your resulting configuration:</span></span>

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="772c1-152">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="772c1-152">This configuration consists of:</span></span>

- <span data-ttu-id="772c1-153">Una versión de prueba de Microsoft 365 E5 o suscripciones de pago con el testlab de dominio DNS.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="772c1-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="772c1-154">registrado.</span><span class="sxs-lookup"><span data-stu-id="772c1-154">registered.</span></span>
- <span data-ttu-id="772c1-155">Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="772c1-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="772c1-156">Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 con el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="772c1-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="772c1-157">Sso de conexión directa de Azure AD está habilitado para que los equipos de la intranet simulada puedan iniciar sesión en recursos en la nube de Microsoft 365 sin especificar una contraseña de cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="772c1-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="772c1-158">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="772c1-158">Next step</span></span>

<span data-ttu-id="772c1-159">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="772c1-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="772c1-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="772c1-160">See also</span></span>

[<span data-ttu-id="772c1-161">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="772c1-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="772c1-162">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="772c1-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="772c1-163">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="772c1-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)