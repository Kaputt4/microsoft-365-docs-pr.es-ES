---
title: API enumerar investigaciones
description: Usar esta API para crear llamadas relacionadas con obtener la colección Investigations
keywords: apis, api de gráficos, api admitidas, colección Investigations
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770150"
---
# <a name="list-investigations-api"></a><span data-ttu-id="9b4c0-104">API enumerar investigaciones</span><span class="sxs-lookup"><span data-stu-id="9b4c0-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9b4c0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9b4c0-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b4c0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9b4c0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9b4c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b4c0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9b4c0-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="9b4c0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b4c0-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="9b4c0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9b4c0-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="9b4c0-110">API description</span></span>
<span data-ttu-id="9b4c0-111">Recupera una colección de [Investigaciones](investigation.md).</span><span class="sxs-lookup"><span data-stu-id="9b4c0-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="9b4c0-112">Admite [consultas de OData V4](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="9b4c0-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="9b4c0-113">La consulta de OData ```$filter``` se admite en: ```startTime``` , y ```state``` ```machineId``` ```triggeringAlertId``` propiedades.</span><span class="sxs-lookup"><span data-stu-id="9b4c0-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="9b4c0-114">Vea ejemplos en [consultas de OData con Microsoft Defender para endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="9b4c0-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="9b4c0-115">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="9b4c0-115">Limitations</span></span>
1. <span data-ttu-id="9b4c0-116">El tamaño máximo de página es 10.000.</span><span class="sxs-lookup"><span data-stu-id="9b4c0-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="9b4c0-117">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="9b4c0-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="9b4c0-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="9b4c0-118">Permissions</span></span>
<span data-ttu-id="9b4c0-119">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="9b4c0-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9b4c0-120">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9b4c0-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9b4c0-121">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="9b4c0-121">Permission type</span></span> |   <span data-ttu-id="9b4c0-122">Permiso</span><span class="sxs-lookup"><span data-stu-id="9b4c0-122">Permission</span></span>  |   <span data-ttu-id="9b4c0-123">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="9b4c0-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9b4c0-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="9b4c0-124">Application</span></span> |   <span data-ttu-id="9b4c0-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="9b4c0-125">Alert.Read.All</span></span> |    <span data-ttu-id="9b4c0-126">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="9b4c0-126">'Read all alerts'</span></span>
<span data-ttu-id="9b4c0-127">Aplicación</span><span class="sxs-lookup"><span data-stu-id="9b4c0-127">Application</span></span> |   <span data-ttu-id="9b4c0-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9b4c0-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="9b4c0-129">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="9b4c0-129">'Read and write all alerts'</span></span>
<span data-ttu-id="9b4c0-130">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="9b4c0-130">Delegated (work or school account)</span></span> | <span data-ttu-id="9b4c0-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="9b4c0-131">Alert.Read</span></span> | <span data-ttu-id="9b4c0-132">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="9b4c0-132">'Read alerts'</span></span>
<span data-ttu-id="9b4c0-133">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="9b4c0-133">Delegated (work or school account)</span></span> | <span data-ttu-id="9b4c0-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9b4c0-134">Alert.ReadWrite</span></span> | <span data-ttu-id="9b4c0-135">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="9b4c0-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="9b4c0-136">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="9b4c0-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9b4c0-137">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="9b4c0-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9b4c0-138">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="9b4c0-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="9b4c0-139">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="9b4c0-139">Request headers</span></span>

<span data-ttu-id="9b4c0-140">Nombre</span><span class="sxs-lookup"><span data-stu-id="9b4c0-140">Name</span></span> | <span data-ttu-id="9b4c0-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="9b4c0-141">Type</span></span> | <span data-ttu-id="9b4c0-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b4c0-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="9b4c0-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="9b4c0-143">Authorization</span></span> | <span data-ttu-id="9b4c0-144">Cadena</span><span class="sxs-lookup"><span data-stu-id="9b4c0-144">String</span></span> | <span data-ttu-id="9b4c0-145">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="9b4c0-145">Bearer {token}.</span></span> <span data-ttu-id="9b4c0-146">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="9b4c0-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9b4c0-147">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="9b4c0-147">Request body</span></span>
<span data-ttu-id="9b4c0-148">En blanco</span><span class="sxs-lookup"><span data-stu-id="9b4c0-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9b4c0-149">Respuesta</span><span class="sxs-lookup"><span data-stu-id="9b4c0-149">Response</span></span>
<span data-ttu-id="9b4c0-150">Si se realiza correctamente, este método devuelve 200 código de respuesta Ok con una colección de entidades [investigations.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="9b4c0-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="9b4c0-151">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9b4c0-151">Example</span></span>

<span data-ttu-id="9b4c0-152">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="9b4c0-152">**Request**</span></span>

<span data-ttu-id="9b4c0-153">Este es un ejemplo de una solicitud para obtener todas las investigaciones:</span><span class="sxs-lookup"><span data-stu-id="9b4c0-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="9b4c0-154">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="9b4c0-154">**Response**</span></span>

<span data-ttu-id="9b4c0-155">Este es un ejemplo de la respuesta:</span><span class="sxs-lookup"><span data-stu-id="9b4c0-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
