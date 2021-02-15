---
title: API de búsqueda avanzada de Microsoft 365 Defender
description: Obtenga información sobre cómo ejecutar consultas de búsqueda avanzada con la API de búsqueda avanzada de Microsoft 365 Defender
keywords: Búsqueda avanzada, API, api, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988121"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="c4abc-104">API de búsqueda avanzada de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4abc-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c4abc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c4abc-105">**Applies to:**</span></span>

- <span data-ttu-id="c4abc-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c4abc-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4abc-107">Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="c4abc-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c4abc-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="c4abc-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c4abc-109">[La búsqueda](advanced-hunting-overview.md) avanzada es una [](advanced-hunting-query-language.md) herramienta de búsqueda de amenazas que usa consultas especialmente construidas para examinar los últimos 30 días de datos de eventos en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c4abc-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="c4abc-110">Puede usar consultas de búsqueda avanzada para inspeccionar actividad inusual, detectar posibles amenazas e incluso responder a ataques.</span><span class="sxs-lookup"><span data-stu-id="c4abc-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="c4abc-111">La API de búsqueda avanzada permite consultar mediante programación los datos de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4abc-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="c4abc-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="c4abc-112">Quotas and resource allocation</span></span>

<span data-ttu-id="c4abc-113">Las siguientes condiciones se relacionan con todas las consultas.</span><span class="sxs-lookup"><span data-stu-id="c4abc-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="c4abc-114">Las consultas exploran y devuelven datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="c4abc-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="c4abc-115">Los resultados pueden devolver hasta 100 000 filas.</span><span class="sxs-lookup"><span data-stu-id="c4abc-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="c4abc-116">Puede realizar hasta 15 llamadas por minuto por inquilino.</span><span class="sxs-lookup"><span data-stu-id="c4abc-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="c4abc-117">Tiene 10 minutos de tiempo de ejecución por hora por inquilino.</span><span class="sxs-lookup"><span data-stu-id="c4abc-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="c4abc-118">Tiene cuatro horas totales de tiempo de ejecución por día por inquilino.</span><span class="sxs-lookup"><span data-stu-id="c4abc-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="c4abc-119">Si una sola solicitud se ejecuta durante más de 10 minutos, agotará el tiempo de espera y devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="c4abc-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="c4abc-120">Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="c4abc-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="c4abc-121">Lea el cuerpo de la respuesta para comprender el límite que ha alcanzado.</span><span class="sxs-lookup"><span data-stu-id="c4abc-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="c4abc-122">Todas las cuotas enumeradas anteriormente (por ejemplo, 15 llamadas por minuto) son por tamaño de espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c4abc-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="c4abc-123">Estas cuotas son las mínimas.</span><span class="sxs-lookup"><span data-stu-id="c4abc-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="c4abc-124">Permissions</span><span class="sxs-lookup"><span data-stu-id="c4abc-124">Permissions</span></span>

<span data-ttu-id="c4abc-125">Se requiere uno de los siguientes permisos para llamar a la API de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="c4abc-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="c4abc-126">Para obtener más información, incluido cómo elegir permisos, consulte Acceso a las API [de Protección de Microsoft 365 Defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c4abc-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="c4abc-127">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="c4abc-127">Permission type</span></span> | <span data-ttu-id="c4abc-128">Permiso</span><span class="sxs-lookup"><span data-stu-id="c4abc-128">Permission</span></span> | <span data-ttu-id="c4abc-129">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="c4abc-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="c4abc-130">Aplicación</span><span class="sxs-lookup"><span data-stu-id="c4abc-130">Application</span></span> | <span data-ttu-id="c4abc-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="c4abc-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="c4abc-132">Ejecutar consultas avanzadas</span><span class="sxs-lookup"><span data-stu-id="c4abc-132">Run advanced queries</span></span>
<span data-ttu-id="c4abc-133">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="c4abc-133">Delegated (work or school account)</span></span> | <span data-ttu-id="c4abc-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="c4abc-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="c4abc-135">Ejecutar consultas avanzadas</span><span class="sxs-lookup"><span data-stu-id="c4abc-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="c4abc-136">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="c4abc-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="c4abc-137">El usuario debe tener el rol de AD "Ver datos"</span><span class="sxs-lookup"><span data-stu-id="c4abc-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="c4abc-138">El usuario debe tener acceso al dispositivo, en función de la configuración del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c4abc-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="c4abc-139">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="c4abc-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="c4abc-140">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="c4abc-140">Request headers</span></span>

<span data-ttu-id="c4abc-141">Encabezado</span><span class="sxs-lookup"><span data-stu-id="c4abc-141">Header</span></span> | <span data-ttu-id="c4abc-142">Valor</span><span class="sxs-lookup"><span data-stu-id="c4abc-142">Value</span></span>
-|-
<span data-ttu-id="c4abc-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="c4abc-143">Authorization</span></span> | <span data-ttu-id="c4abc-144">Bearer {token} **Nota: obligatorio**</span><span class="sxs-lookup"><span data-stu-id="c4abc-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="c4abc-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c4abc-145">Content-Type</span></span> | <span data-ttu-id="c4abc-146">application/json</span><span class="sxs-lookup"><span data-stu-id="c4abc-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="c4abc-147">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="c4abc-147">Request body</span></span>

<span data-ttu-id="c4abc-148">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="c4abc-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c4abc-149">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c4abc-149">Parameter</span></span> | <span data-ttu-id="c4abc-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="c4abc-150">Type</span></span> | <span data-ttu-id="c4abc-151">Description</span><span class="sxs-lookup"><span data-stu-id="c4abc-151">Description</span></span>
-|-|-
<span data-ttu-id="c4abc-152">Consulta</span><span class="sxs-lookup"><span data-stu-id="c4abc-152">Query</span></span> | <span data-ttu-id="c4abc-153">Texto</span><span class="sxs-lookup"><span data-stu-id="c4abc-153">Text</span></span> | <span data-ttu-id="c4abc-154">Consulta que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="c4abc-154">The query to run.</span></span> <span data-ttu-id="c4abc-155">**Nota: obligatorio**</span><span class="sxs-lookup"><span data-stu-id="c4abc-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="c4abc-156">Respuesta</span><span class="sxs-lookup"><span data-stu-id="c4abc-156">Response</span></span>

<span data-ttu-id="c4abc-157">Si se ejecuta correctamente, este método devolverá `200 OK` y un _objeto QueryResponse_ en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c4abc-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="c4abc-158">El objeto de respuesta contiene tres propiedades de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="c4abc-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="c4abc-159">Estadísticas: diccionario de estadísticas de rendimiento de consultas.</span><span class="sxs-lookup"><span data-stu-id="c4abc-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="c4abc-160">Esquema: esquema de la respuesta, una lista de Name-Type pares para cada columna.</span><span class="sxs-lookup"><span data-stu-id="c4abc-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="c4abc-161">Resultados: una lista de eventos de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="c4abc-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="c4abc-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4abc-162">Example</span></span>

<span data-ttu-id="c4abc-163">En el siguiente ejemplo, un usuario envía la consulta siguiente y recibe un objeto de respuesta api que contiene `Stats` `Schema` , y `Results` .</span><span class="sxs-lookup"><span data-stu-id="c4abc-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="c4abc-164">Consulta</span><span class="sxs-lookup"><span data-stu-id="c4abc-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="c4abc-165">Response (objeto)</span><span class="sxs-lookup"><span data-stu-id="c4abc-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="c4abc-166">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="c4abc-166">Related articles</span></span>

- [<span data-ttu-id="c4abc-167">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4abc-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c4abc-168">Más información sobre los límites de la API y las licencias</span><span class="sxs-lookup"><span data-stu-id="c4abc-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c4abc-169">Comprender los códigos de error</span><span class="sxs-lookup"><span data-stu-id="c4abc-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="c4abc-170">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c4abc-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
