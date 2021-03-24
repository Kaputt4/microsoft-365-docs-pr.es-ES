---
title: Consultar procedimientos recomendados para la búsqueda avanzada
description: Obtenga información sobre cómo crear consultas de búsqueda de amenazas rápidas, eficientes y sin errores al usar la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, detecciones personalizadas, esquema, kusto, evitar el tiempo de espera, líneas de comandos, id. de proceso
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072432"
---
# <a name="advanced-hunting-query-best-practices"></a>Prácticas recomendadas para la consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a>Optimizar el rendimiento de las consultas

Aplique estas recomendaciones para obtener resultados más rápido y evitar tiempos de espera mientras ejecuta consultas complejas.

- Al probar nuevas consultas, utilice siempre `limit` para evitar conjuntos de resultados extremadamente grandes. También puede evaluar inicialmente el tamaño del conjunto de resultados con `count`.
- Use los filtros de tiempo primero. Lo ideal es limitar las consultas a siete días.
- Se deben quitar la mayoría de los datos del comienzo de la consulta, justo después del filtro de hora.
- Use el operador `has` a través de `contains` al buscar tokens completos.
- Busque en una columna específica en lugar de ejecutar búsquedas de texto completo en todas las columnas.
- Cuando se unen tablas, primero debe especificarse la tabla con menos filas.
- `project` solo las columnas necesarias de las tablas que ha unido.

>[!TIP]
>Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Sugerencias y dificultades de la consulta

### <a name="queries-with-process-ids"></a>Consultas con Id. de proceso

Los Id. de proceso (PID) se reciclan en Windows y se reutilizan para los nuevos procesos. Por sí solos, no pueden servir como identificadores únicos para procesos específicos. Para obtener un identificador único para un proceso en un dispositivo específico, usa el identificador del proceso junto con el tiempo de creación del proceso. Al unir o resumir datos alrededor de procesos, incluya columnas para el identificador del dispositivo (o ), el identificador de proceso ( o ) y el tiempo de creación `DeviceId` del proceso ( o `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` ).

En la siguiente consulta de ejemplo se buscan procesos que obtienen acceso a más de 10 direcciones IP por el puerto 445 (SMB), lo que podría buscar recursos compartidos de archivos.

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

La consulta resume tanto en `InitiatingProcessId` como en `InitiatingProcessCreationTime` para que se vea un único proceso, sin mezclar varios procesos con el mismo Id. de proceso.

### <a name="queries-with-command-lines"></a>Consultas con líneas de comandos

Las líneas de comandos pueden variar. Cuando sea posible, filtre por nombres de archivo y realice la coincidencia aproximada.

Hay varias formas de crear una línea de comandos para llevar a cabo una tarea. Por ejemplo, un atacante puede hacer referencia a un archivo de imagen con o sin una ruta de acceso, sin una extensión de archivo, mediante variables de entorno, o entre comillas. Además, el atacante también podría cambiar el orden de los parámetros o agregar varias comillas y espacios.

Para crear consultas más duraderas mediante líneas de comandos, aplique los procedimientos siguientes:

- Identifique los procesos conocidos (como, por ejemplo, *net.exe* o *psexec.exe*), en lugar de filtrarlos en el campo de la línea de comandos.
- Al consultar argumentos de la línea de comandos, no busque una coincidencia exacta en varios argumentos no relacionados en un orden determinado. En su lugar, use expresiones regulares o use operadores de contenedores separados múltiples.
- Use coincidencias que no distinga mayúsculas de minúsculas. Por ejemplo, use `=~` , y en lugar de , `in~` `contains` `==` `in` y `contains_cs`
- Para mitigar las técnicas de ofuscación de línea de comandos de DOS, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios seguidos por un solo espacio. Tenga en cuenta que existen técnicas de ofuscación de DOS más complejas que requieren otras soluciones, pero pueden ayudar a solucionar los más comunes.

En los ejemplos siguientes se muestran varias formas de crear una consulta que busque el archivo *net.exe* para detener el servicio Firewall de Windows Defender:

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
