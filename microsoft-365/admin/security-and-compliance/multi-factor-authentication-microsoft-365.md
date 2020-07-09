---
title: Autenticación multifactor para Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información acerca de la autenticación multifactor en Microsoft 365.
ms.openlocfilehash: 71a61c51d2813880cad782d132679fa413ada987
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083591"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="f9aad-103">Autenticación multifactor para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9aad-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="f9aad-104">Las contraseñas son el método más común para autenticar un inicio de sesión en un equipo o servicio en línea, pero también son los más vulnerables.</span><span class="sxs-lookup"><span data-stu-id="f9aad-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="f9aad-105">Los usuarios pueden elegir contraseñas sencillas y usar las mismas contraseñas para varios inicios de sesión en diferentes equipos y servicios.</span><span class="sxs-lookup"><span data-stu-id="f9aad-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="f9aad-106">Para proporcionar un nivel de seguridad adicional para los inicios de sesión, debe usar la autenticación multifactor (MFA), que usa una contraseña, que debe ser segura, y un método de verificación adicional basado en:</span><span class="sxs-lookup"><span data-stu-id="f9aad-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="f9aad-107">Algo que tiene con usted que no se duplica fácilmente, como un smartphone.</span><span class="sxs-lookup"><span data-stu-id="f9aad-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="f9aad-108">Algo que tiene de forma única y biológica, como sus huellas dactilares, rostro u otro atributo de biométrica.</span><span class="sxs-lookup"><span data-stu-id="f9aad-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="f9aad-109">El método de verificación adicional no se emplea hasta que se haya comprobado la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="f9aad-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="f9aad-110">Con MFA, incluso si una contraseña de usuario segura se ve comprometida, el atacante no tiene el teléfono inteligente ni la huella digital para completar el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="f9aad-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="f9aad-111">Compatibilidad con MFA en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9aad-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="f9aad-112">De forma predeterminada, tanto Microsoft 365 como Office 365 admiten MFA para las cuentas de usuario mediante:</span><span class="sxs-lookup"><span data-stu-id="f9aad-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="f9aad-113">Mensaje de texto enviado a un teléfono que requiere que el usuario escriba un código de verificación.</span><span class="sxs-lookup"><span data-stu-id="f9aad-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="f9aad-114">Una llamada de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f9aad-114">A phone call.</span></span>
- <span data-ttu-id="f9aad-115">La aplicación Microsoft Authenticator Smart Phone.</span><span class="sxs-lookup"><span data-stu-id="f9aad-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="f9aad-116">En ambos casos, el inicio de sesión de MFA usa el método "algo que tiene con usted que no se duplica fácilmente" para la comprobación adicional.</span><span class="sxs-lookup"><span data-stu-id="f9aad-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="f9aad-117">Hay varias formas en las que puede habilitar MFA para Microsoft 365 y Office 365:</span><span class="sxs-lookup"><span data-stu-id="f9aad-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="f9aad-118">Con los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="f9aad-118">With security defaults</span></span>
- <span data-ttu-id="f9aad-119">Con directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="f9aad-119">With Conditional Access policies</span></span>
- <span data-ttu-id="f9aad-120">Para cada cuenta de usuario individual (no recomendado)</span><span class="sxs-lookup"><span data-stu-id="f9aad-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="f9aad-121">Estas formas se basan en el plan 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9aad-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="f9aad-122">Plan</span><span class="sxs-lookup"><span data-stu-id="f9aad-122">Plan</span></span>  |<span data-ttu-id="f9aad-123">Recomendación</span><span class="sxs-lookup"><span data-stu-id="f9aad-123">Recommendation</span></span>  | <span data-ttu-id="f9aad-124">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="f9aad-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="f9aad-125">Todos los planes de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9aad-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="f9aad-126">Use los valores predeterminados de seguridad, que requieren MFA para todas las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="f9aad-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="f9aad-127">También puede requerir MFA en cada cuenta de usuario, pero no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="f9aad-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="f9aad-128">Empresa pequeña</span><span class="sxs-lookup"><span data-stu-id="f9aad-128">Small business</span></span> |
| <span data-ttu-id="f9aad-129">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="f9aad-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="f9aad-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="f9aad-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="f9aad-131">Licencias de Azure Active Directory (Azure AD) Premium P1</span><span class="sxs-lookup"><span data-stu-id="f9aad-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="f9aad-132">Use las directivas de acceso condicional para requerir MFA para las cuentas de usuario en función de la pertenencia a grupos, las aplicaciones y otros criterios.</span><span class="sxs-lookup"><span data-stu-id="f9aad-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="f9aad-133">Pequeña empresa a empresarial</span><span class="sxs-lookup"><span data-stu-id="f9aad-133">Small business to enterprise</span></span> |
| <span data-ttu-id="f9aad-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f9aad-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="f9aad-135">Licencias de Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="f9aad-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="f9aad-136">Use Azure AD Identity Protection para requerir MFA en función de los criterios de inicio de sesión en el riesgo.</span><span class="sxs-lookup"><span data-stu-id="f9aad-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="f9aad-137">Empresa</span><span class="sxs-lookup"><span data-stu-id="f9aad-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="f9aad-138">Valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="f9aad-138">Security defaults</span></span>

<span data-ttu-id="f9aad-139">Los valores predeterminados de seguridad son una nueva característica para las suscripciones pago o de prueba de Microsoft 365 y Office 365 creadas después del 21 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="f9aad-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="f9aad-140">Estas suscripciones tienen valores predeterminados de seguridad activados, lo que:</span><span class="sxs-lookup"><span data-stu-id="f9aad-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="f9aad-141">Requiere que todos los usuarios usen MFA con la aplicación Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="f9aad-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="f9aad-142">Bloquea la autenticación heredada.</span><span class="sxs-lookup"><span data-stu-id="f9aad-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="f9aad-143">Los usuarios tienen 14 días para registrarse en MFA con la aplicación Microsoft Authenticator desde sus teléfonos inteligentes, que comienzan a contar desde la primera vez que inician sesión después de que se hayan habilitado los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f9aad-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="f9aad-144">Transcurridos 14 días, el usuario no podrá iniciar sesión hasta que el registro de MFA se haya completado.</span><span class="sxs-lookup"><span data-stu-id="f9aad-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="f9aad-145">Los valores predeterminados de seguridad garantizan que todas las organizaciones tengan un nivel básico de seguridad para el inicio de sesión de usuario habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f9aad-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="f9aad-146">Puede deshabilitar los valores predeterminados de seguridad en favor de MFA con directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="f9aad-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="f9aad-147">Los valores predeterminados de seguridad se habilitan o deshabilitan en el panel **propiedades** de Azure ad en Azure portal.</span><span class="sxs-lookup"><span data-stu-id="f9aad-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Imagen de la página de propiedades del directorio.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="f9aad-149">Puede usar los valores predeterminados de seguridad con cualquier plan de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9aad-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="f9aad-150">Para más información, vea esta [información general de los valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="f9aad-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="f9aad-151">Directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="f9aad-151">Conditional Access policies</span></span>

<span data-ttu-id="f9aad-152">Las directivas de acceso condicional son un conjunto de reglas que especifican las condiciones en las que se evalúan y permiten los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="f9aad-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="f9aad-153">Por ejemplo, puede crear una directiva de acceso condicional que indique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9aad-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="f9aad-154">Si el nombre de la cuenta de usuario es miembro de un grupo de usuarios a los que se han asignado los roles de administrador de Exchange, de usuarios, de contraseñas, de seguridad, de SharePoint o global, requerir MFA antes de permitir el acceso.</span><span class="sxs-lookup"><span data-stu-id="f9aad-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="f9aad-155">Esta directiva le permite exigir MFA en función de la pertenencia a grupos, en lugar de intentar configurar cuentas de usuario individuales para MFA cuando se asignan o se quitan estos roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="f9aad-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="f9aad-156">También puede usar directivas de acceso condicional para capacidades más avanzadas, como requerir MFA para aplicaciones específicas o que el inicio de sesión se realice desde un dispositivo compatible, como el portátil que ejecuta Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f9aad-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="f9aad-157">Las directivas de acceso condicional se configuran desde el panel **seguridad** de Azure ad en Azure portal.</span><span class="sxs-lookup"><span data-stu-id="f9aad-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Picure de la opción de menú para el acceso condicional](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="f9aad-159">Puede usar directivas de acceso condicional con:</span><span class="sxs-lookup"><span data-stu-id="f9aad-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="f9aad-160">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="f9aad-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="f9aad-161">Microsoft 365 E3 y E5</span><span class="sxs-lookup"><span data-stu-id="f9aad-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="f9aad-162">Licencias de Azure AD Premium P1 y Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="f9aad-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="f9aad-163">Para las pequeñas empresas con Microsoft 365 empresa Premium, puede usar fácilmente las directivas de acceso condicional con los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9aad-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="f9aad-164">Cree un grupo que contenga las cuentas de usuario que requieren MFA.</span><span class="sxs-lookup"><span data-stu-id="f9aad-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="f9aad-165">Habilite la directiva **solicitar MFA para administradores globales** .</span><span class="sxs-lookup"><span data-stu-id="f9aad-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="f9aad-166">Cree una directiva de acceso condicional basada en grupos con estos valores:</span><span class="sxs-lookup"><span data-stu-id="f9aad-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="f9aad-167">Asignaciones > Users and Groups: el nombre del grupo del paso 1 anterior.</span><span class="sxs-lookup"><span data-stu-id="f9aad-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="f9aad-168">Tareas > aplicaciones o acciones en la nube: todas las aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="f9aad-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="f9aad-169">Los controles de acceso > conceder > conceder acceso > requieren la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="f9aad-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="f9aad-170">Habilite la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f9aad-170">Enable the policy.</span></span>
5. <span data-ttu-id="f9aad-171">Agregue una cuenta de usuario al grupo creado en el paso 1 y pruebe.</span><span class="sxs-lookup"><span data-stu-id="f9aad-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="f9aad-172">Para requerir MFA para las cuentas de usuario adicionales, agréguelos al grupo creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f9aad-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="f9aad-173">Esta directiva de acceso condicional permite aplicar el requisito de MFA a los usuarios a su propio ritmo.</span><span class="sxs-lookup"><span data-stu-id="f9aad-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="f9aad-174">Las empresas deben usar [directivas de acceso condicional comunes](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las siguientes directivas:</span><span class="sxs-lookup"><span data-stu-id="f9aad-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="f9aad-175">Requerir MFA para los administradores</span><span class="sxs-lookup"><span data-stu-id="f9aad-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="f9aad-176">Requerir MFA para todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="f9aad-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="f9aad-177">Bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="f9aad-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="f9aad-178">Para más información, vea esta [información general sobre el acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="f9aad-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="f9aad-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f9aad-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="f9aad-180">Con Azure AD Identity Protection, puede crear una directiva de acceso condicional adicional que [requiera MFA cuando el riesgo de inicio de sesión sea medio o alto](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="f9aad-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="f9aad-181">Puede usar la protección de identidad de Azure AD y las directivas de acceso condicional basadas en riesgos con:</span><span class="sxs-lookup"><span data-stu-id="f9aad-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="f9aad-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f9aad-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="f9aad-183">Licencias de Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="f9aad-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="f9aad-184">Para más información, vea esta [información general sobre la protección de identidad de Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="f9aad-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="f9aad-185">MFA para una cuenta de usuario individual (no recomendado)</span><span class="sxs-lookup"><span data-stu-id="f9aad-185">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="f9aad-186">Debe usar los valores predeterminados de seguridad o directivas de acceso condicional para requerir MFA para los inicios de sesión de la cuenta de usuario. Sin embargo, si no se puede usar cualquiera de estos, Microsoft recomienda MFA para las cuentas de usuario que tienen roles de administrador, especialmente el rol de administrador global, para cualquier suscripción de tamaño.</span><span class="sxs-lookup"><span data-stu-id="f9aad-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="f9aad-187">Habilite MFA para las cuentas de usuario individuales desde el panel de **usuario activo** del centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9aad-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Imagen de la opción de autenticación multifactor en la página usuarios activos](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="f9aad-189">Una vez habilitada, la próxima vez que el usuario inicie sesión, se le pedirá que se registre para MFA y que elija y pruebe el método de comprobación adicional.</span><span class="sxs-lookup"><span data-stu-id="f9aad-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="f9aad-190">Usar estos métodos conjuntamente</span><span class="sxs-lookup"><span data-stu-id="f9aad-190">Using these methods together</span></span>

<span data-ttu-id="f9aad-191">Esta tabla muestra los resultados de habilitar MFA con los valores predeterminados de seguridad, las directivas de acceso condicional y la configuración de cuenta por usuario.</span><span class="sxs-lookup"><span data-stu-id="f9aad-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="f9aad-192">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f9aad-192">Enabled</span></span> | <span data-ttu-id="f9aad-193">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f9aad-193">Disabled</span></span> | <span data-ttu-id="f9aad-194">Método de autenticación secundario</span><span class="sxs-lookup"><span data-stu-id="f9aad-194">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="f9aad-195">**Valores predeterminados de seguridad**</span><span class="sxs-lookup"><span data-stu-id="f9aad-195">**Security defaults**</span></span> | <span data-ttu-id="f9aad-196">No se pueden usar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="f9aad-196">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="f9aad-197">Se pueden usar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="f9aad-197">Can use Conditional Access policies</span></span> | <span data-ttu-id="f9aad-198">Aplicación Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="f9aad-198">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="f9aad-199">**Directivas de acceso condicional**</span><span class="sxs-lookup"><span data-stu-id="f9aad-199">**Conditional Access policies**</span></span> |<span data-ttu-id="f9aad-200">Si hay alguna habilitada, no puede habilitar los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="f9aad-200">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="f9aad-201">Si se deshabilitan todos, puede habilitar los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="f9aad-201">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="f9aad-202">Especificado por el usuario durante el registro de MFA</span><span class="sxs-lookup"><span data-stu-id="f9aad-202">User-specified during MFA registration</span></span> |
| <span data-ttu-id="f9aad-203">**Configuración de cuenta por usuario (no recomendado)**</span><span class="sxs-lookup"><span data-stu-id="f9aad-203">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="f9aad-204">Invalida los valores predeterminados de seguridad y las directivas de acceso condicional que requieren MFA en cada inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="f9aad-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span> | <span data-ttu-id="f9aad-205">Invalidados por los valores predeterminados de seguridad y directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="f9aad-205">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="f9aad-206">Especificado por el usuario durante el registro de MFA</span><span class="sxs-lookup"><span data-stu-id="f9aad-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="f9aad-207">Si se habilitan los valores predeterminados de seguridad, todos los usuarios nuevos se solicitarán para el registro de MFA y el uso de la aplicación Microsoft Authenticator en el siguiente inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="f9aad-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="f9aad-208">Formas de administrar la configuración de MFA</span><span class="sxs-lookup"><span data-stu-id="f9aad-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="f9aad-209">Hay dos formas de administrar la configuración de MFA.</span><span class="sxs-lookup"><span data-stu-id="f9aad-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="f9aad-210">En Azure portal, puede:</span><span class="sxs-lookup"><span data-stu-id="f9aad-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="f9aad-211">Habilitar y deshabilitar los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="f9aad-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="f9aad-212">Configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="f9aad-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="f9aad-213">En el centro de administración de Microsoft 365, puede configurar las opciones de configuración de MFA por usuario y servicio.</span><span class="sxs-lookup"><span data-stu-id="f9aad-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="f9aad-214">El siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f9aad-214">Your next step</span></span>

[<span data-ttu-id="f9aad-215">Configurar MFA para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9aad-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

