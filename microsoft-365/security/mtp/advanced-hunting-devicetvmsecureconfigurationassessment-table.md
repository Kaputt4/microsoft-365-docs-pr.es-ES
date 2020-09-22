---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtén más información sobre los eventos de evaluación de seguridad de la administración de amenazas y vulnerabilidades en la tabla DeviceTvmSecureConfigurationAssessment del esquema de caza avanzada. Estos eventos proporcionan información del equipo, así como detalles de la configuración de seguridad, consecuencias e información sobre el cumplimiento.
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, amenaza & la administración de vulnerabilidades, TVM, administración de dispositivos, configuración de seguridad, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b186574cfc1307dfd8a01f7a77ef60bf91f4b162
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197002"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica para:**
- Protección contra amenazas de Microsoft



Cada una de las filas de la tabla `DeviceTvmSecureConfigurationAssessment`contiene un evento de evaluación para una configuración de seguridad específica de la administración de [amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.|
| `Timestamp` | datetime | Fecha y hora en que se generó el registro |
| `ConfigurationId` | cadena | Identificador único para una configuración específica |
| `ConfigurationCategory` | string | Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad |
| `ConfigurationSubcategory` | string | Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, describe funciones o características específicas. |
| `ConfigurationImpact` | string | Impacto valorado de la configuración en el resultado general de la configuración (1-10) |
| `IsCompliant` | booleano | Indica si la configuración o la directiva está configurada correctamente |

## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Información general sobre la Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
