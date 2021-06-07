---
title: Obtener información de dominios relacionada con alertas
description: Recupera todos los dominios relacionados con una alerta específica con Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, obtener información de alerta, información de alerta, dominio relacionado
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
ms.openlocfilehash: a5f3db65b42d8dc98c11f2ef2c3c5d509340e386
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771266"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="3f339-104">Obtener API de información de dominio relacionada con alertas</span><span class="sxs-lookup"><span data-stu-id="3f339-104">Get alert related domain information API</span></span>

<span data-ttu-id="3f339-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3f339-105">**Applies to:**</span></span> 
- [<span data-ttu-id="3f339-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3f339-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="3f339-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="3f339-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3f339-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="3f339-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3f339-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="3f339-109">API description</span></span>
<span data-ttu-id="3f339-110">Recupera todos los dominios relacionados con una alerta específica.</span><span class="sxs-lookup"><span data-stu-id="3f339-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="3f339-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="3f339-111">Limitations</span></span>
1. <span data-ttu-id="3f339-112">Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="3f339-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3f339-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="3f339-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3f339-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="3f339-114">Permissions</span></span>
<span data-ttu-id="3f339-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="3f339-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3f339-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3f339-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3f339-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="3f339-117">Permission type</span></span> | <span data-ttu-id="3f339-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="3f339-118">Permission</span></span> | <span data-ttu-id="3f339-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="3f339-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3f339-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="3f339-120">Application</span></span> | <span data-ttu-id="3f339-121">DIRECCIÓN URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="3f339-121">URL.Read.All</span></span> | <span data-ttu-id="3f339-122">'Leer direcciones URL'</span><span class="sxs-lookup"><span data-stu-id="3f339-122">'Read URLs'</span></span>
<span data-ttu-id="3f339-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="3f339-123">Delegated (work or school account)</span></span> | <span data-ttu-id="3f339-124">DIRECCIÓN URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="3f339-124">URL.Read.All</span></span> | <span data-ttu-id="3f339-125">'Leer direcciones URL'</span><span class="sxs-lookup"><span data-stu-id="3f339-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="3f339-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="3f339-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3f339-127">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="3f339-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3f339-128">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="3f339-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3f339-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="3f339-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="3f339-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="3f339-130">Request headers</span></span>

<span data-ttu-id="3f339-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="3f339-131">Name</span></span> | <span data-ttu-id="3f339-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="3f339-132">Type</span></span> | <span data-ttu-id="3f339-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f339-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="3f339-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="3f339-134">Authorization</span></span> | <span data-ttu-id="3f339-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="3f339-135">String</span></span> | <span data-ttu-id="3f339-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="3f339-136">Bearer {token}.</span></span> <span data-ttu-id="3f339-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="3f339-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3f339-138">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="3f339-138">Request body</span></span>
<span data-ttu-id="3f339-139">En blanco</span><span class="sxs-lookup"><span data-stu-id="3f339-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3f339-140">Respuesta</span><span class="sxs-lookup"><span data-stu-id="3f339-140">Response</span></span>
<span data-ttu-id="3f339-141">Si se realiza correctamente y existen alertas y dominio: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="3f339-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="3f339-142">Si no se encuentra la alerta: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="3f339-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="3f339-143">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3f339-143">Example</span></span>

<span data-ttu-id="3f339-144">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="3f339-144">**Request**</span></span>

<span data-ttu-id="3f339-145">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3f339-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="3f339-146">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="3f339-146">**Response**</span></span>

<span data-ttu-id="3f339-147">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="3f339-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
