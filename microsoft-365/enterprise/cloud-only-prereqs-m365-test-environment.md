---
title: Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos de autenticación solo para la nube.
ms.openlocfilehash: eb70153bc2868289fde41ad9a68ffa3a44b01b59
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627376"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="db793-103">Requisitos previos de acceso de dispositivos e identidades solo para la nube en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db793-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="db793-104">[Configuración de acceso de dispositivos e identidades](microsoft-365-policies-configurations.md) es un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios que se integran con Azure Active Directory (Azure AD), incluidos Office 365 y Microsoft Intune en Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="db793-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="db793-105">En este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumpla con los requisitos de la [configuración de requisitos previos solo para la nube](identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="db793-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="db793-106">Existen siete fases para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="db793-106">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="db793-107">Crear el entorno de prueba ligero</span><span class="sxs-lookup"><span data-stu-id="db793-107">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="db793-108">Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="db793-108">Configure named locations</span></span>
3.  <span data-ttu-id="db793-109">Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="db793-109">Configure password writeback</span></span>
4.  <span data-ttu-id="db793-110">Configurar el autoservicio de restablecimiento de contraseñas</span><span class="sxs-lookup"><span data-stu-id="db793-110">Configure self-service password resets</span></span>
5.  <span data-ttu-id="db793-111">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="db793-111">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="db793-112">Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="db793-112">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="db793-113">Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="db793-113">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="db793-114">Fase 1: Crear el entorno de prueba ligero de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db793-114">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="db793-115">Siga las instrucciones de [Configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="db793-115">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="db793-116">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="db793-116">Here is the resulting configuration.</span></span>

![El entorno de prueba ligero de Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="db793-118">Fase 2: Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="db793-118">Phase 2: Configure named locations</span></span>

<span data-ttu-id="db793-119">En primer lugar, determine las direcciones IP públicas o los intervalos de direcciones usados por su organización.</span><span class="sxs-lookup"><span data-stu-id="db793-119">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="db793-120">Luego, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o los intervalos de direcciones como ubicaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="db793-120">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="db793-121">Fase 3: Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="db793-121">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="db793-122">Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="db793-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="db793-123">Fase 4: Configurar el autoservicio de restablecimiento de contraseñas</span><span class="sxs-lookup"><span data-stu-id="db793-123">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="db793-124">Siga las instrucciones de la [Fase 3 de la Guía del laboratorio de pruebas del restablecimiento de contraseñas](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="db793-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="db793-125">Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:</span><span class="sxs-lookup"><span data-stu-id="db793-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="db793-126">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="db793-126">User 2</span></span>
- <span data-ttu-id="db793-127">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="db793-127">User 3</span></span>
- <span data-ttu-id="db793-128">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="db793-128">User 4</span></span>
- <span data-ttu-id="db793-129">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="db793-129">User 5</span></span>

<span data-ttu-id="db793-130">Pruebe el restablecimiento de contraseñas solo para la cuenta de Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="db793-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="db793-131">Fase 5: Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="db793-131">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="db793-132">Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de autenticación multifactor](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:</span><span class="sxs-lookup"><span data-stu-id="db793-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="db793-133">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="db793-133">User 2</span></span>
- <span data-ttu-id="db793-134">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="db793-134">User 3</span></span>
- <span data-ttu-id="db793-135">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="db793-135">User 4</span></span>
- <span data-ttu-id="db793-136">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="db793-136">User 5</span></span>

<span data-ttu-id="db793-137">Pruebe la autenticación multifactor solo para la cuenta del Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="db793-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="db793-138">Fase 6: Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="db793-138">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="db793-139">Siga las instrucciones de la [Fase 2 de la Guía del laboratorio de pruebas de autenticación multifactor de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="db793-139">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="db793-140">Fase 7: Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="db793-140">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="db793-141">Para Exchange Online, siga [estas instrucciones](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="db793-141">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="db793-142">Para Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="db793-142">For Skype for Business Online:</span></span>

1. <span data-ttu-id="db793-143">Conéctese a [Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="db793-143">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="db793-144">Ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="db793-144">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="db793-145">Compruebe que el cambio se realizó correctamente con este comando.</span><span class="sxs-lookup"><span data-stu-id="db793-145">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="db793-146">El resultado es un entorno de prueba que cumple con los requisitos de la [configuración de requisitos previos solo para la nube](identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="db793-146">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="db793-147">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="db793-147">Next step</span></span>

<span data-ttu-id="db793-148">Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="db793-148">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="db793-149">Ver también</span><span class="sxs-lookup"><span data-stu-id="db793-149">See also</span></span>

[<span data-ttu-id="db793-150">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="db793-150">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="db793-151">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="db793-151">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="db793-152">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db793-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="db793-153">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db793-153">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="db793-154">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db793-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
