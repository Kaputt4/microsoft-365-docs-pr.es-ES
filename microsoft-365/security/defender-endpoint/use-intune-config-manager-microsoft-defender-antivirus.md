---
title: Configurar Antivirus de Microsoft Defender con Microsoft Endpoint Manager
description: Use Microsoft Endpoint Manager y Microsoft Intune para configurar Microsoft Defender AV y Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683756"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="6576c-104">Use Microsoft Endpoint Manager para configurar y administrar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6576c-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6576c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6576c-105">**Applies to:**</span></span>

- [<span data-ttu-id="6576c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6576c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6576c-107">Puede usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para configurar los Antivirus de Microsoft Defender digitalizaciones.</span><span class="sxs-lookup"><span data-stu-id="6576c-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="6576c-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Configuration Manager](/mem/configmgr/core/understand/introduction) ahora forman parte de Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="6576c-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="6576c-109">Configurar Antivirus de Microsoft Defender exámenes en Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="6576c-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="6576c-110">Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="6576c-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="6576c-111">Vaya a **Endpoint Security**.</span><span class="sxs-lookup"><span data-stu-id="6576c-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="6576c-112">En **Administrar**, elija **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="6576c-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="6576c-113">Seleccione la directiva Antivirus de Microsoft Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="6576c-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="6576c-114">En **Administrar**, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6576c-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="6576c-115">Junto a **Opciones de configuración**, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6576c-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="6576c-116">Expanda la **sección** Examinar y revise o edite la configuración del examen.</span><span class="sxs-lookup"><span data-stu-id="6576c-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="6576c-117">Elija **Revisar y guardar**</span><span class="sxs-lookup"><span data-stu-id="6576c-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="6576c-118">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="6576c-118">Need help?</span></span> <span data-ttu-id="6576c-119">Consulte [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span><span class="sxs-lookup"><span data-stu-id="6576c-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="6576c-120">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="6576c-120">Related articles</span></span>

- [<span data-ttu-id="6576c-121">Artículos de referencia para herramientas de administración y configuración</span><span class="sxs-lookup"><span data-stu-id="6576c-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6576c-122">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="6576c-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)