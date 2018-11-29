---
title: Guías del laboratorio de pruebas de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Use estas guías del laboratorio de pruebas para configurar la demostración, prueba de concepto y entornos de desarrollo y prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871659"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="2a4d3-103">Guías del laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2a4d3-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="2a4d3-p101">Las Guías del laboratorio de pruebas (TLG) le ayudan a obtener información rápidamente sobre productos de Microsoft. Proporcionan instrucciones prescriptivas para configurar entornos de pruebas representativos pero simplificados. Puede usar estos entornos para la demostración, la personalización o la creación de pruebas de concepto complejas durante el tiempo que dure una suscripción de prueba o de pago.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="2a4d3-p102">Las TLG están diseñadas para ser modulares. Se desarrollan entre sí para crear varias configuraciones que se adapten a sus necesidades de configuración de aprendizaje o de prueba. La experiencia práctica "Lo diseñé yo mismo y funciona" le ayudará a comprender los requisitos de implementación de un nuevo producto o escenario para que pueda planear mejor su hospedaje en producción.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="2a4d3-110">Las TLG también le permiten crear entornos representativos para desarrollo y prueba de aplicaciones, también conocidos como entornos de desarrollo y prueba.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="2a4d3-112">Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="2a4d3-113">Configuración básica</span><span class="sxs-lookup"><span data-stu-id="2a4d3-113">Base configuration</span></span>

<span data-ttu-id="2a4d3-p103">Primero debe crear un entorno de prueba para [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) que incluya Office 365 E5, Enterprise Mobility + Security (EMS) E5 y Windows 10 Enterprise. Puede crear dos tipos distintos de configuraciones básicas:</span><span class="sxs-lookup"><span data-stu-id="2a4d3-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="2a4d3-116">Use la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md) si quiere configurar y demostrar las características y funciones de Microsoft 365 Enterprise solo en un entorno de nube, que no incluye ningún componente local.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="2a4d3-117">Use la [configuración básica empresarial simulada](simulated-ent-base-configuration-microsoft-365-enterprise.md) si quiere configurar y demostrar las características y funciones de Microsoft 365 Enterprise en un entorno de nube híbrido, que incluye componentes locales, como un dominio de Windows Server Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="2a4d3-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as a Windows Server Active Directory (AD) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="2a4d3-118">Identidad</span><span class="sxs-lookup"><span data-stu-id="2a4d3-118">Identity</span></span>

<span data-ttu-id="2a4d3-119">Para mostrar características y funciones relacionadas con identidades, vea:</span><span class="sxs-lookup"><span data-stu-id="2a4d3-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="2a4d3-120">Sincronización de hash de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2a4d3-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="2a4d3-121">Habilitar y probar la sincronización de directorios basada en hash de contraseñas desde un controlador de dominio de Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-121">Enable and test password hash-based directory synchronization from a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="2a4d3-122">Autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="2a4d3-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="2a4d3-123">Habilitar y probar la autenticación de paso a través en un controlador de dominio de Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-123">Enable and test pass-through authentication to a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="2a4d3-124">Inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="2a4d3-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="2a4d3-125">Habilite y pruebe el inicio de sesión único de conexión directa (SSO) de Azure AD con un controlador de dominio de Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="2a4d3-126">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="2a4d3-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="2a4d3-127">Habilite y pruebe la autenticación multifactor basada en teléfono inteligente para una cuenta de usuario determinada.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="2a4d3-128">Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="2a4d3-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="2a4d3-129">Bloquee sus cuentas de administrador global con Office 365 Cloud App Security y directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="2a4d3-130">Restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="2a4d3-130">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="2a4d3-131">Use el restablecimiento de contraseñas de autoservicio (SSPR) para restablecer su contraseña.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-131">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="2a4d3-132">Licencias automáticas y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="2a4d3-132">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="2a4d3-133">Haga que administrar nuevas cuentas sea más fácil que nunca con licencias automáticas y pertenencia a grupos dinámica.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-133">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="2a4d3-134">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="2a4d3-134">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="2a4d3-135">Examine sus cuentas actuales de usuarios en busca de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-135">Scan your current user accounts for vulnerabilities.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="2a4d3-136">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="2a4d3-136">Mobile device management</span></span>

<span data-ttu-id="2a4d3-137">Para mostrar funcionalidades y características relacionadas con la administración de dispositivos móviles, vea:</span><span class="sxs-lookup"><span data-stu-id="2a4d3-137">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="2a4d3-138">Directivas de administración de aplicaciones móviles (MAM)</span><span class="sxs-lookup"><span data-stu-id="2a4d3-138">MAM policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="2a4d3-139">Cree grupos de usuarios y directivas de administración de aplicaciones móviles (MAM) para dispositivos iOS y Android.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-139">Create user groups and mobile application management (MAM) policies for iOS and Android devices.</span></span>
    
- [<span data-ttu-id="2a4d3-140">Inscribir dispositivos iOS y Android</span><span class="sxs-lookup"><span data-stu-id="2a4d3-140">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="2a4d3-141">Inscriba los dispositivos Android o iOS y adminístrelos de forma remota.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-141">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="2a4d3-142">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="2a4d3-142">Information protection</span></span>

<span data-ttu-id="2a4d3-143">Para demostrar características y funciones de la información relacionadas con la protección, vea:</span><span class="sxs-lookup"><span data-stu-id="2a4d3-143">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="2a4d3-144">Mayor seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="2a4d3-144">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="2a4d3-145">Configure las opciones para aumentar la seguridad de Office 365 y analizar las herramientas de seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-145">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="2a4d3-146">Clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="2a4d3-146">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="2a4d3-147">Configure y aplique etiquetas de Office 365 a un documento en un sitio de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-147">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="2a4d3-148">Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2a4d3-148">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="2a4d3-149">Configure la administración del acceso con privilegios para el acceso en el momento a tareas elevadas o con privilegios en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a4d3-149">Configure privileged acccess management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a4d3-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a4d3-150">See also</span></span>

[<span data-ttu-id="2a4d3-151">Experiencia de Microsoft Cloud con guías del laboratorio de pruebas de adopción de la nube</span><span class="sxs-lookup"><span data-stu-id="2a4d3-151">Experience the Microsoft Cloud with Cloud Adoption Test Lab Guides</span></span>](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[<span data-ttu-id="2a4d3-152">Una pila de guía del laboratorio de pruebas de Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="2a4d3-152">One Microsoft Cloud Test Lab Guide stack</span></span>](http://aka.ms/catlgstack)
