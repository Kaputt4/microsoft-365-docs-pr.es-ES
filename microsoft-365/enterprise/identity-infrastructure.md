---
title: 'Fase 2: Identidad'
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
description: Pasos para implementar la infraestructura de identidad para Microsoft 365 Enterprise.
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981960"
---
# <a name="phase-2-identity"></a><span data-ttu-id="47b9c-103">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="47b9c-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="47b9c-104">En Microsoft 365 Enterprise, una infraestructura de identidades bien planeada y ejecutada prepara el camino para conseguir una seguridad y un acceso más eficaces solo por parte de los usuarios y dispositivos autenticados a las cargas de trabajo de productividad y sus datos.</span><span class="sxs-lookup"><span data-stu-id="47b9c-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="47b9c-105">Vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="47b9c-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="47b9c-106">Si ya ha implementado una infraestructura de identidades, vea los [criterios de salida de identidades](identity-exit-criteria.md) para asegurarse de que cumple con las condiciones obligatorias y opcionales para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="47b9c-106">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="47b9c-107">Para obtener información sobre las características de los diferentes planes de Microsoft 365 Enterprise, la función de Azure Active Directory (Azure AD), los componentes locales y basados en la nube, así como las configuraciones de autenticación más habituales, vea el [póster Infraestructura de identidad](media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="47b9c-107">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="47b9c-108">[![El póster Infraestructura de identidad](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="47b9c-108">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="47b9c-109">Este póster de dos páginas es una forma rápida de optimizar los conceptos de identidad y sus configuraciones para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="47b9c-109">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="47b9c-110">Puede [descargar este póster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) para imprimirlo en formato de carta, DIN o cartel (11 x 17 pulgadas).</span><span class="sxs-lookup"><span data-stu-id="47b9c-110">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="47b9c-111">Planear e implementar la infraestructura de identidades de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="47b9c-111">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="47b9c-p101">Siga estos pasos para planear e implementar la nueva infraestructura de identidades en la nube. También puede usar estos pasos para adaptar su infraestructura de identidades híbrida o local para trabajar con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="47b9c-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="47b9c-114">Planeación de usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="47b9c-114">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="47b9c-115">Protección de identidades con privilegios</span><span class="sxs-lookup"><span data-stu-id="47b9c-115">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="47b9c-116">Configuración de identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="47b9c-116">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="47b9c-117">Configuración de autenticación segura de usuario</span><span class="sxs-lookup"><span data-stu-id="47b9c-117">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="47b9c-118">Simplificación del acceso de usuarios</span><span class="sxs-lookup"><span data-stu-id="47b9c-118">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="47b9c-119">Uso de grupos para facilitar la administración</span><span class="sxs-lookup"><span data-stu-id="47b9c-119">Use groups for easier management</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="47b9c-120">Configurar Identity Governance</span><span class="sxs-lookup"><span data-stu-id="47b9c-120">Configure identity governance</span></span>](identity-governance.md) |

<span data-ttu-id="47b9c-121">Cuando complete estos pasos, vaya a los [criterios de salida](identity-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de identidad en Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="47b9c-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="47b9c-122">Recomendaciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="47b9c-122">Identity and device access recommendations</span></span>

<span data-ttu-id="47b9c-p102">Microsoft proporciona un conjunto de recomendaciones para el [acceso a dispositivos e identidades](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los usuarios. Para la identidad, use la configuración y las recomendaciones de los artículos siguientes junto con los pasos en esta fase:</span><span class="sxs-lookup"><span data-stu-id="47b9c-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="47b9c-125">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="47b9c-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="47b9c-126">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="47b9c-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="47b9c-127">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="47b9c-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="47b9c-128">Aprenda como los expertos de IT en Microsoft[administran identidades y acceso seguro](https://www.microsoft.com/es-ES/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="47b9c-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/es-ES/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="47b9c-129">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="47b9c-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="47b9c-130">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó una infraestructura de identidad híbrida](contoso-identity.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="47b9c-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="47b9c-131">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="47b9c-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="47b9c-132">Planeación de usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="47b9c-132">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
