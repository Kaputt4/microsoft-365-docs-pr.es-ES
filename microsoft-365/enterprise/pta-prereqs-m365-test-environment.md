---
title: Requisitos previos de acceso de dispositivos e identidades para la autenticación de paso a través en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos para la autenticación de paso a través.
ms.openlocfilehash: f257b85672a1a1b27f600d145b1f9f3296b21980
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199854"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="dd981-103">Requisitos previos de acceso de dispositivos e identidades para la autenticación de paso a través en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd981-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="dd981-104">*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*</span><span class="sxs-lookup"><span data-stu-id="dd981-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="dd981-105">[Las configuraciones](../security/office-365-security/microsoft-365-policies-configurations.md) de acceso a dispositivos y identidades son un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios de Microsoft 365 para empresas que están integrados con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="dd981-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="dd981-106">Este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumple con los requisitos de la [Configuración de requisitos previos de la autenticación de paso a través](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="dd981-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="dd981-107">Hay diez fases para configurar este entorno de prueba:</span><span class="sxs-lookup"><span data-stu-id="dd981-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="dd981-108">Crear una empresa simulada con el entorno de prueba de Microsoft 365 de autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="dd981-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2. <span data-ttu-id="dd981-109">Configurar el inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="dd981-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="dd981-110">Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="dd981-110">Configure named locations</span></span>
4. <span data-ttu-id="dd981-111">Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="dd981-111">Configure password writeback</span></span>
5. <span data-ttu-id="dd981-112">Configurar el autoservicio de restablecimiento de contraseñas</span><span class="sxs-lookup"><span data-stu-id="dd981-112">Configure self-service password reset</span></span>
6. <span data-ttu-id="dd981-113">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="dd981-113">Configure multifactor authentication</span></span>
7. <span data-ttu-id="dd981-114">Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio</span><span class="sxs-lookup"><span data-stu-id="dd981-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="dd981-115">Configurar la protección con contraseña de Azure AD</span><span class="sxs-lookup"><span data-stu-id="dd981-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="dd981-116">Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="dd981-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="dd981-117">Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="dd981-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="dd981-118">Fase 1: Crear una empresa simulada con el entorno de prueba de Microsoft 365 de autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="dd981-118">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="dd981-119">Siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="dd981-119">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="dd981-120">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="dd981-120">Here is the resulting configuration.</span></span>

![La empresa simulada con el entorno de prueba de la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="dd981-122">Fase 2: Configurar el inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="dd981-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="dd981-123">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 del inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="dd981-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="dd981-124">Fase 3: Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="dd981-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="dd981-125">En primer lugar, determine las direcciones IP públicas o el intervalo de direcciones usadas por su organización.</span><span class="sxs-lookup"><span data-stu-id="dd981-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="dd981-126">A continuación, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o intervalos de direcciones como ubicaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="dd981-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="dd981-127">Fase 4: Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="dd981-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="dd981-128">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="dd981-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="dd981-129">Fase 5: Configurar el autoservicio de restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="dd981-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="dd981-130">Siga las instrucciones en la [Guía de entorno de pruebas, fase 3 de la operación de restablecimiento de contraseña](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="dd981-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="dd981-131">Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:</span><span class="sxs-lookup"><span data-stu-id="dd981-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="dd981-132">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="dd981-132">User 2</span></span>
- <span data-ttu-id="dd981-133">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="dd981-133">User 3</span></span>
- <span data-ttu-id="dd981-134">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="dd981-134">User 4</span></span>
- <span data-ttu-id="dd981-135">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="dd981-135">User 5</span></span>

<span data-ttu-id="dd981-136">Pruebe el restablecimiento de contraseña solo de la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="dd981-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="dd981-137">Fase 6: Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="dd981-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="dd981-138">Siga las instrucciones en [Guía del laboratorio de pruebas, fase 2 de la autenticación multifactor ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd981-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="dd981-139">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="dd981-139">User 2</span></span>
- <span data-ttu-id="dd981-140">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="dd981-140">User 3</span></span>
- <span data-ttu-id="dd981-141">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="dd981-141">User 4</span></span>
- <span data-ttu-id="dd981-142">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="dd981-142">User 5</span></span>

<span data-ttu-id="dd981-143">Pruebe la autenticación multifactor solo para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="dd981-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="dd981-144">Fase 7: Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio</span><span class="sxs-lookup"><span data-stu-id="dd981-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="dd981-145">Sigue [estas instrucciones para](/azure/active-directory/devices/hybrid-azuread-join-plan) habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="dd981-145">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="dd981-146">Fase 8: Configurar la protección con contraseña de Azure AD</span><span class="sxs-lookup"><span data-stu-id="dd981-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="dd981-147">Siga [estas instrucciones para](/azure/active-directory/authentication/concept-password-ban-bad) bloquear las contraseñas débiles conocidas y sus variantes.</span><span class="sxs-lookup"><span data-stu-id="dd981-147">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="dd981-148">Fase 9: Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="dd981-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="dd981-149">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="dd981-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="dd981-150">Fase 10: Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="dd981-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="dd981-151">Para Exchange Online, siga [estas instrucciones](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="dd981-151">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="dd981-152">Para Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="dd981-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="dd981-153">Conéctese a [Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="dd981-153">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="dd981-154">Ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="dd981-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="dd981-155">Compruebe que el cambio se realizó correctamente con este comando.</span><span class="sxs-lookup"><span data-stu-id="dd981-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="dd981-156">El resultado es un entorno de prueba que cumple con los requisitos de la [Configuración de requisitos previos de autenticación de paso a través](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="dd981-156">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="dd981-157">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="dd981-157">Next step</span></span>

<span data-ttu-id="dd981-158">Use [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="dd981-158">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd981-159">Ver también</span><span class="sxs-lookup"><span data-stu-id="dd981-159">See also</span></span>

[<span data-ttu-id="dd981-160">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="dd981-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="dd981-161">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="dd981-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="dd981-162">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dd981-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="dd981-163">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dd981-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="dd981-164">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dd981-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
