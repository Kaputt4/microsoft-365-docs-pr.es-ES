---
title: API de indicadores de lista
description: Obtenga información sobre cómo usar la API de indicadores de lista para recuperar una colección de todos los indicadores activos en Microsoft Defender para endpoint.
keywords: apis, api pública, api admitidas, colección Indicators
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 868fd141cda3b3d92464a2d9247780e0e74d6de8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198558"
---
# <a name="list-indicators-api"></a>API de indicadores de lista

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Recupera una colección de todos los [indicadores activos](ti-indicator.md).
<br>Admite [consultas de OData V4](https://www.odata.org/documentation/).
<br>La consulta de OData ```$filter``` se admite en: ```indicatorValue``` , , , y ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` propiedades.
<br>Vea ejemplos en [consultas de OData con Microsoft Defender para endpoint](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora. 


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Ti.ReadWrite |  Indicadores de lectura y escritura
Aplicación |   Ti.ReadWrite.All |  'Leer y escribir todos los indicadores'
Delegado (cuenta profesional o educativa) |    Ti.ReadWrite |  Indicadores de lectura y escritura

## <a name="http-request"></a>Solicitud HTTP
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.


## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 200 código de respuesta Ok con una colección de [entidades Indicator.](ti-indicator.md)

>[!Note]
> Si la aplicación tiene el permiso "Ti.ReadWrite.All", se expone a todos los indicadores. De lo contrario, solo se mostrará a los indicadores que creó.

## <a name="example-1"></a>Ejemplo 1:

**Solicitud**

Este es un ejemplo de una solicitud que obtiene todos los indicadores

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a>Ejemplo 2:

**Solicitud**

Este es un ejemplo de una solicitud que obtiene todos los indicadores con la acción "AlertAndBlock". 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
