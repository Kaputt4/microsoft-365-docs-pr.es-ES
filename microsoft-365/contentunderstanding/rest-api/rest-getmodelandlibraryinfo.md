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
ms.openlocfilehash: 29240a6210e2079a082be6c3a07aae890d932719
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288760"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="2f484-103">Obtener información de modelo y biblioteca</span><span class="sxs-lookup"><span data-stu-id="2f484-103">Get model and library information</span></span>

<span data-ttu-id="2f484-104">Obtiene información sobre un modelo y la biblioteca donde se ha aplicado (consulte [ejemplo](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="2f484-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="2f484-105">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="2f484-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbymodeluniqueid('{modelUniqueId}') HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="2f484-106">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="2f484-106">URI parameters</span></span>

| <span data-ttu-id="2f484-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="2f484-107">Name</span></span> | <span data-ttu-id="2f484-108">En</span><span class="sxs-lookup"><span data-stu-id="2f484-108">In</span></span> | <span data-ttu-id="2f484-109">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="2f484-109">Required</span></span> | <span data-ttu-id="2f484-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="2f484-110">Type</span></span> | <span data-ttu-id="2f484-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f484-111">Description</span></span> |
|--------|-------|--------|------------|-----------|
|<span data-ttu-id="2f484-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="2f484-112">ModelUniqueId</span></span>|<span data-ttu-id="2f484-113">consulta</span><span class="sxs-lookup"><span data-stu-id="2f484-113">query</span></span>|<span data-ttu-id="2f484-114">True</span><span class="sxs-lookup"><span data-stu-id="2f484-114">True</span></span>|<span data-ttu-id="2f484-115">GUID</span><span class="sxs-lookup"><span data-stu-id="2f484-115">GUID</span></span>|<span data-ttu-id="2f484-116">El Id. único del archivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="2f484-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="2f484-117">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="2f484-117">Request headers</span></span>

| <span data-ttu-id="2f484-118">Encabezado</span><span class="sxs-lookup"><span data-stu-id="2f484-118">Header</span></span> | <span data-ttu-id="2f484-119">Valor</span><span class="sxs-lookup"><span data-stu-id="2f484-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="2f484-120">Accept</span><span class="sxs-lookup"><span data-stu-id="2f484-120">Accept</span></span>|<span data-ttu-id="2f484-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="2f484-121">application/json;odata=verbose</span></span>|


## <a name="response"></a><span data-ttu-id="2f484-122">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2f484-122">Response</span></span>

| <span data-ttu-id="2f484-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="2f484-123">Name</span></span>   | <span data-ttu-id="2f484-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="2f484-124">Type</span></span>  | <span data-ttu-id="2f484-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f484-125">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="2f484-126">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="2f484-126">200 OK</span></span>| |<span data-ttu-id="2f484-127">Correcto</span><span class="sxs-lookup"><span data-stu-id="2f484-127">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="2f484-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2f484-128">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="2f484-129">Obtener información sobre el modelo de contratos y la biblioteca de documentos actualizada en el sitio del repositorio</span><span class="sxs-lookup"><span data-stu-id="2f484-129">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="2f484-130">En este ejemplo, el Id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="2f484-130">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="2f484-131">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="2f484-131">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc') HTTP/1.1
```

#### <a name="sample-response"></a><span data-ttu-id="2f484-132">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="2f484-132">Sample response</span></span>

<span data-ttu-id="2f484-133">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="2f484-133">**Status code:** 200</span></span>

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
}
```

## <a name="see-also"></a><span data-ttu-id="2f484-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f484-134">See also</span></span>

[<span data-ttu-id="2f484-135">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="2f484-135">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
