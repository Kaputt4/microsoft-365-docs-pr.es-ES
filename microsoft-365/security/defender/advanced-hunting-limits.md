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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: fe0ad42ac0ebfc7f6816e412ab6ffb0ac9291b44
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60643178"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Cuotas de búsqueda avanzada y parámetros de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Para mantener el servicio con rendimiento y capacidad de respuesta, la búsqueda avanzada establece varias cuotas y parámetros de uso (también conocidos como "límites de servicio"). Estas cuotas y parámetros se aplican por separado a las consultas que se ejecutan manualmente y a las consultas que se ejecutan mediante reglas [de detección personalizadas.](custom-detection-rules.md) Los clientes que ejecutan varias consultas con regularidad deben tener en cuenta estos límites y aplicar procedimientos recomendados de [optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones.

Consulte la tabla siguiente para comprender las cuotas existentes y los parámetros de uso.

| Cuota o parámetro | Size |  Ciclo de actualización | Descripción |
|--|--|--|--|
| Rango de datos: | 30 días | Cada consulta | Cada consulta puede buscar datos de hasta los últimos 30 días. |
| Conjunto de resultados | 10 000 filas | Cada consulta | Cada consulta puede devolver hasta 10 000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta se puede ejecutar durante un máximo de 10 minutos. Si no se completa en 10 minutos, el servicio muestra un error.
| Recursos de la CPU | En función del tamaño del inquilino | Cada 15 minutos | El [portal muestra un error cada](advanced-hunting-errors.md) vez que se ejecuta una consulta y el inquilino ha consumido más del 10 % de los recursos asignados. Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo de 15 minutos. |

>[!NOTE] 
>Se aplica un conjunto independiente de cuotas y parámetros a las consultas de búsqueda avanzadas realizadas a través de la API. [Leer acerca de las API de búsqueda avanzada](./api-advanced-hunting.md)

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados de búsqueda avanzada](advanced-hunting-best-practices.md)
- [Controlar errores de búsqueda avanzados](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)