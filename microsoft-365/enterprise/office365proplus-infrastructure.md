---
title: 'Fase 4: Aplicaciones de Microsoft 365 para empresas'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Pasos para implementar la infraestructura de Aplicaciones de Microsoft 365 para empresas para Microsoft 365 Enterprise.
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011952"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f4562-103">Fase 4: Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f4562-103">Phase 4: Microsoft 365 Apps for enterprise</span></span>

![Fase 4: Aplicaciones de Microsoft 365 para empresas](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="f4562-105">*Se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise y Microsoft 365 Educación*</span><span class="sxs-lookup"><span data-stu-id="f4562-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="f4562-106">Microsoft 365 Enterprise incluye Aplicaciones de Microsoft 365 para empresas, la versión de suscripción de Office.</span><span class="sxs-lookup"><span data-stu-id="f4562-106">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise, the subscription version of Office.</span></span> <span data-ttu-id="f4562-107">Al igual que Office 2019, Aplicaciones de Microsoft 365 para empresas incluye todas las aplicaciones de Office, y esas aplicaciones se instalan directamente en los dispositivos del cliente.</span><span class="sxs-lookup"><span data-stu-id="f4562-107">Like Office 2019, Microsoft 365 Apps for enterprise includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="f4562-108">A diferencia de Office 2019, Aplicaciones de Microsoft 365 para empresas se actualiza regularmente con nuevas características y tiene un modelo de licencia basado en el usuario que permite a los usuarios instalar Office en varios dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f4562-108">Unlike Office 2019, Microsoft 365 Apps for enterprise is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="f4562-109">Para obtener más información, consulte [Acerca de Aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="f4562-109">For more details, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="f4562-p102">En esta fase, implementará Aplicaciones de Microsoft 365 para empresas en dispositivos cliente como parte de Microsoft 365 Enterprise. Además de esta guía, le recomendamos que use [Microsoft FastTrack](https://fasttrack.microsoft.com/office) para ayudarle con la implementación.</span><span class="sxs-lookup"><span data-stu-id="f4562-p102">In this phase, you deploy Microsoft 365 Apps for enterprise to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft FastTrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="f4562-112">Si ya tiene Aplicaciones de Microsoft 365 para empresas implementado, consulte los [criterios de salida](office365proplus-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f4562-112">If you already have Microsoft 365 Apps for enterprise deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="f4562-113">Para implementar Windows 10 Enterprise y Aplicaciones de Microsoft 365 para empresas juntos consulte el [Centro de implementación de escritorio](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="f4562-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="f4562-114">Paso 1: Evaluar el entorno</span><span class="sxs-lookup"><span data-stu-id="f4562-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="f4562-p103">Antes de implementar Aplicaciones de Microsoft 365 para empresas, siga las instrucciones de [Evaluar el entorno y los requisitos para implementar Aplicaciones de Microsoft 365](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). Esta evaluación incluye los requisitos del sistema, detalles de los dispositivos cliente (como arquitecturas e idiomas necesarios), requisitos de licencia, capacidad de red y compatibilidad de aplicaciones. Al completar la evaluación, podrá tomar decisiones clave como parte de la planeación de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f4562-p103">Before deploying Microsoft 365 Apps for enterprise, follow the guidance in [Assess your environment and requirements for deploying Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="f4562-118">Paso 2: Planear la implementación</span><span class="sxs-lookup"><span data-stu-id="f4562-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="f4562-p104">Después de evaluar el entorno, siga las instrucciones de [Planear una implementación de Aplicaciones de Microsoft 365](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) para crear un plan de implementación. Este plan incluye las decisiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4562-p104">After assessing your environment, follow the guidance in [Plan your deployment of Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="f4562-121">Cómo implementar Office, como qué herramienta usar (por ejemplo, Microsoft Endpoint Configuration Manager o la herramienta de implementación de Office) y desde dónde instalar Office</span><span class="sxs-lookup"><span data-stu-id="f4562-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="f4562-122">Cómo administrar las actualizaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="f4562-122">How to manage updates to Office</span></span>
- <span data-ttu-id="f4562-123">Qué canales de actualización usar (los canales de actualización de Office controlan la frecuencia con la que los usuarios reciben actualizaciones de características para las aplicaciones de Office).</span><span class="sxs-lookup"><span data-stu-id="f4562-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="f4562-124">Los grupos de implementación y los paquetes de instalación de Office que quiera usar, incluidas qué aplicaciones de Office e idiomas se deben instalar para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f4562-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="f4562-125">El [artículo de planeación](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) incluye los procedimientos recomendados para todas estas opciones, como administrar la implementación, administrar las actualizaciones, definir los paquetes de instalación y crear los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="f4562-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="f4562-126">Paso 3: Implementar</span><span class="sxs-lookup"><span data-stu-id="f4562-126">Step 3: Deploy</span></span>

<span data-ttu-id="f4562-127">En función de su plan de implementación, elija cómo desea realizar la implementación:</span><span class="sxs-lookup"><span data-stu-id="f4562-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="f4562-128">**[Implementar Aplicaciones de Microsoft 365 con Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** administre la implementación con Configuration Manager y descargue e implemente Office desde puntos de distribución de la red.</span><span class="sxs-lookup"><span data-stu-id="f4562-128">**[Deploy Microsoft 365 Apps with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="f4562-129">**[Implementar Aplicaciones de Microsoft 365 desde la nube](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** administre la implementación con la ODT e instale Office en dispositivos cliente directamente desde la CDN de Office.</span><span class="sxs-lookup"><span data-stu-id="f4562-129">**[Deploy Microsoft 365 Apps from the cloud](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="f4562-130">**[Autoinstalación de Aplicaciones de Microsoft 365 para empresas desde el portal de Office](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** administre la implementación desde el portal de Office y haga que los usuarios instalen Office en los dispositivos cliente directamente desde el portal.</span><span class="sxs-lookup"><span data-stu-id="f4562-130">**[Self-install Microsoft 365 Apps for enterprise from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="f4562-p105">Muchas organizaciones usarán una combinación de estas opciones para distintos usuarios. Por ejemplo, una organización puede usar Configuration Manager para implementar Office en la mayoría de los usuarios, pero habilitar la instalación propia para un pequeño grupo de trabajadores que no se suelen conectar a la red interna.</span><span class="sxs-lookup"><span data-stu-id="f4562-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="f4562-p106">Si su organización usa Configuration Manager, le recomendamos actualizar a la rama actual y a la versión actual. Para obtener más información, vea [¿Qué rama de Configuration Manager debo utilizar?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="f4562-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="f4562-135">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4562-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f4562-136">Aprenda cómo los expertos en Microsoft están [implementando y gestionando las actualizaciones de Aplicaciones de Microsoft 365 para empresas](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="f4562-136">Learn how the experts at Microsoft are [deploying and managing updates for Microsoft 365 Apps for enterprise](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="f4562-137">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4562-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f4562-138">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó Aplicaciones de Microsoft 365 para empresas](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="f4562-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Microsoft 365 Apps for enterprise](contoso-o365pp.md).</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="f4562-140">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="f4562-140">Next step</span></span>

[<span data-ttu-id="f4562-141">Criterios de salida de la infraestructura para las Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f4562-141">Microsoft 365 Apps for enterprise infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
