---
title: Cuotas de caza avanzadas y parámetros de uso de la protección contra amenazas de Microsoft
description: Comprenda varias cuotas y parámetros de uso (límites de servicio) que mantendrán el servicio de búsqueda avanzada receptivo
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, esquema, kusto, límite de CPU, límite de consulta, recursos, resultados máximos, cuota, parámetros, asignación
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
ms.openlocfilehash: 192fb47aafdd20bd5e1f0774a64ec3215f1203d1
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636910"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="e89b5-104">Cuotas de caza avanzadas y parámetros de uso</span><span class="sxs-lookup"><span data-stu-id="e89b5-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e89b5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e89b5-105">**Applies to:**</span></span>
- <span data-ttu-id="e89b5-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e89b5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e89b5-107">Para mantener el servicio y la capacidad de respuesta del servicio, la búsqueda avanzada establece varias cuotas y parámetros de uso (también conocidos como "límites de servicio").</span><span class="sxs-lookup"><span data-stu-id="e89b5-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="e89b5-108">Estas cuotas y parámetros se aplican a las consultas que se ejecutan manualmente y por [reglas de detección personalizadas](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="e89b5-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="e89b5-109">Los clientes que ejecutan varias consultas regularmente deben realizar un seguimiento del consumo y [aplicar procedimientos recomendados de optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="e89b5-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="e89b5-110">Consulte la tabla siguiente para conocer las cuotas existentes y los parámetros de uso.</span><span class="sxs-lookup"><span data-stu-id="e89b5-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="e89b5-111">Cuota o parámetro</span><span class="sxs-lookup"><span data-stu-id="e89b5-111">Quota or parameter</span></span> | <span data-ttu-id="e89b5-112">Size</span><span class="sxs-lookup"><span data-stu-id="e89b5-112">Size</span></span> | <span data-ttu-id="e89b5-113">Ciclo de actualización</span><span class="sxs-lookup"><span data-stu-id="e89b5-113">Refresh cycle</span></span> | <span data-ttu-id="e89b5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e89b5-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="e89b5-115">Rango de datos</span><span class="sxs-lookup"><span data-stu-id="e89b5-115">Data range</span></span> | <span data-ttu-id="e89b5-116">30 días</span><span class="sxs-lookup"><span data-stu-id="e89b5-116">30 days</span></span> | <span data-ttu-id="e89b5-117">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="e89b5-117">Every query</span></span> | <span data-ttu-id="e89b5-118">Cada consulta puede buscar datos de hasta los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="e89b5-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="e89b5-119">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="e89b5-119">Result set</span></span> | <span data-ttu-id="e89b5-120">10.000 filas</span><span class="sxs-lookup"><span data-stu-id="e89b5-120">10,000 rows</span></span> | <span data-ttu-id="e89b5-121">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="e89b5-121">Every query</span></span> | <span data-ttu-id="e89b5-122">Cada consulta puede devolver hasta 10.000 registros.</span><span class="sxs-lookup"><span data-stu-id="e89b5-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="e89b5-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="e89b5-123">Timeout</span></span> | <span data-ttu-id="e89b5-124">10 minutos</span><span class="sxs-lookup"><span data-stu-id="e89b5-124">10 minutes</span></span> | <span data-ttu-id="e89b5-125">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="e89b5-125">Every query</span></span> | <span data-ttu-id="e89b5-126">Cada consulta puede ejecutarse durante un máximo de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="e89b5-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="e89b5-127">Si no se completa en 10 minutos, el servicio muestra un error.</span><span class="sxs-lookup"><span data-stu-id="e89b5-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="e89b5-128">Recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="e89b5-128">CPU resources</span></span> | <span data-ttu-id="e89b5-129">Basado en el tamaño del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="e89b5-129">Based on tenant size</span></span> | <span data-ttu-id="e89b5-130">-En la hora y después cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="e89b5-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="e89b5-131">-Diariamente el 12 de la noche</span><span class="sxs-lookup"><span data-stu-id="e89b5-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="e89b5-132">El servicio exige por separado la cuota diaria y de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="e89b5-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="e89b5-133">Para cada cuota, el [portal muestra un error](advanced-hunting-errors.md) siempre que se ejecuta una consulta y el inquilino se ha consumido más del 10% de los recursos asignados.</span><span class="sxs-lookup"><span data-stu-id="e89b5-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="e89b5-134">Las consultas se bloquean si el inquilino ha alcanzado el 100% hasta después del siguiente ciclo diario o de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="e89b5-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="e89b5-135">Se aplica un conjunto de cuotas y parámetros por separado a las consultas de búsqueda avanzada realizadas a través de la API.</span><span class="sxs-lookup"><span data-stu-id="e89b5-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="e89b5-136">Leer sobre las API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e89b5-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="e89b5-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e89b5-137">Related topics</span></span>

- [<span data-ttu-id="e89b5-138">Procedimientos recomendados para la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e89b5-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e89b5-139">Controlar errores de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e89b5-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="e89b5-140">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e89b5-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e89b5-141">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="e89b5-141">Custom detections overview</span></span>](custom-detections-overview.md)