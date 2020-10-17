---
title: Microsoft 365 para la autenticación multifactor del entorno de prueba de empresa
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
description: Configure multi-factor Authentication mediante mensajes de texto enviados a un smartphone en su Microsoft 365 para el entorno de prueba de la empresa.
ms.openlocfilehash: f41fe7ad933f85c4b44a1e90529a998651412191
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487145"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5e660-103">Autenticación multifactor para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5e660-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5e660-104">*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*</span><span class="sxs-lookup"><span data-stu-id="5e660-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="5e660-105">Para obtener un nivel adicional de seguridad para iniciar sesión en Microsoft 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su suscripción, puede habilitar la autenticación multifactor de Azure, que requiere más que un nombre de usuario y una contraseña para comprobar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="5e660-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="5e660-106">Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de comprobación enviado en un mensaje de texto o verificar la autenticación con una aplicación en su smartphone, después de escribir correctamente sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="5e660-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="5e660-107">Solo pueden iniciar sesión después de que se cumpla este segundo factor de autenticación.</span><span class="sxs-lookup"><span data-stu-id="5e660-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="5e660-108">En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="5e660-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="5e660-109">La configuración de la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 para empresas implica dos fases y una tercera fase opcional:</span><span class="sxs-lookup"><span data-stu-id="5e660-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="5e660-110">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5e660-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="5e660-111">Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2</span><span class="sxs-lookup"><span data-stu-id="5e660-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="5e660-112">Fase 3: habilitar y probar la autenticación multifactor con una directiva de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="5e660-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="5e660-114">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="5e660-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5e660-115">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5e660-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5e660-116">Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="5e660-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5e660-117">Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5e660-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e660-118">La comprobación de la autenticación multifactor no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5e660-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5e660-119">Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="5e660-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="5e660-120">Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2</span><span class="sxs-lookup"><span data-stu-id="5e660-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="5e660-121">Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:</span><span class="sxs-lookup"><span data-stu-id="5e660-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="5e660-122">Abra una instancia independiente y privada del explorador, vaya al centro de administración de Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) y, a continuación, inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5e660-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="5e660-123">En el panel de navegación izquierdo **, seleccione usuarios**  >  **activos**.</span><span class="sxs-lookup"><span data-stu-id="5e660-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="5e660-124">En el panel usuarios activos, seleccione **multi-factor Authentication**.</span><span class="sxs-lookup"><span data-stu-id="5e660-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="5e660-125">En la lista, seleccione la cuenta **usuario 2** .</span><span class="sxs-lookup"><span data-stu-id="5e660-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="5e660-126">En la sección **usuario 2** , en **pasos rápidos**, seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="5e660-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="5e660-127">En el cuadro de diálogo **acerca de la habilitación de autenticación multifactor** , seleccione **Habilitar multi-factor auth**.</span><span class="sxs-lookup"><span data-stu-id="5e660-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="5e660-128">En el cuadro de diálogo **actualizaciones correctas** , seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5e660-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="5e660-129">En la pestaña **centro de administración de 365 de Microsoft** , seleccione el icono de la cuenta de usuario en la esquina superior derecha y, después, seleccione **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="5e660-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="5e660-130">Cierre la instancia del explorador.</span><span class="sxs-lookup"><span data-stu-id="5e660-130">Close your browser instance.</span></span>
   
<span data-ttu-id="5e660-131">Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e660-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="5e660-132">Abra una nueva instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="5e660-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="5e660-133">Vaya al [centro de administración de 365 de Microsoft](https://admin.microsoft.com) y inicie sesión con el nombre de cuenta y la contraseña del usuario 2.</span><span class="sxs-lookup"><span data-stu-id="5e660-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="5e660-134">Después de iniciar sesión, se le pedirá que configure la cuenta para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5e660-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="5e660-135">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e660-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="5e660-136">En la página **Comprobación de seguridad adicional**: </span><span class="sxs-lookup"><span data-stu-id="5e660-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="5e660-137">Seleccione el país o región.</span><span class="sxs-lookup"><span data-stu-id="5e660-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="5e660-138">Escriba el número de teléfono del smartphone que recibirá los mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="5e660-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="5e660-139">En el **método**, seleccione **enviarme un código por mensaje de texto**.</span><span class="sxs-lookup"><span data-stu-id="5e660-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="5e660-140">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e660-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="5e660-141">Escriba el código de verificación del mensaje de texto que ha recibido en el smartphone y, después, seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="5e660-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="5e660-142">En la página **paso 3: conservar las aplicaciones existentes** , seleccione **listo**.</span><span class="sxs-lookup"><span data-stu-id="5e660-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="5e660-143">Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña.</span><span class="sxs-lookup"><span data-stu-id="5e660-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="5e660-144">Escriba la contraseña original y una nueva contraseña dos veces y, a continuación, seleccione **Actualizar contraseña e iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="5e660-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="5e660-145">Anote la contraseña nueva en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="5e660-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="5e660-146">Debe ver el portal de Office para el usuario 2 en la pestaña **Página principal de Microsoft Office** del explorador.</span><span class="sxs-lookup"><span data-stu-id="5e660-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="5e660-147">Fase 3: habilitar y probar la autenticación multifactor con una directiva de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="5e660-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="5e660-148">*Esta fase solo puede usarse para un entorno de prueba de Microsoft 365 para empresas.*</span><span class="sxs-lookup"><span data-stu-id="5e660-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="5e660-149">En esta fase, habilitará la autenticación multifactor para la cuenta usuario 3 con un grupo y una directiva de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="5e660-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="5e660-150">A continuación, cree un nuevo grupo denominado MFAUsers y agréguele la cuenta de usuario 3.</span><span class="sxs-lookup"><span data-stu-id="5e660-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="5e660-151">En la pestaña **centro de administración de 365 de Microsoft** , seleccione **grupos** en el panel de navegación izquierdo y, a continuación, seleccione **grupos**.</span><span class="sxs-lookup"><span data-stu-id="5e660-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="5e660-152">Seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="5e660-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="5e660-153">En el panel **elegir un tipo de grupo** , seleccione **seguridad**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e660-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="5e660-154">En el panel **configurar conceptos básicos** , seleccione **Crear grupo**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5e660-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="5e660-155">En el panel **revisar y finalizar agregar grupo** , escriba **MFAUsers**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e660-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="5e660-156">En la lista de grupos, seleccione el grupo **MFAUsers** .</span><span class="sxs-lookup"><span data-stu-id="5e660-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="5e660-157">En el panel **MFAUsers** , seleccione **miembros**y, a continuación, seleccione **Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="5e660-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="5e660-158">En el panel **MFAUsers** , seleccione **Agregar miembros**, seleccione la cuenta de **usuario 3** y, a continuación, seleccione **Guardar**  >  **cerrar**  >  **Close**.</span><span class="sxs-lookup"><span data-stu-id="5e660-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="5e660-159">A continuación, cree una directiva de acceso condicional para exigir la autenticación multifactor para los miembros del grupo MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="5e660-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="5e660-160">En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="5e660-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="5e660-161">Seleccione **Azure Active Directory**  >  **Security**  >  **acceso condicional**de seguridad de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5e660-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="5e660-162">En el panel **acceso condicional-directivas** , seleccione **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="5e660-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="5e660-163">En el panel **nuevo** , escriba **MFA para las cuentas de usuario** en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="5e660-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="5e660-164">En la sección **asignaciones** , seleccione **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="5e660-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="5e660-165">En la ficha **incluir** del panel **usuarios y grupos** , seleccione **Seleccionar usuarios y**grupos, seleccione usuarios y  >  **grupos**  >  **Select**.</span><span class="sxs-lookup"><span data-stu-id="5e660-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="5e660-166">En el panel de **selección** , seleccione el grupo **MFAUsers** y, a continuación, seleccione **seleccionar**  >  **listo**.</span><span class="sxs-lookup"><span data-stu-id="5e660-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="5e660-167">En la sección **controles de acceso** del panel **nuevo** , seleccione **conceder**.</span><span class="sxs-lookup"><span data-stu-id="5e660-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="5e660-168">En el panel **conceder** , seleccione **requerir autenticación multifactor**y, a continuación, seleccione **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="5e660-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="5e660-169">En el panel **nuevo** , seleccione **activado** para **Habilitar Directiva**y, a continuación, seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="5e660-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="5e660-170">Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="5e660-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="5e660-171">Para probar esta Directiva, cierre sesión e inicie sesión con la cuenta de usuario 3.</span><span class="sxs-lookup"><span data-stu-id="5e660-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="5e660-172">Se le pedirá que configure la MFA.</span><span class="sxs-lookup"><span data-stu-id="5e660-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="5e660-173">Esto demuestra que se está aplicando la Directiva MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="5e660-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="5e660-174">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5e660-174">Next step</span></span>

<span data-ttu-id="5e660-175">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="5e660-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e660-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e660-176">See also</span></span>

[<span data-ttu-id="5e660-177">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="5e660-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5e660-178">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5e660-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5e660-179">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5e660-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5e660-180">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5e660-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
