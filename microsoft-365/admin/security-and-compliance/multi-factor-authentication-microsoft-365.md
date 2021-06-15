---
title: Autenticación multifactor para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: La autenticación multifactor (MFA) usa una contraseña, que debe ser segura, y un método de comprobación adicional.
ms.openlocfilehash: d9af486cf5e53609557b519612f185a20729cf76
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924736"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="6d385-103">Autenticación multifactor para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d385-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="6d385-104">Las contraseñas son el método más común para autenticar un inicio de sesión en un equipo o servicio en línea, pero también son las más vulnerables.</span><span class="sxs-lookup"><span data-stu-id="6d385-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="6d385-105">Los usuarios pueden elegir contraseñas fáciles y usar las mismas contraseñas para varios inicios de sesión en diferentes equipos y servicios.</span><span class="sxs-lookup"><span data-stu-id="6d385-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="6d385-106">Para proporcionar un nivel adicional de seguridad para los inicios de sesión, debe usar la autenticación multifactor (MFA), que usa una contraseña, que debe ser segura, y un método de comprobación adicional basado en:</span><span class="sxs-lookup"><span data-stu-id="6d385-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="6d385-107">Algo que tiene con usted que no se duplica fácilmente, como un teléfono inteligente.</span><span class="sxs-lookup"><span data-stu-id="6d385-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="6d385-108">Algo que tiene de forma única y biológica, como sus huellas digitales, rostro u otro atributo biométrico.</span><span class="sxs-lookup"><span data-stu-id="6d385-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="6d385-109">El método de comprobación adicional no se emplea hasta después de comprobar la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="6d385-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="6d385-110">Con MFA, incluso si se pone en peligro una contraseña de usuario segura, el atacante no tiene el teléfono inteligente ni la huella digital para completar el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6d385-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="6d385-111">Compatibilidad con MFA en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d385-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="6d385-112">De forma predeterminada, tanto Microsoft 365 como Office 365 mfa para cuentas de usuario que usan:</span><span class="sxs-lookup"><span data-stu-id="6d385-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="6d385-113">Un mensaje de texto enviado a un teléfono que requiere que el usuario escriba un código de verificación.</span><span class="sxs-lookup"><span data-stu-id="6d385-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="6d385-114">Una llamada telefónica.</span><span class="sxs-lookup"><span data-stu-id="6d385-114">A phone call.</span></span>
- <span data-ttu-id="6d385-115">La Microsoft Authenticator de teléfono inteligente.</span><span class="sxs-lookup"><span data-stu-id="6d385-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="6d385-116">En ambos casos, el inicio de sesión de MFA usa el método "algo que tienes contigo que no se duplica fácilmente" para la comprobación adicional.</span><span class="sxs-lookup"><span data-stu-id="6d385-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="6d385-117">Hay varias maneras de habilitar MFA para Microsoft 365 y Office 365:</span><span class="sxs-lookup"><span data-stu-id="6d385-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="6d385-118">Con valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="6d385-118">With security defaults</span></span>
- <span data-ttu-id="6d385-119">Con directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="6d385-119">With Conditional Access policies</span></span>
- <span data-ttu-id="6d385-120">Para cada cuenta de usuario individual (no recomendada)</span><span class="sxs-lookup"><span data-stu-id="6d385-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="6d385-121">Estas formas se basan en su Microsoft 365 plan.</span><span class="sxs-lookup"><span data-stu-id="6d385-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="6d385-122">Plan</span><span class="sxs-lookup"><span data-stu-id="6d385-122">Plan</span></span>|<span data-ttu-id="6d385-123">Recomendación</span><span class="sxs-lookup"><span data-stu-id="6d385-123">Recommendation</span></span>|<span data-ttu-id="6d385-124">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="6d385-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="6d385-125">Todos Microsoft 365 planes</span><span class="sxs-lookup"><span data-stu-id="6d385-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="6d385-126">Use valores predeterminados de seguridad, que requieren MFA para todas las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="6d385-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="6d385-127">También puede configurar MFA por usuario en cuentas de usuario individuales, pero esto no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="6d385-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="6d385-128">Empresa pequeña</span><span class="sxs-lookup"><span data-stu-id="6d385-128">Small business</span></span>|
|<span data-ttu-id="6d385-129">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="6d385-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="6d385-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="6d385-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="6d385-131">Azure Active Directory (Azure AD) Premium licencias P1</span><span class="sxs-lookup"><span data-stu-id="6d385-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="6d385-132">Use directivas de acceso condicional para requerir MFA para cuentas de usuario basadas en la pertenencia a grupos, aplicaciones u otros criterios.</span><span class="sxs-lookup"><span data-stu-id="6d385-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="6d385-133">Pequeña empresa a empresa</span><span class="sxs-lookup"><span data-stu-id="6d385-133">Small business to enterprise</span></span>|
|<span data-ttu-id="6d385-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6d385-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="6d385-135">Licencias Premium P2 de Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d385-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="6d385-136">Use Azure AD Identity Protection para requerir MFA en función de los criterios de riesgo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6d385-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="6d385-137">Empresa</span><span class="sxs-lookup"><span data-stu-id="6d385-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="6d385-138">Valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="6d385-138">Security defaults</span></span>

<span data-ttu-id="6d385-139">Los valores predeterminados de seguridad son una nueva característica para las suscripciones pago o de prueba de Microsoft 365 y Office 365 creadas después del 21 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="6d385-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="6d385-140">Estas suscripciones tienen activados los valores predeterminados de seguridad, que:</span><span class="sxs-lookup"><span data-stu-id="6d385-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="6d385-141">Requiere que todos los usuarios usen MFA con la Microsoft Authenticator aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d385-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="6d385-142">Bloquea la autenticación heredada.</span><span class="sxs-lookup"><span data-stu-id="6d385-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="6d385-143">Los usuarios tienen 14 días para registrarse en MFA con la aplicación Microsoft Authenticator desde sus teléfonos inteligentes, que comienzan a contar desde la primera vez que inician sesión después de que se hayan habilitado los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6d385-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="6d385-144">Transcurridos 14 días, el usuario no podrá iniciar sesión hasta que el registro de MFA se haya completado.</span><span class="sxs-lookup"><span data-stu-id="6d385-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="6d385-145">Los valores predeterminados de seguridad garantizan que todas las organizaciones tengan un nivel básico de seguridad para el inicio de sesión de usuario habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6d385-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="6d385-146">Puede deshabilitar los valores predeterminados de seguridad a favor de MFA con directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="6d385-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="6d385-147">Los valores predeterminados de seguridad se habilitan o deshabilitan en el panel **Propiedades** de Azure AD en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="6d385-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Imagen de la página Propiedades del directorio.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="6d385-149">Puede usar valores predeterminados de seguridad con cualquier Microsoft 365 plan.</span><span class="sxs-lookup"><span data-stu-id="6d385-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="6d385-150">Para más información, vea esta [información general de los valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="6d385-150">For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="6d385-151">Directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="6d385-151">Conditional Access policies</span></span>

<span data-ttu-id="6d385-152">Las directivas de acceso condicional son un conjunto de reglas que especifican las condiciones en las que se evalúan y permiten los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="6d385-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="6d385-153">Por ejemplo, puede crear una directiva de acceso condicional que indique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d385-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="6d385-154">Si el nombre de la cuenta de usuario es miembro de un grupo de usuarios a los que se han asignado los roles de administrador de Exchange, de usuarios, de contraseñas, de seguridad, de SharePoint o global, requerir MFA antes de permitir el acceso.</span><span class="sxs-lookup"><span data-stu-id="6d385-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="6d385-155">Esta directiva le permite exigir MFA en función de la pertenencia a grupos, en lugar de intentar configurar cuentas de usuario individuales para MFA cuando se asignan o se quitan estos roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="6d385-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="6d385-156">También puedes usar directivas de acceso condicional para funcionalidades más avanzadas, como requerir MFA para aplicaciones específicas o que el inicio de sesión se realiza desde un dispositivo compatible, como el portátil que ejecuta Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6d385-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="6d385-157">Las directivas de acceso condicional se configuran **desde** el panel Seguridad de Azure AD en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="6d385-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Imagen de la opción de menú para acceso condicional](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="6d385-159">Puede usar directivas de acceso condicional con:</span><span class="sxs-lookup"><span data-stu-id="6d385-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="6d385-160">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="6d385-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="6d385-161">Microsoft 365 E3 y E5</span><span class="sxs-lookup"><span data-stu-id="6d385-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="6d385-162">Licencias de Azure AD Premium P1 y Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="6d385-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="6d385-163">Para pequeñas empresas con Microsoft 365 Empresa Premium, puede usar fácilmente directivas de acceso condicional con los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="6d385-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="6d385-164">Cree un grupo para contener las cuentas de usuario que requieren MFA.</span><span class="sxs-lookup"><span data-stu-id="6d385-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="6d385-165">Habilite la **directiva Requerir MFA para administradores** globales.</span><span class="sxs-lookup"><span data-stu-id="6d385-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="6d385-166">Cree una directiva de acceso condicional basada en grupos con esta configuración:</span><span class="sxs-lookup"><span data-stu-id="6d385-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="6d385-167">Asignaciones > usuarios y grupos: el nombre del grupo del paso 1 anterior.</span><span class="sxs-lookup"><span data-stu-id="6d385-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="6d385-168">Asignaciones > o acciones en la nube: todas las aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="6d385-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="6d385-169">Controles de > conceder > conceder acceso > Requerir autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="6d385-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="6d385-170">Habilite la directiva.</span><span class="sxs-lookup"><span data-stu-id="6d385-170">Enable the policy.</span></span>
5. <span data-ttu-id="6d385-171">Agregue una cuenta de usuario al grupo creado en el paso 1 anterior y pruebe.</span><span class="sxs-lookup"><span data-stu-id="6d385-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="6d385-172">Para requerir MFA para cuentas de usuario adicionales, agrégrelas al grupo creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="6d385-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="6d385-173">Esta directiva de acceso condicional le permite implantar el requisito de MFA a los usuarios a su propio ritmo.</span><span class="sxs-lookup"><span data-stu-id="6d385-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="6d385-174">Las empresas deben usar [directivas comunes de acceso condicional](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las siguientes directivas:</span><span class="sxs-lookup"><span data-stu-id="6d385-174">Enterprises should use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="6d385-175">Requerir MFA para los administradores</span><span class="sxs-lookup"><span data-stu-id="6d385-175">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="6d385-176">Requerir MFA para todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="6d385-176">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="6d385-177">Bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="6d385-177">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="6d385-178">Para más información, vea esta [información general sobre el acceso condicional](/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="6d385-178">For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="6d385-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="6d385-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="6d385-180">Con Azure AD Identity Protection, puede crear una directiva de acceso condicional adicional para requerir MFA cuando el riesgo de inicio de sesión [es medio o alto.](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="6d385-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="6d385-181">Puede usar Azure AD Identity Protection y directivas de acceso condicional basadas en riesgos con:</span><span class="sxs-lookup"><span data-stu-id="6d385-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="6d385-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6d385-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="6d385-183">Licencias Premium P2 de Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d385-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="6d385-184">Para más información, vea esta [información general sobre la protección de identidad de Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="6d385-184">For more information, see this [overview of Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="6d385-185">MFA heredada por usuario (no recomendada)</span><span class="sxs-lookup"><span data-stu-id="6d385-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="6d385-186">Debe usar los valores predeterminados de seguridad o las directivas de acceso condicional para requerir MFA para los inicios de sesión de la cuenta de usuario. Sin embargo, si cualquiera de estos no se puede usar, Microsoft recomienda encarecidamente MFA para cuentas de usuario que tienen roles de administrador, especialmente el rol de administrador global, para cualquier suscripción de tamaño.</span><span class="sxs-lookup"><span data-stu-id="6d385-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="6d385-187">Puede habilitar MFA para cuentas de usuario individuales desde el **panel usuario** activo del centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="6d385-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Imagen de la opción de autenticación multifactor en la página Usuarios activos](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="6d385-189">Después de habilitarse, la próxima vez que el usuario inicia sesión, se le pedirá que se registre en MFA y que elija y pruebe el método de comprobación adicional.</span><span class="sxs-lookup"><span data-stu-id="6d385-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="6d385-190">Usar estos métodos conjuntamente</span><span class="sxs-lookup"><span data-stu-id="6d385-190">Using these methods together</span></span>

<span data-ttu-id="6d385-191">Esta tabla muestra los resultados de habilitar MFA con los valores predeterminados de seguridad, las directivas de acceso condicional y la configuración de cuenta por usuario.</span><span class="sxs-lookup"><span data-stu-id="6d385-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|<span data-ttu-id="6d385-192">*Elemento*</span><span class="sxs-lookup"><span data-stu-id="6d385-192">*Item*</span></span>|<span data-ttu-id="6d385-193">Habilitado</span><span class="sxs-lookup"><span data-stu-id="6d385-193">Enabled</span></span>|<span data-ttu-id="6d385-194">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6d385-194">Disabled</span></span>|<span data-ttu-id="6d385-195">Método de autenticación secundario</span><span class="sxs-lookup"><span data-stu-id="6d385-195">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="6d385-196">**Valores predeterminados de seguridad**</span><span class="sxs-lookup"><span data-stu-id="6d385-196">**Security defaults**</span></span>|<span data-ttu-id="6d385-197">No se pueden usar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="6d385-197">Can't use Conditional Access policies</span></span>|<span data-ttu-id="6d385-198">Se pueden usar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="6d385-198">Can use Conditional Access policies</span></span>|<span data-ttu-id="6d385-199">Aplicación Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="6d385-199">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="6d385-200">**Directivas de acceso condicional**</span><span class="sxs-lookup"><span data-stu-id="6d385-200">**Conditional Access policies**</span></span>|<span data-ttu-id="6d385-201">Si hay alguno habilitado, no puede habilitar los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="6d385-201">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="6d385-202">Si se deshabilitan todos, puede habilitar los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="6d385-202">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="6d385-203">Especificado por el usuario durante el registro de MFA</span><span class="sxs-lookup"><span data-stu-id="6d385-203">User-specified during MFA registration</span></span>|
|<span data-ttu-id="6d385-204">**MFA heredada por usuario (no recomendada)**</span><span class="sxs-lookup"><span data-stu-id="6d385-204">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="6d385-205">Invalida los valores predeterminados de seguridad y las directivas de acceso condicional que requieren MFA en cada inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="6d385-205">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="6d385-206">Invalidadas por valores predeterminados de seguridad y directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="6d385-206">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="6d385-207">Especificado por el usuario durante el registro de MFA</span><span class="sxs-lookup"><span data-stu-id="6d385-207">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="6d385-208">Si los valores predeterminados de seguridad están habilitados, se pedirá a todos los usuarios nuevos el registro de MFA y el uso de la aplicación Microsoft Authenticator en su siguiente inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6d385-208">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="6d385-209">Formas de administrar la configuración de MFA</span><span class="sxs-lookup"><span data-stu-id="6d385-209">Ways to manage MFA settings</span></span>

<span data-ttu-id="6d385-210">Hay dos formas de administrar la configuración de MFA.</span><span class="sxs-lookup"><span data-stu-id="6d385-210">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="6d385-211">En Azure Portal, puede:</span><span class="sxs-lookup"><span data-stu-id="6d385-211">In the Azure portal, you can:</span></span>

- <span data-ttu-id="6d385-212">Habilitar y deshabilitar valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="6d385-212">Enable and disable security defaults</span></span>
- <span data-ttu-id="6d385-213">Configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="6d385-213">Configure Conditional Access policies</span></span>

<span data-ttu-id="6d385-214">En el centro Microsoft 365 administración, puede configurar la configuración de MFA por usuario y servicio.</span><span class="sxs-lookup"><span data-stu-id="6d385-214">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6d385-215">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6d385-215">Next steps</span></span>

[<span data-ttu-id="6d385-216">Configurar MFA para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d385-216">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-content"></a><span data-ttu-id="6d385-217">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="6d385-217">Related content</span></span>

<span data-ttu-id="6d385-218">[Activar la autenticación multifactor](../../business-video/turn-on-mfa.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="6d385-218">[Turn on multi-factor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>\
<span data-ttu-id="6d385-219">[Activar la autenticación multifactor para su teléfono (Vídeo)](../../business-video/set-up-mfa.md)</span><span class="sxs-lookup"><span data-stu-id="6d385-219">[Turn on multi-factor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>