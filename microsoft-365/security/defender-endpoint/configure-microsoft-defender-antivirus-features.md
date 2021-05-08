---
title: Configurar las funciones del Antivirus de Microsoft Defender
description: Puede configurar las Antivirus de Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo y PowerShell.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, configurar, configuración, Administrador de configuración, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, administración de dispositivos móviles, GP, directiva de grupo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275113"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="701fd-104">Configurar las funciones del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="701fd-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="701fd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="701fd-105">**Applies to:**</span></span>

- [<span data-ttu-id="701fd-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="701fd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="701fd-107">Puede configurar Antivirus de Microsoft Defender con una serie de herramientas, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="701fd-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="701fd-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="701fd-108">Microsoft Intune</span></span>
- <span data-ttu-id="701fd-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="701fd-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="701fd-110">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="701fd-110">Group Policy</span></span>
- <span data-ttu-id="701fd-111">Cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="701fd-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="701fd-112">Instrumental de administración de Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="701fd-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="701fd-113">Se pueden configurar las siguientes categorías generales de características:</span><span class="sxs-lookup"><span data-stu-id="701fd-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="701fd-114">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="701fd-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="701fd-115">Protección siempre activa en tiempo real, incluida la protección basada en el comportamiento, heurística y de aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="701fd-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="701fd-116">Cómo interactúan los usuarios finales con el cliente en puntos de conexión individuales</span><span class="sxs-lookup"><span data-stu-id="701fd-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="701fd-117">En los siguientes artículos se describe cómo realizar tareas clave al configurar Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="701fd-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="701fd-118">Cada artículo incluye instrucciones para la herramienta de configuración aplicable (o herramientas).</span><span class="sxs-lookup"><span data-stu-id="701fd-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="701fd-119">Artículo</span><span class="sxs-lookup"><span data-stu-id="701fd-119">Article</span></span>  |<span data-ttu-id="701fd-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="701fd-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="701fd-121">Usar la protección de protección Antivirus de Microsoft Defender microsoft</span><span class="sxs-lookup"><span data-stu-id="701fd-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="701fd-122">Use la protección entregada en la nube para la detección avanzada, rápida y sólida de antivirus.</span><span class="sxs-lookup"><span data-stu-id="701fd-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="701fd-123">Configurar la protección en tiempo real, heurística y de comportamiento</span><span class="sxs-lookup"><span data-stu-id="701fd-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="701fd-124">Habilite la protección antivirus basada en comportamiento, heurística y en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="701fd-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="701fd-125">Configurar la interacción del usuario final con Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="701fd-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="701fd-126">Configure cómo interactúan los usuarios finales de su organización con Antivirus de Microsoft Defender, qué notificaciones ven y si pueden invalidar la configuración.</span><span class="sxs-lookup"><span data-stu-id="701fd-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="701fd-127">También puede revisar el tema Temas de referencia para [herramientas](configuration-management-reference-microsoft-defender-antivirus.md) de administración y configuración para obtener información general sobre cada herramienta y vínculos para obtener más ayuda.</span><span class="sxs-lookup"><span data-stu-id="701fd-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>