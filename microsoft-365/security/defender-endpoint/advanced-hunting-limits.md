---
title: Límites avanzados de búsqueda en ATP de Microsoft Defender
description: Comprender varios límites de servicio que mantienen el servicio de búsqueda avanzada con capacidad de respuesta
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, wdatp, búsqueda, consulta, telemetría, esquema, kusto, límite de CPU, límite de consulta, recursos, resultados máximos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075984"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="98c17-104">Límites avanzados de servicio de búsqueda</span><span class="sxs-lookup"><span data-stu-id="98c17-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98c17-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="98c17-105">**Applies to:**</span></span>
- [<span data-ttu-id="98c17-106">Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="98c17-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="98c17-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="98c17-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98c17-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="98c17-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="98c17-109">Para mantener el servicio con rendimiento y capacidad de respuesta, la búsqueda avanzada establece varios límites para que las consultas se ejecuten manualmente y mediante reglas [de detección personalizadas.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="98c17-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="98c17-110">Consulte la tabla siguiente para comprender estos límites.</span><span class="sxs-lookup"><span data-stu-id="98c17-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="98c17-111">Límite</span><span class="sxs-lookup"><span data-stu-id="98c17-111">Limit</span></span> | <span data-ttu-id="98c17-112">Size</span><span class="sxs-lookup"><span data-stu-id="98c17-112">Size</span></span> | <span data-ttu-id="98c17-113">Ciclo de actualización</span><span class="sxs-lookup"><span data-stu-id="98c17-113">Refresh cycle</span></span> | <span data-ttu-id="98c17-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="98c17-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="98c17-115">Rango de datos</span><span class="sxs-lookup"><span data-stu-id="98c17-115">Data range</span></span> | <span data-ttu-id="98c17-116">30 días</span><span class="sxs-lookup"><span data-stu-id="98c17-116">30 days</span></span> | <span data-ttu-id="98c17-117">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="98c17-117">Every query</span></span> | <span data-ttu-id="98c17-118">Cada consulta puede buscar datos desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="98c17-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="98c17-119">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="98c17-119">Result set</span></span> | <span data-ttu-id="98c17-120">10.000 filas</span><span class="sxs-lookup"><span data-stu-id="98c17-120">10,000 rows</span></span> | <span data-ttu-id="98c17-121">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="98c17-121">Every query</span></span> | <span data-ttu-id="98c17-122">Cada consulta puede devolver hasta 10 000 registros.</span><span class="sxs-lookup"><span data-stu-id="98c17-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="98c17-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="98c17-123">Timeout</span></span> | <span data-ttu-id="98c17-124">10 minutos</span><span class="sxs-lookup"><span data-stu-id="98c17-124">10 minutes</span></span> | <span data-ttu-id="98c17-125">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="98c17-125">Every query</span></span> | <span data-ttu-id="98c17-126">Cada consulta puede ejecutarse durante un máximo de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="98c17-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="98c17-127">Si no se completa en 10 minutos, el servicio muestra un error.</span><span class="sxs-lookup"><span data-stu-id="98c17-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="98c17-128">Recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="98c17-128">CPU resources</span></span> | <span data-ttu-id="98c17-129">En función del tamaño del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="98c17-129">Based on tenant size</span></span> | <span data-ttu-id="98c17-130">- En la hora y, a continuación, cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="98c17-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="98c17-131">- Diario a las 12 medianoche</span><span class="sxs-lookup"><span data-stu-id="98c17-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="98c17-132">El servicio aplica el límite diario y el límite de 15 minutos por separado.</span><span class="sxs-lookup"><span data-stu-id="98c17-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="98c17-133">Por cada límite, el [portal muestra](advanced-hunting-errors.md) un error cada vez que se ejecuta una consulta y el inquilino ha consumido más del 10 % de los recursos asignados.</span><span class="sxs-lookup"><span data-stu-id="98c17-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="98c17-134">Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo diario o de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="98c17-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="98c17-135">Se aplica un conjunto independiente de límites a las consultas de búsqueda avanzadas realizadas a través de la API.</span><span class="sxs-lookup"><span data-stu-id="98c17-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="98c17-136">Leer acerca de las API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="98c17-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="98c17-137">Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar los procedimientos recomendados de [optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones resultantes de superar estos límites.</span><span class="sxs-lookup"><span data-stu-id="98c17-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="98c17-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="98c17-138">Related topics</span></span>

- [<span data-ttu-id="98c17-139">Procedimientos recomendados de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="98c17-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="98c17-140">Controlar errores de búsqueda avanzados</span><span class="sxs-lookup"><span data-stu-id="98c17-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="98c17-141">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="98c17-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98c17-142">Reglas de detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="98c17-142">Custom detections rules</span></span>](custom-detection-rules.md)
