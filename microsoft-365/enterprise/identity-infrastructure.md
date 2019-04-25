---
title: 'Fase 2: Identidad'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Pasos para implementar la infraestructura de identidad para Microsoft 365 Enterprise.
ms.openlocfilehash: 932b6fb2cfeb86edcf708bdfdea55cdd8b580838
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288746"
---
# <a name="phase-2-identity"></a><span data-ttu-id="cb3b6-103">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="cb3b6-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="cb3b6-104">En Microsoft 365 Enterprise, una infraestructura de identidades bien planeada y ejecutada prepara el camino para conseguir una seguridad y un acceso más eficaces solo por parte de los usuarios y dispositivos autenticados a las cargas de trabajo de productividad y sus datos.</span><span class="sxs-lookup"><span data-stu-id="cb3b6-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="cb3b6-105">Si ya ha implementado una infraestructura de identidades, vea los [criterios de salida de identidades](identity-exit-criteria.md) para asegurarse de que cumple con las condiciones obligatorias y opcionales para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cb3b6-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="cb3b6-106">Planear e implementar la infraestructura de identidades de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cb3b6-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="cb3b6-107">Antes de empezar, vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb3b6-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="cb3b6-p101">Siga estos pasos para planear e implementar la nueva infraestructura de identidades en la nube. También puede usar estos pasos para adaptar su infraestructura de identidades híbrida o local para trabajar con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cb3b6-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="cb3b6-110">Planeación de usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="cb3b6-110">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="cb3b6-111">Protección de identidades con privilegios</span><span class="sxs-lookup"><span data-stu-id="cb3b6-111">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="cb3b6-112">Configuración de identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="cb3b6-112">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="cb3b6-113">Configuración de autenticación segura de usuario</span><span class="sxs-lookup"><span data-stu-id="cb3b6-113">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="cb3b6-114">Simplificación del acceso de usuarios</span><span class="sxs-lookup"><span data-stu-id="cb3b6-114">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="cb3b6-115">Uso de grupos para facilitar la administración</span><span class="sxs-lookup"><span data-stu-id="cb3b6-115">Use groups for easier management</span></span>](identity-self-service-group-management.md) |

<span data-ttu-id="cb3b6-116">Cuando complete estos pasos, vaya a los [criterios de salida](identity-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cb3b6-116">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="cb3b6-117">Recomendaciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="cb3b6-117">Identity and device access recommendations</span></span>

<span data-ttu-id="cb3b6-p102">Microsoft proporciona un conjunto de recomendaciones para el [acceso a dispositivos e identidades](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los usuarios. Para la identidad, use la configuración y las recomendaciones de los artículos siguientes junto con los pasos en esta fase:</span><span class="sxs-lookup"><span data-stu-id="cb3b6-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="cb3b6-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cb3b6-120">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="cb3b6-121">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="cb3b6-121">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="cb3b6-122">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cb3b6-122">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="cb3b6-123">Aprenda cómo los expertos de TI de Microsoft planearon e implementaron las capacidades de identidad de Microsoft 365 Enterprise con estos recursos:</span><span class="sxs-lookup"><span data-stu-id="cb3b6-123">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="cb3b6-124">Administración de identidades de usuario y el acceso seguro de Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb3b6-124">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="cb3b6-125">Uso de Azure AD Privileged Identity Management para un acceso elevado</span><span class="sxs-lookup"><span data-stu-id="cb3b6-125">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="cb3b6-126">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cb3b6-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="cb3b6-127">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó una infraestructura de identidad híbrida](contoso-identity.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb3b6-127">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="cb3b6-128">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="cb3b6-128">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="cb3b6-129">Planeación de usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="cb3b6-129">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
