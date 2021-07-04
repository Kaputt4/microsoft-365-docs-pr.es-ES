---
title: Aplicar modelo en lote
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
description: Use la API de REST para aplicar un modelo de comprensión mediante documentos a una o más bibliotecas.
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286542"
---
# <a name="batch-apply-model"></a><span data-ttu-id="d6aab-103">Aplicar modelo en lote</span><span class="sxs-lookup"><span data-stu-id="d6aab-103">Batch Apply model</span></span>

<span data-ttu-id="d6aab-104">Aplica (o sincroniza) un modelo de comprensión mediante documentos entrenado a una o más bibliotecas (vea el [ejemplo](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="d6aab-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="d6aab-105">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="d6aab-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="d6aab-106">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="d6aab-106">URI parameters</span></span>

<span data-ttu-id="d6aab-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d6aab-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="d6aab-108">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="d6aab-108">Request headers</span></span>

| <span data-ttu-id="d6aab-109">Encabezado</span><span class="sxs-lookup"><span data-stu-id="d6aab-109">Header</span></span> | <span data-ttu-id="d6aab-110">Valor</span><span class="sxs-lookup"><span data-stu-id="d6aab-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="d6aab-111">Accept</span><span class="sxs-lookup"><span data-stu-id="d6aab-111">Accept</span></span>|<span data-ttu-id="d6aab-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="d6aab-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="d6aab-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d6aab-113">Content-Type</span></span>|<span data-ttu-id="d6aab-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="d6aab-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="d6aab-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="d6aab-115">x-requestdigest</span></span>|<span data-ttu-id="d6aab-116">El resumen adecuado del sitio actual.</span><span class="sxs-lookup"><span data-stu-id="d6aab-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="d6aab-117">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d6aab-117">Request body</span></span>

| <span data-ttu-id="d6aab-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="d6aab-118">Name</span></span> | <span data-ttu-id="d6aab-119">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d6aab-119">Required</span></span> | <span data-ttu-id="d6aab-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6aab-120">Type</span></span> | <span data-ttu-id="d6aab-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6aab-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="d6aab-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="d6aab-122">__metadata</span></span>|<span data-ttu-id="d6aab-123">sí</span><span class="sxs-lookup"><span data-stu-id="d6aab-123">yes</span></span>|<span data-ttu-id="d6aab-124">cadena</span><span class="sxs-lookup"><span data-stu-id="d6aab-124">string</span></span>|<span data-ttu-id="d6aab-125">Establezca la meta del objeto en SPO.</span><span class="sxs-lookup"><span data-stu-id="d6aab-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="d6aab-126">Use siempre el valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="d6aab-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="d6aab-127">Publicaciones</span><span class="sxs-lookup"><span data-stu-id="d6aab-127">Publications</span></span>|<span data-ttu-id="d6aab-128">sí</span><span class="sxs-lookup"><span data-stu-id="d6aab-128">yes</span></span>|<span data-ttu-id="d6aab-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="d6aab-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="d6aab-130">Colección de MachineLearningPublicationEntityData, cada una de las cuales especifica el modelo y la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="d6aab-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="d6aab-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="d6aab-131">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="d6aab-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="d6aab-132">Name</span></span> | <span data-ttu-id="d6aab-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d6aab-133">Required</span></span> | <span data-ttu-id="d6aab-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6aab-134">Type</span></span> | <span data-ttu-id="d6aab-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6aab-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="d6aab-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="d6aab-136">ModelUniqueId</span></span>|<span data-ttu-id="d6aab-137">sí</span><span class="sxs-lookup"><span data-stu-id="d6aab-137">yes</span></span>|<span data-ttu-id="d6aab-138">cadena</span><span class="sxs-lookup"><span data-stu-id="d6aab-138">string</span></span>|<span data-ttu-id="d6aab-139">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="d6aab-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="d6aab-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="d6aab-140">TargetSiteUrl</span></span>|<span data-ttu-id="d6aab-141">sí</span><span class="sxs-lookup"><span data-stu-id="d6aab-141">yes</span></span>|<span data-ttu-id="d6aab-142">cadena</span><span class="sxs-lookup"><span data-stu-id="d6aab-142">string</span></span>|<span data-ttu-id="d6aab-143">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="d6aab-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="d6aab-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="d6aab-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="d6aab-145">sí</span><span class="sxs-lookup"><span data-stu-id="d6aab-145">yes</span></span>|<span data-ttu-id="d6aab-146">cadena</span><span class="sxs-lookup"><span data-stu-id="d6aab-146">string</span></span>|<span data-ttu-id="d6aab-147">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="d6aab-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="d6aab-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="d6aab-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="d6aab-149">sí</span><span class="sxs-lookup"><span data-stu-id="d6aab-149">yes</span></span>|<span data-ttu-id="d6aab-150">cadena</span><span class="sxs-lookup"><span data-stu-id="d6aab-150">string</span></span>|<span data-ttu-id="d6aab-151">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="d6aab-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="d6aab-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="d6aab-152">ViewOption</span></span>|<span data-ttu-id="d6aab-153">no</span><span class="sxs-lookup"><span data-stu-id="d6aab-153">no</span></span>|<span data-ttu-id="d6aab-154">string</span><span class="sxs-lookup"><span data-stu-id="d6aab-154">string</span></span>|<span data-ttu-id="d6aab-155">Especifica si se debe establecer la nueva vista de modelo como el valor predeterminado de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d6aab-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="d6aab-156">Respuesta</span><span class="sxs-lookup"><span data-stu-id="d6aab-156">Response</span></span>

| <span data-ttu-id="d6aab-157">Nombre</span><span class="sxs-lookup"><span data-stu-id="d6aab-157">Name</span></span>   | <span data-ttu-id="d6aab-158">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6aab-158">Type</span></span>  | <span data-ttu-id="d6aab-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6aab-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="d6aab-160">201 Created</span><span class="sxs-lookup"><span data-stu-id="d6aab-160">201 Created</span></span>||<span data-ttu-id="d6aab-p102">Se trata de una API personalizada para admitir la aplicación de un modelo a bibliotecas de varios documentos. En caso de éxito parcial, se podría devolver 201 creado y el llamador debe inspeccionar el cuerpo de la respuesta para comprender si el modelo se ha aplicado correctamente a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="d6aab-p102">This is a customized API to support applying a model to multi document libraries. In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="d6aab-163">Cuerpo de la respuesta</span><span class="sxs-lookup"><span data-stu-id="d6aab-163">Response Body</span></span>

| <span data-ttu-id="d6aab-164">Nombre</span><span class="sxs-lookup"><span data-stu-id="d6aab-164">Name</span></span>   | <span data-ttu-id="d6aab-165">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6aab-165">Type</span></span>  | <span data-ttu-id="d6aab-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6aab-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="d6aab-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="d6aab-167">TotalSuccesses</span></span>|<span data-ttu-id="d6aab-168">int</span><span class="sxs-lookup"><span data-stu-id="d6aab-168">int</span></span>|<span data-ttu-id="d6aab-169">El número total de un modelo que se aplica correctamente a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="d6aab-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="d6aab-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="d6aab-170">TotalFailures</span></span>|<span data-ttu-id="d6aab-171">int</span><span class="sxs-lookup"><span data-stu-id="d6aab-171">int</span></span>|<span data-ttu-id="d6aab-172">Número total de un modelo que no se puede aplicar a una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="d6aab-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="d6aab-173">Detalles</span><span class="sxs-lookup"><span data-stu-id="d6aab-173">Details</span></span>|<span data-ttu-id="d6aab-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="d6aab-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="d6aab-175">Colección de MachineLearningPublicationResult, cada una de las cuales especifica el resultado detallado de aplicar el modelo a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="d6aab-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="d6aab-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="d6aab-176">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="d6aab-177">Nombre</span><span class="sxs-lookup"><span data-stu-id="d6aab-177">Name</span></span>   | <span data-ttu-id="d6aab-178">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6aab-178">Type</span></span>  | <span data-ttu-id="d6aab-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6aab-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="d6aab-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="d6aab-180">StatusCode</span></span>|<span data-ttu-id="d6aab-181">int</span><span class="sxs-lookup"><span data-stu-id="d6aab-181">int</span></span>|<span data-ttu-id="d6aab-182">El código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="d6aab-182">The HTTP status code.</span></span>|
|<span data-ttu-id="d6aab-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="d6aab-183">ErrorMessage</span></span>|<span data-ttu-id="d6aab-184">string</span><span class="sxs-lookup"><span data-stu-id="d6aab-184">string</span></span>|<span data-ttu-id="d6aab-185">Mensaje de error que indica el problema al aplicar el modelo a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="d6aab-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="d6aab-186">Publicación</span><span class="sxs-lookup"><span data-stu-id="d6aab-186">Publication</span></span>|<span data-ttu-id="d6aab-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="d6aab-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="d6aab-188">Especifica la información del modelo y la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="d6aab-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="d6aab-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="d6aab-189">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="d6aab-190">Nombre</span><span class="sxs-lookup"><span data-stu-id="d6aab-190">Name</span></span> | <span data-ttu-id="d6aab-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6aab-191">Type</span></span> | <span data-ttu-id="d6aab-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6aab-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="d6aab-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="d6aab-193">ModelUniqueId</span></span>|<span data-ttu-id="d6aab-194">string</span><span class="sxs-lookup"><span data-stu-id="d6aab-194">string</span></span>|<span data-ttu-id="d6aab-195">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="d6aab-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="d6aab-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="d6aab-196">TargetSiteUrl</span></span>|<span data-ttu-id="d6aab-197">string</span><span class="sxs-lookup"><span data-stu-id="d6aab-197">string</span></span>|<span data-ttu-id="d6aab-198">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="d6aab-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="d6aab-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="d6aab-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="d6aab-200">string</span><span class="sxs-lookup"><span data-stu-id="d6aab-200">string</span></span>|<span data-ttu-id="d6aab-201">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="d6aab-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="d6aab-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="d6aab-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="d6aab-203">string</span><span class="sxs-lookup"><span data-stu-id="d6aab-203">string</span></span>|<span data-ttu-id="d6aab-204">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="d6aab-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="d6aab-205">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d6aab-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="d6aab-206">Aplicar un modelo a la biblioteca de documentos de contratos en el sitio de repositorio</span><span class="sxs-lookup"><span data-stu-id="d6aab-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="d6aab-207">En este ejemplo, el id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="d6aab-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="d6aab-208">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="d6aab-208">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="d6aab-209">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="d6aab-209">Sample response</span></span>

<span data-ttu-id="d6aab-210">En la respuesta, TotalFailures y TotalSuccesses hacen referencia al número de errores y éxitos del modelo que se aplica a las bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="d6aab-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="d6aab-211">**Código de estado:** 201</span><span class="sxs-lookup"><span data-stu-id="d6aab-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="d6aab-212">Ver también</span><span class="sxs-lookup"><span data-stu-id="d6aab-212">See also</span></span>

[<span data-ttu-id="d6aab-213">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="d6aab-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
