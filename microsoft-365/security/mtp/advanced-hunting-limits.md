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
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Cuotas de caza avanzadas y parámetros de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Para mantener el servicio y la capacidad de respuesta del servicio, la búsqueda avanzada establece varias cuotas y parámetros de uso (también conocidos como "límites de servicio"). Estas cuotas y parámetros se aplican a las consultas que se ejecutan manualmente y por [reglas de detección personalizadas](custom-detection-rules.md). Los clientes que ejecutan varias consultas regularmente deben realizar un seguimiento del consumo y [aplicar procedimientos recomendados de optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones.

Consulte la tabla siguiente para conocer las cuotas existentes y los parámetros de uso.

| Cuota o parámetro | Size | Ciclo de actualización | Descripción |
|--|--|--|--|
| Rango de datos | 30 días | Cada consulta | Cada consulta puede buscar datos de hasta los últimos 30 días. |
| Conjunto de resultados | 10.000 filas | Cada consulta | Cada consulta puede devolver hasta 10.000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta puede ejecutarse durante un máximo de 10 minutos. Si no se completa en 10 minutos, el servicio muestra un error.
| Recursos de CPU | Basado en el tamaño del espacio empresarial | -En la hora y después cada 15 minutos<br>-Diariamente el 12 de la noche | El servicio exige por separado la cuota diaria y de 15 minutos. Para cada cuota, el [portal muestra un error](advanced-hunting-errors.md) siempre que se ejecuta una consulta y el inquilino se ha consumido más del 10% de los recursos asignados. Las consultas se bloquean si el inquilino ha alcanzado el 100% hasta después del siguiente ciclo diario o de 15 minutos. |

>[!NOTE] 
>Se aplica un conjunto de cuotas y parámetros por separado a las consultas de búsqueda avanzada realizadas a través de la API. [Leer sobre las API de búsqueda avanzada](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados para la búsqueda avanzada](advanced-hunting-best-practices.md)
- [Controlar errores de búsqueda avanzada](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)