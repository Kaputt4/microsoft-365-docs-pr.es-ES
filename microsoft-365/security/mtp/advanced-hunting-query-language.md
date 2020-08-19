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
ms.openlocfilehash: 15e298edfad2d04079322a070615a36bb5df64ad
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797857"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="3d488-104">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3d488-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="3d488-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3d488-105">**Applies to:**</span></span>
- <span data-ttu-id="3d488-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d488-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3d488-107">La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="3d488-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="3d488-108">Puede usar la sintaxis y los operadores Kusto para crear consultas que buscan información en el [esquema](advanced-hunting-schema-tables.md) específicamente estructurado para la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="3d488-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="3d488-109">Para entender mejor estos conceptos, ejecute la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="3d488-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="3d488-110">Pruebe la primera consulta</span><span class="sxs-lookup"><span data-stu-id="3d488-110">Try your first query</span></span>

<span data-ttu-id="3d488-111">En el centro de seguridad de Microsoft 365, vaya a **búsqueda** para ejecutar la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="3d488-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="3d488-112">Utilice el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d488-112">Use the following example:</span></span>

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

<span data-ttu-id="3d488-113">Así se verá en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="3d488-113">This is how it will look like in advanced hunting.</span></span>

![Imagen de la consulta de búsqueda avanzada de Microsoft Threat Protection](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="3d488-115">Describir la consulta y especificar las tablas que se van a buscar</span><span class="sxs-lookup"><span data-stu-id="3d488-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="3d488-116">Se ha agregado un breve comentario al principio de la consulta para describir su significado.</span><span class="sxs-lookup"><span data-stu-id="3d488-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="3d488-117">Esto le ayudará si más adelante decide guardar la consulta y compartirla con otras personas de la organización.</span><span class="sxs-lookup"><span data-stu-id="3d488-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="3d488-118">Generalmente, la consulta comienza con un nombre de tabla seguido de una serie de elementos precedidos por un operador de canalización (`|`).</span><span class="sxs-lookup"><span data-stu-id="3d488-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="3d488-119">En este ejemplo, empezamos creando una Unión de dos tablas  `DeviceProcessEvents` y `DeviceNetworkEvents` , y agregamos elementos canalizados según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3d488-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="3d488-120">Establecer el intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="3d488-120">Set the time range</span></span>
<span data-ttu-id="3d488-121">El primer elemento canalizado es un filtro de tiempo cuyo ámbito es el de los siete días anteriores.</span><span class="sxs-lookup"><span data-stu-id="3d488-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="3d488-122">Un intervalo de tiempo tan reducido como sea posible garantiza que las consultas funcionen bien, devuelvan resultados que se puedan administrar y no se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3d488-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="3d488-123">Comprobar procesos específicos</span><span class="sxs-lookup"><span data-stu-id="3d488-123">Check specific processes</span></span>
<span data-ttu-id="3d488-124">El intervalo de tiempo va seguido inmediatamente de una búsqueda de nombres de archivo de proceso que representan la aplicación de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d488-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="3d488-125">Buscar cadenas de comandos específicas</span><span class="sxs-lookup"><span data-stu-id="3d488-125">Search for specific command strings</span></span>
<span data-ttu-id="3d488-126">Después, la consulta busca cadenas en las líneas de comandos que se suelen usar para descargar archivos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d488-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="3d488-127">Personalizar la longitud y las columnas de resultados</span><span class="sxs-lookup"><span data-stu-id="3d488-127">Customize result columns and length</span></span> 
<span data-ttu-id="3d488-128">Ahora que la consulta identifica claramente los datos que desea localizar, agregue elementos que definen cómo son los resultados.</span><span class="sxs-lookup"><span data-stu-id="3d488-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="3d488-129">`project` Devuelve columnas específicas y `top` limita el número de resultados.</span><span class="sxs-lookup"><span data-stu-id="3d488-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="3d488-130">Estos operadores ayudan a garantizar que los resultados tienen un formato adecuado y un tamaño razonable y sencillo de procesar.</span><span class="sxs-lookup"><span data-stu-id="3d488-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="3d488-131">Haga clic en **Ejecutar consulta** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="3d488-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="3d488-132">Seleccione el icono de expandir en la parte superior derecha del editor de consultas para centrarse en la consulta de búsqueda y los resultados.</span><span class="sxs-lookup"><span data-stu-id="3d488-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Imagen del control de expansión en el editor de consultas de caza avanzada](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="3d488-134">Puede ver los resultados de la consulta en forma de gráficos y ajustar rápidamente los filtros.</span><span class="sxs-lookup"><span data-stu-id="3d488-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="3d488-135">Para obtener instrucciones, [Vea información sobre cómo trabajar con los resultados de la consulta](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="3d488-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="3d488-136">Obtener información sobre operadores de consulta comunes</span><span class="sxs-lookup"><span data-stu-id="3d488-136">Learn common query operators</span></span>

<span data-ttu-id="3d488-137">Ahora que ha ejecutado la primera consulta y tiene una idea general de los componentes, es hora de retroceder un poco y aprender más sobre los aspectos básicos.</span><span class="sxs-lookup"><span data-stu-id="3d488-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="3d488-138">El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.</span><span class="sxs-lookup"><span data-stu-id="3d488-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="3d488-139">Operador</span><span class="sxs-lookup"><span data-stu-id="3d488-139">Operator</span></span> | <span data-ttu-id="3d488-140">Descripción y uso</span><span class="sxs-lookup"><span data-stu-id="3d488-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="3d488-141">Filtra una tabla hasta llegar al subconjunto de filas que satisfacen un predicado.</span><span class="sxs-lookup"><span data-stu-id="3d488-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="3d488-142">Crea una tabla que agrega el contenido de la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="3d488-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="3d488-143">Combina las filas de dos tablas para formar una nueva tabla mediante la coincidencia de los valores de la columna o columnas especificadas de cada tabla.</span><span class="sxs-lookup"><span data-stu-id="3d488-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="3d488-144">Devuelve el número de registros en el conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="3d488-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="3d488-145">Devuelve los primeros N registros ordenados según las columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="3d488-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="3d488-146">Devuelve hasta el número de filas especificado.</span><span class="sxs-lookup"><span data-stu-id="3d488-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="3d488-147">Selecciona las columnas que desea incluir, cambia el nombre o elimina e inserta nuevas columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="3d488-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="3d488-148">Crea columnas calculadas y las anexa al conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="3d488-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="3d488-149">Devuelve una matriz dinámica (JSON) del conjunto de valores distintivos que Expr toma en el grupo.</span><span class="sxs-lookup"><span data-stu-id="3d488-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="3d488-150">Busca las filas que coinciden con un predicado en un conjunto de tablas.</span><span class="sxs-lookup"><span data-stu-id="3d488-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="3d488-151">Para ver un ejemplo dinámico de estos operadores, ejecútelos desde la sección **Comenzar** en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="3d488-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="3d488-152">Descripción de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="3d488-152">Understand data types</span></span>

<span data-ttu-id="3d488-153">Los datos de las tablas de búsqueda avanzada se clasifican generalmente en los siguientes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="3d488-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="3d488-154">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="3d488-154">Data type</span></span> | <span data-ttu-id="3d488-155">Descripción e implicaciones de la consulta</span><span class="sxs-lookup"><span data-stu-id="3d488-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="3d488-156">Información sobre datos y hora que representan las marcas de tiempo del evento</span><span class="sxs-lookup"><span data-stu-id="3d488-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="3d488-157">Cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="3d488-157">Character string</span></span> |
| `bool` | <span data-ttu-id="3d488-158">Verdadero o falso</span><span class="sxs-lookup"><span data-stu-id="3d488-158">True or false</span></span> |
| `int` | <span data-ttu-id="3d488-159">Valor numérico de 32 bits</span><span class="sxs-lookup"><span data-stu-id="3d488-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="3d488-160">Valor numérico de 64 bits</span><span class="sxs-lookup"><span data-stu-id="3d488-160">64-bit numeric value</span></span> |

<span data-ttu-id="3d488-161">Para obtener más información sobre estos tipos de datos y sus implicaciones, [Lea acerca de los tipos de datos Scalar Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span><span class="sxs-lookup"><span data-stu-id="3d488-161">To learn more about these data types and their implications, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="3d488-162">Obtener ayuda mientras escribe consultas</span><span class="sxs-lookup"><span data-stu-id="3d488-162">Get help as you write queries</span></span>
<span data-ttu-id="3d488-163">Aprovéchese de las funciones siguientes para escribir consultas más rápido:</span><span class="sxs-lookup"><span data-stu-id="3d488-163">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="3d488-164">**Autosugerir** : cuando se escriben consultas, la búsqueda avanzada ofrece sugerencias de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="3d488-164">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="3d488-165">**Árbol de esquema** : se proporciona una representación del esquema que incluye la lista de tablas y sus columnas junto a su área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3d488-165">**Schema tree** — a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="3d488-166">Para obtener más información, mueva el puntero sobre un elemento.</span><span class="sxs-lookup"><span data-stu-id="3d488-166">For more information, hover over an item.</span></span> <span data-ttu-id="3d488-167">Haga doble clic en un elemento para insertarlo en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="3d488-167">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="3d488-168">**[Referencia de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : referencia en el portal con las descripciones de las tablas y las columnas, así como los tipos de eventos admitidos ( `ActionType` valores) y las consultas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d488-168">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="3d488-169">Trabajar con varias consultas en el editor</span><span class="sxs-lookup"><span data-stu-id="3d488-169">Work with multiple queries in the editor</span></span>
<span data-ttu-id="3d488-170">El editor de consultas puede servir como un bloc de notas para experimentar con varias consultas.</span><span class="sxs-lookup"><span data-stu-id="3d488-170">The query editor can serve as your scratch pad for experimenting with multiple queries.</span></span> <span data-ttu-id="3d488-171">Para usar varias consultas:</span><span class="sxs-lookup"><span data-stu-id="3d488-171">To use multiple queries:</span></span>

- <span data-ttu-id="3d488-172">Separe cada consulta con una línea vacía.</span><span class="sxs-lookup"><span data-stu-id="3d488-172">Separate each query with an empty line.</span></span>
- <span data-ttu-id="3d488-173">Situar el cursor en cualquier parte de una consulta para seleccionar esa consulta antes de ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="3d488-173">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="3d488-174">Se ejecutará sólo la consulta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3d488-174">This will run only the selected query.</span></span> <span data-ttu-id="3d488-175">Para ejecutar otra consulta, mueva el cursor según corresponda y seleccione **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="3d488-175">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Imagen del editor de consultas con varias consultas](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="3d488-177">Usar las consultas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d488-177">Use sample queries</span></span>

<span data-ttu-id="3d488-178">La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual.</span><span class="sxs-lookup"><span data-stu-id="3d488-178">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="3d488-179">Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.</span><span class="sxs-lookup"><span data-stu-id="3d488-179">Try running these queries and making small modifications to them.</span></span>

![Imagen de la ventana de búsqueda avanzada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="3d488-181">Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas.</span><span class="sxs-lookup"><span data-stu-id="3d488-181">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="3d488-182">Explore las consultas compartidas en la parte izquierda de la página o en el repositorio de consultas de GitHub.</span><span class="sxs-lookup"><span data-stu-id="3d488-182">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="3d488-183">Acceso a documentación del lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="3d488-183">Access query language documentation</span></span>

<span data-ttu-id="3d488-184">Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="3d488-184">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d488-185">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3d488-185">Related topics</span></span>
- [<span data-ttu-id="3d488-186">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3d488-186">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3d488-187">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="3d488-187">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3d488-188">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="3d488-188">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3d488-189">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="3d488-189">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3d488-190">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="3d488-190">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3d488-191">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="3d488-191">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
