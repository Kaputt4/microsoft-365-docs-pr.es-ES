---
title: Restablecimiento de contraseña para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
description: 'Resumen: configure y pruebe el restablecimiento de contraseña para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 96a8b03ca978ac2b2174742c0208444d853ba7c9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632892"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="fd9ec-103">Restablecimiento de contraseña para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd9ec-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="fd9ec-104">*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fd9ec-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="fd9ec-105">El restablecimiento de contraseña de autoservicio (SSPR) de Azure Active Directory (Azure AD) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="fd9ec-106">En este artículo se describe cómo configurar y probar los restablecimientos de contraseña en su entorno de prueba de Microsoft 365 en tres fases:</span><span class="sxs-lookup"><span data-stu-id="fd9ec-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.    <span data-ttu-id="fd9ec-107">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="fd9ec-108">Habilitar escritura diferida de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-108">Enable password writeback.</span></span>
3.    <span data-ttu-id="fd9ec-109">Configure y pruebe el restablecimiento de contraseña para la cuenta de usuario 3.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-109">Configure and test password reset for the User 3 account.</span></span>
    
![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="fd9ec-111">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="fd9ec-112">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd9ec-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="fd9ec-p101">Primero, siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="fd9ec-116">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="fd9ec-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="fd9ec-117">Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="fd9ec-118">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="fd9ec-119">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="fd9ec-120">Fase 2: habilitar escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="fd9ec-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="fd9ec-121">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="fd9ec-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="fd9ec-122">Debe tener la escritura diferida de contraseñas habilitada para utilizar el restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="fd9ec-123">Fase 3: configurar y probar el restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="fd9ec-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="fd9ec-124">En esta fase, configurará el restablecimiento de contraseña del inquilino de Azure AD mediante la pertenencia del grupo y después comprobará que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="fd9ec-125">En primer lugar, habilite el restablecimiento de contraseña de cuentas en un determinado grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="fd9ec-126">Desde una instancia privada del explorador, abra [https://portal.azure.com](https://portal.azure.com) y después inicie sesión con las credenciales de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="fd9ec-127">En Azure Portal, haga clic en **Azure Active Directory > Grupos > Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="fd9ec-128">Configure **Tipo de grupo** como **Seguridad**, **Nombre del grupo** como **PWReset** y **Tipo de pertenencia** como **Asignado**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="fd9ec-129">Haga clic en **Miembros**, busque y seleccione **usuario 3**, después haga clic en **Seleccionar**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="fd9ec-130">Cierre el panel **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="fd9ec-131">En el panel de navegación izquierdo de Azure Active Directory, haga clic en **Restablecer contraseña**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="fd9ec-132">En el panel **Propiedades - Restablecer contraseña**, debajo de la opción **Habilitar autoservicio de restablecimiento de contraseña**, elija **Seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="fd9ec-133">Haga clic en **Seleccionar grupo**, seleccione el grupo **PWReset** y después haga clic en **Seleccionar > Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="fd9ec-134">Cierre la instancia de explorador privada.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-134">Close the private browser instance.</span></span>

<span data-ttu-id="fd9ec-135">Después, pruebe el restablecimiento de contraseña de la cuenta Usuario 3.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="fd9ec-136">Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="fd9ec-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="fd9ec-137">Inicie sesión con las credenciales de la cuenta Usuario 3.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="fd9ec-138">En **más información necesaria**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="fd9ec-139">En **No perder el acceso a su cuenta**, configure el teléfono de autenticación con su número de teléfono y el correo electrónico de autenticación con su cuenta de correo electrónico laboral o personal.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-139">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="fd9ec-140">Cuando haya comprobados ambos, haga clic en **Parece que está bien** y cierre la instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="fd9ec-141">Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="fd9ec-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="fd9ec-142">Escriba el nombre de la cuenta de usuario 3, escriba los caracteres de la CAPTCHA y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="fd9ec-p102">Para el **paso de verificación 1**, haga clic en **Enviar un correo electrónico a mi correo electrónico alternativo** y después en **Correo electrónico**. Cuando reciba el correo electrónico, escriba el código de comprobación y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-p102">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="fd9ec-145">En **Volver a la cuenta**, escriba una nueva contraseña para la cuenta de usuario 3 y después haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="fd9ec-146">Anote la contraseña cambiada de la cuenta de usuario 3 y almacénela en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="fd9ec-147">En una pestaña independiente del mismo explorador, vaya a [https://portal.office.com](https://portal.office.com) y después inicie sesión con el nombre de la cuenta Usuario 3 y la nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="fd9ec-148">Debe ver la página **principal de Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="fd9ec-149">Vea el paso [Simplificar el restablecimiento de contraseña](identity-secure-your-passwords.md#identity-pw-reset) en la fase Identidad para obtener información y vínculos sobre cómo configurar el restablecimiento de contraseña en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="fd9ec-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="fd9ec-150">Next step</span></span>

<span data-ttu-id="fd9ec-151">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="fd9ec-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd9ec-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd9ec-152">See also</span></span>

[<span data-ttu-id="fd9ec-153">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fd9ec-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fd9ec-154">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fd9ec-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fd9ec-155">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fd9ec-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
