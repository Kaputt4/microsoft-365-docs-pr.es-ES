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
ms.technology: mde
ms.openlocfilehash: ff43f6c46d89bc92cd1dc2a4fb0f329757b8f69e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167123"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="62d77-104">OBTENER API de estadísticas de archivos</span><span class="sxs-lookup"><span data-stu-id="62d77-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="62d77-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="62d77-105">**Applies to:**</span></span>
- [<span data-ttu-id="62d77-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="62d77-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="62d77-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62d77-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="62d77-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="62d77-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="62d77-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="62d77-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="62d77-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="62d77-110">API description</span></span>
<span data-ttu-id="62d77-111">Recupera las estadísticas del archivo dado.</span><span class="sxs-lookup"><span data-stu-id="62d77-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="62d77-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="62d77-112">Limitations</span></span>
1. <span data-ttu-id="62d77-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="62d77-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="62d77-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="62d77-114">Permissions</span></span>
<span data-ttu-id="62d77-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="62d77-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="62d77-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="62d77-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="62d77-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="62d77-117">Permission type</span></span> |   <span data-ttu-id="62d77-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="62d77-118">Permission</span></span>  |   <span data-ttu-id="62d77-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="62d77-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="62d77-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="62d77-120">Application</span></span> |   <span data-ttu-id="62d77-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="62d77-121">File.Read.All</span></span> | <span data-ttu-id="62d77-122">'Leer perfiles de archivo'</span><span class="sxs-lookup"><span data-stu-id="62d77-122">'Read file profiles'</span></span>
<span data-ttu-id="62d77-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="62d77-123">Delegated (work or school account)</span></span> | <span data-ttu-id="62d77-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="62d77-124">File.Read.All</span></span> | <span data-ttu-id="62d77-125">'Leer perfiles de archivo'</span><span class="sxs-lookup"><span data-stu-id="62d77-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="62d77-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="62d77-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="62d77-127">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="62d77-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="62d77-128">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="62d77-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="62d77-129">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="62d77-129">Request headers</span></span>

<span data-ttu-id="62d77-130">Nombre</span><span class="sxs-lookup"><span data-stu-id="62d77-130">Name</span></span> | <span data-ttu-id="62d77-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="62d77-131">Type</span></span> | <span data-ttu-id="62d77-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="62d77-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="62d77-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="62d77-133">Authorization</span></span> | <span data-ttu-id="62d77-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="62d77-134">String</span></span> | <span data-ttu-id="62d77-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="62d77-135">Bearer {token}.</span></span> <span data-ttu-id="62d77-136">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="62d77-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="62d77-137">Parámetros uri de solicitud</span><span class="sxs-lookup"><span data-stu-id="62d77-137">Request URI parameters</span></span>

<span data-ttu-id="62d77-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="62d77-138">Name</span></span> | <span data-ttu-id="62d77-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="62d77-139">Type</span></span> | <span data-ttu-id="62d77-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="62d77-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="62d77-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="62d77-141">lookBackHours</span></span> | <span data-ttu-id="62d77-142">Int32</span><span class="sxs-lookup"><span data-stu-id="62d77-142">Int32</span></span> | <span data-ttu-id="62d77-143">Define las horas que buscamos para obtener las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="62d77-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="62d77-144">El valor predeterminado es 30 días.</span><span class="sxs-lookup"><span data-stu-id="62d77-144">Defaults to 30 days.</span></span> <span data-ttu-id="62d77-145">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="62d77-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="62d77-146">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="62d77-146">Request body</span></span>
<span data-ttu-id="62d77-147">En blanco</span><span class="sxs-lookup"><span data-stu-id="62d77-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="62d77-148">Respuesta</span><span class="sxs-lookup"><span data-stu-id="62d77-148">Response</span></span>
<span data-ttu-id="62d77-149">Si se realiza correctamente y el archivo existe: 200 Aceptar con datos estadísticos en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="62d77-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="62d77-150">Si el archivo no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="62d77-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="62d77-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62d77-151">Example</span></span>

<span data-ttu-id="62d77-152">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="62d77-152">**Request**</span></span>

<span data-ttu-id="62d77-153">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="62d77-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="62d77-154">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="62d77-154">**Response**</span></span>

<span data-ttu-id="62d77-155">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="62d77-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
