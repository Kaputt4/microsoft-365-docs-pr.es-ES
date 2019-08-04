---
title: 'Paso 2: Proteger las identidades con privilegios'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure las cuentas de administrador para obtener la protección máxima.
ms.openlocfilehash: 8a1d232ffc0242766d79b2e4884582f3b5524d22
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074060"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="986c3-103">Paso 2: Proteger las identidades con privilegios</span><span class="sxs-lookup"><span data-stu-id="986c3-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="986c3-104">Proteger las cuentas de administrador globales</span><span class="sxs-lookup"><span data-stu-id="986c3-104">Protect global administrator accounts</span></span>

<span data-ttu-id="986c3-105">*Esto es obligatorio y se aplica a las versiones de los E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="986c3-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="986c3-106">En esta sección, ayudará a evitar ataques digitales en su organización, asegurándose de que sus cuentas de administrador sean lo más seguras posible.</span><span class="sxs-lookup"><span data-stu-id="986c3-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="986c3-107">Para ello, debe:</span><span class="sxs-lookup"><span data-stu-id="986c3-107">To do this, you must:</span></span>

- <span data-ttu-id="986c3-108">Crear cuentas de administrador global dedicadas con [contraseñas muy seguras](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) y usarlas solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="986c3-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="986c3-109">Realice tareas de administración cotidianas al asignar roles de administrador específicos (como administrador de Exchange o administrador de contraseñas) a cuentas de usuario o personal de TI, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="986c3-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="986c3-110">Para las cuentas de administrador global dedicadas, también necesita:</span><span class="sxs-lookup"><span data-stu-id="986c3-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="986c3-p102">Probar la configuración de autenticación multifactor (MFA) por cuenta de usuario o basado en el acceso condicional en una cuenta de usuario de prueba para garantizar que MFA funciona correctamente y de forma predecible. MFA exige una forma de autenticación secundaria, como un código de verificación enviado a un smartphone.</span><span class="sxs-lookup"><span data-stu-id="986c3-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="986c3-p103">Configure MFA para todas las cuentas de administrador global de Office 365 dedicadas y use la forma más segura de autenticación secundaria disponible en su organización. Para obtener más información, vea [Autenticación multifactor](identity-multi-factor-authentication.md#identity-mfa).</span><span class="sxs-lookup"><span data-stu-id="986c3-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) for more information.</span></span>
2. <span data-ttu-id="986c3-p104">Use una directiva de acceso condicional para exigir el uso de MFA en las cuentas de administrador global. Para obtener más información, vea [Proteger las cuentas de administrador](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="986c3-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="986c3-117">Para obtener más información sobre la configuración, vea [Proteger las cuentas de administrador global de Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="986c3-117">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="986c3-p105">Las organizaciones tienen que usar identidades solo de nube con el fin de crear cuentas con privilegios (como administradores globales) para escenarios de acción rápida en emergencias, como un ciberataque. Para obtener más información, vea [Administrar cuentas administrativas de acceso de emergencias en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="986c3-p105">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="986c3-120">Los resultados de esta sección son:</span><span class="sxs-lookup"><span data-stu-id="986c3-120">The results of this section are:</span></span>

- <span data-ttu-id="986c3-121">Las únicas cuentas de usuario de su suscripción que tienen el rol de administrador global son aquellas pertenecientes al nuevo conjunto de cuentas de administrador global dedicadas.</span><span class="sxs-lookup"><span data-stu-id="986c3-121">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="986c3-122">Para comprobarlo, use el siguiente comando de Active Directory de Azure PowerShell para Graph:</span><span class="sxs-lookup"><span data-stu-id="986c3-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="986c3-123">El resto de las cuentas de usuario habituales que administran la suscripción tienen asignados roles de administrador que están asociados con las funciones del puesto.</span><span class="sxs-lookup"><span data-stu-id="986c3-123">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="986c3-124">Vea [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para recibir instrucciones sobre la instalación del módulo Azure Active Directory PowerShell para Graph e iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="986c3-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="986c3-126">Guía de laboratorio de pruebas: Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="986c3-126">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="986c3-127">Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-global-admin) de esta sección.</span><span class="sxs-lookup"><span data-stu-id="986c3-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="986c3-128">Configurar los administradores globales a petición</span><span class="sxs-lookup"><span data-stu-id="986c3-128">Set up on-demand global administrators</span></span>

<span data-ttu-id="986c3-129">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="986c3-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="986c3-130">En esta sección, configurará la administración de identidades con privilegios de Azure AD (PIM) para reducir la cantidad de tiempo en el que sus cuentas de administrador global son vulnerables a ataques malintencionados.</span><span class="sxs-lookup"><span data-stu-id="986c3-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="986c3-131">PIM proporciona una tarea a petición y just-in-time del rol de administrador global cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="986c3-131">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="986c3-p108">En lugar de convertir sus cuentas de administrador global en un administrador permanente, se convierten en administradores válidos. El rol de administrador global está inactivo hasta que alguien lo necesita. Después, deberá completar un proceso de activación para agregar el rol de administrador global a la cuenta de administrador global durante un período de tiempo concreto. Cuando expira el tiempo, PIM quita el rol de administrador global de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="986c3-p108">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="986c3-p109">PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 Enterprise E5. También puede comprar licencias individuales de Azure Active Directory Premium P2 para sus cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="986c3-p109">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="986c3-138">Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador global, vea los [pasos para configurar PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="986c3-138">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="986c3-139">Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="986c3-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="986c3-140">Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-pim) de esta sección.</span><span class="sxs-lookup"><span data-stu-id="986c3-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="986c3-141">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="986c3-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="986c3-142">Configurar identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="986c3-142">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

