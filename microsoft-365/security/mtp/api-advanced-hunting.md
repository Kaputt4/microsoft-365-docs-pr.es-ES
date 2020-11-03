---
title: API de búsqueda avanzada
description: Obtenga información sobre cómo ejecutar consultas de búsqueda avanzada mediante la API de Microsoft 365 defender
keywords: Búsqueda avanzada, API, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844037"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="bfe7f-104">API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="bfe7f-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bfe7f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bfe7f-105">**Applies to:**</span></span>
- <span data-ttu-id="bfe7f-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="bfe7f-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="bfe7f-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bfe7f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="bfe7f-109">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="bfe7f-109">Limitations</span></span>
1. <span data-ttu-id="bfe7f-110">Solo se puede ejecutar una consulta con datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="bfe7f-111">Los resultados incluirán un máximo de 100.000 filas.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="bfe7f-112">El número de ejecuciones es limitado por espacio empresarial: hasta 10 llamadas por minuto, 10 minutos de tiempo de ejecución cada hora y 4 horas de tiempo de ejecución al día.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="bfe7f-113">El tiempo de ejecución máximo de una única solicitud es de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="bfe7f-114">429 respuesta representará el límite de la cuota de alcance mediante el número de solicitudes o la CPU.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="bfe7f-115">El cuerpo de respuesta 429 también indicará el tiempo hasta que se renueve la cuota.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="bfe7f-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="bfe7f-116">Permissions</span></span>
<span data-ttu-id="bfe7f-117">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bfe7f-118">Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft 365 defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="bfe7f-118">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="bfe7f-119">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="bfe7f-119">Permission type</span></span> |   <span data-ttu-id="bfe7f-120">Permiso</span><span class="sxs-lookup"><span data-stu-id="bfe7f-120">Permission</span></span>  |   <span data-ttu-id="bfe7f-121">Nombre para mostrar del permiso</span><span class="sxs-lookup"><span data-stu-id="bfe7f-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bfe7f-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="bfe7f-122">Application</span></span> |   <span data-ttu-id="bfe7f-123">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="bfe7f-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="bfe7f-124">' Ejecutar consultas avanzadas '</span><span class="sxs-lookup"><span data-stu-id="bfe7f-124">'Run advanced queries'</span></span>
<span data-ttu-id="bfe7f-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="bfe7f-125">Delegated (work or school account)</span></span> | <span data-ttu-id="bfe7f-126">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="bfe7f-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="bfe7f-127">' Ejecutar consultas avanzadas '</span><span class="sxs-lookup"><span data-stu-id="bfe7f-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="bfe7f-128">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="bfe7f-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bfe7f-129">El usuario debe tener el rol de AD "ver datos"</span><span class="sxs-lookup"><span data-stu-id="bfe7f-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="bfe7f-130">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="bfe7f-131">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="bfe7f-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="bfe7f-132">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="bfe7f-132">Request headers</span></span>

<span data-ttu-id="bfe7f-133">Encabezado</span><span class="sxs-lookup"><span data-stu-id="bfe7f-133">Header</span></span> | <span data-ttu-id="bfe7f-134">Valor</span><span class="sxs-lookup"><span data-stu-id="bfe7f-134">Value</span></span> 
:---|:---
<span data-ttu-id="bfe7f-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="bfe7f-135">Authorization</span></span> | <span data-ttu-id="bfe7f-136">{Token} de portador.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-136">Bearer {token}.</span></span> <span data-ttu-id="bfe7f-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-137">**Required**.</span></span>
<span data-ttu-id="bfe7f-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bfe7f-138">Content-Type</span></span>    | <span data-ttu-id="bfe7f-139">application/json</span><span class="sxs-lookup"><span data-stu-id="bfe7f-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="bfe7f-140">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="bfe7f-140">Request body</span></span>
<span data-ttu-id="bfe7f-141">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="bfe7f-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="bfe7f-142">Parámetro</span><span class="sxs-lookup"><span data-stu-id="bfe7f-142">Parameter</span></span> | <span data-ttu-id="bfe7f-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="bfe7f-143">Type</span></span>    | <span data-ttu-id="bfe7f-144">Description</span><span class="sxs-lookup"><span data-stu-id="bfe7f-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="bfe7f-145">Consulta</span><span class="sxs-lookup"><span data-stu-id="bfe7f-145">Query</span></span> | <span data-ttu-id="bfe7f-146">Texto</span><span class="sxs-lookup"><span data-stu-id="bfe7f-146">Text</span></span> |  <span data-ttu-id="bfe7f-147">La consulta que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-147">The query to run.</span></span> <span data-ttu-id="bfe7f-148">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="bfe7f-149">Respuesta</span><span class="sxs-lookup"><span data-stu-id="bfe7f-149">Response</span></span>
<span data-ttu-id="bfe7f-150">Si se ejecuta correctamente, este método devuelve 200 OK y el objeto _QueryResponse_ en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="bfe7f-151">El objeto Response se divide en 3 partes (propiedades):</span><span class="sxs-lookup"><span data-stu-id="bfe7f-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="bfe7f-152">```Stats``` -Estadísticas de rendimiento de consultas.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="bfe7f-153">```Schema``` -El esquema de la respuesta, una lista de pares de Name-Type para cada columna.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="bfe7f-154">```Results``` -Una lista de eventos de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="bfe7f-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bfe7f-155">Example</span></span>

<span data-ttu-id="bfe7f-156">Solicitud</span><span class="sxs-lookup"><span data-stu-id="bfe7f-156">Request</span></span>

<span data-ttu-id="bfe7f-157">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="bfe7f-158">Respuesta</span><span class="sxs-lookup"><span data-stu-id="bfe7f-158">Response</span></span>

<span data-ttu-id="bfe7f-159">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="bfe7f-159">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="bfe7f-160">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="bfe7f-160">Related topic</span></span>
- [<span data-ttu-id="bfe7f-161">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="bfe7f-161">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
