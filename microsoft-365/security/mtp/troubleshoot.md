---
title: Solucionar problemas de servicio de Microsoft 365 Defender
description: Buscar soluciones y soluciones para problemas conocidos de Microsoft 365 Defender
keywords: solucionar problemas de Microsoft Threat Protection, troubleshoot, Azure ATP, issues, add-on, settings page
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
ms.openlocfilehash: d01912532ad2a00abbecee0d0a337be7baf87017
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918671"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="7ba05-104">Solucionar problemas de servicio de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ba05-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7ba05-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7ba05-105">**Applies to:**</span></span>
- <span data-ttu-id="7ba05-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ba05-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7ba05-107">En esta sección se abordan los problemas que pueden surgir al usar el servicio de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7ba05-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="7ba05-108">No veo contenido de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ba05-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="7ba05-109">Si no ve funcionalidades en el panel de navegación como incidentes, centro de acciones o búsqueda en el portal, deberá comprobar que el inquilino tiene las licencias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="7ba05-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="7ba05-110">Para obtener más información, vea [Requisitos previos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="7ba05-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="7ba05-111">Las alertas de Identidad de Microsoft Defender no aparecen en los incidentes de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ba05-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="7ba05-112">Si tienes Microsoft Defender for Identity implementado en el entorno pero no ves alertas de Defender for Identity como parte de incidentes de Microsoft 365 Defender, tendrás que asegurarte de que la integración de Microsoft Cloud App Security y Defender for Identity está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7ba05-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="7ba05-113">Para obtener más información, vea [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="7ba05-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="7ba05-114">¿Dónde está la página de configuración para activar el servicio?</span><span class="sxs-lookup"><span data-stu-id="7ba05-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="7ba05-115">Para activar Microsoft 365 Defender, accede a **Configuración** desde el panel de navegación en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ba05-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="7ba05-116">Este elemento de navegación solo está visible si tiene los permisos [y licencias de requisitos previos.](mtp-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="7ba05-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>