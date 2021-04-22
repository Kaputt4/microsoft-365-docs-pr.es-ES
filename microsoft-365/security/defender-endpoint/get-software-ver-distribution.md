---
title: Enumerar distribución de versión de software
description: Recupera una lista de la distribución de versiones de software de su organización
keywords: apis, api de gráficos, api admitidas, get, distribución de versiones de software, Api de Microsoft Defender para Endpoint tvm
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
ms.openlocfilehash: e47a97477500491f634e3f5134a32241bd68985b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935298"
---
# <a name="list-software-version-distribution"></a>Enumerar distribución de versión de software 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera una lista de la distribución de versiones de software de su organización. 

## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación | Software.Read.All | 'Leer información de software de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa) | Software.Read | 'Leer información de software de administración de amenazas y vulnerabilidades'

## <a name="http-request"></a>Solicitud HTTP
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a>Encabezados de solicitud

| Nombre        | Tipo | Descripción
|:--------------|:-------|:--------------|
| Authorization | Cadena | Portador {token}. **Obligatorio**.

## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 200 Ok con una lista de datos de distribuciones de software en el cuerpo. 


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Temas relacionados
- [Administración de vulnerabilidades basada & riesgos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventario & de software de vulnerabilidad](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
