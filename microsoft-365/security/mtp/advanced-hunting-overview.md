---
title: Información general sobre la búsqueda avanzada en la Protección contra amenazas de Microsoft
description: Obtenga más información sobre las consultas de búsqueda avanzada en Microsoft 365 y cómo usarlas para encontrar de forma proactiva amenazas y debilidades en la red
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, consulta, telemetría, detecciones personalizadas, esquema, kusto, microsoft 365, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 03cd648a178d63b2b964e0136c105068f4d1c6ca
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911650"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="5a65d-104">Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5a65d-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="5a65d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5a65d-105">**Applies to:**</span></span>
- <span data-ttu-id="5a65d-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5a65d-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="5a65d-107">La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar.</span><span class="sxs-lookup"><span data-stu-id="5a65d-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="5a65d-108">Puede inspeccionar eventos de forma proactiva en su red para localizar indicadores y entidades interesantes.</span><span class="sxs-lookup"><span data-stu-id="5a65d-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="5a65d-109">El acceso flexible a los datos facilita la búsqueda sin restricciones de las amenazas conocidas y potenciales.</span><span class="sxs-lookup"><span data-stu-id="5a65d-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="5a65d-110">En el Centro de seguridad de Microsoft 365, la búsqueda avanzada es compatible con consultas que buscan datos de la ATP de Microsoft Defender, cubren datos de dispositivos integrados y Office 365 ATP, y proporcionan datos de mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5a65d-110">in the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="5a65d-111">Para usar la búsqueda avanzada, [active la Protección contra amenazas de Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="5a65d-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="5a65d-112">Introducción a la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="5a65d-112">Get started with advanced hunting</span></span>

<span data-ttu-id="5a65d-113">Le recomendamos que siga los pasos siguientes para empezar a trabajar rápidamente con la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="5a65d-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="5a65d-114">Objetivo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="5a65d-114">Learning goal</span></span> | <span data-ttu-id="5a65d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a65d-115">Description</span></span> | <span data-ttu-id="5a65d-116">Recurso</span><span class="sxs-lookup"><span data-stu-id="5a65d-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="5a65d-117">**Conozca el idioma**</span><span class="sxs-lookup"><span data-stu-id="5a65d-117">**Get a feel for the language**</span></span> | <span data-ttu-id="5a65d-118">La búsqueda avanzada está basada en el [lenguaje de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/) y admite la misma sintaxis y operadores.</span><span class="sxs-lookup"><span data-stu-id="5a65d-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="5a65d-119">Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta.</span><span class="sxs-lookup"><span data-stu-id="5a65d-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="5a65d-120">Introducción al lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="5a65d-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="5a65d-121">**Entender el esquema**</span><span class="sxs-lookup"><span data-stu-id="5a65d-121">**Understand the schema**</span></span> | <span data-ttu-id="5a65d-122">Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas.</span><span class="sxs-lookup"><span data-stu-id="5a65d-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="5a65d-123">Esto le ayudará a determinar dónde buscar datos y cómo crear las consultas.</span><span class="sxs-lookup"><span data-stu-id="5a65d-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="5a65d-124">Referencia del esquema</span><span class="sxs-lookup"><span data-stu-id="5a65d-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="5a65d-125">**Usar consultas predefinidas**</span><span class="sxs-lookup"><span data-stu-id="5a65d-125">**Use predefined queries**</span></span> | <span data-ttu-id="5a65d-126">Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas.</span><span class="sxs-lookup"><span data-stu-id="5a65d-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="5a65d-127">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="5a65d-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="5a65d-128">**Optimizar las consultas**</span><span class="sxs-lookup"><span data-stu-id="5a65d-128">**Optimize queries**</span></span> | <span data-ttu-id="5a65d-129">Obtenga información acerca de cómo crear consultas eficientes y consultas que combinan datos de mensajes de correo electrónico y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5a65d-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="5a65d-130">[Procedimientos recomendados de consulta](advanced-hunting-shared-queries.md), [buscar entre dispositivos y mensajes de correo electrónico](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="5a65d-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="5a65d-131">Obtener ayuda mientras escribe consultas</span><span class="sxs-lookup"><span data-stu-id="5a65d-131">Get help as you write queries</span></span>
<span data-ttu-id="5a65d-132">Aprovéchese de las funciones siguientes para escribir consultas más rápido:</span><span class="sxs-lookup"><span data-stu-id="5a65d-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="5a65d-133">**Sugerencias automáticas**: cuando escribe consultas, la búsqueda avanzada ofrece sugerencias.</span><span class="sxs-lookup"><span data-stu-id="5a65d-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="5a65d-134">**Referencia del esquema**: se proporciona una referencia de esquema que incluye la lista de tablas y sus columnas junto al área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5a65d-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="5a65d-135">Para obtener más información, mueva el puntero sobre un elemento.</span><span class="sxs-lookup"><span data-stu-id="5a65d-135">For more information, hover over an item.</span></span> <span data-ttu-id="5a65d-136">Haga doble clic en un elemento para insertarlo en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="5a65d-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="5a65d-137">Desglose de los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="5a65d-137">Drilldown from query results</span></span>
<span data-ttu-id="5a65d-138">Para ver más información sobre las entidades, como máquinas, archivos, usuarios, direcciones IP y URL, en los resultados de la consulta, simplemente haga clic en el identificador de entidad.</span><span class="sxs-lookup"><span data-stu-id="5a65d-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="5a65d-139">Se abrirá la página de perfil detallado de la entidad seleccionada en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5a65d-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="5a65d-140">Modificar las consultas de los resultados</span><span class="sxs-lookup"><span data-stu-id="5a65d-140">Tweak your queries from the results</span></span>
<span data-ttu-id="5a65d-141">Haga clic con el botón derecho en un valor en el conjunto de resultados para mejorar la búsqueda rápidamente.</span><span class="sxs-lookup"><span data-stu-id="5a65d-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="5a65d-142">Puede usar las opciones para:</span><span class="sxs-lookup"><span data-stu-id="5a65d-142">You can use the options on this page to modify the server farm settings.</span></span>

- <span data-ttu-id="5a65d-143">Buscar explícitamente el valor seleccionado (`==`)</span><span class="sxs-lookup"><span data-stu-id="5a65d-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="5a65d-144">Excluir el valor seleccionado de la consulta (`!=`)</span><span class="sxs-lookup"><span data-stu-id="5a65d-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="5a65d-145">Obtenga más operadores avanzados para agregar el valor a la consulta, como `contains`, `starts with` y `ends with`</span><span class="sxs-lookup"><span data-stu-id="5a65d-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Imagen del conjunto de resultados de la búsqueda avanzado ATP de Microsoft Defender](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="5a65d-147">Filtrar los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="5a65d-147">Filter the query results</span></span>
<span data-ttu-id="5a65d-148">Los filtros que aparecen a la derecha proporcionan un resumen del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5a65d-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="5a65d-149">Cada columna tiene una sección en la que se muestra una lista de los valores de la columna y el número de instancias.</span><span class="sxs-lookup"><span data-stu-id="5a65d-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="5a65d-150">Para refinar la consulta, seleccione los botones "+" o "-" que aparecen en los valores que desea incluir o excluir y, a continuación, seleccione **ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="5a65d-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Imagen del filtro de búsqueda avanzada](../images/advanced-hunting-filter.png)

<span data-ttu-id="5a65d-152">Cuando aplica el filtro para modificar la consulta y, a continuación, ejecuta la consulta, los resultados se actualizan en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="5a65d-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5a65d-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5a65d-153">Related topics</span></span>
- [<span data-ttu-id="5a65d-154">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="5a65d-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5a65d-155">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="5a65d-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5a65d-156">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5a65d-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5a65d-157">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="5a65d-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5a65d-158">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="5a65d-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)