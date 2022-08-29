---
title: Errores comunes Microsoft Defender para punto de conexión API
description: Lista de errores comunes de api de Microsoft Defender para punto de conexión con descripciones.
keywords: API, API de Microsoft Defender para punto de conexión, errores, solución de problemas
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: dbbfd44f573e216015bfe586d5c309cc3ba12f5e
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326153"
---
# <a name="common-rest-api-error-codes"></a>Códigos de error comunes de API de REST



[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* Los códigos de error enumerados en la tabla siguiente pueden devolverse mediante una operación en cualquiera de Microsoft Defender para punto de conexión API.
* Además del código de error, cada respuesta de error contiene un mensaje de error, que puede ayudar a resolver el problema.
* El mensaje es un texto libre que se puede cambiar.
* En la parte inferior de la página, puede encontrar ejemplos de respuesta.

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Código de error|Código de estado HTTP|Message
---|---|---
BadRequest|BadRequest (400)|Mensaje de error de solicitud incorrecta general.
ODataError|BadRequest (400)|Consulta URI de OData no válida (se especifica el error específico).
InvalidInput|BadRequest (400)|Entrada no válida {la entrada no válida}.
InvalidRequestBody|BadRequest (400)|Cuerpo de la solicitud no válido.
InvalidHashValue|BadRequest (400)|El valor hash {el hash no válido} no es válido.
InvalidDomainName|BadRequest (400)|El nombre de dominio {el dominio no válido} no es válido.
InvalidIpAddress|BadRequest (400)|La dirección IP {la dirección IP no válida} no es válida.
InvalidUrl|BadRequest (400)|La dirección URL {la dirección URL no válida} no es válida.
MaximumBatchSizeExceeded|BadRequest (400)|Se ha superado el tamaño máximo del lote. Recibido: {tamaño de lote recibido}, permitido: {tamaño de lote permitido}.
MissingRequiredParameter|BadRequest (400)|Falta el parámetro {el parámetro que falta}.
OsPlatformNotSupported|BadRequest (400)|La plataforma del sistema operativo {la plataforma del sistema operativo cliente} no se admite para esta acción.
ClientVersionNotSupported|BadRequest (400)|{La acción solicitada} se admite en la versión de cliente {versión de cliente compatible} y versiones posteriores.
No autorizado (Unauthorized)|No autorizado (401)|No autorizado (encabezado de autorización no válido o expirado).
Prohibido (Forbidden)|Prohibido (403)|Prohibido (token válido pero permiso insuficiente para la acción).
DisabledFeature|Prohibido (403)|La característica de inquilino no está habilitada.
No permitidaOperation|Prohibido (403)|{la operación no permitida y el motivo}.
NotFound|No encontrado (404)|Mensaje de error General no encontrado.
ResourceNotFound|No encontrado (404)|No se encontró el recurso {el recurso solicitado}.
InternalServerError|Error interno del servidor (500)|(Sin mensaje de error, vuelva a intentar la operación)
TooManyRequests|Demasiadas solicitudes (429)|La respuesta representará alcanzar el límite de cuota por número de solicitudes o por CPU.

## <a name="body-parameters-are-case-sensitive"></a>Los parámetros del cuerpo distinguen mayúsculas de minúsculas

Los parámetros del cuerpo enviados distinguen entre mayúsculas y minúsculas actualmente.

Si experimenta errores **InvalidRequestBody** o **MissingRequiredParameter** , puede deberse a un mayúscula de parámetro incorrecto o a una letra minúscula.

Revise la página de documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo pertinente.

## <a name="correlation-request-id"></a>Identificador de solicitud de correlación

Cada respuesta de error contiene un parámetro de identificador único para el seguimiento.

El nombre de propiedad de este parámetro es "target".

Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador le ayudará a encontrar la causa principal del problema.

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
