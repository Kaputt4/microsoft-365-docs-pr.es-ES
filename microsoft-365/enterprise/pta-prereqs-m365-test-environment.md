---
title: Requisitos previos de acceso de dispositivos e identidades para la autenticación de paso a través en el entorno de prueba de Microsoft 365
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
description: Cree un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos para la autenticación de paso a través.
ms.openlocfilehash: b8c9ebefacf81293b553aecf8ead0a387c18758b
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073030"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="5fd96-103">Requisitos previos de acceso de dispositivos e identidades para la autenticación de paso a través en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5fd96-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5fd96-104">La [Configuración de acceso de dispositivos e identidades](microsoft-365-policies-configurations.md) es un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios que se integran con Azure Active Directory (Azure AD), incluidos Office 365 y Enterprise Mobility + Security (EMS) en Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5fd96-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="5fd96-105">Este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumple con los requisitos de la [Configuración de requisitos previos de la autenticación de paso a través](identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="5fd96-105">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="5fd96-106">Existen ocho fases para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="5fd96-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="5fd96-107">Crear una empresa simulada con el entorno de prueba de Microsoft 365 de autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="5fd96-107">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="5fd96-108">Configurar el inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5fd96-108">Configure Azure AD single sign-on</span></span>
3.  <span data-ttu-id="5fd96-109">Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="5fd96-109">Configure named locations</span></span>
4.  <span data-ttu-id="5fd96-110">Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="5fd96-110">Configure password writeback</span></span>
5.  <span data-ttu-id="5fd96-111">Configurar el autoservicio de restablecimiento de contraseñas</span><span class="sxs-lookup"><span data-stu-id="5fd96-111">Configure self-service password reset</span></span>
6.  <span data-ttu-id="5fd96-112">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="5fd96-112">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="5fd96-113">Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5fd96-113">Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="5fd96-114">Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5fd96-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="5fd96-115">Fase 1: Crear una empresa simulada con el entorno de prueba de Microsoft 365 de autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="5fd96-115">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="5fd96-116">Siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5fd96-116">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="5fd96-117">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="5fd96-117">Here is the resulting configuration.</span></span>

![La empresa simulada con el entorno de prueba de la autenticación de paso a través](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="5fd96-119">Fase 2: Configurar el inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5fd96-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="5fd96-120">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 del inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="5fd96-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="5fd96-121">Fase 3: Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="5fd96-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="5fd96-122">En primer lugar, determine las direcciones IP públicas o el intervalo de direcciones usadas por su organización.</span><span class="sxs-lookup"><span data-stu-id="5fd96-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="5fd96-123">A continuación, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o intervalos de direcciones como ubicaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="5fd96-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="5fd96-124">Fase 4: Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="5fd96-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="5fd96-125">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="5fd96-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="5fd96-126">Fase 5: Configurar el autoservicio de restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="5fd96-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="5fd96-127">Siga las instrucciones en la [Guía de entorno de pruebas, fase 3 de la operación de restablecimiento de contraseña](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="5fd96-127">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="5fd96-128">Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:</span><span class="sxs-lookup"><span data-stu-id="5fd96-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="5fd96-129">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="5fd96-129">User: %2</span></span>
- <span data-ttu-id="5fd96-130">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="5fd96-130">User Defined 3</span></span>
- <span data-ttu-id="5fd96-131">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="5fd96-131">User: %4</span></span>
- <span data-ttu-id="5fd96-132">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="5fd96-132">User 5</span></span>

<span data-ttu-id="5fd96-133">Pruebe el restablecimiento de contraseña solo de la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="5fd96-133">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="5fd96-134">Fase 6: Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="5fd96-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="5fd96-135">Siga las instrucciones en [Guía del laboratorio de pruebas, fase 2 de la autenticación multifactor ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fd96-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="5fd96-136">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="5fd96-136">User: %2</span></span>
- <span data-ttu-id="5fd96-137">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="5fd96-137">User Defined 3</span></span>
- <span data-ttu-id="5fd96-138">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="5fd96-138">User: %4</span></span>
- <span data-ttu-id="5fd96-139">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="5fd96-139">User 5</span></span>

<span data-ttu-id="5fd96-140">Pruebe la autenticación multifactor solo para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="5fd96-140">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="5fd96-141">Fase 7: Habilitación de Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5fd96-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="5fd96-142">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="5fd96-142">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="5fd96-143">Fase 8: Habilitar autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5fd96-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="5fd96-144">Para Exchange Online, siga [estas instrucciones](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="5fd96-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="5fd96-145">Para Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="5fd96-145">Skype for Business Online</span></span>

1. <span data-ttu-id="5fd96-146">Conéctese a [Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="5fd96-146">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="5fd96-147">Ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="5fd96-147">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="5fd96-148">Compruebe que el cambio se realizó correctamente con este comando.</span><span class="sxs-lookup"><span data-stu-id="5fd96-148">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="5fd96-149">El resultado es un entorno de prueba que cumple con los requisitos de la [Configuración de requisitos previos de autenticación de paso a través](identity-access-prerequisites.md#prerequisites) para el acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="5fd96-149">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="5fd96-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5fd96-150">Next step</span></span>

<span data-ttu-id="5fd96-151">Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="5fd96-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fd96-152">Ver también</span><span class="sxs-lookup"><span data-stu-id="5fd96-152">See also</span></span>

[<span data-ttu-id="5fd96-153">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="5fd96-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="5fd96-154">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="5fd96-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="5fd96-155">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5fd96-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5fd96-156">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5fd96-156">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5fd96-157">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5fd96-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

