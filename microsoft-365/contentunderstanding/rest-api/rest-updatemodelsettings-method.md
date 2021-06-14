---
title: UpdateModelSettings
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
description: Use la API de REST para actualizar la configuración de modelos disponibles para un modelo de comprensión mediante documentos de SharePoint Syntex.
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904306"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="c95f3-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="c95f3-103">UpdateModelSettings</span></span>

<span data-ttu-id="c95f3-104">Actualiza las opciones de configuración de los modelos disponibles (etiqueta de retención asociada y descripción del modelo) para un modelo de comprensión mediante documentos de SharePoint Syntex (vea [ejemplo](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="c95f3-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="c95f3-105">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="c95f3-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="c95f3-106">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="c95f3-106">URI parameters</span></span>

<span data-ttu-id="c95f3-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c95f3-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="c95f3-108">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="c95f3-108">Request headers</span></span>

| <span data-ttu-id="c95f3-109">Encabezado</span><span class="sxs-lookup"><span data-stu-id="c95f3-109">Header</span></span> | <span data-ttu-id="c95f3-110">Valor</span><span class="sxs-lookup"><span data-stu-id="c95f3-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="c95f3-111">Accept</span><span class="sxs-lookup"><span data-stu-id="c95f3-111">Accept</span></span>|<span data-ttu-id="c95f3-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="c95f3-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="c95f3-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c95f3-113">Content-Type</span></span>|<span data-ttu-id="c95f3-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="c95f3-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="c95f3-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="c95f3-115">x-requestdigest</span></span>|<span data-ttu-id="c95f3-116">El resumen adecuado del sitio actual.</span><span class="sxs-lookup"><span data-stu-id="c95f3-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="c95f3-117">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="c95f3-117">Request body</span></span>

|<span data-ttu-id="c95f3-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="c95f3-118">Name</span></span>    |<span data-ttu-id="c95f3-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="c95f3-119">Type</span></span>   |<span data-ttu-id="c95f3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c95f3-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="c95f3-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="c95f3-121">ModelSettings</span></span>|<span data-ttu-id="c95f3-122">cadena</span><span class="sxs-lookup"><span data-stu-id="c95f3-122">string</span></span>|<span data-ttu-id="c95f3-123">JSON de configuración del modelo.</span><span class="sxs-lookup"><span data-stu-id="c95f3-123">JSON of model settings.</span></span>|
|<span data-ttu-id="c95f3-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="c95f3-124">Description</span></span>|<span data-ttu-id="c95f3-125">string</span><span class="sxs-lookup"><span data-stu-id="c95f3-125">string</span></span>|<span data-ttu-id="c95f3-126">La descripción del modelo.</span><span class="sxs-lookup"><span data-stu-id="c95f3-126">The model description.</span></span>|
|<span data-ttu-id="c95f3-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="c95f3-127">RetentionLabel</span></span>| |<span data-ttu-id="c95f3-128">Información de la etiqueta asociada (Id. de etiqueta y nombre).</span><span class="sxs-lookup"><span data-stu-id="c95f3-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="c95f3-129">Respuestas</span><span class="sxs-lookup"><span data-stu-id="c95f3-129">Responses</span></span>

| <span data-ttu-id="c95f3-130">Nombre</span><span class="sxs-lookup"><span data-stu-id="c95f3-130">Name</span></span>   | <span data-ttu-id="c95f3-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="c95f3-131">Type</span></span>  | <span data-ttu-id="c95f3-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="c95f3-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="c95f3-133">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="c95f3-133">200 OK</span></span>| |<span data-ttu-id="c95f3-134">Correcto</span><span class="sxs-lookup"><span data-stu-id="c95f3-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="c95f3-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c95f3-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="c95f3-136">Actualizar configuración del modelo para el contrato de Contoso</span><span class="sxs-lookup"><span data-stu-id="c95f3-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="c95f3-137">En este ejemplo, se actualizan la descripción del modelo y la etiqueta de retención "Suspensión estándar".</span><span class="sxs-lookup"><span data-stu-id="c95f3-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="c95f3-138">El Id. de la etiqueta de retención es `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="c95f3-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="c95f3-139">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="c95f3-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="c95f3-140">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="c95f3-140">Sample response</span></span>

<span data-ttu-id="c95f3-141">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="c95f3-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="c95f3-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c95f3-142">See also</span></span>

[<span data-ttu-id="c95f3-143">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="c95f3-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
