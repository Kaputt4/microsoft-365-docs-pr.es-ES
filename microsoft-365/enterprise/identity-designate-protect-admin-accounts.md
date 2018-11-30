---
title: 'Paso 2: Proteger las cuentas de administrador global'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure las cuentas de administrador para obtener la protección máxima.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871796"
---
# <a name="step-2-protect-global-administrator-accounts"></a><span data-ttu-id="83ab2-103">Paso 2: Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="83ab2-103">Step 2: Protect global administrator accounts</span></span>

<span data-ttu-id="83ab2-104">*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="83ab2-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="83ab2-p101">En este paso, contribuirá a impedir ataques digitales en su organización al comprobar que las cuentas de administrador sean lo más seguras posible. Para hacerlo, necesita:</span><span class="sxs-lookup"><span data-stu-id="83ab2-p101">In Step 5, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span>

- <span data-ttu-id="83ab2-107">Crear cuentas de administrador global dedicadas con [contraseñas muy seguras](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) y usarlas solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="83ab2-107">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="83ab2-108">Realice tareas de administración cotidianas al asignar roles de administrador específicos (como administrador de Exchange o administrador de contraseñas) a cuentas de usuario o personal de TI, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="83ab2-108">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="83ab2-109">Para las cuentas de administrador global dedicadas, también necesita:</span><span class="sxs-lookup"><span data-stu-id="83ab2-109">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="83ab2-p102">Probar la configuración de autenticación multifactor (MFA) por cuenta de usuario o basado en el acceso condicional en una cuenta de usuario de prueba para garantizar que MFA funciona correctamente y de forma predecible. MFA exige una forma de autenticación secundaria, como un código de verificación enviado a un smartphone.</span><span class="sxs-lookup"><span data-stu-id="83ab2-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="83ab2-p103">Configure MFA para todas las cuentas de administrador global de Office 365 dedicadas y use la forma más segura de autenticación secundaria disponible en su organización. Para obtener más información, vea [Autenticación multifactor](identity-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="83ab2-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md) for more information.</span></span>
2. <span data-ttu-id="83ab2-p104">Use una directiva de acceso condicional para exigir el uso de MFA en las cuentas de administrador global. Para obtener más información, vea [Proteger las cuentas de administrador](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="83ab2-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="83ab2-p105">Use una directiva de Office 365 Cloud App Security para supervisar la actividad de las cuentas de administrador global. Para obtener más información, vea [Configurar una mayor seguridad para Office 365](infoprotect-configure-increased-security-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="83ab2-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Information protection for Microsoft 365 Enterprise](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="83ab2-118">Para obtener más información sobre la configuración, vea [Proteger las cuentas de administrador global de Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="83ab2-118">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="83ab2-p106">Las organizaciones tienen que usar identidades solo de nube con el fin de crear cuentas con privilegios (como administradores globales) para escenarios de acción rápida en emergencias, como un ciberataque. Para obtener más información, vea [Administrar cuentas administrativas de acceso de emergencias en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="83ab2-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="83ab2-121">Los resultados de este paso son:</span><span class="sxs-lookup"><span data-stu-id="83ab2-121">The results of this step are:</span></span>

- <span data-ttu-id="83ab2-p107">Las únicas cuentas de usuario de la suscripción que tienen el rol de administrador global son las que pertenecen al nuevo conjunto de cuentas de administrador global dedicadas. Compruebe esto con el siguiente comando de PowerShell de Microsoft Azure AD V2:</span><span class="sxs-lookup"><span data-stu-id="83ab2-p107">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="83ab2-124">El resto de las cuentas de usuario habituales que administran la suscripción tienen asignados roles de administrador que están asociados con las funciones del puesto.</span><span class="sxs-lookup"><span data-stu-id="83ab2-124">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="83ab2-125">Para obtener instrucciones sobre cómo instalar el módulo de PowerShell de Azure AD V2 e iniciar sesión, vea [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="83ab2-125">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="83ab2-127">Guía de laboratorio de pruebas: Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="83ab2-127">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="83ab2-128">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-global-admin) de este paso.</span><span class="sxs-lookup"><span data-stu-id="83ab2-128">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="83ab2-129">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="83ab2-129">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="83ab2-130">Configurar los administradores globales a petición</span><span class="sxs-lookup"><span data-stu-id="83ab2-130">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |

