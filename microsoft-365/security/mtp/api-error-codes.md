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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719219"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="8b30d-104">Códigos de error comunes de la API de REST de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="8b30d-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8b30d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8b30d-105">**Applies to:**</span></span>

- <span data-ttu-id="8b30d-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8b30d-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b30d-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="8b30d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8b30d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8b30d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8b30d-109">Los códigos de error pueden devolverse mediante una operación en cualquiera de las API de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="8b30d-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="8b30d-110">Cada respuesta de error contendrá un mensaje de error, que puede ayudar a resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="8b30d-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="8b30d-111">La columna mensaje de error de la sección tabla proporciona algunos ejemplos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8b30d-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="8b30d-112">El contenido de los mensajes reales variará en función de los factores que desencadenaron la respuesta.</span><span class="sxs-lookup"><span data-stu-id="8b30d-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="8b30d-113">El contenido de la variable se indica en la tabla por corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="8b30d-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="8b30d-114">Códigos de error</span><span class="sxs-lookup"><span data-stu-id="8b30d-114">Error codes</span></span>

<span data-ttu-id="8b30d-115">Código de error</span><span class="sxs-lookup"><span data-stu-id="8b30d-115">Error code</span></span> | <span data-ttu-id="8b30d-116">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="8b30d-116">HTTP status code</span></span> | <span data-ttu-id="8b30d-117">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8b30d-117">Message</span></span>
-|-|-
<span data-ttu-id="8b30d-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="8b30d-118">BadRequest</span></span> | <span data-ttu-id="8b30d-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-119">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-120">Mensaje de error de solicitud incorrecta general.</span><span class="sxs-lookup"><span data-stu-id="8b30d-120">General Bad Request error message.</span></span>
<span data-ttu-id="8b30d-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="8b30d-121">ODataError</span></span> | <span data-ttu-id="8b30d-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-122">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-123">Consulta URI de OData no válida \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="8b30d-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="8b30d-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="8b30d-124">InvalidInput</span></span> | <span data-ttu-id="8b30d-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-125">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-126">Entrada no válida \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="8b30d-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="8b30d-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="8b30d-127">InvalidRequestBody</span></span> | <span data-ttu-id="8b30d-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-128">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-129">Cuerpo de la solicitud no válido.</span><span class="sxs-lookup"><span data-stu-id="8b30d-129">Invalid request body.</span></span>
<span data-ttu-id="8b30d-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="8b30d-130">InvalidHashValue</span></span> | <span data-ttu-id="8b30d-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-131">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-132">El valor hash \<the invalid hash\> no es válido.</span><span class="sxs-lookup"><span data-stu-id="8b30d-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="8b30d-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="8b30d-133">InvalidDomainName</span></span> | <span data-ttu-id="8b30d-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-134">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-135">El nombre de dominio \<the invalid domain\> no es válido.</span><span class="sxs-lookup"><span data-stu-id="8b30d-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="8b30d-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="8b30d-136">InvalidIpAddress</span></span> | <span data-ttu-id="8b30d-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-137">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-138">La dirección IP \<the invalid IP\> no es válida.</span><span class="sxs-lookup"><span data-stu-id="8b30d-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="8b30d-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="8b30d-139">InvalidUrl</span></span> | <span data-ttu-id="8b30d-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-140">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-141">La dirección URL \<the invalid URL\> no es válida.</span><span class="sxs-lookup"><span data-stu-id="8b30d-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="8b30d-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="8b30d-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="8b30d-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-143">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-144">Tamaño máximo de lote superado.</span><span class="sxs-lookup"><span data-stu-id="8b30d-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="8b30d-145">Recibido: \<batch size received\> , permitido: {tamaño de lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="8b30d-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="8b30d-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="8b30d-146">MissingRequiredParameter</span></span> | <span data-ttu-id="8b30d-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-147">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-148">Falta el parámetro \<the missing parameter\> .</span><span class="sxs-lookup"><span data-stu-id="8b30d-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="8b30d-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="8b30d-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="8b30d-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-150">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-151">La plataforma del sistema operativo \<the client OS Platform\> no es compatible con esta acción.</span><span class="sxs-lookup"><span data-stu-id="8b30d-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="8b30d-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="8b30d-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="8b30d-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8b30d-153">BadRequest (400)</span></span> | <span data-ttu-id="8b30d-154">\<The requested action\> es compatible con la versión de cliente \<supported client version\> y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8b30d-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="8b30d-155">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="8b30d-155">Unauthorized</span></span> | <span data-ttu-id="8b30d-156">No autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="8b30d-156">Unauthorized (401)</span></span> | <span data-ttu-id="8b30d-157">No autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="8b30d-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="8b30d-158">*Nota: normalmente causada por un encabezado de autorización no válido o expirado.*</span><span class="sxs-lookup"><span data-stu-id="8b30d-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="8b30d-159">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="8b30d-159">Forbidden</span></span> | <span data-ttu-id="8b30d-160">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="8b30d-160">Forbidden (403)</span></span> | <span data-ttu-id="8b30d-161">Prohibido (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="8b30d-161">Forbidden</span></span> <br /><br /><span data-ttu-id="8b30d-162">*Nota: token válido, pero permiso insuficiente para la acción*.</span><span class="sxs-lookup"><span data-stu-id="8b30d-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="8b30d-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="8b30d-163">DisabledFeature</span></span> | <span data-ttu-id="8b30d-164">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="8b30d-164">Forbidden (403)</span></span> | <span data-ttu-id="8b30d-165">La característica de inquilino no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="8b30d-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="8b30d-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="8b30d-166">DisallowedOperation</span></span> | <span data-ttu-id="8b30d-167">Prohibido (403)</span><span class="sxs-lookup"><span data-stu-id="8b30d-167">Forbidden (403)</span></span> | <span data-ttu-id="8b30d-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="8b30d-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="8b30d-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="8b30d-169">NotFound</span></span> | <span data-ttu-id="8b30d-170">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="8b30d-170">Not Found (404)</span></span> | <span data-ttu-id="8b30d-171">Mensaje de error general no encontrado.</span><span class="sxs-lookup"><span data-stu-id="8b30d-171">General Not Found error message.</span></span>
<span data-ttu-id="8b30d-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="8b30d-172">ResourceNotFound</span></span> | <span data-ttu-id="8b30d-173">No encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="8b30d-173">Not Found (404)</span></span> | <span data-ttu-id="8b30d-174">\<the requested resource\>No se encontró el recurso.</span><span class="sxs-lookup"><span data-stu-id="8b30d-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="8b30d-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="8b30d-175">InternalServerError</span></span> | <span data-ttu-id="8b30d-176">Error interno del servidor (500)</span><span class="sxs-lookup"><span data-stu-id="8b30d-176">Internal Server Error (500)</span></span> | <span data-ttu-id="8b30d-177">*Nota: no hay ningún mensaje de error, vuelva a intentar la operación o póngase en contacto con Microsoft si no se resuelve*</span><span class="sxs-lookup"><span data-stu-id="8b30d-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="8b30d-178">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="8b30d-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="8b30d-179">Parámetros de cuerpo</span><span class="sxs-lookup"><span data-stu-id="8b30d-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b30d-180">Los parámetros Body distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8b30d-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="8b30d-181">Si experimenta un error *InvalidRequestBody* o *MissingRequiredParameter* , puede deberse a un error tipográfico.</span><span class="sxs-lookup"><span data-stu-id="8b30d-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="8b30d-182">Revise la documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8b30d-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="8b30d-183">IDENTIFICADOR de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8b30d-183">Tracking ID</span></span>

<span data-ttu-id="8b30d-184">Cada respuesta de error contiene un parámetro ID único para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8b30d-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="8b30d-185">El nombre de la propiedad de este parámetro es *target*.</span><span class="sxs-lookup"><span data-stu-id="8b30d-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="8b30d-186">Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador nos ayudará a encontrar la causa raíz del problema.</span><span class="sxs-lookup"><span data-stu-id="8b30d-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8b30d-187">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="8b30d-187">Related articles</span></span>

- [<span data-ttu-id="8b30d-188">Información general sobre las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="8b30d-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="8b30d-189">API de Microsoft 365 Defender (versión preliminar) admitidas</span><span class="sxs-lookup"><span data-stu-id="8b30d-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="8b30d-190">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="8b30d-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8b30d-191">Obtenga información sobre los límites de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="8b30d-191">Learn about API limits and licensing</span></span>](api-terms.md)
