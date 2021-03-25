---
title: Obtener API de estadísticas IP
description: Obtén las estadísticas más recientes de tu IP con Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api compatibles, get, ip, statistics, prevalence
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
ms.openlocfilehash: c47a5e58b1888447a4428fad78e71b85cfe79b69
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167183"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="98487-104">Obtener API de estadísticas IP</span><span class="sxs-lookup"><span data-stu-id="98487-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98487-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="98487-105">**Applies to:**</span></span>
- [<span data-ttu-id="98487-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="98487-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98487-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98487-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="98487-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="98487-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98487-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="98487-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="98487-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="98487-110">API description</span></span>
<span data-ttu-id="98487-111">Recupera las estadísticas de la DIRECCIÓN IP determinada.</span><span class="sxs-lookup"><span data-stu-id="98487-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="98487-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="98487-112">Limitations</span></span>
1. <span data-ttu-id="98487-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="98487-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="98487-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="98487-114">Permissions</span></span>
<span data-ttu-id="98487-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="98487-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="98487-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="98487-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="98487-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="98487-117">Permission type</span></span> |   <span data-ttu-id="98487-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="98487-118">Permission</span></span>  |   <span data-ttu-id="98487-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="98487-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="98487-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="98487-120">Application</span></span> |   <span data-ttu-id="98487-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="98487-121">Ip.Read.All</span></span> |   <span data-ttu-id="98487-122">'Leer perfiles de dirección IP'</span><span class="sxs-lookup"><span data-stu-id="98487-122">'Read IP address profiles'</span></span>
<span data-ttu-id="98487-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="98487-123">Delegated (work or school account)</span></span> | <span data-ttu-id="98487-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="98487-124">Ip.Read.All</span></span> |  <span data-ttu-id="98487-125">'Leer perfiles de dirección IP'</span><span class="sxs-lookup"><span data-stu-id="98487-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="98487-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="98487-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="98487-127">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="98487-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="98487-128">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="98487-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="98487-129">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="98487-129">Request headers</span></span>

<span data-ttu-id="98487-130">Nombre</span><span class="sxs-lookup"><span data-stu-id="98487-130">Name</span></span> | <span data-ttu-id="98487-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="98487-131">Type</span></span> | <span data-ttu-id="98487-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="98487-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="98487-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="98487-133">Authorization</span></span> | <span data-ttu-id="98487-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="98487-134">String</span></span> | <span data-ttu-id="98487-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="98487-135">Bearer {token}.</span></span> <span data-ttu-id="98487-136">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="98487-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="98487-137">Parámetros uri de solicitud</span><span class="sxs-lookup"><span data-stu-id="98487-137">Request URI parameters</span></span>

<span data-ttu-id="98487-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="98487-138">Name</span></span> | <span data-ttu-id="98487-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="98487-139">Type</span></span> | <span data-ttu-id="98487-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="98487-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="98487-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="98487-141">lookBackHours</span></span> | <span data-ttu-id="98487-142">Int32</span><span class="sxs-lookup"><span data-stu-id="98487-142">Int32</span></span> | <span data-ttu-id="98487-143">Define las horas que buscamos para obtener las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="98487-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="98487-144">El valor predeterminado es 30 días.</span><span class="sxs-lookup"><span data-stu-id="98487-144">Defaults to 30 days.</span></span> <span data-ttu-id="98487-145">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="98487-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="98487-146">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="98487-146">Request body</span></span>
<span data-ttu-id="98487-147">En blanco</span><span class="sxs-lookup"><span data-stu-id="98487-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="98487-148">Respuesta</span><span class="sxs-lookup"><span data-stu-id="98487-148">Response</span></span>
<span data-ttu-id="98487-149">Si se realiza correctamente e ip existe: 200 Aceptar con datos estadísticos en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="98487-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="98487-150">IP no existe: 404 No se encuentra.</span><span class="sxs-lookup"><span data-stu-id="98487-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="98487-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98487-151">Example</span></span>

<span data-ttu-id="98487-152">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="98487-152">**Request**</span></span>

<span data-ttu-id="98487-153">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="98487-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="98487-154">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="98487-154">**Response**</span></span>

<span data-ttu-id="98487-155">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="98487-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="98487-156">Nombre</span><span class="sxs-lookup"><span data-stu-id="98487-156">Name</span></span> | <span data-ttu-id="98487-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="98487-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="98487-158">Prevalencia de la organización</span><span class="sxs-lookup"><span data-stu-id="98487-158">Org prevalence</span></span> | <span data-ttu-id="98487-159">el recuento distinto de dispositivos que abrieron la conexión de red a esta IP.</span><span class="sxs-lookup"><span data-stu-id="98487-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="98487-160">Org first seen</span><span class="sxs-lookup"><span data-stu-id="98487-160">Org first seen</span></span> | <span data-ttu-id="98487-161">la primera conexión para esta IP en la organización.</span><span class="sxs-lookup"><span data-stu-id="98487-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="98487-162">Org last seen</span><span class="sxs-lookup"><span data-stu-id="98487-162">Org last seen</span></span>  | <span data-ttu-id="98487-163">la última conexión para esta IP en la organización.</span><span class="sxs-lookup"><span data-stu-id="98487-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="98487-164">Esta información estadística se basa en datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="98487-164">This statistic information is based on data from the past 30 days.</span></span> 
