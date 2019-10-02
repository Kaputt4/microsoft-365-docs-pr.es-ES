---
title: 'Fase 2: Identidad'
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
description: Pasos para implementar su infraestructura de identidad para Microsoft 365 Enterprise.
ms.openlocfilehash: cb5b714afcacd1e21951ec9f83fd7f09cbd88662
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370447"
---
# <a name="phase-2-identity"></a><span data-ttu-id="35bf2-103">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="35bf2-103">Phase 2: Identity</span></span>

![Fase 2: Identidad](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="35bf2-105">En Microsoft 365 Enterprise, una infraestructura de identidades bien planeada y ejecutada prepara el camino para conseguir una seguridad y un acceso más eficaces solo por parte de los usuarios y dispositivos autenticados a las cargas de trabajo de productividad y sus datos.</span><span class="sxs-lookup"><span data-stu-id="35bf2-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="35bf2-106">Vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="35bf2-106">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="35bf2-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="35bf2-107"></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="35bf2-108">Si ya ha implementado una infraestructura de identidades, vea los [criterios de salida de identidades](identity-exit-criteria.md) para asegurarse de que cumple con las condiciones obligatorias y opcionales para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="35bf2-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="35bf2-109">Para obtener información sobre las características de los diferentes planes de Microsoft 365 Enterprise, la función de Azure Active Directory (Azure AD), los componentes locales y basados en la nube, así como las configuraciones de autenticación más habituales, vea el [póster Infraestructura de identidad](media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="35bf2-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="35bf2-110">[![El póster Infraestructura de identidad](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="35bf2-110">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="35bf2-111">Este póster de dos páginas es una forma rápida de optimizar los conceptos de identidad y sus configuraciones para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="35bf2-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="35bf2-112">Puede [descargar este póster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) para imprimirlo en formato de carta, DIN o cartel (11 x 17 pulgadas).</span><span class="sxs-lookup"><span data-stu-id="35bf2-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="35bf2-113">Planear e implementar la infraestructura de identidades de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="35bf2-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="35bf2-p101">Siga estos pasos para planear e implementar la nueva infraestructura de identidades en la nube. También puede usar estos pasos para adaptar su infraestructura de identidades híbrida o local para trabajar con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="35bf2-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![Paso 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="35bf2-117">Cree y proteja sus cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="35bf2-117">Step 1: Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![Paso 2](./media/stepnumbers/Step2.png)| [<span data-ttu-id="35bf2-119">Proteja sus contraseñas</span><span class="sxs-lookup"><span data-stu-id="35bf2-119">Step 2: Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![Paso 3](./media/stepnumbers/Step3.png)| [<span data-ttu-id="35bf2-121">Proteja y administre los inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="35bf2-121">Step 3: Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![Paso 4](./media/stepnumbers/Step4.png)| [<span data-ttu-id="35bf2-123">Agregue cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="35bf2-123">Step 4: Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![Paso 5](./media/stepnumbers/Step5.png)| [<span data-ttu-id="35bf2-125">Use grupos para administración</span><span class="sxs-lookup"><span data-stu-id="35bf2-125">Use groups for easier management</span></span>](identity-use-group-management.md) |
|![Paso 6](./media/stepnumbers/Step6.png)| [<span data-ttu-id="35bf2-127">Configure Identity Governance</span><span class="sxs-lookup"><span data-stu-id="35bf2-127">Step 6: Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="35bf2-128">Cuando complete estos pasos, vaya a los [criterios de salida](identity-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de identidad en Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="35bf2-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="35bf2-129">Recomendaciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="35bf2-129">Identity and device access recommendations</span></span>

<span data-ttu-id="35bf2-p102">Microsoft proporciona un conjunto de recomendaciones para el [acceso a dispositivos e identidades](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los usuarios. Para la identidad, use la configuración y las recomendaciones de los artículos siguientes junto con los pasos en esta fase:</span><span class="sxs-lookup"><span data-stu-id="35bf2-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="35bf2-132">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="35bf2-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="35bf2-133">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="35bf2-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="35bf2-134">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="35bf2-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="35bf2-135">Aprenda como los expertos de IT en Microsoft[administran identidades y acceso seguro](https://www.microsoft.com/es-ES/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="35bf2-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/es-ES/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="35bf2-136">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="35bf2-136">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="35bf2-137">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó una infraestructura de identidad híbrida](contoso-identity.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35bf2-137">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="35bf2-139">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="35bf2-139">Next step</span></span>

|||
|:-------|:-----|
|![Paso 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="35bf2-141">Cree y proteja sus cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="35bf2-141">Step 1: Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
