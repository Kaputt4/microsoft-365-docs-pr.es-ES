---
title: Conozca el lenguaje de consulta de búsqueda avanzada
description: Cree su primera consulta de búsqueda de amenazas y obtenga información sobre los operadores comunes y otros aspectos del lenguaje de consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, idioma, aprendizaje, primera consulta, telemetría, eventos, telemetría, detecciones personalizadas, esquema, kusto, operadores, tipos de datos
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21cea1f661de294aea41ea2c4db21b1aca8a0eec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073163"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conozca el lenguaje de consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/). Puede usar operadores y instrucciones kusto para crear consultas que busquen información en un esquema [especializado.](advanced-hunting-schema-reference.md) Para entender mejor estos conceptos, ejecute la primera consulta.

## <a name="try-your-first-query"></a>Pruebe la primera consulta

En el Centro de seguridad de Microsoft Defender, vaya **a Búsqueda avanzada** para ejecutar la primera consulta. Utilice el ejemplo siguiente:

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
**[Ejecutar esta consulta en búsqueda avanzada](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**

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

![Imagen del control Expand en el editor de consultas de búsqueda avanzada](images/advanced-hunting-expand.png)

>[!TIP]
>Puede ver los resultados de la consulta como gráficos y ajustar rápidamente los filtros. Para obtener instrucciones, [lea sobre cómo trabajar con resultados de consulta](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Conozca más operadores comunes de consulta para la búsqueda avanzada

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

Para ver un ejemplo en directo de  estos operadores, ejecutarlos desde la sección Introducción de la página de búsqueda avanzada.

## <a name="understand-data-types"></a>Comprender tipos de datos

La búsqueda avanzada admite tipos de datos kusto, incluidos los siguientes tipos comunes:

| Tipo de datos | Descripción e implicaciones de la consulta |
|--|--|
| `datetime` | La información de datos y horas suele representar marcas de tiempo de eventos. [Ver formatos de fecha y hora admitidos](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Cadena de caracteres en UTF-8 entre comillas simples ( `'` ) o comillas dobles ( `"` ). [Más información sobre las cadenas](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Este tipo de datos admite `true` o `false` estados. [Ver literales y operadores admitidos](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | Entero de 32 bits  |
| `long` | Entero de 64 bits |

Para obtener más información sobre estos tipos de datos, lea acerca de los tipos de datos [escalares de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Obtener ayuda mientras escribe consultas
Aprovéchese de las funciones siguientes para escribir consultas más rápido:

- **Autosuggest:** al escribir consultas, la búsqueda avanzada proporciona sugerencias de IntelliSense.
- **Árbol de esquema:** una representación de esquema que incluye la lista de tablas y sus columnas se proporciona junto al área de trabajo. Para obtener más información, mueva el puntero sobre un elemento. Haga doble clic en un elemento para insertarlo en el editor de consultas.
- **[Referencia de esquema](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**: referencia en el portal con descripciones de tabla y columna, así como tipos de eventos admitidos ( `ActionType` valores) y consultas de ejemplo

## <a name="work-with-multiple-queries-in-the-editor"></a>Trabajar con varias consultas en el editor
Puede usar el editor de consultas para experimentar con varias consultas. Para usar varias consultas:

- Separe cada consulta con una línea vacía.
- Coloque el cursor en cualquier parte de una consulta para seleccionar esa consulta antes de ejecutarla. Solo se ejecutará la consulta seleccionada. Para ejecutar otra consulta, mueva el cursor en consecuencia y seleccione **Ejecutar consulta**.

![Imagen del editor de consultas de búsqueda avanzada con varias consultas Editor de ](images/ah-multi-query.png)
 _consultas con varias consultas_

## <a name="use-sample-queries"></a>Usar las consultas de ejemplo

La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual. Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.

![Imagen de la pestaña introducción a la búsqueda avanzada](images/atp-advanced-hunting.png)

> [!NOTE]
> Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas. Explore las consultas compartidas en el lado izquierdo de la página o el [repositorio de consultas de GitHub](https://aka.ms/hunting-queries).

## <a name="access-comprehensive-query-language-reference"></a>Referencia completa del lenguaje de consulta de acceso

Para obtener información detallada sobre el idioma de consulta, vea Documentación del idioma de [consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
