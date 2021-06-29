---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Use la API de REST para quitar un modelo de comprensión mediante documentos de una o más bibliotecas.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177242"
---
# <a name="batchdelete"></a><span data-ttu-id="061da-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="061da-103">BatchDelete</span></span>

<span data-ttu-id="061da-104">Quita un modelo de comprensión mediante documentos de una o más bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="061da-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="061da-105">Tenga en cuenta que un modelo debe quitarse de todas las bibliotecas antes de que se pueda eliminar (vea [ejemplo](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="061da-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="061da-106">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="061da-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="061da-107">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="061da-107">URI parameters</span></span>

<span data-ttu-id="061da-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="061da-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="061da-109">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="061da-109">Request headers</span></span>

| <span data-ttu-id="061da-110">Encabezado</span><span class="sxs-lookup"><span data-stu-id="061da-110">Header</span></span> | <span data-ttu-id="061da-111">Valor</span><span class="sxs-lookup"><span data-stu-id="061da-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="061da-112">Accept</span><span class="sxs-lookup"><span data-stu-id="061da-112">Accept</span></span>|<span data-ttu-id="061da-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="061da-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="061da-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="061da-114">Content-Type</span></span>|<span data-ttu-id="061da-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="061da-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="061da-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="061da-116">x-requestdigest</span></span>|<span data-ttu-id="061da-117">El resumen adecuado del sitio actual.</span><span class="sxs-lookup"><span data-stu-id="061da-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="061da-118">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="061da-118">Request body</span></span>

| <span data-ttu-id="061da-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="061da-119">Name</span></span> | <span data-ttu-id="061da-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="061da-120">Required</span></span> | <span data-ttu-id="061da-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="061da-121">Type</span></span> | <span data-ttu-id="061da-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="061da-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="061da-123">Publicaciones</span><span class="sxs-lookup"><span data-stu-id="061da-123">Publications</span></span>|<span data-ttu-id="061da-124">sí</span><span class="sxs-lookup"><span data-stu-id="061da-124">yes</span></span>|<span data-ttu-id="061da-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="061da-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="061da-126">Colección de MachineLearningPublicationEntityData, cada una de las cuales especifica el modelo y la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="061da-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="061da-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="061da-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="061da-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="061da-128">Name</span></span> | <span data-ttu-id="061da-129">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="061da-129">Required</span></span> | <span data-ttu-id="061da-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="061da-130">Type</span></span> | <span data-ttu-id="061da-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="061da-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="061da-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="061da-132">ModelUniqueId</span></span>|<span data-ttu-id="061da-133">sí</span><span class="sxs-lookup"><span data-stu-id="061da-133">yes</span></span>|<span data-ttu-id="061da-134">string</span><span class="sxs-lookup"><span data-stu-id="061da-134">string</span></span>|<span data-ttu-id="061da-135">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="061da-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="061da-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="061da-136">TargetSiteUrl</span></span>|<span data-ttu-id="061da-137">sí</span><span class="sxs-lookup"><span data-stu-id="061da-137">yes</span></span>|<span data-ttu-id="061da-138">string</span><span class="sxs-lookup"><span data-stu-id="061da-138">string</span></span>|<span data-ttu-id="061da-139">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="061da-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="061da-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="061da-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="061da-141">sí</span><span class="sxs-lookup"><span data-stu-id="061da-141">yes</span></span>|<span data-ttu-id="061da-142">string</span><span class="sxs-lookup"><span data-stu-id="061da-142">string</span></span>|<span data-ttu-id="061da-143">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="061da-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="061da-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="061da-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="061da-145">sí</span><span class="sxs-lookup"><span data-stu-id="061da-145">yes</span></span>|<span data-ttu-id="061da-146">string</span><span class="sxs-lookup"><span data-stu-id="061da-146">string</span></span>|<span data-ttu-id="061da-147">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="061da-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="061da-148">Respuesta</span><span class="sxs-lookup"><span data-stu-id="061da-148">Response</span></span>

| <span data-ttu-id="061da-149">Nombre</span><span class="sxs-lookup"><span data-stu-id="061da-149">Name</span></span>   | <span data-ttu-id="061da-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="061da-150">Type</span></span>  | <span data-ttu-id="061da-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="061da-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="061da-152">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="061da-152">200 OK</span></span>||<span data-ttu-id="061da-153">Se trata de una API personalizada para admitir la eliminación de un modelo de varias bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="061da-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="061da-154">En caso de éxito parcial, se podría devolver el 200 OK y el llamador debe inspeccionar el cuerpo de la respuesta para comprender si el modelo se ha quitado correctamente de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="061da-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="061da-155">Cuerpo de la respuesta</span><span class="sxs-lookup"><span data-stu-id="061da-155">Response Body</span></span>
| <span data-ttu-id="061da-156">Nombre</span><span class="sxs-lookup"><span data-stu-id="061da-156">Name</span></span>   | <span data-ttu-id="061da-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="061da-157">Type</span></span>  | <span data-ttu-id="061da-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="061da-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="061da-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="061da-159">TotalSuccesses</span></span>|<span data-ttu-id="061da-160">int</span><span class="sxs-lookup"><span data-stu-id="061da-160">int</span></span>|<span data-ttu-id="061da-161">El número total de un modelo que se elimina correctamente de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="061da-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="061da-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="061da-162">TotalFailures</span></span>|<span data-ttu-id="061da-163">int</span><span class="sxs-lookup"><span data-stu-id="061da-163">int</span></span>|<span data-ttu-id="061da-164">Número total de un modelo que no se puede quitar de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="061da-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="061da-165">Detalles</span><span class="sxs-lookup"><span data-stu-id="061da-165">Details</span></span>|<span data-ttu-id="061da-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="061da-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="061da-167">Colección de MachineLearningPublicationResult, cada una de las cuales especifica el resultado detallado de quitar el modelo de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="061da-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="061da-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="061da-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="061da-169">Nombre</span><span class="sxs-lookup"><span data-stu-id="061da-169">Name</span></span>   | <span data-ttu-id="061da-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="061da-170">Type</span></span>  | <span data-ttu-id="061da-171">Descripción</span><span class="sxs-lookup"><span data-stu-id="061da-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="061da-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="061da-172">StatusCode</span></span>|<span data-ttu-id="061da-173">int</span><span class="sxs-lookup"><span data-stu-id="061da-173">int</span></span>|<span data-ttu-id="061da-174">El código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="061da-174">The HTTP status code.</span></span>|
|<span data-ttu-id="061da-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="061da-175">ErrorMessage</span></span>|<span data-ttu-id="061da-176">string</span><span class="sxs-lookup"><span data-stu-id="061da-176">string</span></span>|<span data-ttu-id="061da-177">Mensaje de error que indica el problema al aplicar el modelo a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="061da-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="061da-178">Publicación</span><span class="sxs-lookup"><span data-stu-id="061da-178">Publication</span></span>|<span data-ttu-id="061da-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="061da-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="061da-180">Especifica la información del modelo y la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="061da-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="061da-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="061da-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="061da-182">Nombre</span><span class="sxs-lookup"><span data-stu-id="061da-182">Name</span></span> | <span data-ttu-id="061da-183">Tipo</span><span class="sxs-lookup"><span data-stu-id="061da-183">Type</span></span> | <span data-ttu-id="061da-184">Descripción</span><span class="sxs-lookup"><span data-stu-id="061da-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="061da-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="061da-185">ModelUniqueId</span></span>|<span data-ttu-id="061da-186">string</span><span class="sxs-lookup"><span data-stu-id="061da-186">string</span></span>|<span data-ttu-id="061da-187">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="061da-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="061da-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="061da-188">TargetSiteUrl</span></span>|<span data-ttu-id="061da-189">string</span><span class="sxs-lookup"><span data-stu-id="061da-189">string</span></span>|<span data-ttu-id="061da-190">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="061da-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="061da-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="061da-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="061da-192">string</span><span class="sxs-lookup"><span data-stu-id="061da-192">string</span></span>|<span data-ttu-id="061da-193">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="061da-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="061da-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="061da-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="061da-195">string</span><span class="sxs-lookup"><span data-stu-id="061da-195">string</span></span>|<span data-ttu-id="061da-196">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="061da-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="061da-197">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="061da-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="061da-198">Quitar un modelo de la biblioteca de documentos de contratos en el sitio del repositorio</span><span class="sxs-lookup"><span data-stu-id="061da-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="061da-199">En este ejemplo, el Id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="061da-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="061da-200">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="061da-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a><span data-ttu-id="061da-201">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="061da-201">Sample response</span></span>

<span data-ttu-id="061da-202">En la respuesta, TotalFailures y TotalSuccesses hacen referencia al número de errores y éxitos del modelo que se quita de las bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="061da-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="061da-203">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="061da-203">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="061da-204">Consulte también</span><span class="sxs-lookup"><span data-stu-id="061da-204">See also</span></span>

[<span data-ttu-id="061da-205">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="061da-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
