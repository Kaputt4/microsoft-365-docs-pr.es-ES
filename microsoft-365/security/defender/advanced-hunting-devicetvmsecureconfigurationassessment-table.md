---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de evaluación de seguridad en la tabla DeviceTvmSecureConfigurationAssessment del esquema de búsqueda avanzada. Estos eventos proporcionan información del dispositivo, detalles de configuración de seguridad, impacto e información de cumplimiento.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: dc0e193167eb4cadf658a78de3a1fd497c76be5e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479630"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica para:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

Cada fila de la `DeviceTvmSecureConfigurationAssessment` tabla contiene un evento de evaluación para una configuración de seguridad específica de [Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.

Puede combinar esta tabla con la tabla [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) mediante `ConfigurationId` para, por ejemplo, ver la descripción del texto de la configuración desde la `ConfigurationDescription` columna de la `DeviceTvmSecureConfigurationAssessmentKB` tabla, en los resultados de la evaluación de la configuración.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Identificador único del dispositivo en el servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN) del dispositivo |
| `OSPlatform` | `string` | Plataforma del sistema operativo que se ejecuta en el dispositivo. Indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7.|
| `Timestamp` | `datetime` | Fecha y hora en que se generó el registro |
| `ConfigurationId` | `string` | Identificador único para una configuración específica |
| `ConfigurationCategory` | `string` | Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad |
| `ConfigurationSubcategory` | `string` | Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, la cadena describe funcionalidades o características específicas. |
| `ConfigurationImpact` | `string` | Impacto valorado de la configuración en el resultado general de la configuración (1-10) |
| `IsCompliant` | `boolean` | Indica si la configuración o la directiva está configurada correctamente |
| `IsApplicable` | `boolean` | Indica si la configuración o directiva se aplica al dispositivo. |
| `Context` | `string` | Información contextual adicional sobre la configuración o directiva |
| `IsExpectedUserImpact` | `boolean` | Indica si habrá impacto en el usuario si se aplica la configuración o la directiva. |

Puede probar esta consulta de ejemplo para devolver información sobre dispositivos con configuraciones de antivirus no compatibles junto con los metadatos de configuración pertinentes de la `DeviceTvmSecureConfigurationAssessmentKB` tabla:

```kusto
// Get information on devices with antivirus configurations issues
DeviceTvmSecureConfigurationAssessment
| where ConfigurationSubcategory == 'Antivirus' and IsApplicable == 1 and IsCompliant == 0
| join kind=leftouter (
    DeviceTvmSecureConfigurationAssessmentKB
    | project ConfigurationId, ConfigurationName, ConfigurationDescription, RiskDescription, Tags, ConfigurationImpact
) on ConfigurationId
| project DeviceName, OSPlatform, ConfigurationId, ConfigurationName, ConfigurationCategory, ConfigurationSubcategory, ConfigurationDescription, RiskDescription, ConfigurationImpact, Tags
```

## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)