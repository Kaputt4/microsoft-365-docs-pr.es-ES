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
ms.openlocfilehash: 868fd141cda3b3d92464a2d9247780e0e74d6de8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198558"
---
# <a name="list-indicators-api"></a><span data-ttu-id="e9878-104">API de indicadores de lista</span><span class="sxs-lookup"><span data-stu-id="e9878-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9878-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e9878-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e9878-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e9878-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e9878-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e9878-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e9878-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="e9878-108">API description</span></span>
<span data-ttu-id="e9878-109">Recupera una colección de todos los [indicadores activos](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="e9878-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="e9878-110">Admite [consultas de OData V4](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="e9878-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="e9878-111">La consulta de OData ```$filter``` se admite en: ```indicatorValue``` , , , y ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` propiedades.</span><span class="sxs-lookup"><span data-stu-id="e9878-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="e9878-112">Vea ejemplos en [consultas de OData con Microsoft Defender para endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="e9878-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="e9878-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="e9878-113">Limitations</span></span>
1. <span data-ttu-id="e9878-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="e9878-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="e9878-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="e9878-115">Permissions</span></span>
<span data-ttu-id="e9878-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="e9878-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e9878-117">Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e9878-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="e9878-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="e9878-118">Permission type</span></span> |   <span data-ttu-id="e9878-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="e9878-119">Permission</span></span>  |   <span data-ttu-id="e9878-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="e9878-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e9878-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e9878-121">Application</span></span> |   <span data-ttu-id="e9878-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e9878-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="e9878-123">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="e9878-123">'Read and write Indicators'</span></span>
<span data-ttu-id="e9878-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e9878-124">Application</span></span> |   <span data-ttu-id="e9878-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e9878-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="e9878-126">'Leer y escribir todos los indicadores'</span><span class="sxs-lookup"><span data-stu-id="e9878-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="e9878-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="e9878-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="e9878-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e9878-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="e9878-129">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="e9878-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="e9878-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="e9878-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="e9878-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e9878-131">Request headers</span></span>

<span data-ttu-id="e9878-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="e9878-132">Name</span></span> | <span data-ttu-id="e9878-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="e9878-133">Type</span></span> | <span data-ttu-id="e9878-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9878-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="e9878-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="e9878-135">Authorization</span></span> | <span data-ttu-id="e9878-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="e9878-136">String</span></span> | <span data-ttu-id="e9878-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="e9878-137">Bearer {token}.</span></span> <span data-ttu-id="e9878-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="e9878-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e9878-139">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="e9878-139">Request body</span></span>
<span data-ttu-id="e9878-140">En blanco</span><span class="sxs-lookup"><span data-stu-id="e9878-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e9878-141">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e9878-141">Response</span></span>
<span data-ttu-id="e9878-142">Si se realiza correctamente, este método devuelve 200 código de respuesta Ok con una colección de [entidades Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="e9878-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="e9878-143">Si la aplicación tiene el permiso "Ti.ReadWrite.All", se expone a todos los indicadores.</span><span class="sxs-lookup"><span data-stu-id="e9878-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="e9878-144">De lo contrario, solo se mostrará a los indicadores que creó.</span><span class="sxs-lookup"><span data-stu-id="e9878-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="e9878-145">Ejemplo 1:</span><span class="sxs-lookup"><span data-stu-id="e9878-145">Example 1:</span></span>

<span data-ttu-id="e9878-146">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="e9878-146">**Request**</span></span>

<span data-ttu-id="e9878-147">Este es un ejemplo de una solicitud que obtiene todos los indicadores</span><span class="sxs-lookup"><span data-stu-id="e9878-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="e9878-148">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="e9878-148">**Response**</span></span>

<span data-ttu-id="e9878-149">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e9878-149">Here is an example of the response.</span></span>

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

## <a name="example-2"></a><span data-ttu-id="e9878-150">Ejemplo 2:</span><span class="sxs-lookup"><span data-stu-id="e9878-150">Example 2:</span></span>

<span data-ttu-id="e9878-151">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="e9878-151">**Request**</span></span>

<span data-ttu-id="e9878-152">Este es un ejemplo de una solicitud que obtiene todos los indicadores con la acción "AlertAndBlock".</span><span class="sxs-lookup"><span data-stu-id="e9878-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="e9878-153">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="e9878-153">**Response**</span></span>

<span data-ttu-id="e9878-154">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e9878-154">Here is an example of the response.</span></span>

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
