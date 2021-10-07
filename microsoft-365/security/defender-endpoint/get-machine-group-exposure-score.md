---
title: Puntuación de exposición de lista por grupo de dispositivos
description: Recupera una lista de puntuaciones de exposición por grupo de dispositivos.
keywords: api, api de gráfico, api admitidas, obtener, puntuación de exposición, grupo de dispositivos, puntuación de exposición de grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 03d3535ec972522313bbabeebc1743db3fb55009
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209854"
---
# <a name="list-exposure-score-by-device-group"></a>Puntuación de exposición de lista por grupo de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera la puntuación de exposición de cada grupo de máquinas.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
---|---|---
Aplicación|Score.Read.All|'Leer puntuación de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa)|Score.Read|'Leer puntuación de administración de amenazas y vulnerabilidades'

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
---|---|---
|Authorization|Cadena|Portador {token}. **Obligatorio**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 Ok, con una lista de la puntuación de exposición por datos de grupo de dispositivos en el cuerpo de la respuesta.

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

- [Administración de vulnerabilidades basada & riesgos](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Puntuación de & vulnerabilidad de amenazas](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
