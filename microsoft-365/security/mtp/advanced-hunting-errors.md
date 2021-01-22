---
title: Controlar errores en la búsqueda avanzada de Microsoft 365 Defender
description: Comprender los errores que se muestran al usar la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, esquema, kusto, tiempo de espera, recursos, errores, error desconocido, límites, cuota, parámetro, asignación
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
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929651"
---
# <a name="handle-advanced-hunting-errors"></a>Controlar errores de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


La búsqueda avanzada muestra errores para notificar errores de sintaxis y siempre que las consultas tocan cuotas [predefinidas y parámetros de uso.](advanced-hunting-limits.md) Consulte la tabla siguiente para obtener sugerencias sobre cómo resolver o evitar errores.

| Tipo de error | Motivo | Solución | Ejemplos de mensajes de error |
|--|--|--|--|
| Errores de sintaxis | La consulta contiene nombres no reconocidos, incluidas las referencias a operadores, columnas, funciones o tablas que no existen. | Asegúrate de que las referencias a operadores y funciones de [Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) sean correctas. Compruebe [el esquema de](advanced-hunting-schema-tables.md) las columnas, funciones y tablas de búsqueda avanzada correctas. Escriba las cadenas de variables entre comillas para que se reconozcan. Mientras escribe las consultas, use las sugerencias de autocompletar de IntelliSense. | `A recognition error occurred.` |
| Errores semánticos | Aunque la consulta usa nombres válidos de operador, columna, función o tabla, hay errores en su estructura y lógica resultante. En algunos casos, la búsqueda avanzada identifica el operador específico que provocó el error. | Compruebe si hay errores en la estructura de la consulta. Consulte la [documentación de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) para obtener instrucciones. Mientras escribe las consultas, use las sugerencias de autocompletar de IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Tiempos de espera | Una consulta solo se puede ejecutar en un [período limitado antes de que se desatrase el tiempo de espera.](advanced-hunting-limits.md) Este error puede ocurrir con más frecuencia cuando se ejecutan consultas complejas. | [Optimizar la consulta](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Limitación de CPU | Las consultas en el mismo inquilino han superado los recursos [de CPU](advanced-hunting-limits.md) que se han asignado en función del tamaño del espacio empresarial. | El servicio comprueba el uso de recursos de CPU cada 15 minutos y diariamente y muestra advertencias después de que el uso supere el 10 % de la cuota asignada. Si alcanza el 100 % de uso, el servicio bloquea las consultas hasta después del siguiente ciclo diario o de 15 minutos. [Optimizar las consultas para evitar alcanzar cuotas de CPU](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Se ha excedido el límite de tamaño de resultado  | El tamaño agregado del conjunto de resultados para la consulta ha superado el tamaño máximo. Este error puede producirse si el conjunto de resultados es tan grande que el truncamiento en el límite de 10 000 registros no puede reducirlo a un tamaño aceptable. Es más probable que los resultados que tienen varias columnas con contenido ajustable se verán afectados por este error. | [Optimizar la consulta](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Consumo excesivo de recursos | La consulta ha consumido demasiadas cantidades de recursos y se ha detenido para que no se complete. En algunos casos, la búsqueda avanzada identifica el operador específico que no se ha optimizado. | [Optimizar la consulta](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Errores desconocidos | Error en la consulta debido a un motivo desconocido. | Intente ejecutar la consulta de nuevo. Póngase en contacto con Microsoft a través del portal si las consultas siguen devolviendo errores desconocidos. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Temas relacionados
- [Procedimientos recomendados de búsqueda avanzada](advanced-hunting-best-practices.md)
- [Parámetros de uso y cuotas](advanced-hunting-limits.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Información general sobre el lenguaje de consulta de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
