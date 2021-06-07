---
title: Obtener información de IP relacionada con alertas
description: Recupera todas las IP relacionadas con una alerta específica mediante Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api compatibles, obtener información de alerta, información de alertas, ip relacionada
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
ms.openlocfilehash: b6ac9746ff82f81772505daac7d7f36249687d7d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772334"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="701bf-104">Obtener API de información de IP relacionadas con alertas</span><span class="sxs-lookup"><span data-stu-id="701bf-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="701bf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="701bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="701bf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="701bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="701bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="701bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="701bf-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="701bf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="701bf-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="701bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="701bf-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="701bf-110">API description</span></span>
<span data-ttu-id="701bf-111">Recupera todas las IP relacionadas con una alerta específica.</span><span class="sxs-lookup"><span data-stu-id="701bf-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="701bf-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="701bf-112">Limitations</span></span>
1. <span data-ttu-id="701bf-113">Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="701bf-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="701bf-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="701bf-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="701bf-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="701bf-115">Permissions</span></span>
<span data-ttu-id="701bf-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="701bf-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="701bf-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="701bf-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="701bf-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="701bf-118">Permission type</span></span> |   <span data-ttu-id="701bf-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="701bf-119">Permission</span></span>  |   <span data-ttu-id="701bf-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="701bf-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="701bf-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="701bf-121">Application</span></span> |   <span data-ttu-id="701bf-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="701bf-122">Ip.Read.All</span></span> |   <span data-ttu-id="701bf-123">'Leer perfiles de dirección IP'</span><span class="sxs-lookup"><span data-stu-id="701bf-123">'Read IP address profiles'</span></span>
<span data-ttu-id="701bf-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="701bf-124">Delegated (work or school account)</span></span> | <span data-ttu-id="701bf-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="701bf-125">Ip.Read.All</span></span> |  <span data-ttu-id="701bf-126">'Leer perfiles de dirección IP'</span><span class="sxs-lookup"><span data-stu-id="701bf-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="701bf-127">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="701bf-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="701bf-128">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="701bf-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="701bf-129">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="701bf-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="701bf-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="701bf-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="701bf-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="701bf-131">Request headers</span></span>

<span data-ttu-id="701bf-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="701bf-132">Name</span></span> | <span data-ttu-id="701bf-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="701bf-133">Type</span></span> | <span data-ttu-id="701bf-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="701bf-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="701bf-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="701bf-135">Authorization</span></span> | <span data-ttu-id="701bf-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="701bf-136">String</span></span> | <span data-ttu-id="701bf-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="701bf-137">Bearer {token}.</span></span> <span data-ttu-id="701bf-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="701bf-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="701bf-139">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="701bf-139">Request body</span></span>
<span data-ttu-id="701bf-140">En blanco</span><span class="sxs-lookup"><span data-stu-id="701bf-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="701bf-141">Respuesta</span><span class="sxs-lookup"><span data-stu-id="701bf-141">Response</span></span>
<span data-ttu-id="701bf-142">Si se realiza correctamente y se alerta y existe una IP: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="701bf-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="701bf-143">Si no se encuentra la alerta: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="701bf-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="701bf-144">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="701bf-144">Example</span></span>

<span data-ttu-id="701bf-145">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="701bf-145">**Request**</span></span>

<span data-ttu-id="701bf-146">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="701bf-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="701bf-147">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="701bf-147">**Response**</span></span>

<span data-ttu-id="701bf-148">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="701bf-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```
