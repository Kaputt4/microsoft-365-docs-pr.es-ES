---
title: Solucionar problemas de servicio de Microsoft 365 Defender
description: Buscar soluciones y soluciones para problemas conocidos de Microsoft 365 Defender
keywords: solucionar problemas de Protección contra amenazas de Microsoft, solucionar problemas, Azure ATP, problemas, complemento, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925723"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="09f50-104">Solucionar problemas de servicio de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09f50-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="09f50-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="09f50-105">**Applies to:**</span></span>
- <span data-ttu-id="09f50-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09f50-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="09f50-107">En esta sección se abordan los problemas que pueden surgir al usar el servicio de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="09f50-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="09f50-108">No veo contenido de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09f50-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="09f50-109">Si no ve funcionalidades en el panel de navegación como Incidentes, Centro de actividades o Búsqueda en el portal, deberá comprobar que su espacio empresarial tiene las licencias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="09f50-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="09f50-110">Para obtener más información, vea [Requisitos previos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="09f50-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="09f50-111">Las alertas de Identidad de Microsoft Defender no se muestran en los incidentes de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09f50-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="09f50-112">Si ha implementado Microsoft Defender for Identity en su entorno, pero no ve alertas de Defender for Identity como parte de los incidentes de Microsoft 365 Defender, deberá asegurarse de que la integración de Microsoft Cloud App Security y Defender for Identity está habilitada.</span><span class="sxs-lookup"><span data-stu-id="09f50-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="09f50-113">Para obtener más información, vea [Microsoft Defender para la integración de Identidad.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="09f50-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="09f50-114">¿Dónde está la página de configuración para activar el servicio?</span><span class="sxs-lookup"><span data-stu-id="09f50-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="09f50-115">Para activar Microsoft 365 Defender, acceda a **Configuración** desde el panel de navegación en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09f50-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="09f50-116">Este elemento de navegación solo es visible si tiene los permisos y licencias de [requisitos previos.](mtp-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="09f50-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
