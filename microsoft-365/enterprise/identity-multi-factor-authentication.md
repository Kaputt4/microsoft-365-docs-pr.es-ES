---
title: 'Paso 4: Configurar autenticación segura de usuario'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la autenticación multifactor para las cuentas de usuario.
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072090"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="aee5d-103">Paso 4: Configurar autenticación segura de usuario</span><span class="sxs-lookup"><span data-stu-id="aee5d-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="aee5d-104">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="aee5d-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="aee5d-105">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="aee5d-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="aee5d-p101">En este paso, configurará la autenticación multifactor (MFA) para agregar un segundo nivel de seguridad en las transacciones y los inicios de sesión de usuario. MFA necesita un método de verificación adicional después de que los usuarios escriban correctamente la contraseña. Sin MFA, la contraseña es el único método de verificación. El problema de las contraseñas es que un atacante podría adivinar fácilmente muchas de ellas, o bien se pueden compartir de manera inadvertida con partes que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="aee5d-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="aee5d-110">Con MFA, el segundo nivel de seguridad puede ser:</span><span class="sxs-lookup"><span data-stu-id="aee5d-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="aee5d-111">Un dispositivo personal y de confianza que no se pueda suplantar o duplicar fácilmente, como un smartphone.</span><span class="sxs-lookup"><span data-stu-id="aee5d-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="aee5d-112">Un atributo biométrico, como una huella digital.</span><span class="sxs-lookup"><span data-stu-id="aee5d-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="aee5d-p102">Habilitará MFA y configurará el método de autenticación secundario en cada cuenta de usuario. Asegúrese de informar a los usuarios de que se habilitará MFA para que comprendan los requisitos (como el uso obligatorio de un smartphone para iniciar sesión) y que puedan iniciar sesión correctamente.</span><span class="sxs-lookup"><span data-stu-id="aee5d-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="aee5d-115">Para obtener más información, consulte [el Plan de autenticación multifactor](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="aee5d-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="aee5d-p103">En algunas aplicaciones (como Microsoft Office 2010 o versiones anteriores, y Apple Mail), no se puede usar MFA. Para usar estas aplicaciones, necesitará usar “contraseñas de aplicación” en lugar de la contraseña tradicional. La contraseña de aplicación permite a la aplicación omitir MFA y seguir funcionando. Para obtener más información sobre las contraseñas de aplicación, vea [Crear una contraseña de aplicación para Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="aee5d-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="aee5d-121">Guía de laboratorio de pruebas: Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="aee5d-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="aee5d-122">Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-mfa) de esta sección.</span><span class="sxs-lookup"><span data-stu-id="aee5d-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="aee5d-123">Proteger contra credenciales en peligro</span><span class="sxs-lookup"><span data-stu-id="aee5d-123">Protect against credential compromise</span></span>

<span data-ttu-id="aee5d-124">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="aee5d-124">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="aee5d-125">En esta sección, aprenderá a configurar las directivas que protejan credenciales en peligro, donde un atacante determine el nombre de una cuenta de usuario y la contraseña para acceder a servicios en la nube y los datos de una organización.</span><span class="sxs-lookup"><span data-stu-id="aee5d-125">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="aee5d-126">La protección de identidad de Azure AD proporciona varias formas de evitar que un atacante se desplace lateralmente por las cuentas y grupos, y acceda a sus datos más importantes.</span><span class="sxs-lookup"><span data-stu-id="aee5d-126">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="aee5d-127">Con Azure AD Identity Protection, puede:</span><span class="sxs-lookup"><span data-stu-id="aee5d-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="aee5d-128">Determinar y corregir posibles vulnerabilidades en las identidades de su organización</span><span class="sxs-lookup"><span data-stu-id="aee5d-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="aee5d-p105">Azure AD usa aprendizaje automático para detectar anomalías y actividades sospechosas, como inicios de sesión y actividades posteriores al inicio de sesión. Con estos datos, Identity Protection genera informes y alertas que le permiten evaluar los problemas y tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="aee5d-p105">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="aee5d-131">Detectar acciones sospechosas relacionadas con las identidades de su organización y responder a ellas automáticamente</span><span class="sxs-lookup"><span data-stu-id="aee5d-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="aee5d-p106">Puede configurar directivas basadas en riesgos que responden automáticamente a los problemas encontrados cuando se alcanza un nivel de riesgo especificado. Estas directivas, además de otros controles de acceso condicional proporcionados por Azure Active Directory y Enterprise Mobility + Security (EMS), pueden automáticamente impedir el acceso o realizar acciones correctivas, como activar restablecimientos de contraseña y exigir la autenticación multifactor para los inicios de sesión posteriores.</span><span class="sxs-lookup"><span data-stu-id="aee5d-p106">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="aee5d-134">Investigar incidentes sospechosos y solucionarlos con acciones administrativas</span><span class="sxs-lookup"><span data-stu-id="aee5d-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="aee5d-p107">Puede investigar eventos de riesgo con información sobre el incidente de seguridad. Hay disponibles flujos de trabajo básicos para realizar un seguimiento de las investigaciones e iniciar acciones de corrección, como restablecimientos de contraseña.</span><span class="sxs-lookup"><span data-stu-id="aee5d-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="aee5d-137">Vea [más información sobre Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="aee5d-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="aee5d-138">Vea los [pasos para habilitar Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="aee5d-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="aee5d-139">El resultado de este paso es que habilitó Azure AD Identity Protection y ahora lo usa para:</span><span class="sxs-lookup"><span data-stu-id="aee5d-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="aee5d-140">Solucionar posibles vulnerabilidades de identidad.</span><span class="sxs-lookup"><span data-stu-id="aee5d-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="aee5d-141">Detectar posibles intentos de uso ilícito de credenciales.</span><span class="sxs-lookup"><span data-stu-id="aee5d-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="aee5d-142">Investigar y solucionar incidentes de identidad sospechosos y continuados.</span><span class="sxs-lookup"><span data-stu-id="aee5d-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="aee5d-144">Guía de laboratorio de pruebas: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="aee5d-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="aee5d-145">Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-ident-prot) de esta sección.</span><span class="sxs-lookup"><span data-stu-id="aee5d-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="aee5d-146">Supervisar la actividad de inicio de sesión y del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="aee5d-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="aee5d-147">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="aee5d-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="aee5d-p108">En este paso, revisará los registros de auditoría y la actividad de inicio de sesión con los informes de Azure AD. Hay disponibles dos tipos de informes.</span><span class="sxs-lookup"><span data-stu-id="aee5d-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="aee5d-p109">El **Informe de actividades de registros de auditoría** registra el historial de todas las tareas realizadas en el espacio empresarial de Azure AD. Este informe responde a preguntas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="aee5d-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="aee5d-152">¿Quién agregó a un usuario a un grupo de administradores?</span><span class="sxs-lookup"><span data-stu-id="aee5d-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="aee5d-153">¿Qué usuarios inician sesión en una aplicación específica?</span><span class="sxs-lookup"><span data-stu-id="aee5d-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="aee5d-154">¿Cuántos restablecimientos de contraseña se producen?</span><span class="sxs-lookup"><span data-stu-id="aee5d-154">How many password resets are happening?</span></span>

<span data-ttu-id="aee5d-p110">El **Informe de actividades de inicios de sesión** registra quién realizó las tareas incluidas en el informe de registros de auditoría. Este informe responde a preguntas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="aee5d-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="aee5d-157">Para un usuario específico que esté bajo investigación, ¿cuál es su patrón de inicio de sesión?</span><span class="sxs-lookup"><span data-stu-id="aee5d-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="aee5d-158">¿Cuál es mi volumen de inicios de sesión en un día, semana o mes?</span><span class="sxs-lookup"><span data-stu-id="aee5d-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="aee5d-159">¿Cuántos de estos intentos de inicio de sesión no fueron correctos y para qué cuentas?</span><span class="sxs-lookup"><span data-stu-id="aee5d-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="aee5d-160">Para obtener más información sobre los informes y obtener acceso a ellos, vea [Informes de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="aee5d-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="aee5d-161">Como resultado de este paso, obtendrá información sobre estos informes y conocerá cómo puede usarlos para comprender en profundidad los eventos y actividades de Azure AD con fines de planeamiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="aee5d-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="aee5d-162">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="aee5d-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="aee5d-163">Simplificar el acceso de usuarios</span><span class="sxs-lookup"><span data-stu-id="aee5d-163">Simplify access for users</span></span>](identity-password-reset.md) |

