---
title: API de búsqueda avanzada de Microsoft 365 Defender
description: Obtenga información sobre cómo ejecutar consultas avanzadas de búsqueda con la API avanzada de búsqueda de Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 482801bb47429ae370e06cfcbcf26bacfb8b2a92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074800"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="eca2b-104">API de búsqueda avanzada de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eca2b-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="eca2b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="eca2b-105">**Applies to:**</span></span>

- <span data-ttu-id="eca2b-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="eca2b-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eca2b-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="eca2b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="eca2b-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="eca2b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="eca2b-109">[La búsqueda avanzada](advanced-hunting-overview.md) es una [](advanced-hunting-query-language.md) herramienta de búsqueda de amenazas que usa consultas especialmente construidas para examinar los últimos 30 días de datos de eventos en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="eca2b-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="eca2b-110">Puedes usar consultas avanzadas de búsqueda para inspeccionar actividad inusual, detectar posibles amenazas e incluso responder a ataques.</span><span class="sxs-lookup"><span data-stu-id="eca2b-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="eca2b-111">La API de búsqueda avanzada le permite consultar programáticamente los datos de eventos.</span><span class="sxs-lookup"><span data-stu-id="eca2b-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="eca2b-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="eca2b-112">Quotas and resource allocation</span></span>

<span data-ttu-id="eca2b-113">Las siguientes condiciones se relacionan con todas las consultas.</span><span class="sxs-lookup"><span data-stu-id="eca2b-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="eca2b-114">Las consultas exploran y devuelven datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="eca2b-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="eca2b-115">Los resultados pueden devolver hasta 100 000 filas.</span><span class="sxs-lookup"><span data-stu-id="eca2b-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="eca2b-116">Puede realizar hasta 15 llamadas por minuto por inquilino.</span><span class="sxs-lookup"><span data-stu-id="eca2b-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="eca2b-117">Tiene 10 minutos de tiempo de ejecución por hora por inquilino.</span><span class="sxs-lookup"><span data-stu-id="eca2b-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="eca2b-118">Tiene cuatro horas totales de tiempo de ejecución al día por inquilino.</span><span class="sxs-lookup"><span data-stu-id="eca2b-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="eca2b-119">Si una sola solicitud se ejecuta durante más de 10 minutos, agotará el tiempo de espera y devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="eca2b-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="eca2b-120">Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="eca2b-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="eca2b-121">Lea el cuerpo de la respuesta para comprender el límite que ha alcanzado.</span><span class="sxs-lookup"><span data-stu-id="eca2b-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="eca2b-122">Todas las cuotas enumeradas anteriormente (por ejemplo, 15 llamadas por minuto) son por tamaño de espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="eca2b-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="eca2b-123">Estas cuotas son las mínimas.</span><span class="sxs-lookup"><span data-stu-id="eca2b-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="eca2b-124">Permisos</span><span class="sxs-lookup"><span data-stu-id="eca2b-124">Permissions</span></span>

<span data-ttu-id="eca2b-125">Uno de los siguientes permisos es necesario para llamar a la API de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="eca2b-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="eca2b-126">Para obtener más información, incluido cómo elegir permisos, vea [Access the Microsoft 365 Defender Protection API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="eca2b-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="eca2b-127">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="eca2b-127">Permission type</span></span> | <span data-ttu-id="eca2b-128">Permiso</span><span class="sxs-lookup"><span data-stu-id="eca2b-128">Permission</span></span> | <span data-ttu-id="eca2b-129">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="eca2b-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="eca2b-130">Aplicación</span><span class="sxs-lookup"><span data-stu-id="eca2b-130">Application</span></span> | <span data-ttu-id="eca2b-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="eca2b-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="eca2b-132">Ejecutar consultas avanzadas</span><span class="sxs-lookup"><span data-stu-id="eca2b-132">Run advanced queries</span></span>
<span data-ttu-id="eca2b-133">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="eca2b-133">Delegated (work or school account)</span></span> | <span data-ttu-id="eca2b-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="eca2b-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="eca2b-135">Ejecutar consultas avanzadas</span><span class="sxs-lookup"><span data-stu-id="eca2b-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="eca2b-136">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="eca2b-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="eca2b-137">El usuario debe tener el rol de AD "Ver datos"</span><span class="sxs-lookup"><span data-stu-id="eca2b-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="eca2b-138">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="eca2b-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="eca2b-139">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="eca2b-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="eca2b-140">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="eca2b-140">Request headers</span></span>

<span data-ttu-id="eca2b-141">Encabezado</span><span class="sxs-lookup"><span data-stu-id="eca2b-141">Header</span></span> | <span data-ttu-id="eca2b-142">Valor</span><span class="sxs-lookup"><span data-stu-id="eca2b-142">Value</span></span>
-|-
<span data-ttu-id="eca2b-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="eca2b-143">Authorization</span></span> | <span data-ttu-id="eca2b-144">Portador {token} **Nota: obligatorio**</span><span class="sxs-lookup"><span data-stu-id="eca2b-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="eca2b-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="eca2b-145">Content-Type</span></span> | <span data-ttu-id="eca2b-146">application/json</span><span class="sxs-lookup"><span data-stu-id="eca2b-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="eca2b-147">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="eca2b-147">Request body</span></span>

<span data-ttu-id="eca2b-148">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="eca2b-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="eca2b-149">Parámetro</span><span class="sxs-lookup"><span data-stu-id="eca2b-149">Parameter</span></span> | <span data-ttu-id="eca2b-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="eca2b-150">Type</span></span> | <span data-ttu-id="eca2b-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="eca2b-151">Description</span></span>
-|-|-
<span data-ttu-id="eca2b-152">Consulta</span><span class="sxs-lookup"><span data-stu-id="eca2b-152">Query</span></span> | <span data-ttu-id="eca2b-153">Texto</span><span class="sxs-lookup"><span data-stu-id="eca2b-153">Text</span></span> | <span data-ttu-id="eca2b-154">Consulta que se debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="eca2b-154">The query to run.</span></span> <span data-ttu-id="eca2b-155">**Nota: obligatorio**</span><span class="sxs-lookup"><span data-stu-id="eca2b-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="eca2b-156">Respuesta</span><span class="sxs-lookup"><span data-stu-id="eca2b-156">Response</span></span>

<span data-ttu-id="eca2b-157">Si se ejecuta correctamente, este método devolverá `200 OK` y un _objeto QueryResponse_ en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="eca2b-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="eca2b-158">El objeto response contiene tres propiedades de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="eca2b-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="eca2b-159">Estadísticas: diccionario de estadísticas de rendimiento de consulta.</span><span class="sxs-lookup"><span data-stu-id="eca2b-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="eca2b-160">Esquema: el esquema de la respuesta, una lista de Name-Type pares de cada columna.</span><span class="sxs-lookup"><span data-stu-id="eca2b-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="eca2b-161">Resultados: una lista de eventos de búsqueda avanzados.</span><span class="sxs-lookup"><span data-stu-id="eca2b-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="eca2b-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eca2b-162">Example</span></span>

<span data-ttu-id="eca2b-163">En el siguiente ejemplo, un usuario envía la consulta siguiente y recibe un objeto de respuesta api que contiene `Stats` , `Schema` y `Results` .</span><span class="sxs-lookup"><span data-stu-id="eca2b-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="eca2b-164">Consulta</span><span class="sxs-lookup"><span data-stu-id="eca2b-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="eca2b-165">Response (objeto)</span><span class="sxs-lookup"><span data-stu-id="eca2b-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="eca2b-166">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="eca2b-166">Related articles</span></span>

- [<span data-ttu-id="eca2b-167">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eca2b-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="eca2b-168">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="eca2b-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="eca2b-169">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="eca2b-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="eca2b-170">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="eca2b-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
