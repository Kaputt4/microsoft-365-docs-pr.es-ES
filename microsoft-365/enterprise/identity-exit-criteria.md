---
title: 'Fase 2: Criterios de salida de infraestructura de identidades'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Asegúrese de que la configuración cumpla los criterios de Microsoft 365 Enterprise para la infraestructura y los servicios basados en identidades.
ms.openlocfilehash: 49ba7801b740b2a1cfd77955517646ee80174712
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871763"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="1c484-103">Fase 2: Criterios de salida de infraestructura de identidades</span><span class="sxs-lookup"><span data-stu-id="1c484-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="1c484-p101">Antes de continuar con la fase 3, asegúrese de que la infraestructura de identidades cumpla estas condiciones. Además, vea [Requisitos previos](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) para obtener recomendaciones adicionales de infraestructura de identidades.</span><span class="sxs-lookup"><span data-stu-id="1c484-p101">Before you move on to Phase 3, make sure that your identity infrastructure meets these conditions. Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="1c484-106">Obligatorio: Se crearon todos los usuarios, grupos y pertenencias a grupos</span><span class="sxs-lookup"><span data-stu-id="1c484-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="1c484-107">Creó cuentas de usuario y grupos para que:</span><span class="sxs-lookup"><span data-stu-id="1c484-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="1c484-108">Los empleados de su organización y los proveedores, contratistas y socios que trabajan con su organización o para su organización tengan una cuenta de usuario correspondiente en Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="1c484-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (AD).</span></span>
- <span data-ttu-id="1c484-109">Los grupos de Azure AD y sus miembros contengan cuentas de usuario y otros grupos para distintas finalidades, como el aprovisionamiento de configuración de seguridad para Servicios en la nube de Microsoft, licencias automáticas y otros usos.</span><span class="sxs-lookup"><span data-stu-id="1c484-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="1c484-110">Si es necesario, el [Paso 1](identity-plan-users-groups.md) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="1c484-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="1c484-111">Obligatorio: Los usuarios y grupos se sincronizarán con Azure AD</span><span class="sxs-lookup"><span data-stu-id="1c484-111">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="1c484-112">Si ya usa un proveedor de identidades local, como Windows Server Active Directory (AD), quiere decir que usó Azure AD Connect para sincronizar las cuentas de usuario y grupos de su proveedor de identidades local con el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c484-112">If you have an existing on-premises identity provider, such as Windows Server Active Directory (AD), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="1c484-113">Con la sincronización de directorios, los usuarios pueden iniciar sesión en Office 365 y en otros Servicios en la nube de Microsoft con las mismas credenciales que usen para iniciar sesión en sus equipos y para obtener acceso a recursos locales.</span><span class="sxs-lookup"><span data-stu-id="1c484-113">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="1c484-114">Si es necesario, el [paso 7](identity-azure-ad-connect.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="1c484-114">If needed, [Step 7](identity-azure-ad-connect.md) can help you meet this requirement.</span></span>

<span data-ttu-id="1c484-115">Si omite este requisito, tendrá dos conjuntos de cuentas de usuario y grupos:</span><span class="sxs-lookup"><span data-stu-id="1c484-115">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="1c484-116">Cuentas de usuario y grupos que existen en el proveedor de identidades local</span><span class="sxs-lookup"><span data-stu-id="1c484-116">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="1c484-117">Cuentas de usuario y grupos que existen en el espacio empresarial de Azure AD</span><span class="sxs-lookup"><span data-stu-id="1c484-117">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="1c484-p102">En este estado, es necesario que tanto los administradores de TI como los usuarios realicen el mantenimiento de forma manual de los dos conjuntos de cuentas de usuario y grupos. Sin duda, esto provocará cuentas, contraseñas y grupos no sincronizados.</span><span class="sxs-lookup"><span data-stu-id="1c484-p102">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-120">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-120">How to test</span></span>
<span data-ttu-id="1c484-121">Para comprobar que la autenticación con las credenciales locales funcione correctamente, inicie sesión en el portal de Office 365 con sus credenciales locales.</span><span class="sxs-lookup"><span data-stu-id="1c484-121">To verify that authentication with on-premises credentials works correctly, sign in to the Office 365 portal with your on-premises credentials.</span></span>

<span data-ttu-id="1c484-122">Para comprobar que la sincronización de directorios funcione correctamente, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="1c484-122">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="1c484-123">Cree un grupo de prueba en Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="1c484-123">Create a new test group in Windows Server AD.</span></span>
2.  <span data-ttu-id="1c484-124">Espere hasta la hora de sincronización.</span><span class="sxs-lookup"><span data-stu-id="1c484-124">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="1c484-125">Compruebe que el nuevo nombre de grupo de prueba se muestre en el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c484-125">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="1c484-126">Obligatorio: Las cuentas de administrador global están protegidas</span><span class="sxs-lookup"><span data-stu-id="1c484-126">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="1c484-127">[Protegió las cuentas de administrador global de Office 365](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) para evitar poner en peligro credenciales que puedan llevar a infracciones de una suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c484-127">You've [protected your Office 365 global administrator accounts](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) to avoid compromising credentials that can lead to breaches of an Office 365 subscription.</span></span>

<span data-ttu-id="1c484-128">Si omite este requisito, las cuentas de administrador global pueden ser susceptibles a ataques y estar en peligro, lo que permitiría a un atacante obtener acceso a todo el sistema para recolectar, destruir o bloquear sus datos para pedir un rescate.</span><span class="sxs-lookup"><span data-stu-id="1c484-128">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="1c484-129">Si es necesario, el [paso 2](identity-designate-protect-admin-accounts.md) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="1c484-129">If needed, [Step 2](identity-designate-protect-admin-accounts.md) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-130">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-130">How to test</span></span>

<span data-ttu-id="1c484-131">Siga estos pasos para comprobar que protegió las cuentas de administrador global:</span><span class="sxs-lookup"><span data-stu-id="1c484-131">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="1c484-p103">Ejecute el siguiente comando de Azure AD V2 en el símbolo del sistema de PowerShell. Solo verá la lista de cuentas de administrador global dedicadas.</span><span class="sxs-lookup"><span data-stu-id="1c484-p103">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="1c484-p104">Inicie sesión en Office 365 con todas las cuentas del paso 1. Cada inicio de sesión tiene que exigir la autenticación multifactor y el método más seguro de autenticación secundaria disponible en su organización.</span><span class="sxs-lookup"><span data-stu-id="1c484-p104">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="1c484-136">Para obtener instrucciones sobre cómo instalar el módulo de PowerShell de Azure AD V2 e iniciar sesión en Office 365, vea [Conectar a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="1c484-136">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in to Office 365.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="1c484-137">Opcional: La pantalla de inicio de sesión de Office 365 está personalizada para su organización</span><span class="sxs-lookup"><span data-stu-id="1c484-137">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="1c484-138">Siguió los pasos indicados en [Agregar personalización de marca de la compañía a las páginas de inicio de sesión y del panel de acceso](http://aka.ms/aadpaddbranding) para agregar la personalización de marca de su organización a la página de inicio de sesión de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c484-138">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="1c484-139">Si omitió esta opción, los usuarios verán una pantalla de inicio de sesión de Office 365 genérica y es posible que no estén seguros de si inician la sesión en el sitio de su organización.</span><span class="sxs-lookup"><span data-stu-id="1c484-139">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="1c484-140">Si es necesario, el [paso 11](identity-customize-office-365-sign-in.md) puede resultarle útil con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-140">If needed, [Step 11](identity-customize-office-365-sign-in.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-141">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-141">How to test</span></span>

<span data-ttu-id="1c484-p105">Inicie sesión en el portal de Office 365 con el nombre de la cuenta de usuario y la autenticación multifactor. Verá los elementos de personalización de marca en la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1c484-p105">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="1c484-144">Opcional: La autenticación multifactor está habilitada para los usuarios</span><span class="sxs-lookup"><span data-stu-id="1c484-144">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="1c484-145">Siguió los pasos indicados en [Planear la autenticación multifactor para implementaciones de Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) y [Configurar la autenticación multifactor para usuarios de Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) para habilitar la autenticación multifactor (MFA) para las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="1c484-145">You used [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) and [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) to enable multifactor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="1c484-p106">Si omite esta opción, las cuentas de usuario serán vulnerables a ciberatacantes que intenten apropiarse de las credenciales. Si la contraseña de una cuenta de usuario está en peligro, el atacante tendrá acceso todos los recursos y funciones de la cuenta (como los roles de administrador). Esto permite al atacante copiar, destruir o pedir un rescate por los documentos internos y otros datos.</span><span class="sxs-lookup"><span data-stu-id="1c484-p106">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="1c484-149">Si es necesario, el [paso 5](identity-multi-factor-authentication.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-149">If needed, [Step 5](identity-multi-factor-authentication.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-150">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-150">How to test</span></span>

1.  <span data-ttu-id="1c484-151">Cree una cuenta de usuario de prueba en el Portal de administración de Office 365 y asigne una licencia a esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c484-151">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="1c484-152">Configure la autenticación multifactor para la cuenta de usuario de prueba con el método de verificación adicional que use para las cuentas de usuario reales, como el envío de un mensaje al teléfono.</span><span class="sxs-lookup"><span data-stu-id="1c484-152">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="1c484-153">Inicie sesión en Office 365 o en Azure Portal con la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-153">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="1c484-154">Asegúrese de que MFA le pide la información de verificación adicional y que la autenticación se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="1c484-154">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="1c484-155">Elimine la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-155">Delete the test user account.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="1c484-156">Opcional: La sincronización de directorios se supervisa</span><span class="sxs-lookup"><span data-stu-id="1c484-156">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="1c484-157">Siguió los pasos indicados en [Azure AD Connect Health con sincronización](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (para la sincronización de contraseña) o [Usar Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (para la autenticación federada) e implementó Azure AD Connect Health, lo que implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c484-157">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="1c484-158">La instalación del agente de Azure AD Connect Health en todos los servidores de identidades locales.</span><span class="sxs-lookup"><span data-stu-id="1c484-158">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="1c484-159">Uso del portal de Azure AD Connect Health para supervisar el estado de la sincronización continuada.</span><span class="sxs-lookup"><span data-stu-id="1c484-159">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="1c484-160">Si omite esta opción, podrá evaluar con mayor precisión el estado de su infraestructura de identidades basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="1c484-160">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="1c484-161">Si es necesario, el [paso 8](identity-azure-ad-connect-health.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-161">If needed, [Step 8](identity-azure-ad-connect-health.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-162">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-162">How to test</span></span>
<span data-ttu-id="1c484-163">En el portal de Azure AD Connect Health, se muestra el estado actual y correcto de los servidores de identidades locales y la sincronización continuada.</span><span class="sxs-lookup"><span data-stu-id="1c484-163">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="1c484-164">Opcional: los usuarios pueden restablecer sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="1c484-164">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="1c484-165">Usó la [implementación rápida de autoservicio de restablecimiento de contraseña de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para configurar el restablecimiento de contraseña de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1c484-165">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="1c484-166">Si no cumple esta condición, los usuarios tendrán que ponerse en contacto con los administradores de cuentas de usuario para restablecer sus contraseñas, lo que producirá una sobrecarga administrativa adicional para el personal de TI.</span><span class="sxs-lookup"><span data-stu-id="1c484-166">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="1c484-167">Si es necesario, el [paso 4](identity-password-reset.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-167">If needed, [Step 4](identity-password-reset.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-168">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-168">How to test</span></span>

1. <span data-ttu-id="1c484-169">Cree una cuenta de usuario de prueba con una contraseña inicial.</span><span class="sxs-lookup"><span data-stu-id="1c484-169">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="1c484-170">Siga los pasos que se indican en [Dejar que los usuarios restablezcan sus propias contraseñas en Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) para restablecer la contraseña en la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-170">Use the steps in [Let users reset their own passwords in Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="1c484-171">Cierre la sesión y, después, inicie sesión con la cuenta de usuario de prueba con la contraseña restablecida.</span><span class="sxs-lookup"><span data-stu-id="1c484-171">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="1c484-172">Elimine la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-172">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="1c484-173">Opcional: La escritura diferida de contraseñas está habilitada para los usuarios</span><span class="sxs-lookup"><span data-stu-id="1c484-173">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="1c484-174">Siguió las instrucciones que se indican en [SSPR de Azure AD con escritura diferida de contraseñas](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para habilitar la escritura diferida de contraseñas para el espacio empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1c484-174">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="1c484-175">Si omite esta opción, los usuarios que no estén conectados a la red local tendrán que pedir a un administrador de TI que restablezca o desbloquee sus contraseñas de Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="1c484-175">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their Windows Server AD passwords through an IT administrator.</span></span>

<span data-ttu-id="1c484-176">Si es necesario, el [paso 9](identity-password-writeback.md) puede resultarle útil para agregar esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-176">If needed, [Step 9](identity-password-writeback.md) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="1c484-177">La escritura diferida de contraseñas es necesaria para usar todas las características de protección Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando Azure AD detecte un alto riesgo de peligro para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c484-177">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="1c484-178">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-178">How to test</span></span>

<span data-ttu-id="1c484-p107">Para probar la escritura diferida de contraseñas, cambie la contraseña en Office 365. Debería poder usar la cuenta y la nueva contraseña para obtener acceso a los recursos locales de Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="1c484-p107">You test password writeback by changing your password in Office 365. You should be able to use your account and new password to access on-premises Windows Server AD resources.</span></span>

1. <span data-ttu-id="1c484-181">Cree una cuenta de usuario de prueba en el entorno local de Windows Server AD, permita la sincronización de directorios y, después, asigne una licencia de Office 365 en el Portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c484-181">Create a test user account in your on-premises Windows Server AD, allow directory synchronization to occur, and then grant it an Office 365 license in the Office 365 admin portal.</span></span>
2. <span data-ttu-id="1c484-182">Desde un equipo remoto que esté unido al dominio local de Windows Server AD, inicie sesión en el equipo y en el portal de Office 365 con las credenciales de la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-182">From a remote computer that is joined to your on-premises Windows Server AD domain, sign in to the computer and the Office 365 portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="1c484-183">Seleccione **Configuración > Configuración de Office 365 > Contraseña > Cambiar contraseña**.</span><span class="sxs-lookup"><span data-stu-id="1c484-183">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="1c484-184">Escriba la contraseña actual, la nueva contraseña y la confirmación de contraseña.</span><span class="sxs-lookup"><span data-stu-id="1c484-184">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="1c484-p108">Cierre la sesión del portal de Office 365 y del equipo remoto y, después, inicie sesión en el equipo con la cuenta de usuario de prueba la nueva contraseña. De esta forma, demostrará que pudo cambiar la contraseña de una cuenta de usuario local de Windows Server AD con el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c484-p108">Sign out of the Office 365 portal and the remote computer and then sign in to the computer using the test user account and its new password. This proves that you were able to change the password of an on-premises Windows Server AD user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-single-sign-on"></a><span data-ttu-id="1c484-187">Opcional: Los usuarios pueden iniciar sesión con el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="1c484-187">Optional: Users can sign in using single sign-on</span></span>

<span data-ttu-id="1c484-188">Habilitó [Azure AD Connect: Inicio de sesión único de conexión directa](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) en su organización para simplificar la forma en que los usuarios inician sesión en las aplicaciones basadas en la nube, como Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c484-188">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="1c484-189">Si omite esta opción, se pedirá a los usuarios que proporcionen sus credenciales al obtener acceso a aplicaciones adicionales que usen Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c484-189">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="1c484-190">Si es necesario, el [paso 10](identity-single-sign-on.md) puede resultarle útil con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-190">If needed, [Step 10](identity-single-sign-on.md) can help you with this option.</span></span>


<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="1c484-191">Opcional: licencias basadas en grupos para asignar y quitar automáticamente licencias a cuentas de usuario basándose en la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="1c484-191">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="1c484-192">[Habilitó las licencias basadas en grupos](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) para los grupos de seguridad de Azure AD correspondientes para que se asignen o quiten automáticamente las licencias de Office 365 y EMS.</span><span class="sxs-lookup"><span data-stu-id="1c484-192">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="1c484-193">Si omite esta opción, tendrá que realizar estos pasos de forma manual:</span><span class="sxs-lookup"><span data-stu-id="1c484-193">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="1c484-194">Asignar licencias a los nuevos usuarios que quiera que tengan acceso Office 365 y EMS.</span><span class="sxs-lookup"><span data-stu-id="1c484-194">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="1c484-195">Quitar licencias de usuarios que ya no estén con la organización o que no tengan acceso a Office 365 y EMS.</span><span class="sxs-lookup"><span data-stu-id="1c484-195">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="1c484-196">Si es necesario, el [paso 12](identity-group-based-licensing.md) puede resultarle útil con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-196">If needed, [Step 12](identity-group-based-licensing.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-197">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-197">How to test</span></span>

1. <span data-ttu-id="1c484-198">Cree un grupo de seguridad de prueba en Azure AD con Azure Portal y configure las licencias basadas en grupos para asignar licencias de Office 365 y EMS.</span><span class="sxs-lookup"><span data-stu-id="1c484-198">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="1c484-199">Cree una cuenta de usuario de prueba en Azure AD y agréguela al grupo de seguridad de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-199">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="1c484-200">Examine las propiedades de la cuenta de usuario en el Portal de administración de Office 365 para asegurarse de que se asignaron las licencias de Office 365 y EMS.</span><span class="sxs-lookup"><span data-stu-id="1c484-200">Examine the properties of the user account in the Office 365 admin portal to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="1c484-201">Quite la cuenta de usuario de prueba del grupo de seguridad de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-201">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="1c484-202">Examine las propiedades de la cuenta de usuario para garantizar que ya no tenga asignadas licencias de Office 365 y EMS.</span><span class="sxs-lookup"><span data-stu-id="1c484-202">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="1c484-203">Elimine el grupo de seguridad de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-203">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="1c484-204">Opcional: La configuración de pertenencia a grupos dinámica agrega automáticamente cuentas de usuario a grupos basándose en los atributos de cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="1c484-204">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="1c484-205">Determinó el conjunto de grupos dinámicos de Azure AD y siguió las instrucciones que se indican en [Pertenencia a grupos dinámica basada en atributos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) para crear los grupos y las reglas que determinan el conjunto de atributos de cuenta de usuario y los valores para la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="1c484-205">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="1c484-p109">Si omite esta opción, será necesario asignar la pertenencia a grupos de forma manual cuando se agreguen nuevas cuentas o cuando los atributos de cuenta de usuario cambien con el tiempo. Por ejemplo, si alguien cambia del Departamento de Ventas al Departamento de Contabilidad, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="1c484-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="1c484-208">Actualizar el valor del atributo “Departamento” de esa cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="1c484-208">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="1c484-209">Quitarlo de forma manual del grupo “Ventas”.</span><span class="sxs-lookup"><span data-stu-id="1c484-209">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="1c484-210">Agregarlo de forma manual al grupo “Contabilidad”.</span><span class="sxs-lookup"><span data-stu-id="1c484-210">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="1c484-211">Si los grupos “Ventas” o “Contabilidad” fueran dinámicos, solo tendría que cambiar el valor de “Departamento” de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="1c484-211">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="1c484-212">Si es necesario, el [paso 15](identity-automatic-group-membership.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-212">If needed, [Step 15](identity-automatic-group-membership.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-213">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-213">How to test</span></span>

1. <span data-ttu-id="1c484-214">Cree un grupo dinámico de prueba en Azure AD con Azure Portal y configure la regla para que “Departamento” sea igual a “prueba1”.</span><span class="sxs-lookup"><span data-stu-id="1c484-214">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="1c484-215">Cree una cuenta de usuario de prueba en Azure AD y establezca la propiedad “Departamento” en “prueba1”.</span><span class="sxs-lookup"><span data-stu-id="1c484-215">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="1c484-216">Examine las propiedades de la cuenta de usuario para asegurarse de que sea miembro del grupo dinámico de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-216">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="1c484-217">Cambie el valor de la propiedad “Departamento” de la cuenta de usuario de prueba a “prueba2”.</span><span class="sxs-lookup"><span data-stu-id="1c484-217">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="1c484-218">Examine las propiedades de la cuenta de usuario para asegurarse de que ya no sea miembro del grupo dinámico de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-218">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="1c484-219">Elimine el grupo dinámico de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-219">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="1c484-220">Opcional: La administración de grupos de autoservicio está habilitada para grupos específicos de Office 365 y seguridad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="1c484-220">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="1c484-221">Determinó los grupos adecuados para la administración de autoservicio, informó a los propietarios de las responsabilidades y flujos de trabajo de administración de grupos, y [configuró la administración de autoservicio en Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) para esos grupos.</span><span class="sxs-lookup"><span data-stu-id="1c484-221">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="1c484-222">Si omite esta opción, los administradores de TI tendrán que realizar todas las tareas de administración de grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c484-222">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="1c484-223">Si es necesario, el [paso 14](identity-self-service-group-management.md) puede resultarle útil con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-223">If needed, [Step 14](identity-self-service-group-management.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c484-224">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="1c484-224">How to test</span></span>
1.  <span data-ttu-id="1c484-225">Cree una cuenta de usuario de prueba en Azure AD con Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="1c484-225">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="1c484-226">Inicie sesión con la cuenta de usuario de prueba y cree un grupo de seguridad de Azure AD de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-226">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="1c484-227">Cierre la sesión y, después, inicie sesión con la cuenta de administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="1c484-227">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="1c484-228">Configure el grupo de seguridad de prueba para la administración de autoservicio de la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-228">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="1c484-229">Cierre la sesión y, después, inicie sesión con la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-229">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="1c484-230">Use Azure Portal para agregar miembros al grupo de seguridad de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-230">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="1c484-231">Elimine el grupo de seguridad de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="1c484-231">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a><span data-ttu-id="1c484-232">Opcional: Azure AD Identity Protection está habilitado para protegerse contra peligros de credenciales</span><span class="sxs-lookup"><span data-stu-id="1c484-232">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="1c484-233">Habilitó Azure AD Identity Protection para:</span><span class="sxs-lookup"><span data-stu-id="1c484-233">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="1c484-234">Solucionar posibles vulnerabilidades de identidad.</span><span class="sxs-lookup"><span data-stu-id="1c484-234">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="1c484-235">Detectar posibles intentos de uso ilícito de credenciales.</span><span class="sxs-lookup"><span data-stu-id="1c484-235">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="1c484-236">Investigar y solucionar incidentes de identidad sospechosos y continuados.</span><span class="sxs-lookup"><span data-stu-id="1c484-236">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="1c484-p110">Si omite esta opción, no podrá detectar ni combatir automáticamente intentos de acceso ilícito a credenciales, ni podrá investigar los incidentes de seguridad relacionados con identidades. Esto deja a su organización vulnerable ante posibles ataques de acceso ilícito a credenciales y la amenaza resultante para la información confidencial de su organización.</span><span class="sxs-lookup"><span data-stu-id="1c484-p110">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="1c484-239">Si es necesario, el [paso 6](identity-azure-ad-identity-protection.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-239">If needed, [Step 6](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="1c484-240">Opcional: configuró Privileged Identity Management para facilitar la asignación a petición del rol Administrador global</span><span class="sxs-lookup"><span data-stu-id="1c484-240">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="1c484-241">Siguió las instrucciones que se indican en [Configurar Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) para habilitar PIM en el espacio empresarial de Azure AD y configuró las cuentas de administrador globales como administradores aptos.</span><span class="sxs-lookup"><span data-stu-id="1c484-241">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="1c484-242">También siguió las recomendaciones que se indican en [Proteger el acceso con privilegios para implementaciones híbridas y de nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para elaborar un plan de desarrollo que proteja el acceso con privilegios frente a los ciberatacantes.</span><span class="sxs-lookup"><span data-stu-id="1c484-242">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="1c484-243">Si omite esta opción, las cuentas de administrador global estarán sujetas a ataques en línea continuados y, si se ponen en peligro, pueden permitir que un atacante recopile, destruya o impida el acceso a la información confidencial para pedir un rescate.</span><span class="sxs-lookup"><span data-stu-id="1c484-243">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="1c484-244">Si es necesario, el [paso 3](identity-azure-ad-identity-protection.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="1c484-244">If needed, [Step 3](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>


## <a name="next-phase"></a><span data-ttu-id="1c484-245">Fase siguiente</span><span class="sxs-lookup"><span data-stu-id="1c484-245">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="1c484-246">La siguiente fase del proceso de implementación integral de Microsoft 365 Enterprise es [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="1c484-246">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

