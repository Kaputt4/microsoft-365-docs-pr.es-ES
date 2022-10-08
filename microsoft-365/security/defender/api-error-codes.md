---
title: Códigos de error de la API REST de Microsoft 365 Defender comunes
description: Más información sobre los códigos de error comunes de la API REST de Microsoft 365 Defender
keywords: api, error, códigos, errores comunes, Microsoft 365 Defender, códigos de error de api
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: 0fc6ca121b287887ec1e6ef82a13df1ca85acc35
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066924"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Códigos de error de la API REST de Microsoft 365 Defender comunes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Una operación puede devolver códigos de error en cualquiera de las API de Microsoft 365 Defender. Cada respuesta de error contendrá un mensaje de error, que puede ayudar a resolver el problema. La columna de mensaje de error de la sección de tabla proporciona algunos mensajes de ejemplo. El contenido de los mensajes reales variará en función de los factores que desencadenaron la respuesta. El contenido de la variable se indica en la tabla entre corchetes angulares.

## <a name="error-codes"></a>Códigos de error

Código de error | Código de estado HTTP | Message
-|-|-
BadRequest | BadRequest (400) | Mensaje de error de solicitud incorrecta general.
ODataError | BadRequest (400) | Consulta URI \<the specific error is specified\>de OData no válida.
InvalidInput | BadRequest (400) | Entrada \<the invalid input\>no válida.
InvalidRequestBody | BadRequest (400) | Cuerpo de la solicitud no válido.
InvalidHashValue | BadRequest (400) | El valor \<the invalid hash\> hash no es válido.
InvalidDomainName | BadRequest (400) | El nombre \<the invalid domain\> de dominio no es válido.
InvalidIpAddress | BadRequest (400) | La dirección \<the invalid IP\> IP no es válida.
InvalidUrl | BadRequest (400) | La dirección URL \<the invalid URL\> no es válida.
MaximumBatchSizeExceeded | BadRequest (400) | Se ha superado el tamaño máximo del lote. Recibido: \<batch size received\>, permitido: {tamaño de lote permitido}.
MissingRequiredParameter | BadRequest (400) | Falta el parámetro \<the missing parameter\> .
OsPlatformNotSupported | BadRequest (400) | La plataforma \<the client OS Platform\> del sistema operativo no se admite para esta acción.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> se admite en la versión \<supported client version\> de cliente y versiones posteriores.
No autorizado (Unauthorized) | No autorizado (401) | No autorizado (Unauthorized) <br /><br />*Nota: Normalmente, se debe a un encabezado de autorización no válido o expirado.*
Prohibido (Forbidden) | Prohibido (403) | Prohibido (Forbidden) <br /><br />*Nota: Token válido pero permiso insuficiente para la acción*.
DisabledFeature | Prohibido (403) | La característica de inquilino no está habilitada.
No permitidaOperation | Prohibido (403) | \<the disallowed operation and the reason\>.
NotFound | No encontrado (404) | Mensaje de error General no encontrado.
ResourceNotFound | No encontrado (404) | No se encontró el recurso \<the requested resource\> .
InternalServerError | Error interno del servidor (500) | *Nota: No hay ningún mensaje de error, reintente la operación o [póngase en contacto con Microsoft](../../admin/get-help-support.md) si no se resuelve*

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
> Los parámetros del cuerpo distinguen mayúsculas de minúsculas.

Si experimenta un error *InvalidRequestBody* o *MissingRequiredParameter* , puede deberse a un error tipográfico. Revise la documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo pertinente.

## <a name="tracking-id"></a>Identificador de seguimiento

Cada respuesta de error contiene un parámetro de identificador único para el seguimiento. El nombre de propiedad de este parámetro es *target*. Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador nos ayudará a encontrar la causa principal del problema.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Las API de Microsoft 365 Defender compatibles](api-supported.md)
- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [Más información sobre los límites de API y las licencias](api-terms.md)
