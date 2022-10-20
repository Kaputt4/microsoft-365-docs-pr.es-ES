---
title: Api de importación de indicadores
description: Obtenga información sobre cómo usar el lote De importación de Indicator API en Microsoft Defender para punto de conexión.
keywords: apis, api admitidas, submit, ti, indicator, update
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
ms.topic: conceptual
ms.custom: api
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: d22a686d4a1bac29002d15d876daa15f89a410d8
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621128"
---
# <a name="import-indicators-api"></a>Api de importación de indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Envía o Novedades lote de entidades [indicadoras](ti-indicator.md).

No se admite la notación CIDR para direcciones IP.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son de 30 llamadas por minuto.
2. Hay un límite de 15 000 [indicadores](ti-indicator.md) activos por inquilino.
3. El tamaño máximo del lote para una llamada API es 500.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Introducción](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Ti.ReadWrite|"Indicadores de lectura y escritura"
Application|Ti.ReadWrite.All|"Leer y escribir todos los indicadores"
Delegado (cuenta profesional o educativa)|Ti.ReadWrite|"Indicadores de lectura y escritura"

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
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
Indicadores|[Indicador](ti-indicator.md) de<de lista>|Lista de [indicadores](ti-indicator.md). **Required**

## <a name="response"></a>Respuesta

- Si se ejecuta correctamente, este método devuelve el código de respuesta 200 - OK con una lista de resultados de importación por indicador, vea el ejemplo siguiente.
- Si no se ejecuta correctamente: este método devuelve 400 - Solicitud incorrecta. La solicitud incorrecta suele indicar un cuerpo incorrecto.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a>Tema relacionado

- [Administrar indicadores](manage-indicators.md)
