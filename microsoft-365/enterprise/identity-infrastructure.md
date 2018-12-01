---
title: 'Fase 2: Identidad'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Pasos para implementar la infraestructura de identidad para Microsoft 365 Enterprise.
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871564"
---
# <a name="phase-2-identity"></a><span data-ttu-id="f8015-103">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="f8015-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="f8015-104">En Microsoft 365 Enterprise, una infraestructura de identidades bien planeada y ejecutada prepara el camino para conseguir una seguridad y un acceso más eficaces solo por parte de los usuarios y dispositivos autenticados a las cargas de trabajo de productividad y sus datos.</span><span class="sxs-lookup"><span data-stu-id="f8015-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="f8015-105">Si ya ha implementado una infraestructura de identidades, vea los [criterios de salida de identidades](identity-exit-criteria.md) para asegurarse de que cumple con las condiciones obligatorias y opcionales para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f8015-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="f8015-106">Planear e implementar la infraestructura de identidades de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f8015-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="f8015-p101">Siga estos pasos para planear e implementar la nueva infraestructura de identidades en la nube. También puede usar estos pasos para adaptar su infraestructura de identidades híbrida o local para trabajar con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f8015-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="f8015-109">Planeación de usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="f8015-109">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="f8015-110">Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="f8015-110">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="f8015-111">Configurar los administradores globales a petición</span><span class="sxs-lookup"><span data-stu-id="f8015-111">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="f8015-112">Simplificar los restablecimientos de contraseña</span><span class="sxs-lookup"><span data-stu-id="f8015-112">Simplify password resets</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="f8015-113">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="f8015-113">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="f8015-114">Proteger contra credenciales en peligro</span><span class="sxs-lookup"><span data-stu-id="f8015-114">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="f8015-115">Sincronizar directorios</span><span class="sxs-lookup"><span data-stu-id="f8015-115">Synchronize directories</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="f8015-116">Supervisar el estado de sincronización</span><span class="sxs-lookup"><span data-stu-id="f8015-116">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="f8015-117">Simplificar las actualizaciones de contraseña</span><span class="sxs-lookup"><span data-stu-id="f8015-117">Simplify password updates</span></span>](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="f8015-118">Simplificar el inicio de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="f8015-118">Simplify user sign-in</span></span>](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="f8015-119">Personalizar la página de inicio de sesión de Office 365</span><span class="sxs-lookup"><span data-stu-id="f8015-119">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="f8015-120">Configurar las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="f8015-120">Set up automatic licensing</span></span>](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="f8015-121">Supervisar la actividad de inicio de sesión y del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="f8015-121">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="f8015-122">Permitir a los usuarios crear y administrar sus propios grupos</span><span class="sxs-lookup"><span data-stu-id="f8015-122">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="f8015-123">Configurar la pertenencia a grupos dinámica</span><span class="sxs-lookup"><span data-stu-id="f8015-123">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |

<span data-ttu-id="f8015-124">Cuando complete estos pasos, vaya a los [criterios de salida](identity-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f8015-124">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="f8015-125">Recomendaciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="f8015-125">Identity and device access prerequisites</span></span>

<span data-ttu-id="f8015-p102">Microsoft proporciona un conjunto de recomendaciones para el [acceso a dispositivos e identidades](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los usuarios. Para la identidad, use la configuración y las recomendaciones de los artículos siguientes junto con los pasos en esta fase:</span><span class="sxs-lookup"><span data-stu-id="f8015-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="f8015-128">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f8015-128">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="f8015-129">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="f8015-129">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="f8015-130">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f8015-130">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f8015-131">Aprenda cómo los expertos de TI de Microsoft planearon e implementaron las capacidades de identidad de Microsoft 365 Enterprise con estos recursos:</span><span class="sxs-lookup"><span data-stu-id="f8015-131">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="f8015-132">Administración de identidades de usuario y el acceso seguro de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8015-132">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="f8015-133">Uso de Azure AD Privileged Identity Management para un acceso elevado</span><span class="sxs-lookup"><span data-stu-id="f8015-133">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="f8015-134">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f8015-134">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f8015-135">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó una infraestructura de identidad híbrida](contoso-identity.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8015-135">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="f8015-136">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f8015-136">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="f8015-137">Planeación de usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="f8015-137">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
