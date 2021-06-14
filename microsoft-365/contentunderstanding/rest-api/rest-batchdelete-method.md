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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904276"
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
|ModelUniqueId|sí|cadena|El Id. único del archivo de modelo.|
TargetSiteUrl|sí|cadena|La dirección URL completa del sitio de biblioteca de destino.|
TargetWebServerRelativeUrl|sí|cadena|La dirección URL relativa del servidor de la Web de la biblioteca de destino.|
TargetLibraryServerRelativeUrl|sí|cadena|La dirección URL relativa al servidor de la biblioteca de destino.|
ViewOption|no|string|Especifica si se debe establecer la nueva vista de modelo como el valor predeterminado de la biblioteca.|

## <a name="response"></a>Respuesta

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|200 Correcto| |Correcto|


## <a name="examples"></a>Ejemplos

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Quitar un modelo de la biblioteca de documentos de contratos en el sitio del repositorio

En este ejemplo, el Id. del modelo de comprensión mediante documentos del contrato de Contoso es `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

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
