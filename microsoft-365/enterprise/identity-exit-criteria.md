---
title: 'Fase 2: Criterios de salida de infraestructura de identidades'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Asegúrese de que la configuración cumpla los criterios de Microsoft 365 Enterprise para la infraestructura y los servicios basados en identidades.
ms.openlocfilehash: 4a93d0a9fb497daccba4fd2641fd5faf9c4fb384
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370207"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="7d0ec-103">Fase 2: Criterios de salida de infraestructura de identidades</span><span class="sxs-lookup"><span data-stu-id="7d0ec-103">Phase 2: Identity infrastructure exit criteria</span></span>

![Fase 2-Identidad](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="7d0ec-105">Asegúrese de que su infraestructura de identidad cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-105">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="7d0ec-106">Vea también [Requisitos previos](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) para obtener recomendaciones adicionales de infraestructuras de identidades.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-106">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="7d0ec-107">Obligatorio: Las cuentas de administrador global están protegidas</span><span class="sxs-lookup"><span data-stu-id="7d0ec-107">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="7d0ec-108">Ha [protegido sus cuentas](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) de administrador global de Office 365 para combatir el compromiso de las credenciales por parte de atacantes que puedan ocasionar infracciones de la suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-108">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="7d0ec-109">Si omite este requisito, las cuentas de administrador global pueden ser susceptibles a ataques y estar en peligro, lo que permitiría a un atacante obtener acceso a todo el sistema para recolectar, destruir o bloquear sus datos para pedir un rescate.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-109">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="7d0ec-110">Si es necesario, el [Paso 1](identity-create-protect-global-admins.md#identity-global-admin) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-110">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-111">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-111">How to test</span></span>

<span data-ttu-id="7d0ec-112">Siga estos pasos para comprobar que protegió las cuentas de administrador global:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-112">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="7d0ec-113">Ejecute el siguiente comando de Active Directory de Azure PowerShell para Graph en el símbolo de sistema de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-113">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="7d0ec-114">Solo debería ver la lista de cuentas de administrador global dedicadas.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-114">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="7d0ec-115">Inicie sesión en Office 365 con cada una de las cuentas del paso 1.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-115">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="7d0ec-116">Cada inicio de sesión tiene que exigir la Azure Multi-Factor Authentication y el método más seguro de autenticación secundaria disponible en su organización.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-116">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="7d0ec-117">Vea [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) (Conexión a PowerShell de Office 365) para obtener instrucciones de instalación de Azure Active Directory PowerShell para el módulo de Graph e inicio de sesión en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-117">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="7d0ec-118">Opcional: configuró Privileged Identity Management para facilitar la asignación a petición del rol Administrador global</span><span class="sxs-lookup"><span data-stu-id="7d0ec-118">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="7d0ec-119">Siguió las instrucciones que se indican en [Configurar Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) para habilitar PIM en el espacio empresarial de Azure AD y configuró las cuentas de administrador global como administradores aptos.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-119">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="7d0ec-120">También siguió las recomendaciones que se indican en [Proteger el acceso con privilegios para implementaciones híbridas y de nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para elaborar un plan de desarrollo que proteja el acceso con privilegios frente a los ciberatacantes.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-120">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="7d0ec-121">Si omite esta opción, las cuentas de administrador global estarán sujetas a ataques en línea continuados y, si se ponen en peligro, pueden permitir que un atacante recopile, destruya o impida el acceso a la información confidencial para pedir un rescate.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-121">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="7d0ec-122">Si es necesario, el [paso 1](identity-create-protect-global-admins.md#identity-pim) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-122">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="7d0ec-123">Opcional: ha configurado la administración del acceso con privilegios para Office 365</span><span class="sxs-lookup"><span data-stu-id="7d0ec-123">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="7d0ec-124">Ha usado la información en el tema [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (Configuración de la administración del acceso con privilegios en Office 365) para habilitar el acceso con privilegios y crear una o más directivas de acceso con privilegios en su organización.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-124">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="7d0ec-125">Ha configurado estas directivas y el acceso Just-in-time está habilitado para el acceso a la información confidencial o el acceso a la configuración crítica.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-125">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="7d0ec-126">Si es necesario, el [Paso 1](identity-create-protect-global-admins.md#identity-pam) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-126">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="7d0ec-127">Opcional: la protección con contraseña de Azure AD no permite el uso de contraseñas poco seguras</span><span class="sxs-lookup"><span data-stu-id="7d0ec-127">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="7d0ec-128">Ha habilitado la prohibición de contraseñas no válidas [en la nube](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) y para los [Servicios de dominio de Active Directory (AD DS) locales](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) para las contraseñas no permitidas globales y, opcionalmente, para los términos personalizados.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-128">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="7d0ec-129">Si es necesario, el [paso 2](identity-secure-your-passwords.md#identity-password-prot) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-129">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="7d0ec-130">Opcional: los usuarios pueden restablecer sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="7d0ec-130">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="7d0ec-131">Usó la [implementación rápida de autoservicio de restablecimiento de contraseña de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para configurar el restablecimiento de contraseña de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-131">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="7d0ec-132">Si no cumple esta condición, los usuarios tendrán que ponerse en contacto con los administradores de cuentas de usuario para restablecer sus contraseñas, lo que producirá una sobrecarga administrativa adicional para el personal de TI.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-132">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="7d0ec-133">Si es necesario, el [paso 2](identity-secure-your-passwords.md#identity-pw-reset) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-133">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="7d0ec-134">Opcional: Los usuarios pueden iniciar sesión con el inicio de sesión único de conexión directa de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-134">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="7d0ec-135">Habilitó [Azure AD Connect: Inicio de sesión único de conexión directa](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) en su organización para simplificar la forma en que los usuarios inician sesión en las aplicaciones basadas en la nube, como Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-135">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="7d0ec-136">Si omite esta opción, es posible que se pida a sus usuarios que proporcionen credenciales cuando accedan a aplicaciones adicionales que utilicen su espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-136">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="7d0ec-137">Si es necesario, el [paso 2](identity-secure-your-passwords.md#identity-sso) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-137">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="7d0ec-138">Opcional: La pantalla de inicio de sesión de Office 365 está personalizada para su organización</span><span class="sxs-lookup"><span data-stu-id="7d0ec-138">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="7d0ec-139">Siguió los pasos indicados en [Agregar personalización de marca de la compañía a las páginas de inicio de sesión y del panel de acceso](http://aka.ms/aadpaddbranding) para agregar la personalización de marca de su organización a la página de inicio de sesión de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-139">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="7d0ec-140">Si omitió esta opción, los usuarios verán una pantalla de inicio de sesión de Office 365 genérica y es posible que no estén seguros de si inician la sesión en el sitio de su organización.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-140">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="7d0ec-141">Si es necesario, el [paso 2](identity-secure-your-passwords.md#identity-custom-sign-in) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-141">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="7d0ec-142">Opcional: La Azure Multi-Factor Authentication está habilitada para los usuarios</span><span class="sxs-lookup"><span data-stu-id="7d0ec-142">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="7d0ec-143">Usó [Plan para la Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) y las [directivas de acceso condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) para habilitar la Azure Multi-Factor Authentication (MFA) de Azure para sus cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-143">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="7d0ec-p104">Si omite esta opción, las cuentas de usuario serán vulnerables a ciberatacantes que intenten apropiarse de las credenciales. Si la contraseña de una cuenta de usuario está en peligro, el atacante tendrá acceso todos los recursos y funciones de la cuenta (como los roles de administrador). Esto permite al atacante copiar, destruir o pedir un rescate por los documentos internos y otros datos.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="7d0ec-147">Si es necesario, el [paso 3](identity-secure-user-sign-ins.md#identity-mfa) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-147">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-148">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-148">How to test</span></span>

1.  <span data-ttu-id="7d0ec-149">Cree una cuenta de usuario de prueba y asígnele una licencia.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-149">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="7d0ec-150">Configure la Azure Multi-Factor Authentication para la cuenta de usuario de prueba con el método de verificación adicional que está utilizando para las cuentas de usuario reales, por ejemplo, el envío de un mensaje de texto a su teléfono.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-150">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="7d0ec-151">Inicie sesión en el portal de Office 365 con la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-151">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="7d0ec-152">Asegúrese de que MFA le pide la información de verificación adicional y que la autenticación se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-152">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="7d0ec-153">Elimine la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-153">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="7d0ec-154">Opcional: Azure AD Identity Protection está habilitado para proteger contra riesgos de credenciales (sólo Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="7d0ec-154">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="7d0ec-155">Habilitó Azure AD Identity Protection para:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-155">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="7d0ec-156">Solucionar posibles vulnerabilidades de identidad.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-156">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="7d0ec-157">Detectar posibles intentos de uso ilícito de credenciales.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-157">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="7d0ec-158">Investigar y solucionar incidentes de identidad sospechosos y continuados.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-158">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="7d0ec-p105">Si omite esta opción, no podrá detectar ni combatir automáticamente intentos de acceso ilícito a credenciales, ni podrá investigar los incidentes de seguridad relacionados con identidades. Esto deja a su organización vulnerable ante posibles ataques de acceso ilícito a credenciales y la amenaza resultante para la información confidencial de su organización.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="7d0ec-161">Si es necesario, el [paso 3](identity-secure-user-sign-ins.md#identity-ident-prot) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-161">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="7d0ec-162">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-162">How to test</span></span>

1. <span data-ttu-id="7d0ec-163">Cree una cuenta de usuario de prueba con una contraseña inicial.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-163">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="7d0ec-164">Siga los pasos que se indican en [Dejar que los usuarios restablezcan sus propias contraseñas en Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) para restablecer la contraseña en la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-164">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="7d0ec-165">Cierre la sesión y, después, inicie sesión con la cuenta de usuario de prueba con la contraseña restablecida.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-165">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="7d0ec-166">Elimine la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-166">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="7d0ec-167">Obligatorio para la identidad híbrida: los usuarios y grupos se sincronizarán con Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d0ec-167">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="7d0ec-168">Si ya usa un proveedor de identidades local, como Active Directory Domain Services (AD DS), quiere decir que usó Azure AD Connect para sincronizar las cuentas de usuario y los grupos de su proveedor de identidades local con el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-168">If you have an existing on-premises identity provider, such as Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="7d0ec-169">Con la sincronización de directorios, los usuarios pueden iniciar sesión en Office 365 y en otros Servicios en la nube de Microsoft con las mismas credenciales que usen para iniciar sesión en sus equipos y para obtener acceso a recursos locales.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-169">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="7d0ec-170">Si es necesario, el [Paso 4](identity-add-user-accounts.md#identity-sync) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-170">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="7d0ec-171">Si omite este requisito, tendrá dos conjuntos de cuentas de usuario y grupos:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-171">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="7d0ec-172">Cuentas de usuario y grupos que existen en AD DS local</span><span class="sxs-lookup"><span data-stu-id="7d0ec-172">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="7d0ec-173">Cuentas de usuario y grupos que existen en el espacio empresarial de Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d0ec-173">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="7d0ec-p106">En este estado, es necesario que tanto los administradores de TI como los usuarios realicen el mantenimiento de forma manual de los dos conjuntos de cuentas de usuario y grupos. Sin duda, esto provocará cuentas, contraseñas y grupos no sincronizados.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-176">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-176">How to test</span></span>
<span data-ttu-id="7d0ec-177">Para comprobar que la autenticación con las credenciales locales funcione correctamente, inicie sesión en el portal de Office con sus credenciales locales.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-177">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="7d0ec-178">Para comprobar que la sincronización de directorios funcione correctamente, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-178">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="7d0ec-179">Crear un nuevo grupo de prueba en AD DS.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-179">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="7d0ec-180">Espere hasta la hora de sincronización.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-180">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="7d0ec-181">Compruebe que el nuevo nombre de grupo de prueba se muestre en el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-181">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="7d0ec-182">Opcional: La sincronización de directorios se supervisa</span><span class="sxs-lookup"><span data-stu-id="7d0ec-182">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="7d0ec-183">Siguió los pasos indicados en [Azure AD Connect Health con sincronización](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (para la sincronización de contraseña) o [Usar Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (para la autenticación federada) e implementó Azure AD Connect Health, lo que implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-183">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="7d0ec-184">La instalación del agente de Azure AD Connect Health en todos los servidores de identidades locales.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-184">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="7d0ec-185">Uso del portal de Azure AD Connect Health para supervisar el estado de la sincronización continuada.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-185">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="7d0ec-186">Si omite esta opción, podrá evaluar con mayor precisión el estado de su infraestructura de identidades basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-186">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="7d0ec-187">Si es necesario, el [paso 4](identity-add-user-accounts.md#identity-sync-health) puede resultarle útil con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-187">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-188">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-188">How to test</span></span>
<span data-ttu-id="7d0ec-189">El portal Azure AD Connect Health muestra el estado actual y correcto de sus controladores de dominio locales y la sincronización en curso.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-189">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="7d0ec-190">Opcional: La escritura diferida de contraseñas está habilitada para los usuarios</span><span class="sxs-lookup"><span data-stu-id="7d0ec-190">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="7d0ec-191">Siguió las instrucciones que se indican en [SSPR de Azure AD con escritura diferida de contraseñas](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para habilitar la escritura diferida de contraseñas para el espacio empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-191">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="7d0ec-192">Si omite esta opción, los usuarios que no estén conectados a la red local tendrán que pedir a un administrador de TI que restablezca o desbloquee sus contraseñas de AD DS.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-192">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="7d0ec-193">Si es necesario, el [paso 4](identity-add-user-accounts.md#identity-pw-writeback) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-193">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="7d0ec-194">La escritura diferida de contraseñas es necesaria para usar todas las características de protección Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando Azure AD detecte un alto riesgo de peligro para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-194">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-195">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-195">How to test</span></span>

<span data-ttu-id="7d0ec-196">Puede probar la escritura diferida de contraseñas cambiando la contraseña en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-196">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="7d0ec-197">Debería poder usar su cuenta y su contraseña nueva para acceder a los recursos locales de AD DS.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-197">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="7d0ec-198">Cree una cuenta de usuario de prueba en su AD DS local, permita que se produzca la sincronización de directorios y, a continuación, conceda una licencia de Microsoft 365 Enterprise en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-198">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it an Office 365 license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="7d0ec-199">Desde un equipo remoto unido al dominio local de AD DS, inicie sesión en el equipo y en el portal de Office con las credenciales de la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-199">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="7d0ec-200">Seleccione **Configuración > Configuración de Office 365 > Contraseña > Cambiar contraseña**.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-200">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="7d0ec-201">Escriba la contraseña actual, la nueva contraseña y la confirmación de contraseña.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-201">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="7d0ec-202">Cierre la sesión del portal de Office y del equipo remoto e inicie sesión en el equipo con la cuenta de usuario de prueba y su contraseña nueva.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-202">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="7d0ec-203">Esto comprueba que puede cambiar la contraseña de una cuenta de usuario local de AD DS usando el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-203">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-204">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-204">How to test</span></span>

<span data-ttu-id="7d0ec-205">Inicie sesión en el portal de Office 365 con el nombre de usuario de su cuenta y la Azure Multi-Factor Authentication.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-205">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="7d0ec-206">En la página de inicio de sesión, verá los elementos personalizados de su marca.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-206">Sign in to the Office portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="7d0ec-207">Opcional: La administración de grupos de autoservicio está habilitada para grupos específicos de Office 365 y seguridad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d0ec-207">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="7d0ec-208">Determinó los grupos adecuados para la administración de autoservicio, informó a los propietarios de las responsabilidades y flujos de trabajo de administración de grupos, y [configuró la administración de autoservicio en Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) para esos grupos.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="7d0ec-209">Si omite esta opción, los administradores de TI tendrán que realizar todas las tareas de administración de grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="7d0ec-210">Si necesita ayuda con esta opción, vea el [paso 5](identity-use-group-management.md#identity-self-service-groups).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-210">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-211">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-211">How to test</span></span>
1.  <span data-ttu-id="7d0ec-212">Cree una cuenta de usuario de prueba en Azure AD con Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="7d0ec-213">Inicie sesión con la cuenta de usuario de prueba y cree un grupo de seguridad de Azure AD de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="7d0ec-214">Cierre la sesión y, después, inicie sesión con la cuenta de administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="7d0ec-215">Configure el grupo de seguridad de prueba para la administración de autoservicio de la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-215">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="7d0ec-216">Cierre la sesión y, después, inicie sesión con la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-216">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="7d0ec-217">Use Azure Portal para agregar miembros al grupo de seguridad de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-217">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="7d0ec-218">Elimine el grupo de seguridad de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="7d0ec-219">Opcional: La configuración de pertenencia a grupos dinámica agrega automáticamente cuentas de usuario a grupos basándose en los atributos de cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="7d0ec-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="7d0ec-220">Determinó el conjunto de grupos dinámicos de Azure AD y siguió las instrucciones que se indican en [Pertenencia a grupos dinámica basada en atributos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) para crear los grupos y las reglas que determinan el conjunto de atributos de cuenta de usuario y los valores para la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="7d0ec-p110">Si omite esta opción, será necesario asignar la pertenencia a grupos de forma manual cuando se agreguen nuevas cuentas o cuando los atributos de cuenta de usuario cambien con el tiempo. Por ejemplo, si alguien cambia del Departamento de Ventas al Departamento de Contabilidad, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="7d0ec-223">Actualizar el valor del atributo “Departamento” de esa cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="7d0ec-224">Quitarlo de forma manual del grupo “Ventas”.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="7d0ec-225">Agregarlo de forma manual al grupo “Contabilidad”.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="7d0ec-226">Si los grupos “Ventas” o “Contabilidad” fueran dinámicos, solo tendría que cambiar el valor de “Departamento” de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="7d0ec-227">Si necesita ayuda con esta opción, vea el [paso 5](identity-use-group-management.md#identity-dyn-groups).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-227">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-228">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-228">How to test</span></span>

1. <span data-ttu-id="7d0ec-229">Cree un grupo dinámico de prueba en Azure AD con Azure Portal y configure la regla para que “Departamento” sea igual a “prueba1”.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="7d0ec-230">Cree una cuenta de usuario de prueba en Azure AD y establezca la propiedad “Departamento” en “prueba1”.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-230">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="7d0ec-231">Examine las propiedades de la cuenta de usuario para asegurarse de que sea miembro del grupo dinámico de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="7d0ec-232">Cambie el valor de la propiedad “Departamento” de la cuenta de usuario de prueba a “prueba2”.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-232">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="7d0ec-233">Examine las propiedades de la cuenta de usuario para asegurarse de que ya no sea miembro del grupo dinámico de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="7d0ec-234">Elimine el grupo dinámico de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="7d0ec-235">Opcional: licencias basadas en grupos para asignar y quitar automáticamente licencias a cuentas de usuario basándose en la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="7d0ec-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="7d0ec-236">[Habilitó las licencias basadas en grupos](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) para los grupos de seguridad de Azure AD correspondientes para que se asignen o quiten automáticamente las licencias de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="7d0ec-237">Si omite esta opción, tendrá que realizar estos pasos de forma manual:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="7d0ec-238">Asigne licencias a los nuevos usuarios a los que desea tener acceso.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-238">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="7d0ec-239">Anule la asignación de licencias de usuarios que ya no están en su organización o que no tienen acceso.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-239">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="7d0ec-240">Si necesita ayuda con esta opción, vea el [paso 5](identity-use-group-management.md#identity-group-license).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-240">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7d0ec-241">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="7d0ec-241">How to test</span></span>

1. <span data-ttu-id="7d0ec-242">Cree un grupo de seguridad de prueba en Azure AD en el portal Azure y configure la licencia basada en grupos para asignar la licencia Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="7d0ec-243">Cree una cuenta de usuario de prueba en Azure AD y añádala al grupo de seguridad de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="7d0ec-244">Examinar las propiedades de la cuenta de usuario en el centro de administración de Microsoft 365 para asegurarse de que se le asignó la licencia de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="7d0ec-245">Elimine la cuenta de usuario de prueba del grupo de seguridad de prueba..</span><span class="sxs-lookup"><span data-stu-id="7d0ec-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="7d0ec-246">Examine las propiedades de la cuenta de usuario para asegurarse de que ya no tiene asignada la licencia de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-246">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="7d0ec-247">Elimine el grupo de seguridad de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-247">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="7d0ec-248">Opcional: Revisiones de acceso configuradas y en uso para controlar el acceso</span><span class="sxs-lookup"><span data-stu-id="7d0ec-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="7d0ec-249">Utilizó estos artículos para configurar distintos tipos de revisiones de acceso para supervisar la pertenencia a grupos, el acceso a aplicaciones empresariales y las asignaciones de funciones:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="7d0ec-250">Grupos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7d0ec-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="7d0ec-251">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d0ec-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="7d0ec-252">Roles de recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="7d0ec-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="7d0ec-253">Si es necesario, el [paso 6](identity-configure-identity-governance.md#identity-access-reviews) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-253">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="7d0ec-254">Resultados y siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="7d0ec-254">Results and next steps</span></span>

<span data-ttu-id="7d0ec-255">La infraestructura de identidades en la nube de Microsoft 365 usa autenticación sólida, cuentas de administrador protegidas y administración y acceso simplificado de usuarios.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="7d0ec-257">Si sigue las fases de la implementación de un extremo a otro de Microsoft 365 Enterprise, la siguiente fase es [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-257">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

