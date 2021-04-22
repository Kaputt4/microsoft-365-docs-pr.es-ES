---
title: Códigos de error comunes de la API rest de Microsoft 365 Defender
description: Obtenga información sobre los códigos de error comunes de la API de REST de Microsoft 365 Defender
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
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932886"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="85533-104">Códigos de error comunes de la API rest de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85533-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="85533-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="85533-105">**Applies to:**</span></span>

- <span data-ttu-id="85533-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85533-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85533-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="85533-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="85533-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="85533-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="85533-109">Una operación puede devolver códigos de error en cualquiera de las API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="85533-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="85533-110">Cada respuesta de error contendrá un mensaje de error, lo que puede ayudar a resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="85533-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="85533-111">La columna de mensaje de error de la sección tabla proporciona algunos mensajes de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="85533-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="85533-112">El contenido de los mensajes reales variará en función de los factores que desencadenaron la respuesta.</span><span class="sxs-lookup"><span data-stu-id="85533-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="85533-113">El contenido de las variables se indica en la tabla entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="85533-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="85533-114">Códigos de error</span><span class="sxs-lookup"><span data-stu-id="85533-114">Error codes</span></span>

<span data-ttu-id="85533-115">Código de error</span><span class="sxs-lookup"><span data-stu-id="85533-115">Error code</span></span> | <span data-ttu-id="85533-116">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="85533-116">HTTP status code</span></span> | <span data-ttu-id="85533-117">Message</span><span class="sxs-lookup"><span data-stu-id="85533-117">Message</span></span>
-|-|-
<span data-ttu-id="85533-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="85533-118">BadRequest</span></span> | <span data-ttu-id="85533-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-119">BadRequest (400)</span></span> | <span data-ttu-id="85533-120">Mensaje de error General Bad Request.</span><span class="sxs-lookup"><span data-stu-id="85533-120">General Bad Request error message.</span></span>
<span data-ttu-id="85533-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="85533-121">ODataError</span></span> | <span data-ttu-id="85533-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-122">BadRequest (400)</span></span> | <span data-ttu-id="85533-123">Consulta URI de OData no válida \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="85533-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="85533-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="85533-124">InvalidInput</span></span> | <span data-ttu-id="85533-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-125">BadRequest (400)</span></span> | <span data-ttu-id="85533-126">Entrada no válida \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="85533-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="85533-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="85533-127">InvalidRequestBody</span></span> | <span data-ttu-id="85533-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-128">BadRequest (400)</span></span> | <span data-ttu-id="85533-129">Cuerpo de la solicitud no válido.</span><span class="sxs-lookup"><span data-stu-id="85533-129">Invalid request body.</span></span>
<span data-ttu-id="85533-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="85533-130">InvalidHashValue</span></span> | <span data-ttu-id="85533-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-131">BadRequest (400)</span></span> | <span data-ttu-id="85533-132">El valor hash \<the invalid hash\> no es válido.</span><span class="sxs-lookup"><span data-stu-id="85533-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="85533-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="85533-133">InvalidDomainName</span></span> | <span data-ttu-id="85533-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-134">BadRequest (400)</span></span> | <span data-ttu-id="85533-135">El nombre \<the invalid domain\> de dominio no es válido.</span><span class="sxs-lookup"><span data-stu-id="85533-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="85533-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="85533-136">InvalidIpAddress</span></span> | <span data-ttu-id="85533-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-137">BadRequest (400)</span></span> | <span data-ttu-id="85533-138">La dirección IP \<the invalid IP\> no es válida.</span><span class="sxs-lookup"><span data-stu-id="85533-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="85533-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="85533-139">InvalidUrl</span></span> | <span data-ttu-id="85533-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-140">BadRequest (400)</span></span> | <span data-ttu-id="85533-141">La dirección URL \<the invalid URL\> no es válida.</span><span class="sxs-lookup"><span data-stu-id="85533-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="85533-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="85533-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="85533-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-143">BadRequest (400)</span></span> | <span data-ttu-id="85533-144">Se ha superado el tamaño máximo de lote.</span><span class="sxs-lookup"><span data-stu-id="85533-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="85533-145">Recibido: \<batch size received\> , permitido: {tamaño de lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="85533-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="85533-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="85533-146">MissingRequiredParameter</span></span> | <span data-ttu-id="85533-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-147">BadRequest (400)</span></span> | <span data-ttu-id="85533-148">Falta \<the missing parameter\> el parámetro.</span><span class="sxs-lookup"><span data-stu-id="85533-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="85533-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="85533-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="85533-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-150">BadRequest (400)</span></span> | <span data-ttu-id="85533-151">La plataforma del \<the client OS Platform\> sistema operativo no es compatible con esta acción.</span><span class="sxs-lookup"><span data-stu-id="85533-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="85533-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="85533-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="85533-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="85533-153">BadRequest (400)</span></span> | <span data-ttu-id="85533-154">\<The requested action\> se admite en la versión del cliente \<supported client version\> y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="85533-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="85533-155">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="85533-155">Unauthorized</span></span> | <span data-ttu-id="85533-156">No autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="85533-156">Unauthorized (401)</span></span> | <span data-ttu-id="85533-157">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="85533-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="85533-158">*Nota: Normalmente se debe a un encabezado de autorización no válido o expirado.*</span><span class="sxs-lookup"><span data-stu-id="85533-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="85533-159">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="85533-159">Forbidden</span></span> | <span data-ttu-id="85533-160">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="85533-160">Forbidden (403)</span></span> | <span data-ttu-id="85533-161">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="85533-161">Forbidden</span></span> <br /><br /><span data-ttu-id="85533-162">*Nota: Token válido pero permiso insuficiente para la acción*.</span><span class="sxs-lookup"><span data-stu-id="85533-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="85533-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="85533-163">DisabledFeature</span></span> | <span data-ttu-id="85533-164">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="85533-164">Forbidden (403)</span></span> | <span data-ttu-id="85533-165">La característica inquilino no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="85533-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="85533-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="85533-166">DisallowedOperation</span></span> | <span data-ttu-id="85533-167">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="85533-167">Forbidden (403)</span></span> | <span data-ttu-id="85533-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="85533-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="85533-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="85533-169">NotFound</span></span> | <span data-ttu-id="85533-170">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="85533-170">Not Found (404)</span></span> | <span data-ttu-id="85533-171">Mensaje de error General No encontrado.</span><span class="sxs-lookup"><span data-stu-id="85533-171">General Not Found error message.</span></span>
<span data-ttu-id="85533-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="85533-172">ResourceNotFound</span></span> | <span data-ttu-id="85533-173">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="85533-173">Not Found (404)</span></span> | <span data-ttu-id="85533-174">No \<the requested resource\> se encontró el recurso.</span><span class="sxs-lookup"><span data-stu-id="85533-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="85533-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="85533-175">InternalServerError</span></span> | <span data-ttu-id="85533-176">Error interno del servidor (500)</span><span class="sxs-lookup"><span data-stu-id="85533-176">Internal Server Error (500)</span></span> | <span data-ttu-id="85533-177">*Nota: No hay mensaje de error, vuelva a intentar la operación o póngase en contacto con Microsoft si no se resuelve*</span><span class="sxs-lookup"><span data-stu-id="85533-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="85533-178">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="85533-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="85533-179">Parámetros de cuerpo</span><span class="sxs-lookup"><span data-stu-id="85533-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85533-180">Los parámetros de cuerpo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="85533-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="85533-181">Si experimenta un error *InvalidRequestBody* *o MissingRequiredParameter,* puede deberse a un error tipográfico.</span><span class="sxs-lookup"><span data-stu-id="85533-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="85533-182">Revise la documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="85533-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="85533-183">Id. de seguimiento</span><span class="sxs-lookup"><span data-stu-id="85533-183">Tracking ID</span></span>

<span data-ttu-id="85533-184">Cada respuesta de error contiene un parámetro id. único para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="85533-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="85533-185">El nombre de la propiedad de este parámetro es *target*.</span><span class="sxs-lookup"><span data-stu-id="85533-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="85533-186">Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador nos ayudará a encontrar la causa raíz del problema.</span><span class="sxs-lookup"><span data-stu-id="85533-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="85533-187">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="85533-187">Related articles</span></span>

- [<span data-ttu-id="85533-188">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85533-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="85533-189">API de Microsoft 365 Defender (versión preliminar) admitidas</span><span class="sxs-lookup"><span data-stu-id="85533-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="85533-190">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85533-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="85533-191">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="85533-191">Learn about API limits and licensing</span></span>](api-terms.md)
