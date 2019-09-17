---
title: 'Fase 2: Criterios de salida de infraestructura de identidades'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Asegúrese de que la configuración cumpla los criterios de Microsoft 365 Enterprise para la infraestructura y los servicios basados en identidades.
ms.openlocfilehash: 4621c9e12519e39931fe8b883b3a8c446c39dae3
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981861"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="843f2-103">Fase 2: Criterios de salida de infraestructura de identidades</span><span class="sxs-lookup"><span data-stu-id="843f2-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="843f2-104">Asegúrese de que su infraestructura de identidad cumpla los siguientes criterios necesarios y que ha considerado aquellos que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="843f2-104">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="843f2-105">Vea también [Requisitos previos](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) para obtener recomendaciones adicionales de infraestructuras de identidades.</span><span class="sxs-lookup"><span data-stu-id="843f2-105">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-your-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="843f2-106">Obligatorio: Se crearon todos los usuarios, grupos y pertenencias a grupos</span><span class="sxs-lookup"><span data-stu-id="843f2-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="843f2-107">Creó cuentas de usuario y grupos para que:</span><span class="sxs-lookup"><span data-stu-id="843f2-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="843f2-108">Los empleados de su organización y los proveedores, contratistas y socios que trabajan con su organización o para su organización tengan una cuenta de usuario correspondiente en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="843f2-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (Azure AD).</span></span>
- <span data-ttu-id="843f2-109">Los grupos de Azure AD y sus miembros contengan cuentas de usuario y otros grupos para distintas finalidades, como el aprovisionamiento de configuración de seguridad para Servicios en la nube de Microsoft, licencias automáticas y otros usos.</span><span class="sxs-lookup"><span data-stu-id="843f2-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="843f2-110">Si es necesario, el [Paso 1](identity-plan-users-groups.md) puede resultarle útil para cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="843f2-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="843f2-111">Obligatorio: Las cuentas de administrador global están protegidas</span><span class="sxs-lookup"><span data-stu-id="843f2-111">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="843f2-112">Ha [protegido sus cuentas](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) de administrador global de Office 365 para combatir el compromiso de las credenciales por parte de atacantes que puedan ocasionar infracciones de la suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="843f2-112">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="843f2-113">Si omite este requisito, las cuentas de administrador global pueden ser susceptibles a ataques y estar en peligro, lo que permitiría a un atacante obtener acceso a todo el sistema para recolectar, destruir o bloquear sus datos para pedir un rescate.</span><span class="sxs-lookup"><span data-stu-id="843f2-113">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="843f2-114">Si es necesario, el [paso 2](identity-designate-protect-admin-accounts.md#identity-global-admin) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="843f2-114">If needed, [Step 2](identity-designate-protect-admin-accounts.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-115">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-115">How to test</span></span>

<span data-ttu-id="843f2-116">Siga estos pasos para comprobar que protegió las cuentas de administrador global:</span><span class="sxs-lookup"><span data-stu-id="843f2-116">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="843f2-p101">Ejecute el siguiente comando de Azure Active Directory PowerShell para Graph en el símbolo del sistema de PowerShell. Solo verá la lista de cuentas de administrador global dedicadas.</span><span class="sxs-lookup"><span data-stu-id="843f2-p101">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="843f2-p102">Inicie sesión en Office 365 con todas las cuentas del paso 1. Cada inicio de sesión tiene que exigir la autenticación multifactor y el método más seguro de autenticación secundaria disponible en su organización.</span><span class="sxs-lookup"><span data-stu-id="843f2-p102">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="843f2-121">Vea [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) (Conexión a PowerShell de Office 365) para obtener instrucciones de instalación de Azure Active Directory PowerShell para el módulo de Graph e inicio de sesión en Office 365.</span><span class="sxs-lookup"><span data-stu-id="843f2-121">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="843f2-122">Opcional: configuró Privileged Identity Management para facilitar la asignación a petición del rol Administrador global</span><span class="sxs-lookup"><span data-stu-id="843f2-122">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="843f2-123">Siguió las instrucciones que se indican en [Configurar Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) para habilitar PIM en el espacio empresarial de Azure AD y configuró las cuentas de administrador global como administradores aptos.</span><span class="sxs-lookup"><span data-stu-id="843f2-123">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="843f2-124">También siguió las recomendaciones que se indican en [Proteger el acceso con privilegios para implementaciones híbridas y de nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para elaborar un plan de desarrollo que proteja el acceso con privilegios frente a los ciberatacantes.</span><span class="sxs-lookup"><span data-stu-id="843f2-124">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="843f2-125">Si omite esta opción, las cuentas de administrador global estarán sujetas a ataques en línea continuados y, si se ponen en peligro, pueden permitir que un atacante recopile, destruya o impida el acceso a la información confidencial para pedir un rescate.</span><span class="sxs-lookup"><span data-stu-id="843f2-125">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="843f2-126">Si es necesario, el [paso 2](identity-designate-protect-admin-accounts.md#identity-pim) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-126">If needed, [Step 2](identity-designate-protect-admin-accounts.md#identity-pim) can help you with this option.</span></span>


<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="843f2-127">Obligatorio: Los usuarios y grupos se sincronizarán con Azure AD</span><span class="sxs-lookup"><span data-stu-id="843f2-127">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="843f2-128">Si ya usa un proveedor de identidades local, como Active Directory Domain Services (AD DS), quiere decir que usó Azure AD Connect para sincronizar las cuentas de usuario y los grupos de su proveedor de identidades local con el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="843f2-128">If you have an existing on-premises identity provider, such as Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="843f2-129">Con la sincronización de directorios, los usuarios pueden iniciar sesión en Office 365 y en otros Servicios en la nube de Microsoft con las mismas credenciales que usen para iniciar sesión en sus equipos y para obtener acceso a recursos locales.</span><span class="sxs-lookup"><span data-stu-id="843f2-129">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="843f2-130">Si es necesario, el [paso 3](identity-azure-ad-connect.md#identity-sync) puede ayudarle a cumplir este requisito.</span><span class="sxs-lookup"><span data-stu-id="843f2-130">If needed, [Step 3](identity-azure-ad-connect.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="843f2-131">Si omite este requisito, tendrá dos conjuntos de cuentas de usuario y grupos:</span><span class="sxs-lookup"><span data-stu-id="843f2-131">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="843f2-132">Cuentas de usuario y grupos que existen en AD DS local</span><span class="sxs-lookup"><span data-stu-id="843f2-132">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="843f2-133">Cuentas de usuario y grupos que existen en el espacio empresarial de Azure AD</span><span class="sxs-lookup"><span data-stu-id="843f2-133">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="843f2-p103">En este estado, es necesario que tanto los administradores de TI como los usuarios realicen el mantenimiento de forma manual de los dos conjuntos de cuentas de usuario y grupos. Sin duda, esto provocará cuentas, contraseñas y grupos no sincronizados.</span><span class="sxs-lookup"><span data-stu-id="843f2-p103">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-136">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-136">How to test</span></span>
<span data-ttu-id="843f2-137">Para comprobar que la autenticación con las credenciales locales funcione correctamente, inicie sesión en el portal de Office con sus credenciales locales.</span><span class="sxs-lookup"><span data-stu-id="843f2-137">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="843f2-138">Para comprobar que la sincronización de directorios funcione correctamente, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="843f2-138">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="843f2-139">Crear un nuevo grupo de prueba en AD DS.</span><span class="sxs-lookup"><span data-stu-id="843f2-139">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="843f2-140">Espere hasta la hora de sincronización.</span><span class="sxs-lookup"><span data-stu-id="843f2-140">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="843f2-141">Compruebe que el nuevo nombre de grupo de prueba se muestre en el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="843f2-141">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="843f2-142">Opcional: La sincronización de directorios se supervisa</span><span class="sxs-lookup"><span data-stu-id="843f2-142">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="843f2-143">Siguió los pasos indicados en [Azure AD Connect Health con sincronización](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (para la sincronización de contraseña) o [Usar Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (para la autenticación federada) e implementó Azure AD Connect Health, lo que implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="843f2-143">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="843f2-144">La instalación del agente de Azure AD Connect Health en todos los servidores de identidades locales.</span><span class="sxs-lookup"><span data-stu-id="843f2-144">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="843f2-145">Uso del portal de Azure AD Connect Health para supervisar el estado de la sincronización continuada.</span><span class="sxs-lookup"><span data-stu-id="843f2-145">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="843f2-146">Si omite esta opción, podrá evaluar con mayor precisión el estado de su infraestructura de identidades basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="843f2-146">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="843f2-147">Si es necesario, el [paso 3](identity-azure-ad-connect.md#identity-sync-health) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-147">If needed, [Step 3](identity-azure-ad-connect.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-148">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-148">How to test</span></span>
<span data-ttu-id="843f2-149">En el portal de Azure AD Connect Health, se muestra el estado actual y correcto de los controladores de dominio locales y la sincronización continuada.</span><span class="sxs-lookup"><span data-stu-id="843f2-149">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="843f2-150">Opcional: La autenticación multifactor está habilitada para los usuarios</span><span class="sxs-lookup"><span data-stu-id="843f2-150">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="843f2-151">Usó [Plan para la autenticación multifactor](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) y las [directivas de acceso condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) para habilitar la autenticación multifactor (MFA) para sus cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="843f2-151">You used [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [conditional access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable multi-factor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="843f2-p104">Si omite esta opción, las cuentas de usuario serán vulnerables a ciberatacantes que intenten apropiarse de las credenciales. Si la contraseña de una cuenta de usuario está en peligro, el atacante tendrá acceso todos los recursos y funciones de la cuenta (como los roles de administrador). Esto permite al atacante copiar, destruir o pedir un rescate por los documentos internos y otros datos.</span><span class="sxs-lookup"><span data-stu-id="843f2-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="843f2-155">Si es necesario, el [paso 4](identity-multi-factor-authentication.md#identity-mfa) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-155">If needed, [Step 4](identity-multi-factor-authentication.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-156">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-156">How to test</span></span>

1.  <span data-ttu-id="843f2-157">Cree una cuenta de usuario de prueba y asigne una licencia a esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="843f2-157">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="843f2-158">Configure la autenticación multifactor para la cuenta de usuario de prueba con el método de verificación adicional que use para las cuentas de usuario reales, como el envío de un mensaje de texto al teléfono.</span><span class="sxs-lookup"><span data-stu-id="843f2-158">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="843f2-159">Inicie sesión en el portal de Office 365 con la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-159">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="843f2-160">Asegúrese de que MFA le pide la información de verificación adicional y que la autenticación se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="843f2-160">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="843f2-161">Elimine la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-161">Delete the test user account.</span></span>

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="843f2-162">Opcional: la protección con contraseña de Azure AD no permite el uso de contraseñas poco seguras</span><span class="sxs-lookup"><span data-stu-id="843f2-162">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="843f2-163">Ha habilitado la prohibición de contraseñas no válidas [en la nube](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) y para los [Servicios de dominio de Active Directory (AD DS) locales](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) para las contraseñas no permitidas globales y, opcionalmente, para los términos personalizados.</span><span class="sxs-lookup"><span data-stu-id="843f2-163">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="843f2-164">Si es necesario, el [paso 4](identity-multi-factor-authentication.md#identity-password-prot) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-164">If needed, [Step 4](identity-multi-factor-authentication.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="843f2-165">Opcional: Azure AD Identity Protection está habilitado para protegerse contra peligros de credenciales (solo Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="843f2-165">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="843f2-166">Habilitó Azure AD Identity Protection para:</span><span class="sxs-lookup"><span data-stu-id="843f2-166">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="843f2-167">Solucionar posibles vulnerabilidades de identidad.</span><span class="sxs-lookup"><span data-stu-id="843f2-167">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="843f2-168">Detectar posibles intentos de uso ilícito de credenciales.</span><span class="sxs-lookup"><span data-stu-id="843f2-168">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="843f2-169">Investigar y solucionar incidentes de identidad sospechosos y continuados.</span><span class="sxs-lookup"><span data-stu-id="843f2-169">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="843f2-p105">Si omite esta opción, no podrá detectar ni combatir automáticamente intentos de acceso ilícito a credenciales, ni podrá investigar los incidentes de seguridad relacionados con identidades. Esto deja a su organización vulnerable ante posibles ataques de acceso ilícito a credenciales y la amenaza resultante para la información confidencial de su organización.</span><span class="sxs-lookup"><span data-stu-id="843f2-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="843f2-172">Si es necesario, el [paso 4](identity-multi-factor-authentication.md#identity-ident-prot) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-172">If needed, [Step 4](identity-multi-factor-authentication.md#identity-ident-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="843f2-173">Opcional: los usuarios pueden restablecer sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="843f2-173">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="843f2-174">Usó la [implementación rápida de autoservicio de restablecimiento de contraseña de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para configurar el restablecimiento de contraseña de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="843f2-174">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="843f2-175">Si no cumple esta condición, los usuarios tendrán que ponerse en contacto con los administradores de cuentas de usuario para restablecer sus contraseñas, lo que producirá una sobrecarga administrativa adicional para el personal de TI.</span><span class="sxs-lookup"><span data-stu-id="843f2-175">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="843f2-176">Si necesita ayuda con esta opción, vea el [paso 5](identity-password-reset.md#identity-pw-reset).</span><span class="sxs-lookup"><span data-stu-id="843f2-176">If needed, [Step 5](identity-password-reset.md#identity-pw-reset) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-177">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-177">How to test</span></span>

1. <span data-ttu-id="843f2-178">Cree una cuenta de usuario de prueba con una contraseña inicial.</span><span class="sxs-lookup"><span data-stu-id="843f2-178">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="843f2-179">Siga los pasos que se indican en [Dejar que los usuarios restablezcan sus propias contraseñas en Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) para restablecer la contraseña en la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-179">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="843f2-180">Cierre la sesión y, después, inicie sesión con la cuenta de usuario de prueba con la contraseña restablecida.</span><span class="sxs-lookup"><span data-stu-id="843f2-180">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="843f2-181">Elimine la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-181">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="843f2-182">Opcional: La escritura diferida de contraseñas está habilitada para los usuarios</span><span class="sxs-lookup"><span data-stu-id="843f2-182">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="843f2-183">Siguió las instrucciones que se indican en [SSPR de Azure AD con escritura diferida de contraseñas](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para habilitar la escritura diferida de contraseñas para el espacio empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="843f2-183">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="843f2-184">Si omite esta opción, los usuarios que no estén conectados a la red local tendrán que pedir a un administrador de TI que restablezca o desbloquee sus contraseñas de AD DS.</span><span class="sxs-lookup"><span data-stu-id="843f2-184">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="843f2-185">Si necesita ayuda con esta opción, vea el [paso 5](identity-password-reset.md#identity-pw-writeback).</span><span class="sxs-lookup"><span data-stu-id="843f2-185">If needed, [Step 5](identity-password-reset.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="843f2-186">La escritura diferida de contraseñas es necesaria para usar todas las características de protección Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando Azure AD detecte un alto riesgo de peligro para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="843f2-186">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="843f2-187">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-187">How to test</span></span>

<span data-ttu-id="843f2-188">Puede probar la escritura diferida de contraseñas cambiando la contraseña en Office 365.</span><span class="sxs-lookup"><span data-stu-id="843f2-188">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="843f2-189">Debería poder usar su cuenta y su contraseña nueva para acceder a los recursos locales de AD DS.</span><span class="sxs-lookup"><span data-stu-id="843f2-189">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="843f2-190">Cree una cuenta de usuario de prueba en su AD DS local, permita que se produzca la sincronización de directorios y, a continuación, conceda una licencia de Microsoft 365 Enterprise en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="843f2-190">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it an Office 365 license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="843f2-191">Desde un equipo remoto unido al dominio local de AD DS, inicie sesión en el equipo y en el portal de Office con las credenciales de la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-191">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="843f2-192">Seleccione **Configuración > Configuración de Office 365 > Contraseña > Cambiar contraseña**.</span><span class="sxs-lookup"><span data-stu-id="843f2-192">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="843f2-193">Escriba la contraseña actual, la nueva contraseña y la confirmación de contraseña.</span><span class="sxs-lookup"><span data-stu-id="843f2-193">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="843f2-194">Cierre la sesión del portal de Office y del equipo remoto e inicie sesión en el equipo con la cuenta de usuario de prueba y su contraseña nueva.</span><span class="sxs-lookup"><span data-stu-id="843f2-194">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="843f2-195">Esto comprueba que puede cambiar la contraseña de una cuenta de usuario local de AD DS usando el espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="843f2-195">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="843f2-196">Opcional: Los usuarios pueden iniciar sesión con el inicio de sesión único de conexión directa de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="843f2-196">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="843f2-197">Habilitó [Azure AD Connect: Inicio de sesión único de conexión directa](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) en su organización para simplificar la forma en que los usuarios inician sesión en las aplicaciones basadas en la nube, como Office 365.</span><span class="sxs-lookup"><span data-stu-id="843f2-197">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="843f2-198">Si omite esta opción, se pedirá a los usuarios que proporcionen sus credenciales al obtener acceso a aplicaciones adicionales que usen su espacio empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="843f2-198">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="843f2-199">Si necesita ayuda con esta opción, vea el [paso 5](identity-password-reset.md#identity-sso).</span><span class="sxs-lookup"><span data-stu-id="843f2-199">If needed, [Step 5](identity-password-reset.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="843f2-200">Opcional: La pantalla de inicio de sesión de Office 365 está personalizada para su organización</span><span class="sxs-lookup"><span data-stu-id="843f2-200">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="843f2-201">Siguió los pasos indicados en [Agregar personalización de marca de la compañía a las páginas de inicio de sesión y del panel de acceso](http://aka.ms/aadpaddbranding) para agregar la personalización de marca de su organización a la página de inicio de sesión de Office 365.</span><span class="sxs-lookup"><span data-stu-id="843f2-201">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="843f2-202">Si omitió esta opción, los usuarios verán una pantalla de inicio de sesión de Office 365 genérica y es posible que no estén seguros de si inician la sesión en el sitio de su organización.</span><span class="sxs-lookup"><span data-stu-id="843f2-202">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="843f2-203">Si necesita ayuda con esta opción, vea el [paso 5](identity-password-reset.md#identity-custom-sign-in).</span><span class="sxs-lookup"><span data-stu-id="843f2-203">If needed, [Step 5](identity-password-reset.md#identity-custom-sign-in) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-204">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-204">How to test</span></span>

<span data-ttu-id="843f2-p108">Inicie sesión en el portal de Office 365 con el nombre de la cuenta de usuario y la autenticación multifactor. Verá los elementos de personalización de marca en la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="843f2-p108">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="843f2-207">Opcional: La administración de grupos de autoservicio está habilitada para grupos específicos de Office 365 y seguridad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="843f2-207">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="843f2-208">Determinó los grupos adecuados para la administración de autoservicio, informó a los propietarios de las responsabilidades y flujos de trabajo de administración de grupos, y [configuró la administración de autoservicio en Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) para esos grupos.</span><span class="sxs-lookup"><span data-stu-id="843f2-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="843f2-209">Si omite esta opción, los administradores de TI tendrán que realizar todas las tareas de administración de grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="843f2-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="843f2-210">Si es necesario, el [paso 6](identity-self-service-group-management.md#identity-self-service-groups) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-210">If needed, [Step 6](identity-self-service-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-211">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-211">How to test</span></span>
1.  <span data-ttu-id="843f2-212">Cree una cuenta de usuario de prueba en Azure AD con Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="843f2-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="843f2-213">Inicie sesión con la cuenta de usuario de prueba y cree un grupo de seguridad de Azure AD de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="843f2-214">Cierre la sesión y, después, inicie sesión con la cuenta de administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="843f2-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="843f2-215">Configure el grupo de seguridad de prueba para la administración de autoservicio de la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-215">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="843f2-216">Cierre la sesión y, después, inicie sesión con la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-216">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="843f2-217">Use Azure Portal para agregar miembros al grupo de seguridad de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-217">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="843f2-218">Elimine el grupo de seguridad de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="843f2-219">Opcional: La configuración de pertenencia a grupos dinámica agrega automáticamente cuentas de usuario a grupos basándose en los atributos de cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="843f2-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="843f2-220">Determinó el conjunto de grupos dinámicos de Azure AD y siguió las instrucciones que se indican en [Pertenencia a grupos dinámica basada en atributos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) para crear los grupos y las reglas que determinan el conjunto de atributos de cuenta de usuario y los valores para la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="843f2-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="843f2-p109">Si omite esta opción, será necesario asignar la pertenencia a grupos de forma manual cuando se agreguen nuevas cuentas o cuando los atributos de cuenta de usuario cambien con el tiempo. Por ejemplo, si alguien cambia del Departamento de Ventas al Departamento de Contabilidad, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="843f2-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="843f2-223">Actualizar el valor del atributo “Departamento” de esa cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="843f2-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="843f2-224">Quitarlo de forma manual del grupo “Ventas”.</span><span class="sxs-lookup"><span data-stu-id="843f2-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="843f2-225">Agregarlo de forma manual al grupo “Contabilidad”.</span><span class="sxs-lookup"><span data-stu-id="843f2-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="843f2-226">Si los grupos “Ventas” o “Contabilidad” fueran dinámicos, solo tendría que cambiar el valor de “Departamento” de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="843f2-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="843f2-227">Si es necesario, el [paso 6](identity-self-service-group-management.md#identity-dyn-groups) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-227">If needed, [Step 6](identity-self-service-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-228">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-228">How to test</span></span>

1. <span data-ttu-id="843f2-229">Cree un grupo dinámico de prueba en Azure AD con Azure Portal y configure la regla para que “Departamento” sea igual a “prueba1”.</span><span class="sxs-lookup"><span data-stu-id="843f2-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="843f2-230">Cree una cuenta de usuario de prueba en Azure AD y establezca la propiedad “Departamento” en “prueba1”.</span><span class="sxs-lookup"><span data-stu-id="843f2-230">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="843f2-231">Examine las propiedades de la cuenta de usuario para asegurarse de que sea miembro del grupo dinámico de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="843f2-232">Cambie el valor de la propiedad “Departamento” de la cuenta de usuario de prueba a “prueba2”.</span><span class="sxs-lookup"><span data-stu-id="843f2-232">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="843f2-233">Examine las propiedades de la cuenta de usuario para asegurarse de que ya no sea miembro del grupo dinámico de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="843f2-234">Elimine el grupo dinámico de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="843f2-235">Opcional: licencias basadas en grupos para asignar y quitar automáticamente licencias a cuentas de usuario basándose en la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="843f2-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="843f2-236">[Habilitó las licencias basadas en grupos](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) para los grupos de seguridad de Azure AD correspondientes para que se asignen o quiten automáticamente las licencias de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="843f2-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="843f2-237">Si omite esta opción, tendrá que realizar estos pasos de forma manual:</span><span class="sxs-lookup"><span data-stu-id="843f2-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="843f2-238">Asignar licencias a los nuevos usuarios que quiera que tengan acceso.</span><span class="sxs-lookup"><span data-stu-id="843f2-238">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="843f2-239">Quitar licencias a los usuarios que ya no estén en la organización o que no tengan acceso.</span><span class="sxs-lookup"><span data-stu-id="843f2-239">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="843f2-240">Si es necesario, el [paso 6](identity-self-service-group-management.md#identity-group-license) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-240">If needed, [Step 6](identity-self-service-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="843f2-241">Procedimiento de prueba</span><span class="sxs-lookup"><span data-stu-id="843f2-241">How to test</span></span>

1. <span data-ttu-id="843f2-242">Cree un grupo de seguridad de prueba en Azure AD con Azure Portal y configure las licencias basadas en grupos para asignar una licencia de Microsoft 265 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="843f2-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="843f2-243">Cree una cuenta de usuario de prueba en Azure AD y agréguela al grupo de seguridad de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="843f2-244">Examine las propiedades de la cuenta de usuario en el Centro de administración de Microsoft 365 para asegurarse de que se asignó la licencia de Microsoft 265 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="843f2-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="843f2-245">Quite la cuenta de usuario de prueba del grupo de seguridad de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="843f2-246">Examine las propiedades de la cuenta de usuario para garantizar que ya no tenga asignada la licencia de Microsoft 265 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="843f2-246">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="843f2-247">Elimine el grupo de seguridad de prueba y la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="843f2-247">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="843f2-248">Opcional: Revisiones de acceso configuradas y en uso para controlar el acceso</span><span class="sxs-lookup"><span data-stu-id="843f2-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="843f2-249">Utilizó estos artículos para configurar distintos tipos de revisiones de acceso para supervisar la pertenencia a grupos, el acceso a aplicaciones empresariales y las asignaciones de funciones:</span><span class="sxs-lookup"><span data-stu-id="843f2-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="843f2-250">Grupos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="843f2-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="843f2-251">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="843f2-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="843f2-252">Roles de recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="843f2-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="843f2-253">Si es necesario, el [paso 7](identity-governance.md#identity-access-reviews) puede resultarle útil con esta opción.</span><span class="sxs-lookup"><span data-stu-id="843f2-253">If needed, [Step 5](identity-governance.md#identity-access-reviews) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="843f2-254">Resultados y siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="843f2-254">Results and next steps</span></span>

<span data-ttu-id="843f2-255">La infraestructura de identidades en la nube de Microsoft 365 usa autenticación sólida, cuentas de administrador protegidas y administración y acceso simplificado de usuarios.</span><span class="sxs-lookup"><span data-stu-id="843f2-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="843f2-256">Si sigue las fases de la implementación de un extremo a otro de Microsoft 365 Enterprise, la siguiente fase es [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="843f2-256">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

