---
title: Obtener API de usuarios de inicio de sesión de máquina
description: Obtenga información sobre cómo usar la API Obtener usuarios de inicio de sesión de máquina para recuperar una colección de usuarios que han iniciado sesión en un dispositivo en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, device, log on, users
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
ms.openlocfilehash: 634a381ca862dc7580d82168a4b9540acc0cd394
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229028"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="f240c-104">Obtener API de usuarios de inicio de sesión de máquina</span><span class="sxs-lookup"><span data-stu-id="f240c-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f240c-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f240c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="f240c-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f240c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f240c-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f240c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f240c-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="f240c-108">API description</span></span>
<span data-ttu-id="f240c-109">Recupera una colección de usuarios que han iniciado sesión en un dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="f240c-109">Retrieves a collection of logged on users on a specific device.</span></span>

## <a name="limitations"></a><span data-ttu-id="f240c-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="f240c-110">Limitations</span></span>
1. <span data-ttu-id="f240c-111">Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="f240c-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="f240c-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="f240c-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="f240c-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="f240c-113">Permissions</span></span>
<span data-ttu-id="f240c-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="f240c-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f240c-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f240c-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f240c-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="f240c-116">Permission type</span></span> |<span data-ttu-id="f240c-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="f240c-117">Permission</span></span>|<span data-ttu-id="f240c-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="f240c-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f240c-119">Application</span><span class="sxs-lookup"><span data-stu-id="f240c-119">Application</span></span> |<span data-ttu-id="f240c-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="f240c-120">User.Read.All</span></span> |<span data-ttu-id="f240c-121">'Leer perfiles de usuario'</span><span class="sxs-lookup"><span data-stu-id="f240c-121">'Read user profiles'</span></span>
<span data-ttu-id="f240c-122">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="f240c-122">Delegated (work or school account)</span></span> | <span data-ttu-id="f240c-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="f240c-123">User.Read.All</span></span> | <span data-ttu-id="f240c-124">'Leer perfiles de usuario'</span><span class="sxs-lookup"><span data-stu-id="f240c-124">'Read user profiles'</span></span>

> [!NOTE]
> <span data-ttu-id="f240c-125">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="f240c-125">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="f240c-126">El usuario debe tener al menos el siguiente permiso de función: "Ver datos".</span><span class="sxs-lookup"><span data-stu-id="f240c-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="f240c-127">Para obtener más información, vea [Create and manage roles](user-roles.md)).</span><span class="sxs-lookup"><span data-stu-id="f240c-127">For more information, see [Create and manage roles](user-roles.md)).</span></span>
> - <span data-ttu-id="f240c-128">La respuesta incluirá usuarios solo si el dispositivo es visible para el usuario, en función de la configuración del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f240c-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="f240c-129">Para obtener más información, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f240c-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="f240c-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="f240c-130">HTTP request</span></span>

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="f240c-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="f240c-131">Request headers</span></span>

<span data-ttu-id="f240c-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="f240c-132">Name</span></span> | <span data-ttu-id="f240c-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="f240c-133">Type</span></span> | <span data-ttu-id="f240c-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="f240c-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="f240c-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="f240c-135">Authorization</span></span> | <span data-ttu-id="f240c-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="f240c-136">String</span></span> | <span data-ttu-id="f240c-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="f240c-137">Bearer {token}.</span></span> <span data-ttu-id="f240c-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="f240c-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f240c-139">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="f240c-139">Request body</span></span>

<span data-ttu-id="f240c-140">En blanco</span><span class="sxs-lookup"><span data-stu-id="f240c-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f240c-141">Respuesta</span><span class="sxs-lookup"><span data-stu-id="f240c-141">Response</span></span>

<span data-ttu-id="f240c-142">Si se realiza correctamente y el dispositivo existe: 200 Aceptar con la lista de [entidades](user.md) de usuario en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f240c-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="f240c-143">Si no se encontró el dispositivo: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="f240c-143">If device was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="f240c-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f240c-144">Example</span></span>

### <a name="request"></a><span data-ttu-id="f240c-145">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f240c-145">Request</span></span>

<span data-ttu-id="f240c-146">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f240c-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a><span data-ttu-id="f240c-147">Respuesta</span><span class="sxs-lookup"><span data-stu-id="f240c-147">Response</span></span>

<span data-ttu-id="f240c-148">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f240c-148">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
