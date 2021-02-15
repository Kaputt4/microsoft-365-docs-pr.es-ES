---
title: Códigos de error comunes de la API de REST de Microsoft 365 Defender
description: Obtenga información sobre los códigos de error comunes de la API de REST de Microsoft 365 Defender
keywords: api, error, códigos, errores comunes, mtp, códigos de error de api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928395"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Códigos de error comunes de la API de REST de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Protección contra amenazas de Microsoft

> [!IMPORTANT]
> Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Los códigos de error pueden devolverse mediante una operación en cualquiera de las API de Microsoft 365 Defender. Cada respuesta de error contendrá un mensaje de error, que puede ayudar a resolver el problema. La columna de mensaje de error de la sección de tabla proporciona algunos mensajes de ejemplo. El contenido de los mensajes reales variará en función de los factores que desencadenaron la respuesta. El contenido variable se indica en la tabla mediante corchetes angulares.

## <a name="error-codes"></a>Códigos de error

Código de error | Código de estado HTTP | Mensaje
-|-|-
BadRequest | BadRequest (400) | Mensaje de error General Bad Request.
ODataError | BadRequest (400) | Consulta URI de OData no \<the specific error is specified\> válida.
InvalidInput | BadRequest (400) | Entrada no \<the invalid input\> válida.
InvalidRequestBody | BadRequest (400) | Cuerpo de la solicitud no válido.
InvalidHashValue | BadRequest (400) | El valor hash \<the invalid hash\> no es válido.
InvalidDomainName | BadRequest (400) | El nombre de \<the invalid domain\> dominio no es válido.
InvalidIpAddress | BadRequest (400) | La dirección IP \<the invalid IP\> no es válida.
InvalidUrl | BadRequest (400) | La dirección URL \<the invalid URL\> no es válida.
MaximumBatchSizeExceeded | BadRequest (400) | Se ha excedido el tamaño máximo del lote. Recibido: \<batch size received\> , permitido: {tamaño de lote permitido}.
MissingRequiredParameter | BadRequest (400) | Falta \<the missing parameter\> el parámetro.
OsPlatformNotSupported | BadRequest (400) | La plataforma del \<the client OS Platform\> sistema operativo no es compatible con esta acción.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> se admite en la versión de cliente \<supported client version\> y versiones posteriores.
No autorizado (Unauthorized) | No autorizado (401) | No autorizado (Unauthorized) <br /><br />*Nota: Normalmente se debe a un encabezado de autorización no válido o expirado.*
Prohibido (Forbidden) | Prohibido (403) | Prohibido (Forbidden) <br /><br />*Nota: Token válido pero permisos insuficientes para la acción.*
DisabledFeature | Prohibido (403) | La característica inquilino no está habilitada.
DisallowedOperation | Prohibido (403) | \<the disallowed operation and the reason\>.
NotFound | No encontrado (404) | Mensaje de error general no encontrado.
ResourceNotFound | No encontrado (404) | No \<the requested resource\> se encontró el recurso.
InternalServerError | Error interno del servidor (500) | *Nota: no hay ningún mensaje de error, reintente la operación o póngase en contacto con Microsoft si no se resuelve*

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

## <a name="body-parameters"></a>Parámetros de cuerpo

> [!IMPORTANT]
> Los parámetros de cuerpo distinguen mayúsculas de minúsculas.

Si experimenta un error *InvalidRequestBody* o *MissingRequiredParameter,* puede deberse a un error tipográfico. Revise la documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo relevante.

## <a name="tracking-id"></a>Id. de seguimiento

Cada respuesta de error contiene un parámetro de identificador único para el seguimiento. El nombre de la propiedad de este parámetro es *target*. Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador nos ayudará a encontrar la causa raíz del problema.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [API de Microsoft 365 Defender (versión preliminar) admitidas](api-supported.md)
- [Obtener acceso a las API de Microsoft 365 Defender](api-access.md)
- [Más información sobre los límites de la API y las licencias](api-terms.md)
