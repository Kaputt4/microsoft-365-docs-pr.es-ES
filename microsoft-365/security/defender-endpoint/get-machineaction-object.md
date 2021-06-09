---
title: Obtener API de objetos MachineAction
description: Obtenga información sobre cómo usar la API Get MachineAction para recuperar una acción de máquina específica por su identificador en Microsoft Defender para endpoint.
keywords: apis, api de gráfico, api admitidas, objeto machineaction
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
ms.openlocfilehash: dcb00d0d2afc7f873ea9c4afa3174ac46babf879
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770786"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="1c56d-104">Obtener api machineAction</span><span class="sxs-lookup"><span data-stu-id="1c56d-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c56d-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1c56d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1c56d-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="1c56d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1c56d-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1c56d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1c56d-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="1c56d-108">API description</span></span>
<span data-ttu-id="1c56d-109">Recupera una acción [de máquina específica](machineaction.md) por su identificador.</span><span class="sxs-lookup"><span data-stu-id="1c56d-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="1c56d-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="1c56d-110">Limitations</span></span>
1. <span data-ttu-id="1c56d-111">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="1c56d-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1c56d-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="1c56d-112">Permissions</span></span>
<span data-ttu-id="1c56d-113">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="1c56d-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1c56d-114">Para obtener más información, incluido cómo elegir permisos, consulte [Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1c56d-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1c56d-115">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="1c56d-115">Permission type</span></span> |   <span data-ttu-id="1c56d-116">Permiso</span><span class="sxs-lookup"><span data-stu-id="1c56d-116">Permission</span></span>  |   <span data-ttu-id="1c56d-117">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="1c56d-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1c56d-118">Aplicación</span><span class="sxs-lookup"><span data-stu-id="1c56d-118">Application</span></span> |   <span data-ttu-id="1c56d-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="1c56d-119">Machine.Read.All</span></span> |  <span data-ttu-id="1c56d-120">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="1c56d-120">'Read all machine profiles'</span></span>
<span data-ttu-id="1c56d-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="1c56d-121">Application</span></span> |   <span data-ttu-id="1c56d-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1c56d-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="1c56d-123">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="1c56d-123">'Read and write all machine information'</span></span>
<span data-ttu-id="1c56d-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="1c56d-124">Delegated (work or school account)</span></span> | <span data-ttu-id="1c56d-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="1c56d-125">Machine.Read</span></span> | <span data-ttu-id="1c56d-126">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="1c56d-126">'Read machine information'</span></span>
<span data-ttu-id="1c56d-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="1c56d-127">Delegated (work or school account)</span></span> | <span data-ttu-id="1c56d-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1c56d-128">Machine.ReadWrite</span></span> | <span data-ttu-id="1c56d-129">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="1c56d-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="1c56d-130">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="1c56d-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1c56d-131">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="1c56d-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1c56d-132">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="1c56d-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="1c56d-133">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="1c56d-133">Request headers</span></span>

<span data-ttu-id="1c56d-134">Nombre</span><span class="sxs-lookup"><span data-stu-id="1c56d-134">Name</span></span> | <span data-ttu-id="1c56d-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="1c56d-135">Type</span></span> | <span data-ttu-id="1c56d-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c56d-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="1c56d-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="1c56d-137">Authorization</span></span> | <span data-ttu-id="1c56d-138">Cadena</span><span class="sxs-lookup"><span data-stu-id="1c56d-138">String</span></span> | <span data-ttu-id="1c56d-139">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="1c56d-139">Bearer {token}.</span></span> <span data-ttu-id="1c56d-140">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="1c56d-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1c56d-141">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="1c56d-141">Request body</span></span>
<span data-ttu-id="1c56d-142">En blanco</span><span class="sxs-lookup"><span data-stu-id="1c56d-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1c56d-143">Respuesta</span><span class="sxs-lookup"><span data-stu-id="1c56d-143">Response</span></span>
<span data-ttu-id="1c56d-144">Si se realiza correctamente, este método devuelve 200, código de respuesta Ok con una [entidad Machine Action.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="1c56d-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="1c56d-145">Si no se encontró la entidad de acción de la máquina con el identificador especificado: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="1c56d-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="1c56d-146">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1c56d-146">Example</span></span>

<span data-ttu-id="1c56d-147">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="1c56d-147">**Request**</span></span>

<span data-ttu-id="1c56d-148">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1c56d-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="1c56d-149">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="1c56d-149">**Response**</span></span>

<span data-ttu-id="1c56d-150">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="1c56d-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
