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
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844923"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="7ef2a-104">Solucionar problemas de los servicios de protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ef2a-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="7ef2a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7ef2a-105">**Applies to:**</span></span>
- <span data-ttu-id="7ef2a-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ef2a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7ef2a-107">Esta sección trata los problemas que pueden surgir al usar el servicio de protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ef2a-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="7ef2a-108">No veo el contenido de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7ef2a-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="7ef2a-109">Si no ve funcionalidades en el panel de navegación, como los incidentes, el centro de actividades o la caza, deberá comprobar que el inquilino tiene las licencias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="7ef2a-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="7ef2a-110">Para obtener más información, vea [Requisitos previos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="7ef2a-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="7ef2a-111">Las alertas de ATP de Azure no se muestran dentro de los incidentes de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ef2a-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="7ef2a-112">Si tiene Azure ATP implementado en su entorno, pero no ve las alertas de ATP de Azure como parte de los incidentes de la protección contra amenazas de Microsoft, deberá asegurarse de que la integración entre Microsoft Cloud App Security y Azure ATP está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7ef2a-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="7ef2a-113">Para más información, consulte [Integración de Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration):</span><span class="sxs-lookup"><span data-stu-id="7ef2a-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="7ef2a-114">¿Dónde se encuentra la página de configuración para activar el servicio?</span><span class="sxs-lookup"><span data-stu-id="7ef2a-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="7ef2a-115">Para activar la protección contra amenazas de Microsoft, obtenga acceso a la **configuración** del panel de navegación del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ef2a-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="7ef2a-116">Este elemento de navegación es visible solo si tiene los [permisos y licencias necesarios](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="7ef2a-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

