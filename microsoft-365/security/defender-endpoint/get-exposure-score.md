---
title: Obtener puntuación de exposición
description: Recupera la puntuación de exposición organizativa.
keywords: api, api de gráfico, api admitidas, obtener, puntuación de exposición, puntuación de exposición organizativa
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bc7e1cc6cb19f19fcd9cdd826a6df591abb388313f6680c74a6393e13decd3be
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53884811"
---
# <a name="get-exposure-score"></a>Obtener puntuación de exposición

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Recupera la puntuación de exposición organizativa.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
:---|:---|:---
Aplicación | Score.Read.All | 'Leer puntuación de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa) | Score.Read | 'Leer puntuación de administración de amenazas y vulnerabilidades'

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/exposureScore
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | String | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 Ok, con los datos de exposición en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a>Respuesta

Aquí tiene un ejemplo de la respuesta.

>[!NOTE]
>La lista de respuestas que se muestra aquí puede truncarse por brevedad. 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a>Recursos adicionales

- [Administración de vulnerabilidades basada & riesgos](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Puntuación de & vulnerabilidad de amenazas](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
