---
title: Enumerar archivos de biblioteca
description: Obtenga información sobre cómo enumerar los archivos de biblioteca de respuestas en directo.
keywords: api, api de gráfico, api admitidas, get, dispositivos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1700fffa7014733b44c8ed03b8fdffae085644a9
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331283"
---
#  <a name="list-library-files"></a>Enumerar archivos de biblioteca 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Enumerar los archivos de biblioteca de respuestas en directo.

## <a name="limitations"></a>Limitaciones

1.  Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Introducción](apis-intro.md).

|Tipo de permiso                       |      Permiso          |  Nombre para mostrar de permisos | 
|-----------------|--------|---------------------------|  
| Aplicación                        | Library.Manage | Administrar biblioteca de respuestas en directo |
| Delegado (cuenta profesional o educativa) | Library.Manage | Administrar biblioteca de respuestas en directo |

## <a name="http-request"></a>Solicitud HTTP

```HTTP
GET https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="request-headers"></a>Encabezados de solicitud

| Nombre         |      Tipo                     | Descripción
|-----------------|--------|---------------------------|
| Authorization   | String | {token} de portador. Obligatorio. |

## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta 
Si se realiza correctamente, este método devuelve 200: código de respuesta aceptar con una colección de entidades de archivo de biblioteca de respuestas en directo.

## <a name="example"></a>Ejemplo

**Solicitud**

Este es un ejemplo de una solicitud que obtiene todos los archivos de biblioteca de respuestas en directo

```HTTP
GET https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```JSON
HTTP/1.1 200 Ok
Content-type: application/json
{
"\@odata.context": "https://api.securitycenter.microsoft.com
/api/\$metadata\#LibraryFiles",
"value": [
    {
    "fileName": "script1.ps1",
    "sha256": "6e212a0db618507c44e4ec8ee7499dfef7e5767e5f8d31144df3b96fd1145caf",
    "description": null,
    "creationTime": "2019-10-24T10:54:23.2009016Z",
    "lastUpdatedTime": "2019-10-24T10:54:23.2009016Z",
    "createdBy": "admin",
    "hasParameters": true,
    "parametersDescription": "test"
    },
    {
    "fileName": "script.sh",
    "sha256": "d0f3e3b0641dbf88ee39c822516e81a909d1d06d22341dd9b1f12aa5e5c027a2",
    "description": null,
    "creationTime": "2018-10-24T11:15:35.3688259Z",
    "lastUpdatedTime": "2018-10-24T11:15:35.3688259Z",
    "createdBy": "username",
    "hasParameters": false
    },
    {
    "fileName": "memdump.exe",
    "sha256": "fa70b87730290c0d30fe255d1dfb65de82f96286ebfeeb1d88ed3cc831329825",
    "description": "Process memory dump",
    "creationTime": "2018-10-24T10:54:23.2009016Z",
    "lastUpdatedTime": "2018-10-24T10:54:23.2009016Z",
    "createdBy": "admin",
    "hasParameters": false
    }
]
}
```


## <a name="related-topic"></a>Tema relacionado
- [Ejecutar respuesta directa](run-live-response.md) 