---
title: Errores comunes de La API de Microsoft Defender para puntos de conexión
description: Lista de errores comunes de La API de Microsoft Defender para puntos de conexión con descripciones.
keywords: API, API de Microsoft Defender para endpoints, errores, solución de problemas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771014"
---
# <a name="common-rest-api-error-codes"></a>Códigos de error comunes de API de REST

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* Los códigos de error enumerados en la tabla siguiente pueden devolverse mediante una operación en cualquiera de las API de Microsoft Defender para puntos de conexión.
* Además del código de error, cada respuesta de error contiene un mensaje de error, que puede ayudar a resolver el problema.
* El mensaje es un texto gratuito que se puede cambiar.
* En la parte inferior de la página, puede encontrar ejemplos de respuesta.

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Código de error |Código de estado HTTP |Mensaje 
:---|:---|:---
BadRequest | BadRequest (400) | Mensaje de error General Bad Request.
ODataError | BadRequest (400) | Consulta URI de OData no válida (se especifica el error específico).
InvalidInput | BadRequest (400) | Entrada no válida {la entrada no válida}.
InvalidRequestBody | BadRequest (400) | Cuerpo de la solicitud no válido.
InvalidHashValue | BadRequest (400) | El valor hash {el hash no válido} no es válido.
InvalidDomainName | BadRequest (400) | El nombre de dominio {el dominio no válido} no es válido.
InvalidIpAddress | BadRequest (400) | La dirección IP {la IP no válida} no es válida.
InvalidUrl | BadRequest (400) | La dirección URL {la dirección URL no válida} no es válida.
MaximumBatchSizeExceeded | BadRequest (400) | Se ha superado el tamaño máximo de lote. Received: {batch size received}, allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Falta el parámetro {el parámetro que falta}.
OsPlatformNotSupported | BadRequest (400) | La plataforma del sistema operativo {la plataforma del sistema operativo cliente} no es compatible con esta acción.
ClientVersionNotSupported | BadRequest (400) | {La acción solicitada} se admite en la versión de cliente {versión de cliente admitida} y versiones posteriores.
No autorizado (Unauthorized) | No autorizado (401) | No autorizado (encabezado de autorización no válido o expirado).
Prohibido (Forbidden) | Prohibido (403) | Prohibido (token válido pero permiso insuficiente para la acción).
DisabledFeature | Prohibido (403) | La característica inquilino no está habilitada.
DisallowedOperation | Prohibido (403) | {la operación no permitido y el motivo}.
NotFound | No encontrado (404) | Mensaje de error General No encontrado.
ResourceNotFound | No encontrado (404) | No se encontró el recurso {el recurso solicitado}.
InternalServerError | Error interno del servidor (500) | (Sin mensaje de error, vuelva a intentar la operación)
TooManyRequests | Demasiadas solicitudes (429) | La respuesta representará alcanzar el límite de cuota por número de solicitudes o por CPU.

## <a name="body-parameters-are-case-sensitive"></a>Los parámetros de cuerpo distinguen mayúsculas de minúsculas

Los parámetros de cuerpo enviados distinguen entre mayúsculas y minúsculas.
<br>Si experimenta errores **InvalidRequestBody** o **MissingRequiredParameter,** es posible que se deba a un capital de parámetro incorrecto o a una letra minúscula.
<br>Revise la página de documentación de la API y compruebe que los parámetros enviados coinciden con el ejemplo correspondiente.

## <a name="correlation-request-id"></a>Identificador de solicitud de correlación

Cada respuesta de error contiene un parámetro id. único para el seguimiento.
<br>El nombre de la propiedad de este parámetro es "target".
<br>Al ponerse en contacto con nosotros sobre un error, adjuntar este identificador ayudará a encontrar la causa raíz del problema.

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
