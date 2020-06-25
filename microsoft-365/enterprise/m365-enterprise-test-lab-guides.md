---
title: Guías de laboratorio para pruebas de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Utilice estas guías de laboratorio de pruebas para configurar una demostración, prueba de concepto o entornos de desarrollo/prueba en Microsoft 365 para empresas.
ms.openlocfilehash: 5907edd1bc42b9d679ed020331f225ef2d2b2594
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818746"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="f6849-103">Guías de laboratorio para pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f6849-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="f6849-104">*Esto se aplica tanto a Microsoft 365 para empresas como a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f6849-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f6849-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span><span class="sxs-lookup"><span data-stu-id="f6849-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span></span> <span data-ttu-id="f6849-106">They provide prescriptive instructions to configure simplified but representative test environments.</span><span class="sxs-lookup"><span data-stu-id="f6849-106">They provide prescriptive instructions to configure simplified but representative test environments.</span></span> <span data-ttu-id="f6849-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span><span class="sxs-lookup"><span data-stu-id="f6849-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="f6849-108">TLGs are designed to be modular.</span><span class="sxs-lookup"><span data-stu-id="f6849-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="f6849-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span><span class="sxs-lookup"><span data-stu-id="f6849-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="f6849-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span><span class="sxs-lookup"><span data-stu-id="f6849-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="f6849-111">Las TLG también le permiten crear entornos representativos para desarrollo y prueba de aplicaciones, también conocidos como entornos de desarrollo y prueba.</span><span class="sxs-lookup"><span data-stu-id="f6849-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="f6849-113">Haga clic en [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila de guías de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f6849-113">Go to the [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="f6849-114">[![Pila de guías de laboratorio para pruebas de Microsoft 365 Enterprise](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="f6849-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="f6849-115">Configuración básica</span><span class="sxs-lookup"><span data-stu-id="f6849-115">Base configuration</span></span>

<span data-ttu-id="f6849-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f6849-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span></span> <span data-ttu-id="f6849-117">You can create two different types of base configurations:</span><span class="sxs-lookup"><span data-stu-id="f6849-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="f6849-118">Utilice la [configuración de base ligera](lightweight-base-configuration-microsoft-365-enterprise.md) cuando desee configurar y realizar demostraciones sobre las características y capacidades de Microsoft 365 para empresas en un entorno únicamente de la nube, que no incluya componentes locales.</span><span class="sxs-lookup"><span data-stu-id="f6849-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="f6849-119">Utilice la [configuración de base simulada para empresas](simulated-ent-base-configuration-microsoft-365-enterprise.md) cuando desee configurar y demostrar las características y capacidades de Microsoft 365 para empresas en un entorno híbrido de la nube, que usa componentes locales como el Servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f6849-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="f6849-120">También puede crear entornos de prueba para Office 365 E5 al no agregar la licencia de Microsoft 365 E5 a su prueba o entorno de prueba de producción.</span><span class="sxs-lookup"><span data-stu-id="f6849-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="f6849-121">Identidad</span><span class="sxs-lookup"><span data-stu-id="f6849-121">Identity</span></span>

<span data-ttu-id="f6849-122">Para mostrar características y funciones relacionadas con identidades, vea:</span><span class="sxs-lookup"><span data-stu-id="f6849-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="f6849-123">Sincronización de hash de contraseñas</span><span class="sxs-lookup"><span data-stu-id="f6849-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="f6849-124">Habilite y pruebe la sincronización de directorios basada en hash de contraseñas desde un controlador de dominio AD DS.</span><span class="sxs-lookup"><span data-stu-id="f6849-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="f6849-125">Autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="f6849-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="f6849-126">Habilite y pruebe la autenticación de paso a un controlador de dominio AD DS.</span><span class="sxs-lookup"><span data-stu-id="f6849-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="f6849-127">Autenticación federada</span><span class="sxs-lookup"><span data-stu-id="f6849-127">Federated authentication</span></span>](federated-identity-for-your-office-365-dev-test-environment.md)
  
   <span data-ttu-id="f6849-128">Habilite y pruebe la autenticación federada a un controlador de dominio AD DS.</span><span class="sxs-lookup"><span data-stu-id="f6849-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="f6849-129">Inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="f6849-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="f6849-130">Habilite y pruebe Azure AD Seamless Single Sign-on (SSO) con un controlador de dominio AD DS.</span><span class="sxs-lookup"><span data-stu-id="f6849-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="f6849-131">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="f6849-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="f6849-132">Habilite y pruebe la autenticación multifactor basada en teléfono inteligente para una cuenta de usuario determinada.</span><span class="sxs-lookup"><span data-stu-id="f6849-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="f6849-133">Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="f6849-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="f6849-134">Bloquear sus cuentas de administrador global con directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="f6849-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="f6849-135">Reescritura de contraseña</span><span class="sxs-lookup"><span data-stu-id="f6849-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="f6849-136">Usar una escritura diferida de contraseñas para cambiar la contraseña de su cuenta de usuario de AD DS de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f6849-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="f6849-137">Restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="f6849-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="f6849-138">Use el restablecimiento de contraseñas de autoservicio (SSPR) para restablecer su contraseña.</span><span class="sxs-lookup"><span data-stu-id="f6849-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="f6849-139">Licencias automáticas y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="f6849-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="f6849-140">Haga que administrar nuevas cuentas sea más fácil que nunca con licencias automáticas y pertenencia a grupos dinámica.</span><span class="sxs-lookup"><span data-stu-id="f6849-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="f6849-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f6849-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="f6849-142">Examine sus cuentas actuales de usuarios en busca de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="f6849-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="f6849-143">Acceso de dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="f6849-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="f6849-144">Crear un entorno para probar la identidad recomendada y configuraciones de acceso de dispositivo y directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="f6849-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="f6849-145">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="f6849-145">Mobile device management</span></span>

<span data-ttu-id="f6849-146">Para mostrar funcionalidades y características relacionadas con la administración de dispositivos móviles, vea:</span><span class="sxs-lookup"><span data-stu-id="f6849-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="f6849-147">Directivas de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f6849-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="f6849-148">Cree un grupo de usuarios y una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f6849-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="f6849-149">Inscribir dispositivos iOS y Android</span><span class="sxs-lookup"><span data-stu-id="f6849-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="f6849-150">Inscriba los dispositivos Android o iOS y adminístrelos de forma remota.</span><span class="sxs-lookup"><span data-stu-id="f6849-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="f6849-151">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="f6849-151">Information protection</span></span>

<span data-ttu-id="f6849-152">Para demostrar características y funciones de la información relacionadas con la protección, vea:</span><span class="sxs-lookup"><span data-stu-id="f6849-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="f6849-153">Aumentar la seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6849-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="f6849-154">Configure las opciones para aumentar la seguridad de Microsoft 365 y analizar las herramientas de seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="f6849-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="f6849-155">Clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="f6849-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="f6849-156">Configure y aplique etiquetas a un documento en un sitio de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f6849-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="f6849-157">Administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="f6849-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="f6849-158">Configure la administración del acceso con privilegios para habilitar el acceso puntual a tareas elevadas o con privilegios en su organización.</span><span class="sxs-lookup"><span data-stu-id="f6849-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>


