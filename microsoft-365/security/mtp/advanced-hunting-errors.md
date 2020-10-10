---
title: Controlar los errores de la caza avanzada para la protección contra amenazas de Microsoft
description: Comprender los errores mostrados al usar la búsqueda avanzada
keywords: caza avanzado, cazar amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, esquema, kusto, tiempo de espera, recursos, errores, error desconocido
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 939f235a5168766e1ab6982eb9fb554a749ad041
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413823"
---
# <a name="handle-advanced-hunting-errors"></a>Controlar errores de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


La búsqueda avanzada muestra errores para notificar errores de sintaxis y cada vez que las consultas alcanzan [límites predefinidos](advanced-hunting-limits.md). Consulte la tabla siguiente para obtener sugerencias sobre cómo resolver o evitar errores. 

| Tipo de error | Motivo | Solución | Ejemplos de mensajes de error |
|--|--|--|--|
| Errores de sintaxis | La consulta contiene nombres no reconocidos, incluidas las referencias a operadores inexistentes, columnas, funciones o tablas. | Asegúrese de que las referencias a [operadores y funciones de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) son correctas. Compruebe [el esquema](advanced-hunting-schema-tables.md) para ver las columnas, funciones y tablas de búsqueda avanzada correctas. Las cadenas de variable se encierran entre comillas para que se reconozcan. Mientras escribe las consultas, use las sugerencias de autocompletar de IntelliSense. | `A recognition error occurred.` |
| Errores semánticos | Mientras que la consulta usa nombres válidos de operador, columna, función o tabla, hay errores en su estructura y lógica resultante. En algunos casos, la búsqueda avanzada identifica el operador específico que causó el error. | Compruebe si hay errores en la estructura de la consulta. Consulte la [documentación de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) para obtener instrucciones. Mientras escribe las consultas, use las sugerencias de autocompletar de IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Tiempos | Una consulta solo puede ejecutarse en un [período limitado antes](advanced-hunting-limits.md)de que se agote el tiempo de espera. Este error puede producirse con más frecuencia cuando se ejecutan consultas complejas. | [Optimizar la consulta](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Limitación de CPU | Las consultas en el mismo inquilino han superado los [recursos de CPU](advanced-hunting-limits.md) que se han asignado en función del tamaño del espacio empresarial. | El servicio comprueba el uso de recursos de CPU cada 15 minutos y todos los días, y muestra advertencias después de que el uso supere el 10% del límite asignado. Si alcanza el 100% de uso, el servicio bloquea las consultas hasta después del siguiente ciclo diario o de 15 minutos. [Optimizar las consultas para evitar el golpe de límites de CPU](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Límite de tamaño de resultados superado  | El tamaño agregado del conjunto de resultados de la consulta ha superado el límite máximo. Este error puede producirse si el conjunto de resultados es tan grande que el truncamiento en el límite de 10.000-record no puede reducirlo a un tamaño aceptable. Es más probable que se vean afectados por este error los resultados que tengan varias columnas con contenido de tamaño ajustable. | [Optimizar la consulta](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Consumo excesivo de recursos | La consulta ha consumido cantidades excesivas de recursos y se ha detenido para completarse. En algunos casos, la búsqueda avanzada identifica el operador específico que no se optimizó. | [Optimizar la consulta](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Errores desconocidos | Se produjo un error en la consulta debido a un motivo desconocido. | Intente volver a ejecutar la consulta. Póngase en contacto con Microsoft a través del portal si las consultas continúan devolviendo errores desconocidos. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Temas relacionados
- [Procedimientos recomendados para la búsqueda avanzada](advanced-hunting-best-practices.md)
- [Límites del servicio](advanced-hunting-limits.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Información general sobre el lenguaje de consulta Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
