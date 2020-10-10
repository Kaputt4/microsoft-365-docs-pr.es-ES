---
title: Conozca el lenguaje de consulta de la búsqueda avanzada de la Protección contra amenazas de Microsoft
description: Cree su primera consulta de búsqueda de amenazas y obtenga información sobre los operadores comunes y otros aspectos del lenguaje de consulta de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, idioma, información, primera consulta, telemetría, eventos, telemetría, detecciones personalizadas, esquema, kusto, operadores, tipos de datos, descarga de PowerShell, ejemplo de consulta
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
ms.openlocfilehash: ffa5e6abf7fb1cb0f93fe1c233ef7e3f0b023faf
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412627"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conozca el lenguaje de consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/). Puede usar la sintaxis y los operadores de Kusto para crear consultas que ubiquen información en un [esquema](advanced-hunting-schema-tables.md)especializado. Para entender mejor estos conceptos, ejecute la primera consulta.

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

**[Ejecutar esta consulta en la búsqueda avanzada](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Describir la consulta y especificar las tablas que se van a buscar
Se ha agregado un breve comentario al principio de la consulta para describir su significado. Este comentario ayuda si más adelante decide guardar la consulta y compartirla con otras personas de la organización. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Normalmente, la propia consulta comenzará con un nombre de tabla seguido de varios elementos que comienzan con una barra vertical ( `|` ). En este ejemplo, empezamos creando una Unión de dos tablas  `DeviceProcessEvents` y `DeviceNetworkEvents` , y agregamos elementos canalizados según sea necesario.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Establecer el intervalo de tiempo
El primer elemento canalizado es un filtro de tiempo cuyo ámbito es el de los siete días anteriores. Limitar el intervalo de tiempo contribuye a garantizar que las consultas funcionan bien, devuelven resultados manejables y no se agota el tiempo de espera.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Comprobar procesos específicos
El intervalo de tiempo va seguido inmediatamente de una búsqueda de nombres de archivo de proceso que representan la aplicación de PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Buscar cadenas de comandos específicas
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

### <a name="customize-result-columns-and-length"></a>Personalizar la longitud y las columnas de resultados 
Ahora que la consulta identifica claramente los datos que desea encontrar, puede definir el aspecto de los resultados. `project` Devuelve columnas específicas y `top` limita el número de resultados. Estos operadores ayudan a garantizar que los resultados tienen un formato adecuado y un tamaño razonable y sencillo de procesar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Seleccione **Ejecutar consulta** para ver los resultados. Use el icono de expandir en la parte superior derecha del editor de consultas para centrarse en la consulta de búsqueda y los resultados. 

![Imagen del control de expansión en el editor de consultas de caza avanzada](../../media/advanced-hunting-expand.png)

>[!TIP]
>Puede ver los resultados de la consulta en forma de gráficos y ajustar rápidamente los filtros. Para obtener instrucciones, [Vea información sobre cómo trabajar con los resultados de la consulta](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Obtener información sobre operadores de consulta comunes

Acaba de ejecutar la primera consulta y tener una idea general de sus componentes. Es el momento de hacer un poco de retroceso y aprender algunos conceptos básicos. El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.

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

## <a name="understand-data-types"></a>Descripción de los tipos de datos

La búsqueda avanzada admite tipos de datos de Kusto, incluidos los tipos comunes siguientes:

| Tipo de datos | Descripción e implicaciones de la consulta |
|--|--|
| `datetime` | La información de fecha y hora suele representar marcas de tiempo de evento. [Ver formatos de DateTime admitidos](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Cadena de caracteres en UTF-8 entre comillas simples ( `'` ) o comillas dobles ( `"` ). [Obtenga más información sobre las cadenas](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Este tipo de datos admite o está en `true` `false` Estado. [Ver literales y operadores admitidos](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | entero de 32 bits  |
| `long` | entero de 64 bits |

Para obtener más información sobre estos tipos de datos, [Lea acerca de los tipos de datos escalares Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Obtener ayuda mientras escribe consultas
Aprovéchese de las funciones siguientes para escribir consultas más rápido:
- **Autosugerir**: cuando se escriben consultas, la búsqueda avanzada ofrece sugerencias de IntelliSense. 
- **Árbol de esquema**: se proporciona una representación del esquema que incluye la lista de tablas y sus columnas junto a su área de trabajo. Para obtener más información, mueva el puntero sobre un elemento. Haga doble clic en un elemento para insertarlo en el editor de consultas.
- **[Referencia de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: referencia en el portal con las descripciones de las tablas y las columnas, así como los tipos de eventos admitidos ( `ActionType` valores) y las consultas de ejemplo

## <a name="work-with-multiple-queries-in-the-editor"></a>Trabajar con varias consultas en el editor
Puede usar el editor de consultas para experimentar con varias consultas. Para usar varias consultas:

- Separe cada consulta con una línea vacía.
- Situar el cursor en cualquier parte de una consulta para seleccionar esa consulta antes de ejecutarla. Se ejecutará sólo la consulta seleccionada. Para ejecutar otra consulta, mueva el cursor según corresponda y seleccione **Ejecutar consulta**.

![Imagen del editor de consultas con varias consultas](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Usar las consultas de ejemplo

La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual. Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.

![Imagen de la ventana de búsqueda avanzada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas. Explore las consultas compartidas en el lado izquierdo de la página o el [repositorio de consultas de github](https://aka.ms/hunting-queries).

## <a name="access-query-language-documentation"></a>Acceso a documentación del lenguaje de consulta

Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
