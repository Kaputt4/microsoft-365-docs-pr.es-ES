---
title: Enviar o actualizar API de indicadores
description: Obtenga información sobre cómo usar la API Enviar o Actualizar indicador para enviar o actualizar una nueva entidad Indicator en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, submit, ti, indicator, update
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
ms.openlocfilehash: 42d6ed79868b9f32f8ea3cfe77bb78f1a86a8bea
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656696"
---
# <a name="submit-or-update-indicator-api"></a>Enviar o actualizar API de indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Envía o actualiza la nueva [entidad Indicator.](ti-indicator.md)

No se admite la notación CIDR para IP.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.
2. Hay un límite de 15.000 indicadores activos por inquilino.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Ti.ReadWrite|Indicadores de lectura y escritura
Aplicación|Ti.ReadWrite.All|'Leer y escribir todos los indicadores'
Delegado (cuenta profesional o educativa)|Ti.ReadWrite|Indicadores de lectura y escritura

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|cadena|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro|Tipo|Descripción
:---|:---|:---
indicatorValue|Cadena|Identidad de la [entidad Indicator.](ti-indicator.md) **Required**
indicatorType|Enum|Tipo del indicador. Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url". **Required**
acción|Enum|La acción que se realizará si el indicador se detectará en la organización. Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed". **Required**
aplicación|Cadena|La aplicación asociada al indicador. **Optional**
title|Cadena|Título de alerta del indicador. **Required**
description|Cadena|Descripción del indicador. **Required**
expirationTime|DateTimeOffset|La hora de expiración del indicador. **Optional**
severity|Enum|Gravedad del indicador. los valores posibles son: "Informational", "Low", "Medium" y "High". **Optional**
recommendedActions|Cadena|Acciones recomendadas de alerta del indicador TI. **Optional**
rbacGroupNames|Cadena|Lista separada por comas de nombres de grupo RBAC a los que se aplicaría el indicador. **Optional**

## <a name="response"></a>Respuesta

- Si se realiza correctamente, este método devuelve 200: código de respuesta aceptar y la entidad [Indicator](ti-indicator.md) creada o actualizada en el cuerpo de la respuesta.
- Si no se realiza correctamente: este método devuelve 400 - Solicitud mala. La solicitud incorrecta suele indicar un cuerpo incorrecto.

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
