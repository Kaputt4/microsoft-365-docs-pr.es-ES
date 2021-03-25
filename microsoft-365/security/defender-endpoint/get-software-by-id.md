---
title: Obtener software por identificador
description: Recupera una lista de puntuaciones de exposición por grupo de dispositivos.
keywords: apis, graph api, apis admitidas, get, software, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198594"
---
# <a name="get-software-by-id"></a>Obtener software por identificador

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera los detalles del software por identificador.

## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación | Software.Read.All | 'Leer información de software de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa) | Software.Read | 'Leer información de software de administración de amenazas y vulnerabilidades'

## <a name="http-request"></a>Solicitud HTTP
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a>Encabezados de solicitud

| Nombre        | Tipo | Descripción
|:--------------|:-------|:--------------|
| Authorization | Cadena | Portador {token}. **Obligatorio**.

## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 200 Aceptar con los datos de software especificados en el cuerpo. 


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a>Temas relacionados
- [Administración de vulnerabilidades basada & riesgos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventario & de software de vulnerabilidad](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
