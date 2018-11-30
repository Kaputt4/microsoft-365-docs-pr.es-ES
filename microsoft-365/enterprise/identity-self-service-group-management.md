---
title: 'Paso 14: Permitir a los usuarios crear y administrar sus propios grupos'
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
description: Comprenda y configure la administración de grupos de autoservicio de Azure AD.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871488"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="c0360-103">Paso 14: Permitir a los usuarios crear y administrar sus propios grupos</span><span class="sxs-lookup"><span data-stu-id="c0360-103">Step 14: Allow users to create and manage their own groups</span></span>

<span data-ttu-id="c0360-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c0360-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="c0360-p101">En este paso, identificará grupos de Azure Active Directory (AD) que pueden administrar los propietarios del grupo en lugar de los administradores de TI. Esta característica, que se conoce como *administración de grupos de autoservicio*, permite que los propietarios del grupo que no tienen asignado un rol administrativo creen y administren grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c0360-p101">In Step 14, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="c0360-p102">Los usuarios pueden solicitar la pertenencia a un grupo de seguridad y esa solicitud va al propietario del grupo, en lugar de un administrador de TI. Esto permite delegar el control diario de la pertenencia al grupo a los propietarios del equipo, proyecto o empresa que comprenden el uso empresarial del grupo y pueden administrar su pertenencia.</span><span class="sxs-lookup"><span data-stu-id="c0360-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="c0360-p103">La administración de grupos de autoservicio solo está disponible para la seguridad de Azure AD y los grupos de Office 365. No está disponible para los grupos habilitados para correo, las listas de distribución ni ningún grupo que se haya sincronizado desde la instancia local de Windows Server Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="c0360-p103">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="c0360-111">Para obtener más información, vea las [instrucciones para configurar un grupo de Azure AD para la administración de autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="c0360-111">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="c0360-112">Como control interno, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-self-service-groups) de este paso.</span><span class="sxs-lookup"><span data-stu-id="c0360-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c0360-113">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="c0360-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="c0360-114">Configurar la pertenencia a grupos dinámica</span><span class="sxs-lookup"><span data-stu-id="c0360-114">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
