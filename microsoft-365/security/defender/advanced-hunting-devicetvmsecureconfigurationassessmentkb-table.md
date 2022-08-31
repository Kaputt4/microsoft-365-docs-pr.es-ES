---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtenga información sobre las distintas configuraciones seguras evaluadas por Administración de vulnerabilidades de Microsoft Defender en la tabla DeviceTvmSecureConfigurationAssessmentKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades & amenazas, TVM, administración de dispositivos, configuración de seguridad, MITRE ATT&marco CK, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB, MDVM, Administración de vulnerabilidades de Microsoft Defender
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
ms.openlocfilehash: 6bcd0c404e807c14bac8d33fe5a4014b5207bf19
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481182"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

La `DeviceTvmSecureConfigurationAssessmentKB` tabla del esquema de búsqueda avanzada contiene información sobre las distintas configuraciones seguras comprobadas por [Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK.

Esta tabla no devuelve eventos ni registros. Se recomienda unir esta tabla a la tabla [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) mediante `ConfigurationId` para ver información de texto sobre las configuraciones de seguridad en las evaluaciones devueltas.

Por ejemplo, al consultar la `DeviceTvmSecureConfigurationAssessment` tabla, es posible que desee ver las `ConfigurationDescription` configuraciones de seguridad que a continuación se muestran en los resultados de la evaluación. Para ver esta información, una esta tabla a `DeviceTvmSecureConfigurationAssessment` using `ConfigurationId` y project `ConfigurationDescription`.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `ConfigurationId` | `string` | Identificador único para una configuración específica |
| `ConfigurationImpact` | `string` | Impacto valorado de la configuración en el resultado general de la configuración (1-10) |
| `ConfigurationName` | `string` | Nombre para mostrar de la configuración |
| `ConfigurationDescription` | `string` | Descripción de la configuración |
| `RiskDescription` | `string` | Descripción del riesgo asociado |
| `ConfigurationCategory` | `string` | Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad|
| `ConfigurationSubcategory` | `string` |Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, describe funciones o características específicas. |
| `ConfigurationBenchmarks` | `string` | Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar |
| `Tags` | `string` | Etiquetas que representan varios atributos usados para identificar o clasificar una configuración de seguridad |
| `RemediationOptions` | `string` | Acciones recomendadas para reducir o abordar los riesgos asociados |

Puede probar esta consulta de ejemplo para devolver los metadatos de configuración pertinentes junto con información sobre los dispositivos con configuraciones de antivirus no compatibles de la `DeviceTvmSecureConfigurationAssessment` tabla:

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