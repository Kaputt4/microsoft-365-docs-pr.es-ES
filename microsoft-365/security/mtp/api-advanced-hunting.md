---
title: API de búsqueda avanzada
description: Obtenga información sobre cómo ejecutar consultas de búsqueda avanzada mediante la API de protección contra amenazas de Microsoft
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
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650552"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="176f9-104">API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="176f9-104">Advanced hunting APIs</span></span>

<span data-ttu-id="176f9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="176f9-105">**Applies to:**</span></span>
- <span data-ttu-id="176f9-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="176f9-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="176f9-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="176f9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="176f9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="176f9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="176f9-109">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="176f9-109">Limitations</span></span>
1. <span data-ttu-id="176f9-110">Solo se puede ejecutar una consulta con datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="176f9-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="176f9-111">Los resultados incluirán un máximo de 100.000 filas.</span><span class="sxs-lookup"><span data-stu-id="176f9-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="176f9-112">El número de ejecuciones es limitado por espacio empresarial: hasta 15 llamadas por minuto, 15 minutos de tiempo de ejecución cada hora y 4 horas de tiempo de ejecución al día.</span><span class="sxs-lookup"><span data-stu-id="176f9-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="176f9-113">El tiempo de ejecución máximo de una única solicitud es de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="176f9-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="176f9-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="176f9-114">Permissions</span></span>
<span data-ttu-id="176f9-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="176f9-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="176f9-116">Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft Threat Protection](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="176f9-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="176f9-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="176f9-117">Permission type</span></span> |   <span data-ttu-id="176f9-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="176f9-118">Permission</span></span>  |   <span data-ttu-id="176f9-119">Nombre para mostrar del permiso</span><span class="sxs-lookup"><span data-stu-id="176f9-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="176f9-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="176f9-120">Application</span></span> |   <span data-ttu-id="176f9-121">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="176f9-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="176f9-122">' Ejecutar consultas avanzadas '</span><span class="sxs-lookup"><span data-stu-id="176f9-122">'Run advanced queries'</span></span>
<span data-ttu-id="176f9-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="176f9-123">Delegated (work or school account)</span></span> | <span data-ttu-id="176f9-124">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="176f9-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="176f9-125">' Ejecutar consultas avanzadas '</span><span class="sxs-lookup"><span data-stu-id="176f9-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="176f9-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="176f9-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="176f9-127">El usuario debe tener el rol de AD "ver datos"</span><span class="sxs-lookup"><span data-stu-id="176f9-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="176f9-128">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="176f9-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="176f9-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="176f9-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="176f9-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="176f9-130">Request headers</span></span>

<span data-ttu-id="176f9-131">Encabezado</span><span class="sxs-lookup"><span data-stu-id="176f9-131">Header</span></span> | <span data-ttu-id="176f9-132">Valor</span><span class="sxs-lookup"><span data-stu-id="176f9-132">Value</span></span> 
:---|:---
<span data-ttu-id="176f9-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="176f9-133">Authorization</span></span> | <span data-ttu-id="176f9-134">{Token} de portador.</span><span class="sxs-lookup"><span data-stu-id="176f9-134">Bearer {token}.</span></span> <span data-ttu-id="176f9-135">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="176f9-135">**Required**.</span></span>
<span data-ttu-id="176f9-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="176f9-136">Content-Type</span></span>    | <span data-ttu-id="176f9-137">application/json</span><span class="sxs-lookup"><span data-stu-id="176f9-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="176f9-138">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="176f9-138">Request body</span></span>
<span data-ttu-id="176f9-139">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="176f9-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="176f9-140">Parámetro</span><span class="sxs-lookup"><span data-stu-id="176f9-140">Parameter</span></span> | <span data-ttu-id="176f9-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="176f9-141">Type</span></span>    | <span data-ttu-id="176f9-142">Description</span><span class="sxs-lookup"><span data-stu-id="176f9-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="176f9-143">Consulta</span><span class="sxs-lookup"><span data-stu-id="176f9-143">Query</span></span> | <span data-ttu-id="176f9-144">Texto</span><span class="sxs-lookup"><span data-stu-id="176f9-144">Text</span></span> |  <span data-ttu-id="176f9-145">La consulta que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="176f9-145">The query to run.</span></span> <span data-ttu-id="176f9-146">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="176f9-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="176f9-147">Respuesta</span><span class="sxs-lookup"><span data-stu-id="176f9-147">Response</span></span>
<span data-ttu-id="176f9-148">Si se ejecuta correctamente, este método devuelve 200 OK y el objeto _QueryResponse_ en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="176f9-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="176f9-149">El objeto Response se divide en 3 partes (propiedades):</span><span class="sxs-lookup"><span data-stu-id="176f9-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="176f9-150">```Stats``` -Estadísticas de rendimiento de consultas.</span><span class="sxs-lookup"><span data-stu-id="176f9-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="176f9-151">```Schema``` -El esquema de la respuesta, una lista de pares de nombre-tipo para cada columna.</span><span class="sxs-lookup"><span data-stu-id="176f9-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="176f9-152">```Results``` -Una lista de eventos de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="176f9-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="176f9-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="176f9-153">Example</span></span>

<span data-ttu-id="176f9-154">Solicitud</span><span class="sxs-lookup"><span data-stu-id="176f9-154">Request</span></span>

<span data-ttu-id="176f9-155">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="176f9-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="176f9-156">Respuesta</span><span class="sxs-lookup"><span data-stu-id="176f9-156">Response</span></span>

<span data-ttu-id="176f9-157">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="176f9-157">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="176f9-158">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="176f9-158">Related topic</span></span>
- [<span data-ttu-id="176f9-159">Acceso a las API de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="176f9-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
