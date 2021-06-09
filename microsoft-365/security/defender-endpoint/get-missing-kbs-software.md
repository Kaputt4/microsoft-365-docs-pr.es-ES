---
title: Obtener KBs ausentes por id. de software
description: Recupera las actualizaciones de seguridad que faltan por id. de software
keywords: apis, api de gráficos, api admitidas, get, list, file, information, software id, threat & administración de vulnerabilidades api, Api de Microsoft Defender para Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bbb3e5dfe94d5efb026e21a4cbd94fac45f36594
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845227"
---
# <a name="get-missing-kbs-by-software-id"></a>Obtener KBs ausentes por id. de software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera KBs ausentes (actualizaciones de seguridad) por identificador de software

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.

Tipo de permiso |   Permiso   |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |Software.Read.All |   'Leer información de software de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa) | Software.Read |   'Leer información de software de administración de amenazas y vulnerabilidades'

## <a name="http-request"></a>Solicitud HTTP

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a>Encabezado de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 Ok, con el software especificado que falta datos kb en el cuerpo.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```
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

- [Administración de vulnerabilidades basada & riesgos](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventario & de software de vulnerabilidad](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
