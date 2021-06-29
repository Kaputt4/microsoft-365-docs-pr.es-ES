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
ms.openlocfilehash: 3a796bcdb38a9a6930b51f7d585febb69082732e
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177086"
---
# <a name="create-classification-request"></a>Crear solicitud de clasificación

Crea una solicitud para clasificar uno o más archivos con el modelo de comprensión mediante documentos aplicado (vea [ejemplo](rest-createclassificationrequest.md#examples)).

El servicio REST de SharePoint Online (y SharePoint 2016 y versiones locales posteriores) admite la combinación de varias solicitudes. Las solicitudes se combinan en una sola llamada al servicio mediante el uso de la opción de consulta $batch de OData Este método se puede usar para poner en cola los elementos de trabajo de clasificación para cientos de documentos a la vez.

## <a name="http-request"></a>Solicitud HTTP

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a>Parámetros de URI

Ninguno

## <a name="request-headers"></a>Encabezados de solicitud

| Encabezado | Valor |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Resumen adecuado del sitio actual|

## <a name="request-body"></a>Cuerpo de la solicitud

|Nombre    |Tipo   |Descripción |
|--------|-------|------------|
|_metadata|cadena |Establezca la meta del objeto en SPO. Use siempre el valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}. |
|TargetSiteId|guid|El Id. del sitio donde se encuentra el archivo que se clasificará.|
|TargetWebId|guid|El Id. de la web en la que se encuentra el archivo que se clasificará.|
|TargetUniqueId|guid|El Id. del archivo que se clasificará.|

## <a name="responses"></a>Respuestas

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|201 Created| |Correcto|

## <a name="examples"></a>Ejemplos

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Poner en cola una solicitud para clasificar un archivo de Id. "e6cff8b7-c90c-4564-b5b8-033449090932"

#### <a name="sample-request"></a>Solicitud de muestra

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a>Respuesta de muestra

**Código de estado:** 201

## <a name="see-also"></a>Ver también

[API de REST del modelo de comprensión mediante documentos de Syntex](syntex-model-rest-api.md)
