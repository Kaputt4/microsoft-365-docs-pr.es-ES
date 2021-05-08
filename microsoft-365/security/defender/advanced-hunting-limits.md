---
title: Cuotas de búsqueda avanzadas y parámetros de uso en Microsoft 365 Defender
description: Comprender varias cuotas y parámetros de uso (límites de servicio) que mantienen la capacidad de respuesta del servicio de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, esquema, kusto, límite de CPU, límite de consulta, recursos, resultados máximos, cuota, parámetros, asignación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245605"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="8a85a-104">Cuotas de búsqueda avanzada y parámetros de uso</span><span class="sxs-lookup"><span data-stu-id="8a85a-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a85a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8a85a-105">**Applies to:**</span></span>
- <span data-ttu-id="8a85a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a85a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8a85a-107">Para mantener el servicio con rendimiento y capacidad de respuesta, la búsqueda avanzada establece varias cuotas y parámetros de uso (también conocidos como "límites de servicio").</span><span class="sxs-lookup"><span data-stu-id="8a85a-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="8a85a-108">Estas cuotas y parámetros se aplican por separado a las consultas que se ejecutan manualmente y a las consultas que se ejecutan mediante reglas [de detección personalizadas.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="8a85a-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="8a85a-109">Los clientes que ejecutan varias consultas con regularidad deben tener en cuenta estos límites y aplicar procedimientos recomendados de [optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="8a85a-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="8a85a-110">Consulte la tabla siguiente para comprender las cuotas existentes y los parámetros de uso.</span><span class="sxs-lookup"><span data-stu-id="8a85a-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="8a85a-111">Cuota o parámetro</span><span class="sxs-lookup"><span data-stu-id="8a85a-111">Quota or parameter</span></span> | <span data-ttu-id="8a85a-112">Size</span><span class="sxs-lookup"><span data-stu-id="8a85a-112">Size</span></span> | <span data-ttu-id="8a85a-113">Ciclo de actualización</span><span class="sxs-lookup"><span data-stu-id="8a85a-113">Refresh cycle</span></span> | <span data-ttu-id="8a85a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a85a-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="8a85a-115">Rango de datos</span><span class="sxs-lookup"><span data-stu-id="8a85a-115">Data range</span></span> | <span data-ttu-id="8a85a-116">30 días</span><span class="sxs-lookup"><span data-stu-id="8a85a-116">30 days</span></span> | <span data-ttu-id="8a85a-117">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="8a85a-117">Every query</span></span> | <span data-ttu-id="8a85a-118">Cada consulta puede buscar datos desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="8a85a-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="8a85a-119">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="8a85a-119">Result set</span></span> | <span data-ttu-id="8a85a-120">10.000 filas</span><span class="sxs-lookup"><span data-stu-id="8a85a-120">10,000 rows</span></span> | <span data-ttu-id="8a85a-121">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="8a85a-121">Every query</span></span> | <span data-ttu-id="8a85a-122">Cada consulta puede devolver hasta 10 000 registros.</span><span class="sxs-lookup"><span data-stu-id="8a85a-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="8a85a-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="8a85a-123">Timeout</span></span> | <span data-ttu-id="8a85a-124">10 minutos</span><span class="sxs-lookup"><span data-stu-id="8a85a-124">10 minutes</span></span> | <span data-ttu-id="8a85a-125">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="8a85a-125">Every query</span></span> | <span data-ttu-id="8a85a-126">Cada consulta puede ejecutarse durante un máximo de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="8a85a-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="8a85a-127">Si no se completa en 10 minutos, el servicio muestra un error.</span><span class="sxs-lookup"><span data-stu-id="8a85a-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="8a85a-128">Recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="8a85a-128">CPU resources</span></span> | <span data-ttu-id="8a85a-129">En función del tamaño del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="8a85a-129">Based on tenant size</span></span> | <span data-ttu-id="8a85a-130">Cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="8a85a-130">Every 15 minutes</span></span> | <span data-ttu-id="8a85a-131">El [portal muestra un error cada](advanced-hunting-errors.md) vez que se ejecuta una consulta y el inquilino ha consumido más del 10 % de los recursos asignados.</span><span class="sxs-lookup"><span data-stu-id="8a85a-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="8a85a-132">Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="8a85a-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="8a85a-133">Se aplica un conjunto independiente de cuotas y parámetros a las consultas de búsqueda avanzadas realizadas a través de la API.</span><span class="sxs-lookup"><span data-stu-id="8a85a-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="8a85a-134">Leer acerca de las API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="8a85a-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="8a85a-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8a85a-135">Related topics</span></span>

- [<span data-ttu-id="8a85a-136">Procedimientos recomendados de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="8a85a-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8a85a-137">Controlar errores de búsqueda avanzados</span><span class="sxs-lookup"><span data-stu-id="8a85a-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="8a85a-138">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="8a85a-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a85a-139">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="8a85a-139">Custom detections overview</span></span>](custom-detections-overview.md)