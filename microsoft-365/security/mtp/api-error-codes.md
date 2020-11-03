---
title: Códigos de error comunes de la API de REST de Microsoft 365 defender
description: Obtener información sobre los códigos de error comunes de la API de REST de Microsoft 365 defender
keywords: API, error, códigos, errores comunes, MTP, códigos de error de la API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846013"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Códigos de error comunes de la API de REST de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Los códigos de error que se enumeran en la siguiente tabla pueden devolverse mediante una operación en cualquiera de las API de Microsoft 365 defender.

Cada respuesta de error contiene un mensaje de error, que puede ayudar a resolver el problema.

El mensaje es un texto libre que se puede cambiar.

En la parte inferior de la página, puede encontrar ejemplos de respuesta.

Código de error |Código de estado HTTP |Message 
:---|:---|:---
BadRequest | BadRequest (400) | Mensaje de error de solicitud incorrecta general.
ODataError | BadRequest (400) | Consulta URI de OData no válida (se ha especificado el error específico).
InvalidInput | BadRequest (400) | Entrada no válida {entrada no válida}.
InvalidRequestBody | BadRequest (400) | Cuerpo de la solicitud no válido.
InvalidHashValue | BadRequest (400) | El valor hash {el hash no válido} no es válido.
InvalidDomainName | BadRequest (400) | Nombre de dominio {el dominio no válido} no es válido.
InvalidIpAddress | BadRequest (400) | La dirección IP {IP no válida} no es válida.
InvalidUrl | BadRequest (400) | La dirección URL {URL no válida} no es válida.
MaximumBatchSizeExceeded | BadRequest (400) | Tamaño máximo de lote superado. Recibido: {tamaño de lote recibido}, permitido: {tamaño de lote permitido}.
MissingRequiredParameter | BadRequest (400) | No se encuentra el parámetro {falta el parámetro}.
OsPlatformNotSupported | BadRequest (400) | Plataforma de so {la plataforma de sistema operativo cliente} no es compatible con esta acción.
ClientVersionNotSupported | BadRequest (400) | {La acción solicitada} es compatible con la versión de cliente {versión de cliente admitida} y versiones posteriores.
No autorizado (Unauthorized) | No autorizado (401) | Encabezado de autorización no autorizado (normalmente no válido o expirado).
Prohibido (Forbidden) | Prohibido (403) | Prohibido (token válido, pero permiso insuficiente para la acción).
DisabledFeature | Prohibido (403) | La característica de inquilino no está habilitada.
DisallowedOperation | Prohibido (403) | {la operación no permitida y el motivo}.
NotFound | No encontrado (404) | Mensaje de error general no encontrado.
ResourceNotFound | No encontrado (404) | Recurso {no se encontró el recurso solicitado}.
InternalServerError | Error interno del servidor (500) | (No hay ningún mensaje de error, reintente la operación o póngase en contacto con nosotros si no se resuelve)

## <a name="body-parameters-are-case-sensitive"></a>Los parámetros Body distinguen entre mayúsculas y minúsculas

Los parámetros del cuerpo enviados actualmente distinguen mayúsculas de minúsculas.
<br>Si experimenta errores de **InvalidRequestBody** o **MissingRequiredParameter** , puede deberse a una letra de mayúscula o minúscula del parámetro incorrecto.
<br>Le recomendamos que revise la página de documentación de la API y que compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.

## <a name="correlation-request-id"></a>IDENTIFICADOR de solicitud de correlación

Cada respuesta de error contiene un parámetro ID único para el seguimiento.
<br>El nombre de la propiedad de este parámetro es "target".
<br>Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador le ayudará a encontrar la causa raíz del problema.

## <a name="examples"></a>Ejemplos

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```


```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

