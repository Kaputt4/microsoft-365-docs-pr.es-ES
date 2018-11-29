---
title: Entorno de prueba de la autenticación multifactor para su empresa de 365 de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configuración de la autenticación multifactor mediante mensajes de texto enviados a un teléfono inteligente en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: aae493e79a197635b2e14fa7f238a3189ed695ae
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871161"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="436df-103">Entorno de prueba de la autenticación multifactor para su empresa de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="436df-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="436df-p101">Para obtener un nivel adicional de seguridad para iniciar sesión en Office 365 o cualquier servicio o aplicación que usa el inquilino de Azure AD para su organización, puede habilitar la autenticación multifactor Azure, lo cual requiere algo más que un nombre de usuario y una contraseña para comprobar un cuenta. Con la autenticación multifactor, los usuarios son necesarios para confirmar una llamada de teléfono, escriba un código de comprobación enviado en un mensaje de texto o especificar una contraseña de la aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas. Puede iniciar sesión sólo después de que se haya probado este segundo factor de autenticación.</span><span class="sxs-lookup"><span data-stu-id="436df-p101">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account. With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords. They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="436df-107">En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta específica.</span><span class="sxs-lookup"><span data-stu-id="436df-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="436df-108">Hay dos fases para configurar la autenticación multifactor para una cuenta en su entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="436df-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="436df-109">Crear el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="436df-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="436df-110">Habilitar y probar la autenticación multifactor para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="436df-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="436df-112">Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="436df-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="436df-113">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="436df-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="436df-114">Si desea probar la autenticación multifactor en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="436df-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="436df-115">Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="436df-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="436df-p102">Probar la autenticación multifactor no requiere que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar la autenticación multifactor y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="436df-p102">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="436df-118">Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2</span><span class="sxs-lookup"><span data-stu-id="436df-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="436df-119">Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:</span><span class="sxs-lookup"><span data-stu-id="436df-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="436df-120">Abra una sesión independiente, privada de su explorador, vaya al portal de Office 365 ([https://portal.office.com](https://portal.office.com)) y, a continuación, inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="436df-120">Open a separate, private instance of your browser, go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="436df-121">En la página principal del portal, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="436df-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="436df-122">En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="436df-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="436df-123">En el panel usuarios activos, haga clic en **más > el programa de instalación de la autenticación multifactor**.</span><span class="sxs-lookup"><span data-stu-id="436df-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="436df-124">En la lista, seleccione la cuenta de **usuario 2** .</span><span class="sxs-lookup"><span data-stu-id="436df-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="436df-125">En la sección **Usuario 2**, en **Pasos rápidos**, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="436df-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="436df-126">En el cuadro de diálogo **Acerca de la habilitación de autenticación multifactor**, haga clic en **Habilitar Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="436df-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="436df-127">En el cuadro de diálogo **actualiza correctamente** , haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="436df-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="436df-128">En la pestaña **Página principal de Microsoft Office**, haga clic en el icono de cuenta de usuario en la esquina superior derecha y, después, en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="436df-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="436df-129">Cierre la instancia del explorador.</span><span class="sxs-lookup"><span data-stu-id="436df-129">Close your browser instance.</span></span>
   
<span data-ttu-id="436df-130">Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="436df-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="436df-131">Abra una nueva instancia del explorador privada.</span><span class="sxs-lookup"><span data-stu-id="436df-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="436df-132">Vaya al portal de Office 365 ([https://portal.office.com](https://portal.office.com)) y el inicio de sesión con la cuenta de usuario 2 (user2 @\<nombre de la organización >. onmicrosoft.com) y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="436df-132">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="436df-p103">Después de iniciar sesión, se le pide para configurar la cuenta para obtener más información. Haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="436df-p103">After signing in, you are prompted to set up the account for more information. Click **Next**.</span></span>
    
4. <span data-ttu-id="436df-135">En la página **Comprobación de seguridad adicional**: </span><span class="sxs-lookup"><span data-stu-id="436df-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="436df-136">Seleccione el país o región.</span><span class="sxs-lookup"><span data-stu-id="436df-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="436df-137">Escriba el número de teléfono del smartphone que va a recibir los mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="436df-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="436df-138">En **método**, haga clic en **Enviarme un código por mensaje de texto**.</span><span class="sxs-lookup"><span data-stu-id="436df-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="436df-139">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="436df-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="436df-140">Escriba el código de comprobación incluido en el mensaje de texto que ha recibido en el smartphone y, después, haga clic en **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="436df-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="436df-141">En la página **Step 3: Keep your existing applications** (Paso 3: conservar las aplicaciones existentes), guarde en una ubicación segura la contraseña de aplicación que se muestra para la cuenta Usuario 2 y, después, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="436df-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="436df-p104">Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba la contraseña original y la contraseña nueva dos veces y, después, haga clic en **Actualizar contraseña e iniciar sesión**. Anote la contraseña nueva en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="436df-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="436df-145">Debería ver el portal de Office 365 para el usuario 2 en la ficha **Página principal de Microsoft Office** del explorador.</span><span class="sxs-lookup"><span data-stu-id="436df-145">You should see the Office 365 portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="436df-146">Consulte el paso [Configurar la autenticación multifactor](identity-multi-factor-authentication.md) en la fase de identidad de información y vínculos para implementar la autenticación multifactor en producción.</span><span class="sxs-lookup"><span data-stu-id="436df-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="436df-147">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="436df-147">Next step</span></span>

<span data-ttu-id="436df-148">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="436df-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="436df-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="436df-149">See also</span></span>

[<span data-ttu-id="436df-150">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="436df-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="436df-151">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="436df-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="436df-152">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="436df-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="436df-153">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="436df-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
