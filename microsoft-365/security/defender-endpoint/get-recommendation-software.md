---
title: Obtener recomendaciones por software
description: Recupera una recomendación de seguridad relacionada con un software específico.
keywords: apis, api de gráficos, api admitidas, get, recomendación de seguridad, recomendación de seguridad para software, administración de amenazas y vulnerabilidades, api de administración de amenazas y vulnerabilidades
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
ms.openlocfilehash: 82479b0248ceee95321d269e3f48a4eeea3ad193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199506"
---
# <a name="get-recommendation-by-software"></a>Obtener recomendaciones por software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Recupera una recomendación de seguridad relacionada con un software específico.

## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   SecurityRecommendation.Read.All |   'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa) | SecurityRecommendation.Read |  'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'

## <a name="http-request"></a>Solicitud HTTP
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.


## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 200 Ok con el software asociado con las recomendaciones de seguridad en el cuerpo.


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a>Temas relacionados
- [Administración de vulnerabilidades basada & riesgos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Recomendación & seguridad de vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
