---
title: API de Búsqueda avanzada de amenazas
ms.reviewer: ''
description: Aprenda a usar la API de búsqueda avanzada para ejecutar consultas avanzadas en Microsoft Defender para endpoint. Descubra las limitaciones y vea un ejemplo.
keywords: apis, api admitidas, búsqueda avanzada, consulta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200202"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="e0253-105">API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e0253-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e0253-106">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e0253-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e0253-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e0253-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e0253-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e0253-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="e0253-109">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="e0253-109">Limitations</span></span>
1. <span data-ttu-id="e0253-110">Solo puede ejecutar una consulta de datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="e0253-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="e0253-111">Los resultados incluirán un máximo de 100 000 filas.</span><span class="sxs-lookup"><span data-stu-id="e0253-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="e0253-112">El número de ejecuciones es limitado por inquilino:</span><span class="sxs-lookup"><span data-stu-id="e0253-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="e0253-113">Llamadas API: hasta 45 llamadas por minuto.</span><span class="sxs-lookup"><span data-stu-id="e0253-113">API calls: Up to 45 calls per minute.</span></span>
   - <span data-ttu-id="e0253-114">Tiempo de ejecución: 10 minutos de tiempo de ejecución cada hora y 3 horas de tiempo de ejecución al día.</span><span class="sxs-lookup"><span data-stu-id="e0253-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>
4. <span data-ttu-id="e0253-115">El tiempo máximo de ejecución de una sola solicitud es de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="e0253-115">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="e0253-116">La respuesta 429 representará alcanzar el límite de cuota por número de solicitudes o por CPU.</span><span class="sxs-lookup"><span data-stu-id="e0253-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="e0253-117">Lea el cuerpo de la respuesta para comprender qué límite se ha alcanzado.</span><span class="sxs-lookup"><span data-stu-id="e0253-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="e0253-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="e0253-118">Permissions</span></span>
<span data-ttu-id="e0253-119">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="e0253-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e0253-120">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e0253-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e0253-121">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="e0253-121">Permission type</span></span> |   <span data-ttu-id="e0253-122">Permiso</span><span class="sxs-lookup"><span data-stu-id="e0253-122">Permission</span></span>  |   <span data-ttu-id="e0253-123">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="e0253-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e0253-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e0253-124">Application</span></span> |   <span data-ttu-id="e0253-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="e0253-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="e0253-126">'Ejecutar consultas avanzadas'</span><span class="sxs-lookup"><span data-stu-id="e0253-126">'Run advanced queries'</span></span>
<span data-ttu-id="e0253-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="e0253-127">Delegated (work or school account)</span></span> | <span data-ttu-id="e0253-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="e0253-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="e0253-129">'Ejecutar consultas avanzadas'</span><span class="sxs-lookup"><span data-stu-id="e0253-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="e0253-130">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="e0253-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e0253-131">El usuario debe tener el rol de AD "Ver datos"</span><span class="sxs-lookup"><span data-stu-id="e0253-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="e0253-132">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="e0253-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e0253-133">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="e0253-133">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="e0253-134">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e0253-134">Request headers</span></span>

<span data-ttu-id="e0253-135">Encabezado</span><span class="sxs-lookup"><span data-stu-id="e0253-135">Header</span></span> | <span data-ttu-id="e0253-136">Valor</span><span class="sxs-lookup"><span data-stu-id="e0253-136">Value</span></span> 
:---|:---
<span data-ttu-id="e0253-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="e0253-137">Authorization</span></span> | <span data-ttu-id="e0253-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="e0253-138">Bearer {token}.</span></span> <span data-ttu-id="e0253-139">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="e0253-139">**Required**.</span></span>
<span data-ttu-id="e0253-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e0253-140">Content-Type</span></span>    | <span data-ttu-id="e0253-141">application/json</span><span class="sxs-lookup"><span data-stu-id="e0253-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="e0253-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="e0253-142">Request body</span></span>
<span data-ttu-id="e0253-143">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e0253-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="e0253-144">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e0253-144">Parameter</span></span> | <span data-ttu-id="e0253-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="e0253-145">Type</span></span>    | <span data-ttu-id="e0253-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0253-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="e0253-147">Consulta</span><span class="sxs-lookup"><span data-stu-id="e0253-147">Query</span></span> | <span data-ttu-id="e0253-148">Texto</span><span class="sxs-lookup"><span data-stu-id="e0253-148">Text</span></span> |  <span data-ttu-id="e0253-149">Consulta que se debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e0253-149">The query to run.</span></span> <span data-ttu-id="e0253-150">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="e0253-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="e0253-151">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e0253-151">Response</span></span>
<span data-ttu-id="e0253-152">Si se ejecuta correctamente, este método devuelve 200 Ok y _el objeto QueryResponse_ en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e0253-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="e0253-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0253-153">Example</span></span>

<span data-ttu-id="e0253-154">Solicitud</span><span class="sxs-lookup"><span data-stu-id="e0253-154">Request</span></span>

<span data-ttu-id="e0253-155">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e0253-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

<span data-ttu-id="e0253-156">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e0253-156">Response</span></span>

<span data-ttu-id="e0253-157">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e0253-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="e0253-158">El objeto de respuesta que se muestra aquí puede truncarse por brevedad.</span><span class="sxs-lookup"><span data-stu-id="e0253-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="e0253-159">Todas las propiedades se devolverán desde una llamada real.</span><span class="sxs-lookup"><span data-stu-id="e0253-159">All of the properties will be returned from an actual call.</span></span>

```json
{
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
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="e0253-160">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="e0253-160">Related topic</span></span>
- [<span data-ttu-id="e0253-161">Introducción a las API de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="e0253-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="e0253-162">Búsqueda avanzada desde portal</span><span class="sxs-lookup"><span data-stu-id="e0253-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e0253-163">Búsqueda avanzada con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0253-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
