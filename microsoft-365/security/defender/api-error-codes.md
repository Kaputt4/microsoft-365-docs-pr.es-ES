---
title: Códigos de error comunes de la API rest de Microsoft 365 Defender
description: Obtenga información sobre los códigos de error comunes de la API de REST de Microsoft 365 Defender
keywords: api, error, códigos, errores comunes, mtp, códigos de error de api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ab564ddb0263b501b6aca979f2148dfb5cf92758
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076696"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="dfd9a-104">Códigos de error comunes de la API rest de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dfd9a-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="dfd9a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="dfd9a-105">**Applies to:**</span></span>

- <span data-ttu-id="dfd9a-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfd9a-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfd9a-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dfd9a-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="dfd9a-109">Una operación puede devolver códigos de error en cualquiera de las API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="dfd9a-110">Cada respuesta de error contendrá un mensaje de error, lo que puede ayudar a resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="dfd9a-111">La columna de mensaje de error de la sección tabla proporciona algunos mensajes de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="dfd9a-112">El contenido de los mensajes reales variará en función de los factores que desencadenaron la respuesta.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="dfd9a-113">El contenido de las variables se indica en la tabla entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="dfd9a-114">Códigos de error</span><span class="sxs-lookup"><span data-stu-id="dfd9a-114">Error codes</span></span>

<span data-ttu-id="dfd9a-115">Código de error</span><span class="sxs-lookup"><span data-stu-id="dfd9a-115">Error code</span></span> | <span data-ttu-id="dfd9a-116">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="dfd9a-116">HTTP status code</span></span> | <span data-ttu-id="dfd9a-117">Mensaje</span><span class="sxs-lookup"><span data-stu-id="dfd9a-117">Message</span></span>
-|-|-
<span data-ttu-id="dfd9a-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="dfd9a-118">BadRequest</span></span> | <span data-ttu-id="dfd9a-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-119">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-120">Mensaje de error General Bad Request.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-120">General Bad Request error message.</span></span>
<span data-ttu-id="dfd9a-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="dfd9a-121">ODataError</span></span> | <span data-ttu-id="dfd9a-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-122">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-123">Consulta URI de OData no válida \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="dfd9a-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="dfd9a-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="dfd9a-124">InvalidInput</span></span> | <span data-ttu-id="dfd9a-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-125">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-126">Entrada no válida \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="dfd9a-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="dfd9a-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="dfd9a-127">InvalidRequestBody</span></span> | <span data-ttu-id="dfd9a-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-128">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-129">Cuerpo de la solicitud no válido.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-129">Invalid request body.</span></span>
<span data-ttu-id="dfd9a-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="dfd9a-130">InvalidHashValue</span></span> | <span data-ttu-id="dfd9a-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-131">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-132">El valor hash \<the invalid hash\> no es válido.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="dfd9a-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="dfd9a-133">InvalidDomainName</span></span> | <span data-ttu-id="dfd9a-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-134">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-135">El nombre \<the invalid domain\> de dominio no es válido.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="dfd9a-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="dfd9a-136">InvalidIpAddress</span></span> | <span data-ttu-id="dfd9a-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-137">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-138">La dirección IP \<the invalid IP\> no es válida.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="dfd9a-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="dfd9a-139">InvalidUrl</span></span> | <span data-ttu-id="dfd9a-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-140">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-141">La dirección URL \<the invalid URL\> no es válida.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="dfd9a-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="dfd9a-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="dfd9a-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-143">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-144">Se ha superado el tamaño máximo de lote.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="dfd9a-145">Recibido: \<batch size received\> , permitido: {tamaño de lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="dfd9a-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="dfd9a-146">MissingRequiredParameter</span></span> | <span data-ttu-id="dfd9a-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-147">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-148">Falta \<the missing parameter\> el parámetro.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="dfd9a-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="dfd9a-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="dfd9a-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-150">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-151">La plataforma del \<the client OS Platform\> sistema operativo no es compatible con esta acción.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="dfd9a-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="dfd9a-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="dfd9a-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-153">BadRequest (400)</span></span> | <span data-ttu-id="dfd9a-154">\<The requested action\> se admite en la versión del cliente \<supported client version\> y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="dfd9a-155">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-155">Unauthorized</span></span> | <span data-ttu-id="dfd9a-156">No autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-156">Unauthorized (401)</span></span> | <span data-ttu-id="dfd9a-157">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="dfd9a-158">*Nota: Normalmente se debe a un encabezado de autorización no válido o expirado.*</span><span class="sxs-lookup"><span data-stu-id="dfd9a-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="dfd9a-159">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-159">Forbidden</span></span> | <span data-ttu-id="dfd9a-160">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-160">Forbidden (403)</span></span> | <span data-ttu-id="dfd9a-161">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-161">Forbidden</span></span> <br /><br /><span data-ttu-id="dfd9a-162">*Nota: Token válido pero permiso insuficiente para la acción*.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="dfd9a-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="dfd9a-163">DisabledFeature</span></span> | <span data-ttu-id="dfd9a-164">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-164">Forbidden (403)</span></span> | <span data-ttu-id="dfd9a-165">La característica inquilino no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="dfd9a-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="dfd9a-166">DisallowedOperation</span></span> | <span data-ttu-id="dfd9a-167">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-167">Forbidden (403)</span></span> | <span data-ttu-id="dfd9a-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="dfd9a-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="dfd9a-169">NotFound</span></span> | <span data-ttu-id="dfd9a-170">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-170">Not Found (404)</span></span> | <span data-ttu-id="dfd9a-171">Mensaje de error General No encontrado.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-171">General Not Found error message.</span></span>
<span data-ttu-id="dfd9a-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="dfd9a-172">ResourceNotFound</span></span> | <span data-ttu-id="dfd9a-173">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-173">Not Found (404)</span></span> | <span data-ttu-id="dfd9a-174">No \<the requested resource\> se encontró el recurso.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="dfd9a-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="dfd9a-175">InternalServerError</span></span> | <span data-ttu-id="dfd9a-176">Error interno del servidor (500)</span><span class="sxs-lookup"><span data-stu-id="dfd9a-176">Internal Server Error (500)</span></span> | <span data-ttu-id="dfd9a-177">*Nota: No hay mensaje de error, vuelva a intentar la operación o póngase en contacto con Microsoft si no se resuelve*</span><span class="sxs-lookup"><span data-stu-id="dfd9a-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="dfd9a-178">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="dfd9a-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="dfd9a-179">Parámetros de cuerpo</span><span class="sxs-lookup"><span data-stu-id="dfd9a-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfd9a-180">Los parámetros de cuerpo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="dfd9a-181">Si experimenta un error *InvalidRequestBody* *o MissingRequiredParameter,* puede deberse a un error tipográfico.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="dfd9a-182">Revise la documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="dfd9a-183">Id. de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dfd9a-183">Tracking ID</span></span>

<span data-ttu-id="dfd9a-184">Cada respuesta de error contiene un parámetro id. único para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="dfd9a-185">El nombre de la propiedad de este parámetro es *target*.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="dfd9a-186">Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador nos ayudará a encontrar la causa raíz del problema.</span><span class="sxs-lookup"><span data-stu-id="dfd9a-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dfd9a-187">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="dfd9a-187">Related articles</span></span>

- [<span data-ttu-id="dfd9a-188">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dfd9a-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="dfd9a-189">API de Microsoft 365 Defender (versión preliminar) admitidas</span><span class="sxs-lookup"><span data-stu-id="dfd9a-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="dfd9a-190">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dfd9a-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="dfd9a-191">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="dfd9a-191">Learn about API limits and licensing</span></span>](api-terms.md)
