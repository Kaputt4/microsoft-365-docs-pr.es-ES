---
title: Enumerar todas las recomendaciones
description: Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización.
keywords: api, graph api, api admitidas, get, recomendaciones de seguridad, Microsoft Defender para punto de conexión tvm api, Administración de amenazas y vulnerabilidades, api de Administración de amenazas y vulnerabilidades, mdvm
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: d1e88b8ba553d3e8ad88becf283caa94b8d00ef6
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67696999"
---
# <a name="list-all-recommendations"></a>Enumerar todas las recomendaciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización.


## <a name="api-description"></a>Descripción de la API

Devuelve información sobre todas las recomendaciones de seguridad que afectan a la organización.

*URL:* GET:/api/recommendations
<br>Admite [consultas de OData V4](https://www.odata.org/documentation/).
<br>Operadores compatibles con OData:
<br>```$filter```on: ```id```propiedades , ```productName```, ```vendor```, ```recommendedVersion```, ```recommendationCategory```, ```severityScore``````subCategory```, ```remediationType```, ```recommendedProgram```, , ```recommendedVendor```y ```status``` .
<br>```$top``` con un valor máximo de 10 000.
<br>```$skip```.
<br>Vea ejemplos en [consultas de OData con Microsoft Defender para punto de conexión](exposed-apis-odata-samples.md).

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API](apis-intro.md) para obtener más información.

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|SecurityRecommendation.Read.All|"Leer la información de recomendaciones de seguridad de Administración de amenazas y vulnerabilidades"
Delegado (cuenta profesional o educativa)|SecurityRecommendation.Read |"Leer la información de recomendaciones de seguridad de Administración de amenazas y vulnerabilidades"

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/recommendations
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 Ok con la lista de recomendaciones de seguridad en el cuerpo.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

### <a name="response"></a>Respuesta

Aquí tiene un ejemplo de la respuesta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10" "va-_-microsoft-_-windows_11",
            "productName": "windows_10" "Windows_11",
            "recommendationName": "Update Windows 10" "Update Windows 11",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10" "Windows 11"
        }
        ...
     ]
}
```

## <a name="see-also"></a>Consulte también

- [Administración de vulnerabilidades de Microsoft Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Recomendaciones de seguridad de administración de vulnerabilidades](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
