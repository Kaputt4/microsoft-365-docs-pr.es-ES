---
title: Trabajar con resultados avanzados de consulta de búsqueda en Microsoft 365 Defender
description: Obtener el máximo partido de los resultados de consulta devueltos por la búsqueda avanzada en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, visualización, gráfico, filtros, desglose
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
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952601"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="edc2c-104">Trabajar con resultados avanzados de consulta de búsqueda</span><span class="sxs-lookup"><span data-stu-id="edc2c-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="edc2c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="edc2c-105">**Applies to:**</span></span>
- <span data-ttu-id="edc2c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="edc2c-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="edc2c-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="edc2c-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="edc2c-108">Aunque puede crear [](advanced-hunting-overview.md) las consultas de búsqueda avanzadas para devolver información muy precisa, también puede trabajar con los resultados de la consulta para obtener más información e investigar actividades e indicadores específicos.</span><span class="sxs-lookup"><span data-stu-id="edc2c-108">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="edc2c-109">Puede realizar las siguientes acciones en los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="edc2c-109">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="edc2c-110">Ver resultados como una tabla o gráfico</span><span class="sxs-lookup"><span data-stu-id="edc2c-110">View results as a table or chart</span></span>
- <span data-ttu-id="edc2c-111">Exportar tablas y gráficos</span><span class="sxs-lookup"><span data-stu-id="edc2c-111">Export tables and charts</span></span>
- <span data-ttu-id="edc2c-112">Profundizar en la información detallada de la entidad</span><span class="sxs-lookup"><span data-stu-id="edc2c-112">Drill down to detailed entity information</span></span>
- <span data-ttu-id="edc2c-113">Ajustar las consultas directamente desde los resultados o aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="edc2c-113">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="edc2c-114">Ver resultados de consulta como tabla o gráfico</span><span class="sxs-lookup"><span data-stu-id="edc2c-114">View query results as a table or chart</span></span>
<span data-ttu-id="edc2c-115">De forma predeterminada, la búsqueda avanzada muestra los resultados de la consulta como datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="edc2c-115">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="edc2c-116">También puede mostrar los mismos datos que un gráfico.</span><span class="sxs-lookup"><span data-stu-id="edc2c-116">You can also display the same data as a chart.</span></span> <span data-ttu-id="edc2c-117">La búsqueda avanzada admite las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="edc2c-117">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="edc2c-118">Tipo de vista</span><span class="sxs-lookup"><span data-stu-id="edc2c-118">View type</span></span> | <span data-ttu-id="edc2c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="edc2c-119">Description</span></span> |
| -- | -- |
| <span data-ttu-id="edc2c-120">**Table**</span><span class="sxs-lookup"><span data-stu-id="edc2c-120">**Table**</span></span> | <span data-ttu-id="edc2c-121">Muestra los resultados de la consulta en formato tabular</span><span class="sxs-lookup"><span data-stu-id="edc2c-121">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="edc2c-122">**Gráfico de columnas**</span><span class="sxs-lookup"><span data-stu-id="edc2c-122">**Column chart**</span></span> | <span data-ttu-id="edc2c-123">Representa una serie de elementos únicos en el eje X como barras verticales cuyas alturas representan valores numéricos de otro campo</span><span class="sxs-lookup"><span data-stu-id="edc2c-123">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="edc2c-124">**Gráfico de columnas apiladas**</span><span class="sxs-lookup"><span data-stu-id="edc2c-124">**Stacked column chart**</span></span> | <span data-ttu-id="edc2c-125">Representa una serie de elementos únicos en el eje X como barras verticales apiladas cuyas alturas representan valores numéricos de uno o más campos</span><span class="sxs-lookup"><span data-stu-id="edc2c-125">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="edc2c-126">**Gráfico circular**</span><span class="sxs-lookup"><span data-stu-id="edc2c-126">**Pie chart**</span></span> | <span data-ttu-id="edc2c-127">Representa los pies seccionales que representan elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="edc2c-127">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="edc2c-128">El tamaño de cada circular representa valores numéricos de otro campo.</span><span class="sxs-lookup"><span data-stu-id="edc2c-128">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="edc2c-129">**Gráfico de donas**</span><span class="sxs-lookup"><span data-stu-id="edc2c-129">**Donut chart**</span></span> | <span data-ttu-id="edc2c-130">Representa arcos seccionales que representan elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="edc2c-130">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="edc2c-131">La longitud de cada arco representa valores numéricos de otro campo.</span><span class="sxs-lookup"><span data-stu-id="edc2c-131">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="edc2c-132">**Gráfico de líneas**</span><span class="sxs-lookup"><span data-stu-id="edc2c-132">**Line chart**</span></span> | <span data-ttu-id="edc2c-133">Traza valores numéricos para una serie de elementos únicos y conecta los valores trazados</span><span class="sxs-lookup"><span data-stu-id="edc2c-133">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="edc2c-134">**Gráfico de dispersión**</span><span class="sxs-lookup"><span data-stu-id="edc2c-134">**Scatter chart**</span></span> | <span data-ttu-id="edc2c-135">Traza valores numéricos para una serie de elementos únicos</span><span class="sxs-lookup"><span data-stu-id="edc2c-135">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="edc2c-136">**Gráfico de áreas**</span><span class="sxs-lookup"><span data-stu-id="edc2c-136">**Area chart**</span></span> | <span data-ttu-id="edc2c-137">Traza valores numéricos para una serie de elementos únicos y rellena las secciones debajo de los valores trazados</span><span class="sxs-lookup"><span data-stu-id="edc2c-137">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="edc2c-138">Crear consultas para gráficos efectivos</span><span class="sxs-lookup"><span data-stu-id="edc2c-138">Construct queries for effective charts</span></span>
<span data-ttu-id="edc2c-139">Al representar gráficos, la búsqueda avanzada identifica automáticamente las columnas de interés y los valores numéricos que se agregan.</span><span class="sxs-lookup"><span data-stu-id="edc2c-139">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="edc2c-140">Para obtener gráficos significativos, construya las consultas para devolver los valores específicos que desea ver visualizados.</span><span class="sxs-lookup"><span data-stu-id="edc2c-140">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="edc2c-141">Estas son algunas consultas de ejemplo y los gráficos resultantes.</span><span class="sxs-lookup"><span data-stu-id="edc2c-141">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="edc2c-142">Alertas por gravedad</span><span class="sxs-lookup"><span data-stu-id="edc2c-142">Alerts by severity</span></span>
<span data-ttu-id="edc2c-143">Use el `summarize` operador para obtener un recuento numérico de los valores que desea gráfico.</span><span class="sxs-lookup"><span data-stu-id="edc2c-143">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="edc2c-144">La consulta siguiente usa el `summarize` operador para obtener el número de alertas por gravedad.</span><span class="sxs-lookup"><span data-stu-id="edc2c-144">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="edc2c-145">Al representar los resultados, un gráfico de columnas muestra cada valor de gravedad como una columna independiente:</span><span class="sxs-lookup"><span data-stu-id="edc2c-145">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="edc2c-146">![Imagen de resultados avanzados de consulta de búsqueda que se muestran como un gráfico de columnas Resultados de consulta para alertas por gravedad mostradas ](../../media/advanced-hunting-column-chart.jpg)
 *como gráfico de columnas*</span><span class="sxs-lookup"><span data-stu-id="edc2c-146">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="edc2c-147">Gravedad de alerta por sistema operativo</span><span class="sxs-lookup"><span data-stu-id="edc2c-147">Alert severity by operating system</span></span>
<span data-ttu-id="edc2c-148">También puede usar el operador para `summarize` preparar los resultados de los valores de gráfico de varios campos.</span><span class="sxs-lookup"><span data-stu-id="edc2c-148">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="edc2c-149">Por ejemplo, es posible que desee comprender cómo se distribuyen las gravedades de alerta entre sistemas operativos (SO).</span><span class="sxs-lookup"><span data-stu-id="edc2c-149">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="edc2c-150">La consulta siguiente usa un operador para extraer información del sistema operativo de la tabla y, a continuación, usa para contar los valores `join` `DeviceInfo` de las columnas `summarize` `OSPlatform` `Severity` y:</span><span class="sxs-lookup"><span data-stu-id="edc2c-150">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="edc2c-151">Estos resultados se visualizan mejor con un gráfico de columnas apiladas:</span><span class="sxs-lookup"><span data-stu-id="edc2c-151">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="edc2c-152">![Imagen de resultados avanzados de consulta de búsqueda que se muestran como un gráfico apilado Resultados de consulta para alertas por sistema operativo y gravedad mostradas ](../../media/advanced-hunting-stacked-chart.jpg)
 *como un gráfico apilado*</span><span class="sxs-lookup"><span data-stu-id="edc2c-152">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="edc2c-153">Correos electrónicos de suplantación de identidad (phishing) en los diez dominios de remitente principales</span><span class="sxs-lookup"><span data-stu-id="edc2c-153">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="edc2c-154">Si está trabajando con una lista de valores que no es finita, puede usar el operador para mostrar solo los valores con más `Top` instancias.</span><span class="sxs-lookup"><span data-stu-id="edc2c-154">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="edc2c-155">Por ejemplo, para obtener los diez dominios de remitente con más correos electrónicos de suplantación de identidad, use la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="edc2c-155">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="edc2c-156">Use la vista gráfico circular para mostrar de forma eficaz la distribución en los dominios superiores:</span><span class="sxs-lookup"><span data-stu-id="edc2c-156">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="edc2c-157">![Imagen de resultados avanzados de consulta de búsqueda que se muestran como gráfico circular gráfico circular que muestra la distribución de correos electrónicos de suplantación de identidad ](../../media/advanced-hunting-pie-chart.jpg)
 *(phishing) en los dominios principales del remitente*</span><span class="sxs-lookup"><span data-stu-id="edc2c-157">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="edc2c-158">Actividades de archivo con el tiempo</span><span class="sxs-lookup"><span data-stu-id="edc2c-158">File activities over time</span></span>
<span data-ttu-id="edc2c-159">Con el operador con la función, puede comprobar si hay eventos que impliquen un indicador determinado a lo `summarize` largo del `bin()` tiempo.</span><span class="sxs-lookup"><span data-stu-id="edc2c-159">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="edc2c-160">La consulta siguiente cuenta los eventos que implican el archivo en intervalos de 30 minutos para mostrar picos de `invoice.doc` actividad relacionados con ese archivo:</span><span class="sxs-lookup"><span data-stu-id="edc2c-160">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="edc2c-161">El siguiente gráfico de líneas resalta claramente los períodos de tiempo con más actividad que implica `invoice.doc` :</span><span class="sxs-lookup"><span data-stu-id="edc2c-161">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="edc2c-162">![Imagen de resultados avanzados de consulta de búsqueda que se muestran como un gráfico de líneas Gráfico de líneas que muestra el número de eventos ](../../media/advanced-hunting-line-chart.jpg)
 *que implican un archivo a lo largo del tiempo*</span><span class="sxs-lookup"><span data-stu-id="edc2c-162">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="edc2c-163">Exportar tablas y gráficos</span><span class="sxs-lookup"><span data-stu-id="edc2c-163">Export tables and charts</span></span>
<span data-ttu-id="edc2c-164">Después de ejecutar una consulta, **seleccione Exportar** para guardar los resultados en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="edc2c-164">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="edc2c-165">La vista elegida determina cómo se exportan los resultados:</span><span class="sxs-lookup"><span data-stu-id="edc2c-165">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="edc2c-166">**Vista tabla:** los resultados de la consulta se exportan en forma tabular como un libro Microsoft Excel tabla</span><span class="sxs-lookup"><span data-stu-id="edc2c-166">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="edc2c-167">**Cualquier gráfico:** los resultados de la consulta se exportan como una imagen JPEG del gráfico representado</span><span class="sxs-lookup"><span data-stu-id="edc2c-167">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="edc2c-168">Profundizar en los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="edc2c-168">Drill down from query results</span></span>
<span data-ttu-id="edc2c-169">Para inspeccionar rápidamente un registro en los resultados de la consulta, seleccione la fila correspondiente para abrir el panel **Inspeccionar registro.**</span><span class="sxs-lookup"><span data-stu-id="edc2c-169">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="edc2c-170">El panel proporciona la siguiente información basada en el registro seleccionado:</span><span class="sxs-lookup"><span data-stu-id="edc2c-170">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="edc2c-171">**Activos:** vista resumida de los principales activos (buzones, dispositivos y usuarios) que se encuentran en el registro, enriquecidos con información disponible, como los niveles de riesgo y exposición</span><span class="sxs-lookup"><span data-stu-id="edc2c-171">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="edc2c-172">**Árbol de procesos:** generado para registros con información del proceso y enriquecido mediante información contextual disponible; en general, las consultas que devuelven más columnas pueden dar como resultado árboles de proceso más enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="edc2c-172">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="edc2c-173">**Todos los detalles:** todos los valores de las columnas del registro</span><span class="sxs-lookup"><span data-stu-id="edc2c-173">**All details** — all the values from the columns in the record</span></span>  

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="edc2c-175">Para ver más información sobre una entidad específica en los resultados de la consulta, como una máquina, un archivo, un usuario, una dirección IP o una dirección URL, seleccione el identificador de entidad para abrir una página de perfil detallada para esa entidad.</span><span class="sxs-lookup"><span data-stu-id="edc2c-175">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="edc2c-176">Modificar las consultas de los resultados</span><span class="sxs-lookup"><span data-stu-id="edc2c-176">Tweak your queries from the results</span></span>
<span data-ttu-id="edc2c-177">Haga clic con el botón derecho en un valor en el conjunto de resultados para mejorar la búsqueda rápidamente.</span><span class="sxs-lookup"><span data-stu-id="edc2c-177">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="edc2c-178">Puede usar las opciones para:</span><span class="sxs-lookup"><span data-stu-id="edc2c-178">You can use the options to:</span></span>

- <span data-ttu-id="edc2c-179">Buscar explícitamente el valor seleccionado (`==`)</span><span class="sxs-lookup"><span data-stu-id="edc2c-179">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="edc2c-180">Excluir el valor seleccionado de la consulta (`!=`)</span><span class="sxs-lookup"><span data-stu-id="edc2c-180">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="edc2c-181">Obtenga más operadores avanzados para agregar el valor a la consulta, como `contains`, `starts with` y `ends with`</span><span class="sxs-lookup"><span data-stu-id="edc2c-181">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Imagen del conjunto de resultados de búsqueda avanzada](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="edc2c-183">Filtrar los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="edc2c-183">Filter the query results</span></span>
<span data-ttu-id="edc2c-184">Los filtros que aparecen a la derecha proporcionan un resumen del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="edc2c-184">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="edc2c-185">Cada columna tiene una sección en la que se muestra una lista de los valores de la columna y el número de instancias.</span><span class="sxs-lookup"><span data-stu-id="edc2c-185">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="edc2c-186">Para refinar la consulta, seleccione los botones o de los valores que desea incluir o excluir y, a `+` `-` continuación, seleccione Ejecutar **consulta**.</span><span class="sxs-lookup"><span data-stu-id="edc2c-186">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Imagen del filtro de búsqueda avanzada](../../media/advanced-hunting-filter.png)

<span data-ttu-id="edc2c-188">Cuando aplica el filtro para modificar la consulta y, a continuación, ejecuta la consulta, los resultados se actualizan en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="edc2c-188">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

>[!NOTE]
><span data-ttu-id="edc2c-189">Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="edc2c-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="edc2c-190">[Activa Microsoft 365 Defender para](m365d-enable.md) buscar amenazas con más orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="edc2c-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="edc2c-191">Puede mover los flujos de trabajo avanzados de búsqueda de Microsoft Defender para endpoint a Microsoft 365 Defender siguiendo los pasos descritos en Migrar consultas avanzadas de búsqueda desde [Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md).</span><span class="sxs-lookup"><span data-stu-id="edc2c-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="edc2c-192">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="edc2c-192">Related topics</span></span>
- [<span data-ttu-id="edc2c-193">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="edc2c-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="edc2c-194">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="edc2c-194">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="edc2c-195">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="edc2c-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="edc2c-196">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="edc2c-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="edc2c-197">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="edc2c-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="edc2c-198">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="edc2c-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="edc2c-199">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="edc2c-199">Custom detections overview</span></span>](custom-detections-overview.md)
