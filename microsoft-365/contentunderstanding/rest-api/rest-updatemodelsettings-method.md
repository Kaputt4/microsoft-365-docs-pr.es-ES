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
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288652"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="bcc31-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="bcc31-103">UpdateModelSettings</span></span>

<span data-ttu-id="bcc31-104">Actualiza las opciones de configuración de los modelos disponibles (etiqueta de retención asociada y descripción del modelo) para un modelo de comprensión mediante documentos de SharePoint Syntex (vea [ejemplo](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="bcc31-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="bcc31-105">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="bcc31-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="bcc31-106">Parámetros de URI</span><span class="sxs-lookup"><span data-stu-id="bcc31-106">URI parameters</span></span>

|<span data-ttu-id="bcc31-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="bcc31-107">Name</span></span> |<span data-ttu-id="bcc31-108">En</span><span class="sxs-lookup"><span data-stu-id="bcc31-108">In</span></span> |<span data-ttu-id="bcc31-109">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="bcc31-109">Required</span></span>|<span data-ttu-id="bcc31-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="bcc31-110">Type</span></span>|<span data-ttu-id="bcc31-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcc31-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="bcc31-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="bcc31-112">modelFileName</span></span>|<span data-ttu-id="bcc31-113">consulta</span><span class="sxs-lookup"><span data-stu-id="bcc31-113">query</span></span>|<span data-ttu-id="bcc31-114">True</span><span class="sxs-lookup"><span data-stu-id="bcc31-114">True</span></span>|<span data-ttu-id="bcc31-115">string</span><span class="sxs-lookup"><span data-stu-id="bcc31-115">string</span></span>|<span data-ttu-id="bcc31-116">Nombre del archivo del modelo de Syntex.</span><span class="sxs-lookup"><span data-stu-id="bcc31-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="bcc31-117">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="bcc31-117">Request headers</span></span>

| <span data-ttu-id="bcc31-118">Encabezado</span><span class="sxs-lookup"><span data-stu-id="bcc31-118">Header</span></span> | <span data-ttu-id="bcc31-119">Valor</span><span class="sxs-lookup"><span data-stu-id="bcc31-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="bcc31-120">Accept</span><span class="sxs-lookup"><span data-stu-id="bcc31-120">Accept</span></span>|<span data-ttu-id="bcc31-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="bcc31-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="bcc31-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bcc31-122">Content-Type</span></span>|<span data-ttu-id="bcc31-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="bcc31-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="bcc31-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="bcc31-124">x-requestdigest</span></span>|<span data-ttu-id="bcc31-125">El resumen adecuado del sitio actual.</span><span class="sxs-lookup"><span data-stu-id="bcc31-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="bcc31-126">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="bcc31-126">Request body</span></span>

|<span data-ttu-id="bcc31-127">Nombre</span><span class="sxs-lookup"><span data-stu-id="bcc31-127">Name</span></span>    |<span data-ttu-id="bcc31-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="bcc31-128">Type</span></span>   |<span data-ttu-id="bcc31-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcc31-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="bcc31-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="bcc31-130">ModelSettings</span></span>|<span data-ttu-id="bcc31-131">cadena</span><span class="sxs-lookup"><span data-stu-id="bcc31-131">string</span></span>|<span data-ttu-id="bcc31-132">JSON de configuración del modelo.</span><span class="sxs-lookup"><span data-stu-id="bcc31-132">JSON of model settings.</span></span>|
|<span data-ttu-id="bcc31-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcc31-133">Description</span></span>|<span data-ttu-id="bcc31-134">string</span><span class="sxs-lookup"><span data-stu-id="bcc31-134">string</span></span>|<span data-ttu-id="bcc31-135">La descripción del modelo.</span><span class="sxs-lookup"><span data-stu-id="bcc31-135">The model description.</span></span>|
|<span data-ttu-id="bcc31-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="bcc31-136">RetentionLabel</span></span>| |<span data-ttu-id="bcc31-137">Información de la etiqueta asociada (Id. de etiqueta y nombre).</span><span class="sxs-lookup"><span data-stu-id="bcc31-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="bcc31-138">Respuestas</span><span class="sxs-lookup"><span data-stu-id="bcc31-138">Responses</span></span>

| <span data-ttu-id="bcc31-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="bcc31-139">Name</span></span>   | <span data-ttu-id="bcc31-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="bcc31-140">Type</span></span>  | <span data-ttu-id="bcc31-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcc31-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="bcc31-142">200 Correcto</span><span class="sxs-lookup"><span data-stu-id="bcc31-142">200 OK</span></span>| |<span data-ttu-id="bcc31-143">Correcto</span><span class="sxs-lookup"><span data-stu-id="bcc31-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="bcc31-144">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="bcc31-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="bcc31-145">Actualizar configuración del modelo para el contrato de Contoso</span><span class="sxs-lookup"><span data-stu-id="bcc31-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="bcc31-146">En este ejemplo, se actualizan la descripción del modelo y la etiqueta de retención "Suspensión estándar".</span><span class="sxs-lookup"><span data-stu-id="bcc31-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="bcc31-147">El Id. de la etiqueta de retención es `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="bcc31-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="bcc31-148">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="bcc31-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="bcc31-149">Respuesta de muestra</span><span class="sxs-lookup"><span data-stu-id="bcc31-149">Sample response</span></span>

<span data-ttu-id="bcc31-150">**Código de estado:** 200</span><span class="sxs-lookup"><span data-stu-id="bcc31-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="bcc31-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcc31-151">See also</span></span>

[<span data-ttu-id="bcc31-152">API de REST del modelo de comprensión mediante documentos de Syntex</span><span class="sxs-lookup"><span data-stu-id="bcc31-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
