---
title: Aplicar modelo en lote
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
description: Use la API de REST para aplicar un modelo de comprensión mediante documentos a una o más bibliotecas.
ms.openlocfilehash: 24ea9a480bc3ce5a7745857de17a6fab6ed97685
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177266"
---
# <a name="batch-apply-model"></a>Aplicar modelo en lote

Aplica (o sincroniza) un modelo de comprensión mediante documentos entrenado a una o más bibliotecas (vea el [ejemplo](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>Solicitud HTTP

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
|__metadata|sí|cadena|Establezca la meta del objeto en SPO. Use siempre el valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.|
|Publicaciones|sí|MachineLearningPublicationEntityData[]|Colección de MachineLearningPublicationEntityData, cada una de las cuales especifica el modelo y la biblioteca de documentos de destino.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Nombre | Obligatorio | Tipo | Descripción |
|--------|-------|--------|------------|
|ModelUniqueId|sí|string|El Id. único del archivo de modelo.|
|TargetSiteUrl|sí|string|La dirección URL completa del sitio de biblioteca de destino.|
|TargetWebServerRelativeUrl|sí|string|La dirección URL relativa del servidor de la Web de la biblioteca de destino.|
|TargetLibraryServerRelativeUrl|sí|string|La dirección URL relativa al servidor de la biblioteca de destino.|
|ViewOption|no|string|Especifica si se debe establecer la nueva vista de modelo como el valor predeterminado de la biblioteca.|

## <a name="response"></a>Respuesta

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|201 Created||Se trata de una API personalizada para admitir la aplicación de un modelo a varias bibliotecas de documentos. En caso de éxito parcial, se podría devolver el 201 creado y el llamador debe inspeccionar el cuerpo de la respuesta para comprender si el modelo se ha aplicado correctamente a una biblioteca de documentos.|

## <a name="response-body"></a>Cuerpo de la respuesta
| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|TotalSuccesses|int|El número total de un modelo que se aplica correctamente a una biblioteca de documentos.|
|TotalFailures|int|Número total de un modelo que no se puede aplicar a una biblioteca de documentos.|
|Detalles|MachineLearningPublicationResult[]|Colección de MachineLearningPublicationResult, cada una de las cuales especifica el resultado detallado de aplicar el modelo a la biblioteca de documentos.|

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

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>Aplicar un modelo a la biblioteca de documentos de contratos en el sitio de repositorio

En este ejemplo, el id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Solicitud de muestra

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>Respuesta de muestra

En la respuesta, TotalFailures y TotalSuccesses hacen referencia al número de errores y éxitos del modelo que se aplica a las bibliotecas especificadas.

**Código de estado:** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Ver también

[API de REST del modelo de comprensión mediante documentos de Syntex](syntex-model-rest-api.md)
