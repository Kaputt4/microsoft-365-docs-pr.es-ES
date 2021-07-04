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
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287458"
---
# <a name="batchdelete"></a><span data-ttu-id="a026d-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="a026d-103">BatchDelete</span></span>

<span data-ttu-id="a026d-104">Quita un modelo de comprensión mediante documentos de una o más bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="a026d-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="a026d-105">Tenga en cuenta que un modelo debe quitarse de todas las bibliotecas antes de que se pueda eliminar (vea [ejemplo](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="a026d-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="a026d-106">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="a026d-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="a026d-107">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="a026d-107">URI parameters</span></span>

<span data-ttu-id="a026d-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a026d-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="a026d-109">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="a026d-109">Request headers</span></span>

| <span data-ttu-id="a026d-110">Encabezado</span><span class="sxs-lookup"><span data-stu-id="a026d-110">Header</span></span> | <span data-ttu-id="a026d-111">Valor</span><span class="sxs-lookup"><span data-stu-id="a026d-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="a026d-112">Accept</span><span class="sxs-lookup"><span data-stu-id="a026d-112">Accept</span></span>|<span data-ttu-id="a026d-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="a026d-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="a026d-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a026d-114">Content-Type</span></span>|<span data-ttu-id="a026d-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="a026d-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="a026d-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="a026d-116">x-requestdigest</span></span>|<span data-ttu-id="a026d-117">El resumen adecuado del sitio actual.</span><span class="sxs-lookup"><span data-stu-id="a026d-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="a026d-118">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="a026d-118">Request body</span></span>

| <span data-ttu-id="a026d-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="a026d-119">Name</span></span> | <span data-ttu-id="a026d-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="a026d-120">Required</span></span> | <span data-ttu-id="a026d-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="a026d-121">Type</span></span> | <span data-ttu-id="a026d-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a026d-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a026d-123">Publicaciones</span><span class="sxs-lookup"><span data-stu-id="a026d-123">Publications</span></span>|<span data-ttu-id="a026d-124">sí</span><span class="sxs-lookup"><span data-stu-id="a026d-124">yes</span></span>|<span data-ttu-id="a026d-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="a026d-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="a026d-126">Colección de MachineLearningPublicationEntityData, cada una de las cuales especifica el modelo y la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="a026d-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="a026d-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="a026d-127">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="a026d-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="a026d-128">Name</span></span> | <span data-ttu-id="a026d-129">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="a026d-129">Required</span></span> | <span data-ttu-id="a026d-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="a026d-130">Type</span></span> | <span data-ttu-id="a026d-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a026d-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a026d-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a026d-132">ModelUniqueId</span></span>|<span data-ttu-id="a026d-133">sí</span><span class="sxs-lookup"><span data-stu-id="a026d-133">yes</span></span>|<span data-ttu-id="a026d-134">cadena</span><span class="sxs-lookup"><span data-stu-id="a026d-134">string</span></span>|<span data-ttu-id="a026d-135">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="a026d-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="a026d-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="a026d-136">TargetSiteUrl</span></span>|<span data-ttu-id="a026d-137">sí</span><span class="sxs-lookup"><span data-stu-id="a026d-137">yes</span></span>|<span data-ttu-id="a026d-138">cadena</span><span class="sxs-lookup"><span data-stu-id="a026d-138">string</span></span>|<span data-ttu-id="a026d-139">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a026d-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="a026d-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a026d-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="a026d-141">sí</span><span class="sxs-lookup"><span data-stu-id="a026d-141">yes</span></span>|<span data-ttu-id="a026d-142">cadena</span><span class="sxs-lookup"><span data-stu-id="a026d-142">string</span></span>|<span data-ttu-id="a026d-143">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a026d-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="a026d-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a026d-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="a026d-145">sí</span><span class="sxs-lookup"><span data-stu-id="a026d-145">yes</span></span>|<span data-ttu-id="a026d-146">cadena</span><span class="sxs-lookup"><span data-stu-id="a026d-146">string</span></span>|<span data-ttu-id="a026d-147">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a026d-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="a026d-148">Respuesta</span><span class="sxs-lookup"><span data-stu-id="a026d-148">Response</span></span>

| <span data-ttu-id="a026d-149">Nombre</span><span class="sxs-lookup"><span data-stu-id="a026d-149">Name</span></span>   | <span data-ttu-id="a026d-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="a026d-150">Type</span></span>  | <span data-ttu-id="a026d-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="a026d-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a026d-152">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="a026d-152">200 OK</span></span>||<span data-ttu-id="a026d-p102">Se trata de una API personalizada para admitir la eliminación de un modelo de bibliotecas de varios documentos. En caso de éxito parcial, se podría devolver 200 OK y el autor de la llamada debe inspeccionar el cuerpo de la respuesta para comprender si el modelo se ha quitado correctamente de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a026d-p102">This is a customized API to support removing a model from multi document libraries. In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="a026d-155">Cuerpo de la respuesta</span><span class="sxs-lookup"><span data-stu-id="a026d-155">Response Body</span></span>

| <span data-ttu-id="a026d-156">Nombre</span><span class="sxs-lookup"><span data-stu-id="a026d-156">Name</span></span>   | <span data-ttu-id="a026d-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="a026d-157">Type</span></span>  | <span data-ttu-id="a026d-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="a026d-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a026d-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="a026d-159">TotalSuccesses</span></span>|<span data-ttu-id="a026d-160">int</span><span class="sxs-lookup"><span data-stu-id="a026d-160">int</span></span>|<span data-ttu-id="a026d-161">El número total de un modelo que se elimina correctamente de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a026d-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="a026d-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="a026d-162">TotalFailures</span></span>|<span data-ttu-id="a026d-163">int</span><span class="sxs-lookup"><span data-stu-id="a026d-163">int</span></span>|<span data-ttu-id="a026d-164">Número total de un modelo que no se puede quitar de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a026d-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="a026d-165">Detalles</span><span class="sxs-lookup"><span data-stu-id="a026d-165">Details</span></span>|<span data-ttu-id="a026d-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="a026d-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="a026d-167">Colección de MachineLearningPublicationResult, cada una de las cuales especifica el resultado detallado de quitar el modelo de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a026d-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="a026d-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="a026d-168">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="a026d-169">Nombre</span><span class="sxs-lookup"><span data-stu-id="a026d-169">Name</span></span>   | <span data-ttu-id="a026d-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="a026d-170">Type</span></span>  | <span data-ttu-id="a026d-171">Descripción</span><span class="sxs-lookup"><span data-stu-id="a026d-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a026d-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="a026d-172">StatusCode</span></span>|<span data-ttu-id="a026d-173">int</span><span class="sxs-lookup"><span data-stu-id="a026d-173">int</span></span>|<span data-ttu-id="a026d-174">El código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="a026d-174">The HTTP status code.</span></span>|
|<span data-ttu-id="a026d-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="a026d-175">ErrorMessage</span></span>|<span data-ttu-id="a026d-176">string</span><span class="sxs-lookup"><span data-stu-id="a026d-176">string</span></span>|<span data-ttu-id="a026d-177">Mensaje de error que indica el problema al aplicar el modelo a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a026d-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="a026d-178">Publicación</span><span class="sxs-lookup"><span data-stu-id="a026d-178">Publication</span></span>|<span data-ttu-id="a026d-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="a026d-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="a026d-180">Especifica la información del modelo y la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="a026d-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="a026d-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="a026d-181">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="a026d-182">Nombre</span><span class="sxs-lookup"><span data-stu-id="a026d-182">Name</span></span> | <span data-ttu-id="a026d-183">Tipo</span><span class="sxs-lookup"><span data-stu-id="a026d-183">Type</span></span> | <span data-ttu-id="a026d-184">Descripción</span><span class="sxs-lookup"><span data-stu-id="a026d-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="a026d-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a026d-185">ModelUniqueId</span></span>|<span data-ttu-id="a026d-186">string</span><span class="sxs-lookup"><span data-stu-id="a026d-186">string</span></span>|<span data-ttu-id="a026d-187">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="a026d-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="a026d-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="a026d-188">TargetSiteUrl</span></span>|<span data-ttu-id="a026d-189">string</span><span class="sxs-lookup"><span data-stu-id="a026d-189">string</span></span>|<span data-ttu-id="a026d-190">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a026d-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="a026d-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a026d-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="a026d-192">string</span><span class="sxs-lookup"><span data-stu-id="a026d-192">string</span></span>|<span data-ttu-id="a026d-193">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a026d-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="a026d-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a026d-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="a026d-195">string</span><span class="sxs-lookup"><span data-stu-id="a026d-195">string</span></span>|<span data-ttu-id="a026d-196">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a026d-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="a026d-197">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a026d-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="a026d-198">Quitar un modelo de la biblioteca de documentos de contratos en el sitio del repositorio</span><span class="sxs-lookup"><span data-stu-id="a026d-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="a026d-199">En este ejemplo, el Id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="a026d-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="a026d-200">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="a026d-200">Sample request</span></span>

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

#### <a name="sample-response"></a><span data-ttu-id="a026d-201">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="a026d-201">Sample response</span></span>

<span data-ttu-id="a026d-202">En la respuesta, TotalFailures y TotalSuccesses hacen referencia al número de errores y éxitos del modelo que se quita de las bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="a026d-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="a026d-203">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="a026d-203">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a026d-204">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a026d-204">See also</span></span>

[<span data-ttu-id="a026d-205">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="a026d-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
