---
title: Obtener todas las vulnerabilidades por máquina y software
description: Recupera una lista de todas las vulnerabilidades que afectan a la organización por máquina y software
keywords: apis, graph api, apis admitidas, get, vulnerability information, Microsoft Defender for Endpoint tvm api
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 45c29a70f97c681e6236f4327fed8e344d9dc8ac
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301647"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>Enumerar vulnerabilidades por máquina y software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera una lista de todas las vulnerabilidades que afectan a la organización por [máquina](machine.md) y [software](software.md).

- Si la vulnerabilidad tiene un KB de corrección, aparecerá en la respuesta.
- Admite [consultas de OData V4](https://www.odata.org/documentation/).
- La consulta de OData `$filter` se admite en: `id` , , , , , , y `cveId` `machineId` `fixingKbId` `productName` `productVersion` `severity` `productVendor` propiedades.
<br>```$stop``` con un valor máximo de 10 000
<br>```$skip```

> [!TIP]
> Esta es una excelente API para [Power BI integración.](api-power-bi.md)

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Vulnerability.Read.All|'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa)|Vulnerability.Read|'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|String|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 Ok con la lista de vulnerabilidades en el cuerpo.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>Consulte también

- [Riesgos basados en Administración de amenazas y vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Vulnerabilidades de la organización](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
