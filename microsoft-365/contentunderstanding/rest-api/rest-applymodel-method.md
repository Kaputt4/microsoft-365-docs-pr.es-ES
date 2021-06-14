---
title: Aplicar modelo
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904356"
---
# <a name="apply-model"></a>Aplicar modelo

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
|ModelUniqueId|sí|string|El id. único del archivo de modelo.|
TargetSiteUrl|sí|string|La dirección URL completa del sitio de biblioteca de destino.|
TargetWebServerRelativeUrl|sí|string|La dirección URL relativa del servidor de la Web de la biblioteca de destino.|
TargetLibraryServerRelativeUrl|sí|string|La dirección URL relativa al servidor de la biblioteca de destino.|
ViewOption|no|string|Especifica si se debe establecer la nueva vista de modelo como el valor predeterminado de la biblioteca.|

## <a name="response"></a>Respuesta

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|200 Correcto| |Correcto|
|201 Created| |Tenga en cuenta que, dado que esta API puede aplicar el modelo a varias bibliotecas, se podría devolver un código 201 aunque haya un error al aplicar el modelo a una de las bibliotecas. <br>Compruebe el cuerpo de la respuesta para entender si el modelo se ha aplicado correctamente a todas las bibliotecas especificadas. Vea [Cuerpo de la solicitud](rest-applymodel-method.md#request-body) para obtener más información.|

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
