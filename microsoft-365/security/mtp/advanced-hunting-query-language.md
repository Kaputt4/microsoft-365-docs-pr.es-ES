---
title: Conozca el lenguaje de consulta de la búsqueda avanzada de la Protección contra amenazas de Microsoft
description: Cree su primera consulta de búsqueda de amenazas y obtenga información sobre los operadores comunes y otros aspectos del lenguaje de consulta de búsqueda avanzada
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, idioma, aprendizaje, primera consulta, telemetría, eventos, telemetría, detecciones personalizadas, esquema, kusto, operadores, tipos de datos, PowerShell descarga, ejemplo de consulta
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
ms.openlocfilehash: e093bd9c5a76b44cf66591b4212f37014189186e
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929001"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conozca el lenguaje de consulta de búsqueda avanzada

**Se aplica a:**
- Protección contra amenazas de Microsoft

La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/). Puede usar la sintaxis y los operadores Kusto para crear consultas que buscan información en el [esquema](advanced-hunting-schema-tables.md) específicamente estructurado para la búsqueda avanzada. Para entender mejor estos conceptos, ejecute la primera consulta.

## <a name="try-your-first-query"></a>Pruebe la primera consulta

En el centro de seguridad de Microsoft 365, vaya a **búsqueda** para ejecutar la primera consulta. Utilice el ejemplo siguiente:

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Así se verá en la búsqueda avanzada.

![Imagen de la consulta de búsqueda avanzada de Microsoft Threat Protection](../../media/advanced-hunting-query-example.png)

Se ha agregado un breve comentario al principio de la consulta para describir su significado. Esto le ayudará si más adelante decide guardar la consulta y compartirla con otras personas de la organización. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Generalmente, la consulta comienza con un nombre de tabla seguido de una serie de elementos precedidos por un operador de canalización (`|`). En este ejemplo, empezamos creando una Unión de dos tablas `DeviceProcessEvents` y `DeviceNetworkEvents`, y agregamos elementos canalizados según sea necesario.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
El primer elemento canalizado es un filtro de tiempo cuyo ámbito es el de los siete días anteriores. Un intervalo de tiempo tan reducido como sea posible garantiza que las consultas funcionen bien, devuelvan resultados que se puedan administrar y no se agote el tiempo de espera.

```kusto
| where Timestamp > ago(7d)
```

El intervalo de tiempo va seguido inmediatamente de una búsqueda de nombres de archivo de proceso que representan la aplicación de PowerShell.

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

Después, la consulta busca cadenas en las líneas de comandos que se suelen usar para descargar archivos con PowerShell.

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
```
Ahora que la consulta identifica claramente los datos que desea localizar, agregue elementos que definen cómo son los resultados. `project`Devuelve columnas específicas y `top` limita el número de resultados, lo que ayuda a garantizar que los resultados tengan un formato muy grande y razonable y fácil de procesar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Haga clic en **Ejecutar consulta** para ver los resultados. Seleccione el icono de expandir en la parte superior derecha del editor de consultas para centrarse en la consulta de búsqueda y los resultados.

![Imagen del control de expansión en el editor de consultas de caza avanzada](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Conozca más operadores comunes de consulta para la búsqueda avanzada

Ahora que ha ejecutado la primera consulta y tiene una idea general de los componentes, es hora de retroceder un poco y aprender más sobre los aspectos básicos. El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.

| Operador | Descripción y uso |
|--|--|
| `where` | Filtra una tabla hasta llegar al subconjunto de filas que satisfacen un predicado. |
| `summarize` | Crea una tabla que agrega el contenido de la tabla de entrada. |
| `join` | Combina las filas de dos tablas para formar una nueva tabla mediante la coincidencia de los valores de la columna o columnas especificadas de cada tabla. |
| `count` | Devuelve el número de registros en el conjunto de registros de entrada. |
| `top` | Devuelve los primeros N registros ordenados según las columnas especificadas. |
| `limit` | Devuelve hasta el número de filas especificado. |
| `project` | Selecciona las columnas que desea incluir, cambia el nombre o elimina e inserta nuevas columnas calculadas. |
| `extend` | Crea columnas calculadas y las anexa al conjunto de resultados. |
| `makeset` |  Devuelve una matriz dinámica (JSON) del conjunto de valores distintivos que Expr toma en el grupo. |
| `find` | Busca las filas que coinciden con un predicado en un conjunto de tablas. |

Para ver un ejemplo dinámico de estos operadores, ejecútelos desde la sección **Comenzar** en la búsqueda avanzada.

## <a name="understand-data-types-and-their-query-syntax-implications"></a>Los tipos de datos y sus implicaciones de sintaxis de consulta

Los datos de las tablas de búsqueda avanzada se clasifican generalmente en los siguientes tipos de datos.

| Tipo de datos | Descripción e implicaciones de la consulta |
|--|--|
| `datetime` | Información sobre datos y hora que representan las marcas de tiempo del evento |
| `string` | Cadena de caracteres |
| `bool` | Verdadero o falso |
| `int` | Valor numérico de 32 bits  |
| `long` | Valor numérico de 64 bits |

## <a name="use-sample-queries"></a>Usar las consultas de ejemplo

La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual. Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.

![Imagen de la ventana de búsqueda avanzada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas. Explore las consultas compartidas en la parte izquierda de la página o en el repositorio de consultas de GitHub.

## <a name="access-query-language-documentation"></a>Acceso a documentación del lenguaje de consulta

Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
