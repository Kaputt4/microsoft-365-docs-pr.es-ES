---
title: Autenticación multifactor de Microsoft 365 para entorno de prueba empresarial
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
- seo-marvel-apr2020
description: Configure la autenticación multifactor mediante mensajes de texto enviados a un teléfono inteligente en su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923761"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2b096-103">Autenticación multifactor para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2b096-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2b096-104">*Esta guía del laboratorio de pruebas se puede usar para entornos de prueba de Microsoft 365 para empresas y office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2b096-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2b096-105">Para obtener un nivel adicional de seguridad para iniciar sesión en Microsoft 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su suscripción, puede habilitar la autenticación multifactor de Azure AD, que requiere algo más que un nombre de usuario y una contraseña para comprobar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="2b096-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="2b096-106">Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de verificación enviado en un mensaje de texto o comprobar la autenticación con una aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="2b096-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="2b096-107">Solo pueden iniciar sesión después de que se cumple este segundo factor de autenticación.</span><span class="sxs-lookup"><span data-stu-id="2b096-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="2b096-108">En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="2b096-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="2b096-109">Configurar la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 para empresas implica dos fases y una tercera fase opcional:</span><span class="sxs-lookup"><span data-stu-id="2b096-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="2b096-110">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2b096-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="2b096-111">Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2</span><span class="sxs-lookup"><span data-stu-id="2b096-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="2b096-112">Fase 3: Habilitar y probar la autenticación multifactor con una directiva de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="2b096-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="2b096-114">Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para](../downloads/Microsoft365EnterpriseTLGStack.pdf)enterprise Test Lab Guide Stack .</span><span class="sxs-lookup"><span data-stu-id="2b096-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2b096-115">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2b096-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2b096-116">Si solo desea probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="2b096-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2b096-117">Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2b096-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b096-118">Probar la autenticación multifactor no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="2b096-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="2b096-119">Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="2b096-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="2b096-120">Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2</span><span class="sxs-lookup"><span data-stu-id="2b096-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="2b096-121">Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:</span><span class="sxs-lookup"><span data-stu-id="2b096-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="2b096-122">Abra una instancia privada independiente del explorador, vaya al Centro de administración de Microsoft 365 ( ) y, a continuación, inicie sesión [https://portal.microsoft.com](https://portal.microsoft.com) con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2b096-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="2b096-123">En la navegación izquierda, seleccione **Usuarios**  >  **usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="2b096-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="2b096-124">En el panel Usuarios activos, seleccione **Autenticación multifactor**.</span><span class="sxs-lookup"><span data-stu-id="2b096-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="2b096-125">En la lista, seleccione la **cuenta usuario 2.**</span><span class="sxs-lookup"><span data-stu-id="2b096-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="2b096-126">En la **sección Usuario 2,** en **Pasos rápidos,** seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="2b096-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="2b096-127">En el **cuadro de diálogo Acerca de cómo habilitar la autenticación multifactor,** seleccione Habilitar **autenticación multifactor**.</span><span class="sxs-lookup"><span data-stu-id="2b096-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="2b096-128">En el **cuadro de diálogo** Actualizaciones correctas, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2b096-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="2b096-129">En la pestaña Centro de administración de **Microsoft 365,** seleccione el icono de cuenta de usuario en la parte superior derecha y, a continuación, **seleccione Cerrar sesión.**</span><span class="sxs-lookup"><span data-stu-id="2b096-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="2b096-130">Cierre la instancia del explorador.</span><span class="sxs-lookup"><span data-stu-id="2b096-130">Close your browser instance.</span></span>
   
<span data-ttu-id="2b096-131">Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b096-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="2b096-132">Abra una nueva instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="2b096-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="2b096-133">Vaya al Centro [de administración de Microsoft 365](https://admin.microsoft.com) e inicie sesión con el nombre de cuenta y la contraseña del usuario 2.</span><span class="sxs-lookup"><span data-stu-id="2b096-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="2b096-134">Después de iniciar sesión, se le pedirá que configure la cuenta para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2b096-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="2b096-135">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b096-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="2b096-136">En la página **Comprobación de seguridad adicional**: </span><span class="sxs-lookup"><span data-stu-id="2b096-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="2b096-137">Seleccione el país o región.</span><span class="sxs-lookup"><span data-stu-id="2b096-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="2b096-138">Escriba el número de teléfono del teléfono inteligente que recibirá mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="2b096-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="2b096-139">En **Método**, seleccione **Enviarme un código por mensaje de texto**.</span><span class="sxs-lookup"><span data-stu-id="2b096-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="2b096-140">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b096-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="2b096-141">Escriba el código de verificación del mensaje de texto recibido en su teléfono inteligente y, a continuación, seleccione **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="2b096-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="2b096-142">En la **página Paso 3: Mantener las aplicaciones existentes,** seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="2b096-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="2b096-143">Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña.</span><span class="sxs-lookup"><span data-stu-id="2b096-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="2b096-144">Escriba la contraseña original y una nueva contraseña dos veces y, a continuación, **seleccione Actualizar contraseña e iniciar sesión.**</span><span class="sxs-lookup"><span data-stu-id="2b096-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="2b096-145">Anote la contraseña nueva en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="2b096-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="2b096-146">Debería ver el Portal de Office para el usuario 2 en **la Microsoft Office inicio** del explorador.</span><span class="sxs-lookup"><span data-stu-id="2b096-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="2b096-147">Fase 3: Habilitar y probar la autenticación multifactor con una directiva de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="2b096-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="2b096-148">*Esta fase solo se puede usar para un entorno de prueba de Microsoft 365 para empresas.*</span><span class="sxs-lookup"><span data-stu-id="2b096-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="2b096-149">En esta fase, se habilita la autenticación multifactor para la cuenta de usuario 3 mediante un grupo y una directiva de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="2b096-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="2b096-150">A continuación, cree un nuevo grupo denominado MFAUsers y agregue la cuenta usuario 3 a él.</span><span class="sxs-lookup"><span data-stu-id="2b096-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="2b096-151">En la pestaña Centro de administración de **Microsoft 365,** seleccione **Grupos** en la navegación izquierda y, a continuación, **seleccione Grupos**.</span><span class="sxs-lookup"><span data-stu-id="2b096-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="2b096-152">Seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="2b096-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="2b096-153">En el **panel Elegir un tipo de grupo,** seleccione **Seguridad** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b096-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="2b096-154">En el **panel Configurar los conceptos** básicos, seleccione **Crear grupo** y, a continuación, **seleccione Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2b096-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="2b096-155">En el **panel Revisar y terminar de agregar grupo,** escriba **MFAUsers** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b096-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="2b096-156">En la lista de grupos, seleccione el **grupo MFAUsers.**</span><span class="sxs-lookup"><span data-stu-id="2b096-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="2b096-157">En el **panel MFAUsers,** seleccione **Miembros** y, a continuación, **seleccione Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="2b096-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="2b096-158">En el **panel MFAUsers,** seleccione **Agregar miembros**, seleccione la cuenta usuario **3** y, a continuación, **seleccione Guardar**  >  **cerrar**  >  **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2b096-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="2b096-159">A continuación, cree una directiva de acceso condicional para requerir la autenticación multifactor para los miembros del grupo MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="2b096-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="2b096-160">En una nueva pestaña del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="2b096-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="2b096-161">Seleccione **Azure Active Directory**  >  **Security** Conditional  >  **Access**.</span><span class="sxs-lookup"><span data-stu-id="2b096-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="2b096-162">En el **panel Acceso condicional: directivas,** seleccione **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="2b096-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="2b096-163">En el **panel Nuevo,** escriba **MFA para cuentas de usuario** en el **cuadro** Nombre.</span><span class="sxs-lookup"><span data-stu-id="2b096-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="2b096-164">En la **sección Asignaciones,** seleccione **Usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="2b096-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="2b096-165">En la **pestaña Incluir** del panel Usuarios **y grupos,** seleccione **Seleccionar usuarios y grupos** Usuarios  >  **y grupos**  >  **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="2b096-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="2b096-166">En el **panel Seleccionar,** seleccione el grupo **MFAUsers** y, a continuación, **seleccione Seleccionar**  >  **listo**.</span><span class="sxs-lookup"><span data-stu-id="2b096-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="2b096-167">En la **sección Controles de acceso** del panel **Nuevo,** seleccione **Conceder**.</span><span class="sxs-lookup"><span data-stu-id="2b096-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="2b096-168">En el **panel Conceder,** seleccione **Requerir autenticación multifactor** y, a continuación, **seleccione Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="2b096-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="2b096-169">En el **panel Nuevo,** seleccione **Activar para** **Habilitar directiva** y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="2b096-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="2b096-170">Cierre las **pestañas Azure Portal** y Centro de administración de **Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="2b096-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="2b096-171">Para probar esta directiva, cerrar sesión e iniciar sesión con la cuenta usuario 3.</span><span class="sxs-lookup"><span data-stu-id="2b096-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="2b096-172">Se le pedirá que configure MFA.</span><span class="sxs-lookup"><span data-stu-id="2b096-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="2b096-173">Esto demuestra que se está aplicando la directiva MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="2b096-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="2b096-174">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2b096-174">Next step</span></span>

<span data-ttu-id="2b096-175">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="2b096-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b096-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b096-176">See also</span></span>

[<span data-ttu-id="2b096-177">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="2b096-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="2b096-178">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2b096-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2b096-179">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2b096-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2b096-180">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2b096-180">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)