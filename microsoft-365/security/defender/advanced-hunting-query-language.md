---
title: Aprender el lenguaje avanzado de consulta de búsqueda en Microsoft 365 Defender
description: Cree su primera consulta de búsqueda de amenazas y obtenga información sobre los operadores comunes y otros aspectos del lenguaje de consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, idioma, aprendizaje, primera consulta, telemetría, eventos, telemetría, detecciones personalizadas, esquema, kusto, operadores, tipos de datos, descarga de powershell, ejemplo de consulta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b22badcb9c099679e3d785e407f83d2121a84901
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500365"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conozca el lenguaje de consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](/azure/kusto/query/). Puede usar operadores y instrucciones kusto para crear consultas que busquen información en un esquema [especializado.](advanced-hunting-schema-tables.md) Para entender mejor estos conceptos, ejecute la primera consulta.

## <a name="try-your-first-query"></a>Pruebe la primera consulta

En el Centro de seguridad de Microsoft 365, vaya a **Hunting** para ejecutar la primera consulta. Utilice el ejemplo siguiente:

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

**[Ejecutar esta consulta en búsqueda avanzada](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Describir la consulta y especificar las tablas que se buscarán
Se ha agregado un breve comentario al principio de la consulta para describir para qué se trata. Este comentario ayuda si más adelante decide guardar la consulta y compartirla con otros usuarios de la organización. 

```kusto
// Finds PowerShell execution events that could involve a download
```

La consulta en sí suele comenzar con un nombre de tabla seguido de varios elementos que comienzan con una canalización ( `|` ). En este ejemplo, empezamos creando una unión de dos tablas y  `DeviceProcessEvents` `DeviceNetworkEvents` , y agregamos elementos canalizados según sea necesario.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Establecer el intervalo de tiempo
El primer elemento canalado es un filtro de tiempo con el ámbito de los siete días anteriores. Limitar el intervalo de tiempo ayuda a garantizar que las consultas tienen un buen rendimiento, que devuelven resultados manejables y que no hay tiempo de espera.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Comprobar procesos específicos
Al intervalo de tiempo le sigue inmediatamente una búsqueda de nombres de archivo de proceso que representen la aplicación de PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Buscar cadenas de comandos específicas
Después, la consulta busca cadenas en líneas de comandos que normalmente se usan para descargar archivos con PowerShell.

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

### <a name="customize-result-columns-and-length"></a>Personalizar las columnas de resultados y la longitud 
Ahora que la consulta identifica claramente los datos que desea localizar, puede definir el aspecto de los resultados. `project` devuelve columnas específicas y `top` limita el número de resultados. Estos operadores ayudan a garantizar que los resultados estén bien formatados y sean razonablemente grandes y fáciles de procesar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Seleccione **Ejecutar consulta** para ver los resultados. Use el icono expandir situado en la parte superior derecha del editor de consultas para centrarse en la consulta de búsqueda y los resultados. 

![Imagen del control Expand en el editor de consultas de búsqueda avanzada](../../media/advanced-hunting-expand.png)

>[!TIP]
>Puede ver los resultados de la consulta como gráficos y ajustar rápidamente los filtros. Para obtener instrucciones, [lea sobre cómo trabajar con resultados de consulta](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Información sobre operadores de consulta comunes

Acaba de ejecutar la primera consulta y tiene una idea general de sus componentes. Es hora de retroceder ligeramente y aprender algunos conceptos básicos. El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.

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

## <a name="understand-data-types"></a>Comprender tipos de datos

La búsqueda avanzada admite tipos de datos kusto, incluidos los siguientes tipos comunes:

| Tipo de datos | Descripción e implicaciones de la consulta |
|--|--|
| `datetime` | La información de datos y horas suele representar marcas de tiempo de eventos. [Ver formatos de fecha y hora admitidos](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Cadena de caracteres en UTF-8 entre comillas simples ( `'` ) o comillas dobles ( `"` ). [Más información sobre las cadenas](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Este tipo de datos admite `true` o `false` estados. [Ver literales y operadores admitidos](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | Entero de 32 bits  |
| `long` | Entero de 64 bits |

Para obtener más información sobre estos tipos de datos, lea acerca de los tipos de datos [escalares de Kusto](/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Obtener ayuda mientras escribe consultas
Aprovéchese de las funciones siguientes para escribir consultas más rápido:
- **Autosuggest:** al escribir consultas, la búsqueda avanzada proporciona sugerencias de IntelliSense. 
- **Árbol de esquema:** una representación de esquema que incluye la lista de tablas y sus columnas se proporciona junto al área de trabajo. Para obtener más información, mueva el puntero sobre un elemento. Haga doble clic en un elemento para insertarlo en el editor de consultas.
- **[Referencia de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: referencia en el portal con descripciones de tabla y columna, así como tipos de eventos admitidos ( `ActionType` valores) y consultas de ejemplo

## <a name="work-with-multiple-queries-in-the-editor"></a>Trabajar con varias consultas en el editor
Puede usar el editor de consultas para experimentar con varias consultas. Para usar varias consultas:

- Separe cada consulta con una línea vacía.
- Coloque el cursor en cualquier parte de una consulta para seleccionar esa consulta antes de ejecutarla. Solo se ejecutará la consulta seleccionada. Para ejecutar otra consulta, mueva el cursor en consecuencia y seleccione **Ejecutar consulta**.

![Imagen del editor de consultas con varias consultas](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Usar las consultas de ejemplo

La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual. Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.

![Imagen de la ventana de búsqueda avanzada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas. Explore las consultas compartidas en el lado izquierdo de la página o el [repositorio de consultas de GitHub](https://aka.ms/hunting-queries).

## <a name="access-query-language-documentation"></a>Acceso a documentación del lenguaje de consulta

Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](/azure/kusto/query/).

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)