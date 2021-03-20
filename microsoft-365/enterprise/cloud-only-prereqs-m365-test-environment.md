---
title: Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365
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
description: Cree un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos de autenticación solo para la nube.
ms.openlocfilehash: 3e5a9ef1f610bf3dc6d23c9e584e179fb8ab9ca9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905145"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="5f403-103">Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f403-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="5f403-104">*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*</span><span class="sxs-lookup"><span data-stu-id="5f403-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5f403-105">[Las configuraciones de acceso](../security/office-365-security/microsoft-365-policies-configurations.md) a dispositivos y identidades son un conjunto de configuraciones recomendadas y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5f403-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="5f403-106">En este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumpla con los requisitos de la [configuración de requisitos previos solo para la nube](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="5f403-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="5f403-107">Existen ocho fases para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="5f403-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="5f403-108">Crear el entorno de prueba ligero</span><span class="sxs-lookup"><span data-stu-id="5f403-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="5f403-109">Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="5f403-109">Configure named locations</span></span>
3. <span data-ttu-id="5f403-110">Configurar el autoservicio de restablecimiento de contraseñas</span><span class="sxs-lookup"><span data-stu-id="5f403-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="5f403-111">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="5f403-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="5f403-112">Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio</span><span class="sxs-lookup"><span data-stu-id="5f403-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="5f403-113">Configurar la protección con contraseña de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5f403-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="5f403-114">Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5f403-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="5f403-115">Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5f403-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="5f403-116">Fase 1: Crear el entorno de prueba ligero de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f403-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="5f403-117">Siga las instrucciones de [Configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="5f403-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="5f403-118">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="5f403-118">Here is the resulting configuration.</span></span>

![El entorno de prueba ligero de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="5f403-120">Fase 2: Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="5f403-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="5f403-121">En primer lugar, determine las direcciones IP públicas o los intervalos de direcciones usados por su organización.</span><span class="sxs-lookup"><span data-stu-id="5f403-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="5f403-122">A continuación, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o intervalos de direcciones como ubicaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="5f403-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="5f403-123">Fase 3: Configurar el restablecimiento de contraseñas de autoservicio</span><span class="sxs-lookup"><span data-stu-id="5f403-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="5f403-124">Siga las instrucciones en la [Guía de entorno de pruebas, fase 3 de la operación de restablecimiento de contraseña](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="5f403-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="5f403-125">Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:</span><span class="sxs-lookup"><span data-stu-id="5f403-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="5f403-126">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="5f403-126">User 2</span></span>
- <span data-ttu-id="5f403-127">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="5f403-127">User 3</span></span>
- <span data-ttu-id="5f403-128">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="5f403-128">User 4</span></span>
- <span data-ttu-id="5f403-129">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="5f403-129">User 5</span></span>

<span data-ttu-id="5f403-130">Pruebe el restablecimiento de contraseña solo de la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="5f403-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="5f403-131">Fase 4: Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="5f403-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="5f403-132">Siga las instrucciones en [Guía del laboratorio de pruebas, fase 2 de la autenticación multifactor ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f403-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="5f403-133">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="5f403-133">User 2</span></span>
- <span data-ttu-id="5f403-134">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="5f403-134">User 3</span></span>
- <span data-ttu-id="5f403-135">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="5f403-135">User 4</span></span>
- <span data-ttu-id="5f403-136">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="5f403-136">User 5</span></span>

<span data-ttu-id="5f403-137">Pruebe la autenticación multifactor solo para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="5f403-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="5f403-138">Fase 5: Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio</span><span class="sxs-lookup"><span data-stu-id="5f403-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="5f403-139">Sigue [estas instrucciones para](/azure/active-directory/devices/hybrid-azuread-join-plan) habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="5f403-139">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="5f403-140">Fase 6: Configurar la protección con contraseña de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5f403-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="5f403-141">Siga [estas instrucciones para](/azure/active-directory/authentication/concept-password-ban-bad) bloquear las contraseñas débiles conocidas y sus variantes.</span><span class="sxs-lookup"><span data-stu-id="5f403-141">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="5f403-142">Fase 7: Habilitación de Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5f403-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="5f403-143">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="5f403-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="5f403-144">Fase 8: Habilitar autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5f403-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="5f403-145">Para Exchange Online, siga [estas instrucciones](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="5f403-145">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="5f403-146">Para Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="5f403-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="5f403-147">Conéctese a [Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="5f403-147">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="5f403-148">Ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="5f403-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="5f403-149">Compruebe que el cambio se realizó correctamente con este comando.</span><span class="sxs-lookup"><span data-stu-id="5f403-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="5f403-150">El resultado es un entorno de prueba que cumple los requisitos de la configuración de [requisitos](../security/office-365-security/identity-access-prerequisites.md#prerequisites) previos de solo nube para el acceso de identidades y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5f403-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="5f403-151">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5f403-151">Next step</span></span>

<span data-ttu-id="5f403-152">Use [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="5f403-152">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f403-153">Ver también</span><span class="sxs-lookup"><span data-stu-id="5f403-153">See also</span></span>

[<span data-ttu-id="5f403-154">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="5f403-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="5f403-155">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="5f403-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5f403-156">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5f403-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5f403-157">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5f403-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5f403-158">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5f403-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)