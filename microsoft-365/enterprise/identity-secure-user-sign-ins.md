---
title: 'Paso 3: proteja y administre los inicios de sesión de usuario'
f1.keywords:
- NOCSH
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
description: Haga que los inicios de sesión en los dispositivos Windows y en Microsoft 365 sean más seguros.
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067297"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="7dcfc-103">Paso 3: Proteja y administre los inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="7dcfc-103">Step 3: Secure and manage your user sign-ins</span></span>

![Fase 2-Identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="7dcfc-105">Use Windows Hello para empresas</span><span class="sxs-lookup"><span data-stu-id="7dcfc-105">Use Windows Hello for Business</span></span>

<span data-ttu-id="7dcfc-106">*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="7dcfc-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="7dcfc-107">Windows Hello para empresas en Windows 10 Enterprise reemplaza el mero uso de contraseñas por la ultrasegura autenticación de dos factores cuando inicie sesión en un dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-107">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="7dcfc-108">Esta es un nueva forma de inicio de sesión que vincula el dispositivo de un usuario con un factor biométrico o un PIN.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-108">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="7dcfc-109">Para más información, consulte [Información general para Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span><span class="sxs-lookup"><span data-stu-id="7dcfc-109">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="7dcfc-110">Configure Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="7dcfc-110">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="7dcfc-111">*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="7dcfc-111">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="7dcfc-112">En este paso, configurará Azure Multi-Factor Authentication (MFA) para agregar un segundo nivel de seguridad en inicios de sesión de usuario y transacciones.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-112">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="7dcfc-113">El MFA realiza una comprobación adicional después de que los usuarios hayan escrito correctamente su contraseña.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-113">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="7dcfc-114">Si no usa MFA, la contraseña será el único método de verificación de identidad.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-114">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="7dcfc-115">El problema de las contraseñas consiste en que un atacante pueda adivinarlas fácilmente y se pueden compartir con terceros de dudosa confianza.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-115">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="7dcfc-116">Con MFA, el segundo nivel de seguridad puede ser:</span><span class="sxs-lookup"><span data-stu-id="7dcfc-116">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="7dcfc-117">Un dispositivo personal y de confianza que no se pueda suplantar o duplicar fácilmente, como un smartphone.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-117">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="7dcfc-118">Un atributo biométrico, como una huella digital.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-118">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="7dcfc-119">Habilitará MFA y configurará el método de autenticación secundario con [directivas de acceso condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), que le permiten usar grupos de Azure Active Directory (Azure AD) para implementar MFA en conjuntos específicos de usuarios, como usuarios piloto, regiones geográficas o departamentos.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-119">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="7dcfc-120">Asegúrese de informar a los usuarios de que se habilitará MFA para que comprendan los requisitos (como el uso obligatorio de un smartphone para iniciar sesión) y que puedan iniciar sesión correctamente.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-120">Make sure to let your users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="7dcfc-121">Para obtener más información, vea [Planificar la implementación en la nube de Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="7dcfc-121">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7dcfc-123">Guía de laboratorio de pruebas: Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="7dcfc-123">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="7dcfc-124">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-mfa) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="7dcfc-125">Proteger contra credenciales en peligro</span><span class="sxs-lookup"><span data-stu-id="7dcfc-125">Protect against credential compromise</span></span>

<span data-ttu-id="7dcfc-126">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7dcfc-126">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7dcfc-127">En esta sección, aprenderá a configurar las directivas que protejan credenciales en peligro, donde un atacante determine el nombre de una cuenta de usuario y la contraseña para acceder a servicios en la nube y los datos de una organización.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-127">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="7dcfc-128">La protección de identidad de Azure AD ofrece varias maneras de evitar que un atacante acceda a las credenciales de una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-128">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="7dcfc-129">Con Azure AD Identity Protection, puede:</span><span class="sxs-lookup"><span data-stu-id="7dcfc-129">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="7dcfc-130">Determinar y corregir posibles vulnerabilidades en las identidades de su organización</span><span class="sxs-lookup"><span data-stu-id="7dcfc-130">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="7dcfc-131">Azure AD usa el aprendizaje automático para detectar anomalías y actividad sospechosa, como inicios de sesión y actividades posteriores al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="7dcfc-132">Con estos datos, Azure AD Identity Protection genera informes y alertas que le ayudarán a evaluar los problemas y tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-132">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="7dcfc-133">Detectar acciones sospechosas relacionadas con las identidades de su organización y responder a ellas automáticamente</span><span class="sxs-lookup"><span data-stu-id="7dcfc-133">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="7dcfc-134">Puede configurar directivas basadas en riesgos que respondan automáticamente a problemas detectados si se alcanza un nivel de riesgo específico.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-134">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="7dcfc-135">Estas directivas, además de otros controles de acceso condicional proporcionados por Azure AD y Microsoft Intune, pueden bloquear automáticamente el acceso o llevar a cabo acciones correctivas que incluyen el restablecimiento de contraseñas y la solicitud de Azure Multi-Factor Authentication en posteriores inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-135">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="7dcfc-136">Investigar incidentes sospechosos y solucionarlos con acciones administrativas</span><span class="sxs-lookup"><span data-stu-id="7dcfc-136">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="7dcfc-p107">Puede investigar eventos de riesgo con información sobre el incidente de seguridad. Hay disponibles flujos de trabajo básicos para realizar un seguimiento de las investigaciones e iniciar acciones de corrección, como restablecimientos de contraseña.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="7dcfc-139">Vea [más información sobre Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="7dcfc-139">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="7dcfc-140">Vea los [pasos para habilitar Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="7dcfc-140">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="7dcfc-141">El resultado de este paso es que habilitó Azure AD Identity Protection y ahora lo usa para:</span><span class="sxs-lookup"><span data-stu-id="7dcfc-141">The results of this step are that you've enabled Azure AD Identity Protection and you are using it to:</span></span>

- <span data-ttu-id="7dcfc-142">Solucionar posibles vulnerabilidades de identidad.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-142">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="7dcfc-143">Detectar posibles intentos de uso ilícito de credenciales.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-143">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="7dcfc-144">Investigar y solucionar incidentes de identidad sospechosos y continuados.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-144">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7dcfc-146">Guía de laboratorio de pruebas: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="7dcfc-146">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="7dcfc-147">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-ident-prot) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="7dcfc-147">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![Paso 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="7dcfc-149">Agregue cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="7dcfc-149">Add your user accounts</span></span>](identity-add-user-accounts.md) |
