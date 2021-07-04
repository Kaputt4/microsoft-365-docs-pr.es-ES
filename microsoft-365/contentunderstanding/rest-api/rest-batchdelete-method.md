---
title: BatchDelete
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
description: Use la API de REST para quitar un modelo de comprensión mediante documentos de una o más bibliotecas.
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287458"
---
# <a name="batchdelete"></a>BatchDelete

Quita un modelo de comprensión mediante documentos de una o más bibliotecas. Tenga en cuenta que un modelo debe quitarse de todas las bibliotecas antes de que se pueda eliminar (vea [ejemplo](rest-batchdelete-method.md#examples)).

## <a name="http-request"></a>Solicitud HTTP

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>Parámetros de URI

Ninguno

## <a name="request-headers"></a>Encabezados de solicitud

| Encabezado | Valor |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|El resumen adecuado del sitio actual.|

## <a name="request-body"></a>Cuerpo de la solicitud

| Nombre | Obligatorio | Tipo | Descripción |
|--------|-------|--------|------------|
|Publicaciones|sí|MachineLearningPublicationEntityData[]|Colección de MachineLearningPublicationEntityData, cada una de las cuales especifica el modelo y la biblioteca de documentos de destino.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Nombre | Obligatorio | Tipo | Descripción |
|--------|-------|--------|------------|
|ModelUniqueId|sí|cadena|El Id. único del archivo de modelo.|
|TargetSiteUrl|sí|cadena|La dirección URL completa del sitio de biblioteca de destino.|
|TargetWebServerRelativeUrl|sí|cadena|La dirección URL relativa del servidor de la Web de la biblioteca de destino.|
|TargetLibraryServerRelativeUrl|sí|cadena|La dirección URL relativa al servidor de la biblioteca de destino.|

## <a name="response"></a>Respuesta

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|200 Correcto||Se trata de una API personalizada para admitir la eliminación de un modelo de bibliotecas de varios documentos. En caso de éxito parcial, se podría devolver 200 OK y el autor de la llamada debe inspeccionar el cuerpo de la respuesta para comprender si el modelo se ha quitado correctamente de una biblioteca de documentos.|

## <a name="response-body"></a>Cuerpo de la respuesta

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|TotalSuccesses|int|El número total de un modelo que se elimina correctamente de una biblioteca de documentos.|
|TotalFailures|int|Número total de un modelo que no se puede quitar de una biblioteca de documentos.|
|Detalles|MachineLearningPublicationResult[]|Colección de MachineLearningPublicationResult, cada una de las cuales especifica el resultado detallado de quitar el modelo de la biblioteca de documentos.|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|StatusCode|int|El código de estado HTTP.|
|ErrorMessage|string|Mensaje de error que indica el problema al aplicar el modelo a la biblioteca de documentos.|
|Publicación|MachineLearningPublicationEntityData|Especifica la información del modelo y la biblioteca de documentos de destino.| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Nombre | Tipo | Descripción |
|--------|--------|------------|
|ModelUniqueId|string|El Id. único del archivo de modelo.|
|TargetSiteUrl|string|La dirección URL completa del sitio de biblioteca de destino.|
|TargetWebServerRelativeUrl|string|La dirección URL relativa del servidor de la Web de la biblioteca de destino.|
|TargetLibraryServerRelativeUrl|string|La dirección URL relativa al servidor de la biblioteca de destino.|

## <a name="examples"></a>Ejemplos

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Quitar un modelo de la biblioteca de documentos de contratos en el sitio del repositorio

En este ejemplo, el Id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Solicitud de muestra

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```

#### <a name="sample-response"></a>Respuesta de muestra

En la respuesta, TotalFailures y TotalSuccesses hacen referencia al número de errores y éxitos del modelo que se quita de las bibliotecas especificadas.

**Código de estado:** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Consulte también

[API de REST del modelo de comprensión mediante documentos de Syntex](syntex-model-rest-api.md)
