---
title: Solucionar problemas Microsoft 365 servicio de Defender
description: Buscar soluciones y soluciones para problemas conocidos Microsoft 365 Defender
keywords: solucionar Microsoft 365 Defender, solucionar problemas, Microsoft Defender para identidad, problemas, complemento, página de configuración
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
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782746"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="1c57a-104">Solucionar problemas Microsoft 365 servicio de Defender</span><span class="sxs-lookup"><span data-stu-id="1c57a-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1c57a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1c57a-105">**Applies to:**</span></span>
- <span data-ttu-id="1c57a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c57a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1c57a-107">En esta sección se abordan los problemas que pueden surgir al usar el servicio Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1c57a-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="1c57a-108">No veo el contenido de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c57a-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="1c57a-109">Si no ve funcionalidades en el panel de navegación como incidentes, centro de acciones o búsqueda en el portal, deberá comprobar que el inquilino tiene las licencias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="1c57a-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="1c57a-110">Para obtener más información, consulte [Requisitos previos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="1c57a-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="1c57a-111">Las alertas de Microsoft Defender para identidades no aparecen en los incidentes de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c57a-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="1c57a-112">Si tienes Microsoft Defender for Identity implementado en el entorno, pero no ves alertas de Defender for Identity como parte de incidentes de Microsoft 365 Defender, tendrás que asegurarte de que la integración de Microsoft Cloud App Security y Defender for Identity está habilitada.</span><span class="sxs-lookup"><span data-stu-id="1c57a-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="1c57a-113">Para obtener más información, vea [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="1c57a-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="1c57a-114">¿Dónde está la página de configuración para activar el servicio?</span><span class="sxs-lookup"><span data-stu-id="1c57a-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="1c57a-115">Para activar Microsoft 365 Defender, accede a **Configuración** desde el panel de navegación en el centro Microsoft 365 seguridad.</span><span class="sxs-lookup"><span data-stu-id="1c57a-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="1c57a-116">Este elemento de navegación solo está visible si tiene los permisos [y licencias de requisitos previos.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="1c57a-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="1c57a-117">¿Cómo puedo crear una excepción para mi archivo/dirección URL?</span><span class="sxs-lookup"><span data-stu-id="1c57a-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="1c57a-118">Un falso positivo es un archivo o dirección URL que se detecta como malintencionado pero no es una amenaza.</span><span class="sxs-lookup"><span data-stu-id="1c57a-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="1c57a-119">Puede crear indicadores y definir exclusiones para desbloquear y permitir determinados archivos/direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="1c57a-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="1c57a-120">Consulte [Dirección de falsos positivos/negativos en Defender para Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span><span class="sxs-lookup"><span data-stu-id="1c57a-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


