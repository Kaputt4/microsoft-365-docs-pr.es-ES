---
title: Obtener información sobre el modelo y la biblioteca
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
description: Use la API de REST para obtener información sobre un modelo y la biblioteca donde se ha aplicado.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904299"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="9ca8f-103">Obtener información de modelo y biblioteca</span><span class="sxs-lookup"><span data-stu-id="9ca8f-103">Get model and library information</span></span>

<span data-ttu-id="9ca8f-104">Obtiene información sobre un modelo y la biblioteca donde se ha aplicado (consulte [ejemplo](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="9ca8f-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="9ca8f-105">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="9ca8f-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="9ca8f-106">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="9ca8f-106">URI parameters</span></span>

| <span data-ttu-id="9ca8f-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="9ca8f-107">Name</span></span> | <span data-ttu-id="9ca8f-108">En</span><span class="sxs-lookup"><span data-stu-id="9ca8f-108">In</span></span> | <span data-ttu-id="9ca8f-109">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="9ca8f-109">Required</span></span> | <span data-ttu-id="9ca8f-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="9ca8f-110">Type</span></span> | <span data-ttu-id="9ca8f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ca8f-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="9ca8f-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="9ca8f-112">ModelUniqueId</span></span>|<span data-ttu-id="9ca8f-113">consulta</span><span class="sxs-lookup"><span data-stu-id="9ca8f-113">query</span></span>|<span data-ttu-id="9ca8f-114">True</span><span class="sxs-lookup"><span data-stu-id="9ca8f-114">True</span></span>|<span data-ttu-id="9ca8f-115">GUID</span><span class="sxs-lookup"><span data-stu-id="9ca8f-115">GUID</span></span>|<span data-ttu-id="9ca8f-116">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="9ca8f-117">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="9ca8f-117">Request headers</span></span>

| <span data-ttu-id="9ca8f-118">Encabezado</span><span class="sxs-lookup"><span data-stu-id="9ca8f-118">Header</span></span> | <span data-ttu-id="9ca8f-119">Valor</span><span class="sxs-lookup"><span data-stu-id="9ca8f-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="9ca8f-120">Accept</span><span class="sxs-lookup"><span data-stu-id="9ca8f-120">Accept</span></span>|<span data-ttu-id="9ca8f-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="9ca8f-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="9ca8f-122">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="9ca8f-122">Request body</span></span>

| <span data-ttu-id="9ca8f-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="9ca8f-123">Name</span></span> | <span data-ttu-id="9ca8f-124">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="9ca8f-124">Required</span></span> | <span data-ttu-id="9ca8f-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="9ca8f-125">Type</span></span> | <span data-ttu-id="9ca8f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ca8f-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="9ca8f-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="9ca8f-127">ModelUniqueId</span></span>|<span data-ttu-id="9ca8f-128">sí</span><span class="sxs-lookup"><span data-stu-id="9ca8f-128">yes</span></span>|<span data-ttu-id="9ca8f-129">cadena</span><span class="sxs-lookup"><span data-stu-id="9ca8f-129">string</span></span>|<span data-ttu-id="9ca8f-130">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="9ca8f-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="9ca8f-131">TargetSiteUrl</span></span>|<span data-ttu-id="9ca8f-132">sí</span><span class="sxs-lookup"><span data-stu-id="9ca8f-132">yes</span></span>|<span data-ttu-id="9ca8f-133">cadena</span><span class="sxs-lookup"><span data-stu-id="9ca8f-133">string</span></span>|<span data-ttu-id="9ca8f-134">La dirección URL completa del sitio de biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="9ca8f-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="9ca8f-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="9ca8f-136">sí</span><span class="sxs-lookup"><span data-stu-id="9ca8f-136">yes</span></span>|<span data-ttu-id="9ca8f-137">cadena</span><span class="sxs-lookup"><span data-stu-id="9ca8f-137">string</span></span>|<span data-ttu-id="9ca8f-138">La dirección URL relativa del servidor de la Web de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="9ca8f-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="9ca8f-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="9ca8f-140">sí</span><span class="sxs-lookup"><span data-stu-id="9ca8f-140">yes</span></span>|<span data-ttu-id="9ca8f-141">cadena</span><span class="sxs-lookup"><span data-stu-id="9ca8f-141">string</span></span>|<span data-ttu-id="9ca8f-142">La dirección URL relativa al servidor de la biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="9ca8f-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="9ca8f-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="9ca8f-144">sí</span><span class="sxs-lookup"><span data-stu-id="9ca8f-144">yes</span></span>|<span data-ttu-id="9ca8f-145">int</span><span class="sxs-lookup"><span data-stu-id="9ca8f-145">int</span></span>|<span data-ttu-id="9ca8f-146">La marca que indica si la biblioteca de destino se ha quitado o no.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="9ca8f-147">Respuesta</span><span class="sxs-lookup"><span data-stu-id="9ca8f-147">Response</span></span>

| <span data-ttu-id="9ca8f-148">Nombre</span><span class="sxs-lookup"><span data-stu-id="9ca8f-148">Name</span></span>   | <span data-ttu-id="9ca8f-149">Tipo</span><span class="sxs-lookup"><span data-stu-id="9ca8f-149">Type</span></span>  | <span data-ttu-id="9ca8f-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ca8f-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="9ca8f-151">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="9ca8f-151">200 OK</span></span>| |<span data-ttu-id="9ca8f-152">Correcto</span><span class="sxs-lookup"><span data-stu-id="9ca8f-152">Success</span></span>|
|<span data-ttu-id="9ca8f-153">201 Created</span><span class="sxs-lookup"><span data-stu-id="9ca8f-153">201 Created</span></span>| |<span data-ttu-id="9ca8f-154">Tenga en cuenta que, dado que esta API puede aplicar el modelo a varias bibliotecas, se podría devolver un código 201 aunque haya un error al aplicar el modelo a una de las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="9ca8f-155">Compruebe el cuerpo de la respuesta para entender si el modelo se ha aplicado correctamente a todas las bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="9ca8f-156">Vea [Cuerpo de la solicitud](rest-getmodelandlibraryinfo.md#request-body) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="9ca8f-157">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9ca8f-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="9ca8f-158">Obtener información sobre el modelo de contratos y la biblioteca de documentos actualizada en el sitio del repositorio</span><span class="sxs-lookup"><span data-stu-id="9ca8f-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="9ca8f-159">En este ejemplo, el Id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="9ca8f-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="9ca8f-160">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="9ca8f-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="9ca8f-161">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="9ca8f-161">Sample response</span></span>

<span data-ttu-id="9ca8f-162">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="9ca8f-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="9ca8f-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ca8f-163">See also</span></span>

[<span data-ttu-id="9ca8f-164">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="9ca8f-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
