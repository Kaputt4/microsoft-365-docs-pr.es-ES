---
title: Microsoft 365 API de búsqueda avanzada de Defender
description: Obtenga información sobre cómo ejecutar consultas avanzadas de búsqueda con Microsoft 365 API avanzada de búsqueda de Defender
keywords: Búsqueda avanzada, API, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769592"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="e615e-104">Microsoft 365 API de búsqueda avanzada de Defender</span><span class="sxs-lookup"><span data-stu-id="e615e-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e615e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e615e-105">**Applies to:**</span></span>

- <span data-ttu-id="e615e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e615e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e615e-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="e615e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e615e-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="e615e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e615e-109">[La búsqueda avanzada](advanced-hunting-overview.md) es una [](advanced-hunting-query-language.md) herramienta de búsqueda de amenazas que usa consultas especialmente construidas para examinar los últimos 30 días de datos de eventos en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e615e-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="e615e-110">Puedes usar consultas avanzadas de búsqueda para inspeccionar actividad inusual, detectar posibles amenazas e incluso responder a ataques.</span><span class="sxs-lookup"><span data-stu-id="e615e-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="e615e-111">La API de búsqueda avanzada le permite consultar programáticamente los datos de eventos.</span><span class="sxs-lookup"><span data-stu-id="e615e-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="e615e-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="e615e-112">Quotas and resource allocation</span></span>

<span data-ttu-id="e615e-113">Las siguientes condiciones se relacionan con todas las consultas.</span><span class="sxs-lookup"><span data-stu-id="e615e-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="e615e-114">Las consultas exploran y devuelven datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="e615e-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="e615e-115">Los resultados pueden devolver hasta 100 000 filas.</span><span class="sxs-lookup"><span data-stu-id="e615e-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="e615e-116">Puede realizar hasta 15 llamadas por minuto por inquilino.</span><span class="sxs-lookup"><span data-stu-id="e615e-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="e615e-117">Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="e615e-117">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span>
5. <span data-ttu-id="e615e-118">Si una sola solicitud se ejecuta durante más de 10 minutos, agotará el tiempo de espera y devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="e615e-118">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
6. <span data-ttu-id="e615e-119">Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="e615e-119">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="e615e-120">Lea el cuerpo de la respuesta para comprender el límite que ha alcanzado.</span><span class="sxs-lookup"><span data-stu-id="e615e-120">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="e615e-121">Todas las cuotas enumeradas anteriormente (por ejemplo, 15 llamadas por minuto) son por tamaño de espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="e615e-121">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="e615e-122">Estas cuotas son las mínimas.</span><span class="sxs-lookup"><span data-stu-id="e615e-122">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="e615e-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="e615e-123">Permissions</span></span>

<span data-ttu-id="e615e-124">Uno de los siguientes permisos es necesario para llamar a la API de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="e615e-124">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="e615e-125">Para obtener más información, incluido cómo elegir permisos, consulte [Access the Microsoft 365 Defender Protection API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="e615e-125">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="e615e-126">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="e615e-126">Permission type</span></span> | <span data-ttu-id="e615e-127">Permiso</span><span class="sxs-lookup"><span data-stu-id="e615e-127">Permission</span></span> | <span data-ttu-id="e615e-128">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="e615e-128">Permission display name</span></span>
-|-|-
<span data-ttu-id="e615e-129">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e615e-129">Application</span></span> | <span data-ttu-id="e615e-130">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="e615e-130">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="e615e-131">Ejecutar consultas avanzadas</span><span class="sxs-lookup"><span data-stu-id="e615e-131">Run advanced queries</span></span>
<span data-ttu-id="e615e-132">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="e615e-132">Delegated (work or school account)</span></span> | <span data-ttu-id="e615e-133">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="e615e-133">AdvancedHunting.Read</span></span> | <span data-ttu-id="e615e-134">Ejecutar consultas avanzadas</span><span class="sxs-lookup"><span data-stu-id="e615e-134">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="e615e-135">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="e615e-135">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="e615e-136">El usuario debe tener el rol de AD "Ver datos"</span><span class="sxs-lookup"><span data-stu-id="e615e-136">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="e615e-137">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e615e-137">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="e615e-138">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="e615e-138">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="e615e-139">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e615e-139">Request headers</span></span>

<span data-ttu-id="e615e-140">Encabezado</span><span class="sxs-lookup"><span data-stu-id="e615e-140">Header</span></span> | <span data-ttu-id="e615e-141">Valor</span><span class="sxs-lookup"><span data-stu-id="e615e-141">Value</span></span>
-|-
<span data-ttu-id="e615e-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="e615e-142">Authorization</span></span> | <span data-ttu-id="e615e-143">Portador {token} **Nota: obligatorio**</span><span class="sxs-lookup"><span data-stu-id="e615e-143">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="e615e-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e615e-144">Content-Type</span></span> | <span data-ttu-id="e615e-145">application/json</span><span class="sxs-lookup"><span data-stu-id="e615e-145">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="e615e-146">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="e615e-146">Request body</span></span>

<span data-ttu-id="e615e-147">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e615e-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="e615e-148">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e615e-148">Parameter</span></span> | <span data-ttu-id="e615e-149">Tipo</span><span class="sxs-lookup"><span data-stu-id="e615e-149">Type</span></span> | <span data-ttu-id="e615e-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="e615e-150">Description</span></span>
-|-|-
<span data-ttu-id="e615e-151">Consulta</span><span class="sxs-lookup"><span data-stu-id="e615e-151">Query</span></span> | <span data-ttu-id="e615e-152">Texto</span><span class="sxs-lookup"><span data-stu-id="e615e-152">Text</span></span> | <span data-ttu-id="e615e-153">Consulta que se debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e615e-153">The query to run.</span></span> <span data-ttu-id="e615e-154">**Nota: obligatorio**</span><span class="sxs-lookup"><span data-stu-id="e615e-154">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="e615e-155">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e615e-155">Response</span></span>

<span data-ttu-id="e615e-156">Si se ejecuta correctamente, este método devolverá `200 OK` y un _objeto QueryResponse_ en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e615e-156">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="e615e-157">El objeto response contiene tres propiedades de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="e615e-157">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="e615e-158">Estadísticas: diccionario de estadísticas de rendimiento de consulta.</span><span class="sxs-lookup"><span data-stu-id="e615e-158">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="e615e-159">Esquema: el esquema de la respuesta, una lista de Name-Type pares de cada columna.</span><span class="sxs-lookup"><span data-stu-id="e615e-159">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="e615e-160">Resultados: una lista de eventos de búsqueda avanzados.</span><span class="sxs-lookup"><span data-stu-id="e615e-160">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="e615e-161">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e615e-161">Example</span></span>

<span data-ttu-id="e615e-162">En el siguiente ejemplo, un usuario envía la consulta siguiente y recibe un objeto de respuesta api que contiene `Stats` , `Schema` y `Results` .</span><span class="sxs-lookup"><span data-stu-id="e615e-162">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="e615e-163">Consulta</span><span class="sxs-lookup"><span data-stu-id="e615e-163">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="e615e-164">Response (objeto)</span><span class="sxs-lookup"><span data-stu-id="e615e-164">Response object</span></span>

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="e615e-165">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="e615e-165">Related articles</span></span>

- [<span data-ttu-id="e615e-166">Acceder a las API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e615e-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e615e-167">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="e615e-167">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="e615e-168">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="e615e-168">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="e615e-169">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="e615e-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
