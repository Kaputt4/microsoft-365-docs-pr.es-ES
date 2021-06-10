---
title: Errores comunes de La API de Microsoft Defender para puntos de conexión
description: Lista de errores comunes de La API de Microsoft Defender para puntos de conexión con descripciones.
keywords: API, API de Microsoft Defender para endpoints, errores, solución de problemas
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
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771014"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="27e4f-104">Códigos de error comunes de API de REST</span><span class="sxs-lookup"><span data-stu-id="27e4f-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="27e4f-105">Los códigos de error enumerados en la tabla siguiente pueden devolverse mediante una operación en cualquiera de las API de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="27e4f-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="27e4f-106">Además del código de error, cada respuesta de error contiene un mensaje de error, que puede ayudar a resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="27e4f-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="27e4f-107">El mensaje es un texto gratuito que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="27e4f-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="27e4f-108">En la parte inferior de la página, puede encontrar ejemplos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="27e4f-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="27e4f-109">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="27e4f-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="27e4f-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="27e4f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="27e4f-111">Código de error</span><span class="sxs-lookup"><span data-stu-id="27e4f-111">Error code</span></span> |<span data-ttu-id="27e4f-112">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="27e4f-112">HTTP status code</span></span> |<span data-ttu-id="27e4f-113">Mensaje</span><span class="sxs-lookup"><span data-stu-id="27e4f-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="27e4f-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="27e4f-114">BadRequest</span></span> | <span data-ttu-id="27e4f-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-115">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-116">Mensaje de error General Bad Request.</span><span class="sxs-lookup"><span data-stu-id="27e4f-116">General Bad Request error message.</span></span>
<span data-ttu-id="27e4f-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="27e4f-117">ODataError</span></span> | <span data-ttu-id="27e4f-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-118">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-119">Consulta URI de OData no válida (se especifica el error específico).</span><span class="sxs-lookup"><span data-stu-id="27e4f-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="27e4f-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="27e4f-120">InvalidInput</span></span> | <span data-ttu-id="27e4f-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-121">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-122">Entrada no válida {la entrada no válida}.</span><span class="sxs-lookup"><span data-stu-id="27e4f-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="27e4f-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="27e4f-123">InvalidRequestBody</span></span> | <span data-ttu-id="27e4f-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-124">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-125">Cuerpo de la solicitud no válido.</span><span class="sxs-lookup"><span data-stu-id="27e4f-125">Invalid request body.</span></span>
<span data-ttu-id="27e4f-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="27e4f-126">InvalidHashValue</span></span> | <span data-ttu-id="27e4f-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-127">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-128">El valor hash {el hash no válido} no es válido.</span><span class="sxs-lookup"><span data-stu-id="27e4f-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="27e4f-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="27e4f-129">InvalidDomainName</span></span> | <span data-ttu-id="27e4f-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-130">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-131">El nombre de dominio {el dominio no válido} no es válido.</span><span class="sxs-lookup"><span data-stu-id="27e4f-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="27e4f-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="27e4f-132">InvalidIpAddress</span></span> | <span data-ttu-id="27e4f-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-133">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-134">La dirección IP {la IP no válida} no es válida.</span><span class="sxs-lookup"><span data-stu-id="27e4f-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="27e4f-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="27e4f-135">InvalidUrl</span></span> | <span data-ttu-id="27e4f-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-136">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-137">La dirección URL {la dirección URL no válida} no es válida.</span><span class="sxs-lookup"><span data-stu-id="27e4f-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="27e4f-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="27e4f-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="27e4f-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-139">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-140">Se ha superado el tamaño máximo de lote.</span><span class="sxs-lookup"><span data-stu-id="27e4f-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="27e4f-141">Received: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="27e4f-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="27e4f-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="27e4f-142">MissingRequiredParameter</span></span> | <span data-ttu-id="27e4f-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-143">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-144">Falta el parámetro {el parámetro que falta}.</span><span class="sxs-lookup"><span data-stu-id="27e4f-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="27e4f-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="27e4f-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="27e4f-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-146">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-147">La plataforma del sistema operativo {la plataforma del sistema operativo cliente} no es compatible con esta acción.</span><span class="sxs-lookup"><span data-stu-id="27e4f-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="27e4f-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="27e4f-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="27e4f-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="27e4f-149">BadRequest (400)</span></span> | <span data-ttu-id="27e4f-150">{La acción solicitada} se admite en la versión de cliente {versión de cliente admitida} y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="27e4f-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="27e4f-151">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="27e4f-151">Unauthorized</span></span> | <span data-ttu-id="27e4f-152">No autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="27e4f-152">Unauthorized (401)</span></span> | <span data-ttu-id="27e4f-153">No autorizado (encabezado de autorización no válido o expirado).</span><span class="sxs-lookup"><span data-stu-id="27e4f-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="27e4f-154">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="27e4f-154">Forbidden</span></span> | <span data-ttu-id="27e4f-155">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="27e4f-155">Forbidden (403)</span></span> | <span data-ttu-id="27e4f-156">Prohibido (token válido pero permiso insuficiente para la acción).</span><span class="sxs-lookup"><span data-stu-id="27e4f-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="27e4f-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="27e4f-157">DisabledFeature</span></span> | <span data-ttu-id="27e4f-158">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="27e4f-158">Forbidden (403)</span></span> | <span data-ttu-id="27e4f-159">La característica inquilino no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="27e4f-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="27e4f-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="27e4f-160">DisallowedOperation</span></span> | <span data-ttu-id="27e4f-161">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="27e4f-161">Forbidden (403)</span></span> | <span data-ttu-id="27e4f-162">{la operación no permitido y el motivo}.</span><span class="sxs-lookup"><span data-stu-id="27e4f-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="27e4f-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="27e4f-163">NotFound</span></span> | <span data-ttu-id="27e4f-164">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="27e4f-164">Not Found (404)</span></span> | <span data-ttu-id="27e4f-165">Mensaje de error General No encontrado.</span><span class="sxs-lookup"><span data-stu-id="27e4f-165">General Not Found error message.</span></span>
<span data-ttu-id="27e4f-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="27e4f-166">ResourceNotFound</span></span> | <span data-ttu-id="27e4f-167">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="27e4f-167">Not Found (404)</span></span> | <span data-ttu-id="27e4f-168">No se encontró el recurso {el recurso solicitado}.</span><span class="sxs-lookup"><span data-stu-id="27e4f-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="27e4f-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="27e4f-169">InternalServerError</span></span> | <span data-ttu-id="27e4f-170">Error interno del servidor (500)</span><span class="sxs-lookup"><span data-stu-id="27e4f-170">Internal Server Error (500)</span></span> | <span data-ttu-id="27e4f-171">(Sin mensaje de error, vuelva a intentar la operación)</span><span class="sxs-lookup"><span data-stu-id="27e4f-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="27e4f-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="27e4f-172">TooManyRequests</span></span> | <span data-ttu-id="27e4f-173">Demasiadas solicitudes (429)</span><span class="sxs-lookup"><span data-stu-id="27e4f-173">Too Many Requests (429)</span></span> | <span data-ttu-id="27e4f-174">La respuesta representará alcanzar el límite de cuota por número de solicitudes o por CPU.</span><span class="sxs-lookup"><span data-stu-id="27e4f-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="27e4f-175">Los parámetros de cuerpo distinguen mayúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="27e4f-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="27e4f-176">Los parámetros de cuerpo enviados distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="27e4f-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="27e4f-177">Si experimenta errores **InvalidRequestBody** o **MissingRequiredParameter,** es posible que se deba a un capital de parámetro incorrecto o a una letra minúscula.</span><span class="sxs-lookup"><span data-stu-id="27e4f-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="27e4f-178">Revise la página de documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="27e4f-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="27e4f-179">Identificador de solicitud de correlación</span><span class="sxs-lookup"><span data-stu-id="27e4f-179">Correlation request ID</span></span>

<span data-ttu-id="27e4f-180">Cada respuesta de error contiene un parámetro id. único para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="27e4f-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="27e4f-181">El nombre de la propiedad de este parámetro es "target".</span><span class="sxs-lookup"><span data-stu-id="27e4f-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="27e4f-182">Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador ayudará a encontrar la causa raíz del problema.</span><span class="sxs-lookup"><span data-stu-id="27e4f-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="27e4f-183">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="27e4f-183">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```


```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```
