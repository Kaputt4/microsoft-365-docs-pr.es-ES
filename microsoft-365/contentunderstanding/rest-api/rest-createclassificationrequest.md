---
title: Crear solicitud de clasificación de archivos
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
description: Use la API de REST para crear una solicitud para clasificar uno o más archivos con un modelo entrenado de comprensión mediante documentos.
ms.openlocfilehash: 50aa406d25e6d598b568d7c21db6f56e04e111da
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2021
ms.locfileid: "59776733"
---
# <a name="create-file-classification-request"></a>Crear solicitud de clasificación de archivos

Crea una solicitud para clasificar uno o más archivos con el modelo de comprensión mediante documentos aplicado (para obtener más información, consulte el [ejemplo](rest-createclassificationrequest.md#examples)).

El servicio REST de SharePoint Online (y SharePoint 2016 y versiones posteriores locales) admite la combinación de varias solicitudes. Las solicitudes se combinan en una sola llamada al servicio mediante el uso de la opción de consulta $batch de OData Este método se puede usar para poner en cola los elementos de trabajo de clasificación para cientos de documentos a la vez.

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
|TargetSiteId|guid|Id. del sitio donde se encuentra el archivo que se clasificará. Esto se puede omitir cuando TargetSiteUrl tenga un valor. |
|TargetSiteUrl|string|La dirección URL del sitio donde se encuentra el archivo que se clasificará. Esto se puede omitir cuando TargeSiteId tenga un valor.|
|TargetWebId|guid|Id. de la web en la que se encuentra el archivo que se clasificará. Esto se puede omitir cuando TargetWebServerRelativeUrl tenga un valor. |
|TargetWebServerRelativeUrl|string|Dirección URL relativa del servidor de la web donde se encuentra el archivo que se va a clasificar. Esto se puede omitir cuando TargetWebId tenga un valor.  |
|TargetUniqueId|guid|Id. de la carpeta que se va a clasificar. Esto se puede omitir cuando TargetServerRelativeUrl tenga un valor. |
|TargetServerRelativeUrl|cadena|Dirección URL relativa donde se encuentra el archivo que se va a clasificar. Esto se puede omitir cuando TargetUniqueId tenga un valor.|

## <a name="responses"></a>Respuestas

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|201 Created| |La respuesta es personalizada. En caso de error, podría devolver 201 Created. El autor de la llamada debe comprobar adicionalmente el cuerpo de la respuesta para determinar el resultado exacto.|

## <a name="examples"></a>Ejemplos

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Poner en cola una solicitud para clasificar un archivo de id. "e6cff8b7-c90c-4564-b5b8-033449090932"

#### <a name="sample-request"></a>Solicitud de muestra

```JSON
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
```JSON
{
    "ErrorMessage":  null,
    "StatusCode":  201
}
```

```JSON
{
    "ErrorMessage":  null,
    "StatusCode":  201
}
```

## <a name="see-also"></a>Ver también

[API de REST del modelo de comprensión mediante documentos de Syntex](syntex-model-rest-api.md)
