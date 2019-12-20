---
title: Mejores prácticas de búsqueda avanzada de Protección contra amenazas de Microsoft
description: Obtenga información sobre cómo crear consultas de búsqueda de amenazas rápidas, eficientes y sin errores al usar la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, consulta, telemetría, detecciones personalizadas, esquema, kusto, evitar tiempos de espera, líneas de comando, identificación del proceso
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 871f659074c4f8386746e341db4d3500c5e80a31
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807009"
---
# <a name="advanced-hunting-query-best-practices"></a>Prácticas recomendadas para la consulta de búsqueda avanzada

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="optimize-query-performance"></a>Optimizar el rendimiento de las consultas
Aplique estas recomendaciones para obtener resultados más rápidamente y evite tiempos de espera al ejecutar consultas complejas:
- Al probar nuevas consultas, utilice siempre `limit` para evitar conjuntos de resultados extremadamente grandes. También puede evaluar inicialmente el tamaño del conjunto de resultados con `count`.
- Use los filtros de tiempo primero. Idealmente, limite sus consultas a esos días.
- Se deben quitar la mayoría de los datos del comienzo de la consulta, justo después del filtro de hora.
- Use el operador `has` a través de `contains` al buscar tokens completos.
- Busque en una columna específica en lugar de ejecutar búsquedas de texto completo en todas las columnas.
- Cuando se unen tablas, primero debe especificarse la tabla con menos filas.
- `project` solo las columnas necesarias de las tablas que ha unido.

>[!Tip]
>Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Sugerencias y dificultades de la consulta

### <a name="queries-with-process-ids"></a>Consultas con Id. de proceso
Los Id. de proceso (PID) se reciclan en Windows y se reutilizan para los nuevos procesos. Por sí solos, no pueden servir como identificadores únicos para procesos específicos.

Para obtener un identificador único para un proceso en un equipo específico, utilice el Id. de proceso conjuntamente con la hora de creación del proceso. Cuando se une a los datos en torno a los procesos, debe incluir columnas para el identificador de la máquina (tanto `DeviceId` como `DeviceName`), el identificador de proceso (`ProcessId` o `InitiatingProcessId`) y la hora de creación del proceso (`ProcessCreationTime` o `InitiatingProcessCreationTime`).

En la siguiente consulta de ejemplo se buscan procesos que obtienen acceso a más de 10 direcciones IP por el puerto 445 (SMB), lo que podría buscar recursos compartidos de archivos.

Consulta de ejemplo:
```
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
- Use coincidencias que no distinga mayúsculas de minúsculas. Por ejemplo, use `=~`, `in~` y `contains` en lugar de `==`, `in` y `contains_cs`
- Para mitigar las técnicas de ofuscación de línea de comandos de DOS, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios seguidos por un solo espacio. Tenga en cuenta que existen técnicas de ofuscación de DOS más complejas que requieren otras soluciones, pero pueden ayudar a solucionar los más comunes.

En los ejemplos siguientes se muestran varias formas de crear una consulta que busque el archivo *net.exe* para detener el servicio Firewall de Windows Defender:

```
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
## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
