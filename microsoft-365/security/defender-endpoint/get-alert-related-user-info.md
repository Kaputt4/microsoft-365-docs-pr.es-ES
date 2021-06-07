---
title: Obtener información de usuario relacionada con alertas
description: Obtenga información sobre cómo usar la API Obtener información de usuario relacionada con alertas para recuperar el usuario relacionado con una alerta específica en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api compatibles, get, alert, information, related, user
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
ms.openlocfilehash: e895885a638c60a845ed4857c682cd472e42615c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772322"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="4a4d4-104">Obtener api de información de usuario relacionada con alertas</span><span class="sxs-lookup"><span data-stu-id="4a4d4-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a4d4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4a4d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a4d4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4a4d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4a4d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a4d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="4a4d4-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="4a4d4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4a4d4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4a4d4-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="4a4d4-110">API description</span></span>
<span data-ttu-id="4a4d4-111">Recupera el usuario relacionado con una alerta específica.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="4a4d4-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="4a4d4-112">Limitations</span></span>
1. <span data-ttu-id="4a4d4-113">Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="4a4d4-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4a4d4-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="4a4d4-115">Permissions</span></span>
<span data-ttu-id="4a4d4-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4a4d4-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4a4d4-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4a4d4-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="4a4d4-118">Permission type</span></span> |   <span data-ttu-id="4a4d4-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="4a4d4-119">Permission</span></span>  |   <span data-ttu-id="4a4d4-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="4a4d4-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4a4d4-121">Application</span><span class="sxs-lookup"><span data-stu-id="4a4d4-121">Application</span></span> |   <span data-ttu-id="4a4d4-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="4a4d4-122">User.Read.All</span></span> | <span data-ttu-id="4a4d4-123">'Leer perfiles de usuario'</span><span class="sxs-lookup"><span data-stu-id="4a4d4-123">'Read user profiles'</span></span>
<span data-ttu-id="4a4d4-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="4a4d4-124">Delegated (work or school account)</span></span> | <span data-ttu-id="4a4d4-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="4a4d4-125">User.Read.All</span></span> | <span data-ttu-id="4a4d4-126">'Leer perfiles de usuario'</span><span class="sxs-lookup"><span data-stu-id="4a4d4-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="4a4d4-127">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="4a4d4-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4a4d4-128">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="4a4d4-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4a4d4-129">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="4a4d4-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4a4d4-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="4a4d4-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="4a4d4-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="4a4d4-131">Request headers</span></span>

<span data-ttu-id="4a4d4-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="4a4d4-132">Name</span></span> | <span data-ttu-id="4a4d4-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="4a4d4-133">Type</span></span> | <span data-ttu-id="4a4d4-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a4d4-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="4a4d4-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="4a4d4-135">Authorization</span></span> | <span data-ttu-id="4a4d4-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="4a4d4-136">String</span></span> | <span data-ttu-id="4a4d4-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-137">Bearer {token}.</span></span> <span data-ttu-id="4a4d4-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4a4d4-139">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="4a4d4-139">Request body</span></span>
<span data-ttu-id="4a4d4-140">En blanco</span><span class="sxs-lookup"><span data-stu-id="4a4d4-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4a4d4-141">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4a4d4-141">Response</span></span>
<span data-ttu-id="4a4d4-142">Si se realiza correctamente y alerta y existe un usuario: 200 Aceptar con el usuario en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="4a4d4-143">Si no se encuentra la alerta o el usuario: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4a4d4-144">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a4d4-144">Example</span></span>

<span data-ttu-id="4a4d4-145">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="4a4d4-145">**Request**</span></span>

<span data-ttu-id="4a4d4-146">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="4a4d4-147">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="4a4d4-147">**Response**</span></span>

<span data-ttu-id="4a4d4-148">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="4a4d4-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```
