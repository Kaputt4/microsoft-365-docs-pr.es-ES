---
title: Requisitos previos de acceso de dispositivos e identidades para la sincronización de hash de contraseña en su entorno de prueba de Microsoft 365
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
description: Crear un entorno de Microsoft 365 para probar el acceso de dispositivos e identidades con los requisitos previos para la autenticación de sincronización de hash de contraseña.
ms.openlocfilehash: 6aa6b1cd1b8f9459b27e46fa67c62b35014b2d7e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686255"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="2f920-103">Requisitos previos de acceso de dispositivos e identidades para la sincronización de hash de contraseña en su entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f920-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="2f920-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="2f920-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="2f920-105">Las [configuraciones de identidad y acceso a dispositivos](microsoft-365-policies-configurations.md) son un conjunto de configuraciones y directivas de acceso condicional para proteger el acceso a todos los servicios de Microsoft 365 para empresas que se integran con Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="2f920-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="2f920-106">Este artículo describe cómo configurar un entorno de prueba de Microsoft 365 que cumpla los requisitos del [Active Directory con la configuración de requisitos previos de sincronización de hash de contraseña](identity-access-prerequisites.md#prerequisites) para acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="2f920-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="2f920-107">Existen ocho fases para configurar el entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="2f920-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="2f920-108">Crear una empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2f920-108">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="2f920-109">Configurar el inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="2f920-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="2f920-110">Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="2f920-110">Configure named locations</span></span>
4.  <span data-ttu-id="2f920-111">Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2f920-111">Configure password writeback</span></span>
5.  <span data-ttu-id="2f920-112">Configurar el autoservicio de restablecimiento de contraseñas para todas las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="2f920-112">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="2f920-113">Configurar la autenticación multifactor para todas las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="2f920-113">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="2f920-114">Habilitar Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="2f920-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="2f920-115">Habilitar la autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2f920-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="2f920-116">Fase 1: Crear una empresa simulada con la sincronización de hash de contraseñas en el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f920-116">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="2f920-117">Siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2f920-117">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="2f920-118">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="2f920-118">Here is the resulting configuration.</span></span>

![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="2f920-120">Fase 2: Configurar inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="2f920-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="2f920-121">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 del inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="2f920-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="2f920-122">Fase 3: Configurar ubicaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="2f920-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="2f920-123">En primer lugar, determine las direcciones IP públicas o el intervalo de direcciones usadas por su organización.</span><span class="sxs-lookup"><span data-stu-id="2f920-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="2f920-124">A continuación, siga las instrucciones de [Configurar ubicaciones con nombre en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para agregar las direcciones o intervalos de direcciones como ubicaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="2f920-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="2f920-125">Fase 4: Configurar la escritura diferida de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2f920-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="2f920-126">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="2f920-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="2f920-127">Fase 5: Configurar el autoservicio de restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="2f920-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="2f920-128">Siga las instrucciones en la [Guía de entorno de pruebas, fase 3 de la operación de restablecimiento de contraseña](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="2f920-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="2f920-129">Al habilitar la contraseña para las cuentas en un determinado grupo de Azure AD, agregue estas cuentas al grupo de **Restablecimiento de contraseña**:</span><span class="sxs-lookup"><span data-stu-id="2f920-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="2f920-130">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="2f920-130">User 2</span></span>
- <span data-ttu-id="2f920-131">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="2f920-131">User 3</span></span>
- <span data-ttu-id="2f920-132">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="2f920-132">User 4</span></span>
- <span data-ttu-id="2f920-133">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="2f920-133">User 5</span></span>

<span data-ttu-id="2f920-134">Pruebe el restablecimiento de contraseña solo de la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="2f920-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="2f920-135">Fase 6: Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="2f920-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="2f920-136">Siga las instrucciones en [Guía del laboratorio de pruebas, fase 2 de la autenticación multifactor ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para las cuentas de usuario siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f920-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="2f920-137">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="2f920-137">User 2</span></span>
- <span data-ttu-id="2f920-138">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="2f920-138">User 3</span></span>
- <span data-ttu-id="2f920-139">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="2f920-139">User 4</span></span>
- <span data-ttu-id="2f920-140">Usuario 5</span><span class="sxs-lookup"><span data-stu-id="2f920-140">User 5</span></span>

<span data-ttu-id="2f920-141">Pruebe la autenticación multifactor solo para la cuenta Usuario 2.</span><span class="sxs-lookup"><span data-stu-id="2f920-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="2f920-142">Fase 7: Habilitación de Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="2f920-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="2f920-143">Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="2f920-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="2f920-144">Fase 8: Habilitar autenticación moderna para Exchange Online y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2f920-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="2f920-145">Para Exchange Online, siga [estas instrucciones](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="2f920-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="2f920-146">Para Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="2f920-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="2f920-147">Conéctese a [Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="2f920-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="2f920-148">Ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="2f920-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="2f920-149">Compruebe que el cambio se realizó correctamente con este comando.</span><span class="sxs-lookup"><span data-stu-id="2f920-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="2f920-150">El resultado es un entorno de prueba que cumple los requisitos de [Active Directory con la configuración de requisitos previos de sincronización de hash de contraseña](identity-access-prerequisites.md#prerequisites) para acceso de dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="2f920-150">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="2f920-151">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2f920-151">Next step</span></span>

<span data-ttu-id="2f920-152">Use [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) para configurar las directivas que se basan en los requisitos previos y protegen dispositivos e identidades.</span><span class="sxs-lookup"><span data-stu-id="2f920-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f920-153">Ver también</span><span class="sxs-lookup"><span data-stu-id="2f920-153">See also</span></span>

[<span data-ttu-id="2f920-154">Guías de laboratorio de pruebas de identidad adicionales</span><span class="sxs-lookup"><span data-stu-id="2f920-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="2f920-155">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="2f920-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="2f920-156">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2f920-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2f920-157">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2f920-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2f920-158">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2f920-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
