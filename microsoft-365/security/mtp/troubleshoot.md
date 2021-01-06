---
title: Solución de problemas del servicio Microsoft 365 defender
description: Buscar soluciones y trabajos relacionados con problemas conocidos de Microsoft 365 defender
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
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760463"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="54670-104">Solución de problemas del servicio Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="54670-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="54670-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="54670-105">**Applies to:**</span></span>
- <span data-ttu-id="54670-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54670-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="54670-107">En esta sección se tratan los problemas que pueden surgir al usar el servicio de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="54670-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="54670-108">No veo contenido de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="54670-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="54670-109">Si no ve funcionalidades en el panel de navegación, como los incidentes, el centro de actividades o la caza, deberá comprobar que el inquilino tiene las licencias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="54670-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="54670-110">Para obtener más información, vea [Requisitos previos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="54670-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="54670-111">Microsoft defender para las alertas de identidad no se muestra en los incidentes de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="54670-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="54670-112">Si tiene Microsoft defender para la identidad implementada en su entorno pero no ve defender para las alertas de identidad como parte de los incidentes de Microsoft 365 defender, deberá asegurarse de que esté habilitada la seguridad de Microsoft Cloud App y defender para la integración de identidades.</span><span class="sxs-lookup"><span data-stu-id="54670-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="54670-113">Para obtener más información, consulte [Microsoft defender para la integración de identidades](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="54670-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="54670-114">¿Dónde se encuentra la página de configuración para activar el servicio?</span><span class="sxs-lookup"><span data-stu-id="54670-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="54670-115">Para activar Microsoft 365 defender, obtenga acceso a la **configuración** desde el panel de navegación del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54670-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="54670-116">Este elemento de navegación es visible solo si tiene los [permisos y licencias necesarios](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="54670-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
