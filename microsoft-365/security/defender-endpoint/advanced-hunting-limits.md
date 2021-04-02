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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499526"
---
# <a name="advanced-hunting-service-limits"></a>Límites avanzados de servicio de búsqueda

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Para mantener el servicio con rendimiento y capacidad de respuesta, la búsqueda avanzada establece varios límites para que las consultas se ejecuten manualmente y mediante reglas [de detección personalizadas.](custom-detection-rules.md) Consulte la tabla siguiente para comprender estos límites.

| Límite | Size | Ciclo de actualización | Descripción |
|--|--|--|--|
| Rango de datos | 30 días | Cada consulta | Cada consulta puede buscar datos desde los últimos 30 días. |
| Conjunto de resultados | 10.000 filas | Cada consulta | Cada consulta puede devolver hasta 10 000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta puede ejecutarse durante un máximo de 10 minutos. Si no se completa en 10 minutos, el servicio muestra un error.
| Recursos de CPU | En función del tamaño del espacio empresarial | - En la hora y, a continuación, cada 15 minutos<br>- Diario a las 12 medianoche | El servicio aplica el límite diario y el límite de 15 minutos por separado. Por cada límite, el [portal muestra](advanced-hunting-errors.md) un error cada vez que se ejecuta una consulta y el inquilino ha consumido más del 10 % de los recursos asignados. Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo diario o de 15 minutos. |

>[!NOTE] 
>Se aplica un conjunto independiente de límites a las consultas de búsqueda avanzadas realizadas a través de la API. [Leer acerca de las API de búsqueda avanzada](run-advanced-query-api.md)

Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar los procedimientos recomendados de [optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones resultantes de superar estos límites.

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados de búsqueda avanzada](advanced-hunting-best-practices.md)
- [Controlar errores de búsqueda avanzados](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Reglas de detecciones personalizadas](custom-detection-rules.md)
