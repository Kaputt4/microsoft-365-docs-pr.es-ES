---
title: 'Paso 5: Configurar la autenticación multifactor'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la autenticación multifactor para las cuentas de usuario.
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871643"
---
# <a name="step-5-set-up-multi-factor-authentication"></a><span data-ttu-id="94218-103">Paso 5: Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="94218-103">Step 5: Set up multi-factor authentication</span></span>

<span data-ttu-id="94218-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="94218-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="94218-p101">En este paso, configurará la autenticación multifactor (MFA) para agregar un segundo nivel de seguridad en las transacciones y los inicios de sesión de usuario. MFA necesita un método de verificación adicional después de que los usuarios escriban correctamente la contraseña. Sin MFA, la contraseña es el único método de verificación. El problema de las contraseñas es que un atacante podría adivinar fácilmente muchas de ellas, o bien se pueden compartir de manera inadvertida con partes que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="94218-p101">In Step 7, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="94218-109">Con MFA, el segundo nivel de seguridad puede ser:</span><span class="sxs-lookup"><span data-stu-id="94218-109">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="94218-110">Un dispositivo personal y de confianza que no se pueda suplantar o duplicar fácilmente, como un smartphone.</span><span class="sxs-lookup"><span data-stu-id="94218-110">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="94218-111">Un atributo biométrico, como una huella digital.</span><span class="sxs-lookup"><span data-stu-id="94218-111">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="94218-p102">Habilitará MFA y configurará el método de autenticación secundario en cada cuenta de usuario. Asegúrese de informar a los usuarios de que se habilitará MFA para que comprendan los requisitos (como el uso obligatorio de un smartphone para iniciar sesión) y que puedan iniciar sesión correctamente.</span><span class="sxs-lookup"><span data-stu-id="94218-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements (such as mandatory use of a smart phone to sign in) and can sign in successfully.</span></span>

<span data-ttu-id="94218-114">Para obtener más información, vea [Planear la autenticación multifactor para implementaciones de Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span><span class="sxs-lookup"><span data-stu-id="94218-114">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span></span>

<span data-ttu-id="94218-115">Para configurar la autenticación multifactor, vea [Configurar la autenticación multifactor para usuarios de Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span><span class="sxs-lookup"><span data-stu-id="94218-115">To configure multifactor authentication, [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

<span data-ttu-id="94218-p103">Puede exigir MFA con directivas de acceso condicional. Por ejemplo, puede configurar una directiva que exija MFA cuando se determine que la autenticación sea de riesgo medio o alto. Para obtener más información, vea [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="94218-p103">You can also require MFA with conditional access policies. For example, you can configure a policy that required MFA when the authentication is determined to be of medium or high risk. For more information, see [Step 2: Configure conditional access policy settings](identity-access-policies.md#require-mfa-based-on-sign-in-risk) in the Information Protection phase.</span></span>

>[!Note]
><span data-ttu-id="94218-p104">En algunas aplicaciones (como Microsoft Office 2010 o versiones anteriores, y Apple Mail), no se puede usar MFA. Para usar estas aplicaciones, necesitará usar “contraseñas de aplicación” en lugar de la contraseña tradicional. La contraseña de aplicación permite a la aplicación omitir MFA y seguir funcionando. Para obtener más información sobre las contraseñas de aplicación, vea [Crear una contraseña de aplicación para Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="94218-p104">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="94218-124">Guía de laboratorio de pruebas: Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="94218-124">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="94218-125">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-mfa) de este paso.</span><span class="sxs-lookup"><span data-stu-id="94218-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="94218-126">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="94218-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="94218-127">Protegerse frente al compromisos de credenciales</span><span class="sxs-lookup"><span data-stu-id="94218-127">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |

