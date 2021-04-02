---
title: Procedimientos recomendados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Aprenda a crear consultas de búsqueda de amenazas rápidas, eficientes y sin errores con búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, esquema, kusto, evitar el tiempo de espera, líneas de comandos, identificador de proceso, optimizar, procedimiento recomendado, analizar, unirse, resumir
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
ms.openlocfilehash: e0744a01fc599b66f371b01194579f4845ed19fb
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498728"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="c969f-104">Prácticas recomendadas para la consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c969f-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c969f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c969f-105">**Applies to:**</span></span>
- <span data-ttu-id="c969f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c969f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c969f-107">Aplique estas recomendaciones para obtener resultados más rápido y evitar tiempos de espera mientras ejecuta consultas complejas.</span><span class="sxs-lookup"><span data-stu-id="c969f-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="c969f-108">Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="c969f-108">For more guidance on improving query performance, read [Kusto query best practices](/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="c969f-109">Comprender las cuotas de recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="c969f-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="c969f-110">Según su tamaño, cada inquilino tiene acceso a una cantidad establecida de recursos de CPU asignados para ejecutar consultas de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="c969f-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="c969f-111">Para obtener información detallada acerca de los distintos límites de servicio, lea acerca de las cuotas de búsqueda [avanzadas y los parámetros de uso](advanced-hunting-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c969f-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="c969f-112">Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar las instrucciones de optimización de este artículo para minimizar las interrupciones resultantes de la superación de cuotas o parámetros de uso.</span><span class="sxs-lookup"><span data-stu-id="c969f-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="c969f-113">Sugerencias de optimización general</span><span class="sxs-lookup"><span data-stu-id="c969f-113">General optimization tips</span></span>

- <span data-ttu-id="c969f-114">**Nuevas consultas de tamaño:** si sospecha que una consulta devolverá un conjunto de resultados grande, evalúe primero con el [operador count](/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="c969f-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="c969f-115">Use [limit](/azure/data-explorer/kusto/query/limitoperator) o su sinónimo `take` para evitar conjuntos de resultados grandes.</span><span class="sxs-lookup"><span data-stu-id="c969f-115">Use [limit](/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="c969f-116">Aplicar filtros de forma anticipada **:** aplique filtros de tiempo y otros filtros para reducir el conjunto de datos, especialmente antes de usar funciones de transformación y análisis, como [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)o [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="c969f-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="c969f-117">En el ejemplo siguiente, se usa la función de análisis [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) después de que los operadores de filtrado han reducido el número de registros.</span><span class="sxs-lookup"><span data-stu-id="c969f-117">In the example below, the parsing function [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="c969f-118">**Tiene latidos contiene**: para evitar buscar subcadenas en palabras innecesariamente, use el `has` operador en lugar de `contains` .</span><span class="sxs-lookup"><span data-stu-id="c969f-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="c969f-119">Información sobre operadores de cadenas</span><span class="sxs-lookup"><span data-stu-id="c969f-119">Learn about string operators</span></span>](/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="c969f-120">**Buscar en columnas específicas:** busque en una columna específica en lugar de ejecutar búsquedas de texto completo en todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="c969f-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="c969f-121">No lo use para `*` comprobar todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="c969f-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="c969f-122">**Distingue entre mayúsculas y minúsculas para** la velocidad: las búsquedas entre mayúsculas y minúsculas son más específicas y, por lo general, más rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c969f-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="c969f-123">Nombres de operadores de cadena que distinguen mayúsculas de [minúsculas,](/azure/data-explorer/kusto/query/datatypes-string-operators) `has_cs` como y , generalmente terminan con `contains_cs` `_cs` .</span><span class="sxs-lookup"><span data-stu-id="c969f-123">Names of case-sensitive [string operators](/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="c969f-124">También puede usar el operador igual a mayúsculas y minúsculas `==` en lugar de `=~` .</span><span class="sxs-lookup"><span data-stu-id="c969f-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="c969f-125">**Analizar, no extraer**— Siempre que sea posible, use el operador [de](/azure/data-explorer/kusto/query/parseoperator) análisis o una función de análisis como [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="c969f-125">**Parse, don't extract**—Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="c969f-126">Evite el `matches regex` operador de cadena o la función [extract(),](/azure/data-explorer/kusto/query/extractfunction)que usan expresión regular.</span><span class="sxs-lookup"><span data-stu-id="c969f-126">Avoid the `matches regex` string operator or the [extract() function](/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="c969f-127">Reserve el uso de la expresión regular para escenarios más complejos.</span><span class="sxs-lookup"><span data-stu-id="c969f-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="c969f-128">Más información sobre las funciones de análisis</span><span class="sxs-lookup"><span data-stu-id="c969f-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="c969f-129">**Tablas de filtro no expresiones**: no filtre en una columna calculada si puede filtrar en una columna de tabla.</span><span class="sxs-lookup"><span data-stu-id="c969f-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="c969f-130">**Sin términos de tres caracteres:** evite comparar o filtrar con términos con tres caracteres o menos.</span><span class="sxs-lookup"><span data-stu-id="c969f-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="c969f-131">Estos términos no están indizados y la coincidencia de ellos requerirá más recursos.</span><span class="sxs-lookup"><span data-stu-id="c969f-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="c969f-132">**Project selectivamente:** haga que los resultados sean más fáciles de comprender proyectando solo las columnas que necesita.</span><span class="sxs-lookup"><span data-stu-id="c969f-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="c969f-133">La proyección de columnas específicas antes de ejecutar [la combinación](/azure/data-explorer/kusto/query/joinoperator) o operaciones similares también ayuda a mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c969f-133">Projecting specific columns prior to running [join](/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="c969f-134">Optimizar el `join` operador</span><span class="sxs-lookup"><span data-stu-id="c969f-134">Optimize the `join` operator</span></span>
<span data-ttu-id="c969f-135">El [operador join](/azure/data-explorer/kusto/query/joinoperator) combina filas de dos tablas mediante valores coincidentes en columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="c969f-135">The [join operator](/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="c969f-136">Aplique estas sugerencias para optimizar las consultas que usan este operador.</span><span class="sxs-lookup"><span data-stu-id="c969f-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="c969f-137">**Tabla más pequeña a la izquierda:** el operador coincide con los registros de la tabla del lado izquierdo de la instrucción `join` join con los registros de la derecha.</span><span class="sxs-lookup"><span data-stu-id="c969f-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="c969f-138">Al tener la tabla más pequeña a la izquierda, se necesitarán hacer coincidir menos registros, lo que acelerará la consulta.</span><span class="sxs-lookup"><span data-stu-id="c969f-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="c969f-139">En la tabla siguiente, reducimos la tabla izquierda para cubrir solo tres dispositivos específicos antes de unirla con los SID de `DeviceLogonEvents` `IdentityLogonEvents` cuenta.</span><span class="sxs-lookup"><span data-stu-id="c969f-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- <span data-ttu-id="c969f-140">**Use** el sabor de unión [](/azure/data-explorer/kusto/query/joinoperator#join-flavors) interna : el tipo de combinación predeterminado o la combinación [innerunique](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplica las filas de la tabla izquierda por la clave de combinación antes de devolver una fila para cada coincidencia a la tabla derecha.</span><span class="sxs-lookup"><span data-stu-id="c969f-140">**Use the inner-join flavor**—The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="c969f-141">Si la tabla izquierda tiene varias filas con el mismo valor para la clave, esas filas se deduplicarán para dejar una sola fila aleatoria `join` para cada valor único.</span><span class="sxs-lookup"><span data-stu-id="c969f-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="c969f-142">Este comportamiento predeterminado puede dejar fuera información importante de la tabla izquierda que puede proporcionar información útil.</span><span class="sxs-lookup"><span data-stu-id="c969f-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="c969f-143">Por ejemplo, la consulta siguiente solo mostrará un correo electrónico que contenga datos adjuntos determinados, incluso si ese mismo dato adjunto se envió con varios mensajes de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="c969f-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="c969f-144">Para solucionar esta limitación, aplicamos el tipo [de](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) combinación interna especificando para mostrar todas las filas de la tabla izquierda con valores coincidentes `kind=inner` a la derecha:</span><span class="sxs-lookup"><span data-stu-id="c969f-144">To address this limitation, we apply the [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="c969f-145">**Unir registros desde una ventana de tiempo:** al investigar eventos de seguridad, los analistas buscan eventos relacionados que se producen alrededor del mismo período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c969f-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="c969f-146">Aplicar el mismo enfoque al usar también `join` beneficia el rendimiento al reducir el número de registros que se deben comprobar.</span><span class="sxs-lookup"><span data-stu-id="c969f-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="c969f-147">La consulta siguiente comprueba si hay eventos de inicio de sesión en un plazo de 30 minutos después de recibir un archivo malintencionado:</span><span class="sxs-lookup"><span data-stu-id="c969f-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="c969f-148">**Aplicar** filtros de tiempo en ambos lados: incluso si no está investigando una ventana de tiempo específica, la aplicación de filtros de tiempo en las tablas izquierda y derecha puede reducir el número de registros para comprobar y mejorar el `join` rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c969f-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="c969f-149">La consulta siguiente se aplica a ambas tablas de modo que solo `Timestamp > ago(1h)` une registros de la última hora:</span><span class="sxs-lookup"><span data-stu-id="c969f-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="c969f-150">**Usar sugerencias para el rendimiento:** use sugerencias con el operador para indicar al back-end que distribuya la carga al `join` ejecutar operaciones que consumen muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="c969f-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="c969f-151">Más información sobre las sugerencias de unión</span><span class="sxs-lookup"><span data-stu-id="c969f-151">Learn more about join hints</span></span>](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="c969f-152">Por ejemplo, **[la](/azure/data-explorer/kusto/query/shufflequery)** sugerencia aleatoria ayuda a mejorar el rendimiento de las consultas al unir tablas con una clave con una cardinalidad alta(una clave con muchos valores únicos), como la siguiente `AccountObjectId` consulta:</span><span class="sxs-lookup"><span data-stu-id="c969f-152">For example, the **[shuffle hint](/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="c969f-153">La **[sugerencia de difusión](/azure/data-explorer/kusto/query/broadcastjoin)** ayuda cuando la tabla izquierda es pequeña (hasta 100 000 registros) y la tabla derecha es extremadamente grande.</span><span class="sxs-lookup"><span data-stu-id="c969f-153">The **[broadcast hint](/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="c969f-154">Por ejemplo, la consulta siguiente está intentando unir algunos  correos electrónicos que tienen asuntos específicos con todos los mensajes que contienen vínculos en la `EmailUrlInfo` tabla:</span><span class="sxs-lookup"><span data-stu-id="c969f-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="c969f-155">Optimizar el `summarize` operador</span><span class="sxs-lookup"><span data-stu-id="c969f-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="c969f-156">El [operador de resumen](/azure/data-explorer/kusto/query/summarizeoperator) agrega el contenido de una tabla.</span><span class="sxs-lookup"><span data-stu-id="c969f-156">The [summarize operator](/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="c969f-157">Aplique estas sugerencias para optimizar las consultas que usan este operador.</span><span class="sxs-lookup"><span data-stu-id="c969f-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="c969f-158">**Buscar valores distintos:** en general, se usan `summarize` para buscar valores distintos que pueden ser repetitivos.</span><span class="sxs-lookup"><span data-stu-id="c969f-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="c969f-159">Puede ser innecesario usarlo para agregar columnas que no tienen valores repetitivos.</span><span class="sxs-lookup"><span data-stu-id="c969f-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="c969f-160">Aunque un solo correo electrónico puede formar parte  de varios eventos, el ejemplo siguiente no es un uso eficaz de porque un identificador de mensaje de red para un correo electrónico individual siempre viene con una dirección `summarize` de remitente única.</span><span class="sxs-lookup"><span data-stu-id="c969f-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="c969f-161">El operador se puede reemplazar fácilmente con , lo que produce potencialmente los mismos resultados `summarize` `project` mientras consume menos recursos:</span><span class="sxs-lookup"><span data-stu-id="c969f-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="c969f-162">El ejemplo siguiente es un uso más eficaz de porque puede haber varias instancias distintas de una dirección de remitente que envíe correo electrónico `summarize` a la misma dirección de destinatario.</span><span class="sxs-lookup"><span data-stu-id="c969f-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="c969f-163">Estas combinaciones son menos distintas y es probable que tengan duplicados.</span><span class="sxs-lookup"><span data-stu-id="c969f-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="c969f-164">**Barajar la consulta:** aunque se usa mejor en columnas con valores repetitivos, las mismas columnas también pueden tener una gran cardinalidad o un gran número `summarize` de valores únicos. </span><span class="sxs-lookup"><span data-stu-id="c969f-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="c969f-165">Al igual que el operador, también puede aplicar la sugerencia aleatoria con para distribuir la carga de procesamiento y mejorar potencialmente el rendimiento al operar en columnas `join` con una [](/azure/data-explorer/kusto/query/shufflequery) `summarize` cardinalidad alta.</span><span class="sxs-lookup"><span data-stu-id="c969f-165">Like the `join` operator, you can also apply the [shuffle hint](/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="c969f-166">La consulta siguiente se usa para contar una dirección de correo electrónico de destinatario distinta, que puede ejecutarse `summarize` en los cientos de miles de organizaciones grandes.</span><span class="sxs-lookup"><span data-stu-id="c969f-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="c969f-167">Para mejorar el rendimiento, incorpora `hint.shufflekey` :</span><span class="sxs-lookup"><span data-stu-id="c969f-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="c969f-168">Escenarios de consulta</span><span class="sxs-lookup"><span data-stu-id="c969f-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="c969f-169">Identificar procesos únicos con identificadores de proceso</span><span class="sxs-lookup"><span data-stu-id="c969f-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="c969f-170">Los Id. de proceso (PID) se reciclan en Windows y se reutilizan para los nuevos procesos.</span><span class="sxs-lookup"><span data-stu-id="c969f-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="c969f-171">Por sí solos, no pueden servir como identificadores únicos para procesos específicos.</span><span class="sxs-lookup"><span data-stu-id="c969f-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="c969f-172">Para obtener un identificador único para un proceso en un equipo específico, utilice el Id. de proceso conjuntamente con la hora de creación del proceso.</span><span class="sxs-lookup"><span data-stu-id="c969f-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="c969f-173">Cuando se une a los datos en torno a los procesos, debe incluir columnas para el identificador de la máquina (tanto `DeviceId` como `DeviceName`), el identificador de proceso (`ProcessId` o `InitiatingProcessId`) y la hora de creación del proceso (`ProcessCreationTime` o `InitiatingProcessCreationTime`).</span><span class="sxs-lookup"><span data-stu-id="c969f-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="c969f-174">En la siguiente consulta de ejemplo se buscan procesos que obtienen acceso a más de 10 direcciones IP por el puerto 445 (SMB), lo que podría buscar recursos compartidos de archivos.</span><span class="sxs-lookup"><span data-stu-id="c969f-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="c969f-175">Consulta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c969f-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="c969f-176">La consulta resume tanto en `InitiatingProcessId` como en `InitiatingProcessCreationTime` para que se vea un único proceso, sin mezclar varios procesos con el mismo Id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="c969f-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="c969f-177">Líneas de comandos de consulta</span><span class="sxs-lookup"><span data-stu-id="c969f-177">Query command lines</span></span>
<span data-ttu-id="c969f-178">Hay varias formas de crear una línea de comandos para llevar a cabo una tarea.</span><span class="sxs-lookup"><span data-stu-id="c969f-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="c969f-179">Por ejemplo, un atacante puede hacer referencia a un archivo de imagen sin una ruta de acceso, sin una extensión de archivo, con variables de entorno o con comillas.</span><span class="sxs-lookup"><span data-stu-id="c969f-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="c969f-180">El atacante también podría cambiar el orden de los parámetros o agregar varias comillas y espacios.</span><span class="sxs-lookup"><span data-stu-id="c969f-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="c969f-181">Para crear consultas más duraderas alrededor de las líneas de comandos, aplique los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="c969f-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="c969f-182">Identifique los procesos conocidos (como *net.exe* *opsexec.exe*) haciendo coincidir en los campos de nombre de archivo, en lugar de filtrar en la propia línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c969f-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="c969f-183">Analizar secciones de línea de comandos mediante [la función parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="c969f-183">Parse command-line sections using the [parse_command_line() function](/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="c969f-184">Al consultar argumentos de la línea de comandos, no busque una coincidencia exacta en varios argumentos no relacionados en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="c969f-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="c969f-185">En su lugar, use expresiones regulares o use operadores de contenedores separados múltiples.</span><span class="sxs-lookup"><span data-stu-id="c969f-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="c969f-186">Use coincidencias que no distinga mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c969f-186">Use case insensitive matches.</span></span> <span data-ttu-id="c969f-187">Por ejemplo, use `=~` , , y en lugar de , y `in~` `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="c969f-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="c969f-188">Para mitigar las técnicas de ofuscación de línea de comandos, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios consecutivos por un solo espacio.</span><span class="sxs-lookup"><span data-stu-id="c969f-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="c969f-189">Hay técnicas de ofuscación más complejas que requieren otros enfoques, pero estos retoques pueden ayudar a abordar los métodos comunes.</span><span class="sxs-lookup"><span data-stu-id="c969f-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="c969f-190">Los ejemplos siguientes muestran varias formas de crear  una consulta que busca el archivonet.exedetener el servicio de firewall "MpsSvc":</span><span class="sxs-lookup"><span data-stu-id="c969f-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="c969f-191">Ingerir datos de orígenes externos</span><span class="sxs-lookup"><span data-stu-id="c969f-191">Ingest data from external sources</span></span>
<span data-ttu-id="c969f-192">Para incorporar listas largas o tablas grandes a la consulta, use el operador [externaldata](/azure/data-explorer/kusto/query/externaldata-operator) para ingerir datos de un URI especificado.</span><span class="sxs-lookup"><span data-stu-id="c969f-192">To incorporate long lists or large tables into your query, use the [externaldata operator](/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="c969f-193">Puede obtener datos de archivos en TXT, CSV, JSON u [otros formatos](/azure/data-explorer/ingestion-supported-formats).</span><span class="sxs-lookup"><span data-stu-id="c969f-193">You can get data from files in TXT, CSV, JSON, or [other formats](/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="c969f-194">En el ejemplo siguiente se muestra cómo usar la extensa lista de hashes sha-256 de malware proporcionados por MalwareBazaar (abuse.ch) para comprobar los datos adjuntos de los correos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="c969f-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a><span data-ttu-id="c969f-195">Analizar cadenas</span><span class="sxs-lookup"><span data-stu-id="c969f-195">Parse strings</span></span>
<span data-ttu-id="c969f-196">Hay varias funciones que puede usar para controlar eficazmente las cadenas que necesitan análisis o conversión.</span><span class="sxs-lookup"><span data-stu-id="c969f-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="c969f-197">Cadena</span><span class="sxs-lookup"><span data-stu-id="c969f-197">String</span></span> | <span data-ttu-id="c969f-198">Función</span><span class="sxs-lookup"><span data-stu-id="c969f-198">Function</span></span> | <span data-ttu-id="c969f-199">Ejemplo de uso</span><span class="sxs-lookup"><span data-stu-id="c969f-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="c969f-200">Líneas de comandos</span><span class="sxs-lookup"><span data-stu-id="c969f-200">Command-lines</span></span> | [<span data-ttu-id="c969f-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="c969f-201">parse_command_line()</span></span>](/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="c969f-202">Extraiga el comando y todos los argumentos.</span><span class="sxs-lookup"><span data-stu-id="c969f-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="c969f-203">Paths</span><span class="sxs-lookup"><span data-stu-id="c969f-203">Paths</span></span> | [<span data-ttu-id="c969f-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="c969f-204">parse_path()</span></span>](/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="c969f-205">Extraiga las secciones de una ruta de acceso de archivo o carpeta.</span><span class="sxs-lookup"><span data-stu-id="c969f-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="c969f-206">Números de versión</span><span class="sxs-lookup"><span data-stu-id="c969f-206">Version numbers</span></span> | [<span data-ttu-id="c969f-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="c969f-207">parse_version()</span></span>](/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="c969f-208">Deconstruir un número de versión con hasta cuatro secciones y hasta ocho caracteres por sección.</span><span class="sxs-lookup"><span data-stu-id="c969f-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="c969f-209">Use los datos analizados para comparar la antigüedad de la versión.</span><span class="sxs-lookup"><span data-stu-id="c969f-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="c969f-210">Direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="c969f-210">IPv4 addresses</span></span> | [<span data-ttu-id="c969f-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="c969f-211">parse_ipv4()</span></span>](/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="c969f-212">Convertir una dirección IPv4 en un entero largo.</span><span class="sxs-lookup"><span data-stu-id="c969f-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="c969f-213">Para comparar direcciones IPv4 sin convertirlas, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="c969f-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="c969f-214">Direcciones IPv6</span><span class="sxs-lookup"><span data-stu-id="c969f-214">IPv6 addresses</span></span> | [<span data-ttu-id="c969f-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="c969f-215">parse_ipv6()</span></span>](/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="c969f-216">Convierta una dirección IPv4 o IPv6 en la notación IPv6 canónica.</span><span class="sxs-lookup"><span data-stu-id="c969f-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="c969f-217">Para comparar direcciones IPv6, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="c969f-217">To compare IPv6 addresses, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="c969f-218">Para obtener información sobre todas las funciones de análisis admitidas, [lea acerca de las funciones de cadena kusto](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="c969f-218">To learn about all supported parsing functions, [read about Kusto string functions](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="c969f-219">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c969f-219">Related topics</span></span>
- [<span data-ttu-id="c969f-220">Documentación del idioma de consulta de Kusto</span><span class="sxs-lookup"><span data-stu-id="c969f-220">Kusto query language documentation</span></span>](/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="c969f-221">Parámetros de uso y cuotas</span><span class="sxs-lookup"><span data-stu-id="c969f-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="c969f-222">Controlar errores de búsqueda avanzados</span><span class="sxs-lookup"><span data-stu-id="c969f-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="c969f-223">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="c969f-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c969f-224">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c969f-224">Learn the query language</span></span>](advanced-hunting-query-language.md)