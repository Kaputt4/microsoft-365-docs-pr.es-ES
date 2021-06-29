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
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177170"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="e47af-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="e47af-103">UpdateModelSettings</span></span>

<span data-ttu-id="e47af-104">Actualiza las opciones de configuración de los modelos disponibles (etiqueta de retención asociada y descripción del modelo) para un modelo de comprensión mediante documentos de SharePoint Syntex (vea [ejemplo](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="e47af-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="e47af-105">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="e47af-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="e47af-106">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="e47af-106">URI parameters</span></span>

|<span data-ttu-id="e47af-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="e47af-107">Name</span></span> |<span data-ttu-id="e47af-108">En</span><span class="sxs-lookup"><span data-stu-id="e47af-108">In</span></span> |<span data-ttu-id="e47af-109">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e47af-109">Required</span></span>|<span data-ttu-id="e47af-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="e47af-110">Type</span></span>|<span data-ttu-id="e47af-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e47af-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="e47af-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="e47af-112">modelFileName</span></span>|<span data-ttu-id="e47af-113">consulta</span><span class="sxs-lookup"><span data-stu-id="e47af-113">query</span></span>|<span data-ttu-id="e47af-114">True</span><span class="sxs-lookup"><span data-stu-id="e47af-114">True</span></span>|<span data-ttu-id="e47af-115">string</span><span class="sxs-lookup"><span data-stu-id="e47af-115">string</span></span>|<span data-ttu-id="e47af-116">Nombre del archivo del modelo de Syntex.</span><span class="sxs-lookup"><span data-stu-id="e47af-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="e47af-117">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e47af-117">Request headers</span></span>

| <span data-ttu-id="e47af-118">Encabezado</span><span class="sxs-lookup"><span data-stu-id="e47af-118">Header</span></span> | <span data-ttu-id="e47af-119">Valor</span><span class="sxs-lookup"><span data-stu-id="e47af-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="e47af-120">Accept</span><span class="sxs-lookup"><span data-stu-id="e47af-120">Accept</span></span>|<span data-ttu-id="e47af-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="e47af-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="e47af-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e47af-122">Content-Type</span></span>|<span data-ttu-id="e47af-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="e47af-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="e47af-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="e47af-124">x-requestdigest</span></span>|<span data-ttu-id="e47af-125">El resumen adecuado del sitio actual.</span><span class="sxs-lookup"><span data-stu-id="e47af-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="e47af-126">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="e47af-126">Request body</span></span>

|<span data-ttu-id="e47af-127">Nombre</span><span class="sxs-lookup"><span data-stu-id="e47af-127">Name</span></span>    |<span data-ttu-id="e47af-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="e47af-128">Type</span></span>   |<span data-ttu-id="e47af-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="e47af-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="e47af-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="e47af-130">ModelSettings</span></span>|<span data-ttu-id="e47af-131">cadena</span><span class="sxs-lookup"><span data-stu-id="e47af-131">string</span></span>|<span data-ttu-id="e47af-132">JSON de configuración del modelo.</span><span class="sxs-lookup"><span data-stu-id="e47af-132">JSON of model settings.</span></span>|
|<span data-ttu-id="e47af-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="e47af-133">Description</span></span>|<span data-ttu-id="e47af-134">string</span><span class="sxs-lookup"><span data-stu-id="e47af-134">string</span></span>|<span data-ttu-id="e47af-135">La descripción del modelo.</span><span class="sxs-lookup"><span data-stu-id="e47af-135">The model description.</span></span>|
|<span data-ttu-id="e47af-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="e47af-136">RetentionLabel</span></span>| |<span data-ttu-id="e47af-137">Información de la etiqueta asociada (Id. de etiqueta y nombre).</span><span class="sxs-lookup"><span data-stu-id="e47af-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="e47af-138">Respuestas</span><span class="sxs-lookup"><span data-stu-id="e47af-138">Responses</span></span>

| <span data-ttu-id="e47af-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="e47af-139">Name</span></span>   | <span data-ttu-id="e47af-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="e47af-140">Type</span></span>  | <span data-ttu-id="e47af-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="e47af-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="e47af-142">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="e47af-142">200 OK</span></span>| |<span data-ttu-id="e47af-143">Correcto</span><span class="sxs-lookup"><span data-stu-id="e47af-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="e47af-144">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e47af-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="e47af-145">Actualizar configuración del modelo para el contrato de Contoso</span><span class="sxs-lookup"><span data-stu-id="e47af-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="e47af-146">En este ejemplo, se actualizan la descripción del modelo y la etiqueta de retención "Suspensión estándar".</span><span class="sxs-lookup"><span data-stu-id="e47af-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="e47af-147">El Id. de la etiqueta de retención es `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="e47af-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="e47af-148">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="e47af-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="e47af-149">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="e47af-149">Sample response</span></span>

<span data-ttu-id="e47af-150">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="e47af-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="e47af-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e47af-151">See also</span></span>

[<span data-ttu-id="e47af-152">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="e47af-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
