---
title: Límites de caza avanzado en la protección contra amenazas de Microsoft
description: Comprenda los distintos límites de servicio que mantienen el servicio de búsqueda avanzada receptivo
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, esquema, kusto, límite de CPU, límite de consulta, recursos, máximo de resultados
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ab19c86bbdec243dd4abb8b6c9fab9b5ec6f2228
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430460"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="47efc-104">Límites del servicio de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="47efc-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="47efc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="47efc-105">**Applies to:**</span></span>
- <span data-ttu-id="47efc-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="47efc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="47efc-107">Para mantener el funcionamiento del servicio y responder, la búsqueda avanzada establece varios límites para las consultas que se ejecutan de forma manual y mediante [reglas de detección personalizadas](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="47efc-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="47efc-108">Consulte la tabla siguiente para conocer estos límites.</span><span class="sxs-lookup"><span data-stu-id="47efc-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="47efc-109">Límite</span><span class="sxs-lookup"><span data-stu-id="47efc-109">Limit</span></span> | <span data-ttu-id="47efc-110">Size</span><span class="sxs-lookup"><span data-stu-id="47efc-110">Size</span></span> | <span data-ttu-id="47efc-111">Ciclo de actualización</span><span class="sxs-lookup"><span data-stu-id="47efc-111">Refresh cycle</span></span> | <span data-ttu-id="47efc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="47efc-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="47efc-113">Rango de datos</span><span class="sxs-lookup"><span data-stu-id="47efc-113">Data range</span></span> | <span data-ttu-id="47efc-114">30 días</span><span class="sxs-lookup"><span data-stu-id="47efc-114">30 days</span></span> | <span data-ttu-id="47efc-115">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="47efc-115">Every query</span></span> | <span data-ttu-id="47efc-116">Cada consulta puede buscar datos de hasta los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="47efc-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="47efc-117">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="47efc-117">Result set</span></span> | <span data-ttu-id="47efc-118">10.000 filas</span><span class="sxs-lookup"><span data-stu-id="47efc-118">10,000 rows</span></span> | <span data-ttu-id="47efc-119">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="47efc-119">Every query</span></span> | <span data-ttu-id="47efc-120">Cada consulta puede devolver hasta 10.000 registros.</span><span class="sxs-lookup"><span data-stu-id="47efc-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="47efc-121">Timeout</span><span class="sxs-lookup"><span data-stu-id="47efc-121">Timeout</span></span> | <span data-ttu-id="47efc-122">10 minutos</span><span class="sxs-lookup"><span data-stu-id="47efc-122">10 minutes</span></span> | <span data-ttu-id="47efc-123">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="47efc-123">Every query</span></span> | <span data-ttu-id="47efc-124">Cada consulta puede ejecutarse durante un máximo de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="47efc-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="47efc-125">Si no se completa en 10 minutos, el servicio muestra un error.</span><span class="sxs-lookup"><span data-stu-id="47efc-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="47efc-126">Recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="47efc-126">CPU resources</span></span> | <span data-ttu-id="47efc-127">Basado en el tamaño del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="47efc-127">Based on tenant size</span></span> | <span data-ttu-id="47efc-128">-En la hora y después cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="47efc-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="47efc-129">-Diariamente el 12 de la noche</span><span class="sxs-lookup"><span data-stu-id="47efc-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="47efc-130">El servicio exige el límite diario y de 15 minutos por separado.</span><span class="sxs-lookup"><span data-stu-id="47efc-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="47efc-131">Para cada límite, el [portal muestra un error](advanced-hunting-errors.md) siempre que se ejecuta una consulta y el inquilino se ha consumido más del 10% de los recursos asignados.</span><span class="sxs-lookup"><span data-stu-id="47efc-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="47efc-132">Las consultas se bloquean si el inquilino ha alcanzado el 100% hasta después del siguiente ciclo diario o de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="47efc-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="47efc-133">Se aplica un conjunto de límites independiente a las consultas de búsqueda avanzada realizadas a través de la API.</span><span class="sxs-lookup"><span data-stu-id="47efc-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="47efc-134">Leer sobre las API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="47efc-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="47efc-135">Los clientes que ejecutan varias consultas regularmente deben realizar un seguimiento del consumo y [aplicar los procedimientos recomendados de optimización](advanced-hunting-best-practices.md) para minimizar la interrupción que se derive de superar estos límites.</span><span class="sxs-lookup"><span data-stu-id="47efc-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="47efc-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="47efc-136">Related topics</span></span>

- [<span data-ttu-id="47efc-137">Procedimientos recomendados para la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="47efc-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="47efc-138">Controlar errores de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="47efc-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="47efc-139">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="47efc-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="47efc-140">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="47efc-140">Custom detections overview</span></span>](custom-detections-overview.md)
