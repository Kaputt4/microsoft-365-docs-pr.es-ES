---
title: Obtener API de recopilación de estados de seguridad de máquinas
description: Recupera una colección de estados de seguridad de dispositivos con Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, device, security, state
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: api
ms.openlocfilehash: 91df2aab70b2bb8edb46700feefdae59df4ac68b
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166907"
---
# <a name="get-machines-security-states-collection-api"></a>OBTENER API de recopilación de estados de seguridad de Máquinas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** 
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera una colección de estados de seguridad de dispositivos.

## <a name="permissions"></a>Permissions

El usuario necesita permisos de lectura.

## <a name="http-request"></a>Solicitud HTTP

```http
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado|Valor
:---|:---
Authorization|Portador {token}. **Necesario**.
Tipo de contenido|application/json

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente: 200 Aceptar.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Este es un ejemplo de la solicitud.

```http
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

### <a name="response-example"></a>Ejemplo de respuesta

Este es un ejemplo de la respuesta:

El *identificador de* campo contiene el identificador de dispositivo e igual que el identificador de *campo** en la información de dispositivos.

```json
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        ...
    ]
}
```
