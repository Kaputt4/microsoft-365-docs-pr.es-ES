---
title: Crear solicitud de clasificación
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
description: Use la API de REST para crear una solicitud para clasificar uno o más archivos con un modelo de comprensión mediante documentos entrenado.
ms.openlocfilehash: 6a218db181368c2837d570062b6101bc3bacfb05
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904279"
---
# <a name="create-classification-request"></a><span data-ttu-id="9f99b-103">Crear solicitud de clasificación</span><span class="sxs-lookup"><span data-stu-id="9f99b-103">Create classification request</span></span>

<span data-ttu-id="9f99b-104">Crea una solicitud para clasificar uno o más archivos con el modelo de comprensión mediante documentos aplicado (vea [ejemplo](rest-createclassificationrequest.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="9f99b-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="9f99b-105">El servicio REST de SharePoint Online (y SharePoint 2016 y versiones locales posteriores) admite la combinación de varias solicitudes.</span><span class="sxs-lookup"><span data-stu-id="9f99b-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="9f99b-106">Las solicitudes se combinan en una sola llamada al servicio mediante el uso de la opción de consulta $batch de OData</span><span class="sxs-lookup"><span data-stu-id="9f99b-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="9f99b-107">Este método se puede usar para poner en cola los elementos de trabajo de clasificación para cientos de documentos a la vez.</span><span class="sxs-lookup"><span data-stu-id="9f99b-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="9f99b-108">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="9f99b-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="9f99b-109">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="9f99b-109">URI Parameters</span></span>

<span data-ttu-id="9f99b-110">Ninguno</span><span class="sxs-lookup"><span data-stu-id="9f99b-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="9f99b-111">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="9f99b-111">Request headers</span></span>

| <span data-ttu-id="9f99b-112">Encabezado</span><span class="sxs-lookup"><span data-stu-id="9f99b-112">Header</span></span> | <span data-ttu-id="9f99b-113">Valor</span><span class="sxs-lookup"><span data-stu-id="9f99b-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="9f99b-114">Accept</span><span class="sxs-lookup"><span data-stu-id="9f99b-114">Accept</span></span>|<span data-ttu-id="9f99b-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="9f99b-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="9f99b-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9f99b-116">Content-Type</span></span>|<span data-ttu-id="9f99b-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="9f99b-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="9f99b-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="9f99b-118">x-requestdigest</span></span>|<span data-ttu-id="9f99b-119">Resumen adecuado del sitio actual</span><span class="sxs-lookup"><span data-stu-id="9f99b-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="9f99b-120">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="9f99b-120">Request body</span></span>

|<span data-ttu-id="9f99b-121">Nombre</span><span class="sxs-lookup"><span data-stu-id="9f99b-121">Name</span></span>    |<span data-ttu-id="9f99b-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="9f99b-122">Type</span></span>   |<span data-ttu-id="9f99b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f99b-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="9f99b-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="9f99b-124">_metadata</span></span>|<span data-ttu-id="9f99b-125">cadena</span><span class="sxs-lookup"><span data-stu-id="9f99b-125">string</span></span> |<span data-ttu-id="9f99b-126">Establezca la meta del objeto en SPO.</span><span class="sxs-lookup"><span data-stu-id="9f99b-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="9f99b-127">Use siempre el valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="9f99b-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="9f99b-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="9f99b-128">TargetSiteId</span></span>|<span data-ttu-id="9f99b-129">guid</span><span class="sxs-lookup"><span data-stu-id="9f99b-129">guid</span></span>|<span data-ttu-id="9f99b-130">El Id. del sitio donde se encuentra el archivo que se clasificará.</span><span class="sxs-lookup"><span data-stu-id="9f99b-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="9f99b-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="9f99b-131">TargetWebId</span></span>|<span data-ttu-id="9f99b-132">guid</span><span class="sxs-lookup"><span data-stu-id="9f99b-132">guid</span></span>|<span data-ttu-id="9f99b-133">El Id. de la web en la que se encuentra el archivo que se clasificará.</span><span class="sxs-lookup"><span data-stu-id="9f99b-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="9f99b-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="9f99b-134">TargetUniqueId</span></span>|<span data-ttu-id="9f99b-135">guid</span><span class="sxs-lookup"><span data-stu-id="9f99b-135">guid</span></span>|<span data-ttu-id="9f99b-136">El Id. del archivo que se clasificará.</span><span class="sxs-lookup"><span data-stu-id="9f99b-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="9f99b-137">Respuestas</span><span class="sxs-lookup"><span data-stu-id="9f99b-137">Responses</span></span>

| <span data-ttu-id="9f99b-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="9f99b-138">Name</span></span>   | <span data-ttu-id="9f99b-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="9f99b-139">Type</span></span>  | <span data-ttu-id="9f99b-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f99b-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="9f99b-141">201 Created</span><span class="sxs-lookup"><span data-stu-id="9f99b-141">201 Created</span></span>| |<span data-ttu-id="9f99b-142">Correcto</span><span class="sxs-lookup"><span data-stu-id="9f99b-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="9f99b-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9f99b-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="9f99b-144">Poner en cola una solicitud para clasificar un archivo de Id. "e6cff8b7-c90c-4564-b5b8-033449090932"</span><span class="sxs-lookup"><span data-stu-id="9f99b-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="9f99b-145">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="9f99b-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="9f99b-146">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="9f99b-146">Sample response</span></span>

<span data-ttu-id="9f99b-147">**Código de estado:** 201</span><span class="sxs-lookup"><span data-stu-id="9f99b-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="9f99b-148">Ver también</span><span class="sxs-lookup"><span data-stu-id="9f99b-148">See also</span></span>

[<span data-ttu-id="9f99b-149">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="9f99b-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
