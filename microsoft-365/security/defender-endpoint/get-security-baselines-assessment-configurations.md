---
title: Configuraciones de evaluación de líneas base de seguridad
description: Proporciona información sobre las configuraciones de evaluación de líneas base de seguridad que extraen datos "Administración de vulnerabilidades de Microsoft Defender". Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 51de6f79f3293d488e10ec7a90c5d0f5e949b127
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694753"
---
# <a name="list-security-baselines-assessment-configurations"></a>Lista de configuraciones de evaluación de líneas base de seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quieres experimentar Administración de vulnerabilidades de Microsoft Defender? Obtenga más información sobre cómo puede registrarse en la [versión de prueba de Administración de vulnerabilidades de Microsoft Defender versión preliminar pública](../defender-vulnerability-management/get-defender-vulnerability-management.md).

## <a name="1-get-all-security-baselines-assessment-configurations"></a>1. Obtención de todas las configuraciones de evaluación de líneas de base de seguridad

Esta API recupera una lista de todas las configuraciones y configuraciones posibles de evaluación de líneas de base de seguridad para todas las pruebas comparativas disponibles.

### <a name="11-parameters"></a>1.1 Parámetros

- Admite consultas de OData V4
- Operadores compatibles con OData:
  - `$filter` on: `id`, `category`, , `name`, `CCE`
  - `$top` con un valor máximo de 10 000
  - `$skip`

### <a name="12-http-request"></a>1.2 Solicitud HTTP

```http
GET /api/baselineConfigurations 
```

### <a name="13-request-headers"></a>1.3 Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

### <a name="14-response"></a>1.4 Respuesta

Si se ejecuta correctamente, este método devuelve 200 Ok con la lista de configuraciones de línea base en el cuerpo.

### <a name="15-properties"></a>1.5 Propiedades

|Propiedad | Tipo | Descripción |
|:---|:---|:---|
|Id | Cadena | Identificador único de la configuración específica en la referencia comparativa de línea base.
|name | Cadena | El nombre de configuración en él aparece en la prueba comparativa.
|description | Cadena | Descripción de la configuración tal como aparece en la prueba comparativa.
|categoría | Cadena | La categoría de configuración tal como aparece en la prueba comparativa.
|complianceLevel|Cadena|Nivel de cumplimiento de la prueba comparativa en la que aparece esta configuración.
|`cce`|Int|El CCE para esta configuración tal como aparece en el punto de referencia.
|Fundamento |Cadena|La justificación de esta configuración tal como aparece en la prueba comparativa. Para la prueba comparativa de STIG, esto no se proporciona para esta configuración.

## <a name="16-example"></a>Ejemplo 1.6

### <a name="151-request-example"></a>1.5.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/baselineConfigurations
```

### <a name="162-response-example"></a>Ejemplo de respuesta 1.6.2

```json
{
    "@odata.context": " https://api-df.securitycenter.microsoft.com/api/$metadata#BaselineConfigurations ", 
    "value": [
        {
            "id": "1.1.8", 
            "name": "(L1) Ensure 'Allow importing of payment info' is set to 'Disabled'",
            "description": "<p xmlns:xhtml=\"http://www.w3.org/1999/xhtml\">This policy setting controls whether users are able to import payment information from another browser into Microsoft Edge as well as whether payment information is imported on first use.</p>",
            "category": "Microsoft Edge",
            "complianceLevels": [
                "Level 1 (L1) - Corporate/Enterprise Environment (general use)",
                "Level 2 (L2) - High Security/Sensitive Data Environment (limited functionality)"
            ],
            "cce": "",
            "rationale": "<p xmlns:xhtml=\"http://www.w3.org/1999/xhtml\">Having payment information automatically imported or allowing users to import payment data from another browser into Microsoft Edge could allow for sensitive data to be imported into Edge.</p>",
            "remediation": "<div xmlns:xhtml=\"http://www.w3.org/1999/xhtml\">\r\n  <p>\r\n    <p>\r\nTo establish the recommended configuration via GP, set the following UI path to                 <span class=\"inline_block\">Disabled</span></p>\r\n    <code class=\"code_block\">Computer Configuration\\Policies\\Administrative Templates\\Microsoft Edge\\Allow importing of payment info\r\n</code>\r\n    <p>\r\n      <strong>Note:</strong>\r\n This Group Policy path may not exist by default. It is provided by the Group Policy template                 <span class=\"inline_block\">MSEdge.admx/adml</span>\r\n that can be downloaded from Microsoft                 <a href=\"https://www.microsoft.com/en-us/edge/business/download\">here</a>\r\n.              </p>\r\n    <p class=\"bold\">Impact:</p>\r\n    <p>\r\n      <p>Users will be unable to perform a payment information import from other browsers into Microsoft Edge.</p>\r\n    </p>\r\n  </p>\r\n</div>",
            "benchmarkName": "CIS"
"recommendedValue": [ 
                "Equals '0'" 
            ], 
            "source": [ 
                "hkey_local_machine\\software\\policies\\microsoft\\windows\\eventlog\\security\\retention" 
            ]
        }, 
    ] 
} 
```

## <a name="see-also"></a>Vea también

- [Evaluación de las líneas base de la seguridad de las exportaciones](export-security-baseline-assessment.md)
- [Obtención de perfiles de evaluación de líneas de base de seguridad](get-security-baselines-assessment-profiles.md)
