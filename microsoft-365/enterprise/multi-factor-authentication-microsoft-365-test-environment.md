---
title: Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure multi-factor Authentication mediante mensajes de texto enviados a un smartphone en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 6c004f1ac093a997c263162ab8c945366f6361bd
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639910"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="db5b0-103">Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db5b0-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="db5b0-104">Para obtener un nivel adicional de seguridad para iniciar sesión en Office 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su organización, puede habilitar la autenticación multifactor de Azure, que requiere más que un nombre de usuario y una contraseña para comprobar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="db5b0-104">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="db5b0-105">Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de comprobación enviado en un mensaje de texto o especificar una contraseña de aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="db5b0-105">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="db5b0-106">Pueden iniciar sesión solo después de que se haya cumplido este segundo factor de autenticación.</span><span class="sxs-lookup"><span data-stu-id="db5b0-106">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="db5b0-107">En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta específica.</span><span class="sxs-lookup"><span data-stu-id="db5b0-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="db5b0-108">Hay dos fases para configurar la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="db5b0-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="db5b0-109">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="db5b0-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="db5b0-110">Habilitar y probar la autenticación multifactor para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="db5b0-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="db5b0-112">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="db5b0-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="db5b0-113">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db5b0-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="db5b0-114">Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="db5b0-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="db5b0-115">Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="db5b0-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="db5b0-116">La comprobación de la autenticación multifactor no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="db5b0-116">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="db5b0-117">Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="db5b0-117">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="db5b0-118">Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2</span><span class="sxs-lookup"><span data-stu-id="db5b0-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="db5b0-119">Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:</span><span class="sxs-lookup"><span data-stu-id="db5b0-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="db5b0-120">Abra una instancia independiente y privada del explorador, vaya al centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)) y, a continuación, inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="db5b0-120">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="db5b0-121">En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-121">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="db5b0-122">En el panel usuarios activos, haga clic en **más > configuración de multi-factor Authentication**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-122">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
4. <span data-ttu-id="db5b0-123">En la lista, seleccione la cuenta **usuario 2** .</span><span class="sxs-lookup"><span data-stu-id="db5b0-123">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="db5b0-124">En la sección **Usuario 2**, en **Pasos rápidos**, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-124">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="db5b0-125">En el cuadro de diálogo **Acerca de la habilitación de autenticación multifactor**, haga clic en **Habilitar Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-125">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="db5b0-126">En el cuadro de diálogo **actualizaciones correctas** , haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-126">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="db5b0-127">En la pestaña **centro de administración de 365 de Microsoft** , haga clic en el icono de la cuenta de usuario en la esquina superior derecha y, después, en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-127">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="db5b0-128">Cierre la instancia del explorador.</span><span class="sxs-lookup"><span data-stu-id="db5b0-128">Close your browser instance.</span></span>
   
<span data-ttu-id="db5b0-129">Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="db5b0-129">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="db5b0-130">Abra una nueva instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="db5b0-130">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="db5b0-131">Vaya al portal de Office 365 ([https://portal.office.com](https://portal.office.com)) e inicie sesión con el nombre de cuenta y la contraseña del usuario 2.</span><span class="sxs-lookup"><span data-stu-id="db5b0-131">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="db5b0-132">Después de iniciar sesión, se le pedirá que configure la cuenta para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="db5b0-132">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="db5b0-133">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-133">Click **Next**.</span></span>
    
4. <span data-ttu-id="db5b0-134">En la página **Comprobación de seguridad adicional**: </span><span class="sxs-lookup"><span data-stu-id="db5b0-134">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="db5b0-135">Seleccione el país o región.</span><span class="sxs-lookup"><span data-stu-id="db5b0-135">Select your country or region.</span></span>
    
   - <span data-ttu-id="db5b0-136">Escriba el número de teléfono del smartphone que va a recibir los mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="db5b0-136">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="db5b0-137">En **método**, haga clic en **enviarme un código por mensaje de texto**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-137">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="db5b0-138">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-138">Click **Next**.</span></span>
    
6. <span data-ttu-id="db5b0-139">Escriba el código de comprobación incluido en el mensaje de texto que ha recibido en el smartphone y, después, haga clic en **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-139">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="db5b0-140">En la página **Step 3: Keep your existing applications** (Paso 3: conservar las aplicaciones existentes), guarde en una ubicación segura la contraseña de aplicación que se muestra para la cuenta Usuario 2 y, después, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="db5b0-140">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="db5b0-p104">Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba la contraseña original y la contraseña nueva dos veces y, después, haga clic en **Actualizar contraseña e iniciar sesión**. Anote la contraseña nueva en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="db5b0-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="db5b0-144">Debe ver el portal de Office para el usuario 2 en la pestaña **Página principal de Microsoft Office** del explorador.</span><span class="sxs-lookup"><span data-stu-id="db5b0-144">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="db5b0-145">Consulte el paso [configurar la autenticación multifactor](identity-secure-user-sign-ins.md#identity-mfa) en la fase de identidad para obtener información y vínculos para implementar la autenticación multifactor en producción.</span><span class="sxs-lookup"><span data-stu-id="db5b0-145">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="db5b0-146">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="db5b0-146">Next step</span></span>

<span data-ttu-id="db5b0-147">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="db5b0-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="db5b0-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="db5b0-148">See also</span></span>

[<span data-ttu-id="db5b0-149">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="db5b0-149">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="db5b0-150">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db5b0-150">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="db5b0-151">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db5b0-151">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="db5b0-152">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db5b0-152">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
