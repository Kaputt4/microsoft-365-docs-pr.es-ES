---
title: Códigos de error comunes de la API de REST de Microsoft Threat Protection
description: Obtenga información sobre los códigos de error comunes de la API de REST de Microsoft Threat Protection
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
ms.openlocfilehash: 81375b919b52ff895e5ec7014feb747b1a0eae65
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201344"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a><span data-ttu-id="96771-104">Códigos de error comunes de la API de REST de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="96771-104">Common Microsoft Threat Protection REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="96771-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="96771-105">**Applies to:**</span></span>
- <span data-ttu-id="96771-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="96771-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="96771-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="96771-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="96771-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="96771-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="96771-109">Los códigos de error que se enumeran en la siguiente tabla pueden devolverse mediante una operación en cualquiera de las API de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="96771-109">The error codes listed in the following table may be returned by an operation on any of Microsoft Threat Protection APIs.</span></span>

<span data-ttu-id="96771-110">Cada respuesta de error contiene un mensaje de error, que puede ayudar a resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="96771-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="96771-111">El mensaje es un texto libre que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="96771-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="96771-112">En la parte inferior de la página, puede encontrar ejemplos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="96771-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="96771-113">Código de error</span><span class="sxs-lookup"><span data-stu-id="96771-113">Error code</span></span> |<span data-ttu-id="96771-114">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="96771-114">HTTP status code</span></span> |<span data-ttu-id="96771-115">Message</span><span class="sxs-lookup"><span data-stu-id="96771-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="96771-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="96771-116">BadRequest</span></span> | <span data-ttu-id="96771-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-117">BadRequest (400)</span></span> | <span data-ttu-id="96771-118">Mensaje de error de solicitud incorrecta general.</span><span class="sxs-lookup"><span data-stu-id="96771-118">General Bad Request error message.</span></span>
<span data-ttu-id="96771-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="96771-119">ODataError</span></span> | <span data-ttu-id="96771-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-120">BadRequest (400)</span></span> | <span data-ttu-id="96771-121">Consulta URI de OData no válida (se ha especificado el error específico).</span><span class="sxs-lookup"><span data-stu-id="96771-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="96771-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="96771-122">InvalidInput</span></span> | <span data-ttu-id="96771-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-123">BadRequest (400)</span></span> | <span data-ttu-id="96771-124">Entrada no válida {entrada no válida}.</span><span class="sxs-lookup"><span data-stu-id="96771-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="96771-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="96771-125">InvalidRequestBody</span></span> | <span data-ttu-id="96771-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-126">BadRequest (400)</span></span> | <span data-ttu-id="96771-127">Cuerpo de la solicitud no válido.</span><span class="sxs-lookup"><span data-stu-id="96771-127">Invalid request body.</span></span>
<span data-ttu-id="96771-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="96771-128">InvalidHashValue</span></span> | <span data-ttu-id="96771-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-129">BadRequest (400)</span></span> | <span data-ttu-id="96771-130">El valor hash {el hash no válido} no es válido.</span><span class="sxs-lookup"><span data-stu-id="96771-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="96771-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="96771-131">InvalidDomainName</span></span> | <span data-ttu-id="96771-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-132">BadRequest (400)</span></span> | <span data-ttu-id="96771-133">Nombre de dominio {el dominio no válido} no es válido.</span><span class="sxs-lookup"><span data-stu-id="96771-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="96771-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="96771-134">InvalidIpAddress</span></span> | <span data-ttu-id="96771-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-135">BadRequest (400)</span></span> | <span data-ttu-id="96771-136">La dirección IP {IP no válida} no es válida.</span><span class="sxs-lookup"><span data-stu-id="96771-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="96771-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="96771-137">InvalidUrl</span></span> | <span data-ttu-id="96771-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-138">BadRequest (400)</span></span> | <span data-ttu-id="96771-139">La dirección URL {URL no válida} no es válida.</span><span class="sxs-lookup"><span data-stu-id="96771-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="96771-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="96771-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="96771-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-141">BadRequest (400)</span></span> | <span data-ttu-id="96771-142">Tamaño máximo de lote superado.</span><span class="sxs-lookup"><span data-stu-id="96771-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="96771-143">Recibido: {tamaño de lote recibido}, permitido: {tamaño de lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="96771-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="96771-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="96771-144">MissingRequiredParameter</span></span> | <span data-ttu-id="96771-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-145">BadRequest (400)</span></span> | <span data-ttu-id="96771-146">No se encuentra el parámetro {falta el parámetro}.</span><span class="sxs-lookup"><span data-stu-id="96771-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="96771-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="96771-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="96771-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-148">BadRequest (400)</span></span> | <span data-ttu-id="96771-149">Plataforma de so {la plataforma de sistema operativo cliente} no es compatible con esta acción.</span><span class="sxs-lookup"><span data-stu-id="96771-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="96771-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="96771-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="96771-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="96771-151">BadRequest (400)</span></span> | <span data-ttu-id="96771-152">{La acción solicitada} es compatible con la versión de cliente {versión de cliente admitida} y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="96771-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="96771-153">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="96771-153">Unauthorized</span></span> | <span data-ttu-id="96771-154">No autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="96771-154">Unauthorized (401)</span></span> | <span data-ttu-id="96771-155">Encabezado de autorización no autorizado (normalmente no válido o expirado).</span><span class="sxs-lookup"><span data-stu-id="96771-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="96771-156">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="96771-156">Forbidden</span></span> | <span data-ttu-id="96771-157">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="96771-157">Forbidden (403)</span></span> | <span data-ttu-id="96771-158">Prohibido (token válido, pero permiso insuficiente para la acción).</span><span class="sxs-lookup"><span data-stu-id="96771-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="96771-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="96771-159">DisabledFeature</span></span> | <span data-ttu-id="96771-160">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="96771-160">Forbidden (403)</span></span> | <span data-ttu-id="96771-161">La característica de inquilino no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="96771-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="96771-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="96771-162">DisallowedOperation</span></span> | <span data-ttu-id="96771-163">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="96771-163">Forbidden (403)</span></span> | <span data-ttu-id="96771-164">{la operación no permitida y el motivo}.</span><span class="sxs-lookup"><span data-stu-id="96771-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="96771-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="96771-165">NotFound</span></span> | <span data-ttu-id="96771-166">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="96771-166">Not Found (404)</span></span> | <span data-ttu-id="96771-167">Mensaje de error general no encontrado.</span><span class="sxs-lookup"><span data-stu-id="96771-167">General Not Found error message.</span></span>
<span data-ttu-id="96771-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="96771-168">ResourceNotFound</span></span> | <span data-ttu-id="96771-169">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="96771-169">Not Found (404)</span></span> | <span data-ttu-id="96771-170">Recurso {no se encontró el recurso solicitado}.</span><span class="sxs-lookup"><span data-stu-id="96771-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="96771-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="96771-171">InternalServerError</span></span> | <span data-ttu-id="96771-172">Error interno del servidor (500)</span><span class="sxs-lookup"><span data-stu-id="96771-172">Internal Server Error (500)</span></span> | <span data-ttu-id="96771-173">(No hay ningún mensaje de error, reintente la operación o póngase en contacto con nosotros si no se resuelve)</span><span class="sxs-lookup"><span data-stu-id="96771-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="96771-174">Los parámetros Body distinguen entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="96771-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="96771-175">Los parámetros del cuerpo enviados actualmente distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="96771-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="96771-176">Si experimenta errores de **InvalidRequestBody** o **MissingRequiredParameter** , puede deberse a una letra de mayúscula o minúscula del parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="96771-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="96771-177">Le recomendamos que revise la página de documentación de la API y que compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="96771-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="96771-178">IDENTIFICADOR de solicitud de correlación</span><span class="sxs-lookup"><span data-stu-id="96771-178">Correlation request ID</span></span>

<span data-ttu-id="96771-179">Cada respuesta de error contiene un parámetro ID único para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96771-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="96771-180">El nombre de la propiedad de este parámetro es "target".</span><span class="sxs-lookup"><span data-stu-id="96771-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="96771-181">Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador le ayudará a encontrar la causa raíz del problema.</span><span class="sxs-lookup"><span data-stu-id="96771-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="96771-182">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="96771-182">Examples</span></span>

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

