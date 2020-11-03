---
title: Códigos de error comunes de la API de REST de Microsoft 365 defender
description: Obtener información sobre los códigos de error comunes de la API de REST de Microsoft 365 defender
keywords: API, error, códigos, errores comunes, MTP, códigos de error de la API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846013"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="86263-104">Códigos de error comunes de la API de REST de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="86263-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="86263-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="86263-105">**Applies to:**</span></span>
- <span data-ttu-id="86263-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="86263-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="86263-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="86263-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="86263-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="86263-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="86263-109">Los códigos de error que se enumeran en la siguiente tabla pueden devolverse mediante una operación en cualquiera de las API de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="86263-109">The error codes listed in the following table may be returned by an operation on any of Microsoft 365 Defender APIs.</span></span>

<span data-ttu-id="86263-110">Cada respuesta de error contiene un mensaje de error, que puede ayudar a resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="86263-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="86263-111">El mensaje es un texto libre que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="86263-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="86263-112">En la parte inferior de la página, puede encontrar ejemplos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="86263-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="86263-113">Código de error</span><span class="sxs-lookup"><span data-stu-id="86263-113">Error code</span></span> |<span data-ttu-id="86263-114">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="86263-114">HTTP status code</span></span> |<span data-ttu-id="86263-115">Message</span><span class="sxs-lookup"><span data-stu-id="86263-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="86263-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="86263-116">BadRequest</span></span> | <span data-ttu-id="86263-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-117">BadRequest (400)</span></span> | <span data-ttu-id="86263-118">Mensaje de error de solicitud incorrecta general.</span><span class="sxs-lookup"><span data-stu-id="86263-118">General Bad Request error message.</span></span>
<span data-ttu-id="86263-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="86263-119">ODataError</span></span> | <span data-ttu-id="86263-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-120">BadRequest (400)</span></span> | <span data-ttu-id="86263-121">Consulta URI de OData no válida (se ha especificado el error específico).</span><span class="sxs-lookup"><span data-stu-id="86263-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="86263-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="86263-122">InvalidInput</span></span> | <span data-ttu-id="86263-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-123">BadRequest (400)</span></span> | <span data-ttu-id="86263-124">Entrada no válida {entrada no válida}.</span><span class="sxs-lookup"><span data-stu-id="86263-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="86263-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="86263-125">InvalidRequestBody</span></span> | <span data-ttu-id="86263-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-126">BadRequest (400)</span></span> | <span data-ttu-id="86263-127">Cuerpo de la solicitud no válido.</span><span class="sxs-lookup"><span data-stu-id="86263-127">Invalid request body.</span></span>
<span data-ttu-id="86263-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="86263-128">InvalidHashValue</span></span> | <span data-ttu-id="86263-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-129">BadRequest (400)</span></span> | <span data-ttu-id="86263-130">El valor hash {el hash no válido} no es válido.</span><span class="sxs-lookup"><span data-stu-id="86263-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="86263-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="86263-131">InvalidDomainName</span></span> | <span data-ttu-id="86263-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-132">BadRequest (400)</span></span> | <span data-ttu-id="86263-133">Nombre de dominio {el dominio no válido} no es válido.</span><span class="sxs-lookup"><span data-stu-id="86263-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="86263-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="86263-134">InvalidIpAddress</span></span> | <span data-ttu-id="86263-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-135">BadRequest (400)</span></span> | <span data-ttu-id="86263-136">La dirección IP {IP no válida} no es válida.</span><span class="sxs-lookup"><span data-stu-id="86263-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="86263-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="86263-137">InvalidUrl</span></span> | <span data-ttu-id="86263-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-138">BadRequest (400)</span></span> | <span data-ttu-id="86263-139">La dirección URL {URL no válida} no es válida.</span><span class="sxs-lookup"><span data-stu-id="86263-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="86263-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="86263-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="86263-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-141">BadRequest (400)</span></span> | <span data-ttu-id="86263-142">Tamaño máximo de lote superado.</span><span class="sxs-lookup"><span data-stu-id="86263-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="86263-143">Recibido: {tamaño de lote recibido}, permitido: {tamaño de lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="86263-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="86263-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="86263-144">MissingRequiredParameter</span></span> | <span data-ttu-id="86263-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-145">BadRequest (400)</span></span> | <span data-ttu-id="86263-146">No se encuentra el parámetro {falta el parámetro}.</span><span class="sxs-lookup"><span data-stu-id="86263-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="86263-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="86263-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="86263-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-148">BadRequest (400)</span></span> | <span data-ttu-id="86263-149">Plataforma de so {la plataforma de sistema operativo cliente} no es compatible con esta acción.</span><span class="sxs-lookup"><span data-stu-id="86263-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="86263-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="86263-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="86263-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="86263-151">BadRequest (400)</span></span> | <span data-ttu-id="86263-152">{La acción solicitada} es compatible con la versión de cliente {versión de cliente admitida} y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="86263-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="86263-153">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="86263-153">Unauthorized</span></span> | <span data-ttu-id="86263-154">No autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="86263-154">Unauthorized (401)</span></span> | <span data-ttu-id="86263-155">Encabezado de autorización no autorizado (normalmente no válido o expirado).</span><span class="sxs-lookup"><span data-stu-id="86263-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="86263-156">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="86263-156">Forbidden</span></span> | <span data-ttu-id="86263-157">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="86263-157">Forbidden (403)</span></span> | <span data-ttu-id="86263-158">Prohibido (token válido, pero permiso insuficiente para la acción).</span><span class="sxs-lookup"><span data-stu-id="86263-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="86263-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="86263-159">DisabledFeature</span></span> | <span data-ttu-id="86263-160">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="86263-160">Forbidden (403)</span></span> | <span data-ttu-id="86263-161">La característica de inquilino no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="86263-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="86263-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="86263-162">DisallowedOperation</span></span> | <span data-ttu-id="86263-163">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="86263-163">Forbidden (403)</span></span> | <span data-ttu-id="86263-164">{la operación no permitida y el motivo}.</span><span class="sxs-lookup"><span data-stu-id="86263-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="86263-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="86263-165">NotFound</span></span> | <span data-ttu-id="86263-166">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="86263-166">Not Found (404)</span></span> | <span data-ttu-id="86263-167">Mensaje de error general no encontrado.</span><span class="sxs-lookup"><span data-stu-id="86263-167">General Not Found error message.</span></span>
<span data-ttu-id="86263-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="86263-168">ResourceNotFound</span></span> | <span data-ttu-id="86263-169">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="86263-169">Not Found (404)</span></span> | <span data-ttu-id="86263-170">Recurso {no se encontró el recurso solicitado}.</span><span class="sxs-lookup"><span data-stu-id="86263-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="86263-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="86263-171">InternalServerError</span></span> | <span data-ttu-id="86263-172">Error interno del servidor (500)</span><span class="sxs-lookup"><span data-stu-id="86263-172">Internal Server Error (500)</span></span> | <span data-ttu-id="86263-173">(No hay ningún mensaje de error, reintente la operación o póngase en contacto con nosotros si no se resuelve)</span><span class="sxs-lookup"><span data-stu-id="86263-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="86263-174">Los parámetros Body distinguen entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="86263-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="86263-175">Los parámetros del cuerpo enviados actualmente distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="86263-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="86263-176">Si experimenta errores de **InvalidRequestBody** o **MissingRequiredParameter** , puede deberse a una letra de mayúscula o minúscula del parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="86263-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="86263-177">Le recomendamos que revise la página de documentación de la API y que compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="86263-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="86263-178">IDENTIFICADOR de solicitud de correlación</span><span class="sxs-lookup"><span data-stu-id="86263-178">Correlation request ID</span></span>

<span data-ttu-id="86263-179">Cada respuesta de error contiene un parámetro ID único para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="86263-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="86263-180">El nombre de la propiedad de este parámetro es "target".</span><span class="sxs-lookup"><span data-stu-id="86263-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="86263-181">Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador le ayudará a encontrar la causa raíz del problema.</span><span class="sxs-lookup"><span data-stu-id="86263-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="86263-182">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="86263-182">Examples</span></span>

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

