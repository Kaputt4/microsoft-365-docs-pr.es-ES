---
title: 'Fase 1: Infraestructura de red para Microsoft 365 Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Los pasos para implementar la infraestructura de red de Microsoft 365 Enterprise.
ms.openlocfilehash: d575d8c3156ac1fc1a8a2bca96c875d4587ebf05
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871420"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="1f0c7-103">Fase 1: Infraestructura de red para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f0c7-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="1f0c7-p101">En Microsoft 365 Enterprise, se incluyen Office 365 y Windows Intune como parte de Enterprise Mobility + Security (EMS). Estos dos servicios basados en la nube usan la seguridad, el rendimiento y la confiabilidad de las conexiones de dispositivos cliente por Internet o con circuitos dedicados. Para hospedar estos servicios y ofrecerlos a clientes de todo el mundo, Microsoft diseñó una infraestructura de red que da prioridad al rendimiento y la integración.</span><span class="sxs-lookup"><span data-stu-id="1f0c7-p101">Microsoft 365 Enterprise includes Office 365 and Windows Intune as part of Enterprise Management + Security (EMS). Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits. To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="1f0c7-p102">En esta fase, se describen las consideraciones clave para crear una conexión estable a los servicios en la nube de Microsoft 365 Enterprise. Para obtener información general, vea [Principios de redes de Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="1f0c7-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="1f0c7-109">Si ya implementó una infraestructura de red, vea los [criterios de salida](networking-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1f0c7-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="1f0c7-110">Planear e implementar la infraestructura de red de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f0c7-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="1f0c7-111">Siga este procedimiento para preparar la infraestructura de red para los requisitos y funciones de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1f0c7-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="1f0c7-112">Preparar la red para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f0c7-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="1f0c7-113">Configurar conexiones a Internet locales para cada oficina</span><span class="sxs-lookup"><span data-stu-id="1f0c7-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="1f0c7-114">Evitar las redirecciones de red</span><span class="sxs-lookup"><span data-stu-id="1f0c7-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="1f0c7-115">Configurar la omisión de tráfico</span><span class="sxs-lookup"><span data-stu-id="1f0c7-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="1f0c7-116">Optimizar el rendimiento del servicio de Office 365 y el cliente</span><span class="sxs-lookup"><span data-stu-id="1f0c7-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="1f0c7-117">Cuando complete estos pasos, vaya a los [criterios de salida](networking-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1f0c7-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="1f0c7-118">Cómo Microsoft migra a Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f0c7-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1f0c7-119">Eche un vistazo en Microsoft y aprenda cómo se prepara la empresa para una red de Microsoft optimizada para los servicios de nube de Office 365 con [Optimización del rendimiento de red para Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span><span class="sxs-lookup"><span data-stu-id="1f0c7-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="1f0c7-120">Cómo Contoso implementó Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f0c7-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1f0c7-121">Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [optimizó su red](contoso-networking.md) para los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f0c7-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="1f0c7-122">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="1f0c7-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="1f0c7-123">Preparar la red para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f0c7-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

