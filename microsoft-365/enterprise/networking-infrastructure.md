---
title: 'Fase 1: Infraestructura de red para Microsoft 365 Enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Los pasos para implementar la infraestructura de red de Microsoft 365 Enterprise.
ms.openlocfilehash: 9a805ffbdbdc19ef5943a0c0ba0ff8f010d3e19b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066612"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="e5fd1-103">Fase 1: Infraestructura de red para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e5fd1-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![Fase 1: Redes](../media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="e5fd1-105">Microsoft 365 Enterprise incluye Office 365, Microsoft Intune y numerosos servicios de identidad y seguridad de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e5fd1-105">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="e5fd1-106">Todos estos servicios en la nube se basan en la seguridad, rendimiento y confiabilidad de conexiones de los dispositivos del cliente a través de Internet o circuitos dedicados.</span><span class="sxs-lookup"><span data-stu-id="e5fd1-106">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="e5fd1-107">Para hospedar estos servicios y hacer que estén disponibles para los clientes de todo el mundo, Microsoft ha diseñado una infraestructura de red que destaca por el rendimiento e integración.</span><span class="sxs-lookup"><span data-stu-id="e5fd1-107">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="e5fd1-p102">En esta fase, se describen las consideraciones clave para crear una conexión estable a los servicios en la nube de Microsoft 365 Enterprise. Para obtener información general, vea [Principios de redes de Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="e5fd1-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="e5fd1-110">Si ya implementó una infraestructura de red, vea los [criterios de salida](networking-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e5fd1-110">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="e5fd1-111">Planear e implementar la infraestructura de red de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e5fd1-111">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="e5fd1-112">Siga este procedimiento para preparar la infraestructura de red para los requisitos y funciones de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e5fd1-112">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Paso 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="e5fd1-114">Preparar la red para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5fd1-114">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![Paso 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="e5fd1-116">Configurar conexiones a Internet locales para cada oficina</span><span class="sxs-lookup"><span data-stu-id="e5fd1-116">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![Paso 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="e5fd1-118">Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="e5fd1-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![Paso 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="e5fd1-120">Configurar la omisión de tráfico</span><span class="sxs-lookup"><span data-stu-id="e5fd1-120">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![Paso 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="e5fd1-122">Optimizar el rendimiento del servicio de Office 365 y el cliente</span><span class="sxs-lookup"><span data-stu-id="e5fd1-122">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="e5fd1-123">Cuando complete estos pasos, vaya a los [criterios de salida](networking-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e5fd1-123">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="e5fd1-124">Cómo Microsoft utiliza Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e5fd1-124">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e5fd1-125">Obtenga información sobre Microsoft y cómo la empresa [optimizó la red de Microsoft para servicios en la nube](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="e5fd1-125">Peek inside Microsoft and learn how the company [optimized the Microsoft network for cloud services](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="e5fd1-126">Cómo Contoso hizo Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e5fd1-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e5fd1-127">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [optimizó sus dispositivos de red y conexión a Internet](contoso-networking.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5fd1-127">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="e5fd1-129">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="e5fd1-129">Next step</span></span>

|||
|:-------|:-----|
|![Paso 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="e5fd1-131">Preparar la red para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5fd1-131">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

