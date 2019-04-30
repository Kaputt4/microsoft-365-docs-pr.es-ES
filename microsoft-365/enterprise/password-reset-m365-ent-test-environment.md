---
title: Restablecimiento de contraseña para el entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
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
ms.openlocfilehash: 30ce8517d1b0eb8967bd7cb26abba780d81eb8b0
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353163"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a74a4-103">Restablecimiento de contraseña para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a74a4-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a74a4-104">El restablecimiento de contraseña de autoservicio (SSPR) de Azure Active Directory (Azure AD) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas.</span><span class="sxs-lookup"><span data-stu-id="a74a4-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="a74a4-105">En este artículo se describe cómo configurar y probar los restablecimientos de contraseña en su entorno de prueba de Microsoft 365 en tres fases:</span><span class="sxs-lookup"><span data-stu-id="a74a4-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="a74a4-106">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a74a4-106">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="a74a4-107">Habilitar escritura diferida de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="a74a4-107">Enable password writeback.</span></span>
3.  <span data-ttu-id="a74a4-108">Configurar y probar el restablecimiento de contraseña de la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="a74a4-108">Configure and test password reset for the User 2 account.</span></span>
    
![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a74a4-110">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a74a4-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a74a4-111">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a74a4-111">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a74a4-p101">Primero, siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="a74a4-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="a74a4-115">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="a74a4-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="a74a4-116">Suscripciones de prueba o de pago de Office 365 E5 y EMS E5.</span><span class="sxs-lookup"><span data-stu-id="a74a4-116">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="a74a4-117">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="a74a4-117">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="a74a4-118">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Office 365 y E5 EMS.</span><span class="sxs-lookup"><span data-stu-id="a74a4-118">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>


## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="a74a4-119">Fase 2: habilitar escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="a74a4-119">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="a74a4-120">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="a74a4-120">Next, follow the instructions in [Phase 2 of the password writeback](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) Test Lab Guide.</span></span>

<span data-ttu-id="a74a4-121">Debe tener la escritura diferida de contraseñas habilitada para utilizar el restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="a74a4-121">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="a74a4-122">Fase 3: configurar y probar el restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="a74a4-122">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="a74a4-123">En esta fase, configurará el restablecimiento de contraseña del inquilino de Azure AD mediante la pertenencia del grupo y después comprobará que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="a74a4-123">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="a74a4-124">En primer lugar, habilite el restablecimiento de contraseña de cuentas en un determinado grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a74a4-124">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="a74a4-125">Desde una instancia privada del explorador, abra [https://portal.azure.com](https://portal.azure.com) y después inicie sesión con las credenciales de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a74a4-125">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="a74a4-126">En Azure Portal, haga clic en **Azure Active Directory > Grupos > Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-126">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="a74a4-p102">Configure **Tipo de grupo** como **Seguridad**, **Nombre del grupo** como **PWReset** y **Tipo de pertenencia** como **Asignado**. Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="a74a4-129">Haga clic en el grupo **PWReset** en la lista y después haga clic en **Miembros**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-129">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="a74a4-p103">Haga clic en **Agregar miembros**, después en **Usuario 2** y elija **Seleccionar**. Cierre las páginas **PWReset** y **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="a74a4-132">En la página de Azure Active Directory, haga clic en **Restablecimiento de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-132">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="a74a4-133">En la página **Propiedades**, en la opción **Restablecimiento de contraseña autoservicio habilitado**, elija **Seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-133">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="a74a4-134">En **Seleccionar grupo**, escoja **PWReset** y después haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-134">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="a74a4-135">Cierre la instancia de explorador privada.</span><span class="sxs-lookup"><span data-stu-id="a74a4-135">Close the private browser instance.</span></span>

<span data-ttu-id="a74a4-136">Después, pruebe el restablecimiento de contraseña de la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="a74a4-136">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="a74a4-137">Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="a74a4-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="a74a4-138">Inicie sesión con las credenciales de la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="a74a4-138">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="a74a4-139">En **No perder el acceso a su cuenta**, configure el teléfono de autenticación con su número de teléfono y el correo electrónico de autenticación con su cuenta de correo electrónico laboral o personal.</span><span class="sxs-lookup"><span data-stu-id="a74a4-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="a74a4-140">Cuando haya comprobados ambos, haga clic en **Parece que está bien** y cierre la instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="a74a4-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="a74a4-141">Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="a74a4-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="a74a4-142">Inicie sesión con las credenciales de la cuenta Usuario 2, escriba los caracteres de la CAPTCHA y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-142">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="a74a4-p104">Para el **paso de verificación 1**, haga clic en **Enviar un correo electrónico a mi correo electrónico alternativo** y después en **Correo electrónico**. Cuando reciba el correo electrónico, escriba el código de comprobación y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="a74a4-p105">En **Volver a su cuenta**, escriba una nueva contraseña para la cuenta Usuario 2 y después haga clic en **Finalizar**. Anote la contraseña cambiada de la cuenta Usuario 2 y guárdela en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="a74a4-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="a74a4-147">En una pestaña independiente del mismo explorador, escriba [https://portal.office.com](https://portal.office.com) y después inicie sesión con el nombre de la cuenta Usuario 2 y la nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="a74a4-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password. You should see the Office Home page.</span></span> <span data-ttu-id="a74a4-148">Debe ver la página **principal de Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="a74a4-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="a74a4-149">Vea el paso [Simplificar el restablecimiento de contraseña](identity-password-reset.md#identity-pw-reset) en la fase Identidad para obtener información y vínculos sobre cómo configurar el restablecimiento de contraseña en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="a74a4-149">See the [Simplify password resets](identity-password-reset.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a74a4-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a74a4-150">Next step</span></span>

<span data-ttu-id="a74a4-151">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="a74a4-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a74a4-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="a74a4-152">See also</span></span>

[<span data-ttu-id="a74a4-153">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a74a4-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a74a4-154">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a74a4-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a74a4-155">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a74a4-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
