---
title: Trabajar con los resultados de la consulta de búsqueda avanzada en protección contra amenazas de Microsoft
description: Aprovechar al máximo la mayoría de los resultados de la consulta de búsqueda avanzada en la protección contra amenazas de Microsoft
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, Microsoft 365, protección contra amenazas de Microsoft, visualización, gráfico, filtros explorar en profundidad
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
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929247"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="0a33c-104">Trabajar con los resultados de la consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="0a33c-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="0a33c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0a33c-105">**Applies to:**</span></span>
- <span data-ttu-id="0a33c-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0a33c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0a33c-107">Aunque puede crear consultas de [búsqueda avanzada](advanced-hunting-overview.md) para devolver información muy precisa, también puede trabajar con los resultados de la consulta para obtener más información e investigar actividades e indicadores específicos.</span><span class="sxs-lookup"><span data-stu-id="0a33c-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="0a33c-108">Puede realizar las siguientes acciones en los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="0a33c-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="0a33c-109">Ver los resultados como una tabla o un gráfico</span><span class="sxs-lookup"><span data-stu-id="0a33c-109">View results as a table or chart</span></span>
- <span data-ttu-id="0a33c-110">Exportar tablas y gráficos</span><span class="sxs-lookup"><span data-stu-id="0a33c-110">Export tables and charts</span></span>
- <span data-ttu-id="0a33c-111">Profundizar en la información de la entidad detallada</span><span class="sxs-lookup"><span data-stu-id="0a33c-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="0a33c-112">Ajustar las consultas directamente desde los resultados o aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="0a33c-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="0a33c-113">Ver los resultados de la consulta como una tabla o un gráfico</span><span class="sxs-lookup"><span data-stu-id="0a33c-113">View query results as a table or chart</span></span>
<span data-ttu-id="0a33c-114">De forma predeterminada, la búsqueda avanzada muestra los resultados de la consulta como datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="0a33c-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="0a33c-115">También puede mostrar los mismos datos que un gráfico.</span><span class="sxs-lookup"><span data-stu-id="0a33c-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="0a33c-116">La búsqueda avanzada es compatible con las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="0a33c-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="0a33c-117">Tipo de vista</span><span class="sxs-lookup"><span data-stu-id="0a33c-117">View type</span></span> | <span data-ttu-id="0a33c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0a33c-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="0a33c-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="0a33c-119">**Table**</span></span> | <span data-ttu-id="0a33c-120">Muestra los resultados de la consulta en formato de tabla.</span><span class="sxs-lookup"><span data-stu-id="0a33c-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="0a33c-121">**Gráfico de columnas**</span><span class="sxs-lookup"><span data-stu-id="0a33c-121">**Column chart**</span></span> | <span data-ttu-id="0a33c-122">Representa una serie de elementos únicos en el eje x como barras verticales cuyos altos representan valores numéricos de otro campo.</span><span class="sxs-lookup"><span data-stu-id="0a33c-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="0a33c-123">**Gráfico de columnas apiladas**</span><span class="sxs-lookup"><span data-stu-id="0a33c-123">**Stacked column chart**</span></span> | <span data-ttu-id="0a33c-124">Representa una serie de elementos únicos en el eje x como barras verticales apiladas cuyos altos representan valores numéricos de uno o más campos.</span><span class="sxs-lookup"><span data-stu-id="0a33c-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="0a33c-125">**Gráfico circular**</span><span class="sxs-lookup"><span data-stu-id="0a33c-125">**Pie chart**</span></span> | <span data-ttu-id="0a33c-126">Representa los gráficos circulares de sección que representan elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="0a33c-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="0a33c-127">El tamaño de cada gráfico circular representa valores numéricos de otro campo.</span><span class="sxs-lookup"><span data-stu-id="0a33c-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="0a33c-128">**Gráfico de anillos**</span><span class="sxs-lookup"><span data-stu-id="0a33c-128">**Donut chart**</span></span> | <span data-ttu-id="0a33c-129">Representa arcos de sección que representan elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="0a33c-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="0a33c-130">La longitud de cada arco representa valores numéricos de otro campo.</span><span class="sxs-lookup"><span data-stu-id="0a33c-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="0a33c-131">**Gráfico de líneas**</span><span class="sxs-lookup"><span data-stu-id="0a33c-131">**Line chart**</span></span> | <span data-ttu-id="0a33c-132">Traza valores numéricos para una serie de elementos únicos y conecta los valores trazados.</span><span class="sxs-lookup"><span data-stu-id="0a33c-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="0a33c-133">**Gráfico de dispersión**</span><span class="sxs-lookup"><span data-stu-id="0a33c-133">**Scatter chart**</span></span> | <span data-ttu-id="0a33c-134">Traza valores numéricos para una serie de elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="0a33c-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="0a33c-135">**Gráfico de área**</span><span class="sxs-lookup"><span data-stu-id="0a33c-135">**Area chart**</span></span> | <span data-ttu-id="0a33c-136">Traza valores numéricos para una serie de elementos únicos y rellena las secciones debajo de los valores representados.</span><span class="sxs-lookup"><span data-stu-id="0a33c-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="0a33c-137">Crear consultas para gráficos efectivos</span><span class="sxs-lookup"><span data-stu-id="0a33c-137">Construct queries for effective charts</span></span>
<span data-ttu-id="0a33c-138">Al representar gráficos, la caza avanzada identifica automáticamente las columnas de interés y los valores numéricos que se van a agregar.</span><span class="sxs-lookup"><span data-stu-id="0a33c-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="0a33c-139">Para obtener gráficos significativos, construya las consultas para devolver los valores específicos que desea ver visuales.</span><span class="sxs-lookup"><span data-stu-id="0a33c-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="0a33c-140">A continuación se muestran algunas consultas de ejemplo y los gráficos resultantes.</span><span class="sxs-lookup"><span data-stu-id="0a33c-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="0a33c-141">Alertas por gravedad</span><span class="sxs-lookup"><span data-stu-id="0a33c-141">Alerts by severity</span></span>
<span data-ttu-id="0a33c-142">Use el `summarize` operador para obtener un recuento numérico de los valores que desea representar en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="0a33c-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="0a33c-143">La siguiente consulta usa el `summarize` operador para obtener el número de alertas por gravedad.</span><span class="sxs-lookup"><span data-stu-id="0a33c-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="0a33c-144">Al representar los resultados, un gráfico de columnas muestra cada valor de gravedad como una columna independiente:</span><span class="sxs-lookup"><span data-stu-id="0a33c-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="0a33c-145">![Imagen de los resultados de la consulta de búsqueda avanzada mostrados como un gráfico](../../media/advanced-hunting-column-chart.jpg)
*de columnas resultados de consulta de alertas por gravedad mostrados como un gráfico de columnas*</span><span class="sxs-lookup"><span data-stu-id="0a33c-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="0a33c-146">Gravedad de la alerta por sistema operativo</span><span class="sxs-lookup"><span data-stu-id="0a33c-146">Alert severity by operating system</span></span>
<span data-ttu-id="0a33c-147">También puede usar el `summarize` operador para preparar los resultados para representar gráficamente valores de varios campos.</span><span class="sxs-lookup"><span data-stu-id="0a33c-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="0a33c-148">Por ejemplo, es posible que quiera comprender cómo se distribuyen las gravedades de las alertas entre sistemas operativos (SO).</span><span class="sxs-lookup"><span data-stu-id="0a33c-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="0a33c-149">La siguiente consulta usa un `join` operador para extraer información del sistema operativo de `DeviceInfo` la tabla y, a `summarize` continuación, usa para contar los `OSPlatform` valores `Severity` en las columnas y:</span><span class="sxs-lookup"><span data-stu-id="0a33c-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="0a33c-150">Estos resultados se pueden visualizar mejor usando un gráfico de columnas apiladas:</span><span class="sxs-lookup"><span data-stu-id="0a33c-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="0a33c-151">![Imagen de los resultados de la consulta de búsqueda avanzada mostrados](../../media/advanced-hunting-stacked-chart.jpg)
como*resultado de una consulta de gráfico apilado para alertas por sistema operativo y gravedad mostradas como un gráfico apilado*</span><span class="sxs-lookup"><span data-stu-id="0a33c-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="0a33c-152">Mensajes de suplantación de identidad en los diez principales dominios del remitente</span><span class="sxs-lookup"><span data-stu-id="0a33c-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="0a33c-153">Si está tratando con una lista de valores que no son finitos, puede usar el `Top` operador para representar solo los valores con la mayoría de las instancias.</span><span class="sxs-lookup"><span data-stu-id="0a33c-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="0a33c-154">Por ejemplo, para obtener los diez principales dominios de remitentes con la mayoría de los correos electrónicos de suplantación de identidad, use la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="0a33c-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="0a33c-155">Use la vista gráfico circular para mostrar de forma eficaz la distribución en los dominios superiores:</span><span class="sxs-lookup"><span data-stu-id="0a33c-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="0a33c-156">![Imagen de los resultados de la consulta de búsqueda avanzada mostrados como un gráfico circular gráfico](../../media/advanced-hunting-pie-chart.jpg)
circular*que muestra la distribución de mensajes de suplantación de identidad en los dominios principales del remitente*</span><span class="sxs-lookup"><span data-stu-id="0a33c-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="0a33c-157">Actividades de archivo a lo largo del tiempo</span><span class="sxs-lookup"><span data-stu-id="0a33c-157">File activities over time</span></span>
<span data-ttu-id="0a33c-158">Mediante el `summarize` operador con la `bin()` función, puede comprobar si hay eventos que impliquen un indicador en particular a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="0a33c-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="0a33c-159">La consulta siguiente cuenta los eventos relacionados con el `invoice.doc` archivo en intervalos de 30 minutos para mostrar picos en la actividad relacionada con el archivo:</span><span class="sxs-lookup"><span data-stu-id="0a33c-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="0a33c-160">El gráfico de líneas siguiente destaca claramente los períodos de tiempo con más `invoice.doc`actividad, lo que implica:</span><span class="sxs-lookup"><span data-stu-id="0a33c-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="0a33c-161">![Imagen de los resultados de la consulta de búsqueda avanzada mostrados como un gráfico de líneas del gráfico](../../media/advanced-hunting-line-chart.jpg)
de líneas*que muestra el número de eventos que implican un archivo a lo largo del tiempo*</span><span class="sxs-lookup"><span data-stu-id="0a33c-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="0a33c-162">Exportar tablas y gráficos</span><span class="sxs-lookup"><span data-stu-id="0a33c-162">Export tables and charts</span></span>
<span data-ttu-id="0a33c-163">Después de ejecutar una consulta, seleccione **exportar** para guardar los resultados en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="0a33c-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="0a33c-164">La vista elegida determina cómo se exportarán los resultados:</span><span class="sxs-lookup"><span data-stu-id="0a33c-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="0a33c-165">**Vista de tabla** : los resultados de la consulta se exportan en formato tabular como libro de Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="0a33c-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="0a33c-166">**Cualquier gráfico** : los resultados de la consulta se exportan como una imagen JPEG del gráfico representado.</span><span class="sxs-lookup"><span data-stu-id="0a33c-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="0a33c-167">Profundizar desde los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="0a33c-167">Drill down from query results</span></span>
<span data-ttu-id="0a33c-168">Para ver más información sobre las entidades, como máquinas, archivos, usuarios, direcciones IP y URL, en los resultados de la consulta, simplemente haga clic en el identificador de entidad.</span><span class="sxs-lookup"><span data-stu-id="0a33c-168">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="0a33c-169">Se abrirá la página de perfil detallado de la entidad seleccionada en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0a33c-169">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="0a33c-170">Modificar las consultas de los resultados</span><span class="sxs-lookup"><span data-stu-id="0a33c-170">Tweak your queries from the results</span></span>
<span data-ttu-id="0a33c-171">Haga clic con el botón derecho en un valor en el conjunto de resultados para mejorar la búsqueda rápidamente.</span><span class="sxs-lookup"><span data-stu-id="0a33c-171">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="0a33c-172">Puede usar las opciones para:</span><span class="sxs-lookup"><span data-stu-id="0a33c-172">You can use the options to:</span></span>

- <span data-ttu-id="0a33c-173">Buscar explícitamente el valor seleccionado (`==`)</span><span class="sxs-lookup"><span data-stu-id="0a33c-173">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="0a33c-174">Excluir el valor seleccionado de la consulta (`!=`)</span><span class="sxs-lookup"><span data-stu-id="0a33c-174">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="0a33c-175">Obtenga más operadores avanzados para agregar el valor a la consulta, como `contains`, `starts with` y `ends with`</span><span class="sxs-lookup"><span data-stu-id="0a33c-175">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Imagen del conjunto de resultados de caza avanzado](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="0a33c-177">Filtrar los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="0a33c-177">Filter the query results</span></span>
<span data-ttu-id="0a33c-178">Los filtros que aparecen a la derecha proporcionan un resumen del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0a33c-178">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="0a33c-179">Cada columna tiene una sección en la que se muestra una lista de los valores de la columna y el número de instancias.</span><span class="sxs-lookup"><span data-stu-id="0a33c-179">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="0a33c-180">Refine la consulta seleccionando los `+` botones `-` o de los valores que desea incluir o excluir y, a continuación, seleccionando **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="0a33c-180">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Imagen del filtro de búsqueda avanzada](../../media/advanced-hunting-filter.png)

<span data-ttu-id="0a33c-182">Cuando aplica el filtro para modificar la consulta y, a continuación, ejecuta la consulta, los resultados se actualizan en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="0a33c-182">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a33c-183">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0a33c-183">Related topics</span></span>
- [<span data-ttu-id="0a33c-184">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="0a33c-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0a33c-185">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="0a33c-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0a33c-186">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="0a33c-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0a33c-187">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0a33c-187">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0a33c-188">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="0a33c-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0a33c-189">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="0a33c-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="0a33c-190">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="0a33c-190">Custom detections overview</span></span>](custom-detections-overview.md)
