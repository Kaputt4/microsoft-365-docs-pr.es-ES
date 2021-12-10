---
title: Obtener API de mapa CVE-KB
description: Obtenga información sobre cómo usar la API de mapa Get CVE-KB para recuperar un mapa de CVE a KBs y detalles cve en Microsoft Defender para endpoint.
keywords: apis, graph api, apis admitidas, get, cve, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ROBOTS: NOINDEX
ms.technology: mde
ms.custom: api
ms.openlocfilehash: d0672804d0d2a8221480fe76e4237114a88f4cfb
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168179"
---
# <a name="get-cve-kb-map-api"></a>Obtener API de mapa CVE-KB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera un mapa de CVE a KBs y detalles de CVE.

## <a name="permissions"></a>Permissions

El usuario necesita permisos de lectura.

## <a name="http-request"></a>Solicitud HTTP

```http
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado|Valor
:---|:---
Authorization|Portador {token}. **Necesario**.
Tipo de contenido|application/json

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente y existe la asignación: 200 Aceptar.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Este es un ejemplo de la solicitud:

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

### <a name="response-example"></a>Ejemplo de respuesta

Este es un ejemplo de la respuesta:

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    ...
}
```
