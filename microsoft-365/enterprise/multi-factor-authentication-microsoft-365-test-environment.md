---
title: Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure multi-factor Authentication mediante mensajes de texto enviados a un smartphone en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 8e202936451030718c0c86601c2c621c50f78e1a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291145"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3c553-103">Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c553-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3c553-104">Para obtener un nivel adicional de seguridad para iniciar sesión en Office 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su organización, puede habilitar la autenticación multifactor de Azure, que requiere más que un nombre de usuario y una contraseña para comprobar una cuenta.</span><span class="sxs-lookup"><span data-stu-id="3c553-104">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="3c553-105">Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de comprobación enviado en un mensaje de texto o especificar una contraseña de aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="3c553-105">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="3c553-106">Pueden iniciar sesión solo después de que se haya cumplido este segundo factor de autenticación.</span><span class="sxs-lookup"><span data-stu-id="3c553-106">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="3c553-107">En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta específica.</span><span class="sxs-lookup"><span data-stu-id="3c553-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="3c553-108">Hay dos fases para configurar la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="3c553-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="3c553-109">Cree el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3c553-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="3c553-110">Habilitar y probar la autenticación multifactor para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="3c553-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3c553-112">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3c553-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3c553-113">Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c553-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3c553-114">Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="3c553-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3c553-115">Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3c553-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c553-116">La comprobación de la autenticación multifactor no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="3c553-116">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3c553-117">Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="3c553-117">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="3c553-118">Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2</span><span class="sxs-lookup"><span data-stu-id="3c553-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="3c553-119">Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:</span><span class="sxs-lookup"><span data-stu-id="3c553-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="3c553-120">Abra una instancia independiente y privada del explorador, vaya al portal de Office ([https://office.com](https://office.com)) y, a continuación, inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="3c553-120">Open a separate, private instance of your browser, go to the Office portal ([https://office.com](https://office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="3c553-121">En la página principal del portal, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="3c553-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="3c553-122">En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="3c553-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="3c553-123">En el panel usuarios activos, haga clic en **más _GT_ multi-factor Authentication Setup**.</span><span class="sxs-lookup"><span data-stu-id="3c553-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="3c553-124">En la lista, seleccione la cuenta **usuario 2** .</span><span class="sxs-lookup"><span data-stu-id="3c553-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="3c553-125">En la sección **Usuario 2**, en **Pasos rápidos**, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="3c553-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="3c553-126">En el cuadro de diálogo **Acerca de la habilitación de autenticación multifactor**, haga clic en **Habilitar Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="3c553-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="3c553-127">En el cuadro de diálogo **actualizaciones correctas** , haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="3c553-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="3c553-128">En la pestaña **Página principal de Microsoft Office**, haga clic en el icono de cuenta de usuario en la esquina superior derecha y, después, en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="3c553-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="3c553-129">Cierre la instancia del explorador.</span><span class="sxs-lookup"><span data-stu-id="3c553-129">Close your browser instance.</span></span>
   
<span data-ttu-id="3c553-130">Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3c553-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="3c553-131">Abra una nueva instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="3c553-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="3c553-132">Vaya al portal de Office ([https://office.com](https://office.com)) e inicie sesión con la cuenta usuario 2 (usuario2 @\<Organization name>. en Microsoft. com) y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="3c553-132">Go to the Office portal ([https://office.com](https://office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="3c553-133">Después de iniciar sesión, se le pedirá que configure la cuenta para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3c553-133">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="3c553-134">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c553-134">Click **Next**.</span></span>
    
4. <span data-ttu-id="3c553-135">En la página **Comprobación de seguridad adicional**: </span><span class="sxs-lookup"><span data-stu-id="3c553-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="3c553-136">Seleccione el país o región.</span><span class="sxs-lookup"><span data-stu-id="3c553-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="3c553-137">Escriba el número de teléfono del smartphone que va a recibir los mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="3c553-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="3c553-138">En **método**, haga clic en **enviarme un código por mensaje de texto**.</span><span class="sxs-lookup"><span data-stu-id="3c553-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="3c553-139">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c553-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="3c553-140">Escriba el código de comprobación incluido en el mensaje de texto que ha recibido en el smartphone y, después, haga clic en **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="3c553-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="3c553-141">En la página **Step 3: Keep your existing applications** (Paso 3: conservar las aplicaciones existentes), guarde en una ubicación segura la contraseña de aplicación que se muestra para la cuenta Usuario 2 y, después, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="3c553-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="3c553-p104">Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba la contraseña original y la contraseña nueva dos veces y, después, haga clic en **Actualizar contraseña e iniciar sesión**. Anote la contraseña nueva en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="3c553-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="3c553-145">Debe ver el portal de Office para el usuario 2 en la pestaña **Página principal de Microsoft Office** del explorador.</span><span class="sxs-lookup"><span data-stu-id="3c553-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="3c553-146">Consulte el paso [configurar la autenticación multifactor](identity-multi-factor-authentication.md#identity-mfa) en la fase de identidad para obtener información y vínculos para implementar la autenticación multifactor en producción.</span><span class="sxs-lookup"><span data-stu-id="3c553-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="3c553-147">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="3c553-147">Next step</span></span>

<span data-ttu-id="3c553-148">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="3c553-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c553-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c553-149">See also</span></span>

[<span data-ttu-id="3c553-150">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="3c553-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="3c553-151">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c553-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3c553-152">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c553-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3c553-153">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3c553-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
