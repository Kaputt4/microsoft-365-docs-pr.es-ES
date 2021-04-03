---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Para obtener información sobre las distintas configuraciones seguras evaluadas por la Administración de amenazas y vulnerabilidades, vea la tabla DeviceTvmSecureConfigurationAssessmentKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de &, TVM, administración de dispositivos, configuración de seguridad, marco de CK de MITRE ATT&, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 71ebcd759e9fb6fd39550975039eb58be13e6b84
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501157"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



La tabla `DeviceTvmSecureConfigurationAssessmentKB` en el esquema de búsqueda avanzada contiene información acerca de las distintas configuraciones seguras (por ejemplo, si un dispositivo tiene activadas las actualizaciones automáticas) que son evaluadas por la [Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `ConfigurationId` | string | Identificador único para una configuración específica |
| `ConfigurationImpact` | cadena | Impacto valorado de la configuración en el resultado general de la configuración (1-10) |
| `ConfigurationName` | string | Nombre para mostrar de la configuración |
| `ConfigurationDescription` | string | Descripción de la configuración |
| `RiskDescription` | string | Descripción del riesgo asociado |
| `ConfigurationCategory` | string | Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad|
| `ConfigurationSubcategory` | cadena |Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, describe funciones o características específicas. |
| `ConfigurationBenchmarks` | string | Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar |
| `Tags` | string | Etiquetas que representan varios atributos usados para identificar o clasificar una configuración de seguridad |
| `RemediationOptions` | cadena | Acciones recomendadas para reducir o solucionar los riesgos asociados |

## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Información general sobre la Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)