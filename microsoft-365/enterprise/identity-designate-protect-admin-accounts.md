---
title: 'Paso 2: Proteger las identidades con privilegios'
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
description: Comprenda y configure las cuentas de administrador para obtener la protección máxima.
ms.openlocfilehash: b9c645d597dfeb2bdc42e2b0b7615252dc1f5ecb
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981911"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="c45d2-103">Paso 2: Proteger las identidades con privilegios</span><span class="sxs-lookup"><span data-stu-id="c45d2-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="c45d2-104">Proteger las cuentas de administrador globales</span><span class="sxs-lookup"><span data-stu-id="c45d2-104">Protect global administrator accounts</span></span>

<span data-ttu-id="c45d2-105">*Esto es obligatorio y se aplica a las versiones de los E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c45d2-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c45d2-106">En esta sección, ayudará a evitar ataques digitales en su organización, asegurándose de que sus cuentas de administrador sean lo más seguras posible.</span><span class="sxs-lookup"><span data-stu-id="c45d2-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="c45d2-107">Para ello, debe:</span><span class="sxs-lookup"><span data-stu-id="c45d2-107">To do this, you must:</span></span>

- <span data-ttu-id="c45d2-108">Crear cuentas de administrador global dedicadas con [contraseñas muy seguras](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) y usarlas solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c45d2-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="c45d2-109">Realice tareas de administración cotidianas al asignar roles de administrador específicos (como administrador de Exchange o administrador de contraseñas) a cuentas de usuario o personal de TI, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c45d2-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="c45d2-110">Para las cuentas de administrador global dedicadas, también necesita:</span><span class="sxs-lookup"><span data-stu-id="c45d2-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="c45d2-p102">Probar la configuración de autenticación multifactor (MFA) por cuenta de usuario o basado en el acceso condicional en una cuenta de usuario de prueba para garantizar que MFA funciona correctamente y de forma predecible. MFA exige una forma de autenticación secundaria, como un código de verificación enviado a un smartphone.</span><span class="sxs-lookup"><span data-stu-id="c45d2-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="c45d2-113">Habilite la **Directiva de línea base: requerir MFA para los administradores** para las directivas de acceso condicional para las cuentas de administrador global y use la forma más segura de autenticación secundaria disponible en la organización.</span><span class="sxs-lookup"><span data-stu-id="c45d2-113">Enable the **Baseline policy: Require MFA for admins** conditional access policy for your global administrator accounts and use the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="c45d2-114">Consulte [Autenticación multifactor](identity-access-prerequisites.md#protecting-administrator-accounts) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c45d2-114">See [Multi-factor authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="c45d2-115">Para obtener protección adicional, consulte [Proteger las cuentas de administrador global de Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="c45d2-115">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="c45d2-p104">Las organizaciones tienen que usar identidades solo de nube con el fin de crear cuentas con privilegios (como administradores globales) para escenarios de acción rápida en emergencias, como un ciberataque. Para obtener más información, vea [Administrar cuentas administrativas de acceso de emergencias en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="c45d2-p104">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="c45d2-118">Los resultados de esta sección son:</span><span class="sxs-lookup"><span data-stu-id="c45d2-118">The results of this section are:</span></span>

- <span data-ttu-id="c45d2-119">Las únicas cuentas de usuario de su suscripción que tienen el rol de administrador global son las cuentas de administrador global dedicadas.</span><span class="sxs-lookup"><span data-stu-id="c45d2-119">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="c45d2-120">Para comprobarlo, use el siguiente comando de Active Directory de Azure PowerShell para Graph:</span><span class="sxs-lookup"><span data-stu-id="c45d2-120">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="c45d2-121">El resto de cuentas de usuario que administran los servicios de suscripción tienen asignados roles de administrador que están asociados con las funciones del puesto.</span><span class="sxs-lookup"><span data-stu-id="c45d2-121">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="c45d2-122">Vea [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para recibir instrucciones sobre la instalación del módulo Azure Active Directory PowerShell para Graph e iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="c45d2-122">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="c45d2-124">Para poner en práctica esta configuración en un entorno de prueba, consulte la [Guía de entorno de pruebas para proteger cuentas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c45d2-124">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="c45d2-125">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-global-admin) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="c45d2-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="c45d2-126">Configurar los administradores globales a petición</span><span class="sxs-lookup"><span data-stu-id="c45d2-126">Set up on-demand global administrators</span></span>

<span data-ttu-id="c45d2-127">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c45d2-127">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c45d2-128">En esta sección, configurará la administración de identidades con privilegios de Azure AD (PIM) para reducir la cantidad de tiempo en el que sus cuentas de administrador global son vulnerables a ataques malintencionados.</span><span class="sxs-lookup"><span data-stu-id="c45d2-128">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="c45d2-129">PIM proporciona una tarea a petición y just-in-time del rol de administrador global cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c45d2-129">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="c45d2-p107">En lugar de convertir sus cuentas de administrador global en un administrador permanente, se convierten en administradores válidos. El rol de administrador global está inactivo hasta que alguien lo necesita. Después, deberá completar un proceso de activación para agregar el rol de administrador global a la cuenta de administrador global durante un período de tiempo concreto. Cuando expira el tiempo, PIM quita el rol de administrador global de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c45d2-p107">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="c45d2-p108">PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 Enterprise E5. También puede comprar licencias individuales de Azure Active Directory Premium P2 para sus cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c45d2-p108">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="c45d2-136">Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador global, vea los [pasos para configurar PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="c45d2-136">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="c45d2-137">Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="c45d2-137">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="c45d2-138">Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-pim) de esta sección.</span><span class="sxs-lookup"><span data-stu-id="c45d2-138">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="c45d2-139">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="c45d2-139">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="c45d2-140">Configurar identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="c45d2-140">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

