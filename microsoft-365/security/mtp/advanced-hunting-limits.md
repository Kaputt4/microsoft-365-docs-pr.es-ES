---
title: Cuotas de búsqueda avanzada y parámetros de uso en Microsoft 365 Defender
description: Comprender varias cuotas y parámetros de uso (límites de servicio) que mantienen la capacidad de respuesta del servicio de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, esquema, kusto, límite de CPU, límite de consulta, recursos, resultados máximos, cuota, parámetros, asignación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929795"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Cuotas de búsqueda avanzada y parámetros de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Para mantener el servicio con rendimiento y capacidad de respuesta, la búsqueda avanzada establece varias cuotas y parámetros de uso (también conocidos como "límites de servicio"). Estas cuotas y parámetros se aplican a las consultas que se ejecutan manualmente y mediante reglas [de detección personalizadas.](custom-detection-rules.md) Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar los procedimientos recomendados [de optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones.

Consulte la tabla siguiente para comprender las cuotas existentes y los parámetros de uso.

| Cuota o parámetro | Size | Ciclo de actualización | Description |
|--|--|--|--|
| Rango de datos | 30 días | Cada consulta | Cada consulta puede buscar datos de hasta los últimos 30 días. |
| Conjunto de resultados | 10 000 filas | Cada consulta | Cada consulta puede devolver hasta 10.000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta puede ejecutarse durante un máximo de 10 minutos. Si no se completa en 10 minutos, el servicio muestra un error.
| Recursos de CPU | En función del tamaño del espacio empresarial | - En la hora y, a continuación, cada 15 minutos<br>- Diariamente a las 12 medianoche | El servicio aplica la cuota diaria y la cuota de 15 minutos por separado. Por cada cuota, el [portal muestra](advanced-hunting-errors.md) un error siempre que se ejecuta una consulta y el espacio empresarial ha consumido más del 10 % de los recursos asignados. Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo diario o de 15 minutos. |

>[!NOTE] 
>Se aplica un conjunto independiente de cuotas y parámetros a las consultas de búsqueda avanzada realizadas a través de la API. [Leer sobre las API de búsqueda avanzada](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados de búsqueda avanzada](advanced-hunting-best-practices.md)
- [Controlar errores de búsqueda avanzada](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)