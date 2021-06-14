---
title: Crear modelo
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
description: Use la API de REST para crear un modelo y su tipo de contenido asociado.
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904296"
---
# <a name="create-model"></a><span data-ttu-id="852ce-103">Crear modelo</span><span class="sxs-lookup"><span data-stu-id="852ce-103">Create model</span></span>

<span data-ttu-id="852ce-104">Crea un modelo y su tipo de contenido asociado.</span><span class="sxs-lookup"><span data-stu-id="852ce-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="852ce-105">Tenga en cuenta que esto solo crea el modelo.</span><span class="sxs-lookup"><span data-stu-id="852ce-105">Note that this only creates the model.</span></span> <span data-ttu-id="852ce-106">Aún tendrá que ser entrenado en el centro de contenido (vea [ejemplo](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="852ce-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="852ce-107">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="852ce-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="852ce-108">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="852ce-108">URI Parameters</span></span>

<span data-ttu-id="852ce-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="852ce-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="852ce-110">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="852ce-110">Request headers</span></span>

| <span data-ttu-id="852ce-111">Encabezado</span><span class="sxs-lookup"><span data-stu-id="852ce-111">Header</span></span> | <span data-ttu-id="852ce-112">Valor</span><span class="sxs-lookup"><span data-stu-id="852ce-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="852ce-113">Accept</span><span class="sxs-lookup"><span data-stu-id="852ce-113">Accept</span></span>|<span data-ttu-id="852ce-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="852ce-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="852ce-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="852ce-115">Content-Type</span></span>|<span data-ttu-id="852ce-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="852ce-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="852ce-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="852ce-117">x-requestdigest</span></span>|<span data-ttu-id="852ce-118">Resumen adecuado del sitio actual</span><span class="sxs-lookup"><span data-stu-id="852ce-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="852ce-119">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="852ce-119">Request body</span></span>

|<span data-ttu-id="852ce-120">Nombre</span><span class="sxs-lookup"><span data-stu-id="852ce-120">Name</span></span>    |<span data-ttu-id="852ce-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="852ce-121">Type</span></span>   |<span data-ttu-id="852ce-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="852ce-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="852ce-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="852ce-123">_metadata</span></span>|  |<span data-ttu-id="852ce-124">Establezca la meta del objeto en SPO.</span><span class="sxs-lookup"><span data-stu-id="852ce-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="852ce-125">Use siempre el valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="852ce-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="852ce-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="852ce-126">ContentTypeGroup</span></span>|<span data-ttu-id="852ce-127">cadena</span><span class="sxs-lookup"><span data-stu-id="852ce-127">string</span></span>|<span data-ttu-id="852ce-128">El grupo de tipo de contenido asociado al modelo.</span><span class="sxs-lookup"><span data-stu-id="852ce-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="852ce-129">El valor predeterminado es "Tipos de contenido de documento inteligente".</span><span class="sxs-lookup"><span data-stu-id="852ce-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="852ce-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="852ce-130">ContentTypeName</span></span>|<span data-ttu-id="852ce-131">cadena</span><span class="sxs-lookup"><span data-stu-id="852ce-131">string</span></span>|<span data-ttu-id="852ce-132">El nombre del tipo de contenido asociado.</span><span class="sxs-lookup"><span data-stu-id="852ce-132">The associated content type name.</span></span> <span data-ttu-id="852ce-133">El archivo de modelo creado tendrá el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="852ce-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="852ce-134">Respuestas</span><span class="sxs-lookup"><span data-stu-id="852ce-134">Responses</span></span>

| <span data-ttu-id="852ce-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="852ce-135">Name</span></span>   | <span data-ttu-id="852ce-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="852ce-136">Type</span></span>  | <span data-ttu-id="852ce-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="852ce-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="852ce-138">201 Created</span><span class="sxs-lookup"><span data-stu-id="852ce-138">201 Created</span></span>| |<span data-ttu-id="852ce-139">Correcto</span><span class="sxs-lookup"><span data-stu-id="852ce-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="852ce-140">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="852ce-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="852ce-141">Crear un nuevo modelo de comprensión mediante documentos denominado "Contrato de Contoso"</span><span class="sxs-lookup"><span data-stu-id="852ce-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="852ce-142">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="852ce-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a><span data-ttu-id="852ce-143">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="852ce-143">Sample response</span></span>

<span data-ttu-id="852ce-144">**Código de estado:** 201</span><span class="sxs-lookup"><span data-stu-id="852ce-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="852ce-145">Ver también</span><span class="sxs-lookup"><span data-stu-id="852ce-145">See also</span></span>

[<span data-ttu-id="852ce-146">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="852ce-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
