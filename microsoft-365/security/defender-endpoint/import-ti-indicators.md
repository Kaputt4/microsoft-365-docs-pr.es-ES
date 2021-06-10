---
title: API importar indicadores
description: Obtenga información sobre cómo usar el lote Importar lote de API de indicadores en Microsoft Defender para endpoint.
keywords: apis, api admitidas, submit, ti, indicator, update
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198250"
---
# <a name="import-indicators-api"></a><span data-ttu-id="96ab5-104">API importar indicadores</span><span class="sxs-lookup"><span data-stu-id="96ab5-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="96ab5-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="96ab5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="96ab5-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="96ab5-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="96ab5-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="96ab5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="96ab5-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="96ab5-108">API description</span></span>
<span data-ttu-id="96ab5-109">Envía o actualiza el lote de [entidades de](ti-indicator.md) indicador.</span><span class="sxs-lookup"><span data-stu-id="96ab5-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="96ab5-110">No se admite la notación CIDR para IP.</span><span class="sxs-lookup"><span data-stu-id="96ab5-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="96ab5-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="96ab5-111">Limitations</span></span>
1. <span data-ttu-id="96ab5-112">Las limitaciones de velocidad para esta API son 30 llamadas por minuto.</span><span class="sxs-lookup"><span data-stu-id="96ab5-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="96ab5-113">Hay un límite de 15 000 indicadores [activos](ti-indicator.md) por inquilino.</span><span class="sxs-lookup"><span data-stu-id="96ab5-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="96ab5-114">El tamaño máximo de lote para una llamada API es 500.</span><span class="sxs-lookup"><span data-stu-id="96ab5-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="96ab5-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="96ab5-115">Permissions</span></span>
<span data-ttu-id="96ab5-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="96ab5-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="96ab5-117">Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="96ab5-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="96ab5-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="96ab5-118">Permission type</span></span> |   <span data-ttu-id="96ab5-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="96ab5-119">Permission</span></span>  |   <span data-ttu-id="96ab5-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="96ab5-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="96ab5-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="96ab5-121">Application</span></span> |   <span data-ttu-id="96ab5-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="96ab5-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="96ab5-123">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="96ab5-123">'Read and write Indicators'</span></span>
<span data-ttu-id="96ab5-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="96ab5-124">Application</span></span> |   <span data-ttu-id="96ab5-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="96ab5-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="96ab5-126">'Leer y escribir todos los indicadores'</span><span class="sxs-lookup"><span data-stu-id="96ab5-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="96ab5-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="96ab5-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="96ab5-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="96ab5-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="96ab5-129">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="96ab5-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="96ab5-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="96ab5-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="96ab5-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="96ab5-131">Request headers</span></span>

<span data-ttu-id="96ab5-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="96ab5-132">Name</span></span> | <span data-ttu-id="96ab5-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="96ab5-133">Type</span></span> | <span data-ttu-id="96ab5-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="96ab5-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="96ab5-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="96ab5-135">Authorization</span></span> | <span data-ttu-id="96ab5-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="96ab5-136">String</span></span> | <span data-ttu-id="96ab5-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="96ab5-137">Bearer {token}.</span></span> <span data-ttu-id="96ab5-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="96ab5-138">**Required**.</span></span>
<span data-ttu-id="96ab5-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="96ab5-139">Content-Type</span></span> | <span data-ttu-id="96ab5-140">cadena</span><span class="sxs-lookup"><span data-stu-id="96ab5-140">string</span></span> | <span data-ttu-id="96ab5-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="96ab5-141">application/json.</span></span> <span data-ttu-id="96ab5-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="96ab5-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="96ab5-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="96ab5-143">Request body</span></span>
<span data-ttu-id="96ab5-144">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="96ab5-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="96ab5-145">Parámetro</span><span class="sxs-lookup"><span data-stu-id="96ab5-145">Parameter</span></span> | <span data-ttu-id="96ab5-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="96ab5-146">Type</span></span>    | <span data-ttu-id="96ab5-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="96ab5-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="96ab5-148">Indicadores</span><span class="sxs-lookup"><span data-stu-id="96ab5-148">Indicators</span></span> | <span data-ttu-id="96ab5-149">Indicador<[lista](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="96ab5-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="96ab5-150">Lista de [indicadores](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="96ab5-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="96ab5-151">**Required**</span><span class="sxs-lookup"><span data-stu-id="96ab5-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="96ab5-152">Respuesta</span><span class="sxs-lookup"><span data-stu-id="96ab5-152">Response</span></span>
- <span data-ttu-id="96ab5-153">Si se realiza correctamente, este método devuelve 200: código de respuesta aceptar con una lista de resultados de importación por indicador, vea el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="96ab5-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="96ab5-154">Si no se realiza correctamente: este método devuelve 400 - Solicitud mala.</span><span class="sxs-lookup"><span data-stu-id="96ab5-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="96ab5-155">La solicitud incorrecta suele indicar un cuerpo incorrecto.</span><span class="sxs-lookup"><span data-stu-id="96ab5-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="96ab5-156">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="96ab5-156">Example</span></span>

<span data-ttu-id="96ab5-157">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="96ab5-157">**Request**</span></span>

<span data-ttu-id="96ab5-158">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="96ab5-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="96ab5-159">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="96ab5-159">**Response**</span></span>

<span data-ttu-id="96ab5-160">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="96ab5-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="96ab5-161">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="96ab5-161">Related topic</span></span>
- [<span data-ttu-id="96ab5-162">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="96ab5-162">Manage indicators</span></span>](manage-indicators.md)
