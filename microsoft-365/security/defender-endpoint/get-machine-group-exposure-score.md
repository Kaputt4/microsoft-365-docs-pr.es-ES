---
title: Enumeración de la puntuación de exposición por grupo de dispositivos
description: Recupera una lista de puntuaciones de exposición por grupo de dispositivos.
keywords: api, graph api, api admitidas, get, puntuación de exposición, grupo de dispositivos, puntuación de exposición del grupo de dispositivos
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: adc65d8cde79acd782b88c47bf281fe6cead61ea
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68642533"
---
# <a name="list-exposure-score-by-device-group"></a>Enumeración de la puntuación de exposición por grupo de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera la puntuación de exposición de cada grupo de máquinas.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Score.Read.All|"Leer la puntuación de administración de amenazas y vulnerabilidades"
Delegado (cuenta profesional o educativa)|Score.Read|"Leer la puntuación de administración de amenazas y vulnerabilidades"

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
---|---|---
|Authorization|Cadena|Portador {token}. **Obligatorio**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK, con una lista de la puntuación de exposición por los datos del grupo de dispositivos en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

### <a name="example-request"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="example-response"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Temas relacionados

- [Administración de vulnerabilidades de Microsoft Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Puntuación de exposición de Defender Vulnerability Management](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
