---
title: 'Paso 3: Configurar los administradores globales a petición'
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
description: Comprenda y configure Azure AD Privileged Identity Management.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871350"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="26cb0-103">Paso 3: Configurar los administradores globales a petición</span><span class="sxs-lookup"><span data-stu-id="26cb0-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="26cb0-104">*Este paso es opcional y solo es válido para la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="26cb0-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="26cb0-p101">En este paso, configurará Azure AD Privileged Identity Management (PIM) para reducir el tiempo durante el que sus cuentas de administrador global son vulnerables ante ataques de usuarios malintencionados. PIM proporciona una asignación a petición y Just-In-Time del rol de administrador global cuando sea necesaria.</span><span class="sxs-lookup"><span data-stu-id="26cb0-p101">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="26cb0-p102">En lugar de convertir sus cuentas de administrador global en un administrador permanente, se convierten en administradores válidos. El rol de administrador global está inactivo hasta que alguien lo necesita. Después, deberá completar un proceso de activación para agregar el rol de administrador global a la cuenta de administrador global durante un período de tiempo concreto. Cuando expira el tiempo, PIM quita el rol de administrador global de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="26cb0-p102">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="26cb0-p103">PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 Enterprise E5. También puede comprar licencias individuales de Azure Active Directory Premium P2 para sus cuentas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="26cb0-p103">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="26cb0-113">Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador global, vea los [pasos para configurar PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="26cb0-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="26cb0-114">Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="26cb0-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="26cb0-115">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-pim) de este paso.</span><span class="sxs-lookup"><span data-stu-id="26cb0-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="26cb0-116">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="26cb0-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="26cb0-117">Simplificar los restablecimientos de contraseña</span><span class="sxs-lookup"><span data-stu-id="26cb0-117">Simplify password resets</span></span>](identity-password-reset.md) |

