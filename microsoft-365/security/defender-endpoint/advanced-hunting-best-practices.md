---
title: Consultar procedimientos recomendados para la búsqueda avanzada
description: Obtenga información sobre cómo crear consultas de búsqueda de amenazas rápidas, eficientes y sin errores al usar la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, detecciones personalizadas, esquema, kusto, evitar el tiempo de espera, líneas de comandos, id. de proceso
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072432"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="fae13-104">Prácticas recomendadas para la consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="fae13-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fae13-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="fae13-105">**Applies to:**</span></span>
- [<span data-ttu-id="fae13-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="fae13-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="fae13-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="fae13-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fae13-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="fae13-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="fae13-109">Optimizar el rendimiento de las consultas</span><span class="sxs-lookup"><span data-stu-id="fae13-109">Optimize query performance</span></span>

<span data-ttu-id="fae13-110">Aplique estas recomendaciones para obtener resultados más rápido y evitar tiempos de espera mientras ejecuta consultas complejas.</span><span class="sxs-lookup"><span data-stu-id="fae13-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="fae13-111">Al probar nuevas consultas, utilice siempre `limit` para evitar conjuntos de resultados extremadamente grandes.</span><span class="sxs-lookup"><span data-stu-id="fae13-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="fae13-112">También puede evaluar inicialmente el tamaño del conjunto de resultados con `count`.</span><span class="sxs-lookup"><span data-stu-id="fae13-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="fae13-113">Use los filtros de tiempo primero.</span><span class="sxs-lookup"><span data-stu-id="fae13-113">Use time filters first.</span></span> <span data-ttu-id="fae13-114">Lo ideal es limitar las consultas a siete días.</span><span class="sxs-lookup"><span data-stu-id="fae13-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="fae13-115">Se deben quitar la mayoría de los datos del comienzo de la consulta, justo después del filtro de hora.</span><span class="sxs-lookup"><span data-stu-id="fae13-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="fae13-116">Use el operador `has` a través de `contains` al buscar tokens completos.</span><span class="sxs-lookup"><span data-stu-id="fae13-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="fae13-117">Busque en una columna específica en lugar de ejecutar búsquedas de texto completo en todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="fae13-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="fae13-118">Cuando se unen tablas, primero debe especificarse la tabla con menos filas.</span><span class="sxs-lookup"><span data-stu-id="fae13-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="fae13-119">`project` solo las columnas necesarias de las tablas que ha unido.</span><span class="sxs-lookup"><span data-stu-id="fae13-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="fae13-120">Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="fae13-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="fae13-121">Sugerencias y dificultades de la consulta</span><span class="sxs-lookup"><span data-stu-id="fae13-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="fae13-122">Consultas con Id. de proceso</span><span class="sxs-lookup"><span data-stu-id="fae13-122">Queries with process IDs</span></span>

<span data-ttu-id="fae13-123">Los Id. de proceso (PID) se reciclan en Windows y se reutilizan para los nuevos procesos.</span><span class="sxs-lookup"><span data-stu-id="fae13-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="fae13-124">Por sí solos, no pueden servir como identificadores únicos para procesos específicos.</span><span class="sxs-lookup"><span data-stu-id="fae13-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="fae13-125">Para obtener un identificador único para un proceso en un dispositivo específico, usa el identificador del proceso junto con el tiempo de creación del proceso.</span><span class="sxs-lookup"><span data-stu-id="fae13-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="fae13-126">Al unir o resumir datos alrededor de procesos, incluya columnas para el identificador del dispositivo (o ), el identificador de proceso ( o ) y el tiempo de creación `DeviceId` del proceso ( o `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` ).</span><span class="sxs-lookup"><span data-stu-id="fae13-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="fae13-127">En la siguiente consulta de ejemplo se buscan procesos que obtienen acceso a más de 10 direcciones IP por el puerto 445 (SMB), lo que podría buscar recursos compartidos de archivos.</span><span class="sxs-lookup"><span data-stu-id="fae13-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="fae13-128">La consulta resume tanto en `InitiatingProcessId` como en `InitiatingProcessCreationTime` para que se vea un único proceso, sin mezclar varios procesos con el mismo Id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="fae13-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="fae13-129">Consultas con líneas de comandos</span><span class="sxs-lookup"><span data-stu-id="fae13-129">Queries with command lines</span></span>

<span data-ttu-id="fae13-130">Las líneas de comandos pueden variar.</span><span class="sxs-lookup"><span data-stu-id="fae13-130">Command lines can vary.</span></span> <span data-ttu-id="fae13-131">Cuando sea posible, filtre por nombres de archivo y realice la coincidencia aproximada.</span><span class="sxs-lookup"><span data-stu-id="fae13-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="fae13-132">Hay varias formas de crear una línea de comandos para llevar a cabo una tarea.</span><span class="sxs-lookup"><span data-stu-id="fae13-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="fae13-133">Por ejemplo, un atacante puede hacer referencia a un archivo de imagen con o sin una ruta de acceso, sin una extensión de archivo, mediante variables de entorno, o entre comillas.</span><span class="sxs-lookup"><span data-stu-id="fae13-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="fae13-134">Además, el atacante también podría cambiar el orden de los parámetros o agregar varias comillas y espacios.</span><span class="sxs-lookup"><span data-stu-id="fae13-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="fae13-135">Para crear consultas más duraderas mediante líneas de comandos, aplique los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fae13-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="fae13-136">Identifique los procesos conocidos (como, por ejemplo, *net.exe* o *psexec.exe*), en lugar de filtrarlos en el campo de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fae13-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="fae13-137">Al consultar argumentos de la línea de comandos, no busque una coincidencia exacta en varios argumentos no relacionados en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="fae13-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="fae13-138">En su lugar, use expresiones regulares o use operadores de contenedores separados múltiples.</span><span class="sxs-lookup"><span data-stu-id="fae13-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="fae13-139">Use coincidencias que no distinga mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fae13-139">Use case insensitive matches.</span></span> <span data-ttu-id="fae13-140">Por ejemplo, use `=~` , y en lugar de , `in~` `contains` `==` `in` y `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="fae13-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="fae13-141">Para mitigar las técnicas de ofuscación de línea de comandos de DOS, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios seguidos por un solo espacio.</span><span class="sxs-lookup"><span data-stu-id="fae13-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="fae13-142">Tenga en cuenta que existen técnicas de ofuscación de DOS más complejas que requieren otras soluciones, pero pueden ayudar a solucionar los más comunes.</span><span class="sxs-lookup"><span data-stu-id="fae13-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="fae13-143">En los ejemplos siguientes se muestran varias formas de crear una consulta que busque el archivo *net.exe* para detener el servicio Firewall de Windows Defender:</span><span class="sxs-lookup"><span data-stu-id="fae13-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

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

> <span data-ttu-id="fae13-144">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="fae13-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fae13-145">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="fae13-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="fae13-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fae13-146">Related topics</span></span>

- [<span data-ttu-id="fae13-147">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="fae13-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fae13-148">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="fae13-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fae13-149">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="fae13-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="fae13-150">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="fae13-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="fae13-151">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="fae13-151">Custom detections overview</span></span>](overview-custom-detections.md)
