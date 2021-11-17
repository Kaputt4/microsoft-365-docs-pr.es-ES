---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de evaluación de seguridad en la tabla DeviceTvmSecureConfigurationAssessment del esquema de búsqueda avanzado. Estos eventos proporcionan información del dispositivo, detalles de configuración de seguridad, impacto e información de cumplimiento.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, amenaza & administración de vulnerabilidades, TVM, administración de dispositivos, configuración de seguridad, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3487ced09cfd0bbd3a25f8e8124f84a05368d290
ms.sourcegitcommit: bd43f08b4719ba984ea6712227508d4a281148cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2021
ms.locfileid: "61035975"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica para:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión


Cada una de las filas de la tabla `DeviceTvmSecureConfigurationAssessment`contiene un evento de evaluación para una configuración de seguridad específica de la administración de [amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.

Puede unir esta tabla a la tabla [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) con el fin de poder, por ejemplo, ver la descripción de texto de la configuración desde la columna de la tabla, en los resultados de la evaluación de `ConfigurationId` `ConfigurationDescription` `DeviceTvmSecureConfigurationAssessmentKB` configuración.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador único del dispositivo en el servicio |
| `DeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo |
| `OSPlatform` | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7.|
| `Timestamp` | datetime | Fecha y hora en que se generó el registro |
| `ConfigurationId` | cadena | Identificador único para una configuración específica |
| `ConfigurationCategory` | string | Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad |
| `ConfigurationSubcategory` | string | Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, la cadena describe funciones o características específicas. |
| `ConfigurationImpact` | string | Impacto valorado de la configuración en el resultado general de la configuración (1-10) |
| `IsCompliant` | booleano | Indica si la configuración o la directiva está configurada correctamente |
| `IsApplicable` | Booleano | Indica si la configuración o directiva se aplica al dispositivo |
| `Context` | string | Información contextual adicional sobre la configuración o la directiva |
| `IsExpectedUserImpact` | booleano | Indica si habrá impacto en el usuario si se aplica la configuración o la directiva |

Puede probar esta consulta de ejemplo para devolver información sobre dispositivos con configuraciones antivirus no compatibles junto con los metadatos de configuración relevantes de la `DeviceTvmSecureConfigurationAssessmentKB` tabla:

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
- [Información general sobre la Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)