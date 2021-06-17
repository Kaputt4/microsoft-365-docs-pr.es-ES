---
title: OBTENER API de estadísticas de archivos
description: Obtenga información sobre cómo usar la API Obtener estadísticas de archivos para recuperar las estadísticas del archivo especificado en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, file, statistics
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
ms.openlocfilehash: 826b2ff25363f1d9a6276e1a42a10c1cf4995904
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998817"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="06485-104">OBTENER API de estadísticas de archivos</span><span class="sxs-lookup"><span data-stu-id="06485-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="06485-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="06485-105">**Applies to:**</span></span>
- [<span data-ttu-id="06485-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="06485-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="06485-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06485-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="06485-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="06485-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06485-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="06485-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="06485-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="06485-110">API description</span></span>
<span data-ttu-id="06485-111">Recupera las estadísticas del archivo dado.</span><span class="sxs-lookup"><span data-stu-id="06485-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="06485-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="06485-112">Limitations</span></span>
1. <span data-ttu-id="06485-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="06485-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="06485-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="06485-114">Permissions</span></span>
<span data-ttu-id="06485-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="06485-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="06485-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="06485-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="06485-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="06485-117">Permission type</span></span> |   <span data-ttu-id="06485-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="06485-118">Permission</span></span>  |   <span data-ttu-id="06485-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="06485-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="06485-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="06485-120">Application</span></span> |   <span data-ttu-id="06485-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="06485-121">File.Read.All</span></span> | <span data-ttu-id="06485-122">'Leer perfiles de archivo'</span><span class="sxs-lookup"><span data-stu-id="06485-122">'Read file profiles'</span></span>
<span data-ttu-id="06485-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="06485-123">Delegated (work or school account)</span></span> | <span data-ttu-id="06485-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="06485-124">File.Read.All</span></span> | <span data-ttu-id="06485-125">'Leer perfiles de archivo'</span><span class="sxs-lookup"><span data-stu-id="06485-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="06485-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="06485-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="06485-127">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="06485-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="06485-128">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="06485-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="06485-129">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="06485-129">Request headers</span></span>

<span data-ttu-id="06485-130">Nombre</span><span class="sxs-lookup"><span data-stu-id="06485-130">Name</span></span> | <span data-ttu-id="06485-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="06485-131">Type</span></span> | <span data-ttu-id="06485-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="06485-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="06485-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="06485-133">Authorization</span></span> | <span data-ttu-id="06485-134">String</span><span class="sxs-lookup"><span data-stu-id="06485-134">String</span></span> | <span data-ttu-id="06485-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="06485-135">Bearer {token}.</span></span> <span data-ttu-id="06485-136">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="06485-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="06485-137">Parámetros uri de solicitud</span><span class="sxs-lookup"><span data-stu-id="06485-137">Request URI parameters</span></span>

<span data-ttu-id="06485-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="06485-138">Name</span></span> | <span data-ttu-id="06485-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="06485-139">Type</span></span> | <span data-ttu-id="06485-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="06485-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="06485-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="06485-141">lookBackHours</span></span> | <span data-ttu-id="06485-142">Int32</span><span class="sxs-lookup"><span data-stu-id="06485-142">Int32</span></span> | <span data-ttu-id="06485-143">Define las horas que buscamos para obtener las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="06485-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="06485-144">El valor predeterminado es 30 días.</span><span class="sxs-lookup"><span data-stu-id="06485-144">Defaults to 30 days.</span></span> <span data-ttu-id="06485-145">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="06485-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="06485-146">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="06485-146">Request body</span></span>
<span data-ttu-id="06485-147">En blanco</span><span class="sxs-lookup"><span data-stu-id="06485-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="06485-148">Respuesta</span><span class="sxs-lookup"><span data-stu-id="06485-148">Response</span></span>
<span data-ttu-id="06485-149">Si se realiza correctamente y el archivo existe: 200 Aceptar con datos estadísticos en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="06485-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="06485-150">Si el archivo no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="06485-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="06485-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06485-151">Example</span></span>

<span data-ttu-id="06485-152">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="06485-152">**Request**</span></span>

<span data-ttu-id="06485-153">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="06485-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="06485-154">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="06485-154">**Response**</span></span>

<span data-ttu-id="06485-155">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="06485-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "organizationPrevalence": 14850,
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globallyPrevalence": 705012,
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
