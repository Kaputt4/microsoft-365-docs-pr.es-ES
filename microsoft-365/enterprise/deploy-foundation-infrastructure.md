---
title: Infraestructura básica de Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda las fases principales para implementar la infraestructura básica de Microsoft 365 Enterprise en su organización.
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871158"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="7c0f3-103">Infraestructura básica de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c0f3-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="7c0f3-104">Para alcanzar por completo las ventajas de Microsoft 365 Enterprise, empezará la implementación con su infraestructura básica.</span><span class="sxs-lookup"><span data-stu-id="7c0f3-104">To fully realize the benefits of Microsoft 365 Enterprise, you’ll begin your deployment with its foundation infrastructure.</span></span> 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a><span data-ttu-id="7c0f3-105">Infraestructura básica para implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c0f3-105">Foundation infrastructure for deploying Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7c0f3-p101">La infraestructura básica es el trabajo preliminar necesario antes de implementar cargas de trabajo de productividad (como Microsoft Teams y Exchange Online en Office 365) y escenarios (como la migración a Microsoft 365 y la automatización de actualizaciones del cliente). Ofrece una integración de seguridad inteligente que simplifica la administración continuada, lo que garantiza que el software cliente se actualice con las mejoras más recientes en productividad y seguridad.</span><span class="sxs-lookup"><span data-stu-id="7c0f3-p101">The foundation infrastructure is the groundwork upon which you can deploy productivity workloads (such as Microsoft Teams and Exchange Online in Office 365) and scenarios (such as migrating to Microsoft 365 and automating client updates). It provides intelligent security and integration that simplifies ongoing management, which ensures that your client software is updated with the latest productivity and security enhancements.</span></span>

<span data-ttu-id="7c0f3-108">Use las fases siguientes para planear e implementar la infraestructura básica de Microsoft 365 Enterprise en su organización:</span><span class="sxs-lookup"><span data-stu-id="7c0f3-108">You'll use the following phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise in your organization:</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="7c0f3-109">Fase 1: Redes</span><span class="sxs-lookup"><span data-stu-id="7c0f3-109">Phase 1: Networking</span></span>](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="7c0f3-110">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="7c0f3-110">Phase 2: Identity</span></span>](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="7c0f3-111">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c0f3-111">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="7c0f3-112">Fase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="7c0f3-112">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="7c0f3-113">Fase 5: Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="7c0f3-113">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="7c0f3-114">Fase 6: Protección de la información</span><span class="sxs-lookup"><span data-stu-id="7c0f3-114">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)|


<span data-ttu-id="7c0f3-p102">Antes de terminar cada fase, necesita examinar los criterios de salida, que son un conjunto de condiciones obligatorias que necesita cumplir y de condiciones opcionales que es importante tener en cuenta. Los criterios de salida de cada fase garantizan que la infraestructura de nube y local, así como la configuración de un extremo a otro, cumplan con los requisitos de una implementación de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7c0f3-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="7c0f3-117">Vea este vídeo breve sobre cómo funciona el contenido de la infraestructura básica.</span><span class="sxs-lookup"><span data-stu-id="7c0f3-117">Watch this short video on how the foundation infrastructure content works.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="7c0f3-118">En la siguiente ilustración se muestra la infraestructura básica en el contenido general de la implementación de Microsoft 365 Enterprise y los pasos intermedios.</span><span class="sxs-lookup"><span data-stu-id="7c0f3-118">The following figure shows the foundation infrastructure in the overall Microsoft 365 Enterprise deployment content and your path through it.</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a><span data-ttu-id="7c0f3-119">FastTrack</span><span class="sxs-lookup"><span data-stu-id="7c0f3-119">FastTrack</span></span>

<span data-ttu-id="7c0f3-p103">FastTrack es una ventaja continuada y repetible (disponible como parte de su suscripción) ofrecida por ingenieros de Microsoft para ayudarle a migrar a la nube a su propio ritmo. FastTrack también le ofrece acceso a partners cualificados para servicios adicionales, si es necesario. Con más de 40 000 clientes habilitados hasta la fecha, FastTrack permite maximizar la rentabilidad de la inversión, agilizar la implementación y mejorar la adopción en su organización. Vea [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span><span class="sxs-lookup"><span data-stu-id="7c0f3-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span> 

<span data-ttu-id="7c0f3-p104">Si quiere aprovechar FastTrack para implementar Microsoft 365 Enterprise, puede usar el [Asesor de implementación de Microsoft 365](https://aka.ms/microsoft365setupguide) de FastTrack para obtener directrices sobre cómo implementar y configurar la infraestructura básica. Debe haber iniciado sesión como administrador global en un inquilino de Office 365 o Microsoft 365 para disponer de acceso a esta página.</span><span class="sxs-lookup"><span data-stu-id="7c0f3-p104">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="next-step"></a><span data-ttu-id="7c0f3-126">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7c0f3-126">Next step</span></span>

<span data-ttu-id="7c0f3-p105">Si tiene una infraestructura existente para Office 365, Enterprise Mobility + Security o Windows 10 Enterprise, vea [Implementación de Microsoft 365 Enterprise con una infraestructura existente](deploy-with-existing-infrastructure.md). En este artículo, se describen los criterios de salida de cada fase. Con esta información, podrá determinar con mayor rapidez lo que necesita cambiar para conseguir que su infraestructura de TI sea compatible con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7c0f3-p105">If you have existing infrastructure for Office 365, Enterprise Mobility + Security, or Windows 10 Enterprise, see [Deployment of Microsoft 365 Enterprise with existing infrastructure](deploy-with-existing-infrastructure.md). This article steps you through the exit criteria for each phase. With this information, you can more quickly determine what you need to change to make your IT infrastructure Microsoft 365 Enterprise-compliant.</span></span>

<span data-ttu-id="7c0f3-130">De lo contrario, puede empezar la implementación integral de Microsoft 365 Enterprise con [Fase 1: Redes](networking-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="7c0f3-130">Otherwise, you can begin your Microsoft 365 Enterprise end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>