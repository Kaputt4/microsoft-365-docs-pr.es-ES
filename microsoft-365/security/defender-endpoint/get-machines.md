---
title: ENUMERAR API de máquinas
description: Obtenga información sobre cómo usar la API enumerar máquinas para recuperar una colección de máquinas que se han comunicado con Microsoft Defender para la nube de puntos de conexión.
keywords: api, api de gráfico, api admitidas, get, dispositivos
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f06973bc45ecac05c15d48afe5f0e2e9e7788f78
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770756"
---
# <a name="list-machines-api"></a><span data-ttu-id="142c9-104">ENUMERAR API de máquinas</span><span class="sxs-lookup"><span data-stu-id="142c9-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="142c9-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="142c9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="142c9-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="142c9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="142c9-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="142c9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="142c9-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="142c9-108">API description</span></span>
<span data-ttu-id="142c9-109">Recupera una colección de [máquinas](machine.md) que se han comunicado con Microsoft Defender para la nube de extremo.</span><span class="sxs-lookup"><span data-stu-id="142c9-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="142c9-110">Admite [consultas de OData V4](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="142c9-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="142c9-111">La consulta de OData `$filter` se admite en: `computerDnsName` , , , y `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="142c9-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="142c9-112">Vea ejemplos en [consultas de OData con Defender para endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="142c9-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="142c9-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="142c9-113">Limitations</span></span>
1. <span data-ttu-id="142c9-114">Puedes obtener dispositivos vistos por última vez según el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="142c9-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="142c9-115">El tamaño máximo de página es 10.000.</span><span class="sxs-lookup"><span data-stu-id="142c9-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="142c9-116">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="142c9-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="142c9-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="142c9-117">Permissions</span></span>

<span data-ttu-id="142c9-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="142c9-118">Permission type</span></span> |   <span data-ttu-id="142c9-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="142c9-119">Permission</span></span>  |   <span data-ttu-id="142c9-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="142c9-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="142c9-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="142c9-121">Application</span></span> |   <span data-ttu-id="142c9-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="142c9-122">Machine.Read.All</span></span> |  <span data-ttu-id="142c9-123">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="142c9-123">'Read all machine profiles'</span></span>
<span data-ttu-id="142c9-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="142c9-124">Application</span></span> |   <span data-ttu-id="142c9-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="142c9-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="142c9-126">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="142c9-126">'Read and write all machine information'</span></span>
<span data-ttu-id="142c9-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="142c9-127">Delegated (work or school account)</span></span> | <span data-ttu-id="142c9-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="142c9-128">Machine.Read</span></span> | <span data-ttu-id="142c9-129">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="142c9-129">'Read machine information'</span></span>
<span data-ttu-id="142c9-130">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="142c9-130">Delegated (work or school account)</span></span> | <span data-ttu-id="142c9-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="142c9-131">Machine.ReadWrite</span></span> | <span data-ttu-id="142c9-132">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="142c9-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="142c9-133">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="142c9-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="142c9-134">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="142c9-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="142c9-135">La respuesta incluirá solo dispositivos a los que el usuario tenga acceso, en función de la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="142c9-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="142c9-136">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="142c9-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="142c9-137">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="142c9-137">Request headers</span></span>

<span data-ttu-id="142c9-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="142c9-138">Name</span></span> | <span data-ttu-id="142c9-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="142c9-139">Type</span></span> | <span data-ttu-id="142c9-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="142c9-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="142c9-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="142c9-141">Authorization</span></span> | <span data-ttu-id="142c9-142">Cadena</span><span class="sxs-lookup"><span data-stu-id="142c9-142">String</span></span> | <span data-ttu-id="142c9-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="142c9-143">Bearer {token}.</span></span> <span data-ttu-id="142c9-144">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="142c9-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="142c9-145">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="142c9-145">Request body</span></span>
<span data-ttu-id="142c9-146">En blanco</span><span class="sxs-lookup"><span data-stu-id="142c9-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="142c9-147">Respuesta</span><span class="sxs-lookup"><span data-stu-id="142c9-147">Response</span></span>
<span data-ttu-id="142c9-148">Si se realiza correctamente y las máquinas existen: 200 Aceptar con una lista [de](machine.md) entidades de máquina en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="142c9-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="142c9-149">Si no hay máquinas recientes: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="142c9-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="142c9-150">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="142c9-150">Example</span></span>

<span data-ttu-id="142c9-151">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="142c9-151">**Request**</span></span>

<span data-ttu-id="142c9-152">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="142c9-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="142c9-153">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="142c9-153">**Response**</span></span>

<span data-ttu-id="142c9-154">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="142c9-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="142c9-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="142c9-155">Related topics</span></span>
- [<span data-ttu-id="142c9-156">Consultas de OData con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="142c9-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
