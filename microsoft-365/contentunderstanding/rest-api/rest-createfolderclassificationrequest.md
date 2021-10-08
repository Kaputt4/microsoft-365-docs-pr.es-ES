---
title: Crear solicitud de clasificación de carpetas
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
ms.localizationpriority: high
description: Use la API de REST para crear una solicitud para clasificar una carpeta completa con un modelo entrenado de comprensión mediante documentos.
ms.openlocfilehash: ea5748b5eb376872738d30b142927314abfe9d3e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60186878"
---
# <a name="create-folder-classification-request"></a>Crear solicitud de clasificación de carpetas

Crea una solicitud para clasificar una carpeta completa durante las horas de poca actividad mediante el modelo aplicado de comprensión de documentos (para obtener más información, vea el [ejemplo](rest-createfolderclassificationrequest.md#examples)). Esta API se puede usar para clasificar una biblioteca de documentos completa mediante la creación de un elemento de trabajo para su carpeta raíz.

## <a name="http-request"></a>Solicitud HTTP

```http
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
|TargetSiteId|guid|El id. del sitio donde se encuentra el archivo que se clasificará. Esto se puede omitir cuando TargetSiteUrl tenga un valor. |
|TargetSiteUrl|string|Dirección URL completa del sitio donde se encuentra la carpeta que se va a clasificar. Esto se puede omitir cuando TargeSiteId tenga un valor.|
|TargetWebId|guid|Id. de la web en la que se encuentra la carpeta que se clasificará. Esto se puede omitir cuando TargetWebServerRelativeUrl tenga un valor. |
|TargetWebServerRelativeUrl|string|Dirección URL relativa del servidor de la web donde se encuentra la carpeta que se va a clasificar. Esto se puede omitir cuando TargetWebId tenga un valor.  |
|TargetUniqueId|guid|Id. de la carpeta que se va a clasificar. Esto se puede omitir cuando TargetServerRelativeUrl tenga un valor. |
|TargetServerRelativeUrl|cadena|Dirección URL relativa del servidor donde se encuentra la carpeta que se va a clasificar. Esto se puede omitir cuando TargetUniqueId tenga un valor.|
|IsFolder|booleano|Marca que indica si lo que se clasificará es una carpeta. Establezca esto en TRUE siempre para crear un elemento de trabajo de clasificación de carpetas. |


## <a name="responses"></a>Respuestas

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|201 Created| |La respuesta es personalizada. Si se produce un error, podría devolver 201 Created. El autor de la llamada debe comprobar adicionalmente el cuerpo de la respuesta para determinar el resultado exacto.|

## <a name="response-body"></a>Cuerpo de la respuesta

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|StatusCode |int |Código de estado HTTP. Si no es 200 o 201, la API debería haber producido un error.|
|ErrorMessage |string |Mensaje de error que indica el problema al aplicar el modelo a la biblioteca de documentos.|

## <a name="examples"></a>Ejemplos

### <a name="enqueue-a-request-to-classify-a-whole-folder-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Poner en cola una solicitud para clasificar una carpeta completa de id. "e6cff8b7-c90c-4564-b5b8-033449090932"


#### <a name="sample-request"></a>Solicitud de muestra

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932",
    "IsFolder": true 
}
```

#### <a name="sample-response"></a>Respuesta de muestra

**Código de estado:** 201

```JSON
{
    "ErrorMessage":  null,
    "StatusCode":  201
}
```

## <a name="see-also"></a>Ver también

[API de REST del modelo de comprensión mediante documentos de Syntex](syntex-model-rest-api.md)
