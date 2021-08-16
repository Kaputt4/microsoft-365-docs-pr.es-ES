---
title: Crear modelo
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
description: Use la API de REST para crear un modelo y su tipo de contenido asociado.
ms.openlocfilehash: ac5a48f92352c2c286323b8a679a975e0dbdca80703f9f727d16a4999b4a2f65
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53899816"
---
# <a name="create-model"></a>Crear modelo

Crea un modelo y su tipo de contenido asociado. Tenga en cuenta que esto solo crea el modelo. Aún tendrá que ser entrenado en el centro de contenido (vea [ejemplo](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>Solicitud HTTP

```http
POST /_api/machinelearning/models HTTP/1.1
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
|_metadata|  |Establezca la meta del objeto en SPO. Use siempre el valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|cadena|El grupo de tipo de contenido asociado al modelo. El valor predeterminado es "Tipos de contenido de documento inteligente".|
|ContentTypeName|cadena|El nombre del tipo de contenido asociado. El archivo de modelo creado tendrá el mismo nombre.|

## <a name="responses"></a>Respuestas

| Nombre   | Tipo  | Descripción|
|--------|-------|------------|
|201 Created| |Correcto|

## <a name="examples"></a>Ejemplos

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Crear un nuevo modelo de comprensión mediante documentos denominado "Contrato de Contoso"

#### <a name="sample-request"></a>Solicitud de muestra

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a>Respuesta de muestra

**Código de estado:** 201

## <a name="see-also"></a>Ver también

[API de REST del modelo de comprensión mediante documentos de Syntex](syntex-model-rest-api.md)
