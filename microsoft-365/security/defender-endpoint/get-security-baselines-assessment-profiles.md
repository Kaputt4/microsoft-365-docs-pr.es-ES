---
title: Perfiles de evaluación de líneas base de seguridad
description: Proporciona información sobre las API de perfiles de evaluación de líneas de base de seguridad que extraen datos "Administración de amenazas y vulnerabilidades". Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
ms.prod: m365-security
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 2f02243686c943ad38c410a23dabca666aa35a15
ms.sourcegitcommit: 6e570b79944862c86735db455349b685d5b903b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67020448"
---
# <a name="list-all-security-baselines-assessment-profiles"></a>Enumerar todos los perfiles de evaluación de líneas de base de seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quieres experimentar Administración de vulnerabilidades de Microsoft Defender? Obtenga más información sobre cómo puede registrarse en la [versión de prueba de Administración de vulnerabilidades de Microsoft Defender versión preliminar pública](../defender-vulnerability-management/get-defender-vulnerability-management.md).

## <a name="1-get-security-baselines-assessment-profiles"></a>1. Obtención de perfiles de evaluación de líneas de base de seguridad

Esta API recupera una lista de todos los perfiles de evaluación de líneas de base de seguridad creados por la organización.

### <a name="11-parameters"></a>1.1 Parámetros

- Admite consultas de OData V4.
- Operadores compatibles con OData:
  - $filter en : id,name, operatingSystem, operatingSystemVersion, status, settingsNumber, passedDevices, totalDevices
  - $top con un valor máximo de 10 000.
  - $skip.

### <a name="12-http-request"></a>1.2 Solicitud HTTP

```http
GET:/api/baselineProfiles
```

### <a name="13-request-headers"></a>1.3 Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

### <a name="14-properties"></a>1.4 Propiedades

|Propiedad | Tipo | Descripción |
|:---|:---|:---|
|Id | Cadena | Identificador único del perfil de línea base específico.
|name | Cadena | Nombre del perfil.
|description | Cadena | Descripción del perfil.
|Referencia | Cadena | La prueba comparativa del perfil.
|version | Cadena | La versión del perfil.
|operatingSystem|Cadena|El perfil del sistema operativo aplicable.
|operatingSystemVersion|String|La versión del sistema operativo aplicable al perfil.
|status|Boolean|Indica si el perfil está activo o no
|complianceLevel|Cadena|Nivel de cumplimiento elegido para el perfil.
|settingsNumber|Int|Número de configuraciones seleccionadas en el perfil.
|createdBy|String|El usuario que creó este perfil.
|lastUpdatedBy|DateTime|El último usuario en modificar este perfil.
|createdOnTimeOffset|DateTime|Fecha y hora en que se creó el perfil.
|lastUpdateTimeOffset|DateTime|Fecha y hora en que se actualizó por última vez el perfil.
|passedDevices|Int|Número de dispositivos aplicables a este perfil que son compatibles con todas las configuraciones de perfil.
|totalDevices|Int|Número de dispositivos aplicables a este perfil.

## <a name="15-example"></a>Ejemplo 1.5

### <a name="151-request-example"></a>1.5.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/baselineProfiles
```

### <a name="162-response-example"></a>Ejemplo de respuesta 1.6.2

```json
{
    "@odata.context": "https:// api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicBaselineProfileDto)",
    "value":
    [
        {
            "id": "02bcbb9d-d197-479e-811e-1cd5a6f9f8fa",
            "name": "Windows 10 build 1909 CIS profile",
            "description": "important",
            "benchmark": "CIS",
            "version": "1.0.0",
            "operatingSystem": "Windows 10",
            "operatingSystemVersion": "1909",
            "status": true,
            "complianceLevel": "Level 1 (L1) - Corporate/Enterprise Environment (general use)",
            "settingsNumber": 51,
            "createdBy": "user@org.net",
            "lastUpdatedBy": null,
            "createdOnTimestampUTC": "0001-01-01T00:00:00Z",
            "lastUpdateTimestampUTC": "0001-01-01T00:00:00Z",
            "passedDevices": 0,
            "totalDevices": 10
        }
     ]
}
```

## <a name="see-also"></a>Vea también

- [Evaluación de las líneas base de la seguridad de las exportaciones](export-security-baseline-assessment.md)
- [Obtención de configuraciones de evaluación de líneas de base de seguridad](get-security-baselines-assessment-configurations.md)
