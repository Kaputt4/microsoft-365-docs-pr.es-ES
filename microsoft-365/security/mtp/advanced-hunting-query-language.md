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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 26b376fe3e804a3ebaa478e484807bea4c33d38b
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049705"
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

![Imagen de la consulta de búsqueda avanzada de Microsoft Threat Protection](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Describir la consulta y especificar las tablas que se van a buscar
Se ha agregado un breve comentario al principio de la consulta para describir su significado. Esto le ayudará si más adelante decide guardar la consulta y compartirla con otras personas de la organización. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Generalmente, la consulta comienza con un nombre de tabla seguido de una serie de elementos precedidos por un operador de canalización (`|`). En este ejemplo, empezamos creando una Unión de dos tablas `DeviceProcessEvents` y `DeviceNetworkEvents` , y agregamos elementos canalizados según sea necesario.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Establecer el intervalo de tiempo
El primer elemento canalizado es un filtro de tiempo cuyo ámbito es el de los siete días anteriores. Un intervalo de tiempo tan reducido como sea posible garantiza que las consultas funcionen bien, devuelvan resultados que se puedan administrar y no se agote el tiempo de espera.

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
Ahora que la consulta identifica claramente los datos que desea localizar, agregue elementos que definen cómo son los resultados. `project`Devuelve columnas específicas y `top` limita el número de resultados. Estos operadores ayudan a garantizar que los resultados tienen un formato adecuado y un tamaño razonable y sencillo de procesar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Haga clic en **Ejecutar consulta** para ver los resultados. Seleccione el icono de expandir en la parte superior derecha del editor de consultas para centrarse en la consulta de búsqueda y los resultados. 

![Imagen del control de expansión en el editor de consultas de caza avanzada](../../media/advanced-hunting-expand.png)

>[!TIP]
>Puede ver los resultados de la consulta en forma de gráficos y ajustar rápidamente los filtros. Para obtener instrucciones, [Vea información sobre cómo trabajar con los resultados de la consulta](advanced-hunting-query-results.md)

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

## <a name="get-help-as-you-write-queries"></a>Obtener ayuda mientras escribe consultas
Aprovéchese de las funciones siguientes para escribir consultas más rápido:
- **Autosugerir** : cuando se escriben consultas, la búsqueda avanzada ofrece sugerencias de IntelliSense. 
- **Árbol de esquema** : se proporciona una representación del esquema que incluye la lista de tablas y sus columnas junto a su área de trabajo. Para obtener más información, mueva el puntero sobre un elemento. Haga doble clic en un elemento para insertarlo en el editor de consultas.
- **[Referencia de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : referencia en el portal con las descripciones de las tablas y las columnas, así como los tipos de eventos admitidos ( `ActionType` valores) y las consultas de ejemplo

## <a name="work-with-multiple-queries-in-the-editor"></a>Trabajar con varias consultas en el editor
El editor de consultas puede servir como un bloc de notas para experimentar con varias consultas. Para usar varias consultas:

- Separe cada consulta con una línea vacía.
- Situar el cursor en cualquier parte de una consulta para seleccionar esa consulta antes de ejecutarla. Se ejecutará sólo la consulta seleccionada. Para ejecutar otra consulta, mueva el cursor según corresponda y seleccione **Ejecutar consulta**.

![Imagen del editor de consultas con varias consultas](../../media/mtp-ah/ah-multi-query.png)

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
