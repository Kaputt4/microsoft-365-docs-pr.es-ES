---
title: Obtener información de máquina relacionada con alertas
description: Recupera todos los dispositivos relacionados con una alerta específica con Microsoft Defender para endpoint.
keywords: api, api de gráfico, api admitidas, obtener información de alerta, información de alertas, dispositivo relacionado
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
ms.openlocfilehash: ef10d2bd7193fc7b4a1604658f496ef38ef33555
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772355"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="c6538-104">Obtener API de información de máquina relacionada con alertas</span><span class="sxs-lookup"><span data-stu-id="c6538-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c6538-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c6538-105">**Applies to:**</span></span>
- [<span data-ttu-id="c6538-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c6538-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c6538-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6538-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c6538-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="c6538-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c6538-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c6538-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c6538-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="c6538-110">API description</span></span>
<span data-ttu-id="c6538-111">Recupera El [dispositivo](machine.md) relacionado con una alerta específica.</span><span class="sxs-lookup"><span data-stu-id="c6538-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="c6538-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="c6538-112">Limitations</span></span>
1. <span data-ttu-id="c6538-113">Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="c6538-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="c6538-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="c6538-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c6538-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="c6538-115">Permissions</span></span>
<span data-ttu-id="c6538-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="c6538-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c6538-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c6538-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c6538-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="c6538-118">Permission type</span></span> |   <span data-ttu-id="c6538-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="c6538-119">Permission</span></span>  |   <span data-ttu-id="c6538-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="c6538-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c6538-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="c6538-121">Application</span></span> |   <span data-ttu-id="c6538-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="c6538-122">Machine.Read.All</span></span> |  <span data-ttu-id="c6538-123">'Leer toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="c6538-123">'Read all machine information'</span></span>
<span data-ttu-id="c6538-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="c6538-124">Application</span></span> |   <span data-ttu-id="c6538-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c6538-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="c6538-126">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="c6538-126">'Read and write all machine information'</span></span>
<span data-ttu-id="c6538-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="c6538-127">Delegated (work or school account)</span></span> | <span data-ttu-id="c6538-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="c6538-128">Machine.Read</span></span> | <span data-ttu-id="c6538-129">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="c6538-129">'Read machine information'</span></span>
<span data-ttu-id="c6538-130">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="c6538-130">Delegated (work or school account)</span></span> | <span data-ttu-id="c6538-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c6538-131">Machine.ReadWrite</span></span> | <span data-ttu-id="c6538-132">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="c6538-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="c6538-133">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="c6538-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c6538-134">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="c6538-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c6538-135">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="c6538-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c6538-136">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="c6538-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="c6538-137">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="c6538-137">Request headers</span></span>

<span data-ttu-id="c6538-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="c6538-138">Name</span></span> | <span data-ttu-id="c6538-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="c6538-139">Type</span></span> | <span data-ttu-id="c6538-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6538-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="c6538-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="c6538-141">Authorization</span></span> | <span data-ttu-id="c6538-142">Cadena</span><span class="sxs-lookup"><span data-stu-id="c6538-142">String</span></span> | <span data-ttu-id="c6538-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="c6538-143">Bearer {token}.</span></span> <span data-ttu-id="c6538-144">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="c6538-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c6538-145">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="c6538-145">Request body</span></span>
<span data-ttu-id="c6538-146">En blanco</span><span class="sxs-lookup"><span data-stu-id="c6538-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c6538-147">Respuesta</span><span class="sxs-lookup"><span data-stu-id="c6538-147">Response</span></span>
<span data-ttu-id="c6538-148">Si se realiza correctamente y la alerta y el dispositivo existen: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="c6538-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="c6538-149">Si no se encuentra la alerta o no se encuentra el dispositivo: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="c6538-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="c6538-150">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c6538-150">Example</span></span>

<span data-ttu-id="c6538-151">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="c6538-151">**Request**</span></span>

<span data-ttu-id="c6538-152">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c6538-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="c6538-153">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="c6538-153">**Response**</span></span>

<span data-ttu-id="c6538-154">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c6538-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
