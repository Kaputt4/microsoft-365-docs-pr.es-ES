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
# <a name="updatemodelsettings"></a>UpdateModelSettings

Actualiza las opciones de configuración de los modelos disponibles (etiqueta de retención asociada y descripción del modelo) para un modelo de comprensión mediante documentos de SharePoint Syntex (vea [ejemplo](rest-updatemodelsettings-method.md#examples)).

## <a name="http-request"></a>Solicitud HTTP

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>Parámetros de URI

|Nombre |En |Obligatorio|Tipo|Descripción|
|-----|---|--------|----|-----------|
|modelFileName|consulta|True|string|Nombre del archivo del modelo de Syntex.|

## <a name="request-headers"></a>Encabezados de solicitud

| Encabezado | Valor |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|El resumen adecuado del sitio actual.|

## <a name="request-body"></a>Cuerpo de la solicitud

|Nombre    |Tipo   |Descripción |
|--------|-------|-------|
|ModelSettings|cadena|JSON de configuración del modelo.|
|Descripción|string|La descripción del modelo.|
|RetentionLabel| |Información de la etiqueta asociada (Id. de etiqueta y nombre).|

## <a name="responses"></a>Respuestas

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|200 Correcto| |Correcto|

## <a name="examples"></a>Ejemplos

### <a name="update-model-settings-for-contoso-contract"></a>Actualizar configuración del modelo para el contrato de Contoso

En este ejemplo, se actualizan la descripción del modelo y la etiqueta de retención "Suspensión estándar". El Id. de la etiqueta de retención es `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.

#### <a name="sample-request"></a>Solicitud de muestra

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>Respuesta de muestra

**Código de estado:** 200

## <a name="see-also"></a>Consulte también

[API de REST del modelo de comprensión mediante documentos de Syntex](syntex-model-rest-api.md)
