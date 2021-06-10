---
title: Obtener API de información de usuario
description: Obtenga información sobre cómo usar la API Obtener información del usuario para recuperar una entidad User por clave o nombre de usuario en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, obtener, usuario, información de usuario
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198546"
---
# <a name="get-user-information-api"></a><span data-ttu-id="f84e4-104">Obtener API de información de usuario</span><span class="sxs-lookup"><span data-stu-id="f84e4-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f84e4-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f84e4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f84e4-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f84e4-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f84e4-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f84e4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="f84e4-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f84e4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f84e4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f84e4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="f84e4-110">Recuperar una entidad User por clave (nombre de usuario).</span><span class="sxs-lookup"><span data-stu-id="f84e4-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="f84e4-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="f84e4-111">Permissions</span></span>
<span data-ttu-id="f84e4-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="f84e4-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f84e4-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f84e4-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f84e4-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="f84e4-114">Permission type</span></span> |   <span data-ttu-id="f84e4-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="f84e4-115">Permission</span></span>  |   <span data-ttu-id="f84e4-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="f84e4-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f84e4-117">Application</span><span class="sxs-lookup"><span data-stu-id="f84e4-117">Application</span></span> |   <span data-ttu-id="f84e4-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="f84e4-118">User.Read.All</span></span> | <span data-ttu-id="f84e4-119">'Leer todos los perfiles de usuario'</span><span class="sxs-lookup"><span data-stu-id="f84e4-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="f84e4-120">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="f84e4-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="f84e4-121">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="f84e4-121">Request headers</span></span>

<span data-ttu-id="f84e4-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="f84e4-122">Name</span></span> | <span data-ttu-id="f84e4-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="f84e4-123">Type</span></span> | <span data-ttu-id="f84e4-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="f84e4-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="f84e4-125">Authorization</span><span class="sxs-lookup"><span data-stu-id="f84e4-125">Authorization</span></span> | <span data-ttu-id="f84e4-126">Cadena</span><span class="sxs-lookup"><span data-stu-id="f84e4-126">String</span></span> | <span data-ttu-id="f84e4-127">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="f84e4-127">Bearer {token}.</span></span> <span data-ttu-id="f84e4-128">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="f84e4-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f84e4-129">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="f84e4-129">Request body</span></span>
<span data-ttu-id="f84e4-130">En blanco</span><span class="sxs-lookup"><span data-stu-id="f84e4-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f84e4-131">Respuesta</span><span class="sxs-lookup"><span data-stu-id="f84e4-131">Response</span></span>
<span data-ttu-id="f84e4-132">Si se realiza correctamente y el usuario existe: 200 Aceptar con [la entidad de](user.md) usuario en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f84e4-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="f84e4-133">Si el usuario no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="f84e4-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f84e4-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f84e4-134">Example</span></span>

<span data-ttu-id="f84e4-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="f84e4-135">**Request**</span></span>

<span data-ttu-id="f84e4-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f84e4-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="f84e4-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="f84e4-137">**Response**</span></span>

<span data-ttu-id="f84e4-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f84e4-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
