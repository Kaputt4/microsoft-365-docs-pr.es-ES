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
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="3e7b7-104">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3e7b7-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="3e7b7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3e7b7-105">**Applies to:**</span></span>
- <span data-ttu-id="3e7b7-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e7b7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3e7b7-107">La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="3e7b7-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="3e7b7-108">Puede usar la sintaxis y los operadores Kusto para crear consultas que buscan información en el [esquema](advanced-hunting-schema-tables.md) específicamente estructurado para la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="3e7b7-109">Para entender mejor estos conceptos, ejecute la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="3e7b7-110">Pruebe la primera consulta</span><span class="sxs-lookup"><span data-stu-id="3e7b7-110">Try your first query</span></span>

<span data-ttu-id="3e7b7-111">En el centro de seguridad de Microsoft 365, vaya a **búsqueda** para ejecutar la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="3e7b7-112">Utilice el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e7b7-112">Use the following example:</span></span>

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

<span data-ttu-id="3e7b7-113">Así se verá en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-113">This is how it will look like in advanced hunting.</span></span>

![Imagen de la consulta de búsqueda avanzada de Microsoft Threat Protection](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="3e7b7-115">Se ha agregado un breve comentario al principio de la consulta para describir su significado.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="3e7b7-116">Esto le ayudará si más adelante decide guardar la consulta y compartirla con otras personas de la organización.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-116">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="3e7b7-117">Generalmente, la consulta comienza con un nombre de tabla seguido de una serie de elementos precedidos por un operador de canalización (`|`).</span><span class="sxs-lookup"><span data-stu-id="3e7b7-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="3e7b7-118">En este ejemplo, empezamos creando una Unión de dos tablas `DeviceProcessEvents` y `DeviceNetworkEvents`, y agregamos elementos canalizados según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
<span data-ttu-id="3e7b7-119">El primer elemento canalizado es un filtro de tiempo cuyo ámbito es el de los siete días anteriores.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-119">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="3e7b7-120">Un intervalo de tiempo tan reducido como sea posible garantiza que las consultas funcionen bien, devuelvan resultados que se puedan administrar y no se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="3e7b7-121">El intervalo de tiempo va seguido inmediatamente de una búsqueda de nombres de archivo de proceso que representan la aplicación de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-121">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

<span data-ttu-id="3e7b7-122">Después, la consulta busca cadenas en las líneas de comandos que se suelen usar para descargar archivos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-122">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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
<span data-ttu-id="3e7b7-123">Ahora que la consulta identifica claramente los datos que desea localizar, agregue elementos que definen cómo son los resultados.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="3e7b7-124">`project`Devuelve columnas específicas y `top` limita el número de resultados, lo que ayuda a garantizar que los resultados tengan un formato muy grande y razonable y fácil de procesar.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-124">`project` returns specific columns and `top` limits the number of results, helping ensure the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="3e7b7-125">Haga clic en **Ejecutar consulta** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="3e7b7-126">Seleccione el icono de expandir en la parte superior derecha del editor de consultas para centrarse en la consulta de búsqueda y los resultados.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-126">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span>

![Imagen del control de expansión en el editor de consultas de caza avanzada](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="3e7b7-128">Conozca más operadores comunes de consulta para la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3e7b7-128">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="3e7b7-129">Ahora que ha ejecutado la primera consulta y tiene una idea general de los componentes, es hora de retroceder un poco y aprender más sobre los aspectos básicos.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-129">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="3e7b7-130">El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-130">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="3e7b7-131">Operador</span><span class="sxs-lookup"><span data-stu-id="3e7b7-131">Operator</span></span> | <span data-ttu-id="3e7b7-132">Descripción y uso</span><span class="sxs-lookup"><span data-stu-id="3e7b7-132">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="3e7b7-133">Filtra una tabla hasta llegar al subconjunto de filas que satisfacen un predicado.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-133">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="3e7b7-134">Crea una tabla que agrega el contenido de la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-134">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="3e7b7-135">Combina las filas de dos tablas para formar una nueva tabla mediante la coincidencia de los valores de la columna o columnas especificadas de cada tabla.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-135">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="3e7b7-136">Devuelve el número de registros en el conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-136">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="3e7b7-137">Devuelve los primeros N registros ordenados según las columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-137">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="3e7b7-138">Devuelve hasta el número de filas especificado.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-138">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="3e7b7-139">Selecciona las columnas que desea incluir, cambia el nombre o elimina e inserta nuevas columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-139">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="3e7b7-140">Crea columnas calculadas y las anexa al conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-140">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="3e7b7-141">Devuelve una matriz dinámica (JSON) del conjunto de valores distintivos que Expr toma en el grupo.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-141">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="3e7b7-142">Busca las filas que coinciden con un predicado en un conjunto de tablas.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-142">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="3e7b7-143">Para ver un ejemplo dinámico de estos operadores, ejecútelos desde la sección **Comenzar** en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-143">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="3e7b7-144">Los tipos de datos y sus implicaciones de sintaxis de consulta</span><span class="sxs-lookup"><span data-stu-id="3e7b7-144">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="3e7b7-145">Los datos de las tablas de búsqueda avanzada se clasifican generalmente en los siguientes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-145">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="3e7b7-146">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="3e7b7-146">Data type</span></span> | <span data-ttu-id="3e7b7-147">Descripción e implicaciones de la consulta</span><span class="sxs-lookup"><span data-stu-id="3e7b7-147">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="3e7b7-148">Información sobre datos y hora que representan las marcas de tiempo del evento</span><span class="sxs-lookup"><span data-stu-id="3e7b7-148">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="3e7b7-149">Cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="3e7b7-149">Character string</span></span> |
| `bool` | <span data-ttu-id="3e7b7-150">Verdadero o falso</span><span class="sxs-lookup"><span data-stu-id="3e7b7-150">True or false</span></span> |
| `int` | <span data-ttu-id="3e7b7-151">Valor numérico de 32 bits</span><span class="sxs-lookup"><span data-stu-id="3e7b7-151">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="3e7b7-152">Valor numérico de 64 bits</span><span class="sxs-lookup"><span data-stu-id="3e7b7-152">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="3e7b7-153">Usar las consultas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e7b7-153">Use sample queries</span></span>

<span data-ttu-id="3e7b7-154">La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-154">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="3e7b7-155">Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-155">Try running these queries and making small modifications to them.</span></span>

![Imagen de la ventana de búsqueda avanzada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="3e7b7-157">Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-157">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="3e7b7-158">Explore las consultas compartidas en la parte izquierda de la página o en el repositorio de consultas de GitHub.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-158">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="3e7b7-159">Acceso a documentación del lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="3e7b7-159">Access query language documentation</span></span>

<span data-ttu-id="3e7b7-160">Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="3e7b7-160">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3e7b7-161">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3e7b7-161">Related topics</span></span>
- [<span data-ttu-id="3e7b7-162">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3e7b7-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3e7b7-163">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="3e7b7-163">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3e7b7-164">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="3e7b7-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3e7b7-165">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3e7b7-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3e7b7-166">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="3e7b7-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3e7b7-167">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="3e7b7-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
