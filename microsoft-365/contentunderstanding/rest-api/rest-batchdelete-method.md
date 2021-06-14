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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904276"
---
# <a name="batchdelete"></a><span data-ttu-id="a5179-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="a5179-103">BatchDelete</span></span>

<span data-ttu-id="a5179-104">Quita un modelo de comprensión mediante documentos de una o más bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="a5179-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="a5179-105">Tenga en cuenta que un modelo debe quitarse de todas las bibliotecas antes de que se pueda eliminar (vea [ejemplo](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="a5179-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="a5179-106">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="a5179-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="a5179-107">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="a5179-107">URI parameters</span></span>

<span data-ttu-id="a5179-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a5179-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="a5179-109">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="a5179-109">Request headers</span></span>

| <span data-ttu-id="a5179-110">Encabezado</span><span class="sxs-lookup"><span data-stu-id="a5179-110">Header</span></span> | <span data-ttu-id="a5179-111">Valor</span><span class="sxs-lookup"><span data-stu-id="a5179-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="a5179-112">Accept</span><span class="sxs-lookup"><span data-stu-id="a5179-112">Accept</span></span>|<span data-ttu-id="a5179-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="a5179-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="a5179-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a5179-114">Content-Type</span></span>|<span data-ttu-id="a5179-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="a5179-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="a5179-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="a5179-116">x-requestdigest</span></span>|<span data-ttu-id="a5179-117">El resumen adecuado del sitio actual.</span><span class="sxs-lookup"><span data-stu-id="a5179-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="a5179-118">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="a5179-118">Request body</span></span>

| <span data-ttu-id="a5179-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="a5179-119">Name</span></span> | <span data-ttu-id="a5179-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="a5179-120">Required</span></span> | <span data-ttu-id="a5179-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="a5179-121">Type</span></span> | <span data-ttu-id="a5179-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5179-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a5179-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a5179-123">ModelUniqueId</span></span>|<span data-ttu-id="a5179-124">sí</span><span class="sxs-lookup"><span data-stu-id="a5179-124">yes</span></span>|<span data-ttu-id="a5179-125">cadena</span><span class="sxs-lookup"><span data-stu-id="a5179-125">string</span></span>|<span data-ttu-id="a5179-126">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="a5179-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="a5179-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="a5179-127">TargetSiteUrl</span></span>|<span data-ttu-id="a5179-128">sí</span><span class="sxs-lookup"><span data-stu-id="a5179-128">yes</span></span>|<span data-ttu-id="a5179-129">cadena</span><span class="sxs-lookup"><span data-stu-id="a5179-129">string</span></span>|<span data-ttu-id="a5179-130">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a5179-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="a5179-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a5179-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="a5179-132">sí</span><span class="sxs-lookup"><span data-stu-id="a5179-132">yes</span></span>|<span data-ttu-id="a5179-133">cadena</span><span class="sxs-lookup"><span data-stu-id="a5179-133">string</span></span>|<span data-ttu-id="a5179-134">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a5179-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="a5179-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a5179-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="a5179-136">sí</span><span class="sxs-lookup"><span data-stu-id="a5179-136">yes</span></span>|<span data-ttu-id="a5179-137">cadena</span><span class="sxs-lookup"><span data-stu-id="a5179-137">string</span></span>|<span data-ttu-id="a5179-138">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a5179-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="a5179-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="a5179-139">ViewOption</span></span>|<span data-ttu-id="a5179-140">no</span><span class="sxs-lookup"><span data-stu-id="a5179-140">no</span></span>|<span data-ttu-id="a5179-141">string</span><span class="sxs-lookup"><span data-stu-id="a5179-141">string</span></span>|<span data-ttu-id="a5179-142">Especifica si se debe establecer la nueva vista de modelo como el valor predeterminado de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a5179-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="a5179-143">Respuesta</span><span class="sxs-lookup"><span data-stu-id="a5179-143">Response</span></span>

| <span data-ttu-id="a5179-144">Nombre</span><span class="sxs-lookup"><span data-stu-id="a5179-144">Name</span></span>   | <span data-ttu-id="a5179-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="a5179-145">Type</span></span>  | <span data-ttu-id="a5179-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5179-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a5179-147">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="a5179-147">200 OK</span></span>| |<span data-ttu-id="a5179-148">Correcto</span><span class="sxs-lookup"><span data-stu-id="a5179-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="a5179-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a5179-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="a5179-150">Quitar un modelo de la biblioteca de documentos de contratos en el sitio del repositorio</span><span class="sxs-lookup"><span data-stu-id="a5179-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="a5179-151">En este ejemplo, el Id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="a5179-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="a5179-152">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="a5179-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="a5179-153">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="a5179-153">Sample response</span></span>

<span data-ttu-id="a5179-154">En la respuesta, TotalFailures y TotalSuccesses hacen referencia al número de errores y éxitos del modelo que se aplica a las bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="a5179-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="a5179-155">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="a5179-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a5179-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5179-156">See also</span></span>

[<span data-ttu-id="a5179-157">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="a5179-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
