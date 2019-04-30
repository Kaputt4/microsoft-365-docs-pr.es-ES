---
title: Guías del laboratorio de pruebas de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
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
ms.openlocfilehash: 007fac786e7676d219d7e82c435e37fe3c3221df
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353152"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="c36e6-103">Guías del laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c36e6-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="c36e6-p101">Las Guías del laboratorio de pruebas (TLG) le ayudan a obtener información rápidamente sobre productos de Microsoft. Proporcionan instrucciones prescriptivas para configurar entornos de pruebas representativos pero simplificados. Puede usar estos entornos para la demostración, la personalización o la creación de pruebas de concepto complejas durante el tiempo que dure una suscripción de prueba o de pago.</span><span class="sxs-lookup"><span data-stu-id="c36e6-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="c36e6-p102">Las TLG están diseñadas para ser modulares. Se desarrollan entre sí para crear varias configuraciones que se adapten a sus necesidades de configuración de aprendizaje o de prueba. La experiencia práctica "Lo diseñé yo mismo y funciona" le ayudará a comprender los requisitos de implementación de un nuevo producto o escenario para que pueda planear mejor su hospedaje en producción.</span><span class="sxs-lookup"><span data-stu-id="c36e6-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="c36e6-110">Las TLG también le permiten crear entornos representativos para desarrollo y prueba de aplicaciones, también conocidos como entornos de desarrollo y prueba.</span><span class="sxs-lookup"><span data-stu-id="c36e6-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c36e6-112">Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c36e6-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="c36e6-113">Configuración básica</span><span class="sxs-lookup"><span data-stu-id="c36e6-113">Base configuration</span></span>

<span data-ttu-id="c36e6-p103">Primero debe crear un entorno de prueba para [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) que incluya Office 365 E5, Enterprise Mobility + Security (EMS) E5 y Windows 10 Enterprise. Puede crear dos tipos distintos de configuraciones básicas:</span><span class="sxs-lookup"><span data-stu-id="c36e6-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="c36e6-116">Use la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md) si quiere configurar y demostrar las características y funciones de Microsoft 365 Enterprise solo en un entorno de nube, que no incluye ningún componente local.</span><span class="sxs-lookup"><span data-stu-id="c36e6-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="c36e6-117">Use la [configuración básica de empresa simulada](simulated-ent-base-configuration-microsoft-365-enterprise.md) para configurar y demostrar las características y funciones de Microsoft 365 Enterprise en un entorno híbrido de nube, que use componentes locales como un dominio Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c36e6-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="c36e6-118">Identidad</span><span class="sxs-lookup"><span data-stu-id="c36e6-118">Identity</span></span>

<span data-ttu-id="c36e6-119">Para mostrar características y funciones relacionadas con identidades, vea:</span><span class="sxs-lookup"><span data-stu-id="c36e6-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="c36e6-120">Sincronización de hash de contraseñas</span><span class="sxs-lookup"><span data-stu-id="c36e6-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="c36e6-121">Habilitar y probar la sincronización de directorios basada en hash y por contraseña de un controlador de dominio de Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c36e6-121">Enable and test password hash-based directory synchronization from a Active Directory Domain Services (AD DS) domain controller.</span></span>

- [<span data-ttu-id="c36e6-122">Autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="c36e6-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="c36e6-123">Habilitar y probar la autenticación de paso en un controlador de dominio de AD DS.</span><span class="sxs-lookup"><span data-stu-id="c36e6-123">Enable and test pass-through authentication to a AD DS domain controller.</span></span>

- [<span data-ttu-id="c36e6-124">Inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="c36e6-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="c36e6-125">Habilitar y probar el Inicio de sesión único de conexión directa (SSO) de Azure AD con un controlador de dominio de AD DS.</span><span class="sxs-lookup"><span data-stu-id="c36e6-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a AD DS domain controller.</span></span>

- [<span data-ttu-id="c36e6-126">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="c36e6-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="c36e6-127">Habilite y pruebe la autenticación multifactor basada en teléfono inteligente para una cuenta de usuario determinada.</span><span class="sxs-lookup"><span data-stu-id="c36e6-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="c36e6-128">Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="c36e6-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="c36e6-129">Bloquear sus cuentas de administrador global con directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="c36e6-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="c36e6-130">Reescritura de contraseña</span><span class="sxs-lookup"><span data-stu-id="c36e6-130">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="c36e6-131">Usar una escritura diferida de contraseñas para cambiar la contraseña de su cuenta de usuario de AD DS de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c36e6-131">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="c36e6-132">Restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="c36e6-132">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="c36e6-133">Use el restablecimiento de contraseñas de autoservicio (SSPR) para restablecer su contraseña.</span><span class="sxs-lookup"><span data-stu-id="c36e6-133">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="c36e6-134">Licencias automáticas y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="c36e6-134">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="c36e6-135">Haga que administrar nuevas cuentas sea más fácil que nunca con licencias automáticas y pertenencia a grupos dinámica.</span><span class="sxs-lookup"><span data-stu-id="c36e6-135">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="c36e6-136">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="c36e6-136">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="c36e6-137">Examine sus cuentas actuales de usuarios en busca de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="c36e6-137">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="c36e6-138">Acceso de dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="c36e6-138">Identity and device access configurations</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="c36e6-139">Crear un entorno para probar la identidad recomendada y configuraciones de acceso de dispositivo y directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="c36e6-139">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="c36e6-140">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="c36e6-140">Mobile device management</span></span>

<span data-ttu-id="c36e6-141">Para mostrar funcionalidades y características relacionadas con la administración de dispositivos móviles, vea:</span><span class="sxs-lookup"><span data-stu-id="c36e6-141">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="c36e6-142">Directivas de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c36e6-142">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="c36e6-143">Cree un grupo de usuarios y una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c36e6-143">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="c36e6-144">Inscribir dispositivos iOS y Android</span><span class="sxs-lookup"><span data-stu-id="c36e6-144">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="c36e6-145">Inscriba los dispositivos Android o iOS y adminístrelos de forma remota.</span><span class="sxs-lookup"><span data-stu-id="c36e6-145">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="c36e6-146">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="c36e6-146">Information protection</span></span>

<span data-ttu-id="c36e6-147">Para demostrar características y funciones de la información relacionadas con la protección, vea:</span><span class="sxs-lookup"><span data-stu-id="c36e6-147">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="c36e6-148">Mayor seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="c36e6-148">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="c36e6-149">Configure las opciones para aumentar la seguridad de Office 365 y analizar las herramientas de seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="c36e6-149">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="c36e6-150">Clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="c36e6-150">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="c36e6-151">Configure y aplique etiquetas de Office 365 a un documento en un sitio de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c36e6-151">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="c36e6-152">Administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="c36e6-152">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="c36e6-153">Configure la administración del acceso con privilegios para habilitar el acceso puntual a tareas elevadas o con privilegios en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c36e6-153">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="c36e6-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="c36e6-154">See also</span></span>

[<span data-ttu-id="c36e6-155">Probar Office 365 con la adopción de nube TLG</span><span class="sxs-lookup"><span data-stu-id="c36e6-155">Test Office 365 with cloud adoption TLGs</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
