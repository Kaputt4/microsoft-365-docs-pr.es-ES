---
title: Aplicar modelo
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904356"
---
# <a name="apply-model"></a><span data-ttu-id="acd19-103">Aplicar modelo</span><span class="sxs-lookup"><span data-stu-id="acd19-103">Apply model</span></span>

<span data-ttu-id="acd19-104">Aplica (o sincroniza) un modelo de comprensión mediante documentos entrenado a una o más bibliotecas (vea el [ejemplo](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="acd19-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="acd19-105">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="acd19-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="acd19-106">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="acd19-106">URI parameters</span></span>

<span data-ttu-id="acd19-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="acd19-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="acd19-108">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="acd19-108">Request headers</span></span>

| <span data-ttu-id="acd19-109">Encabezado</span><span class="sxs-lookup"><span data-stu-id="acd19-109">Header</span></span> | <span data-ttu-id="acd19-110">Valor</span><span class="sxs-lookup"><span data-stu-id="acd19-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="acd19-111">Accept</span><span class="sxs-lookup"><span data-stu-id="acd19-111">Accept</span></span>|<span data-ttu-id="acd19-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="acd19-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="acd19-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="acd19-113">Content-Type</span></span>|<span data-ttu-id="acd19-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="acd19-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="acd19-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="acd19-115">x-requestdigest</span></span>|<span data-ttu-id="acd19-116">El resumen adecuado del sitio actual.</span><span class="sxs-lookup"><span data-stu-id="acd19-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="acd19-117">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="acd19-117">Request body</span></span>

| <span data-ttu-id="acd19-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="acd19-118">Name</span></span> | <span data-ttu-id="acd19-119">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="acd19-119">Required</span></span> | <span data-ttu-id="acd19-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="acd19-120">Type</span></span> | <span data-ttu-id="acd19-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="acd19-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="acd19-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="acd19-122">ModelUniqueId</span></span>|<span data-ttu-id="acd19-123">sí</span><span class="sxs-lookup"><span data-stu-id="acd19-123">yes</span></span>|<span data-ttu-id="acd19-124">string</span><span class="sxs-lookup"><span data-stu-id="acd19-124">string</span></span>|<span data-ttu-id="acd19-125">El id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="acd19-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="acd19-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="acd19-126">TargetSiteUrl</span></span>|<span data-ttu-id="acd19-127">sí</span><span class="sxs-lookup"><span data-stu-id="acd19-127">yes</span></span>|<span data-ttu-id="acd19-128">string</span><span class="sxs-lookup"><span data-stu-id="acd19-128">string</span></span>|<span data-ttu-id="acd19-129">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="acd19-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="acd19-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="acd19-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="acd19-131">sí</span><span class="sxs-lookup"><span data-stu-id="acd19-131">yes</span></span>|<span data-ttu-id="acd19-132">string</span><span class="sxs-lookup"><span data-stu-id="acd19-132">string</span></span>|<span data-ttu-id="acd19-133">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="acd19-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="acd19-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="acd19-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="acd19-135">sí</span><span class="sxs-lookup"><span data-stu-id="acd19-135">yes</span></span>|<span data-ttu-id="acd19-136">string</span><span class="sxs-lookup"><span data-stu-id="acd19-136">string</span></span>|<span data-ttu-id="acd19-137">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="acd19-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="acd19-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="acd19-138">ViewOption</span></span>|<span data-ttu-id="acd19-139">no</span><span class="sxs-lookup"><span data-stu-id="acd19-139">no</span></span>|<span data-ttu-id="acd19-140">string</span><span class="sxs-lookup"><span data-stu-id="acd19-140">string</span></span>|<span data-ttu-id="acd19-141">Especifica si se debe establecer la nueva vista de modelo como el valor predeterminado de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="acd19-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="acd19-142">Respuesta</span><span class="sxs-lookup"><span data-stu-id="acd19-142">Response</span></span>

| <span data-ttu-id="acd19-143">Nombre</span><span class="sxs-lookup"><span data-stu-id="acd19-143">Name</span></span>   | <span data-ttu-id="acd19-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="acd19-144">Type</span></span>  | <span data-ttu-id="acd19-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="acd19-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="acd19-146">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="acd19-146">200 OK</span></span>| |<span data-ttu-id="acd19-147">Correcto</span><span class="sxs-lookup"><span data-stu-id="acd19-147">Success</span></span>|
|<span data-ttu-id="acd19-148">201 Created</span><span class="sxs-lookup"><span data-stu-id="acd19-148">201 Created</span></span>| |<span data-ttu-id="acd19-149">Tenga en cuenta que, dado que esta API puede aplicar el modelo a varias bibliotecas, se podría devolver un código 201 aunque haya un error al aplicar el modelo a una de las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="acd19-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="acd19-150">Compruebe el cuerpo de la respuesta para entender si el modelo se ha aplicado correctamente a todas las bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="acd19-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="acd19-151">Vea [Cuerpo de la solicitud](rest-applymodel-method.md#request-body) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="acd19-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="acd19-152">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="acd19-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="acd19-153">Aplicar un modelo a la biblioteca de documentos de contratos en el sitio de repositorio</span><span class="sxs-lookup"><span data-stu-id="acd19-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="acd19-154">En este ejemplo, el id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="acd19-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="acd19-155">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="acd19-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="acd19-156">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="acd19-156">Sample response</span></span>

<span data-ttu-id="acd19-157">En la respuesta, TotalFailures y TotalSuccesses hacen referencia al número de errores y éxitos del modelo que se aplica a las bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="acd19-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="acd19-158">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="acd19-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="acd19-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acd19-159">See also</span></span>

[<span data-ttu-id="acd19-160">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="acd19-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
