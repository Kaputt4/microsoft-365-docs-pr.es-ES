---
title: Trabajar con resultados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Obtener el máximo partido de los resultados de la consulta devueltos por la búsqueda avanzada en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, microsoft 365, Protección contra amenazas de Microsoft, visualización, gráfico, filtros, exploración en profundidad
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
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932327"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="2a333-104">Trabajar con resultados de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="2a333-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a333-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2a333-105">**Applies to:**</span></span>
- <span data-ttu-id="2a333-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a333-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2a333-107">Aunque puede crear [](advanced-hunting-overview.md) consultas de búsqueda avanzada para devolver información muy precisa, también puede trabajar con los resultados de la consulta para obtener más información e investigar actividades e indicadores específicos.</span><span class="sxs-lookup"><span data-stu-id="2a333-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="2a333-108">Puede realizar las siguientes acciones en los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="2a333-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="2a333-109">Ver resultados como una tabla o gráfico</span><span class="sxs-lookup"><span data-stu-id="2a333-109">View results as a table or chart</span></span>
- <span data-ttu-id="2a333-110">Exportar tablas y gráficos</span><span class="sxs-lookup"><span data-stu-id="2a333-110">Export tables and charts</span></span>
- <span data-ttu-id="2a333-111">Explorar en profundidad la información detallada de la entidad</span><span class="sxs-lookup"><span data-stu-id="2a333-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="2a333-112">Retocar las consultas directamente desde los resultados o aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="2a333-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="2a333-113">Ver los resultados de la consulta como una tabla o un gráfico</span><span class="sxs-lookup"><span data-stu-id="2a333-113">View query results as a table or chart</span></span>
<span data-ttu-id="2a333-114">De forma predeterminada, la búsqueda avanzada muestra los resultados de la consulta como datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="2a333-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="2a333-115">También puede mostrar los mismos datos que un gráfico.</span><span class="sxs-lookup"><span data-stu-id="2a333-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="2a333-116">La búsqueda avanzada admite las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="2a333-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="2a333-117">Tipo de vista</span><span class="sxs-lookup"><span data-stu-id="2a333-117">View type</span></span> | <span data-ttu-id="2a333-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a333-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="2a333-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="2a333-119">**Table**</span></span> | <span data-ttu-id="2a333-120">Muestra los resultados de la consulta en formato tabular</span><span class="sxs-lookup"><span data-stu-id="2a333-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="2a333-121">**Gráfico de columnas**</span><span class="sxs-lookup"><span data-stu-id="2a333-121">**Column chart**</span></span> | <span data-ttu-id="2a333-122">Representa una serie de elementos únicos en el eje X como barras verticales cuyos altos representan valores numéricos de otro campo</span><span class="sxs-lookup"><span data-stu-id="2a333-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="2a333-123">**Gráfico de columnas apiladas**</span><span class="sxs-lookup"><span data-stu-id="2a333-123">**Stacked column chart**</span></span> | <span data-ttu-id="2a333-124">Representa una serie de elementos únicos en el eje X como barras verticales apiladas cuyos altos representan valores numéricos de uno o más campos</span><span class="sxs-lookup"><span data-stu-id="2a333-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="2a333-125">**Gráfico circular**</span><span class="sxs-lookup"><span data-stu-id="2a333-125">**Pie chart**</span></span> | <span data-ttu-id="2a333-126">Representa los pies de sección que representan elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="2a333-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="2a333-127">El tamaño de cada gráfico circular representa valores numéricos de otro campo.</span><span class="sxs-lookup"><span data-stu-id="2a333-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="2a333-128">**Gráfico de donas**</span><span class="sxs-lookup"><span data-stu-id="2a333-128">**Donut chart**</span></span> | <span data-ttu-id="2a333-129">Representa arcos de sección que representan elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="2a333-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="2a333-130">La longitud de cada arco representa valores numéricos de otro campo.</span><span class="sxs-lookup"><span data-stu-id="2a333-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="2a333-131">**Gráfico de líneas**</span><span class="sxs-lookup"><span data-stu-id="2a333-131">**Line chart**</span></span> | <span data-ttu-id="2a333-132">Traza valores numéricos para una serie de elementos únicos y conecta los valores trazados</span><span class="sxs-lookup"><span data-stu-id="2a333-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="2a333-133">**Gráfico de dispersión**</span><span class="sxs-lookup"><span data-stu-id="2a333-133">**Scatter chart**</span></span> | <span data-ttu-id="2a333-134">Traza valores numéricos para una serie de elementos únicos</span><span class="sxs-lookup"><span data-stu-id="2a333-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="2a333-135">**Gráfico de áreas**</span><span class="sxs-lookup"><span data-stu-id="2a333-135">**Area chart**</span></span> | <span data-ttu-id="2a333-136">Traza los valores numéricos de una serie de elementos únicos y rellena las secciones debajo de los valores trazados</span><span class="sxs-lookup"><span data-stu-id="2a333-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="2a333-137">Crear consultas para gráficos efectivos</span><span class="sxs-lookup"><span data-stu-id="2a333-137">Construct queries for effective charts</span></span>
<span data-ttu-id="2a333-138">Al representar gráficos, la búsqueda avanzada identifica automáticamente las columnas de interés y los valores numéricos que se agregan.</span><span class="sxs-lookup"><span data-stu-id="2a333-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="2a333-139">Para obtener gráficos significativos, cree las consultas para devolver los valores específicos que desea ver visualizados.</span><span class="sxs-lookup"><span data-stu-id="2a333-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="2a333-140">Estas son algunas consultas de ejemplo y los gráficos resultantes.</span><span class="sxs-lookup"><span data-stu-id="2a333-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="2a333-141">Alertas por gravedad</span><span class="sxs-lookup"><span data-stu-id="2a333-141">Alerts by severity</span></span>
<span data-ttu-id="2a333-142">Use el `summarize` operador para obtener un recuento numérico de los valores que desea gráficos.</span><span class="sxs-lookup"><span data-stu-id="2a333-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="2a333-143">La consulta siguiente usa el `summarize` operador para obtener el número de alertas por gravedad.</span><span class="sxs-lookup"><span data-stu-id="2a333-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="2a333-144">Al representar los resultados, un gráfico de columnas muestra cada valor de gravedad como una columna independiente:</span><span class="sxs-lookup"><span data-stu-id="2a333-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="2a333-145">![Imagen de resultados de consulta de búsqueda avanzada que se muestran como un gráfico de columnas Resultados de consulta para alertas por gravedad mostradas ](../../media/advanced-hunting-column-chart.jpg)
 *como un gráfico de columnas*</span><span class="sxs-lookup"><span data-stu-id="2a333-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="2a333-146">Gravedad de alerta por sistema operativo</span><span class="sxs-lookup"><span data-stu-id="2a333-146">Alert severity by operating system</span></span>
<span data-ttu-id="2a333-147">También puede usar el operador `summarize` para preparar los resultados de los gráficos de valores de varios campos.</span><span class="sxs-lookup"><span data-stu-id="2a333-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="2a333-148">Por ejemplo, es posible que quieras comprender cómo se distribuyen las gravedades de alerta entre sistemas operativos (SO).</span><span class="sxs-lookup"><span data-stu-id="2a333-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="2a333-149">La consulta siguiente usa un operador para extraer información del sistema operativo de la tabla y, a continuación, usa para contar los valores de `join` las columnas y las `DeviceInfo` `summarize` `OSPlatform` `Severity` columnas:</span><span class="sxs-lookup"><span data-stu-id="2a333-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="2a333-150">Estos resultados se visualizan mejor con un gráfico de columnas apiladas:</span><span class="sxs-lookup"><span data-stu-id="2a333-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="2a333-151">![Imagen de resultados de consulta de búsqueda avanzada que se muestran como un gráfico apilado Resultados de consulta para alertas por sistema operativo y gravedad mostradas ](../../media/advanced-hunting-stacked-chart.jpg)
 *como un gráfico apilado*</span><span class="sxs-lookup"><span data-stu-id="2a333-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="2a333-152">Mensajes de correo electrónico de suplantación de identidad (phishing) en los diez principales dominios de remitente</span><span class="sxs-lookup"><span data-stu-id="2a333-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="2a333-153">Si está trabajando con una lista de valores que no es finita, puede usar el operador para crear un gráfico solo de los valores con `Top` la mayoría de las instancias.</span><span class="sxs-lookup"><span data-stu-id="2a333-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="2a333-154">Por ejemplo, para obtener los diez dominios de remitente con más correos electrónicos de suplantación de identidad( phishing), use la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="2a333-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="2a333-155">Use la vista de gráfico circular para mostrar de forma eficaz la distribución entre los dominios principales:</span><span class="sxs-lookup"><span data-stu-id="2a333-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="2a333-156">![Imagen de los resultados de la consulta de búsqueda avanzada que se muestra como gráfico circular con una distribución de correos electrónicos de suplantación de identidad ](../../media/advanced-hunting-pie-chart.jpg)
 *entre los principales dominios de remitentes*</span><span class="sxs-lookup"><span data-stu-id="2a333-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="2a333-157">Actividades de archivos a lo largo del tiempo</span><span class="sxs-lookup"><span data-stu-id="2a333-157">File activities over time</span></span>
<span data-ttu-id="2a333-158">Si usas el operador con la función, puedes comprobar si hay eventos `summarize` relacionados con un indicador determinado a lo largo del `bin()` tiempo.</span><span class="sxs-lookup"><span data-stu-id="2a333-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="2a333-159">La consulta siguiente cuenta los eventos relacionados con el archivo en intervalos de 30 minutos para mostrar picos de `invoice.doc` actividad relacionados con ese archivo:</span><span class="sxs-lookup"><span data-stu-id="2a333-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="2a333-160">El siguiente gráfico de líneas resalta claramente los períodos de tiempo con más actividad que `invoice.doc` implica:</span><span class="sxs-lookup"><span data-stu-id="2a333-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="2a333-161">![Imagen de los resultados de la consulta de búsqueda avanzada que se muestra como un gráfico de líneas del gráfico de líneas que muestra el número de eventos relacionados ](../../media/advanced-hunting-line-chart.jpg)
 *con un archivo a lo largo del tiempo*</span><span class="sxs-lookup"><span data-stu-id="2a333-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="2a333-162">Exportar tablas y gráficos</span><span class="sxs-lookup"><span data-stu-id="2a333-162">Export tables and charts</span></span>
<span data-ttu-id="2a333-163">Después de ejecutar una consulta, **seleccione Exportar** para guardar los resultados en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="2a333-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="2a333-164">La vista elegida determina cómo se exportan los resultados:</span><span class="sxs-lookup"><span data-stu-id="2a333-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="2a333-165">**Vista de tabla:** los resultados de la consulta se exportan en formato tabular como un libro de Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="2a333-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="2a333-166">**Cualquier gráfico:** los resultados de la consulta se exportan como una imagen JPEG del gráfico representado</span><span class="sxs-lookup"><span data-stu-id="2a333-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="2a333-167">Explorar en profundidad los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="2a333-167">Drill down from query results</span></span>
<span data-ttu-id="2a333-168">Para inspeccionar rápidamente un registro en los resultados de la consulta, seleccione la fila correspondiente para abrir el panel **Inspeccionar registro.**</span><span class="sxs-lookup"><span data-stu-id="2a333-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="2a333-169">El panel proporciona la siguiente información en función del registro seleccionado:</span><span class="sxs-lookup"><span data-stu-id="2a333-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="2a333-170">**Activos:** vista resumida de los activos principales (buzones, dispositivos y usuarios) que se encuentran en el registro, enriquecida con la información disponible, como los niveles de riesgo y exposición.</span><span class="sxs-lookup"><span data-stu-id="2a333-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="2a333-171">**Árbol de procesos:** generado para registros con información de procesos y enriquecido mediante información contextual disponible; En general, las consultas que devuelven más columnas pueden dar como resultado árboles de proceso más enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="2a333-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="2a333-172">**Todos los** detalles: todos los valores de las columnas del registro</span><span class="sxs-lookup"><span data-stu-id="2a333-172">**All details** — all the values from the columns in the record</span></span>  

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="2a333-174">Para ver más información sobre una entidad específica en los resultados de la consulta, como una máquina, un archivo, un usuario, una dirección IP o una dirección URL, seleccione el identificador de entidad para abrir una página de perfil detallada para esa entidad.</span><span class="sxs-lookup"><span data-stu-id="2a333-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="2a333-175">Modificar las consultas de los resultados</span><span class="sxs-lookup"><span data-stu-id="2a333-175">Tweak your queries from the results</span></span>
<span data-ttu-id="2a333-176">Haga clic con el botón derecho en un valor en el conjunto de resultados para mejorar la búsqueda rápidamente.</span><span class="sxs-lookup"><span data-stu-id="2a333-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="2a333-177">Puede usar las opciones para:</span><span class="sxs-lookup"><span data-stu-id="2a333-177">You can use the options to:</span></span>

- <span data-ttu-id="2a333-178">Buscar explícitamente el valor seleccionado (`==`)</span><span class="sxs-lookup"><span data-stu-id="2a333-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="2a333-179">Excluir el valor seleccionado de la consulta (`!=`)</span><span class="sxs-lookup"><span data-stu-id="2a333-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="2a333-180">Obtenga más operadores avanzados para agregar el valor a la consulta, como `contains`, `starts with` y `ends with`</span><span class="sxs-lookup"><span data-stu-id="2a333-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Imagen del conjunto de resultados de búsqueda avanzada](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="2a333-182">Filtrar los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="2a333-182">Filter the query results</span></span>
<span data-ttu-id="2a333-183">Los filtros que aparecen a la derecha proporcionan un resumen del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2a333-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="2a333-184">Cada columna tiene una sección en la que se muestra una lista de los valores de la columna y el número de instancias.</span><span class="sxs-lookup"><span data-stu-id="2a333-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="2a333-185">Para refinar la consulta, seleccione los botones o los valores que desee incluir o excluir y, a `+` `-` continuación, seleccione Ejecutar **consulta.**</span><span class="sxs-lookup"><span data-stu-id="2a333-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Imagen del filtro de búsqueda avanzada](../../media/advanced-hunting-filter.png)

<span data-ttu-id="2a333-187">Cuando aplica el filtro para modificar la consulta y, a continuación, ejecuta la consulta, los resultados se actualizan en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="2a333-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a333-188">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2a333-188">Related topics</span></span>
- [<span data-ttu-id="2a333-189">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="2a333-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2a333-190">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="2a333-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2a333-191">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="2a333-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2a333-192">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="2a333-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2a333-193">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="2a333-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2a333-194">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="2a333-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2a333-195">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="2a333-195">Custom detections overview</span></span>](custom-detections-overview.md)
