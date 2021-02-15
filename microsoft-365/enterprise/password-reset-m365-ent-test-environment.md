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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure y pruebe el restablecimiento de contraseña para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487429"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="86b87-103">Restablecimiento de contraseña para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="86b87-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="86b87-104">*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*</span><span class="sxs-lookup"><span data-stu-id="86b87-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="86b87-105">El restablecimiento de contraseña de autoservicio (SSPR) de Azure Active Directory (Azure AD) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas.</span><span class="sxs-lookup"><span data-stu-id="86b87-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="86b87-106">En este artículo se describe cómo configurar y probar restablecimientos de contraseña en el entorno de prueba de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b87-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="86b87-107">La configuración de SSPR consta de tres fases:</span><span class="sxs-lookup"><span data-stu-id="86b87-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="86b87-108">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="86b87-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="86b87-109">Fase 2: habilitar escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="86b87-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="86b87-110">Fase 3: configurar y probar el restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="86b87-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="86b87-112">Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="86b87-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="86b87-113">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="86b87-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="86b87-114">En primer lugar, siga las instrucciones de sincronización [de hash de contraseña.](password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="86b87-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="86b87-115">La configuración resultante tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="86b87-115">Your resulting configuration looks like this:</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="86b87-117">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="86b87-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="86b87-118">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="86b87-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="86b87-119">Intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="86b87-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="86b87-120">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b87-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="86b87-121">Fase 2: habilitar escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="86b87-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="86b87-122">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="86b87-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="86b87-123">Debe tener la escritura diferida de contraseñas habilitada para utilizar el restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="86b87-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="86b87-124">Fase 3: configurar y probar el restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="86b87-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="86b87-125">En esta fase, configure el restablecimiento de contraseña en el inquilino de Azure AD a través de la pertenencia a grupos y, a continuación, compruebe que funciona.</span><span class="sxs-lookup"><span data-stu-id="86b87-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="86b87-126">En primer lugar, habilite el restablecimiento de contraseña de cuentas en un determinado grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="86b87-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="86b87-127">Desde una instancia privada del explorador, abra [https://portal.azure.com](https://portal.azure.com) y después inicie sesión con las credenciales de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="86b87-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="86b87-128">En Azure Portal, seleccione **Grupos de Azure Active Directory** Nuevo  >    >  **grupo.**</span><span class="sxs-lookup"><span data-stu-id="86b87-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="86b87-129">Configure **Tipo de grupo** como **Seguridad**, **Nombre del grupo** como **PWReset** y **Tipo de pertenencia** como **Asignado**.</span><span class="sxs-lookup"><span data-stu-id="86b87-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="86b87-130">Seleccione **Miembros,** busque y seleccione **Usuario 3,** **Seleccione** y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="86b87-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="86b87-131">Cierre el panel **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="86b87-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="86b87-132">En el panel de Azure Active Directory, seleccione **Restablecimiento de contraseña** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="86b87-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="86b87-133">En el panel **Propiedades - Restablecer contraseña**, debajo de la opción **Habilitar autoservicio de restablecimiento de contraseña**, elija **Seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="86b87-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="86b87-134">Seleccione **Seleccionar grupo,** seleccione el **grupo PWReset** y, a continuación, **seleccione**  >  **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86b87-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="86b87-135">Cierre la instancia de explorador privada.</span><span class="sxs-lookup"><span data-stu-id="86b87-135">Close the private browser instance.</span></span>

<span data-ttu-id="86b87-136">A continuación, pruebe el restablecimiento de contraseña para la cuenta usuario 3.</span><span class="sxs-lookup"><span data-stu-id="86b87-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="86b87-137">Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="86b87-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="86b87-138">Inicie sesión con las credenciales de la cuenta Usuario 3.</span><span class="sxs-lookup"><span data-stu-id="86b87-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="86b87-139">En **Más información necesaria,** seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86b87-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="86b87-140">En **No perder el acceso a su cuenta**, configure el teléfono de autenticación con su número de teléfono y el correo electrónico de autenticación con su cuenta de correo electrónico laboral o personal.</span><span class="sxs-lookup"><span data-stu-id="86b87-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="86b87-141">Después de comprobar ambos, seleccione **Se ve bien** y, a continuación, cierre la instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="86b87-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="86b87-142">En una nueva instancia de explorador privado, vaya a [https://aka.ms/sspr](https://aka.ms/sspr) .</span><span class="sxs-lookup"><span data-stu-id="86b87-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="86b87-143">Escriba el nombre de la cuenta usuario 3, escriba los caracteres de captcha y, a continuación, **seleccione siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86b87-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="86b87-144">Para **el paso de verificación 1,** seleccione Enviar un correo electrónico a mi **correo** electrónico alternativo y, a continuación, seleccione **Correo electrónico.**</span><span class="sxs-lookup"><span data-stu-id="86b87-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="86b87-145">Cuando reciba el correo electrónico, escriba el código de verificación y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86b87-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="86b87-146">En **Volver a su cuenta,** escriba una nueva contraseña para la cuenta usuario 3 y, a continuación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="86b87-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="86b87-147">Anote la contraseña cambiada de la cuenta de usuario 3 y almacénela en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="86b87-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="86b87-148">En una pestaña independiente del mismo explorador, vaya a [https://portal.office.com](https://portal.office.com) y después inicie sesión con el nombre de la cuenta Usuario 3 y la nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="86b87-148">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="86b87-149">Debe ver la página **principal de Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="86b87-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="86b87-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="86b87-150">Next step</span></span>

<span data-ttu-id="86b87-151">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="86b87-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="86b87-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="86b87-152">See also</span></span>

[<span data-ttu-id="86b87-153">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="86b87-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="86b87-154">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="86b87-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="86b87-155">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="86b87-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
