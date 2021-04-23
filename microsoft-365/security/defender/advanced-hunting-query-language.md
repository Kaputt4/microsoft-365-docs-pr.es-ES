---
title: Aprender el lenguaje avanzado de consulta de búsqueda en Microsoft 365 Defender
description: Cree su primera consulta de búsqueda de amenazas y obtenga información sobre los operadores comunes y otros aspectos del lenguaje de consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, idioma, aprender, primera consulta, telemetría, eventos, telemetría, detecciones personalizadas, esquema, kusto, operadores, tipos de datos, descarga de powershell, ejemplo de consulta
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
ms.openlocfilehash: 14287fb6dea9dda8accb580246b383f0427c3b3f
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952625"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="6b833-104">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="6b833-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6b833-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6b833-105">**Applies to:**</span></span>
- <span data-ttu-id="6b833-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b833-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6b833-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6b833-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="6b833-108">La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="6b833-108">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="6b833-109">Puede usar operadores y instrucciones kusto para crear consultas que busquen información en un esquema [especializado.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6b833-109">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="6b833-110">Para entender mejor estos conceptos, ejecute la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="6b833-110">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="6b833-111">Pruebe la primera consulta</span><span class="sxs-lookup"><span data-stu-id="6b833-111">Try your first query</span></span>

<span data-ttu-id="6b833-112">En el Centro de seguridad de Microsoft 365, vaya a **Hunting** para ejecutar la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="6b833-112">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="6b833-113">Utilice el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b833-113">Use the following example:</span></span>

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

<span data-ttu-id="6b833-114">**[Ejecutar esta consulta en búsqueda avanzada](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="6b833-114">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="6b833-115">Describir la consulta y especificar las tablas que se buscarán</span><span class="sxs-lookup"><span data-stu-id="6b833-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="6b833-116">Se ha agregado un breve comentario al principio de la consulta para describir para qué se trata.</span><span class="sxs-lookup"><span data-stu-id="6b833-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="6b833-117">Este comentario ayuda si más adelante decide guardar la consulta y compartirla con otros usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="6b833-117">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="6b833-118">La consulta en sí suele comenzar con un nombre de tabla seguido de varios elementos que comienzan con una canalización ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="6b833-118">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="6b833-119">En este ejemplo, empezamos creando una unión de dos tablas y  `DeviceProcessEvents` `DeviceNetworkEvents` , y agregamos elementos canalizados según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6b833-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="6b833-120">Establecer el intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="6b833-120">Set the time range</span></span>
<span data-ttu-id="6b833-121">El primer elemento canalado es un filtro de tiempo con el ámbito de los siete días anteriores.</span><span class="sxs-lookup"><span data-stu-id="6b833-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="6b833-122">Limitar el intervalo de tiempo ayuda a garantizar que las consultas tienen un buen rendimiento, que devuelven resultados manejables y que no hay tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6b833-122">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="6b833-123">Comprobar procesos específicos</span><span class="sxs-lookup"><span data-stu-id="6b833-123">Check specific processes</span></span>
<span data-ttu-id="6b833-124">Al intervalo de tiempo le sigue inmediatamente una búsqueda de nombres de archivo de proceso que representen la aplicación de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b833-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="6b833-125">Buscar cadenas de comandos específicas</span><span class="sxs-lookup"><span data-stu-id="6b833-125">Search for specific command strings</span></span>
<span data-ttu-id="6b833-126">Después, la consulta busca cadenas en líneas de comandos que normalmente se usan para descargar archivos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b833-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="6b833-127">Personalizar las columnas de resultados y la longitud</span><span class="sxs-lookup"><span data-stu-id="6b833-127">Customize result columns and length</span></span> 
<span data-ttu-id="6b833-128">Ahora que la consulta identifica claramente los datos que desea localizar, puede definir el aspecto de los resultados.</span><span class="sxs-lookup"><span data-stu-id="6b833-128">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="6b833-129">`project` devuelve columnas específicas y `top` limita el número de resultados.</span><span class="sxs-lookup"><span data-stu-id="6b833-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="6b833-130">Estos operadores ayudan a garantizar que los resultados estén bien formatados y sean razonablemente grandes y fáciles de procesar.</span><span class="sxs-lookup"><span data-stu-id="6b833-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="6b833-131">Seleccione **Ejecutar consulta** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="6b833-131">Select **Run query** to see the results.</span></span> <span data-ttu-id="6b833-132">Use el icono expandir situado en la parte superior derecha del editor de consultas para centrarse en la consulta de búsqueda y los resultados.</span><span class="sxs-lookup"><span data-stu-id="6b833-132">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Imagen del control Expand en el editor de consultas de búsqueda avanzada](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="6b833-134">Puede ver los resultados de la consulta como gráficos y ajustar rápidamente los filtros.</span><span class="sxs-lookup"><span data-stu-id="6b833-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="6b833-135">Para obtener instrucciones, [lea sobre cómo trabajar con resultados de consulta](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="6b833-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="6b833-136">Información sobre operadores de consulta comunes</span><span class="sxs-lookup"><span data-stu-id="6b833-136">Learn common query operators</span></span>

<span data-ttu-id="6b833-137">Acaba de ejecutar la primera consulta y tiene una idea general de sus componentes.</span><span class="sxs-lookup"><span data-stu-id="6b833-137">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="6b833-138">Es hora de retroceder ligeramente y aprender algunos conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="6b833-138">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="6b833-139">El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.</span><span class="sxs-lookup"><span data-stu-id="6b833-139">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="6b833-140">Operador</span><span class="sxs-lookup"><span data-stu-id="6b833-140">Operator</span></span> | <span data-ttu-id="6b833-141">Descripción y uso</span><span class="sxs-lookup"><span data-stu-id="6b833-141">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="6b833-142">Filtra una tabla hasta llegar al subconjunto de filas que satisfacen un predicado.</span><span class="sxs-lookup"><span data-stu-id="6b833-142">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="6b833-143">Crea una tabla que agrega el contenido de la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="6b833-143">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="6b833-144">Combina las filas de dos tablas para formar una nueva tabla mediante la coincidencia de los valores de la columna o columnas especificadas de cada tabla.</span><span class="sxs-lookup"><span data-stu-id="6b833-144">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="6b833-145">Devuelve el número de registros en el conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="6b833-145">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="6b833-146">Devuelve los primeros N registros ordenados según las columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="6b833-146">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="6b833-147">Devuelve hasta el número de filas especificado.</span><span class="sxs-lookup"><span data-stu-id="6b833-147">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="6b833-148">Selecciona las columnas que desea incluir, cambia el nombre o elimina e inserta nuevas columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="6b833-148">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="6b833-149">Crea columnas calculadas y las anexa al conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="6b833-149">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="6b833-150">Devuelve una matriz dinámica (JSON) del conjunto de valores distintivos que Expr toma en el grupo.</span><span class="sxs-lookup"><span data-stu-id="6b833-150">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="6b833-151">Busca las filas que coinciden con un predicado en un conjunto de tablas.</span><span class="sxs-lookup"><span data-stu-id="6b833-151">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="6b833-152">Para ver un ejemplo dinámico de estos operadores, ejecútelos desde la sección **Comenzar** en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="6b833-152">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="6b833-153">Comprender tipos de datos</span><span class="sxs-lookup"><span data-stu-id="6b833-153">Understand data types</span></span>

<span data-ttu-id="6b833-154">La búsqueda avanzada admite tipos de datos kusto, incluidos los siguientes tipos comunes:</span><span class="sxs-lookup"><span data-stu-id="6b833-154">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="6b833-155">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6b833-155">Data type</span></span> | <span data-ttu-id="6b833-156">Descripción e implicaciones de la consulta</span><span class="sxs-lookup"><span data-stu-id="6b833-156">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="6b833-157">La información de datos y horas suele representar marcas de tiempo de eventos.</span><span class="sxs-lookup"><span data-stu-id="6b833-157">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="6b833-158">Ver formatos de fecha y hora admitidos</span><span class="sxs-lookup"><span data-stu-id="6b833-158">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="6b833-159">Cadena de caracteres en UTF-8 entre comillas simples ( `'` ) o comillas dobles ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="6b833-159">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="6b833-160">Más información sobre las cadenas</span><span class="sxs-lookup"><span data-stu-id="6b833-160">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="6b833-161">Este tipo de datos admite `true` o `false` estados.</span><span class="sxs-lookup"><span data-stu-id="6b833-161">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="6b833-162">Ver literales y operadores admitidos</span><span class="sxs-lookup"><span data-stu-id="6b833-162">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="6b833-163">Entero de 32 bits</span><span class="sxs-lookup"><span data-stu-id="6b833-163">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="6b833-164">Entero de 64 bits</span><span class="sxs-lookup"><span data-stu-id="6b833-164">64-bit integer</span></span> |

<span data-ttu-id="6b833-165">Para obtener más información sobre estos tipos de datos, lea acerca de los tipos de datos [escalares de Kusto](/azure/data-explorer/kusto/query/scalar-data-types/).</span><span class="sxs-lookup"><span data-stu-id="6b833-165">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="6b833-166">Obtener ayuda mientras escribe consultas</span><span class="sxs-lookup"><span data-stu-id="6b833-166">Get help as you write queries</span></span>
<span data-ttu-id="6b833-167">Aprovéchese de las funciones siguientes para escribir consultas más rápido:</span><span class="sxs-lookup"><span data-stu-id="6b833-167">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="6b833-168">**Autosuggest:** al escribir consultas, la búsqueda avanzada proporciona sugerencias de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="6b833-168">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="6b833-169">**Árbol de esquema:** una representación de esquema que incluye la lista de tablas y sus columnas se proporciona junto al área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6b833-169">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="6b833-170">Para obtener más información, mueva el puntero sobre un elemento.</span><span class="sxs-lookup"><span data-stu-id="6b833-170">For more information, hover over an item.</span></span> <span data-ttu-id="6b833-171">Haga doble clic en un elemento para insertarlo en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="6b833-171">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="6b833-172">**[Referencia de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: referencia en el portal con descripciones de tabla y columna, así como tipos de eventos admitidos ( `ActionType` valores) y consultas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b833-172">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="6b833-173">Trabajar con varias consultas en el editor</span><span class="sxs-lookup"><span data-stu-id="6b833-173">Work with multiple queries in the editor</span></span>
<span data-ttu-id="6b833-174">Puede usar el editor de consultas para experimentar con varias consultas.</span><span class="sxs-lookup"><span data-stu-id="6b833-174">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="6b833-175">Para usar varias consultas:</span><span class="sxs-lookup"><span data-stu-id="6b833-175">To use multiple queries:</span></span>

- <span data-ttu-id="6b833-176">Separe cada consulta con una línea vacía.</span><span class="sxs-lookup"><span data-stu-id="6b833-176">Separate each query with an empty line.</span></span>
- <span data-ttu-id="6b833-177">Coloque el cursor en cualquier parte de una consulta para seleccionar esa consulta antes de ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="6b833-177">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="6b833-178">Solo se ejecutará la consulta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6b833-178">This will run only the selected query.</span></span> <span data-ttu-id="6b833-179">Para ejecutar otra consulta, mueva el cursor en consecuencia y seleccione **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="6b833-179">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Imagen del editor de consultas con varias consultas](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="6b833-181">Usar las consultas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b833-181">Use sample queries</span></span>

<span data-ttu-id="6b833-182">La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual.</span><span class="sxs-lookup"><span data-stu-id="6b833-182">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="6b833-183">Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.</span><span class="sxs-lookup"><span data-stu-id="6b833-183">Try running these queries and making small modifications to them.</span></span>

![Imagen de la ventana de búsqueda avanzada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="6b833-185">Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas.</span><span class="sxs-lookup"><span data-stu-id="6b833-185">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="6b833-186">Explore las consultas compartidas en el lado izquierdo de la página o el [repositorio de consultas de GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="6b833-186">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="6b833-187">Acceso a documentación del lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="6b833-187">Access query language documentation</span></span>

<span data-ttu-id="6b833-188">Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="6b833-188">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

>[!NOTE]
><span data-ttu-id="6b833-189">Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="6b833-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6b833-190">[Activa Microsoft 365 Defender para](m365d-enable.md) buscar amenazas con más orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="6b833-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="6b833-191">Puede mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para endpoint a Microsoft 365 Defender siguiendo los pasos descritos en Migrar consultas avanzadas de búsqueda desde [Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md).</span><span class="sxs-lookup"><span data-stu-id="6b833-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b833-192">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6b833-192">Related topics</span></span>
- [<span data-ttu-id="6b833-193">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="6b833-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6b833-194">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="6b833-194">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="6b833-195">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="6b833-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6b833-196">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="6b833-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6b833-197">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="6b833-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6b833-198">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="6b833-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)