---
title: Solucionar problemas de los servicios de protección contra amenazas de Microsoft
description: Encontrar soluciones y alternativas para los problemas conocidos de la protección contra amenazas de Microsoft.
keywords: solucionar problemas de protección contra amenazas de Microsoft, solución de problemas, ATP de Azure, problemas, complemento, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661986"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="ad90c-104">Solucionar problemas de los servicios de protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ad90c-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="ad90c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ad90c-105">**Applies to:**</span></span>
- <span data-ttu-id="ad90c-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ad90c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ad90c-107">Esta sección trata los problemas que pueden surgir al usar el servicio de protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad90c-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="ad90c-108">No veo el contenido de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ad90c-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="ad90c-109">Si no ve funcionalidades en el panel de navegación, como los incidentes, el centro de actividades o la caza, deberá comprobar que el inquilino tiene las licencias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="ad90c-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="ad90c-110">Para obtener más información, vea [Requisitos previos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="ad90c-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="ad90c-111">Las alertas de ATP de Azure no se muestran dentro de los incidentes de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ad90c-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="ad90c-112">Si tiene Azure ATP implementado en su entorno, pero no ve las alertas de ATP de Azure como parte de los incidentes de la protección contra amenazas de Microsoft, deberá asegurarse de que la integración entre Microsoft Cloud App Security y Azure ATP está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ad90c-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="ad90c-113">Para más información, consulte [Integración de Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration):</span><span class="sxs-lookup"><span data-stu-id="ad90c-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="ad90c-114">¿Está disponible la protección contra amenazas de Microsoft en la nube de la comunidad del gobierno de los EE. UU. (GCC) o en GCC High?</span><span class="sxs-lookup"><span data-stu-id="ad90c-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="ad90c-115">No está disponible por el momento.</span><span class="sxs-lookup"><span data-stu-id="ad90c-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="ad90c-116">¿Dónde se encuentra la página de configuración para activar el servicio?</span><span class="sxs-lookup"><span data-stu-id="ad90c-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="ad90c-117">Para activar la protección contra amenazas de Microsoft, obtenga acceso a la **configuración** del panel de navegación del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad90c-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="ad90c-118">Este elemento de navegación es visible solo si tiene los [permisos y licencias necesarios](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="ad90c-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="ad90c-119">¿Puedo usar un complemento en lugar de las licencias de E5 necesarias?</span><span class="sxs-lookup"><span data-stu-id="ad90c-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="ad90c-120">Actualmente no hay complementos para la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad90c-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="ad90c-121">Ver requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="ad90c-121">See licensing requirements</span></span>](prerequisites.md) 

