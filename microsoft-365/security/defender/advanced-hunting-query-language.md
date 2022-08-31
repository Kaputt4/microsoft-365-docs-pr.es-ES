---
title: Obtenga información sobre el lenguaje de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Cree su primera consulta de búsqueda de amenazas y obtenga información sobre los operadores comunes y otros aspectos del lenguaje de consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, lenguaje, aprendizaje, primera consulta, telemetría, eventos, telemetría, detecciones personalizadas, esquema, kusto, operadores, tipos de datos, descarga de PowerShell, ejemplo de consulta
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
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ee267084501fad28a0bff592f5c06d130f73a424
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480808"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conozca el lenguaje de consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**

- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](/azure/kusto/query/). Puede usar instrucciones y operadores de Kusto para construir consultas que busquen información en un [esquema](advanced-hunting-schema-tables.md) especializado. 

Vea este breve vídeo para aprender algunos conceptos básicos del lenguaje de consulta Kusto.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRwfJ]
 
Para entender mejor estos conceptos, ejecute la primera consulta.

## <a name="try-your-first-query"></a>Pruebe la primera consulta

En el portal de Microsoft 365 Defender, vaya a **Búsqueda** para ejecutar la primera consulta. Utilice el ejemplo siguiente: 

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

**[Ejecución de esta consulta en la búsqueda avanzada](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Describir la consulta y especificar las tablas que se van a buscar

Se ha agregado un breve comentario al principio de la consulta para describir para qué sirve. Este comentario es útil si luego decide guardar la consulta y compartirla con otras personas de su organización. 

```kusto
// Finds PowerShell execution events that could involve a download
```

La propia consulta normalmente comenzará con un nombre de tabla seguido de varios elementos que comienzan por una canalización (`|`). En este ejemplo, comenzamos creando una unión de dos tablas,  `DeviceProcessEvents` y , y `DeviceNetworkEvents`agregamos elementos canalados según sea necesario.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```

### <a name="set-the-time-range"></a>Establecer el intervalo de tiempo

El primer elemento canalado es un filtro de tiempo con el ámbito de los siete días anteriores. Limitar el intervalo de tiempo ayuda a garantizar que las consultas funcionan bien, devuelven resultados administrables y no agotan el tiempo de espera.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Comprobación de procesos específicos

El intervalo de tiempo va seguido inmediatamente de una búsqueda de nombres de archivo de proceso que representan la aplicación de PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Buscar cadenas de comandos específicas

Después, la consulta busca cadenas en las líneas de comandos que se usan normalmente para descargar archivos mediante PowerShell.

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

### <a name="customize-result-columns-and-length"></a>Personalización de las columnas de resultado y la longitud 

Ahora que la consulta identifica claramente los datos que desea localizar, puede definir cómo se ven los resultados. `project` devuelve columnas específicas y `top` limita el número de resultados. Estos operadores ayudan a garantizar que los resultados tengan un formato correcto y sean razonablemente grandes y fáciles de procesar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Seleccione **Ejecutar consulta** para ver los resultados.

>[!TIP]
>Puede ver los resultados de la consulta como gráficos y ajustar rápidamente los filtros. Para obtener instrucciones, [lea sobre cómo trabajar con los resultados de la consulta](advanced-hunting-query-results.md).



## <a name="learn-common-query-operators"></a>Obtenga información sobre los operadores de consulta comunes

Acaba de ejecutar la primera consulta y tiene una idea general de sus componentes. Es el momento de retroceder ligeramente y aprender algunos conceptos básicos. El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.

| Operador | Descripción y uso |
|--|--|
| `where` | Filtra una tabla hasta llegar al subconjunto de filas que satisfacen un predicado. |
| `summarize` | Crea una tabla que agrega el contenido de la tabla de entrada. |
| `join` | Combina las filas de dos tablas para formar una nueva tabla mediante la coincidencia de los valores de la columna o columnas especificadas de cada tabla. Vea [Combinación de tablas en KQL](https://www.youtube.com/watch?v=8qZx7Pp5XgM) para obtener información sobre cómo hacerlo.|
| `count` | Devuelve el número de registros en el conjunto de registros de entrada. |
| `top` | Devuelve los primeros N registros ordenados según las columnas especificadas. |
| `limit` | Devuelve hasta el número de filas especificado. |
| `project` | Selecciona las columnas que desea incluir, cambia el nombre o elimina e inserta nuevas columnas calculadas. |
| `extend` | Crea columnas calculadas y las anexa al conjunto de resultados. |
| `makeset` |  Devuelve una matriz dinámica (JSON) del conjunto de valores distintivos que Expr toma en el grupo. |
| `find` | Busca las filas que coinciden con un predicado en un conjunto de tablas. |

Para ver un ejemplo dinámico de estos operadores, ejecútelos desde la sección **Comenzar** en la búsqueda avanzada.

## <a name="understand-data-types"></a>Comprender los tipos de datos

La búsqueda avanzada admite tipos de datos kusto, incluidos los siguientes tipos comunes:

| Tipo de datos | Descripción e implicaciones de la consulta |
|--|--|
| `datetime` | Información sobre datos y hora que representan las marcas de tiempo del evento [Consulte los formatos de fecha y hora admitidos](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Cadena de caracteres en UTF-8 entre comillas simples (`'`) o comillas dobles (`"`). [Obtenga más información sobre las cadenas.](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Este tipo de datos admite `true`or `false`states. [Consulte los literales y operadores admitidos](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | Entero de 32 bits  |
| `long` | Entero de 64 bits |

Para obtener más información sobre estos tipos de datos, [lea sobre los tipos de datos escalares de Kusto](/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Obtener ayuda mientras escribe consultas

Aprovéchese de las funciones siguientes para escribir consultas más rápido:
- **Autouggest**: a medida que escribe consultas, la búsqueda avanzada proporciona sugerencias de IntelliSense. 
- **Árbol de** esquema: se proporciona una representación de esquema que incluye la lista de tablas y sus columnas junto al área de trabajo. Para obtener más información, mueva el puntero sobre un elemento. Haga doble clic en un elemento para insertarlo en el editor de consultas.
- **[Referencia de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: referencia en el portal con descripciones de tabla y columna, así como tipos de eventos admitidos (`ActionType` valores) y consultas de ejemplo

## <a name="work-with-multiple-queries-in-the-editor"></a>Trabajar con varias consultas en el editor

Puede usar el editor de consultas para experimentar con varias consultas. Para usar varias consultas:

- Separe cada consulta con una línea vacía.
- Coloque el cursor en cualquier parte de una consulta para seleccionar esa consulta antes de ejecutarla. Esto solo ejecutará la consulta seleccionada. Para ejecutar otra consulta, mueva el cursor en consecuencia y seleccione **Ejecutar consulta**.

:::image type="content" source="../../media/multiple-queries.png" alt-text="Ejemplo de ejecución de varias consultas en la página **Nueva consulta** del portal de Microsoft 365 Defender" lightbox="../../media/multiple-queries.png":::

Para un área de trabajo más eficaz, también puede usar varias pestañas en la misma página de búsqueda. Seleccione **Nueva consulta** para abrir una pestaña para la nueva consulta.

:::image type="content" source="../../media/multitab.png" alt-text="Para abrir una nueva pestaña, seleccione Crear nuevo en búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="../../media/multitab.png":::

A continuación, puede ejecutar consultas diferentes sin abrir nunca una nueva pestaña del explorador. 

:::image type="content" source="../../media/multitab-examples.png" alt-text="Ejecutar consultas diferentes sin salir nunca de la página de búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="../../media/multitab-examples.png":::

>[!NOTE] 
> El uso de varias pestañas del explorador con búsqueda avanzada puede hacer que pierda las consultas no guardadas. Para evitar que esto suceda, use la característica de tabulación dentro de la búsqueda avanzada en lugar de pestañas de explorador independientes.

## <a name="use-sample-queries"></a>Usar las consultas de ejemplo

La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual. Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.

:::image type="content" source="../../media/get-started-section.png" alt-text="La sección **Introducción** de la página **Búsqueda avanzada** del portal de Microsoft 365 Defender" lightbox="../../media/get-started-section.png":::

>[!NOTE]
>Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas. Explore las consultas compartidas en el lado izquierdo de la página o en el [repositorio de consultas de GitHub](https://aka.ms/hunting-queries).

## <a name="access-query-language-documentation"></a>Acceso a documentación del lenguaje de consulta

Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](/azure/kusto/query/).

>[!NOTE]
>Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para punto de conexión. [Active Microsoft 365 Defender](m365d-enable.md) para buscar amenazas mediante más orígenes de datos. Para mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender, siga los pasos descritos en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) .

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)