---
title: Información general sobre las capacidades de detección y respuesta de puntos de conexión
ms.reviewer: ''
description: Obtenga información sobre las capacidades de detección y respuesta de puntos de conexión en ATP de Microsoft Defender
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 858ea0f8d46ac2489dd6ef5c10caf2ce0879e4fb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076520"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="9b426-103">Información general sobre la detección y respuesta de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="9b426-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9b426-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9b426-104">**Applies to:**</span></span>
- [<span data-ttu-id="9b426-105">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9b426-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9b426-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b426-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9b426-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="9b426-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b426-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="9b426-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9b426-109">Las capacidades de detección y respuesta de puntos de conexión de Defender para endpoints proporcionan detecciones avanzadas de ataques que son casi en tiempo real y que pueden actuar.</span><span class="sxs-lookup"><span data-stu-id="9b426-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="9b426-110">Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas.</span><span class="sxs-lookup"><span data-stu-id="9b426-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="9b426-111">Cuando se detecta una amenaza, se crean alertas en el sistema para que un analista la investigue.</span><span class="sxs-lookup"><span data-stu-id="9b426-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="9b426-112">Las alertas con las mismas técnicas de ataque o atribuidas al mismo atacante se agregan a una entidad denominada _incidente_.</span><span class="sxs-lookup"><span data-stu-id="9b426-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="9b426-113">Agregar alertas de esta manera permite a los analistas investigar y responder de forma colectiva a las amenazas con facilidad.</span><span class="sxs-lookup"><span data-stu-id="9b426-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="9b426-114">Inspirada en la mentalidad de "asumir vulneración", Defender for Endpoint recopila continuamente la telemetría cibernética de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9b426-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="9b426-115">Esto incluye la información de procesos, las actividades de red, ópticas produndas en el kernel y el administrador de memoria, las actividades de inicio de sesión de usuario, los cambios en el registro y el sistema de archivos, entre otros.</span><span class="sxs-lookup"><span data-stu-id="9b426-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="9b426-116">La información se almacena durante seis meses, lo que permite que un analista se desplace hacia el tiempo de inicio de un ataque.</span><span class="sxs-lookup"><span data-stu-id="9b426-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="9b426-117">El analista puede dinamizar varias vistas y enfocar una investigación a través de varios vectores.</span><span class="sxs-lookup"><span data-stu-id="9b426-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="9b426-118">Las capacidades de respuesta le ofrecen la posibilidad de solucionar rápidamente las amenazas al actuar en las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="9b426-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9b426-119">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9b426-119">Related topics</span></span>
- [<span data-ttu-id="9b426-120">Panel de operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="9b426-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="9b426-121">Cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="9b426-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="9b426-122">Cola de alertas</span><span class="sxs-lookup"><span data-stu-id="9b426-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="9b426-123">Lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="9b426-123">Devices list</span></span>](machines-view-overview.md)

