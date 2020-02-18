---
title: 'Paso 1: crea y proteja sus cuentas de administrador global'
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
description: Las cuentas de administrador global necesitan un tratamiento especial para proteger la integridad de sus credenciales.
ms.openlocfilehash: 27b76671581ebd2dac32304752a85f8a6f60ac98
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067347"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="76cf2-103">Paso 1: crea y proteja sus cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="76cf2-103">Step 1: Create and protect your global admin accounts</span></span>

![Fase 2-Identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="76cf2-105">Proteger las cuentas de administrador globales</span><span class="sxs-lookup"><span data-stu-id="76cf2-105">Protect global administrator accounts</span></span>

<span data-ttu-id="76cf2-106">*Esto es obligatorio y se aplica a las versiones de los E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="76cf2-106">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="76cf2-107">En esta sección, ayudará a evitar ataques digitales en su organización, asegurándose de que sus cuentas de administrador sean lo más seguras posible.</span><span class="sxs-lookup"><span data-stu-id="76cf2-107">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="76cf2-108">Para ello, debe:</span><span class="sxs-lookup"><span data-stu-id="76cf2-108">To do this, you must:</span></span>

- <span data-ttu-id="76cf2-109">Cree más de una cuenta de administrador global dedicada con [contraseñas seguras](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) y úselas solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="76cf2-109">Create more than one dedicated global administrator accounts with [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="76cf2-110">Realice tareas de administración cotidianas al asignar roles de administrador específicos (como administrador de Exchange o administrador de contraseñas) a otras cuentas dedicadas para esos roles o cuentas de usuario o personal de TI, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="76cf2-110">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to other dedicated accounts for those roles or user accounts of IT staff as needed.</span></span>

<span data-ttu-id="76cf2-111">Para las cuentas de administrador global dedicadas, también necesita:</span><span class="sxs-lookup"><span data-stu-id="76cf2-111">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="76cf2-112">Probar la configuración de Azure Multi-Factor Authentication (MFA) por cuenta de usuario o basado en el acceso condicional en una cuenta de usuario de prueba para garantizar que MFA funciona correctamente y de forma predecible.</span><span class="sxs-lookup"><span data-stu-id="76cf2-112">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="76cf2-113">La MFA obliga al uso de una forma de autenticación secundaria, como un código de comprobación enviado a un smartphone.</span><span class="sxs-lookup"><span data-stu-id="76cf2-113">MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="76cf2-114">Cree y habilite directivas de acceso condicional para las cuentas de administrador global y use la forma más segura de autenticación secundaria disponible en la organización.</span><span class="sxs-lookup"><span data-stu-id="76cf2-114">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="76cf2-115">Consulte [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="76cf2-115">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="76cf2-116">Para obtener protección adicional, consulte [Proteger las cuentas de administrador global de Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="76cf2-116">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for additional protections.</span></span>

> [!Note]
> <span data-ttu-id="76cf2-117">Las cuentas de emergencia para casos urgentes, como un ciberataque, deben basarse exclusivamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="76cf2-117">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="76cf2-118">Sí es posible tener cuentas de administrador global (aptas o permanentes) que no sean solo de la nube.</span><span class="sxs-lookup"><span data-stu-id="76cf2-118">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="76cf2-119">Para más información, consulte [Administración de cuentas administrativas de acceso de emergencia en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="76cf2-119">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="76cf2-120">Los resultados de esta sección son:</span><span class="sxs-lookup"><span data-stu-id="76cf2-120">The results of this section are:</span></span>

- <span data-ttu-id="76cf2-121">Las únicas cuentas de usuario de su suscripción que tienen el rol de administrador global son las cuentas de administrador global dedicadas.</span><span class="sxs-lookup"><span data-stu-id="76cf2-121">The only user accounts in your subscription that have the global admin role are the dedicated global administrator accounts.</span></span> <span data-ttu-id="76cf2-122">Para comprobarlo, use el siguiente comando de Active Directory de Azure PowerShell para Graph:</span><span class="sxs-lookup"><span data-stu-id="76cf2-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="76cf2-123">El resto de cuentas de usuario que administran los servicios de suscripción tienen asignados roles de administrador que están asociados con las funciones del puesto.</span><span class="sxs-lookup"><span data-stu-id="76cf2-123">All other user accounts that manage your subscription services have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="76cf2-124">Vea [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para recibir instrucciones sobre la instalación del módulo Azure Active Directory PowerShell para Graph e iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="76cf2-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="76cf2-126">Para poner en práctica esta configuración en un entorno de prueba, consulte la [Guía de entorno de pruebas para proteger cuentas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="76cf2-126">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="76cf2-127">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-global-admin) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="76cf2-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="76cf2-128">Configure administradores a petición</span><span class="sxs-lookup"><span data-stu-id="76cf2-128">Set up on-demand administrators</span></span>

<span data-ttu-id="76cf2-129">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="76cf2-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="76cf2-130">En esta sección, configurará Azure AD Privileged Identity Management (PIM) para reducir la cantidad de tiempo en el que sus cuentas de administrador son vulnerables a ataques malintencionados.</span><span class="sxs-lookup"><span data-stu-id="76cf2-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="76cf2-131">PIM proporciona una tarea a petición y just-in-time del rol de administrador cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="76cf2-131">PIM provides on-demand, just-in-time assignment of the administrator roles when needed.</span></span>  

<span data-ttu-id="76cf2-132">Sus cuentas de administrador pasan de ser administradores permanentes a ser administradores aptos.</span><span class="sxs-lookup"><span data-stu-id="76cf2-132">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="76cf2-133">El rol de administrador permanece inactivo hasta que lo necesite.</span><span class="sxs-lookup"><span data-stu-id="76cf2-133">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="76cf2-134">Luego completará un proceso de activación para agregar el rol de administrador a la cuenta de administrador durante un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="76cf2-134">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="76cf2-135">Cuando la hora expire, PIM quita el rol de administrador de la cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="76cf2-135">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="76cf2-136">PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="76cf2-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="76cf2-137">Como alternativa, puede comprar licencias individuales de Azure Active Directory Premium P2 para las cuentas de administrador.</span><span class="sxs-lookup"><span data-stu-id="76cf2-137">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>

<span data-ttu-id="76cf2-138">Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador, vea los [pasos para configurar PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="76cf2-138">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="76cf2-139">Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="76cf2-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="76cf2-140">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-pim) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="76cf2-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="76cf2-141">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="76cf2-141">Privileged access management</span></span>

<span data-ttu-id="76cf2-p109">La administración del acceso con privilegios se habilita configurando directivas que especifiquen el acceso puntual para actividades basadas en tareas en el inquilino de Office 365. Permite proteger la organización ante infracciones que puedan usar las cuentas existentes de administrador con privilegios y acceso permanente para acceder a datos confidenciales o acceder a opciones de configuración críticas. Por ejemplo, puede configurar una directiva de administración del acceso con privilegios que requiera una autorización explícita para acceder a la configuración del buzón de correo del inquilino de Office 365 y modificar la misma.</span><span class="sxs-lookup"><span data-stu-id="76cf2-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="76cf2-p110">En este paso, habilitará la administración del acceso con privilegios en el inquilino de Office 365 y configurará directivas de acceso con privilegios que proporcionen seguridad adicional para el acceso basado en tareas a los datos y las opciones de configuración de Office 365 de la organización. Para empezar con el acceso con privilegios en la organización de Office 365, debe seguir estos tres pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="76cf2-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="76cf2-147">Crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="76cf2-147">Creating an approver's group</span></span>
- <span data-ttu-id="76cf2-148">Habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="76cf2-148">Enabling privileged access</span></span>
- <span data-ttu-id="76cf2-149">Crear directivas de aprobación</span><span class="sxs-lookup"><span data-stu-id="76cf2-149">Creating approval policies</span></span>

<span data-ttu-id="76cf2-p111">Una vez configurada, la administración del acceso con privilegios permitirá a la organización trabajar sin privilegios permanentes y proporcionará un nivel de defensa contra las vulnerabilidades derivadas de dicho acceso administrativo. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea a la que se haya asociado una directiva definida de aprobación. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deberán solicitar y obtener la aprobación de acceso para tener los permisos necesarios para ejecutar las tareas definidas en la directiva.</span><span class="sxs-lookup"><span data-stu-id="76cf2-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="76cf2-153">Para habilitar la administración del acceso con privilegios de Office 365, vea el tema [Configurar la administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="76cf2-153">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="76cf2-154">Para obtener más información, vea el tema [Administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="76cf2-154">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="76cf2-156">Para poner en práctica esta configuración en un entorno de prueba, consulte [Guía de gestión de acceso privilegiado en un entorno de pruebas](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="76cf2-156">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="76cf2-157">Como punto de control provisional, vea los [criterios de salida](identity-exit-criteria.md#crit-identity-pam) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="76cf2-157">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="76cf2-158">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="76cf2-158">Next step</span></span>

|||
|:-------|:-----|
|![Paso 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="76cf2-160">Proteja sus contraseñas</span><span class="sxs-lookup"><span data-stu-id="76cf2-160">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

