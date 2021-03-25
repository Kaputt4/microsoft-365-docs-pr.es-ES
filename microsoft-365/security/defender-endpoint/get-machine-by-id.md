---
title: Obtener api de máquina por id.
description: Obtén información sobre cómo usar la API Obtener máquina por id. para recuperar una máquina por su id. de dispositivo o nombre de equipo en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, dispositivos, entidad, id
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
ms.openlocfilehash: 29423230d0d8d4baaa1acca9a3661dc3436f303d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200104"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="299f7-104">Obtener api de máquina por id.</span><span class="sxs-lookup"><span data-stu-id="299f7-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="299f7-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="299f7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="299f7-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="299f7-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="299f7-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="299f7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="299f7-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="299f7-108">API description</span></span>
<span data-ttu-id="299f7-109">Recupera un equipo [específico por](machine.md) su identificador de dispositivo o el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="299f7-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="299f7-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="299f7-110">Limitations</span></span>
1. <span data-ttu-id="299f7-111">Puedes obtener dispositivos vistos por última vez de acuerdo con la directiva de retención configurada.</span><span class="sxs-lookup"><span data-stu-id="299f7-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="299f7-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="299f7-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="299f7-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="299f7-113">Permissions</span></span>
<span data-ttu-id="299f7-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="299f7-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="299f7-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="299f7-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="299f7-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="299f7-116">Permission type</span></span> |   <span data-ttu-id="299f7-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="299f7-117">Permission</span></span>  |   <span data-ttu-id="299f7-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="299f7-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="299f7-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="299f7-119">Application</span></span> |   <span data-ttu-id="299f7-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="299f7-120">Machine.Read.All</span></span> |  <span data-ttu-id="299f7-121">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="299f7-121">'Read all machine profiles'</span></span>
<span data-ttu-id="299f7-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="299f7-122">Application</span></span> |   <span data-ttu-id="299f7-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299f7-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="299f7-124">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="299f7-124">'Read and write all machine information'</span></span>
<span data-ttu-id="299f7-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="299f7-125">Delegated (work or school account)</span></span> | <span data-ttu-id="299f7-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="299f7-126">Machine.Read</span></span> | <span data-ttu-id="299f7-127">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="299f7-127">'Read machine information'</span></span>
<span data-ttu-id="299f7-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="299f7-128">Delegated (work or school account)</span></span> | <span data-ttu-id="299f7-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="299f7-129">Machine.ReadWrite</span></span> | <span data-ttu-id="299f7-130">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="299f7-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="299f7-131">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="299f7-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="299f7-132">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="299f7-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="299f7-133">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="299f7-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="299f7-134">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="299f7-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="299f7-135">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="299f7-135">Request headers</span></span>

<span data-ttu-id="299f7-136">Nombre</span><span class="sxs-lookup"><span data-stu-id="299f7-136">Name</span></span> | <span data-ttu-id="299f7-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="299f7-137">Type</span></span> | <span data-ttu-id="299f7-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="299f7-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="299f7-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="299f7-139">Authorization</span></span> | <span data-ttu-id="299f7-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="299f7-140">String</span></span> | <span data-ttu-id="299f7-141">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="299f7-141">Bearer {token}.</span></span> <span data-ttu-id="299f7-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="299f7-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="299f7-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="299f7-143">Request body</span></span>
<span data-ttu-id="299f7-144">En blanco</span><span class="sxs-lookup"><span data-stu-id="299f7-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="299f7-145">Respuesta</span><span class="sxs-lookup"><span data-stu-id="299f7-145">Response</span></span>
<span data-ttu-id="299f7-146">Si se realiza correctamente y el dispositivo existe: 200 Aceptar con la [entidad de la](machine.md) máquina en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="299f7-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="299f7-147">Si no se encontró el equipo con el identificador especificado: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="299f7-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="299f7-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="299f7-148">Example</span></span>

<span data-ttu-id="299f7-149">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="299f7-149">**Request**</span></span>

<span data-ttu-id="299f7-150">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="299f7-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="299f7-151">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="299f7-151">**Response**</span></span>

<span data-ttu-id="299f7-152">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="299f7-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
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

```
