---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de evaluación de seguridad en la tabla DeviceTvmSecureConfigurationAssessment del esquema de búsqueda avanzado. Estos eventos de & de administración de vulnerabilidades proporcionan información del dispositivo, así como detalles de configuración de seguridad, impacto e información de cumplimiento.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades & amenazas, TVM, administración de dispositivos, configuración de seguridad, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 891bfcc775f8c8ebddea63d5490c1c9fef4e691a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907353"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica para:**
- Microsoft 365 Defender



Cada una de las filas de la tabla `DeviceTvmSecureConfigurationAssessment`contiene un evento de evaluación para una configuración de seguridad específica de la administración de [amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador único del dispositivo en el servicio |
| `DeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo |
| `OSPlatform` | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.|
| `Timestamp` | datetime | Fecha y hora en que se generó el registro |
| `ConfigurationId` | cadena | Identificador único para una configuración específica |
| `ConfigurationCategory` | string | Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad |
| `ConfigurationSubcategory` | string | Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, describe funciones o características específicas. |
| `ConfigurationImpact` | string | Impacto valorado de la configuración en el resultado general de la configuración (1-10) |
| `IsCompliant` | booleano | Indica si la configuración o la directiva está configurada correctamente |
| `IsApplicable` | boolean | Indica si la configuración o directiva se aplica al dispositivo |
| `Context` | string | Información contextual adicional sobre la configuración o la directiva |
| `IsExpectedUserImpactCompliant` | boolean | Indica si habrá impacto en el usuario si se aplica la configuración o la directiva |

## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Información general sobre la Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)