---
title: Solucionar problemas de servicio de Microsoft 365 Defender
description: Buscar soluciones y soluciones alternativas a problemas conocidos de Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a2cd27bf7bf8b1c4931b9d768f3a6b5e5f2a0d93
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592041"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="c4f7a-104">Solucionar problemas de servicio de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4f7a-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c4f7a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c4f7a-105">**Applies to:**</span></span>
- <span data-ttu-id="c4f7a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4f7a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c4f7a-107">En esta sección se abordan los problemas que pueden surgir al usar el servicio de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c4f7a-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="c4f7a-108">No veo contenido de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4f7a-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="c4f7a-109">Si no ve funcionalidades en el panel de navegación como incidentes, centro de acciones o búsqueda en el portal, deberá comprobar que el inquilino tiene las licencias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="c4f7a-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="c4f7a-110">Para obtener más información, vea [Requisitos previos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="c4f7a-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="c4f7a-111">Las alertas de Identidad de Microsoft Defender no aparecen en los incidentes de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4f7a-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="c4f7a-112">Si tienes Microsoft Defender for Identity implementado en el entorno pero no ves alertas de Defender for Identity como parte de incidentes de Microsoft 365 Defender, tendrás que asegurarte de que la integración de Microsoft Cloud App Security y Defender for Identity está habilitada.</span><span class="sxs-lookup"><span data-stu-id="c4f7a-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="c4f7a-113">Para obtener más información, vea [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="c4f7a-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="c4f7a-114">¿Dónde está la página de configuración para activar el servicio?</span><span class="sxs-lookup"><span data-stu-id="c4f7a-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="c4f7a-115">Para activar Microsoft 365 Defender, accede a **Configuración** desde el panel de navegación en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4f7a-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="c4f7a-116">Este elemento de navegación solo está visible si tiene los permisos [y licencias de requisitos previos.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="c4f7a-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="c4f7a-117">¿Cómo puedo crear una excepción para mi archivo/dirección URL?</span><span class="sxs-lookup"><span data-stu-id="c4f7a-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="c4f7a-118">Un falso positivo es un archivo o dirección URL que se detecta como malintencionado pero no es una amenaza.</span><span class="sxs-lookup"><span data-stu-id="c4f7a-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="c4f7a-119">Puede crear indicadores y definir exclusiones para desbloquear y permitir determinados archivos/direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="c4f7a-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="c4f7a-120">Consulte [Dirección de falsos positivos/negativos en Defender para Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span><span class="sxs-lookup"><span data-stu-id="c4f7a-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


