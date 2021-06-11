---
title: Ver estadísticas de resultados de búsqueda de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo usar la característica de estadísticas de búsqueda para mostrar estadísticas de búsquedas de contenido y búsquedas asociadas con un caso de exhibición de documentos electrónicos principales en el centro de Microsoft 365 cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311153"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="d16b0-103">Ver estadísticas de resultados de búsqueda de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="d16b0-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="d16b0-104">Después de crear y ejecutar una búsqueda de contenido o una búsqueda asociada con un caso de exhibición de documentos electrónicos principal, puede ver estadísticas sobre los resultados de búsqueda estimados.</span><span class="sxs-lookup"><span data-stu-id="d16b0-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="d16b0-105">Esto incluye un resumen de los resultados de búsqueda (similar al resumen de los resultados de búsqueda estimados que se muestran en la página desplegable de búsqueda), las estadísticas de consulta, como el número de ubicaciones de contenido con elementos que coinciden con la consulta de búsqueda y la identidad de las ubicaciones de contenido que tienen los elementos más correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d16b0-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="d16b0-106">Además, puede usar la lista de palabras clave para configurar una búsqueda para devolver estadísticas para cada palabra clave de una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="d16b0-107">Esto le permite comparar el número de resultados devueltos por cada palabra clave de una consulta.</span><span class="sxs-lookup"><span data-stu-id="d16b0-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="d16b0-108">También puede descargar estadísticas de búsqueda en un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="d16b0-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="d16b0-109">Así, una vez que abra el archivo con Excel podrá usar las opciones de filtrado y ordenación del programa para comparar los resultados, o preparar informes de los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="d16b0-110">Obtener estadísticas para búsquedas</span><span class="sxs-lookup"><span data-stu-id="d16b0-110">Get statistics for searches</span></span>

<span data-ttu-id="d16b0-111">Para mostrar estadísticas de una búsqueda de contenido o una búsqueda asociada a un caso de exhibición de documentos electrónicos principal.:</span><span class="sxs-lookup"><span data-stu-id="d16b0-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="d16b0-112">En el centro Microsoft 365 cumplimiento, haga clic **en Mostrar todo** y, a continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d16b0-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="d16b0-113">Haga **clic en Búsqueda de** contenido y, a continuación, seleccione una búsqueda para mostrar la página desplegable.</span><span class="sxs-lookup"><span data-stu-id="d16b0-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="d16b0-114">O</span><span class="sxs-lookup"><span data-stu-id="d16b0-114">OR</span></span>

   - <span data-ttu-id="d16b0-115">Haga **clic en eDiscovery** Core , seleccione un caso y, a continuación, seleccione una búsqueda en la pestaña  >  Búsquedas para mostrar la página desplegable. </span><span class="sxs-lookup"><span data-stu-id="d16b0-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="d16b0-116">En la página desplegable de la búsqueda seleccionada, haga clic en la **pestaña Estadísticas de** búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![Ficha Estadísticas de búsqueda](../media/SearchStatistics1.png)

<span data-ttu-id="d16b0-118">La **pestaña Estadísticas de** búsqueda contiene las siguientes secciones que contienen diferentes tipos de estadísticas sobre la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="d16b0-119">Contenido de búsqueda</span><span class="sxs-lookup"><span data-stu-id="d16b0-119">Search content</span></span>

<span data-ttu-id="d16b0-120">En esta sección se muestra un resumen gráfico de los elementos estimados devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="d16b0-121">Esto indica el número de elementos que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="d16b0-122">Esta información le ofrece una idea sobre el número estimado de elementos devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![Estimaciones de búsqueda para una búsqueda](../media/SearchContentReport.png)

- <span data-ttu-id="d16b0-124">**Elementos estimados por ubicaciones:** el número total de elementos estimados devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="d16b0-125">También se muestra el número específico de elementos ubicados en buzones de correo y ubicados en sitios.</span><span class="sxs-lookup"><span data-stu-id="d16b0-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="d16b0-126">**Ubicaciones estimadas con aciertos:** el número total de ubicaciones de contenido que contienen elementos devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="d16b0-127">También se muestra el número específico de ubicaciones de buzones y sitios.</span><span class="sxs-lookup"><span data-stu-id="d16b0-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="d16b0-128">**Volumen de datos por ubicación (en MB):** tamaño total de todos los elementos estimados devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="d16b0-129">También se muestra el tamaño específico de los elementos de buzón y los elementos del sitio.</span><span class="sxs-lookup"><span data-stu-id="d16b0-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="d16b0-130">Informe de condiciones</span><span class="sxs-lookup"><span data-stu-id="d16b0-130">Condition report</span></span>

<span data-ttu-id="d16b0-131">En esta sección se muestran estadísticas sobre la consulta de búsqueda y el número de elementos estimados que coinciden con distintas partes de la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="d16b0-132">Puede usar estas estadísticas para analizar el número de elementos que coinciden con cada componente de la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="d16b0-133">Esto puede ayudarle a refinar los criterios de búsqueda y, si es necesario, restringir el ámbito del ámbito.</span><span class="sxs-lookup"><span data-stu-id="d16b0-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="d16b0-134">También puede descargar una copia de este informe en formato CSV.</span><span class="sxs-lookup"><span data-stu-id="d16b0-134">You can also download a copy of this report in CSV format.</span></span>

![Informe de condiciones](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="d16b0-136">**Tipo de ubicación:** tipo de ubicación de contenido a la que se aplican las estadísticas de consulta.</span><span class="sxs-lookup"><span data-stu-id="d16b0-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="d16b0-137">El valor de **Exchange** indica una ubicación de buzón; un valor de **SharePoint** indica una ubicación del sitio.</span><span class="sxs-lookup"><span data-stu-id="d16b0-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="d16b0-138">**Parte:** la parte de la consulta de búsqueda a la que se aplican las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="d16b0-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="d16b0-139">**Primary** indica toda la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="d16b0-140">**Palabra** clave indica que las estadísticas de la fila son para una palabra clave específica.</span><span class="sxs-lookup"><span data-stu-id="d16b0-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="d16b0-141">Si usa una lista de palabras clave para la consulta de búsqueda, las estadísticas de cada componente de la consulta se incluyen en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="d16b0-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="d16b0-142">Para obtener más información, vea [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span><span class="sxs-lookup"><span data-stu-id="d16b0-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="d16b0-143">**Condición:** el componente real (palabra clave o condición) de la consulta de búsqueda que devuelve las estadísticas mostradas en la fila correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d16b0-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="d16b0-144">**Ubicaciones con** aciertos: el número de ubicaciones de contenido (especificadas por la columna **Tipo** de ubicación) que contienen elementos que coinciden con la consulta principal o de palabra clave enumerada en la **columna Condición.**</span><span class="sxs-lookup"><span data-stu-id="d16b0-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="d16b0-145">**Elementos:** el número de elementos (desde la ubicación de contenido especificada) que coinciden con la consulta enumerada en la **columna Condición.**</span><span class="sxs-lookup"><span data-stu-id="d16b0-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="d16b0-146">Como se explicó anteriormente, si un elemento contiene varias instancias de una palabra clave que se está buscando, solo se cuenta una vez en esta columna.</span><span class="sxs-lookup"><span data-stu-id="d16b0-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="d16b0-147">**Tamaño (MB):** tamaño total de todos los elementos encontrados (en la ubicación de contenido especificada) que coinciden con la consulta de búsqueda en la **columna Condición.**</span><span class="sxs-lookup"><span data-stu-id="d16b0-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="d16b0-148">Ubicaciones principales</span><span class="sxs-lookup"><span data-stu-id="d16b0-148">Top locations</span></span>

<span data-ttu-id="d16b0-149">En esta sección se muestran estadísticas sobre las ubicaciones de contenido específicas con la mayoría de los elementos devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="d16b0-150">Se mostrarán las 1000 ubicaciones más importantes.</span><span class="sxs-lookup"><span data-stu-id="d16b0-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="d16b0-151">También puede descargar una copia de este informe en formato CSV.</span><span class="sxs-lookup"><span data-stu-id="d16b0-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="d16b0-152">El nombre de la ubicación (la dirección de correo electrónico de los buzones y la dirección URL de los sitios).</span><span class="sxs-lookup"><span data-stu-id="d16b0-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="d16b0-153">Tipo de ubicación (un buzón o sitio).</span><span class="sxs-lookup"><span data-stu-id="d16b0-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="d16b0-154">Número estimado de elementos en la ubicación de contenido devuelta por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="d16b0-155">Tamaño total de los elementos estimados en cada ubicación de contenido.</span><span class="sxs-lookup"><span data-stu-id="d16b0-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="d16b0-156">Obtener estadísticas de palabras clave para búsquedas</span><span class="sxs-lookup"><span data-stu-id="d16b0-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="d16b0-157">Como se explicó anteriormente, la sección **Informe de condiciones** muestra la consulta de búsqueda y el número (y tamaño) de los elementos que coinciden con la consulta.</span><span class="sxs-lookup"><span data-stu-id="d16b0-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="d16b0-158">Si usa una lista de palabras clave al crear o editar una consulta de búsqueda, puede obtener estadísticas mejoradas que muestran cuántos elementos coinciden con cada palabra clave o frase de palabra clave.</span><span class="sxs-lookup"><span data-stu-id="d16b0-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="d16b0-159">Esto puede ayudarle a identificar rápidamente qué partes de la consulta son las más (y menos) eficaces.</span><span class="sxs-lookup"><span data-stu-id="d16b0-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="d16b0-160">Por ejemplo, si una palabra clave devuelve un gran número de elementos, puede optar por refinar la consulta de palabras clave para restringir los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="d16b0-161">Para crear una lista de palabras clave y ver estadísticas de palabras clave para una búsqueda:</span><span class="sxs-lookup"><span data-stu-id="d16b0-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="d16b0-162">En el Microsoft 365 de cumplimiento, cree una nueva búsqueda de contenido o una búsqueda asociada con un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="d16b0-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="d16b0-163">En la **página Condiciones** del asistente para búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="d16b0-164">active la casilla **Mostrar lista de palabras clave.**</span><span class="sxs-lookup"><span data-stu-id="d16b0-164">select the **Show keyword list** checkbox.</span></span>

   ![Casilla mostrar lista de palabras clave](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="d16b0-166">Escriba una palabra clave o fase de palabra clave en una fila de la tabla de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="d16b0-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="d16b0-167">Por ejemplo, escriba **presupuesto en** la primera fila, escriba **seguridad** en la segunda fila y escriba **FY2021** en la tercera fila.</span><span class="sxs-lookup"><span data-stu-id="d16b0-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![Escriba hasta 20 palabras clave o frases de palabras clave en la lista](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="d16b0-169">Para ayudar a reducir los problemas causados por listas de palabras clave grandes, está limitado a un máximo de 20 filas en la lista de palabras clave de una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="d16b0-170">Después de agregar las palabras clave a la lista en la que desea buscar y obtener estadísticas, ejecute la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="d16b0-171">Cuando se complete la búsqueda, selecciónelo para mostrar la página desplegable.</span><span class="sxs-lookup"><span data-stu-id="d16b0-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="d16b0-172">En la **pestaña Estadísticas de búsqueda,** haga clic en el **informe Condición** para mostrar las estadísticas de palabras clave de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![Se muestran las estadísticas de cada palabra clave](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="d16b0-174">Como se muestra en la captura de pantalla anterior, se muestran las estadísticas de cada palabra clave; esto incluye:</span><span class="sxs-lookup"><span data-stu-id="d16b0-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="d16b0-175">Estadísticas de palabras clave para cada tipo de ubicación de contenido incluida en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="d16b0-176">Número de elementos de buzón sin indizar.</span><span class="sxs-lookup"><span data-stu-id="d16b0-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="d16b0-177">La consulta de búsqueda real y los resultados de cada palabra clave (identificada como **Palabra** clave en la **columna Parte),** que incluye cualquier condición de la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d16b0-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="d16b0-178">La consulta de búsqueda completa (identificada como **Principal** en la **columna Parte)** y las estadísticas de la consulta completa para cada tipo de ubicación.</span><span class="sxs-lookup"><span data-stu-id="d16b0-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="d16b0-179">Tenga en cuenta que estas son las mismas estadísticas que se muestran en la **pestaña** Resumen.</span><span class="sxs-lookup"><span data-stu-id="d16b0-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
