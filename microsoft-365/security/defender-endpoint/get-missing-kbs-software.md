---
title: Obtención de KB que faltan por identificador de software
description: Recupera las actualizaciones de seguridad que faltan por identificador de software
keywords: api, graph api, api admitidas, get, list, file, information, software id, threat & vulnerability management api, Microsoft Defender para punto de conexión tvm api, mdvm, Administración de vulnerabilidades de Microsoft Defender
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: afa61d24804157c484912f158679ae8f9dd32357
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68190689"
---
# <a name="get-missing-kbs-by-software-id"></a>Obtención de KB que faltan por identificador de software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera los KB que faltan (actualizaciones de seguridad) por identificador de software.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API](apis-intro.md) para obtener más información.

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Software.Read.All|"Leer la información del software de administración de amenazas y vulnerabilidades"
Delegado (cuenta profesional o educativa)|Software.Read|"Leer la información del software de administración de amenazas y vulnerabilidades"

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a>Encabezado de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK, con los datos de kb que faltan en el software especificado en el cuerpo.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
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
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a>Temas relacionados

- [Administración de vulnerabilidades de Microsoft Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventario de software de Administración de vulnerabilidades de Defender](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
