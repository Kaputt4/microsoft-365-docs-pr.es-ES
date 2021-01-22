---
title: Obtenga información sobre el lenguaje de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Cree su primera consulta de búsqueda de amenazas y obtenga información sobre los operadores comunes y otros aspectos del lenguaje de consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, idioma, aprender, primera consulta, telemetría, eventos, telemetría, detecciones personalizadas, esquema, kusto, operadores, tipos de datos, descarga de PowerShell, ejemplo de consulta
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
ms.openlocfilehash: 41341a2b5238485fc58021fe4af71cd5c635352c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929807"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="e0dc4-104">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e0dc4-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e0dc4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e0dc4-105">**Applies to:**</span></span>
- <span data-ttu-id="e0dc4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0dc4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e0dc4-107">La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="e0dc4-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="e0dc4-108">Puede usar instrucciones y operadores de Kusto para crear consultas que busquen información en un esquema [especializado.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="e0dc4-108">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="e0dc4-109">Para entender mejor estos conceptos, ejecute la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="e0dc4-110">Pruebe la primera consulta</span><span class="sxs-lookup"><span data-stu-id="e0dc4-110">Try your first query</span></span>

<span data-ttu-id="e0dc4-111">En el Centro de seguridad de Microsoft 365, vaya **a Búsqueda** para ejecutar la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="e0dc4-112">Utilice el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0dc4-112">Use the following example:</span></span>

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

<span data-ttu-id="e0dc4-113">**[Ejecutar esta consulta en la búsqueda avanzada](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="e0dc4-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="e0dc4-114">Describir la consulta y especificar las tablas en las que buscar</span><span class="sxs-lookup"><span data-stu-id="e0dc4-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="e0dc4-115">Se ha agregado un breve comentario al principio de la consulta para describir para qué es.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="e0dc4-116">Este comentario ayuda si más adelante decide guardar la consulta y compartirla con otras personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="e0dc4-117">La consulta en sí suele comenzar con un nombre de tabla seguido de varios elementos que comienzan con una canalización ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="e0dc4-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="e0dc4-118">En este ejemplo, empezamos creando una unión de dos tablas y agregando elementos  `DeviceProcessEvents` `DeviceNetworkEvents` canalizados según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="e0dc4-119">Establecer el intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="e0dc4-119">Set the time range</span></span>
<span data-ttu-id="e0dc4-120">El primer elemento canalado es un filtro de tiempo con ámbito de los siete días anteriores.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="e0dc4-121">Limitar el intervalo de tiempo ayuda a garantizar que las consultas tienen un buen rendimiento, devuelven resultados administrables y no se ha pasado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="e0dc4-122">Comprobar procesos específicos</span><span class="sxs-lookup"><span data-stu-id="e0dc4-122">Check specific processes</span></span>
<span data-ttu-id="e0dc4-123">El intervalo de tiempo va seguido inmediatamente de una búsqueda de nombres de archivo de proceso que representen la aplicación de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="e0dc4-124">Buscar cadenas de comandos específicas</span><span class="sxs-lookup"><span data-stu-id="e0dc4-124">Search for specific command strings</span></span>
<span data-ttu-id="e0dc4-125">Después, la consulta busca cadenas en las líneas de comandos que normalmente se usan para descargar archivos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="e0dc4-126">Personalizar las columnas de resultado y la longitud</span><span class="sxs-lookup"><span data-stu-id="e0dc4-126">Customize result columns and length</span></span> 
<span data-ttu-id="e0dc4-127">Ahora que la consulta identifica claramente los datos que desea localizar, puede definir el aspecto de los resultados.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="e0dc4-128">`project` devuelve columnas específicas y `top` limita el número de resultados.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="e0dc4-129">Estos operadores ayudan a garantizar que los resultados tienen un formato correcto y son razonablemente grandes y fáciles de procesar.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="e0dc4-130">Seleccione **Ejecutar consulta** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="e0dc4-131">Use el icono expandir situado en la parte superior derecha del editor de consultas para centrarse en la consulta de búsqueda y los resultados.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Imagen del control Expandir en el editor de consultas de búsqueda avanzada](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="e0dc4-133">Puede ver los resultados de la consulta como gráficos y ajustar rápidamente los filtros.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="e0dc4-134">Para obtener instrucciones, [obtenga información sobre cómo trabajar con los resultados de la consulta](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="e0dc4-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="e0dc4-135">Obtener información sobre operadores de consulta comunes</span><span class="sxs-lookup"><span data-stu-id="e0dc4-135">Learn common query operators</span></span>

<span data-ttu-id="e0dc4-136">Acaba de ejecutar la primera consulta y tiene una idea general de sus componentes.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="e0dc4-137">Es el momento de retroceder ligeramente y aprender algunos conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="e0dc4-138">El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="e0dc4-139">Operador</span><span class="sxs-lookup"><span data-stu-id="e0dc4-139">Operator</span></span> | <span data-ttu-id="e0dc4-140">Descripción y uso</span><span class="sxs-lookup"><span data-stu-id="e0dc4-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="e0dc4-141">Filtra una tabla hasta llegar al subconjunto de filas que satisfacen un predicado.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="e0dc4-142">Crea una tabla que agrega el contenido de la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="e0dc4-143">Combina las filas de dos tablas para formar una nueva tabla mediante la coincidencia de los valores de la columna o columnas especificadas de cada tabla.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="e0dc4-144">Devuelve el número de registros en el conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="e0dc4-145">Devuelve los primeros N registros ordenados según las columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="e0dc4-146">Devuelve hasta el número de filas especificado.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="e0dc4-147">Selecciona las columnas que desea incluir, cambia el nombre o elimina e inserta nuevas columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="e0dc4-148">Crea columnas calculadas y las anexa al conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="e0dc4-149">Devuelve una matriz dinámica (JSON) del conjunto de valores distintivos que Expr toma en el grupo.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="e0dc4-150">Busca las filas que coinciden con un predicado en un conjunto de tablas.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="e0dc4-151">Para ver un ejemplo dinámico de estos operadores, ejecútelos desde la sección **Comenzar** en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="e0dc4-152">Comprender los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="e0dc4-152">Understand data types</span></span>

<span data-ttu-id="e0dc4-153">La búsqueda avanzada admite tipos de datos kusto, incluidos los siguientes tipos comunes:</span><span class="sxs-lookup"><span data-stu-id="e0dc4-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="e0dc4-154">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e0dc4-154">Data type</span></span> | <span data-ttu-id="e0dc4-155">Descripción e implicaciones de la consulta</span><span class="sxs-lookup"><span data-stu-id="e0dc4-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="e0dc4-156">Información de datos y hora que suele representar las marcas de tiempo del evento.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="e0dc4-157">Ver formatos de fecha y hora admitidos</span><span class="sxs-lookup"><span data-stu-id="e0dc4-157">See supported datetime formats</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="e0dc4-158">Cadena de caracteres en UTF-8 entre comillas simples ( `'` ) o comillas dobles ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="e0dc4-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="e0dc4-159">Más información sobre las cadenas</span><span class="sxs-lookup"><span data-stu-id="e0dc4-159">Read more about strings</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="e0dc4-160">Este tipo de datos es compatible `true` o `false` estados.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="e0dc4-161">Ver los literales y operadores admitidos</span><span class="sxs-lookup"><span data-stu-id="e0dc4-161">See supported literals and operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="e0dc4-162">Entero de 32 bits</span><span class="sxs-lookup"><span data-stu-id="e0dc4-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="e0dc4-163">Entero de 64 bits</span><span class="sxs-lookup"><span data-stu-id="e0dc4-163">64-bit integer</span></span> |

<span data-ttu-id="e0dc4-164">Para obtener más información sobre estos tipos de datos, lea acerca de los tipos de datos [escalares de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span><span class="sxs-lookup"><span data-stu-id="e0dc4-164">To learn more about these data types, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="e0dc4-165">Obtener ayuda mientras escribe consultas</span><span class="sxs-lookup"><span data-stu-id="e0dc4-165">Get help as you write queries</span></span>
<span data-ttu-id="e0dc4-166">Aprovéchese de las funciones siguientes para escribir consultas más rápido:</span><span class="sxs-lookup"><span data-stu-id="e0dc4-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="e0dc4-167">**Autosuggest:** a medida que escribe consultas, la búsqueda avanzada proporciona sugerencias de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="e0dc4-168">**Árbol de esquema:** una representación de esquema que incluye la lista de tablas y sus columnas se proporciona junto al área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="e0dc4-169">Para obtener más información, mueva el puntero sobre un elemento.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-169">For more information, hover over an item.</span></span> <span data-ttu-id="e0dc4-170">Haga doble clic en un elemento para insertarlo en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="e0dc4-171">**[Referencia de esquema:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** referencia en el portal con descripciones de tabla y columna, así como tipos de eventos admitidos (valores) `ActionType` y consultas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0dc4-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="e0dc4-172">Trabajar con varias consultas en el editor</span><span class="sxs-lookup"><span data-stu-id="e0dc4-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="e0dc4-173">Puede usar el editor de consultas para experimentar con varias consultas.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="e0dc4-174">Para usar varias consultas:</span><span class="sxs-lookup"><span data-stu-id="e0dc4-174">To use multiple queries:</span></span>

- <span data-ttu-id="e0dc4-175">Separe cada consulta con una línea vacía.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="e0dc4-176">Coloque el cursor en cualquier parte de una consulta para seleccionarla antes de ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="e0dc4-177">Solo se ejecutará la consulta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-177">This will run only the selected query.</span></span> <span data-ttu-id="e0dc4-178">Para ejecutar otra consulta, mueva el cursor en consecuencia y seleccione **Ejecutar consulta.**</span><span class="sxs-lookup"><span data-stu-id="e0dc4-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Imagen del editor de consultas con varias consultas](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="e0dc4-180">Usar las consultas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0dc4-180">Use sample queries</span></span>

<span data-ttu-id="e0dc4-181">La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="e0dc4-182">Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-182">Try running these queries and making small modifications to them.</span></span>

![Imagen de la ventana de búsqueda avanzada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="e0dc4-184">Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas.</span><span class="sxs-lookup"><span data-stu-id="e0dc4-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="e0dc4-185">Explore las consultas compartidas en el lado izquierdo de la página o el repositorio de [consultas de GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="e0dc4-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="e0dc4-186">Acceso a documentación del lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="e0dc4-186">Access query language documentation</span></span>

<span data-ttu-id="e0dc4-187">Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="e0dc4-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0dc4-188">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e0dc4-188">Related topics</span></span>
- [<span data-ttu-id="e0dc4-189">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e0dc4-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e0dc4-190">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="e0dc4-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="e0dc4-191">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="e0dc4-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e0dc4-192">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="e0dc4-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e0dc4-193">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="e0dc4-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e0dc4-194">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="e0dc4-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
