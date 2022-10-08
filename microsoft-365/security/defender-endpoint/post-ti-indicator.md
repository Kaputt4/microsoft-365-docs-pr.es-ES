---
title: API de enviar o actualizar indicador
description: Obtenga información sobre cómo usar la API Submit or Update Indicator para enviar o actualizar una nueva entidad Indicator en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, submit, ti, indicator, update
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 1afe71e8a25b0c623be2039c471c75d707c5c50a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226545"
---
# <a name="submit-or-update-indicator-api"></a>API de enviar o actualizar indicador

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Envía o Novedades nueva entidad [Indicator](ti-indicator.md).

No se admite la notación CIDR para direcciones IP.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.
2. Hay un límite de 15 000 indicadores activos por inquilino.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Introducción](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Ti.ReadWrite|"Indicadores de lectura y escritura"
Application|Ti.ReadWrite.All|"Leer y escribir todos los indicadores"
Delegado (cuenta profesional o educativa)|Ti.ReadWrite|"Indicadores de lectura y escritura"

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|string|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los parámetros siguientes:

Parámetro|Tipo|Descripción
:---|:---|:---
indicatorValue|Cadena|Identidad de la entidad [Indicator](ti-indicator.md) . **Required**
indicatorType|Enum|Tipo del indicador. Los valores posibles son: "FileSha1", "FileMd5", "CertificateThumbprint", "FileSha256", "IpAddress", "DomainName" y "Url". **Required**
acción|Enum|Acción que se realizará si el indicador se detectará en la organización. Los valores posibles son: "Alert", "Warn", "Block", "Audit, "BlockAndRemediate", "AlertAndBlock" y "Allowed". **Necesario**. El parámetro "GenerateAlert" debe establecerse en "TRUE" al crear una acción con "Auditar".
aplicación|Cadena|Aplicación asociada al indicador. Este campo solo funciona para nuevos indicadores. No actualizará el valor en un indicador existente. **Optional**
title|Cadena|Título de alerta de indicador. **Required**
description|Cadena|Descripción del indicador. **Required**
expirationTime|DateTimeOffset|Tiempo de expiración del indicador. **Optional**
severity|Enum|Gravedad del indicador. Los valores posibles son: "Informativo", "Bajo", "Medio" y "Alto". **Optional**
recommendedActions|Cadena|Acciones recomendadas de alerta de indicador de TI. **Optional**
rbacGroupNames|Cadena|Lista separada por comas de nombres de grupo de RBAC a los que se aplicaría el indicador. **Optional**
educateUrl|Cadena|Dirección URL de soporte técnico o notificación personalizada. Compatible con los tipos de acción Bloquear y Advertir para los indicadores de dirección URL. **Optional**
generateAlert|Enum|**True** si se requiere la generación de alertas, **False** si este indicador no debe generar una alerta.
## <a name="response"></a>Respuesta

- Si se ejecuta correctamente, este método devuelve el código de respuesta 200 - OK y la entidad [Indicator](ti-indicator.md) creada o actualizada en el cuerpo de la respuesta.
- Si no se ejecuta correctamente: este método devuelve 400 - Solicitud incorrecta. La solicitud incorrecta suele indicar un cuerpo incorrecto.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>Tema relacionado

- [Administrar indicadores](manage-indicators.md)
