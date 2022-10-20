---
title: Cuotas de búsqueda avanzadas y parámetros de uso en Microsoft 365 Defender
description: Descripción de varias cuotas y parámetros de uso (límites de servicio) que mantienen la capacidad de respuesta del servicio de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, esquema, kusto, límite de CPU, límite de consultas, recursos, resultados máximos, cuota, parámetros, asignación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 479495a5d0026283622cc1c42db6ab0b730c3652
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633579"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Cuotas de búsqueda avanzadas y parámetros de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Para mantener el rendimiento y la capacidad de respuesta del servicio, la búsqueda avanzada establece varias cuotas y parámetros de uso (también conocidos como "límites de servicio"). Estas cuotas y parámetros se aplican por separado a las consultas que se ejecutan manualmente y a las consultas que se ejecutan mediante [reglas de detección personalizadas](custom-detection-rules.md). Los clientes que ejecutan varias consultas con regularidad deben tener en cuenta estos límites y [aplicar los procedimientos recomendados de optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones.

Consulte la tabla siguiente para comprender las cuotas y los parámetros de uso existentes.

| Cuota o parámetro | Size |  Ciclo de actualización | Descripción |
|--|--|--|--|
| Rango de datos: | 30 días | Cada consulta | Cada consulta puede buscar datos de hasta los últimos 30 días. |
| Conjunto de resultados | 10 000 filas | Cada consulta | Cada consulta puede devolver hasta 10 000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta se puede ejecutar durante un máximo de 10 minutos. Si no se completa en 10 minutos, el servicio muestra un error.
| Recursos de la CPU | En función del tamaño del inquilino | Cada 15 minutos | El [portal muestra un error](advanced-hunting-errors.md) cada vez que se ejecuta una consulta y el inquilino ha consumido más del 10 % de los recursos asignados. Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo de 15 minutos. |

>[!NOTE] 
>Un conjunto independiente de cuotas y parámetros se aplica a las consultas de búsqueda avanzada realizadas a través de la API. [Obtenga información sobre las API de búsqueda avanzadas.](./api-advanced-hunting.md)

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados de búsqueda avanzada](advanced-hunting-best-practices.md)
- [Controlar errores de búsqueda avanzados](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)