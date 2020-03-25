---
title: Mejores prácticas de búsqueda avanzada de Protección contra amenazas de Microsoft
description: Obtenga información sobre cómo crear consultas de búsqueda de amenazas rápidas, eficientes y sin errores al usar la búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, evitar tiempo de espera, líneas de comandos, identificador de proceso
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
ms.openlocfilehash: 9d7f6ee67e231ce7aa9bce1decc4de2f2d5a6d41
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929509"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="0b080-104">Prácticas recomendadas para la consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="0b080-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="0b080-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0b080-105">**Applies to:**</span></span>
- <span data-ttu-id="0b080-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0b080-106">Microsoft Threat Protection</span></span>



## <a name="optimize-query-performance"></a><span data-ttu-id="0b080-107">Optimizar el rendimiento de las consultas</span><span class="sxs-lookup"><span data-stu-id="0b080-107">Optimize query performance</span></span>
<span data-ttu-id="0b080-108">Aplique estas recomendaciones para obtener resultados más rápidamente y evite tiempos de espera al ejecutar consultas complejas:</span><span class="sxs-lookup"><span data-stu-id="0b080-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="0b080-109">Al probar nuevas consultas, utilice siempre `limit` para evitar conjuntos de resultados extremadamente grandes.</span><span class="sxs-lookup"><span data-stu-id="0b080-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="0b080-110">También puede evaluar inicialmente el tamaño del conjunto de resultados con `count`.</span><span class="sxs-lookup"><span data-stu-id="0b080-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="0b080-111">Use los filtros de tiempo primero.</span><span class="sxs-lookup"><span data-stu-id="0b080-111">Use time filters first.</span></span> <span data-ttu-id="0b080-112">Idealmente, limite sus consultas a esos días.</span><span class="sxs-lookup"><span data-stu-id="0b080-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="0b080-113">Se deben quitar la mayoría de los datos del comienzo de la consulta, justo después del filtro de hora.</span><span class="sxs-lookup"><span data-stu-id="0b080-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="0b080-114">Use el operador `has` a través de `contains` al buscar tokens completos.</span><span class="sxs-lookup"><span data-stu-id="0b080-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="0b080-115">Busque en una columna específica en lugar de ejecutar búsquedas de texto completo en todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="0b080-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="0b080-116">Cuando se unen tablas, primero debe especificarse la tabla con menos filas.</span><span class="sxs-lookup"><span data-stu-id="0b080-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="0b080-117">`project` solo las columnas necesarias de las tablas que ha unido.</span><span class="sxs-lookup"><span data-stu-id="0b080-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="0b080-118">Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="0b080-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="0b080-119">Sugerencias y dificultades de la consulta</span><span class="sxs-lookup"><span data-stu-id="0b080-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="0b080-120">Consultas con Id. de proceso</span><span class="sxs-lookup"><span data-stu-id="0b080-120">Queries with process IDs</span></span>
<span data-ttu-id="0b080-121">Los Id. de proceso (PID) se reciclan en Windows y se reutilizan para los nuevos procesos.</span><span class="sxs-lookup"><span data-stu-id="0b080-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="0b080-122">Por sí solos, no pueden servir como identificadores únicos para procesos específicos.</span><span class="sxs-lookup"><span data-stu-id="0b080-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="0b080-123">Para obtener un identificador único para un proceso en un equipo específico, utilice el Id. de proceso conjuntamente con la hora de creación del proceso.</span><span class="sxs-lookup"><span data-stu-id="0b080-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="0b080-124">Cuando se une a los datos en torno a los procesos, debe incluir columnas para el identificador de la máquina (tanto `DeviceId` como `DeviceName`), el identificador de proceso (`ProcessId` o `InitiatingProcessId`) y la hora de creación del proceso (`ProcessCreationTime` o `InitiatingProcessCreationTime`).</span><span class="sxs-lookup"><span data-stu-id="0b080-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="0b080-125">En la siguiente consulta de ejemplo se buscan procesos que obtienen acceso a más de 10 direcciones IP por el puerto 445 (SMB), lo que podría buscar recursos compartidos de archivos.</span><span class="sxs-lookup"><span data-stu-id="0b080-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="0b080-126">Consulta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0b080-126">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="0b080-127">La consulta resume tanto en `InitiatingProcessId` como en `InitiatingProcessCreationTime` para que se vea un único proceso, sin mezclar varios procesos con el mismo Id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="0b080-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="0b080-128">Consultas con líneas de comandos</span><span class="sxs-lookup"><span data-stu-id="0b080-128">Queries with command lines</span></span>

<span data-ttu-id="0b080-129">Las líneas de comandos pueden variar.</span><span class="sxs-lookup"><span data-stu-id="0b080-129">Command lines can vary.</span></span> <span data-ttu-id="0b080-130">Cuando sea posible, filtre por nombres de archivo y realice la coincidencia aproximada.</span><span class="sxs-lookup"><span data-stu-id="0b080-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="0b080-131">Hay varias formas de crear una línea de comandos para llevar a cabo una tarea.</span><span class="sxs-lookup"><span data-stu-id="0b080-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="0b080-132">Por ejemplo, un atacante puede hacer referencia a un archivo de imagen con o sin una ruta de acceso, sin una extensión de archivo, mediante variables de entorno, o entre comillas.</span><span class="sxs-lookup"><span data-stu-id="0b080-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="0b080-133">Además, el atacante también podría cambiar el orden de los parámetros o agregar varias comillas y espacios.</span><span class="sxs-lookup"><span data-stu-id="0b080-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="0b080-134">Para crear consultas más duraderas mediante líneas de comandos, aplique los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0b080-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="0b080-135">Identifique los procesos conocidos (como, por ejemplo, *net.exe* o *psexec.exe*), en lugar de filtrarlos en el campo de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0b080-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="0b080-136">Al consultar argumentos de la línea de comandos, no busque una coincidencia exacta en varios argumentos no relacionados en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="0b080-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="0b080-137">En su lugar, use expresiones regulares o use operadores de contenedores separados múltiples.</span><span class="sxs-lookup"><span data-stu-id="0b080-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="0b080-138">Use coincidencias que no distinga mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0b080-138">Use case insensitive matches.</span></span> <span data-ttu-id="0b080-139">Por ejemplo, use `=~`, `in~` y `contains` en lugar de `==`, `in` y `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="0b080-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="0b080-140">Para mitigar las técnicas de ofuscación de línea de comandos de DOS, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios seguidos por un solo espacio.</span><span class="sxs-lookup"><span data-stu-id="0b080-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="0b080-141">Tenga en cuenta que existen técnicas de ofuscación de DOS más complejas que requieren otras soluciones, pero pueden ayudar a solucionar los más comunes.</span><span class="sxs-lookup"><span data-stu-id="0b080-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="0b080-142">En los ejemplos siguientes se muestran varias formas de crear una consulta que busque el archivo *net.exe* para detener el servicio Firewall de Windows Defender:</span><span class="sxs-lookup"><span data-stu-id="0b080-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="0b080-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0b080-143">Related topics</span></span>
- [<span data-ttu-id="0b080-144">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="0b080-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0b080-145">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="0b080-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0b080-146">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="0b080-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="0b080-147">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="0b080-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0b080-148">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0b080-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0b080-149">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="0b080-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
