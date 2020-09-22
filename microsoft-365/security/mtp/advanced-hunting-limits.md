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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aaba01f5970c9abf55f5fae760d1ba1fed8ba914
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199882"
---
# <a name="advanced-hunting-service-limits"></a>Límites del servicio de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Para mantener el funcionamiento del servicio y responder, la búsqueda avanzada establece varios límites para las consultas que se ejecutan de forma manual y mediante [reglas de detección personalizadas](custom-detection-rules.md). Consulte la tabla siguiente para conocer estos límites.

| Límite | Size | Ciclo de actualización | Descripción |
|--|--|--|--|
| Rango de datos | 30 días | Cada consulta | Cada consulta puede buscar datos de hasta los últimos 30 días. |
| Conjunto de resultados | 10.000 filas | Cada consulta | Cada consulta puede devolver hasta 10.000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta puede ejecutarse durante un máximo de 10 minutos. Si no se completa en 10 minutos, el servicio muestra un error.
| Recursos de CPU | Basado en el tamaño del espacio empresarial | -En la hora y después cada 15 minutos<br>-Diariamente el 12 de la noche | El servicio exige el límite diario y de 15 minutos por separado. Para cada límite, el [portal muestra un error](advanced-hunting-errors.md) siempre que se ejecuta una consulta y el inquilino se ha consumido más del 10% de los recursos asignados. Las consultas se bloquean si el inquilino ha alcanzado el 100% hasta después del siguiente ciclo diario o de 15 minutos. |

>[!NOTE] 
>Se aplica un conjunto de límites independiente a las consultas de búsqueda avanzada realizadas a través de la API. [Leer sobre las API de búsqueda avanzada](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

Los clientes que ejecutan varias consultas regularmente deben realizar un seguimiento del consumo y [aplicar los procedimientos recomendados de optimización](advanced-hunting-best-practices.md) para minimizar la interrupción que se derive de superar estos límites.

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados para la búsqueda avanzada](advanced-hunting-best-practices.md)
- [Controlar errores de búsqueda avanzada](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
