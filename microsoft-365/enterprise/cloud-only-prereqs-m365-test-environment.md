---
title: Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos de autenticación solo para la nube.
ms.openlocfilehash: aa18e1a9943ec12465737f6c3f2e12c1fa49e2a3
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398882"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="7f6c7-103">Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f6c7-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="7f6c7-104">*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*</span><span class="sxs-lookup"><span data-stu-id="7f6c7-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7f6c7-105">[Las configuraciones de](../security/office-365-security/microsoft-365-policies-configurations.md) acceso a dispositivos e identidades son un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios integrados con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7f6c7-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="7f6c7-106">En este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumpla con los requisitos de la [configuración de requisitos previos solo para la nube](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="7f6c7-107">Existen siete fases para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="7f6c7-107">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="7f6c7-108">Crear el entorno de prueba ligero</span><span class="sxs-lookup"><span data-stu-id="7f6c7-108">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="7f6c7-109">Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="7f6c7-109">Configure named locations</span></span>
3.  <span data-ttu-id="7f6c7-110">Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7f6c7-110">Configure password writeback</span></span>
4.  <span data-ttu-id="7f6c7-111">Configurar el autoservicio de restablecimiento de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7f6c7-111">Configure self-service password resets</span></span>
5.  <span data-ttu-id="7f6c7-112">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="7f6c7-112">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="7f6c7-113">Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="7f6c7-113">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="7f6c7-114">Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7f6c7-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="7f6c7-115">Fase 1: Crear el entorno de prueba ligero de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f6c7-115">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="7f6c7-116">Siga las instrucciones de [Configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7f6c7-116">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="7f6c7-117">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-117">Here is the resulting configuration.</span></span>

![El entorno de prueba ligero de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="7f6c7-119">Fase 2: Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="7f6c7-119">Phase 2: Configure named locations</span></span>

<span data-ttu-id="7f6c7-120">En primer lugar, determine las direcciones IP públicas o los intervalos de direcciones usados por su organización.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-120">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="7f6c7-121">Luego, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o los intervalos de direcciones como ubicaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-121">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="7f6c7-122">Fase 3: Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7f6c7-122">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="7f6c7-123">Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="7f6c7-123">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="7f6c7-124">Fase 4: Configurar el autoservicio de restablecimiento de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7f6c7-124">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="7f6c7-125">Siga las instrucciones de la [Fase 3 de la Guía del laboratorio de pruebas del restablecimiento de contraseñas](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="7f6c7-125">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="7f6c7-126">Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:</span><span class="sxs-lookup"><span data-stu-id="7f6c7-126">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="7f6c7-127">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="7f6c7-127">User 2</span></span>
- <span data-ttu-id="7f6c7-128">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="7f6c7-128">User 3</span></span>
- <span data-ttu-id="7f6c7-129">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="7f6c7-129">User 4</span></span>
- <span data-ttu-id="7f6c7-130">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="7f6c7-130">User 5</span></span>

<span data-ttu-id="7f6c7-131">Pruebe el restablecimiento de contraseñas solo para la cuenta de Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-131">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="7f6c7-132">Fase 5: Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="7f6c7-132">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="7f6c7-133">Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de autenticación multifactor](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f6c7-133">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="7f6c7-134">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="7f6c7-134">User 2</span></span>
- <span data-ttu-id="7f6c7-135">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="7f6c7-135">User 3</span></span>
- <span data-ttu-id="7f6c7-136">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="7f6c7-136">User 4</span></span>
- <span data-ttu-id="7f6c7-137">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="7f6c7-137">User 5</span></span>

<span data-ttu-id="7f6c7-138">Pruebe la autenticación multifactor solo para la cuenta del Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-138">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="7f6c7-139">Fase 6: Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="7f6c7-139">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="7f6c7-140">Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de autenticación multifactor de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="7f6c7-140">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="7f6c7-141">Fase 7: Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7f6c7-141">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="7f6c7-142">Para Exchange Online, siga [estas instrucciones](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="7f6c7-142">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="7f6c7-143">Para Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="7f6c7-143">For Skype for Business Online:</span></span>

1. <span data-ttu-id="7f6c7-144">Conéctese a [Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="7f6c7-144">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="7f6c7-145">Ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-145">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="7f6c7-146">Compruebe que el cambio se realizó correctamente con este comando.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-146">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="7f6c7-147">El resultado es un entorno de prueba que cumple con los requisitos de la [configuración de requisitos previos solo para la nube](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-147">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="7f6c7-148">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7f6c7-148">Next step</span></span>

<span data-ttu-id="7f6c7-149">Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-149">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f6c7-150">Ver también</span><span class="sxs-lookup"><span data-stu-id="7f6c7-150">See also</span></span>

[<span data-ttu-id="7f6c7-151">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="7f6c7-151">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="7f6c7-152">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="7f6c7-152">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7f6c7-153">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7f6c7-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7f6c7-154">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7f6c7-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7f6c7-155">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7f6c7-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
