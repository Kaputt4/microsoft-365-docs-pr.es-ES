---
title: Procedimientos recomendados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Obtenga información sobre cómo crear consultas de búsqueda de amenazas rápidas, eficientes y sin errores con la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, esquema, kusto, evitar tiempo de espera, líneas de comandos, id. de proceso, optimizar, procedimiento recomendado, analizar, unirse, resumir
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
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928479"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="3c146-104">Prácticas recomendadas para la consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3c146-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3c146-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3c146-105">**Applies to:**</span></span>
- <span data-ttu-id="3c146-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c146-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3c146-107">Aplique estas recomendaciones para obtener resultados más rápidos y evitar tiempos de espera mientras ejecuta consultas complejas.</span><span class="sxs-lookup"><span data-stu-id="3c146-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="3c146-108">Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="3c146-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="3c146-109">Comprender las cuotas de recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="3c146-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="3c146-110">Según su tamaño, cada inquilino tiene acceso a una cantidad establecida de recursos de CPU asignados para ejecutar consultas de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="3c146-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="3c146-111">Para obtener información detallada acerca de los distintos límites de servicio, [lea acerca de las cuotas de búsqueda avanzada y los parámetros de uso.](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="3c146-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="3c146-112">Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar las instrucciones de optimización de este artículo para minimizar la interrupción resultante del exceso de cuotas o parámetros de uso.</span><span class="sxs-lookup"><span data-stu-id="3c146-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="3c146-113">Sugerencias generales de optimización</span><span class="sxs-lookup"><span data-stu-id="3c146-113">General optimization tips</span></span>

- <span data-ttu-id="3c146-114">**Tamaño de las consultas nuevas:** si sospecha que una consulta devolverá un conjunto de resultados grande, evalúe primero con el operador [de recuento.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)</span><span class="sxs-lookup"><span data-stu-id="3c146-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="3c146-115">Use [el límite](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) o su sinónimo para evitar grandes conjuntos de `take` resultados.</span><span class="sxs-lookup"><span data-stu-id="3c146-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="3c146-116">Aplicar filtros de forma anticipada: aplique filtros de tiempo y otros filtros para reducir el conjunto de datos, especialmente antes de usar funciones de transformación y análisis, como [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)o [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="3c146-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="3c146-117">En el ejemplo siguiente, se usa la función de análisis [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) después de que los operadores de filtrado han reducido el número de registros.</span><span class="sxs-lookup"><span data-stu-id="3c146-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="3c146-118">**Contiene latidos:** para evitar buscar subcadenas en palabras innecesariamente, use el `has` operador en lugar de `contains` .</span><span class="sxs-lookup"><span data-stu-id="3c146-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="3c146-119">Más información sobre los operadores de cadena</span><span class="sxs-lookup"><span data-stu-id="3c146-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="3c146-120">**Buscar en columnas específicas:** busque en una columna específica en lugar de ejecutar búsquedas de texto completo en todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="3c146-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="3c146-121">No se usa `*` para comprobar todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="3c146-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="3c146-122">**Distingue mayúsculas de minúsculas para la** velocidad: las búsquedas que distinguen mayúsculas de minúsculas son más específicas y, por lo general, más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="3c146-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="3c146-123">Los nombres de operadores de [cadena](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)que distinguen mayúsculas de minúsculas, `has_cs` como y , generalmente terminan con `contains_cs` `_cs` .</span><span class="sxs-lookup"><span data-stu-id="3c146-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="3c146-124">También puede usar el operador que distingue mayúsculas de minúsculas en `==` lugar de `=~` .</span><span class="sxs-lookup"><span data-stu-id="3c146-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="3c146-125">**Analizar, no extraer:** siempre que sea [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) posible, use el operador de análisis o una función de análisis [como parse_json().](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)</span><span class="sxs-lookup"><span data-stu-id="3c146-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="3c146-126">Evite el `matches regex` operador de cadena o la función [extract(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)que usan expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="3c146-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="3c146-127">Reserve el uso de expresiones regulares para escenarios más complejos.</span><span class="sxs-lookup"><span data-stu-id="3c146-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="3c146-128">Más información sobre el análisis de funciones</span><span class="sxs-lookup"><span data-stu-id="3c146-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="3c146-129">**Tablas de filtro no expresiones:** no filtre en una columna calculada si puede filtrar por una columna de tabla.</span><span class="sxs-lookup"><span data-stu-id="3c146-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="3c146-130">**Sin términos de tres caracteres:** evite comparar o filtrar usando términos con tres caracteres o menos.</span><span class="sxs-lookup"><span data-stu-id="3c146-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="3c146-131">Estos términos no se indizan y su coincidencia requerirá más recursos.</span><span class="sxs-lookup"><span data-stu-id="3c146-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="3c146-132">**Proyecto selectivamente:** haga que los resultados sean más fáciles de entender proyectando solo las columnas que necesita.</span><span class="sxs-lookup"><span data-stu-id="3c146-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="3c146-133">La proyección de columnas específicas antes de ejecutar [la combinación](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) u operaciones similares también ayuda a mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="3c146-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="3c146-134">Optimizar el `join` operador</span><span class="sxs-lookup"><span data-stu-id="3c146-134">Optimize the `join` operator</span></span>
<span data-ttu-id="3c146-135">El [operador join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) combina filas de dos tablas mediante valores coincidentes en columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="3c146-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="3c146-136">Aplique estas sugerencias para optimizar las consultas que usan este operador.</span><span class="sxs-lookup"><span data-stu-id="3c146-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="3c146-137">**Tabla más pequeña a la izquierda:** el operador hace que los registros de la tabla del lado izquierdo de la instrucción join coincidan con `join` los registros de la derecha.</span><span class="sxs-lookup"><span data-stu-id="3c146-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="3c146-138">Al tener la tabla más pequeña a la izquierda, será necesario hacer coincidir menos registros, lo que acelerará la consulta.</span><span class="sxs-lookup"><span data-stu-id="3c146-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="3c146-139">En la tabla siguiente, se reduce la tabla izquierda para cubrir solo tres dispositivos específicos antes de `DeviceLogonEvents` unirse por `IdentityLogonEvents` SID de cuenta.</span><span class="sxs-lookup"><span data-stu-id="3c146-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="3c146-140">**Use** el tipo de combinación [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) interna: el tipo de combinación predeterminado o [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplica las filas de la tabla izquierda por la tecla join antes de devolver una fila para cada coincidencia a la tabla derecha.</span><span class="sxs-lookup"><span data-stu-id="3c146-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="3c146-141">Si la tabla izquierda tiene varias filas con el mismo valor para la clave, dichas filas se desduplicarán para dejar una sola fila aleatoria `join` para cada valor único.</span><span class="sxs-lookup"><span data-stu-id="3c146-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="3c146-142">Este comportamiento predeterminado puede dejar fuera información importante de la tabla izquierda que puede proporcionar información útil.</span><span class="sxs-lookup"><span data-stu-id="3c146-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="3c146-143">Por ejemplo, la consulta siguiente solo mostrará un correo electrónico que contiene datos adjuntos concretos, incluso si el mismo archivo adjunto se envió con varios mensajes de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="3c146-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="3c146-144">Para solucionar esta limitación, aplicamos el tipo de combinación interna especificando que se muestren todas las filas de la tabla izquierda con valores coincidentes a la [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) `kind=inner` derecha:</span><span class="sxs-lookup"><span data-stu-id="3c146-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="3c146-145">**Unir registros desde una ventana de tiempo:** al investigar eventos de seguridad, los analistas buscan eventos relacionados que se producen alrededor del mismo período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3c146-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="3c146-146">Aplicar el mismo enfoque al usar también `join` beneficia el rendimiento al reducir el número de registros que se deben comprobar.</span><span class="sxs-lookup"><span data-stu-id="3c146-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="3c146-147">La consulta siguiente comprueba si hay eventos de inicio de sesión en un plazo de 30 minutos desde la recepción de un archivo malintencionado:</span><span class="sxs-lookup"><span data-stu-id="3c146-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="3c146-148">**Aplicar** filtros de tiempo en ambos lados: incluso si no está investigando una ventana de tiempo específica, la aplicación de filtros de tiempo en las tablas izquierda y derecha puede reducir el número de registros para comprobar y mejorar el `join` rendimiento.</span><span class="sxs-lookup"><span data-stu-id="3c146-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="3c146-149">La consulta siguiente se aplica a ambas tablas para que solo `Timestamp > ago(1h)` una registros de la última hora:</span><span class="sxs-lookup"><span data-stu-id="3c146-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="3c146-150">**Usa sugerencias para el rendimiento:** usa sugerencias con el operador para indicar al back-end que distribuya la carga al ejecutar operaciones `join` que consumen muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="3c146-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="3c146-151">Más información sobre las sugerencias de unión</span><span class="sxs-lookup"><span data-stu-id="3c146-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="3c146-152">Por ejemplo, **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** la sugerencia de aleatorio ayuda a mejorar el rendimiento de las consultas al unir tablas mediante una clave con una cardinalidad alta (una clave con muchos valores únicos), como la de la `AccountObjectId` consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c146-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="3c146-153">La **[sugerencia de difusión](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** ayuda cuando la tabla izquierda es pequeña (hasta 100.000 registros) y la tabla derecha es extremadamente grande.</span><span class="sxs-lookup"><span data-stu-id="3c146-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="3c146-154">Por ejemplo, la consulta siguiente está intentando unirse  a algunos correos electrónicos que tienen asuntos específicos con todos los mensajes que contienen vínculos en la `EmailUrlInfo` tabla:</span><span class="sxs-lookup"><span data-stu-id="3c146-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="3c146-155">Optimizar el `summarize` operador</span><span class="sxs-lookup"><span data-stu-id="3c146-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="3c146-156">El [operador de resumen](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) agrega el contenido de una tabla.</span><span class="sxs-lookup"><span data-stu-id="3c146-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="3c146-157">Aplique estas sugerencias para optimizar las consultas que usan este operador.</span><span class="sxs-lookup"><span data-stu-id="3c146-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="3c146-158">**Buscar valores distintos:** en general, se usan para buscar valores `summarize` distintos que pueden ser repetitivos.</span><span class="sxs-lookup"><span data-stu-id="3c146-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="3c146-159">No es necesario usarlo para agregar columnas que no tienen valores repetitivos.</span><span class="sxs-lookup"><span data-stu-id="3c146-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="3c146-160">Aunque un solo correo electrónico puede formar parte  de varios eventos, el siguiente ejemplo no es un uso eficaz porque un identificador de mensaje de red para un correo electrónico individual siempre incluye una dirección `summarize` de remitente única.</span><span class="sxs-lookup"><span data-stu-id="3c146-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="3c146-161">El operador se puede reemplazar fácilmente por , lo que produce potencialmente los mismos resultados `summarize` mientras consume menos `project` recursos:</span><span class="sxs-lookup"><span data-stu-id="3c146-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="3c146-162">El siguiente ejemplo es un uso más eficaz porque puede haber varias instancias distintas de una dirección de remitente que envía correo electrónico `summarize` a la misma dirección de destinatario.</span><span class="sxs-lookup"><span data-stu-id="3c146-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="3c146-163">Estas combinaciones son menos distintas y es probable que tengan duplicados.</span><span class="sxs-lookup"><span data-stu-id="3c146-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="3c146-164">**Aleatorio de la consulta:** aunque se usa mejor en columnas con valores repetitivos, las mismas columnas también pueden tener una gran cardinalidad o un gran número `summarize` de valores  únicos.</span><span class="sxs-lookup"><span data-stu-id="3c146-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="3c146-165">Al igual que el operador, también puedes aplicar la sugerencia de reproducción aleatoria para distribuir la carga de procesamiento y mejorar potencialmente el rendimiento cuando se opera en columnas `join` con una [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` cardinalidad alta.</span><span class="sxs-lookup"><span data-stu-id="3c146-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="3c146-166">La consulta siguiente se usa para contar una dirección de correo electrónico de destinatario distinta, que puede ejecutarse `summarize` en los cientos de miles de organizaciones grandes.</span><span class="sxs-lookup"><span data-stu-id="3c146-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="3c146-167">Para mejorar el rendimiento, `hint.shufflekey` incorpora:</span><span class="sxs-lookup"><span data-stu-id="3c146-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="3c146-168">Escenarios de consulta</span><span class="sxs-lookup"><span data-stu-id="3c146-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="3c146-169">Identificar procesos únicos con identificadores de proceso</span><span class="sxs-lookup"><span data-stu-id="3c146-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="3c146-170">Los Id. de proceso (PID) se reciclan en Windows y se reutilizan para los nuevos procesos.</span><span class="sxs-lookup"><span data-stu-id="3c146-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="3c146-171">Por sí solos, no pueden servir como identificadores únicos para procesos específicos.</span><span class="sxs-lookup"><span data-stu-id="3c146-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="3c146-172">Para obtener un identificador único para un proceso en un equipo específico, utilice el Id. de proceso conjuntamente con la hora de creación del proceso.</span><span class="sxs-lookup"><span data-stu-id="3c146-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="3c146-173">Cuando se une a los datos en torno a los procesos, debe incluir columnas para el identificador de la máquina (tanto `DeviceId` como `DeviceName`), el identificador de proceso (`ProcessId` o `InitiatingProcessId`) y la hora de creación del proceso (`ProcessCreationTime` o `InitiatingProcessCreationTime`).</span><span class="sxs-lookup"><span data-stu-id="3c146-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="3c146-174">En la siguiente consulta de ejemplo se buscan procesos que obtienen acceso a más de 10 direcciones IP por el puerto 445 (SMB), lo que podría buscar recursos compartidos de archivos.</span><span class="sxs-lookup"><span data-stu-id="3c146-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="3c146-175">Consulta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3c146-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="3c146-176">La consulta resume tanto en `InitiatingProcessId` como en `InitiatingProcessCreationTime` para que se vea un único proceso, sin mezclar varios procesos con el mismo Id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="3c146-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="3c146-177">Líneas de comandos de consulta</span><span class="sxs-lookup"><span data-stu-id="3c146-177">Query command lines</span></span>
<span data-ttu-id="3c146-178">Hay varias formas de crear una línea de comandos para llevar a cabo una tarea.</span><span class="sxs-lookup"><span data-stu-id="3c146-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="3c146-179">Por ejemplo, un atacante podría hacer referencia a un archivo de imagen sin una ruta de acceso, sin una extensión de archivo, usando variables de entorno o entre comillas.</span><span class="sxs-lookup"><span data-stu-id="3c146-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="3c146-180">El atacante también podría cambiar el orden de los parámetros o agregar varias comillas y espacios.</span><span class="sxs-lookup"><span data-stu-id="3c146-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="3c146-181">Para crear consultas más duraderas en torno a las líneas de comandos, aplique los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="3c146-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="3c146-182">Identifique los procesos conocidos (como *net.exe* o *psexec.exe)* haciendo coincidir en los campos de nombre de archivo, en lugar de filtrarlos en la propia línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3c146-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="3c146-183">Analizar secciones de línea de comandos mediante [la parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="3c146-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="3c146-184">Al consultar argumentos de la línea de comandos, no busque una coincidencia exacta en varios argumentos no relacionados en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="3c146-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="3c146-185">En su lugar, use expresiones regulares o use operadores de contenedores separados múltiples.</span><span class="sxs-lookup"><span data-stu-id="3c146-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="3c146-186">Use coincidencias que no distinga mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3c146-186">Use case insensitive matches.</span></span> <span data-ttu-id="3c146-187">Por ejemplo, use `=~` , y en lugar de , y `in~` `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="3c146-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="3c146-188">Para mitigar las técnicas de ofuscación de la línea de comandos, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios consecutivos por un solo espacio.</span><span class="sxs-lookup"><span data-stu-id="3c146-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="3c146-189">Existen técnicas de ofuscación más complejas que requieren otros enfoques, pero estos retoques pueden ayudar a abordar los más comunes.</span><span class="sxs-lookup"><span data-stu-id="3c146-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="3c146-190">Los ejemplos siguientes muestran varias formas de crear una consulta que busca el archivo *net.exe* para detener el servicio de firewall "MpsSvc":</span><span class="sxs-lookup"><span data-stu-id="3c146-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="3c146-191">Ingerir datos de orígenes externos</span><span class="sxs-lookup"><span data-stu-id="3c146-191">Ingest data from external sources</span></span>
<span data-ttu-id="3c146-192">Para incorporar listas largas o tablas grandes en la consulta, use el operador [externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) para ingerir datos de un URI especificado.</span><span class="sxs-lookup"><span data-stu-id="3c146-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="3c146-193">Puede obtener datos de archivos en formato TXT, CSV, JSON u [otros formatos.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="3c146-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="3c146-194">En el ejemplo siguiente se muestra cómo puede usar la amplia lista de hash sha-256 de malware proporcionado por MalwareBazaar (abuse.ch) para comprobar los datos adjuntos de los correos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="3c146-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a><span data-ttu-id="3c146-195">Analizar cadenas</span><span class="sxs-lookup"><span data-stu-id="3c146-195">Parse strings</span></span>
<span data-ttu-id="3c146-196">Hay varias funciones que puedes usar para controlar de forma eficaz las cadenas que necesitan análisis o conversión.</span><span class="sxs-lookup"><span data-stu-id="3c146-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="3c146-197">Cadena</span><span class="sxs-lookup"><span data-stu-id="3c146-197">String</span></span> | <span data-ttu-id="3c146-198">Función</span><span class="sxs-lookup"><span data-stu-id="3c146-198">Function</span></span> | <span data-ttu-id="3c146-199">Ejemplo de uso</span><span class="sxs-lookup"><span data-stu-id="3c146-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="3c146-200">Líneas de comandos</span><span class="sxs-lookup"><span data-stu-id="3c146-200">Command-lines</span></span> | [<span data-ttu-id="3c146-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="3c146-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="3c146-202">Extraiga el comando y todos los argumentos.</span><span class="sxs-lookup"><span data-stu-id="3c146-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="3c146-203">Paths</span><span class="sxs-lookup"><span data-stu-id="3c146-203">Paths</span></span> | [<span data-ttu-id="3c146-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="3c146-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="3c146-205">Extraiga las secciones de una ruta de acceso de archivo o carpeta.</span><span class="sxs-lookup"><span data-stu-id="3c146-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="3c146-206">Números de versión</span><span class="sxs-lookup"><span data-stu-id="3c146-206">Version numbers</span></span> | [<span data-ttu-id="3c146-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="3c146-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="3c146-208">Deconstruir un número de versión con hasta cuatro secciones y hasta ocho caracteres por sección.</span><span class="sxs-lookup"><span data-stu-id="3c146-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="3c146-209">Use los datos analizados para comparar la antigüedad de la versión.</span><span class="sxs-lookup"><span data-stu-id="3c146-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="3c146-210">Direcciones IPv4</span><span class="sxs-lookup"><span data-stu-id="3c146-210">IPv4 addresses</span></span> | [<span data-ttu-id="3c146-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="3c146-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="3c146-212">Convertir una dirección IPv4 en un entero largo.</span><span class="sxs-lookup"><span data-stu-id="3c146-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="3c146-213">Para comparar direcciones IPv4 sin convertirlas, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="3c146-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="3c146-214">Direcciones IPv6</span><span class="sxs-lookup"><span data-stu-id="3c146-214">IPv6 addresses</span></span> | [<span data-ttu-id="3c146-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="3c146-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="3c146-216">Convierte una dirección IPv4 o IPv6 en la notación IPv6 canónica.</span><span class="sxs-lookup"><span data-stu-id="3c146-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="3c146-217">Para comparar direcciones IPv6, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="3c146-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="3c146-218">Para obtener información sobre todas las funciones de análisis admitidas, [lea acerca de las funciones de cadena de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="3c146-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="3c146-219">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3c146-219">Related topics</span></span>
- [<span data-ttu-id="3c146-220">Documentación del lenguaje de consulta de Kusto</span><span class="sxs-lookup"><span data-stu-id="3c146-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="3c146-221">Parámetros de uso y cuotas</span><span class="sxs-lookup"><span data-stu-id="3c146-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="3c146-222">Controlar errores de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3c146-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="3c146-223">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3c146-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3c146-224">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="3c146-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
