---
title: 'Fase 1: Infraestructura de red para Microsoft 365 Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Los pasos para implementar la infraestructura de red de Microsoft 365 Enterprise.
ms.openlocfilehash: 35c65515854bb0c47a45e48d8e3c6af6a80d907c
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982801"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="3b7d7-103">Fase 1: Infraestructura de red para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b7d7-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="3b7d7-104">Microsoft 365 Enterprise incluye Office 365, Microsoft Intune y numerosos servicios de identidad y seguridad de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="3b7d7-104">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="3b7d7-105">Todos estos servicios en la nube se basan en la seguridad, rendimiento y confiabilidad de conexiones de los dispositivos del cliente a través de Internet o circuitos dedicados.</span><span class="sxs-lookup"><span data-stu-id="3b7d7-105">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="3b7d7-106">Para hospedar estos servicios y hacer que estén disponibles para los clientes de todo el mundo, Microsoft ha diseñado una infraestructura de red que destaca por el rendimiento e integración.</span><span class="sxs-lookup"><span data-stu-id="3b7d7-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="3b7d7-p102">En esta fase, se describen las consideraciones clave para crear una conexión estable a los servicios en la nube de Microsoft 365 Enterprise. Para obtener información general, vea [Principios de redes de Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="3b7d7-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="3b7d7-109">Si ya implementó una infraestructura de red, vea los [criterios de salida](networking-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3b7d7-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="3b7d7-110">Planear e implementar la infraestructura de red de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b7d7-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="3b7d7-111">Siga este procedimiento para preparar la infraestructura de red para los requisitos y funciones de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3b7d7-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="3b7d7-112">Preparar la red para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b7d7-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="3b7d7-113">Configurar conexiones a Internet locales para cada oficina</span><span class="sxs-lookup"><span data-stu-id="3b7d7-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="3b7d7-114">Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="3b7d7-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="3b7d7-115">Configurar la omisión de tráfico</span><span class="sxs-lookup"><span data-stu-id="3b7d7-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="3b7d7-116">Optimizar el rendimiento del servicio de Office 365 y el cliente</span><span class="sxs-lookup"><span data-stu-id="3b7d7-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="3b7d7-117">Cuando complete estos pasos, vaya a los [criterios de salida](networking-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3b7d7-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="3b7d7-118">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b7d7-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3b7d7-119">Obtenga información sobre Microsoft y cómo la empresa [optimizó la red de Microsoft para servicios en la nube](https://www.microsoft.com/es-ES/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="3b7d7-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/es-ES/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="3b7d7-120">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b7d7-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3b7d7-121">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [optimizó sus dispositivos de red y conexión a Internet](contoso-networking.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b7d7-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="3b7d7-122">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="3b7d7-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="3b7d7-123">Preparar la red para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b7d7-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

