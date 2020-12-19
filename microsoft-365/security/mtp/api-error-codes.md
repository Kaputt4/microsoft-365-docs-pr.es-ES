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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719219"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Códigos de error comunes de la API de REST de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Protección contra amenazas de Microsoft

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Los códigos de error pueden devolverse mediante una operación en cualquiera de las API de Microsoft 365 defender. Cada respuesta de error contendrá un mensaje de error, que puede ayudar a resolver el problema. La columna mensaje de error de la sección tabla proporciona algunos ejemplos de mensajes. El contenido de los mensajes reales variará en función de los factores que desencadenaron la respuesta. El contenido de la variable se indica en la tabla por corchetes angulares.

## <a name="error-codes"></a>Códigos de error

Código de error | Código de estado HTTP | Mensaje
-|-|-
BadRequest | BadRequest (400) | Mensaje de error de solicitud incorrecta general.
ODataError | BadRequest (400) | Consulta URI de OData no válida \<the specific error is specified\> .
InvalidInput | BadRequest (400) | Entrada no válida \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Cuerpo de la solicitud no válido.
InvalidHashValue | BadRequest (400) | El valor hash \<the invalid hash\> no es válido.
InvalidDomainName | BadRequest (400) | El nombre de dominio \<the invalid domain\> no es válido.
InvalidIpAddress | BadRequest (400) | La dirección IP \<the invalid IP\> no es válida.
InvalidUrl | BadRequest (400) | La dirección URL \<the invalid URL\> no es válida.
MaximumBatchSizeExceeded | BadRequest (400) | Tamaño máximo de lote superado. Recibido: \<batch size received\> , permitido: {tamaño de lote permitido}.
MissingRequiredParameter | BadRequest (400) | Falta el parámetro \<the missing parameter\> .
OsPlatformNotSupported | BadRequest (400) | La plataforma del sistema operativo \<the client OS Platform\> no es compatible con esta acción.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> es compatible con la versión de cliente \<supported client version\> y versiones posteriores.
No autorizado (Unauthorized) | No autorizado (401) | No autorizado (Unauthorized) <br /><br />*Nota: normalmente causada por un encabezado de autorización no válido o expirado.*
Prohibido (Forbidden) | Prohibido (403) | Prohibido (Forbidden) <br /><br />*Nota: token válido, pero permiso insuficiente para la acción*.
DisabledFeature | Prohibido (403) | La característica de inquilino no está habilitada.
DisallowedOperation | Prohibido (403) | \<the disallowed operation and the reason\>.
NotFound | No encontrado (404) | Mensaje de error general no encontrado.
ResourceNotFound | No encontrado (404) | \<the requested resource\>No se encontró el recurso.
InternalServerError | Error interno del servidor (500) | *Nota: no hay ningún mensaje de error, vuelva a intentar la operación o póngase en contacto con Microsoft si no se resuelve*

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
> Los parámetros Body distinguen mayúsculas de minúsculas.

Si experimenta un error *InvalidRequestBody* o *MissingRequiredParameter* , puede deberse a un error tipográfico. Revise la documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.

## <a name="tracking-id"></a>IDENTIFICADOR de seguimiento

Cada respuesta de error contiene un parámetro ID único para el seguimiento. El nombre de la propiedad de este parámetro es *target*. Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador nos ayudará a encontrar la causa raíz del problema.

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las API de Microsoft 365 defender](api-overview.md)
- [API de Microsoft 365 Defender (versión preliminar) admitidas](api-supported.md)
- [Acceso a las API de Microsoft 365 defender](api-access.md)
- [Obtenga información sobre los límites de API y las licencias](api-terms.md)
