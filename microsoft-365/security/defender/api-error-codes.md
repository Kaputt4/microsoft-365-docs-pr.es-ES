---
title: Códigos de error Microsoft 365 API de REST de Defender
description: Obtenga información sobre los códigos de error comunes Microsoft 365 de error de la API de REST de Defender
keywords: api, error, códigos, errores comunes, Microsoft 365 Defender, códigos de error de api
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
ms.openlocfilehash: de24856e8ea7555a96de18cabca5ccadfe71b431
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930276"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="cd496-104">Códigos de error Microsoft 365 API de REST de Defender</span><span class="sxs-lookup"><span data-stu-id="cd496-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cd496-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cd496-105">**Applies to:**</span></span>

- <span data-ttu-id="cd496-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd496-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd496-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="cd496-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cd496-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="cd496-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cd496-109">Una operación puede devolver códigos de error en cualquiera de las API Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="cd496-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="cd496-110">Cada respuesta de error contendrá un mensaje de error, lo que puede ayudar a resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="cd496-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="cd496-111">La columna de mensaje de error de la sección tabla proporciona algunos mensajes de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cd496-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="cd496-112">El contenido de los mensajes reales variará en función de los factores que desencadenaron la respuesta.</span><span class="sxs-lookup"><span data-stu-id="cd496-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="cd496-113">El contenido de las variables se indica en la tabla entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="cd496-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="cd496-114">Códigos de error</span><span class="sxs-lookup"><span data-stu-id="cd496-114">Error codes</span></span>

<span data-ttu-id="cd496-115">Código de error</span><span class="sxs-lookup"><span data-stu-id="cd496-115">Error code</span></span> | <span data-ttu-id="cd496-116">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="cd496-116">HTTP status code</span></span> | <span data-ttu-id="cd496-117">Mensaje</span><span class="sxs-lookup"><span data-stu-id="cd496-117">Message</span></span>
-|-|-
<span data-ttu-id="cd496-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="cd496-118">BadRequest</span></span> | <span data-ttu-id="cd496-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-119">BadRequest (400)</span></span> | <span data-ttu-id="cd496-120">Mensaje de error General Bad Request.</span><span class="sxs-lookup"><span data-stu-id="cd496-120">General Bad Request error message.</span></span>
<span data-ttu-id="cd496-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="cd496-121">ODataError</span></span> | <span data-ttu-id="cd496-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-122">BadRequest (400)</span></span> | <span data-ttu-id="cd496-123">Consulta URI de OData no válida \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="cd496-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="cd496-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="cd496-124">InvalidInput</span></span> | <span data-ttu-id="cd496-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-125">BadRequest (400)</span></span> | <span data-ttu-id="cd496-126">Entrada no válida \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="cd496-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="cd496-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="cd496-127">InvalidRequestBody</span></span> | <span data-ttu-id="cd496-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-128">BadRequest (400)</span></span> | <span data-ttu-id="cd496-129">Cuerpo de la solicitud no válido.</span><span class="sxs-lookup"><span data-stu-id="cd496-129">Invalid request body.</span></span>
<span data-ttu-id="cd496-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="cd496-130">InvalidHashValue</span></span> | <span data-ttu-id="cd496-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-131">BadRequest (400)</span></span> | <span data-ttu-id="cd496-132">El valor hash \<the invalid hash\> no es válido.</span><span class="sxs-lookup"><span data-stu-id="cd496-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="cd496-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="cd496-133">InvalidDomainName</span></span> | <span data-ttu-id="cd496-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-134">BadRequest (400)</span></span> | <span data-ttu-id="cd496-135">El nombre \<the invalid domain\> de dominio no es válido.</span><span class="sxs-lookup"><span data-stu-id="cd496-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="cd496-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="cd496-136">InvalidIpAddress</span></span> | <span data-ttu-id="cd496-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-137">BadRequest (400)</span></span> | <span data-ttu-id="cd496-138">La dirección IP \<the invalid IP\> no es válida.</span><span class="sxs-lookup"><span data-stu-id="cd496-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="cd496-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="cd496-139">InvalidUrl</span></span> | <span data-ttu-id="cd496-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-140">BadRequest (400)</span></span> | <span data-ttu-id="cd496-141">La dirección URL \<the invalid URL\> no es válida.</span><span class="sxs-lookup"><span data-stu-id="cd496-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="cd496-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="cd496-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="cd496-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-143">BadRequest (400)</span></span> | <span data-ttu-id="cd496-144">Se ha superado el tamaño máximo de lote.</span><span class="sxs-lookup"><span data-stu-id="cd496-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="cd496-145">Recibido: \<batch size received\> , permitido: {tamaño de lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="cd496-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="cd496-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="cd496-146">MissingRequiredParameter</span></span> | <span data-ttu-id="cd496-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-147">BadRequest (400)</span></span> | <span data-ttu-id="cd496-148">Falta \<the missing parameter\> el parámetro.</span><span class="sxs-lookup"><span data-stu-id="cd496-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="cd496-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="cd496-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="cd496-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-150">BadRequest (400)</span></span> | <span data-ttu-id="cd496-151">La plataforma del \<the client OS Platform\> sistema operativo no es compatible con esta acción.</span><span class="sxs-lookup"><span data-stu-id="cd496-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="cd496-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="cd496-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="cd496-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd496-153">BadRequest (400)</span></span> | <span data-ttu-id="cd496-154">\<The requested action\> se admite en la versión del cliente \<supported client version\> y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="cd496-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="cd496-155">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="cd496-155">Unauthorized</span></span> | <span data-ttu-id="cd496-156">No autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="cd496-156">Unauthorized (401)</span></span> | <span data-ttu-id="cd496-157">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="cd496-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="cd496-158">*Nota: Normalmente se debe a un encabezado de autorización no válido o expirado.*</span><span class="sxs-lookup"><span data-stu-id="cd496-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="cd496-159">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="cd496-159">Forbidden</span></span> | <span data-ttu-id="cd496-160">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="cd496-160">Forbidden (403)</span></span> | <span data-ttu-id="cd496-161">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="cd496-161">Forbidden</span></span> <br /><br /><span data-ttu-id="cd496-162">*Nota: Token válido pero permiso insuficiente para la acción*.</span><span class="sxs-lookup"><span data-stu-id="cd496-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="cd496-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="cd496-163">DisabledFeature</span></span> | <span data-ttu-id="cd496-164">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="cd496-164">Forbidden (403)</span></span> | <span data-ttu-id="cd496-165">La característica inquilino no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="cd496-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="cd496-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="cd496-166">DisallowedOperation</span></span> | <span data-ttu-id="cd496-167">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="cd496-167">Forbidden (403)</span></span> | <span data-ttu-id="cd496-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="cd496-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="cd496-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="cd496-169">NotFound</span></span> | <span data-ttu-id="cd496-170">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="cd496-170">Not Found (404)</span></span> | <span data-ttu-id="cd496-171">Mensaje de error General No encontrado.</span><span class="sxs-lookup"><span data-stu-id="cd496-171">General Not Found error message.</span></span>
<span data-ttu-id="cd496-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="cd496-172">ResourceNotFound</span></span> | <span data-ttu-id="cd496-173">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="cd496-173">Not Found (404)</span></span> | <span data-ttu-id="cd496-174">No \<the requested resource\> se encontró el recurso.</span><span class="sxs-lookup"><span data-stu-id="cd496-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="cd496-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="cd496-175">InternalServerError</span></span> | <span data-ttu-id="cd496-176">Error interno del servidor (500)</span><span class="sxs-lookup"><span data-stu-id="cd496-176">Internal Server Error (500)</span></span> | <span data-ttu-id="cd496-177">*Nota: No hay mensaje de error, vuelva a intentar la operación o [póngase en contacto con Microsoft](/microsoft-365/business-video/get-help-support) si no se resuelve*</span><span class="sxs-lookup"><span data-stu-id="cd496-177">*Note: No error message,  retry the operation or [contact Microsoft](/microsoft-365/business-video/get-help-support) if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="cd496-178">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="cd496-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="cd496-179">Parámetros de cuerpo</span><span class="sxs-lookup"><span data-stu-id="cd496-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd496-180">Los parámetros de cuerpo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="cd496-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="cd496-181">Si experimenta un error *InvalidRequestBody* *o MissingRequiredParameter,* puede deberse a un error tipográfico.</span><span class="sxs-lookup"><span data-stu-id="cd496-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="cd496-182">Revise la documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="cd496-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="cd496-183">Id. de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cd496-183">Tracking ID</span></span>

<span data-ttu-id="cd496-184">Cada respuesta de error contiene un parámetro id. único para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="cd496-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="cd496-185">El nombre de la propiedad de este parámetro es *target*.</span><span class="sxs-lookup"><span data-stu-id="cd496-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="cd496-186">Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador nos ayudará a encontrar la causa raíz del problema.</span><span class="sxs-lookup"><span data-stu-id="cd496-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cd496-187">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="cd496-187">Related articles</span></span>

- [<span data-ttu-id="cd496-188">Microsoft 365 Introducción a las API de Defender</span><span class="sxs-lookup"><span data-stu-id="cd496-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cd496-189">API de Microsoft 365 Defender (versión preliminar) admitidas</span><span class="sxs-lookup"><span data-stu-id="cd496-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="cd496-190">Acceder a las API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd496-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="cd496-191">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="cd496-191">Learn about API limits and licensing</span></span>](api-terms.md)
