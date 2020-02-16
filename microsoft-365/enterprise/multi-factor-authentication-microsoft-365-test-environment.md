---
title: Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure multi-factor Authentication mediante mensajes de texto enviados a un smartphone en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: ea2041a463b224781df101251dab0f4d9f0e8753
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066737"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1af39-103">Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af39-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1af39-104">*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1af39-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1af39-105">Para obtener un nivel adicional de seguridad para iniciar sesión en Microsoft 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su suscripción, puede habilitar la autenticación multifactor de Azure, que requiere más que un nombre de usuario y una contraseña para comprobar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="1af39-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="1af39-106">Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de comprobación enviado en un mensaje de texto o especificar una contraseña de aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="1af39-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="1af39-107">Pueden iniciar sesión solo después de que se haya cumplido este segundo factor de autenticación.</span><span class="sxs-lookup"><span data-stu-id="1af39-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="1af39-108">En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="1af39-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="1af39-109">Hay dos fases para configurar la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="1af39-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="1af39-110">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1af39-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="1af39-111">Habilitar y probar la autenticación multifactor para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="1af39-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="1af39-112">Habilitar y probar la autenticación multifactor con una directiva de acceso condicional (opcional).</span><span class="sxs-lookup"><span data-stu-id="1af39-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="1af39-114">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1af39-114">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1af39-115">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af39-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1af39-116">Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1af39-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1af39-117">Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1af39-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1af39-118">La comprobación de la autenticación multifactor no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1af39-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1af39-119">Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="1af39-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="1af39-120">Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2</span><span class="sxs-lookup"><span data-stu-id="1af39-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="1af39-121">Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:</span><span class="sxs-lookup"><span data-stu-id="1af39-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="1af39-122">Abra una instancia independiente y privada del explorador, vaya al centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)) y, a continuación, inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1af39-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="1af39-123">En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="1af39-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="1af39-124">En el panel usuarios activos, haga clic en **multi-factor Authentication**.</span><span class="sxs-lookup"><span data-stu-id="1af39-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="1af39-125">En la lista, seleccione la cuenta **usuario 2** .</span><span class="sxs-lookup"><span data-stu-id="1af39-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="1af39-126">En la sección **Usuario 2**, en **Pasos rápidos**, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="1af39-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="1af39-127">En el cuadro de diálogo **Acerca de la habilitación de autenticación multifactor**, haga clic en **Habilitar Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="1af39-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="1af39-128">En el cuadro de diálogo **actualizaciones correctas** , haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1af39-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="1af39-129">En la pestaña **centro de administración de 365 de Microsoft** , haga clic en el icono de la cuenta de usuario en la esquina superior derecha y, después, en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="1af39-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="1af39-130">Cierre la instancia del explorador.</span><span class="sxs-lookup"><span data-stu-id="1af39-130">Close your browser instance.</span></span>
   
<span data-ttu-id="1af39-131">Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1af39-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="1af39-132">Abra una nueva instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="1af39-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="1af39-133">Vaya al portal de Office 365 ([https://portal.office.com](https://portal.office.com)) e inicie sesión con el nombre de cuenta y la contraseña del usuario 2.</span><span class="sxs-lookup"><span data-stu-id="1af39-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="1af39-134">Después de iniciar sesión, se le pedirá que configure la cuenta para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1af39-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="1af39-135">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1af39-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="1af39-136">En la página **Comprobación de seguridad adicional**: </span><span class="sxs-lookup"><span data-stu-id="1af39-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="1af39-137">Seleccione el país o región.</span><span class="sxs-lookup"><span data-stu-id="1af39-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="1af39-138">Escriba el número de teléfono del smartphone que va a recibir los mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="1af39-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="1af39-139">En **método**, haga clic en **enviarme un código por mensaje de texto**.</span><span class="sxs-lookup"><span data-stu-id="1af39-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="1af39-140">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1af39-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="1af39-141">Escriba el código de comprobación incluido en el mensaje de texto que ha recibido en el smartphone y, después, haga clic en **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="1af39-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="1af39-142">En la página **Step 3: Keep your existing applications** (Paso 3: conservar las aplicaciones existentes), guarde en una ubicación segura la contraseña de aplicación que se muestra para la cuenta Usuario 2 y, después, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="1af39-142">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="1af39-p104">Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba la contraseña original y la contraseña nueva dos veces y, después, haga clic en **Actualizar contraseña e iniciar sesión**. Anote la contraseña nueva en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="1af39-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="1af39-146">Debe ver el portal de Office para el usuario 2 en la pestaña **Página principal de Microsoft Office** del explorador.</span><span class="sxs-lookup"><span data-stu-id="1af39-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="1af39-147">Fase 3: habilitar y probar la autenticación multifactor con una directiva de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="1af39-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="1af39-148">*Esta fase solo se puede usar para un entorno de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1af39-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="1af39-149">En esta fase, se habilita la autenticación multifactor para la cuenta de usuario 3 con un grupo y una directiva de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="1af39-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="1af39-150">A continuación, cree un nuevo grupo denominado MFAUsers y agréguele la cuenta de usuario 3.</span><span class="sxs-lookup"><span data-stu-id="1af39-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="1af39-151">En la pestaña **centro de administración de 365 de Microsoft** , haga clic en **grupos** en el panel de navegación izquierdo y, después, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="1af39-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="1af39-152">Haga clic en **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="1af39-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="1af39-153">En el panel **elegir un tipo de grupo** , seleccione **seguridad**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1af39-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="1af39-154">En el panel **configurar conceptos básicos** , haga clic en **Crear grupo**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1af39-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="1af39-155">En el panel **revisar y finalizar agregar grupo** , escriba **MFAUsers**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1af39-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="1af39-156">En la lista de grupos, haga clic en el grupo **MFAUsers** .</span><span class="sxs-lookup"><span data-stu-id="1af39-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="1af39-157">En el panel **MFAUsers** , haga clic en **miembros**y, a continuación, haga clic en **Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="1af39-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="1af39-158">En el panel de **MFAUsers** , haga clic en **Agregar miembros**, seleccione la cuenta de **usuario 3** y, a continuación, haga clic en **Guardar > cerrar > cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1af39-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="1af39-159">A continuación, cree una directiva de acceso condicional para exigir la autenticación multifactor para los miembros del grupo MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="1af39-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="1af39-160">En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="1af39-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="1af39-161">Haga clic en **Azure active directory > Security > el acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="1af39-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="1af39-162">En el panel **acceso condicional-directivas** , haga clic en **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="1af39-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="1af39-163">En el panel **nuevo** , escriba **MFA para las cuentas de usuario** en **nombre**.</span><span class="sxs-lookup"><span data-stu-id="1af39-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="1af39-164">En la sección **asignaciones** , haga clic en **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="1af39-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="1af39-165">En la ficha **incluir** del panel **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos > usuarios y grupos > seleccione**.</span><span class="sxs-lookup"><span data-stu-id="1af39-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="1af39-166">En el panel de **selección** , haga clic en el grupo **MFAUsers** y, a continuación, haga clic en **seleccionar > listo**.</span><span class="sxs-lookup"><span data-stu-id="1af39-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="1af39-167">En la sección **controles de acceso** del panel **nuevo** , haga clic en **conceder**.</span><span class="sxs-lookup"><span data-stu-id="1af39-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="1af39-168">En el panel **conceder** , haga clic en **requerir multi-factor Authentication**y, a continuación, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1af39-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="1af39-169">En el panel **nuevo** , haga clic **en** **Habilitar Directiva**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="1af39-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="1af39-170">Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="1af39-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="1af39-171">Para probar esta Directiva, cierre sesión e inicie sesión con la cuenta de usuario 3.</span><span class="sxs-lookup"><span data-stu-id="1af39-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="1af39-172">Se le pedirá que configure la MFA.</span><span class="sxs-lookup"><span data-stu-id="1af39-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="1af39-173">Esto demuestra que se está aplicando la Directiva MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="1af39-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="1af39-174">Consulte el paso [configurar la autenticación multifactor](identity-secure-user-sign-ins.md#identity-mfa) en la fase de identidad para obtener información y vínculos para implementar la autenticación multifactor en producción.</span><span class="sxs-lookup"><span data-stu-id="1af39-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="1af39-175">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="1af39-175">Next step</span></span>

<span data-ttu-id="1af39-176">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="1af39-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1af39-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="1af39-177">See also</span></span>

[<span data-ttu-id="1af39-178">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="1af39-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="1af39-179">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af39-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1af39-180">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af39-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1af39-181">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af39-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
