---
title: 'Fase 2: Identidad'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Pasos para implementar la infraestructura de identidad para Microsoft 365 Enterprise.
ms.openlocfilehash: 6acd462a0fcd4169a42a0b1d0e1738ffcba597f5
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073900"
---
# <a name="phase-2-identity"></a><span data-ttu-id="0aa53-103">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="0aa53-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="0aa53-104">En Microsoft 365 Enterprise, una infraestructura de identidades bien planeada y ejecutada prepara el camino para conseguir una seguridad y un acceso más eficaces solo por parte de los usuarios y dispositivos autenticados a las cargas de trabajo de productividad y sus datos.</span><span class="sxs-lookup"><span data-stu-id="0aa53-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="0aa53-105">Si ya ha implementado una infraestructura de identidades, vea los [criterios de salida de identidades](identity-exit-criteria.md) para asegurarse de que cumple con las condiciones obligatorias y opcionales para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0aa53-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="0aa53-106">Planear e implementar la infraestructura de identidades de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0aa53-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="0aa53-107">Antes de empezar, vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0aa53-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="0aa53-p101">Siga estos pasos para planear e implementar la nueva infraestructura de identidades en la nube. También puede usar estos pasos para adaptar su infraestructura de identidades híbrida o local para trabajar con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0aa53-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="0aa53-110">Planeación de usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="0aa53-110">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="0aa53-111">Protección de identidades con privilegios</span><span class="sxs-lookup"><span data-stu-id="0aa53-111">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="0aa53-112">Configuración de identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="0aa53-112">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="0aa53-113">Configuración de autenticación segura de usuario</span><span class="sxs-lookup"><span data-stu-id="0aa53-113">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="0aa53-114">Simplificación del acceso de usuarios</span><span class="sxs-lookup"><span data-stu-id="0aa53-114">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="0aa53-115">Uso de grupos para facilitar la administración</span><span class="sxs-lookup"><span data-stu-id="0aa53-115">Use groups for easier management</span></span>](identity-self-service-group-management.md) |

<span data-ttu-id="0aa53-116">Cuando complete estos pasos, vaya a los [criterios de salida](identity-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0aa53-116">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="0aa53-117">Recomendaciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="0aa53-117">Identity and device access recommendations</span></span>

<span data-ttu-id="0aa53-p102">Microsoft proporciona un conjunto de recomendaciones para el [acceso a dispositivos e identidades](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los usuarios. Para la identidad, use la configuración y las recomendaciones de los artículos siguientes junto con los pasos en esta fase:</span><span class="sxs-lookup"><span data-stu-id="0aa53-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="0aa53-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0aa53-120">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="0aa53-121">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="0aa53-121">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="0aa53-122">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0aa53-122">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0aa53-123">Aprenda como los expertos de IT en Microsoft[administran identidades y acceso seguro](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="0aa53-123">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="0aa53-124">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0aa53-124">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0aa53-125">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó una infraestructura de identidad híbrida](contoso-identity.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0aa53-125">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="0aa53-126">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="0aa53-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="0aa53-127">Planeación de usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="0aa53-127">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
