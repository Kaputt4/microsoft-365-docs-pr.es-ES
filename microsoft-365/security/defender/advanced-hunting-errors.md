---
title: Controlar errores en la búsqueda avanzada de Microsoft 365 Defender
description: Descripción de los errores que se muestran al usar la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, esquema, kusto, tiempo de espera, recursos, errores, error desconocido, límites, cuota, parámetro, asignación
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
ms.topic: article
ms.openlocfilehash: 3886e1b8e70ba16e02e039171b60c4a209a83ec4
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68049416"
---
# <a name="handle-advanced-hunting-errors"></a>Controlar errores de búsqueda avanzados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión


La búsqueda avanzada muestra errores para notificar errores de sintaxis y cada vez que las consultas alcanzan [cuotas predefinidas y parámetros de uso](advanced-hunting-limits.md). Consulte la tabla siguiente para obtener sugerencias sobre cómo resolver o evitar errores.

| Tipo de error | Causa | Solución | Ejemplos de mensajes de error |
|--|--|--|--|
| Errores de sintaxis | La consulta contiene nombres no reconocidos, incluidas referencias a operadores, columnas, funciones o tablas que no existen. | Asegúrese de que las referencias a [los operadores y funciones de Kusto](/azure/data-explorer/kusto/query/) son correctas. Compruebe [el esquema](advanced-hunting-schema-tables.md) de las columnas, funciones y tablas de búsqueda avanzadas correctas. Incluya las cadenas de variable entre comillas para que se reconozcan. Mientras escribe las consultas, use las sugerencias de autocompletar de IntelliSense. | `A recognition error occurred.` |
| Errores semánticos | Aunque la consulta usa nombres válidos para operador, columna, función o tabla, hay errores en su estructura y en la lógica resultante. En algunos casos, la búsqueda avanzada identifica al operador específico que produjo el error. | Compruebe si hay errores en la estructura de la consulta. Consulte la [documentación de Kusto](/azure/data-explorer/kusto/query/) para obtener instrucciones. Mientras escribe las consultas, use las sugerencias de autocompletar de IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeouts | Una consulta solo se puede ejecutar dentro de un [período limitado antes de agotar el tiempo de espera](advanced-hunting-limits.md). Este error puede producirse con más frecuencia al ejecutar consultas complejas. | [Optimización de la consulta](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Limitación de la CPU | Las consultas del mismo inquilino han superado los [recursos de CPU](advanced-hunting-limits.md) asignados en función del tamaño del inquilino. | El servicio comprueba el uso de recursos de la CPU cada 15 minutos y cada día y muestra advertencias después de que el uso supere el 10 % de la cuota asignada. Si alcanza un uso del 100 %, el servicio bloquea las consultas hasta después del siguiente ciclo diario o de 15 minutos. [Optimización de las consultas para evitar alcanzar las cuotas de CPU](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Se ha superado el límite de tamaño de los resultados  | El tamaño agregado del conjunto de resultados de la consulta ha superado el tamaño máximo. Este error puede producirse si el conjunto de resultados es tan grande que el truncamiento en el límite de 10 000 registros no puede reducirlo a un tamaño aceptable. Los resultados que tienen varias columnas con un contenido considerable tienen más probabilidades de verse afectados por este error. | [Optimización de la consulta](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Consumo excesivo de recursos | La consulta ha consumido una cantidad excesiva de recursos y se ha impedido que se complete. En algunos casos, la búsqueda avanzada identifica al operador específico que no se ha optimizado. | [Optimización de la consulta](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Errores desconocidos | Error en la consulta debido a un motivo desconocido. | Intente ejecutar la consulta de nuevo. Póngase en contacto con Microsoft a través del portal si las consultas siguen devolviendo errores desconocidos. | `An unexpected error occurred during query execution. Please try again in a few minutes.`



## <a name="related-topics"></a>Temas relacionados
- [Procedimientos recomendados de búsqueda avanzada](advanced-hunting-best-practices.md)
- [Parámetros de uso y cuotas](advanced-hunting-limits.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [introducción a Lenguaje de consulta Kusto](/azure/data-explorer/kusto/query/)