---
title: Obtención de KB que faltan por identificador de dispositivo
description: Recupera las actualizaciones de seguridad que faltan por identificador de dispositivo
keywords: apis, graph api, api admitidas, get, list, file, information, device id, threat & administración de vulnerabilidades api, Microsoft Defender para punto de conexión tvm api
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4a570851263b6a52193353e2c229e2df47b677e3
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65840329"
---
# <a name="get-missing-kbs-by-device-id"></a>Obtención de KB que faltan por identificador de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera los KB que faltan (actualizaciones de seguridad) por identificador de dispositivo

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/machines/{machineId}/getmissingkbs
```
## <a name="permissions"></a>Permisos

Se requiere el permiso siguiente para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md).

Tipo de permiso | Permiso | Nombre para mostrar del permiso
:---|:---|:---
Aplicación | Software.Read.All | "Leer la información del software de administración de amenazas y vulnerabilidades"

## <a name="request-header"></a>Encabezado de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK, con los datos de kb que faltan en el dispositivo especificado en el cuerpo.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a>Respuesta

Aquí tiene un ejemplo de la respuesta.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        }
        ]
}
```

## <a name="related-topics"></a>Temas relacionados

- [Administración de vulnerabilidades & amenazas basada en riesgos](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventario de software de vulnerabilidad & amenazas](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
