---
title: Obtener API de estadísticas de dominio
description: Obtenga información sobre cómo usar la API Obtener estadísticas de dominio para recuperar las estadísticas del dominio especificado en Microsoft Defender para endpoint.
keywords: api, api de gráfico, api admitidas, obtener, dominio, dispositivos relacionados con el dominio
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
ms.openlocfilehash: d2edc5d429d124412134b466753b65506d2dd7a9
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772190"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="98617-104">Obtener API de estadísticas de dominio</span><span class="sxs-lookup"><span data-stu-id="98617-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98617-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="98617-105">**Applies to:**</span></span>
- [<span data-ttu-id="98617-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="98617-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98617-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98617-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="98617-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="98617-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="98617-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="98617-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="98617-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="98617-110">API description</span></span>
<span data-ttu-id="98617-111">Recupera las estadísticas del dominio determinado.</span><span class="sxs-lookup"><span data-stu-id="98617-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="98617-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="98617-112">Limitations</span></span>
1. <span data-ttu-id="98617-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="98617-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="98617-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="98617-114">Permissions</span></span>
<span data-ttu-id="98617-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="98617-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="98617-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="98617-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="98617-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="98617-117">Permission type</span></span> |   <span data-ttu-id="98617-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="98617-118">Permission</span></span>  |   <span data-ttu-id="98617-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="98617-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="98617-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="98617-120">Application</span></span> |   <span data-ttu-id="98617-121">DIRECCIÓN URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="98617-121">URL.Read.All</span></span> |  <span data-ttu-id="98617-122">'Leer direcciones URL'</span><span class="sxs-lookup"><span data-stu-id="98617-122">'Read URLs'</span></span>
<span data-ttu-id="98617-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="98617-123">Delegated (work or school account)</span></span> | <span data-ttu-id="98617-124">DIRECCIÓN URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="98617-124">URL.Read.All</span></span> | <span data-ttu-id="98617-125">'Leer direcciones URL'</span><span class="sxs-lookup"><span data-stu-id="98617-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="98617-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="98617-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="98617-127">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="98617-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="98617-128">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="98617-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="98617-129">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="98617-129">Request headers</span></span>

<span data-ttu-id="98617-130">Encabezado</span><span class="sxs-lookup"><span data-stu-id="98617-130">Header</span></span> | <span data-ttu-id="98617-131">Valor</span><span class="sxs-lookup"><span data-stu-id="98617-131">Value</span></span> 
:---|:---
<span data-ttu-id="98617-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="98617-132">Authorization</span></span> | <span data-ttu-id="98617-133">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="98617-133">Bearer {token}.</span></span> <span data-ttu-id="98617-134">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="98617-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="98617-135">Parámetros uri de solicitud</span><span class="sxs-lookup"><span data-stu-id="98617-135">Request URI parameters</span></span>

<span data-ttu-id="98617-136">Nombre</span><span class="sxs-lookup"><span data-stu-id="98617-136">Name</span></span> | <span data-ttu-id="98617-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="98617-137">Type</span></span> | <span data-ttu-id="98617-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="98617-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="98617-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="98617-139">lookBackHours</span></span> | <span data-ttu-id="98617-140">Int32</span><span class="sxs-lookup"><span data-stu-id="98617-140">Int32</span></span> | <span data-ttu-id="98617-141">Define las horas que buscamos para obtener las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="98617-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="98617-142">El valor predeterminado es 30 días.</span><span class="sxs-lookup"><span data-stu-id="98617-142">Defaults to 30 days.</span></span> <span data-ttu-id="98617-143">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="98617-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="98617-144">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="98617-144">Request body</span></span>
<span data-ttu-id="98617-145">En blanco</span><span class="sxs-lookup"><span data-stu-id="98617-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="98617-146">Respuesta</span><span class="sxs-lookup"><span data-stu-id="98617-146">Response</span></span>
<span data-ttu-id="98617-147">Si se realiza correctamente y el dominio existe: 200 Ok, con el objeto statistics en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="98617-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="98617-148">Si el dominio no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="98617-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="98617-149">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98617-149">Example</span></span>

<span data-ttu-id="98617-150">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="98617-150">**Request**</span></span>

<span data-ttu-id="98617-151">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="98617-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="98617-152">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="98617-152">**Response**</span></span>

<span data-ttu-id="98617-153">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="98617-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
