---
title: Guías del laboratorio de pruebas de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/04/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Use estas guías del laboratorio de pruebas para configurar la demostración, prueba de concepto y entornos de desarrollo y prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 2f6fd8c17096c9c25a0f1af886894e68d33e939d
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672576"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="05ae5-103">Guías del laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="05ae5-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="05ae5-104">*Estas aplican tanto para Microsoft 365 Enterprise como para Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="05ae5-104">*This applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="05ae5-p101">Las Guías del laboratorio de pruebas (TLG) le ayudan a obtener información rápidamente sobre productos de Microsoft. Proporcionan instrucciones prescriptivas para configurar entornos de pruebas representativos pero simplificados. Puede usar estos entornos para la demostración, la personalización o la creación de pruebas de concepto complejas durante el tiempo que dure una suscripción de prueba o de pago.</span><span class="sxs-lookup"><span data-stu-id="05ae5-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="05ae5-p102">Las TLG están diseñadas para ser modulares. Se desarrollan entre sí para crear varias configuraciones que se adapten a sus necesidades de configuración de aprendizaje o de prueba. La experiencia práctica "Lo diseñé yo mismo y funciona" le ayudará a comprender los requisitos de implementación de un nuevo producto o escenario para que pueda planear mejor su hospedaje en producción.</span><span class="sxs-lookup"><span data-stu-id="05ae5-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="05ae5-111">Las TLG también le permiten crear entornos representativos para desarrollo y prueba de aplicaciones, también conocidos como entornos de desarrollo y prueba.</span><span class="sxs-lookup"><span data-stu-id="05ae5-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="05ae5-113">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="05ae5-113">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="05ae5-114">[![Pila de guías de laboratorio de pruebas de Microsoft 365 Enterprise](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="05ae5-114">[![The Microsoft 365 Enterprise Test Lab Guide stack](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="05ae5-115">Configuración básica</span><span class="sxs-lookup"><span data-stu-id="05ae5-115">Base configuration</span></span>

<span data-ttu-id="05ae5-p103">Primero debe crear un entorno de prueba para [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) que incluya Office 365 E5, Enterprise Mobility + Security (EMS) E5 y Windows 10 Enterprise. Puede crear dos tipos distintos de configuraciones básicas:</span><span class="sxs-lookup"><span data-stu-id="05ae5-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="05ae5-118">Use la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md) si quiere configurar y demostrar las características y funciones de Microsoft 365 Enterprise solo en un entorno de nube, que no incluye ningún componente local.</span><span class="sxs-lookup"><span data-stu-id="05ae5-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="05ae5-119">Use la [configuración básica de empresa simulada](simulated-ent-base-configuration-microsoft-365-enterprise.md) para configurar y demostrar las características y funciones de Microsoft 365 Enterprise en un entorno híbrido de nube, que use componentes locales como un dominio Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="05ae5-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="05ae5-120">También puede crear entornos de prueba para Office 365 E5 al no agregar la licencia de Microsoft 365 E5 a su prueba o entorno de prueba de producción.</span><span class="sxs-lookup"><span data-stu-id="05ae5-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="05ae5-121">Identidad</span><span class="sxs-lookup"><span data-stu-id="05ae5-121">Identity</span></span>

<span data-ttu-id="05ae5-122">Para mostrar características y funciones relacionadas con identidades, vea:</span><span class="sxs-lookup"><span data-stu-id="05ae5-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="05ae5-123">Sincronización de hash de contraseñas</span><span class="sxs-lookup"><span data-stu-id="05ae5-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="05ae5-124">Habilite y pruebe la sincronización de directorios basada en hash de contraseñas desde un controlador de dominio AD DS.</span><span class="sxs-lookup"><span data-stu-id="05ae5-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="05ae5-125">Autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="05ae5-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="05ae5-126">Habilite y pruebe la autenticación de paso a un controlador de dominio AD DS.</span><span class="sxs-lookup"><span data-stu-id="05ae5-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="05ae5-127">Inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="05ae5-127">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="05ae5-128">Habilite y pruebe Azure AD Seamless Single Sign-on (SSO) con un controlador de dominio AD DS.</span><span class="sxs-lookup"><span data-stu-id="05ae5-128">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="05ae5-129">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="05ae5-129">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="05ae5-130">Habilite y pruebe la autenticación multifactor basada en teléfono inteligente para una cuenta de usuario determinada.</span><span class="sxs-lookup"><span data-stu-id="05ae5-130">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="05ae5-131">Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="05ae5-131">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="05ae5-132">Bloquear sus cuentas de administrador global con directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="05ae5-132">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="05ae5-133">Reescritura de contraseña</span><span class="sxs-lookup"><span data-stu-id="05ae5-133">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="05ae5-134">Usar una escritura diferida de contraseñas para cambiar la contraseña de su cuenta de usuario de AD DS de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="05ae5-134">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="05ae5-135">Restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="05ae5-135">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="05ae5-136">Use el restablecimiento de contraseñas de autoservicio (SSPR) para restablecer su contraseña.</span><span class="sxs-lookup"><span data-stu-id="05ae5-136">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="05ae5-137">Licencias automáticas y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="05ae5-137">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="05ae5-138">Haga que administrar nuevas cuentas sea más fácil que nunca con licencias automáticas y pertenencia a grupos dinámica.</span><span class="sxs-lookup"><span data-stu-id="05ae5-138">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="05ae5-139">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="05ae5-139">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="05ae5-140">Examine sus cuentas actuales de usuarios en busca de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="05ae5-140">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="05ae5-141">Acceso de dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="05ae5-141">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="05ae5-142">Crear un entorno para probar la identidad recomendada y configuraciones de acceso de dispositivo y directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="05ae5-142">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="05ae5-143">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="05ae5-143">Mobile device management</span></span>

<span data-ttu-id="05ae5-144">Para mostrar funcionalidades y características relacionadas con la administración de dispositivos móviles, vea:</span><span class="sxs-lookup"><span data-stu-id="05ae5-144">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="05ae5-145">Directivas de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="05ae5-145">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="05ae5-146">Cree un grupo de usuarios y una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="05ae5-146">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="05ae5-147">Inscribir dispositivos iOS y Android</span><span class="sxs-lookup"><span data-stu-id="05ae5-147">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="05ae5-148">Inscriba los dispositivos Android o iOS y adminístrelos de forma remota.</span><span class="sxs-lookup"><span data-stu-id="05ae5-148">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="05ae5-149">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="05ae5-149">Information protection</span></span>

<span data-ttu-id="05ae5-150">Para demostrar características y funciones de la información relacionadas con la protección, vea:</span><span class="sxs-lookup"><span data-stu-id="05ae5-150">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="05ae5-151">Mayor seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="05ae5-151">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="05ae5-152">Configure las opciones para aumentar la seguridad de Office 365 y analizar las herramientas de seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="05ae5-152">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="05ae5-153">Clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="05ae5-153">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="05ae5-154">Configure y aplique etiquetas de Office 365 a un documento en un sitio de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="05ae5-154">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="05ae5-155">Administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="05ae5-155">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="05ae5-156">Configure la administración del acceso con privilegios para habilitar el acceso puntual a tareas elevadas o con privilegios en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="05ae5-156">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>


