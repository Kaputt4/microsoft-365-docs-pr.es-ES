---
title: Implementación de Microsoft 365 Enterprise con una infraestructura existente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/04/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Revise los criterios de salida para la implementación de Microsoft 365 Enterprise si tiene una infraestructura existente.
ms.openlocfilehash: 8c9c1d1900e9fd1a025d3fd74cc9f358b612a4d1
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073920"
---
# <a name="deployment-of-microsoft-365-enterprise-with-existing-infrastructure"></a><span data-ttu-id="d5f37-103">Implementación de Microsoft 365 Enterprise con una infraestructura existente</span><span class="sxs-lookup"><span data-stu-id="d5f37-103">Deployment of Microsoft 365 Enterprise with existing infrastructure</span></span>

<span data-ttu-id="d5f37-p101">Muchas organizaciones ya poseen componentes de redes, identidades o de otro tipo en productos locales de Microsoft y servicios basados en la nube. En este artículo, se describe cada fase de la implementación de Microsoft 365 Enterprise para que pueda determinar rápidamente cómo adaptar o cambiar su infraestructura existente.</span><span class="sxs-lookup"><span data-stu-id="d5f37-p101">Many organizations have exisiting networking, identity, and other components or Microsoft on-premises products and cloud-based services. This article steps through each phase of the deployment of Microsoft 365 Enterprise so you can quickly determine how to adapt or change your existing infrastructure.</span></span>

<span data-ttu-id="d5f37-p102">Antes de terminar cada fase, necesita examinar los criterios de salida, que son un conjunto de condiciones obligatorias que necesita cumplir y de condiciones opcionales que es importante tener en cuenta. Los criterios de salida de cada fase garantizan que la infraestructura de nube y local, así como la configuración de un extremo a otro, cumplan con los requisitos de una implementación de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d5f37-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meets the requirements for a Microsoft 365 Enterprise deployment.</span></span>

> [!Note] 
> <span data-ttu-id="d5f37-p103">FastTrack es una ventaja continuada y repetible (disponible como parte de su suscripción) ofrecida por ingenieros de Microsoft para ayudarle a migrar a la nube a su propio ritmo. FastTrack también le ofrece acceso a partners cualificados para servicios adicionales, si es necesario. Con más de 40 000 clientes habilitados hasta la fecha, FastTrack permite maximizar la rentabilidad de la inversión, agilizar la implementación y mejorar la adopción en su organización. Vea [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span><span class="sxs-lookup"><span data-stu-id="d5f37-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

## <a name="exit-criteria-for-networking-phase-1"></a><span data-ttu-id="d5f37-112">Criterios de salida de redes (fase 1)</span><span class="sxs-lookup"><span data-stu-id="d5f37-112">Exit criteria for networking (phase 1)</span></span>

<span data-ttu-id="d5f37-113">Revise las siguientes condiciones obligatorias y opcionales para la infraestructura de red.</span><span class="sxs-lookup"><span data-stu-id="d5f37-113">Step through the following required and optional conditions for the networking infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for networking](./includes/deployment-exit-criteria-networking.md)]

## <a name="exit-criteria-for-identity-phase-2"></a><span data-ttu-id="d5f37-114">Criterios de salida de identidades (fase 2)</span><span class="sxs-lookup"><span data-stu-id="d5f37-114">Exit criteria for identity (phase 2)</span></span>

<span data-ttu-id="d5f37-115">Revise las siguientes condiciones obligatorias y opcionales para la infraestructura de identidades.</span><span class="sxs-lookup"><span data-stu-id="d5f37-115">Step through the following required and optional conditions for the identity infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-identity.md)]

## <a name="exit-criteria-for-windows-10-enterprise-phase-3"></a><span data-ttu-id="d5f37-116">Criterios de salida para Windows 10 Enterprise (fase 3)</span><span class="sxs-lookup"><span data-stu-id="d5f37-116">Exit criteria for Windows 10 Enterprise (phase 3)</span></span>

<span data-ttu-id="d5f37-117">Revise las siguientes condiciones obligatorias y opcionales para la infraestructura de Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d5f37-117">Step through the following required and optional conditions for the Windows 10 Enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-windows10.md)]

## <a name="exit-criteria-for-office-365-proplus-phase-4"></a><span data-ttu-id="d5f37-118">Criterios de salida de Office 365 ProPlus (fase 4)</span><span class="sxs-lookup"><span data-stu-id="d5f37-118">Exit criteria for Office 365 ProPlus (phase 4)</span></span>

<span data-ttu-id="d5f37-119">Asegúrese de que cumple con los requisitos de evaluación, planeamiento de implementación e implementación de la infraestructura de Office 365 ProPlus para Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d5f37-119">Meet the requirements for assessment, deployment planning, and deployment of the Office 365 ProPlus infrastructure for Microsoft 365 Enterprise.</span></span>

[!INCLUDE [Deployment exit criteria for Office 365 ProPlus](./includes/deployment-exit-criteria-office365proplus.md)]

## <a name="exit-criteria-for-mobile-device-management-phase-5"></a><span data-ttu-id="d5f37-120">Criterios de salida para la administración de dispositivos móviles (fase 5)</span><span class="sxs-lookup"><span data-stu-id="d5f37-120">Exit criteria for mobile device management (phase 5)</span></span>

<span data-ttu-id="d5f37-121">Asegúrese de que cumple con los requisitos siguientes para la infraestructura de administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="d5f37-121">Meet the following requirements for the mobile device management infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for mobile device management](./includes/deployment-exit-criteria-mobility.md)]

## <a name="exit-criteria-for-information-protection-phase-6"></a><span data-ttu-id="d5f37-122">Criterios de salida de protección de la información (fase 6)</span><span class="sxs-lookup"><span data-stu-id="d5f37-122">Exit criteria for information protection (phase 6)</span></span>

<span data-ttu-id="d5f37-123">Revise las siguientes condiciones obligatorias y opcionales para la infraestructura de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="d5f37-123">Step through the following required and optional conditions for the information protection infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for information protection](./includes/deployment-exit-criteria-infoprotect.md)]

