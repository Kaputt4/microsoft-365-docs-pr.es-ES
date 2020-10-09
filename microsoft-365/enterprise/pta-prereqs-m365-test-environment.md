---
title: Requisitos previos de acceso de dispositivos e identidades para la autenticación de paso a través en el entorno de prueba de Microsoft 365
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
description: Cree un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos para la autenticación de paso a través.
ms.openlocfilehash: 7741b38a947e58d81192326c412760487d803e36
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399186"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="dc5d9-103">Requisitos previos de acceso de dispositivos e identidades para la autenticación de paso a través en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dc5d9-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="dc5d9-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="dc5d9-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="dc5d9-105">Las [configuraciones de identidad y acceso a dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) son un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios de Microsoft 365 para empresas que se integran con Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="dc5d9-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="dc5d9-106">Este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumple con los requisitos de la [Configuración de requisitos previos de la autenticación de paso a través](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="dc5d9-107">Existen ocho fases para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="dc5d9-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="dc5d9-108">Crear una empresa simulada con el entorno de prueba de Microsoft 365 de autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="dc5d9-109">Configurar el inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc5d9-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="dc5d9-110">Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="dc5d9-110">Configure named locations</span></span>
4.  <span data-ttu-id="dc5d9-111">Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="dc5d9-111">Configure password writeback</span></span>
5.  <span data-ttu-id="dc5d9-112">Configurar el autoservicio de restablecimiento de contraseñas</span><span class="sxs-lookup"><span data-stu-id="dc5d9-112">Configure self-service password reset</span></span>
6.  <span data-ttu-id="dc5d9-113">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="dc5d9-113">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="dc5d9-114">Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="dc5d9-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="dc5d9-115">Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="dc5d9-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="dc5d9-116">Fase 1: Crear una empresa simulada con el entorno de prueba de Microsoft 365 de autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-116">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="dc5d9-117">Siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="dc5d9-117">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="dc5d9-118">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-118">Here is the resulting configuration.</span></span>

![La empresa simulada con el entorno de prueba de la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="dc5d9-120">Fase 2: Configurar el inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc5d9-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="dc5d9-121">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 del inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="dc5d9-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="dc5d9-122">Fase 3: Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="dc5d9-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="dc5d9-123">En primer lugar, determine las direcciones IP públicas o el intervalo de direcciones usadas por su organización.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="dc5d9-124">A continuación, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o intervalos de direcciones como ubicaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="dc5d9-125">Fase 4: Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="dc5d9-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="dc5d9-126">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="dc5d9-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="dc5d9-127">Fase 5: Configurar el autoservicio de restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="dc5d9-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="dc5d9-128">Siga las instrucciones en la [Guía de entorno de pruebas, fase 3 de la operación de restablecimiento de contraseña](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="dc5d9-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="dc5d9-129">Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:</span><span class="sxs-lookup"><span data-stu-id="dc5d9-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="dc5d9-130">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="dc5d9-130">User 2</span></span>
- <span data-ttu-id="dc5d9-131">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="dc5d9-131">User 3</span></span>
- <span data-ttu-id="dc5d9-132">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="dc5d9-132">User 4</span></span>
- <span data-ttu-id="dc5d9-133">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="dc5d9-133">User 5</span></span>

<span data-ttu-id="dc5d9-134">Pruebe el restablecimiento de contraseña solo de la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="dc5d9-135">Fase 6: Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="dc5d9-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="dc5d9-136">Siga las instrucciones en [Guía del laboratorio de pruebas, fase 2 de la autenticación multifactor ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc5d9-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="dc5d9-137">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="dc5d9-137">User 2</span></span>
- <span data-ttu-id="dc5d9-138">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="dc5d9-138">User 3</span></span>
- <span data-ttu-id="dc5d9-139">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="dc5d9-139">User 4</span></span>
- <span data-ttu-id="dc5d9-140">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="dc5d9-140">User 5</span></span>

<span data-ttu-id="dc5d9-141">Pruebe la autenticación multifactor solo para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="dc5d9-142">Fase 7: Habilitación de Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="dc5d9-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="dc5d9-143">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="dc5d9-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="dc5d9-144">Fase 8: Habilitar autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="dc5d9-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="dc5d9-145">Para Exchange Online, siga [estas instrucciones](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="dc5d9-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="dc5d9-146">Para Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="dc5d9-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="dc5d9-147">Conéctese a [Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="dc5d9-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="dc5d9-148">Ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="dc5d9-149">Compruebe que el cambio se realizó correctamente con este comando.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="dc5d9-150">El resultado es un entorno de prueba que cumple con los requisitos de la [Configuración de requisitos previos de autenticación de paso a través](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-150">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="dc5d9-151">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="dc5d9-151">Next step</span></span>

<span data-ttu-id="dc5d9-152">Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="dc5d9-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc5d9-153">Ver también</span><span class="sxs-lookup"><span data-stu-id="dc5d9-153">See also</span></span>

[<span data-ttu-id="dc5d9-154">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="dc5d9-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="dc5d9-155">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="dc5d9-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="dc5d9-156">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dc5d9-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="dc5d9-157">Información general de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dc5d9-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="dc5d9-158">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dc5d9-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

