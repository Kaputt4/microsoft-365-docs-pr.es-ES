---
title: Tabla DeviceTvmSoftwareVulnerabilitiesKB en el esquema de búsqueda avanzada
description: Obtenga información sobre las vulnerabilidades de software a las que realiza un seguimiento Administración de vulnerabilidades de Microsoft Defender en la tabla DeviceTvmSoftwareVulnerabilitiesKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.openlocfilehash: b2ddcad3dcc72dce0c7f6b24d441befcd52b45ab
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68049460"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión



La `DeviceTvmSoftwareVulnerabilitiesKB` tabla del esquema de búsqueda avanzada contiene la lista de vulnerabilidades [Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) evalúa los dispositivos. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `CveId` | `string` | Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE) |
| `CvssScore` | `string` | La puntuación de gravedad asignada a la vulnerabilidad de seguridad por debajo de sistema de puntuación de vulnerabilidades común (CVSS) |
| `IsExploitAvailable` | `boolean` | Indica si el código que aprovecha la vulnerabilidad está disponible para el público |
| `VulnerabilitySeverityLevel` | `string` | Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas |
| `LastModifiedTime` | `datetime` | Fecha y hora en que se modificó por última vez el elemento o los metadatos relacionados |
| `PublishedDate` | `datetime` | Fecha en que se ha divulgado la vulnerabilidad al público |
| `VulnerabilityDescription` | `string` | Descripción de vulnerabilidad y riesgos asociados |
| `AffectedSoftware` | `string` | Lista de todos los productos de software afectados por la vulnerabilidad |

## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)