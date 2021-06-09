---
title: API de indicadores de lista
description: Obtenga información sobre cómo usar la API de indicadores de lista para recuperar una colección de todos los indicadores activos en Microsoft Defender para endpoint.
keywords: apis, api pública, api admitidas, colección Indicators
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9ec8610957af0bc7741848e7c7bd4fe850f5e32
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770433"
---
# <a name="list-indicators-api"></a><span data-ttu-id="db960-104">API de indicadores de lista</span><span class="sxs-lookup"><span data-stu-id="db960-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db960-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="db960-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="db960-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="db960-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="db960-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="db960-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="db960-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="db960-108">API description</span></span>
<span data-ttu-id="db960-109">Recupera una colección de todos los [indicadores activos](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="db960-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="db960-110">Admite [consultas de OData V4](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="db960-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="db960-111">La consulta de OData ```$filter``` se admite en: ```indicatorValue``` , , , y ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` propiedades.</span><span class="sxs-lookup"><span data-stu-id="db960-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="db960-112">Vea ejemplos en [consultas de OData con Microsoft Defender para endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="db960-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="db960-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="db960-113">Limitations</span></span>
1. <span data-ttu-id="db960-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="db960-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="db960-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="db960-115">Permissions</span></span>
<span data-ttu-id="db960-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="db960-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="db960-117">Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="db960-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="db960-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="db960-118">Permission type</span></span> |   <span data-ttu-id="db960-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="db960-119">Permission</span></span>  |   <span data-ttu-id="db960-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="db960-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="db960-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="db960-121">Application</span></span> |   <span data-ttu-id="db960-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="db960-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="db960-123">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="db960-123">'Read and write Indicators'</span></span>
<span data-ttu-id="db960-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="db960-124">Application</span></span> |   <span data-ttu-id="db960-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="db960-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="db960-126">'Leer y escribir todos los indicadores'</span><span class="sxs-lookup"><span data-stu-id="db960-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="db960-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="db960-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="db960-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="db960-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="db960-129">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="db960-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="db960-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="db960-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="db960-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="db960-131">Request headers</span></span>

<span data-ttu-id="db960-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="db960-132">Name</span></span> | <span data-ttu-id="db960-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="db960-133">Type</span></span> | <span data-ttu-id="db960-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="db960-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="db960-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="db960-135">Authorization</span></span> | <span data-ttu-id="db960-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="db960-136">String</span></span> | <span data-ttu-id="db960-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="db960-137">Bearer {token}.</span></span> <span data-ttu-id="db960-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="db960-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="db960-139">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="db960-139">Request body</span></span>
<span data-ttu-id="db960-140">En blanco</span><span class="sxs-lookup"><span data-stu-id="db960-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="db960-141">Respuesta</span><span class="sxs-lookup"><span data-stu-id="db960-141">Response</span></span>
<span data-ttu-id="db960-142">Si se realiza correctamente, este método devuelve 200 código de respuesta Ok con una colección de [entidades Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="db960-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="db960-143">Si la aplicación tiene el permiso "Ti.ReadWrite.All", se expone a todos los indicadores.</span><span class="sxs-lookup"><span data-stu-id="db960-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="db960-144">De lo contrario, solo se mostrará a los indicadores que creó.</span><span class="sxs-lookup"><span data-stu-id="db960-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="db960-145">Ejemplo 1:</span><span class="sxs-lookup"><span data-stu-id="db960-145">Example 1:</span></span>

<span data-ttu-id="db960-146">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="db960-146">**Request**</span></span>

<span data-ttu-id="db960-147">Este es un ejemplo de una solicitud que obtiene todos los indicadores</span><span class="sxs-lookup"><span data-stu-id="db960-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="db960-148">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="db960-148">**Response**</span></span>

<span data-ttu-id="db960-149">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="db960-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="db960-150">Ejemplo 2:</span><span class="sxs-lookup"><span data-stu-id="db960-150">Example 2:</span></span>

<span data-ttu-id="db960-151">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="db960-151">**Request**</span></span>

<span data-ttu-id="db960-152">Este es un ejemplo de una solicitud que obtiene todos los indicadores con la acción "AlertAndBlock".</span><span class="sxs-lookup"><span data-stu-id="db960-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="db960-153">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="db960-153">**Response**</span></span>

<span data-ttu-id="db960-154">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="db960-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
