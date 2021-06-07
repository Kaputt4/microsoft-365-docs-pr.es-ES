---
title: Enumerar api machineActions
description: Obtenga información sobre cómo usar la API List MachineActions para recuperar una colección de acciones de máquina en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, colección machineaction
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
ms.openlocfilehash: 2ee9a4e29dded3e299ffbb2c2997fd02f32d1abf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771122"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="bfcfd-104">Enumerar API MachineActions</span><span class="sxs-lookup"><span data-stu-id="bfcfd-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bfcfd-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bfcfd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bfcfd-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="bfcfd-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bfcfd-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="bfcfd-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="bfcfd-108">API description</span></span>
<span data-ttu-id="bfcfd-109">Recupera una colección de [acciones de máquina](machineaction.md).</span><span class="sxs-lookup"><span data-stu-id="bfcfd-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="bfcfd-110">Admite [consultas de OData V4](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="bfcfd-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="bfcfd-111">La consulta de OData ```$filter``` se admite en: ```status``` , , y ```machineId``` ```type``` ```requestor``` ```creationDateTimeUtc``` propiedades.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="bfcfd-112">Vea ejemplos en [consultas de OData con Microsoft Defender para endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="bfcfd-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="bfcfd-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="bfcfd-113">Limitations</span></span>
1. <span data-ttu-id="bfcfd-114">El tamaño máximo de página es 10.000.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="bfcfd-115">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="bfcfd-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="bfcfd-116">Permissions</span></span>
<span data-ttu-id="bfcfd-117">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bfcfd-118">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bfcfd-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bfcfd-119">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="bfcfd-119">Permission type</span></span> |   <span data-ttu-id="bfcfd-120">Permiso</span><span class="sxs-lookup"><span data-stu-id="bfcfd-120">Permission</span></span>  |   <span data-ttu-id="bfcfd-121">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="bfcfd-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bfcfd-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="bfcfd-122">Application</span></span> |   <span data-ttu-id="bfcfd-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="bfcfd-123">Machine.Read.All</span></span> |  <span data-ttu-id="bfcfd-124">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="bfcfd-124">'Read all machine profiles'</span></span>
<span data-ttu-id="bfcfd-125">Aplicación</span><span class="sxs-lookup"><span data-stu-id="bfcfd-125">Application</span></span> |   <span data-ttu-id="bfcfd-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="bfcfd-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="bfcfd-127">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="bfcfd-127">'Read and write all machine information'</span></span>
<span data-ttu-id="bfcfd-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="bfcfd-128">Delegated (work or school account)</span></span> | <span data-ttu-id="bfcfd-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="bfcfd-129">Machine.Read</span></span> | <span data-ttu-id="bfcfd-130">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="bfcfd-130">'Read machine information'</span></span>
<span data-ttu-id="bfcfd-131">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="bfcfd-131">Delegated (work or school account)</span></span> | <span data-ttu-id="bfcfd-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="bfcfd-132">Machine.ReadWrite</span></span> | <span data-ttu-id="bfcfd-133">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="bfcfd-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="bfcfd-134">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="bfcfd-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bfcfd-135">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="bfcfd-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bfcfd-136">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="bfcfd-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="bfcfd-137">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="bfcfd-137">Request headers</span></span>

<span data-ttu-id="bfcfd-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="bfcfd-138">Name</span></span> | <span data-ttu-id="bfcfd-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="bfcfd-139">Type</span></span> | <span data-ttu-id="bfcfd-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfcfd-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="bfcfd-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="bfcfd-141">Authorization</span></span> | <span data-ttu-id="bfcfd-142">Cadena</span><span class="sxs-lookup"><span data-stu-id="bfcfd-142">String</span></span> | <span data-ttu-id="bfcfd-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-143">Bearer {token}.</span></span> <span data-ttu-id="bfcfd-144">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="bfcfd-145">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="bfcfd-145">Request body</span></span>
<span data-ttu-id="bfcfd-146">En blanco</span><span class="sxs-lookup"><span data-stu-id="bfcfd-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="bfcfd-147">Respuesta</span><span class="sxs-lookup"><span data-stu-id="bfcfd-147">Response</span></span>
<span data-ttu-id="bfcfd-148">Si se realiza correctamente, este método devuelve 200 código de respuesta Ok con una colección de [entidades machineAction.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="bfcfd-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="bfcfd-149">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="bfcfd-149">Example 1</span></span>

<span data-ttu-id="bfcfd-150">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="bfcfd-150">**Request**</span></span>

<span data-ttu-id="bfcfd-151">Este es un ejemplo de la solicitud en una organización que tiene tres MachineActions.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="bfcfd-152">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="bfcfd-152">**Response**</span></span>

<span data-ttu-id="bfcfd-153">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="bfcfd-154">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="bfcfd-154">Example 2</span></span>

<span data-ttu-id="bfcfd-155">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="bfcfd-155">**Request**</span></span>

<span data-ttu-id="bfcfd-156">Este es un ejemplo de una solicitud que filtra MachineActions por id. de máquina y muestra las dos MachineActions más recientes.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="bfcfd-157">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="bfcfd-157">**Response**</span></span>

<span data-ttu-id="bfcfd-158">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="bfcfd-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="bfcfd-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bfcfd-159">Related topics</span></span>
- [<span data-ttu-id="bfcfd-160">Consultas de OData con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="bfcfd-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
